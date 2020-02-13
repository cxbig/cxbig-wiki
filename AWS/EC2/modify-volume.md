# Modify Volume | RBS | AWS

Last modified date: `2019-05-28`

## Manual

```
NAME
       modify-volume -

DESCRIPTION
       You  can modify several parameters of an existing EBS volume, including
       volume size, volume type, and IOPS capacity.  If  your  EBS  volume  is
       attached  to a current-generation EC2 instance type, you may be able to
       apply these changes without stopping the instance or detaching the vol-
       ume from it. For more information about modifying an EBS volume running
       Linux, see Modifying the Size, IOPS, or Type of an EBS Volume on  Linux
       .  For  more information about modifying an EBS volume running Windows,
       see Modifying the Size, IOPS, or Type of an EBS Volume on Windows .

       When you complete a resize operation on your volume, you need to extend
       the  volume's  file-system  size  to  take advantage of the new storage
       capacity. For information about extending  a  Linux  file  system,  see
       Extending  a Linux File System . For information about extending a Win-
       dows file system, see Extending a Windows File System .

       You can use CloudWatch Events to check the status of a modification  to
       an  EBS volume. For information about CloudWatch Events, see the Amazon
       CloudWatch Events User Guide . You can also track the status of a modi-
       fication  using  the  DescribeVolumesModifications API. For information
       about tracking status changes using either method, see Monitoring  Vol-
       ume Modifications .

       With  previous-generation  instance  types,  resizing an EBS volume may
       require detaching and reattaching the volume or stopping and restarting
       the  instance.  For  more information, see Modifying the Size, IOPS, or
       Type of an EBS Volume on Linux and Modifying the Size, IOPS, or Type of
       an EBS Volume on Windows .

       If you reach the maximum volume modification rate per volume limit, you
       will need to wait at least six hours before applying further  modifica-
       tions to the affected EBS volume.

       See also: AWS API Documentation

       See 'aws help' for descriptions of global parameters.

SYNOPSIS
            modify-volume
          [--dry-run | --no-dry-run]
          --volume-id <value>
          [--size <value>]
          [--volume-type <value>]
          [--iops <value>]
          [--cli-input-json <value>]
          [--generate-cli-skeleton <value>]

OPTIONS
       --dry-run | --no-dry-run (boolean)
          Checks  whether  you  have  the required permissions for the action,
          without actually making the request, and provides an error response.
          If  you have the required permissions, the error response is DryRun-
          Operation . Otherwise, it is UnauthorizedOperation .

       --volume-id (string)
          The ID of the volume.

       --size (integer)
          The target size of the volume, in GiB. The target volume  size  must
          be  greater  than  or equal to than the existing size of the volume.
          For information about available EBS volume  sizes,  see  Amazon  EBS
          Volume Types .

          Default: If no size is specified, the existing size is retained.

       --volume-type (string)
          The target EBS volume type of the volume.

          Default: If no type is specified, the existing type is retained.

          Possible values:

          o standard

          o io1

          o gp2

          o sc1

          o st1

       --iops (integer)
          The target IOPS rate of the volume.

          This is only valid for Provisioned IOPS SSD (io1 ) volumes. For more
          information, see Provisioned IOPS SSD (io1) Volumes .

          Default: If no IOPS  value  is  specified,  the  existing  value  is
          retained.

       --cli-input-json  (string) Performs service operation based on the JSON
       string provided. The JSON string follows the format provided by  --gen-
       erate-cli-skeleton.  If  other  arguments  are  provided on the command
       line, the CLI values will override the JSON-provided values. It is  not
       possible to pass arbitrary binary values using a JSON-provided value as
       the string will be taken literally.

       --generate-cli-skeleton (string) Prints a  JSON  skeleton  to  standard
       output without sending an API request. If provided with no value or the
       value input, prints a sample input JSON that can be used as an argument
       for  --cli-input-json.  If provided with the value output, it validates
       the command inputs and returns a sample output JSON for that command.

       See 'aws help' for descriptions of global parameters.

OUTPUT
       VolumeModification -> (structure)
          Information about the volume modification.

          VolumeId -> (string)
              The ID of the volume.

          ModificationState -> (string)
              The current modification state. The modification state  is  null
              for unmodified volumes.

          StatusMessage -> (string)
              A status message about the modification progress or failure.

          TargetSize -> (integer)
              The target size of the volume, in GiB.

          TargetIops -> (integer)
              The target IOPS rate of the volume.

          TargetVolumeType -> (string)
              The target EBS volume type of the volume.

          OriginalSize -> (integer)
              The original size of the volume.

          OriginalIops -> (integer)
              The original IOPS rate of the volume.

          OriginalVolumeType -> (string)
              The original EBS volume type of the volume.

          Progress -> (long)
              The modification progress, from 0 to 100 percent complete.

          StartTime -> (timestamp)
              The modification start time.

          EndTime -> (timestamp)
              The modification completion or failure time.
```

## Usage samples

```sh
### command to change size
aws ec2 modify-volume --volume-id vol-xxxxx --size 100 --volume-type gp2

### commands for result check
aws ec2 describe-volumes-modifications --volume-id vol-xxxxx
aws ec2 describe-volumes --volume-id vol-xxxxx
```

## Cases

### Enlarge primary volume size for Linux

#### 1. Update volume size

```sh
### Original 30GB, upgrade to 100GB
aws ec2 modify-volume --volume-id vol-xxxxx --size 100 --volume-type gp2

### Check result
aws ec2 describe-volumes-modifications --volume-id vol-xxxxx
aws ec2 describe-volumes --volume-id vol-xxxxx
```

#### 2. Check block size in Linux

Primary volume size is not automatically extended.

```sh
### Check block sizes
lsblk

# NAME          MAJ:MIN RM  SIZE RO TYPE MOUNTPOINT
# nvme0n1       259:0    0  100G  0 disk
# ├─nvme0n1p1   259:1    0   30G  0 part /
# └─nvme0n1p128 259:2    0    1M  0 part
```

#### 3. Extend primary partition size

```sh
### Enlarge the first partition
growpart /dev/nvme0n1 1

### Then, check again
lsblk

# NAME          MAJ:MIN RM  SIZE RO TYPE MOUNTPOINT
# nvme0n1       259:0    0  100G  0 disk
# ├─nvme0n1p1   259:1    0  100G  0 part /
# └─nvme0n1p128 259:2    0    1M  0 part
```

We can see volume size is upgraded.

#### 4. Check filesystem size

```sh
# Check filesystem size
df -h

# Filesystem                       Size  Used Avail Use% Mounted on
# ......
# /dev/nvme0n1p1                    30G  1.8G   28G   7% /
# ......
```

### 5. Extend filesystem size

```sh
### Resize filesystem size
resize2fs /dev/nvme0n1p1

### Check again
df -h

# Filesystem                       Size  Used Avail Use% Mounted on
# ......
# /dev/nvme0n1p1                    99G  1.8G   97G   2% /
# ......
```
