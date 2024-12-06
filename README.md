# TheGoguardianAppBypass
The first solution to bypass "TheGoguardianApp.exe".

# Steps
## Download a non-chromium kernel browser that can not "be managed by your organization"(ex. Firefox, Arc browser)
* Download the installer
  * If the download is blocked, please use this repository: https://github.com/1234567Yang/cf-proxy-ex
* Install
    * For some browser, the first download is online version, which is blocked as well, so after the install application lead you to a offline version, copy the value of `ctx` parameter from blocked.goguardian.com and decode with base64, this will let you see the original link
    * Use url decode to decode the url if you need to
    * Proxy the offline version link as well and download the browser

## Goto browser settings
* Search "proxy"
* Change to "do not use the system proxy"

## Run this in powershell
```
for ($i = 1; $i -le 100; $i++) {
    Stop-Process -Name "TheGoguardianApp" -Force
    Start-Sleep -Seconds 1.5
}
```
If it is not working, try this one:
```
for ($i = 1; $i -le 100; $i++) {
    Stop-Process -n "TheGoguardianApp"
    Start-Sleep -Seconds 1.5
}
```
