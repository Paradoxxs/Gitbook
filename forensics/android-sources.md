# Device information

## Calendar Items and Timezone information
````
/data/com.android.providers.calendar/databases/calendar.db
````


## Lock settings information

````
/data/com.android.providers.settings/databases/settings.db

````
 
````
/data/com.android.providers.settings/databases/settings.db-WAL
````

````
/data/com.android.providers.settings/databases/locksettings.db

````


````
/data/com.android.providers.settings/databases/locksettings.db-WAL
````
 
## Activity on device related to installed SIM (ICCID and Google Account included)

````
/data/com.google.android.gms/shared_prefs/Checkin.xml
````


## Fitness settings network settings other settings

````
/data/com.google.android.gsf/databases/gservices.db
````


## Timezone (Up to Android 8)

````
/Property/persist.sys.timezone
````


## Timezone (From Android 9)
````
/Property/persistent_properties
````


## Passcode requirements and policies. Syncing info may exist

````
/system/device_policies.xml
````
 

## Lock settings information

````
/system/locksettings.db
````
 
 
## Lock settings information
````
/system/locksettings.db-WAL
````


## Timezone
````
/system/netpolicy.xml
````
 

## Sim card and phone number information
````
/system/SimCard.dat
````




# Account and password information

## Email accounts 3rd party app data and messages associated with Email notifications Email accounts 3rd party app data and messages associated with Email notifications
````
/data/com.android.email/databases/EmailProvider.db
````
 Account Email AddressCache Mailbox*


## Login info
````
/data/com.android.providers.contacts/databases/contacts2.db
````

 accounts

## Username and passwords

