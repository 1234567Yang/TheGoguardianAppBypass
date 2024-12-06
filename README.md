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

# Dear Goguardian developer:
I do not know what did you learned during your university life, but your application has a lot of BUGs.
If I were you, I would improve these things:
* For the Javascript injected (`MutationObserver`), save the element changed into an array and use `setTimeout` to avoid lagging (Google translate), and you can also set `var max` to avoid the website continue changing element that you can not detect.
* I do not know what did you inject to the html body, but it messes up with the element positions a lot, why not just inject `<script>` in the very beginning of the body, as browser will auto parse it correctly.
* For the front end, using C# is not a good idea, as you need to detect a lot of websites, and C++ is a better idea
* Also add an Virtual Network Card like Cloudflare Warp, and change the CA of the computer, for those applications which do not follow system proxy rule
  * This also allow you to detect any VPN services(via traffic characteristics. ex. ShadowSocks, Hysteria2), you might want to see https://github.com/apernet/OpenGFW
* Also screenshot the website and use OCR and other technology to detect the webpage

Hopefully these suggestions will help you fulfill your dictatorial ambitions
