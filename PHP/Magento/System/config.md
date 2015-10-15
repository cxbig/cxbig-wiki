# Magento - System Configuration

## File location

```
<Package>/<Module>/etc/system.xml
```

## Tricky for `label` definition

Normally, we only fill text into `label`. Like:

```
<label>My Label</label>

or

<label><![CDATA[My Label]]></label>
```

But, we can add a little bit more inside. Like:

```
<label><![CDATA[<img width="16" height="16" title="" alt="" style="vertical-align: top; margin-right: 5px;" src="/url/to/image.jpg" />My Label]]></label>

or

<label><![CDATA[<img width="16" height="16" title="" alt="" style="vertical-align: top; margin-right: 5px;" src="data:image/png;base64,iVBOR...ggg==" />My Label]]></label>
```