````
/data/com.android.providers.settings/*
````

## Last account used on Google PlayStore (Android 9 and above)
````
/data/com.android.vending/shared_prefs/lastaccount.xml
````

## Backup account email address

````
/data/com.google.android.gms/shared_prefs/BackupAccount.xml
````

## Google Account Information
````
/data/com.google.android.googlequicksearchbox/databases/app_icons.db
````

````
/data/com.google.android.googlequicksearchbox/databases/launcher.db
````
 

````
/data/com.google.android.googlequicksearchbox/databases/opa_history
````

## Fitness settings network settings other settings
````
/data/com.google.android.gsf/databases/gservices.db
````


## Additional accounts (could also be system_de or accounts_de)
````
/system_ce/0/accounts_ce.db
````


````
/system_de/0/accounts_de.db
````
 


## Hotspot Passwords
````
/misc/wifi/softap.conf 
````
 
 
## Wi-Fi Network Password
````
/misc/wifi/wpa_supplicant.conf
````

## User account information
````
/system/accounts*.db
````
 
````
/system/sync/accounts.xml
````
 
````
/system/users/0/0.xml
````
 




# System settings

## Preference files

````
/data/com.google.android.gms/shared_prefs/*
````
 


## Fitness settings network settings other settings
````
/data/com.google.android.gsf/databases/gservices.db
````
 

## Application snapshots

````
/system/recent_images/*.png
````
 
````
/system_ce/recent_images/*.png
````


## Global settings
````
/system/users/0/settings_global.xml
````
 


 
## Secure Settings
````
/system/users/0/settings_secure.xml 
````

 
## System Settings


````
/system/users/0/settings_system.xml
````



# User settings

## Calendar Items and Timezone information
````
/data/com.android.providers.calendar/databases/calendar.db
````
 

## Dictionary Files (Keylogging)

````
/data/com.android.providers.userdictionary/databases/user_dict.db
````
 

## Application User and Location traces


````
/data/com.google.android.gms/databases/NetworkUsage.db
````
 


````
/data/com.google.android.gms/databases/ns.db
````
 



````
/data/com.google.android.gms/databases/reminders.db
````


## Google preferences 
````
/data/com.google.android.gsf/databases/googlesettings.db
````
 


## Fitness settings network settings other settings

````
/data/com.google.android.gsf/databases/gservices.db
````
 
## Dictionary Files (Keylogging) SwiftKey folder name may vary

````
/data/com.sec.android.inputmethod/Swiftkey/user/dynamic.lm
````
 




# Comms

## Call logs (From Android 7)
````
/data/com.android.providers.contacts/databases/calllog.db
````
 calls


## Call logs (Up to Android 6)
````
/data/com.android.providers.contacts/databases/contacts2.db
````
 calls


## SMS/MMS
````
/data/com.android.providers.telephony/databases/mmssms.db
````
 sms and part


## RCS/Android Messages (refer to notebook for query)
````
/data/com.google.android.apps.messaging/databases/bugle.db
````
 


## Call logs
````
/data/com.google.android.dialer/databases/dialer.db
````
 


## Gmail snippets
````
/data/com.google.android.gm/databases/<mail-name>.db
````
 conversations and messages


## Email information
````
/data/com.google.android.gm/databases/bigTopDataDB.<user-id>
````
 null



````
/data/com.google.android.gm/databases/EmailProvider.db
````
 null


## SMS/MMS
````
/data/com.google.android.gms/databases/icing_mmssms.db
````
 



````
/data/com.google.android.gms/databases/ipa_mmssms.db
````
 

## Call logs
````
/data/com.sec.android.provider.logsprovider/databases/logs.db
````
 logs




# Multimedia

## Traces to SD card used in the device. This is stored on the phone.
````
/data/com.android.providers.media/databases/external*.db
````

````
/data/com.android.providers.media/databases/external*.db-WAL
````
 


## Camera Photos information
````
/data/com.google.android.apps.photos/databases/gphotos0.db
````
 local_media


## Camera Photo - Samsung Devices
````
/data/com.samsung.cmh/databases/cmh.db
````
 files



````
/data/com.samsung.storyservice/databases/dme.db
````
 info


````
/data/com.samsung.visionprovider/databases/visionprovider.db
````
 files


## Acts like SD card
````
/media/
````
 




# Browser

## Internet History
````
/data/com.android.browser/app_databases/*
````


````
/data/com.android.browser/app_geolocation/GeolocationPermissions.db
````

````
/data/com.android.browser/databases/Browser.db
````

````
/data/com.android.browser/databases/browser2.db
````

````
/data/com.android.browser/databases/webview.db
````

````
/data/com.android.browser/databases/webviewCache.db
````
 
````
/data/com.android.email/webviewCache.db
````
 




# Network connection

## USB Bluetooth NFC and other connects - Acquisition connection tracked here

````
/data/com.android.connectivity.metrics/databases/events.db
````
 completed_events_requests


## Wireless network and MAC addresses
````
/data/com.google.android.gms/databases/herrevad
````

## Cellular and WiFi


````
/data/com.google.android.locations/files/cache.cell
````

````
/data/com.google.android.locations/files/cache.wifi
````



## Wireless network
````
/misc/wifi/WifiConfigStore.xml
````
 




# Syncing artifacts

## Google Docs

````
/data/com.google.android.apps.docs.editors.docs/databases/*
````
 
 
## Google sheets

````
/data/com.google.android.apps.docs.editors.sheets/databases/*
````

## Google slides

````
/data/com.google.android.apps.docs.editors.slides/databases/*
````
 

## Google Docs

````
/data/com.google.android.apps.docs/databases/* 
````
 

 
## Sync activity

````
/data/com.google.android.apps.genie.geniewidget/databases/newsweather.db
````


## Sync activity - contacts
````
/data/com.google.android.gms/databases/peoplelog.db
````
 


## Sync Activity
````
/data/com.google.android.gms/shared_prefs/com.google.android.gms.auth.authzen.cryptauth.SyncManager.proximity_features.xml
````
 

## Synced Accounts

````
/system/sync/accounts.xml
````
 




# Location artifacts

## Maps
````
/data/com.google.android.apps.maps/databases/da_destination_history
````
 destination history

## Search history Maps

````
/data/com.google.android.apps.maps/databases/gmm_storage.db
````
 


## Maps
````
/data/com.google.android.apps.maps/databases/search_history.db
````
 history and suggestions


## Syncing

````
/data/com.google.android.apps.maps/databases/gmm_sync.db
````
 
## Location artifacts

````
/data/com.sec.android.daemonapp.db/weatherClock
````


## EXIF data with location info


````
/Media/0/DCIM/Camera
````
 



# Application usage

## APK files for installed applications
````
/app/*
````
 


## .dex/.oat/.art files for installed applications
````
/dalvik-cache
````
 

## Application Data Files

````
/data/\Application Folder\
````
 

## Application traces

````
/data/com.android.vending/databases/data_usage.db
````
 app_data_usage


## Application traces
````
/data/com.android.vending/databases/frosting.db
````
 frosting


## Application traces
````
/data/com.android.vending/databases/install_queue.db
````
 install_requests


## Application traces
````
/data/com.android.vending/databases/library.db
````
 ownership


## Application traces
````
/data/com.android.vending/databases/localappstate.db
````
 appstate


## Application traces
````
/data/com.android.vending/databases/notification_cache
````
 notifications


## Application traces
````
/data/com.android.vending/databases/package_verification.db
````
 verification_cache


## Application traces
````
/data/com.android.vending/databases/suggestions.db
````
 suggestions


## Application traces
````
/data/com.android.vending/databases/verify_apps.db
````
 


## Application traces
````
/data/com.google.android.gms/databases/config.db
````
 main


## Application traces
````
/data/com.google.android.gms/databases/gass.db
````
 app_info



````
/data/com.google.android.gms/databases/gcm_registrar.db
````
 packages



````
/data/com.google.android.gms/databases/google_app_measurement.db
````
 


## Battery Usage Stats - Contains Application Usage information
````
/data/com.google.android.gms/shared_prefs/batterystats.xml
````
 


## Google App searches installed applications and more
````
/data/com.google.android.googlequicksearchbox/*
````
 
 

## Application traces (Samsung devices)
````
/data/com.samsung.android.providers.context.databases.ContextLog_0.db
````
 


## Application artifacts (even after deleted)
````
/data/com.sec.android.app.launcher/databases/launcher.db
````
 


## Battery Usage Stats - Contains Application Usage information
````
/data/data/com.google.android.gms/files/batterystatsdumpsystask.gz
````
 


## Application permissions
````
/system/appops.xml
````
 

## Battery Usage Stats - Contains Application Usage information

````
/system/batterystats.bin
````
 



````
/system/batterystats-checkin.bin
````
 



````
/system/batterystats-daily.xml
````
 


## Application Usage

````
/system/dmappmgr.db
````
 


````
/system/job/jobs.xml
````
 

## Application notifications

````
/system/notification_log.db
````
 


## Application permissions and metadata
````
/system/packages.list
````
 


## Application permissions
````
/system/packages.xml
````
 

## Application Usage Stats

````
/system/usagestats/0/*
````



## Application Usage
````
/system/users/0/app_idle_stats.xml
````
 


## Application snapshots
````
/system_ce/0/recent_images/*.png
````
 


## Recent Tasks
````
/system_ce/0/recent_tasks/*.xml
````
 




# Native apps

## Calendar
 Calendar Items
````
/data/com.android.providers.calendar/databases/calendar.db
````

## Contacts
 Calendar Items
````
/data/com.android.providers.contacts/databases/contacts2.db
````

## Call Logs
 Calendar Items
````
/data/com.android.providers.contacts/databases/contacts2.db
````

## Call Logs
 Calendar Items
````
/data/com.android.providers.contacts/databases/calllog.db
````

## Downloads
 Calendar Items
````
/data/com.android.providers.downloads/databases/downloads.db
````

## Contacts
 Calendar Items
````
/data/com.google.android.gms/databases/icing_contacts.db
````

## MMS/SMS
 Calendar Items
````
/data/com.google.android.gms/databases/icing_mmssms.db
````

## MMS/SMS
 Calendar Items
````
/data/com.google.android.gms/databases/ipa_mmssms.db
````

## Android Pay
 Calendar Items
````
/data/com.google.android.gms/databases/android_pay
````

## Google+ Contacts
 Calendar Items

````
/data/com.google.android.gms/databases/pluscontacts.db
````


