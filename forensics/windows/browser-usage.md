# Browser usage



### Account records

Records number of times visited

* Internet Explorer
  * IE8-9: %USERPROFILE%\AppData\Roaming\Microsoft\Windows\IEDownloadHistory\index.dat
  * IE10-11: %USERPROFILE%\AppData\Local\Microsoft\Windows\WebCache\WebCacheV\*.dat
* Firefox
  * v3-25: %userprofile%\AppData\Roaming\Mozilla\ Firefox\Profiles.default\downloads.sqlite
  * v26+: %userprofile%\AppData\Roaming\Mozilla\ Firefox\Profiles.default\places.sqlite Table:moz\_annos
* Chrome
  * Win7/8/10: %USERPROFILE%\AppData\Local\Google\Chrome\User Data\Default\History



### Cookies

Cookies give insight into websites visted and activity

* Internet Explorer
  * IE6-8: %USERPROFILE%\AppData\Roaming\Microsoft\Windows\Cookies
  * IE10: %USERPROFILE%\AppData\Roaming\Microsoft\Windows\Cookies
  * IE11: %USERPROFILE%\AppData\Local\Microsoft\Windows\INetCookies
* Firefox
  * XP: %USERPROFILE%\Application Data\Mozilla\Firefox\Profiles.default\ cookies.sqlite
  * Win7/8/10: %USERPROFILE%\AppData\Roaming\Mozilla\Firefox\Profiles.default\ cookies.sqlite
* Chrome
  * XP: %USERPROFILE%\Local Settings\ApplicationData\Google\Chrome\User Data\Default\ Local Storage
  * Win7/8/10: %USERPROFILE%\AppData\Local\Google\Chrome\User Data\Default\Local Storage



### History

Records of website visited

* Internet Explorer
  * IE6-7: %USERPROFILE%\Local Settings\History\History.IE5
  * IE8-9: %USERPROFILE%\AppData\Local\Microsoft\Windows\History\ History.IE5
  * IE10, 11, Edge: %USERPROFILE%\AppData\Local\Microsoft\Windows\ WebCache\WebCacheV\*.dat
* Firefox
  * XP: %USERPROFILE%\Application Data\Mozilla\Firefox\Profiles.default\places.sqlite
  * Win7/8/10: %USERPROFILE%\AppData\Roaming\Mozilla\Firefox\ Profiles.default\places.sqlite
* Chrome
  * XP: %USERPROFILE%\Local Settings\Application Data\Google\Chrome\User Data\Default\History
  * Win7/8/10: %USERPROFILE%\AppData\Local\Google\Chrome\User Data\ Default\History



### Cache

Cache for web page components to speed up site load time

* Internet Explorer
  * IE8-9: %USERPROFILE%\AppData\Local\Microsoft\Windows\Temporary Internet Files\Content.IE5
  * IE10: %USERPROFILE%\AppData\Local\Microsoft\Windows\Temporary Internet Files\Content.IE5
  * IE11: %USERPROFILE%\AppData\Local\Microsoft\Windows\INetCache\IE
* Edge: %USERPROFILE%\AppData\Local\Packages\microsoftc
* Firefox
  * XP: %USERPROFILE%\Local Settings\ApplicationData\Mozilla\Firefox\ Profiles.default\Cache
  * Win7/8/10: %USERPROFILE%\AppData\Local\Mozilla\Firefox\ Profiles.default\Cache
* Crome
  * XP: %USERPROFILE%\Local Settings\Application Data\Google\Chrome\User Data\Default\Cache - data\_# and f\_######
  * Win7/8/10: %USERPROFILE%\AppData\Local\Google\Chrome\User Data\ Default\Cache\ - data\_# and f\_######


### Browser download manager

little-known fact about the IE History is that the information stored in the history files is not just related to Internet browsing. The history also records local and remote (via network shares) file access, giving us an excellent means for determining which files and applications were accessed on the system, day by day.

Firefox

* XP:
  * %userprofile%\Application Data\Mozilla\ Firefox\Profiles.default\downloads.sqlite
* Win7/8/10:
  * %userprofile%\AppData\Roaming\Mozilla\ Firefox\Profiles.default\downloads.sqlite

Internet Explorer:

* IE6-7
  * %USERPROFILE%\LocalSettings\History\History.IE5
* IE8-9
  * %USERPROFILE%\AppData\Local\Microsoft\WindowsHistory\History.IE5
* IE10-11
  * %USERPROFILE%\AppData\Local\Microsoft\Windows\WebCache\WebCacheV\*.dat


## Session restore

Crash recovery

* Internet Explorer Win7/8/10:
  * %USERPROFILE%/AppData/Local/Microsoft/Internet Explorer/ Recovery
* Firefox Win7/8/10
  * %USERPROFILE%\AppData\Roaming\Mozilla\Firefox\ Profiles.default\sessionstore.js
* Chrome Win7/8/10:
  * %USERPROFILE%\AppData\Local\Google\Chrome\User Data\ Default\ Files = Current Session, Current Tabs, Last Session, Last Tabs

### Super cookies

local stored objects (LSO) or flash cookies

```
%appdata%Roaming\macromedia\Flashplayer\#sharedObjects\<randomprofileid>
```
