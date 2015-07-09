# How to remove MS Office from Mac completely

Reference document : [How to completely remove Office for Mac 2011](https://support.microsoft.com/en-us/kb/2398768)

1. Quit all opened MS Office applications
2. Delete application folder `/Microsoft Office 2011` in `/Application`
3. Delete `com.microsoft*` files under the `/Library/Preferences`
4. Delete `com.microsoft.office.licensing.helper.plist` under the `/Library/LaunchDaemons`
5. Delete `com.microsoft.office.licensing.helper` under the `/Library/PrivilegedHelperTools`
6. Delete `com.microsoft*` files under the `~/Library/Preferences/ByHost`
