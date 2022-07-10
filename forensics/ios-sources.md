
# Device info

##  Operating system version

path: /private/var/installd/Library/MobileInstallation/LastBuildInfo.plist
- BFU: Y
- Backup: Y
- Sysdiagnose: N


##  Lock/Device Passcode Info (0=unlocked 1=locked) (Up to iOS 9)
path: /private/var/mobile/Library/CoreDuet/coreduetd.db
- BFU: N
- Backup: N
- Sysdiagnose: N

##  Mobile Activation Logs
path: /private/var/mobile/Library/Logs/mobileactivationd/

- BFU: Y
- Backup: N
- Sysdiagnose: Y

##  May show older iOS versions used
path: /private/var/mobile/Library/Preferences/com.apple.AdLib.plist
- BFU: Y
- Backup: Y
- Sysdiagnose: N

##  Last Boot Time
path: /private/var/mobile/Library/Preferences/com.apple.aggregated.plist
- BFU: Y
- Backup: Y
- Sysdiagnose: N

##  IMSIs
path: /private/var/mobile/Library/Preferences/com.apple.mmcs.plist 
- BFU: Y
- Backup: Y
- Sysdiagnose: N

##  Device name
path: /private/var/mobile/Library/Preferences/com.apple.mobilegestalt.plist
- BFU: Y
- Backup: Y
- Sysdiagnose: N

##  Time settings
path: /private/var/mobile/Library/Preferences/com.apple.preferences.datetime.plist
- BFU: Y
- Backup: Y
- Sysdiagnose: N

##  Airplane mode (on/off)
path: /private/var/mobile/Library/Preferences/com.apple.preferences.network.plist

path: /private/var/preferences/SystemConfiguration/com.apple.radios.plist

path: /private/var/root/Library/Preferences/com.apple.preferences.network.plist

- BFU: Y
- Backup: Y
- Sysdiagnose: N

##  Disk usage
path: /private/var/mobile/Library/Preferences/com.apple.Preferences.plist
- BFU: Y
- Backup: Y
- Sysdiagnose: N

##  Language Country info Device IDs
path: /private/var/mobile/Library/Preferences/com.apple.purplebuddy.plist
- BFU: Y
- Backup: Y
- Sysdiagnose: N

##  Auto Time and Auto Time Zone settings
path: /private/var/mobile/Library/Preferences/com.apple.timed.plist
- BFU: Y
- Backup: Y
- Sysdiagnose: N

##  Network IP WiFi Cellular Information
path: /private/var/preferences/SystemConfiguration/com.apple.networkidentification.plist
- BFU: Y
- Backup: Y
- Sysdiagnose: N


##  Wi-Fi Mac Addresses
path: /private/var/preferences/SystemConfiguration/NetworkInterfaces.plist
- BFU: Y
- Backup: N
- Sysdiagnose: Y

##  Network and VPN information
path: /private/var/preferences/SystemConfiguration/preferences.plist
- BFU: Y
- Backup: Y
- Sysdiagnose: N

##  Computer Trust/Pair certificates
path: /private/var/root/Library/Lockdown/escrow_records/

path: /private/var/root/Library/Lockdown/pair_records/

- BFU: Y
- Backup: N
- Sysdiagnose: N


##  Device Info (IMEI Phone Number Network Carrier ICCIDs IMSIs etc.)
path: /private/var/wireless/Library/Preferences/com.apple.commcenter.plist
- BFU: Y
- Backup: Y
- Sysdiagnose: N




# Account and password info

##  Account information
path: /private/var/mobile/Library/Accounts/Accounts3.sqlite
- BFU: Y
- Backup: Y
- Sysdiagnose: N

##  Account information used to set up apps (Email # etc) 
path: /private/var/mobile/Library/DataAccess/
- BFU: Y
- Backup: Y
- Sysdiagnose: N

##  Email sync data
path: /private/var/mobile/Library/DataAccess/AccountInformation.plist
- BFU: Y
- Backup: Y
- Sysdiagnose: N

##  iCloud Email account information
path: /private/var/mobile/Library/DataAccess/iCloud-[iCloud email account name/.mboxCache.plist
- BFU: Y
- Backup: Y
- Sysdiagnose: N

##  Health data personal data iOS version info etc.
path: /private/var/mobile/Library/Health/healthdb.sqlite

path: /private/var/mobile/Library/Health/healthdb_secure.sqlite

- BFU: N
- Backup: Y
- Sysdiagnose: N


##  Medical Information (bloodtype organ donor name DOB etc.)
path: /private/var/mobile/Library/MedicalID/MedicalIDData.Archive

- BFU: N
- Backup: Y
- Sysdiagnose: N

##  Email accounts pushed to device
path: /private/var/mobile/Library/Preferences/com.apple.accountsettings.plist 
- BFU: Y
- Backup: Y
- Sysdiagnose: N

##  Blocked Dialers
path: /private/var/mobile/Library/Preferences/com.apple.cmfsyncagent.plist

- BFU: Y
- Backup: Y
- Sysdiagnose: N

##  Phone number
path: /private/var/mobile/Library/Preferences/com.apple.commcenter.shared.plist

- BFU: Y
- Backup: Y
- Sysdiagnose: N

##  Facetime phone number in use SMS phone number user accounts
path: /private/var/mobile/Library/Preferences/com.apple.conference.plist 

- BFU: Y
- Backup: Y
- Sysdiagnose: N

##  Last Metrics Attempts (usage information)
path: /private/var/mobile/Library/Preferences/com.apple.contacts.donation-agent.plist

- BFU: Y
- Backup: Y
- Sysdiagnose: N

##  Activity throttling
path: /private/var/mobile/Library/Preferences/com.apple.contextstored.plist 

path: /private/var/mobile/Library/Preferences/com.apple.coreduetd.plist


- BFU: Y
- Backup: Y
- Sysdiagnose: N


##  iCloud login information
path: /private/var/mobile/Library/Preferences/com.apple.corerecents.recentsd.plist

- BFU: Y
- Backup: Y
- Sysdiagnose: N

##  Last successful email address used to login to cloud
path: /private/var/mobile/Library/Preferences/com.apple.FeedbackAssistant.plist

- BFU: Y
- Backup: Y
- Sysdiagnose: N

##  iCloud account information
path: /private/var/mobile/Library/Preferences/com.apple.homesharing.plist

- BFU: Y
- Backup: Y
- Sysdiagnose: N

##  Find My iPhone settings
path: /private/var/mobile/Library/Preferences/com.apple.icloud.findmydeviced.FMIPAccounts.plist

- BFU: Y
- Backup: Y
- Sysdiagnose: N

##  Profiles and restrictions
path: /private/var/mobile/Library/UserConfigurationProfiles/

- BFU: Y
- Backup: Y
- Sysdiagnose: N

##  Account information
path: /private/var/preferences/SystemConfiguration/com.apple.accounts.exists.plist

- BFU: Y
- Backup: Y
- Sysdiagnose: N

##  Last - Backup computer iCloud - Backup Settings Device info
path: /private/var/root/Library/Lockdown/data_ark.plist

- BFU: Y
- Backup: N
- Sysdiagnose: N

##  Last iCloud account
path: /private/var/wireless/Library/preferences/com.apple.commcenter.callservices.plist

- BFU: Y
- Backup: N
- Sysdiagnose: N


# System setting

##  Mobile Applications Installation Logs
path: /private/installd/Library/Logs/MobileInstallation/mobile_installation.log.*

- BFU: Y
- Backup: N
- Sysdiagnose: Y

##  Application Folders
path: /private/var/mobile/Containers/ 

- BFU: Y
- Backup: Y
- Sysdiagnose: N

##  Logs of cleared notifications
path: /private/var/mobile/Library/BulletinBoard/ClearedSections.plist

- BFU: Y
- Backup: Y
- Sysdiagnose: N

##  Auto correction / Predictive text
path: /private/var/mobile/Library/Keyboard/<language>-dynamic.lm/dynamic-lexicon.dat

- BFU: N
- Backup: N
- Sysdiagnose: N

## Preferences
path: /private/var/mobile/Library/Preferences/

Examine plists for more information

- BFU: Y
- Backup: Y
- Sysdiagnose: N

##  Wi-Fi Mac Addresses
path: /private/var/preferences/SystemConfiguration/NetworkInterfaces.plist

- BFU: Y
- Backup: N
- Sysdiagnose: Y

# User settings

##  Cloud configurations
path: /private/var/containers/Shared/SystemGroup/systemgroup.com.apple.configurationprofiles/Library/ConfigurationProfilesCloudConfigurationDetails.plist

- BFU: N
- Backup: N
- Sysdiagnose: N

##  Do not disturb settings
path: /private/var/mobile/Library/DoNotDisturb/DB/Settings.json

- BFU: Y
- Backup: Y
- Sysdiagnose: N

##  User created auto-correct
path: /private/var/mobile/Library/Keyboard/UserDictionary.sqlite

- BFU: N
- Backup: N
- Sysdiagnose: N

##  Mail and settings
path: /private/var/mobile/Library/Mail/

- BFU: N
- Backup: N
- Sysdiagnose: N

##  Siri
path: /private/var/mobile/Library/Preferences/com.apple.assistant*

- BFU: Y
- Backup: Y
- Sysdiagnose: N

##  Cloud sync settings
path: /private/var/mobile/Library/Preferences/com.apple.assistant.backedup.plist

- BFU: Y
- Backup: Y
- Sysdiagnose: N

##  Camera settings
path: /private/var/mobile/Library/Preferences/com.apple.camera.plist

- BFU: Y
- Backup: Y
- Sysdiagnose: N

##  Camera CarPlay Volumes and other settings
path: /private/var/mobile/Library/Preferences/com.apple.celestial.plist

- BFU: Y
- Backup: Y
- Sysdiagnose: N

##  Cloud photo sync information
path: /private/var/mobile/Library/Preferences/com.apple.cloudphotod.plist

- BFU: Y
- Backup: Y
- Sysdiagnose: N

##  Cloud sync settings
path: /private/var/mobile/Library/Preferences/com.apple.CoreDuet.plist

- BFU: Y
- Backup: Y
- Sysdiagnose: N

##  SMS iMessage and FaceTime
path: /private/var/mobile/Library/Preferences/com.apple.imservice*

- BFU: Y
- Backup: Y
- Sysdiagnose: N

##  Time to keep messages
path: /private/var/mobile/Library/Preferences/com.apple.MobileSMS.plist

- BFU: Y
- Backup: Y
- Sysdiagnose: N

##  Airplane Mode Settings
path: /private/var/mobile/Library/Preferences/com.apple.preferences.network.plist

- BFU: Y
- Backup: Y
- Sysdiagnose: N

##  User created restrictions/Remote wipe settings
path: /private/var/mobile/Library/Preferences/com.apple.springboard.plist

- BFU: Y
- Backup: Y
- Sysdiagnose: N

##  Weather (including current city)
path: /private/var/mobile/Library/Preferences/com.apple.weather.plist

- BFU: Y
- Backup: Y
- Sysdiagnose: N

##  Wallpaper
path: /private/var/mobile/Library/SpringBoard/HomeBackground.cpbitmap

path: /private/var/mobile/Library/SpringBoard/HomeBackgroundThumbnail.jpg

path: /private/var/mobile/Library/SpringBoard/LockBackground.cpbitmap

path: /private/var/mobile/Library/SpringBoard/LockBackgroundThumbnail.jpg

path: /private/var/mobile/Library/SpringBoard/LockBackgroundThumbnaildark.jpg


- BFU: Y
- Backup: Y
- Sysdiagnose: N


##  Homescreen icon layout
path: /private/var/mobile/Library/SpringBoard/IconState.plist

- BFU: Y
- Backup: Y
- Sysdiagnose: N


##  Notifications
path: /private/var/mobile/Library/SpringBoard/PushStore/

- BFU: N
- Backup: N
- Sysdiagnose: N

##  User created restrictions
path: /private/var/mobile/Library/UserConfigurationProfiles/UserSettings.plist

- BFU: Y
- Backup: Y
- Sysdiagnose: N

##  User Notifications
path: /private/var/mobile/Library/UserNotifications/

- BFU: Y
- Backup: Y
- Sysdiagnose: N

##  Last - Backup computer iCloud - Backup Settings Device info
path: /private/var/root/Library/Lockdown/data_ark.plist

- BFU: Y
- Backup: N
- Sysdiagnose: N

##  Airplane Mode Settings
path: /private/var/root/Library/Preferences/com.apple.preferences.network.plist

- BFU: Y
- Backup: Y
- Sysdiagnose: N


# Communication 

##  Call log (Up to iOS 7)
path: /private/var/mobile/Library/CallHistory/call_history.db

- BFU: N
- Backup: Y
- Sysdiagnose: N

##  Call log (From iOS 8)
path: /private/var/mobile/Library/CallHistoryDB/CallHistory.storedata

- BFU: N
- Backup: Y
- Sysdiagnose: N

##  Call History Temporary storage 
path: /private/var/mobile/Library/CallHistoryDB/CallHistoryTemp.storedata

- BFU: Y
- Backup: N
- Sysdiagnose: N

##  Mail and settings
path: /private/var/mobile/Library/Mail/

- BFU: N
- Backup: N
- Sysdiagnose: N

##  SMS iMessage and FaceTime
path: /private/var/mobile/Library/Preferences/com.apple.madrid.plist

- BFU: Y
- Backup: Y
- Sysdiagnose: N

##  List of contacts added to the phone application’s favorites list
path: /private/var/mobile/Library/Preferences/com.apple.mobilephone.*

- BFU: N
- Backup: Y
- Sysdiagnose: N

##  SMS iMessage and FaceTime
path: /private/var/mobile/Library/Preferences/com.apple.MobileSMS.plist

- BFU: Y
- Backup: Y
- Sysdiagnose: N

##  Recents communications
path: /private/var/mobile/Library/Recents/

- BFU: N
- Backup: N
- Sysdiagnose: N

##  MMS File
path: /private/var/mobile/Library/SMS/Attachments/*

- BFU: N
- Backup: Y
- Sysdiagnose: N

##  SMS/MMS Drafts
path: /private/var/mobile/Library/SMS/Drafts/*

path: /private/var/mobile/Library/SMS/sms.db

- BFU: N
- Backup: Y
- Sysdiagnose: N


##  SMS Temporary storage (Before First Unlock)
path: /private/var/mobile/Library/SMS/sms-temp.db

- BFU: Y
- Backup: N
- Sysdiagnose: N

##  Contains iMessage/SMS traces
path: /private/var/mobile/Library/Suggestions/query_predictions.db

- BFU: N
- Backup: N
- Sysdiagnose: N

##  Voicemail
path: /private/var/mobile/Library/Voicemail/voicemail.db

- BFU: Y
- Backup: N
- Sysdiagnose: N

##  Voice Memos
path: /private/var/mobile/Media/Recordings/*

- BFU: N
- Backup: Y
- Sysdiagnose: N

# Browser activity

##  Safari Cache files
path: /private/var/mobile/Containers/Data/Application/<Apple Safari GUID>/Library/Caches/com.apple.mobilesafari/

- BFU: N
- Backup: N
- Sysdiagnose: N

##  Safari Cache database
path: /private/var/mobile/Containers/Data/Application/<Apple Safari GUID>/Library/Caches/com.apple.mobilesafari/Cache.db

- BFU: N
- Backup: N
- Sysdiagnose: N

##  Safari Website cache
path: /private/var/mobile/Containers/Data/Application/<Apple Safari GUID>/Library/Caches/com.apple.WebAppCache/ApplicationCache.db

- BFU: N
- Backup: N
- Sysdiagnose: N

##  Safari Cookies
path: /private/var/mobile/Containers/Data/Application/<Apple Safari GUID>/Library/Cookies/Cookies.binarycookies

- BFU: N
- Backup: Y
- Sysdiagnose: N

##  Safari Website favicons
path: /private/var/mobile/Containers/Data/Application/<Apple Safari GUID>/Library/Favicons/Favicons/

- BFU: N
- Backup: N
- Sysdiagnose: N

##  Safari Configuration
path: /private/var/mobile/Containers/Data/Application/<Apple Safari GUID>/Library/Preferences/com.apple.mobilesafari.plist

- BFU: N
- Backup: Y
- Sysdiagnose: N

##  Safari Download History
path: /private/var/mobile/Containers/Data/Application/<Apple Safari GUID>/Library/Safari/Downloads/Downloads.plist

- BFU: N
- Backup: Y
- Sysdiagnose: N

##  Safari Tabs Screenshots (PNG or KTX format)
path: /private/var/mobile/Containers/Data/Application/<Apple Safari GUID>/Library/Safari/Thumbnails/

- BFU: N
- Backup: Y
- Sysdiagnose: N

##  Safari WebKit Localstorage
path: /private/var/mobile/Containers/Data/Application/<Apple Safari GUID>/Library/WebKit/WebsiteData/LocalStorage/*

- BFU: Y
- Backup: Y
- Sysdiagnose: N

##  Safari History information
path: /private/var/mobile/Library/Assistant/knowledgeC.db

- BFU: N
- Backup: N
- Sysdiagnose: N

##  Safari Bookmarks
path: /private/var/mobile/Library/Safari/Bookmarks.db

- BFU: N
- Backup: Y
- Sysdiagnose: N

##  Safari Suspended State Tab
path: /private/var/mobile/Library/Safari/BrowserState.db

- BFU: N
- Backup: N
- Sysdiagnose: N

##  Safari Cloud Tabs
path: /private/var/mobile/Library/Safari/CloudTabs.db

- BFU: N
- Backup: N
- Sysdiagnose: N

##  Safari History
path: /private/var/mobile/Library/Safari/History.db

- BFU: N
- Backup: N
- Sysdiagnose: N

# Multimedia

##  Application Snapshots
path: *.ktx

- BFU: N
- Backup: N
- Sysdiagnose: N

##  Contacts pictures
path: /private/var/mobile/Library/AddressBook/AddressBookImages.sqlitedb

- BFU: N
- Backup: Y
- Sysdiagnose: N

##  Photos
path: /private/var/mobile/Library/Preferences/com.apple.mobileslideshow.plist

- BFU: Y
- Backup: Y
- Sysdiagnose: N

##  MMS File
path: /private/var/mobile/Library/SMS/Attachments/

- BFU: N
- Backup: Y
- Sysdiagnose: N

##  User Created/Saved Photos
path: /private/var/mobile/Media/DCIM/1*APPLE 

- BFU: N
- Backup: Y
- Sysdiagnose: N

##  iTunes Media Library
path: /private/var/mobile/Media/iTunes_Control/iTunes/MediaLibrary.sqlitedb

- BFU: Y
- Backup: Y
- Sysdiagnose: N

##  Thumbnails databases
path: /private/var/mobile/Media/PhotoData/*.ithmb

- BFU: N
- Backup: Y
- Sysdiagnose: N

##  Photo Albums Metadata
path: /private/var/mobile/Media/PhotoData/AlbumsMetadata/

- BFU: N
- Backup: Y
- Sysdiagnose: N

##  Cloud Photo Library
path: /private/var/mobile/Media/PhotoData/CPL/

- BFU: N
- Backup: Y
- Sysdiagnose: N

##  Photos/Videos Database
path: /private/var/mobile/Media/PhotoData/Photos.sqlite

- BFU: N
- Backup: Y
- Sysdiagnose: N

##  Photos saved from Live Video and SMS photo capture
path: /private/var/mobile/Media/PhotoData/V2/

- BFU: N
- Backup: Y
- Sysdiagnose: N

# Network connections

##  DHCP Lease
path: /private/var/db/dhcpclient/leases/

- BFU: Y
- Backup: N
- Sysdiagnose: N

##  Airplane mode ON/OFF
path: /private/var/mobile/Library/Preferences/com.apple.preferences.network.plist

- BFU: Y
- Backup: Y
- Sysdiagnose: N

##  Network data usage per App

path: /private/var/networkd/netusage.sqlite

- BFU: N
- Backup: N
- Sysdiagnose: N

##  Network Extension
path: /private/var/preferences/com.apple.networkextension.plist

- BFU: Y
- Backup: Y
- Sysdiagnose: N

##  Network IP Wi-Fi Cellular
path: /private/var/preferences/SystemConfiguration/com.apple.networkidentification.plist

- BFU: Y
- Backup: Y
- Sysdiagnose: N

##  Wi-Fi
path: /private/var/preferences/SystemConfiguration/com.apple.wifi.plist

- BFU: Y
- Backup: Y
- Sysdiagnose: Y

##  Wi-Fi Mac Addresses
path: /private/var/preferences/SystemConfiguration/NetworkInterfaces.plist

- BFU: Y
- Backup: N
- Sysdiagnose: Y

##  Wi-Fi VPN Certs and more
path: /private/var/preferences/SystemConfiguration/preferences.plist

- BFU: Y
- Backup: Y
- Sysdiagnose: N

##  Wi-Fi ON/OFF
path: /private/var/root/Library/Preferences/com.apple.preferences.network.plist

- BFU: Y
- Backup: Y
- Sysdiagnose: N

##  SIMs used in device including most recent
path: /private/var/wireless/Library/Databases/CellularUsage.db

- BFU: Y
- Backup: Y
- Sysdiagnose: N

##  Data and Cellular network statistics
path: /private/var/wireless/Library/Preferences/com.apple.CommCenter.counts.plist

- BFU: Y
- Backup: Y
- Sysdiagnose: N

##  Device IMEI
path: /private/var/wireless/Library/Preferences/com.apple.commcenter.device_specific_no- Backup.plist

- BFU: Y
- Backup: Y
- Sysdiagnose: N

##  SIM Card ICCID
path: /private/var/wireless/Library/Preferences/com.apple.commcenter.plist

- BFU: Y
- Backup: Y
- Sysdiagnose: N

# Syncing

##  Seen Bluetooth devices
path: /private/var/containers/Shared/SystemGroup/<GUID>/Library/Database/com.apple.MobileBluetooth.ledevices.other.db

- BFU: N
- Backup: Y
- Sysdiagnose: N

##  Paired Bluetooth devices
path: /private/var/containers/Shared/SystemGroup/<GUID>/Library/Database/com.apple.MobileBluetooth.ledevices.paired.db

- BFU: Y
- Backup: Y
- Sysdiagnose: N

##  Paired Bluetooth devices
path: /private/var/containers/Shared/SystemGroup/<GUID>/Library/Preferences/com.apple.MobileBluetooth.devices.plist

- BFU: N
- Backup: Y
- Sysdiagnose: N

##  iClould offline cache
path: /private/var/mobile/Library/DataAccess/iCloud-[iCloud email account name/.OfflineCache/[number

- BFU: Y
- Backup: Y
- Sysdiagnose: N

##  Apple Watch pairing information
path: /private/var/mobile/Library/DeviceRegistry.state/activeStateMachine.plist

- BFU: Y
- Backup: Y
- Sysdiagnose: N

##  Apple Watch information (also previously paired Apple Watch)
path: /private/var/mobile/Library/DeviceRegistry.state/historySecureProperties.plist

- BFU: N
- Backup: Y
- Sysdiagnose: N

##  Apple Watch pairing information (also previously paired Apple Watch)
path: /private/var/mobile/Library/DeviceRegistry.state/stateMachine-<GUID>.plist

- BFU: N
- Backup: Y
- Sysdiagnose: N

##  Apple Watch data
path: /private/var/mobile/Library/DeviceRegistry/<GUID>/

- BFU: Y
- Backup: Y
- Sysdiagnose: N

##  Apple Watch Applications
path: /private/var/mobile/Library/DeviceRegistry/<GUID>/NanoAppRegistry/Applications/

- BFU: Y
- Backup: Y
- Sysdiagnose: N

##  Apple Watch Mail application
path: /private/var/mobile/Library/DeviceRegistry/<GUID>/NanoMail/registry.sqlite

- BFU: Y
- Backup: Y
- Sysdiagnose: N

##  Apple Watch Wallet Passes
path: /private/var/mobile/Library/DeviceRegistry/<GUID>/NanoPasses/nanopasses.sqlite3

- BFU: N
- Backup: Y
- Sysdiagnose: N

##  Apple Watch Faces
path: /private/var/mobile/Library/DeviceRegistry/<GUID>/NanoPreferencesSync/- Backup/Files/

- BFU: Y
- Backup: Y
- Sysdiagnose: N

##  AppleWatch Health data sync
path: /private/var/mobile/Library/Health/NanoSync/com.apple.private.alloy.health.sync.db

- BFU: N
- Backup: Y
- Sysdiagnose: N

##  Apple HomeKit Devices
path: /private/var/mobile/Library/homed/datastore.sqlite

- BFU: N
- Backup: Y
- Sysdiagnose: N

##  Seen Bluetooth devices
path: /private/var/mobile/Library/MobileBluetooth/com.apple.MobileBluetooth.ledevices.plist

- BFU: Y
- Backup: Y
- Sysdiagnose: N

##  Apple Watch information
path: /private/var/mobile/Library/Nano- Backup/

- BFU: Y
- Backup: Y
- Sysdiagnose: N

##  Apple Watch information
path: /private/var/mobile/Library/NanoMusicSync/

path: /private/var/mobile/Library/NanoPreferencesSync/

path: /private/var/mobile/Library/NanoTimeKit/

- BFU: Y
- Backup: N
- Sysdiagnose: N


##  Apple CarPlay configuration
path: /private/var/mobile/Library/Preferences/com.apple.carplay.plist

- BFU: Y
- Backup: Y
- Sysdiagnose: N

##  iCloud quota information
path: /private/var/mobile/Library/Preferences/com.apple.cloud.quota.plist

- BFU: Y
- Backup: Y
- Sysdiagnose: N

##  Cloud Sync denials and dates
path: /private/var/mobile/Library/Preferences/com.apple.CoreDuet.QueuedDenials.plist

- BFU: Y
- Backup: Y
- Sysdiagnose: N

##  sync devices
path: /private/var/mobile/Library/Preferences/com.apple.coreduetd.plist

- BFU: Y
- Backup: Y
- Sysdiagnose: N

##  iCloud sync Email FaceTime Email more
path: /private/var/mobile/Library/Preferences/com.apple.identityservices.idstatuscache.plist

- BFU: Y
- Backup: Y
- Sysdiagnose: N

##  Last iTunes and last iCloud - Backup date and timezone.
path: /private/var/mobile/Library/Preferences/com.apple.mobile.ld- Backup.plist

- BFU: Y
- Backup: Y
- Sysdiagnose: N

##  Apple Watch preferences
path: /private/var/mobile/Library/Preferences/com.apple.nano*.plist

- BFU: Y
- Backup: Y
- Sysdiagnose: N

##  Device AirDrop ID
path: /private/var/mobile/Library/Preferences/com.apple.sharingd.plist

- BFU: Y
- Backup: Y
- Sysdiagnose: N

##  Apple CarPlay per car App Icon configuration
path: /private/var/mobile/Library/Springboard/<GUID>-CarDisplay[DesiredIconState.plist

- BFU: Y
- Backup: Y
- Sysdiagnose: N

##  List of computer where the device was connected to
path: /private/var/mobile/Media/iTunesControl/iTunes/iTunesPrefs

- BFU: Y
- Backup: Y
- Sysdiagnose: N

##  Last - Backup computer iCloud - Backup Settings Device info
path: /private/var/root/Library/Lockdown/data_ark.plist

- BFU: Y
- Backup: N
- Sysdiagnose: N

##  Watch Application Usage
path: /private/var/wireless/Library/Databases/DataUsage-watch.sqlite

- BFU: N
- Backup: N
- Sysdiagnose: N

# Location artifacts

##  Seen Bluetooth devices
path: /private/var/containers/Shared/SystemGroup/<GUID>/Library/Database/com.apple.MobileBluetooth.ledevices.other.db

- BFU: N
- Backup: Y
- Sysdiagnose: N

##  Apple Maps history
path: /private/var/mobile/Containers/Data/Application/<Apple_Maps_GUID>/Library/Maps/GeoHistory.mapsdata

- BFU: N
- Backup: Y
- Sysdiagnose: N

##  Apple Maps history
path: /private/var/mobile/Containers/Data/Application/<Apple_Maps_GUID>/Library/Maps/History.mapsdata

- BFU: N
- Backup: Y
- Sysdiagnose: N

##  Last latitude and longitude map search history
path: /private/var/mobile/Containers/Data/Application/<Apple_Maps_GUID>/Library/Preferences/com.apple.Maps.plist

- BFU: Y
- Backup: Y
- Sysdiagnose: N

##  Apple Maps recents
path: /private/var/mobile/Containers/Data/Application/<Apple_Maps_GUID>/Library/SyncedPreferences/com.apple.Maps-com.apple.Maps.recents.plist

- BFU: Y
- Backup: N
- Sysdiagnose: N

##  Apple Maps bookmarks
path: /private/var/mobile/Containers/Data/Application/<Apple_Maps_GUID>/Library/SyncedPreferences/com.apple.Maps-com.apple.MapsSupport.bookmarks.plist

- BFU: Y
- Backup: N
- Sysdiagnose: N

##  Apple Maps history
path: /private/var/mobile/Containers/Data/Application/<Apple_Maps_GUID>/Library/SyncedPreferences/com.apple.Maps-com.apple.MapsSupport.history.plist

- BFU: Y
- Backup: N
- Sysdiagnose: N

##  Last latitude and longitude map search history
path: /private/var/mobile/Containers/Shared/AppGroup/<Apple_MAPS_GUID>/Library/Preferences/group.com.apple.Maps.plist

- BFU: Y
- Backup: Y
- Sysdiagnose: N

##  Location information
path: /private/var/mobile/Library/Caches/com.apple.routined/Cache.sqlite

- BFU: N
- Backup: N
- Sysdiagnose: N


##  location service
path: /private/var/mobile/Library/Preferences/com.apple.locationd.plist

setting
Enabled = 1
Disabled = 0)

- BFU: Y
- Backup: Y
- Sysdiagnose: N

##  Time settings
path: /private/var/mobile/Library/Preferences/com.apple.preferences.datetime.plist

- BFU: Y
- Backup: Y
- Sysdiagnose: N

##  Language Country info Device IDs
path: /private/var/mobile/Library/Preferences/com.apple.purplebuddy.plist

- BFU: Y
- Backup: Y
- Sysdiagnose: N

##  Network IP WiFi Cellular
path: /private/var/preferences/SystemConfiguration/com.apple.networkidentification.plist

- BFU: Y
- Backup: Y
- Sysdiagnose: N

##  Network and VPN information
path: /private/var/preferences/SystemConfiguration/preferences.plist

- BFU: Y
- Backup: Y
- Sysdiagnose: N

##  Location information

path: /private/var/root/Library/Caches/locationd/Cache.sqlite


path: /private/var/root/Library/Caches/locationd/cache_encryptedA.db


path: /private/var/root/Library/Caches/locationd/cache_encryptedB.db


path: /private/var/root/Library/Caches/locationd/cache_encryptedC.db

- BFU: N
- Backup: N
- Sysdiagnose: N

##  Application Traces and GeoFence information

path: /private/var/root/Library/Caches/locationd/consolidated.db

- BFU: Y
- Backup: Y
- Sysdiagnose: N

##  Significant Location
path: /private/var/root/Library/Caches/locationd/significant.plist

- BFU: N
- Backup: Y
- Sysdiagnose: N


path: /private/var/root/Library/Caches/locationd/significantVisitAuth.plist


path: /private/var/root/Library/Caches/locationd/significantVisitInterest.plist

- BFU: Y
- Backup: Y
- Sysdiagnose: N


# Application usage

##  Mobile Applications Installation Logs
path: /private/var/installd/Library/Logs/MobileInstallation/mobile_installation.log.*

- BFU: Y
- Backup: N
- Sysdiagnose: Y

##  Battery life tracker
path: /private/var/containers/Shared/SystemGroup/<GUID>/Library/BatteryLife/CurrentPowerLog.PLSQL

- BFU: N
- Backup: N
- Sysdiagnose: Y


##  Installed Apps and Apps Path
path: /private/var/mobile/Library/AppConduit/AvailableApps.plist


path: /private/var/mobile/Library/AppConduit/AvailableCompanionApps.plist

- BFU: Y
- Backup: N
- Sysdiagnose: N

##  Screen time

path: /private/var/mobile/Library/Application Support/com.apple.remotemanagmentd/RMAdminStore-Local.sqlite

- BFU: N
- Backup: N
- Sysdiagnose: N

##  Application order on the SpringBoard
path: /private/var/mobile/Library/ApplicationSync/AssetSortOrder.plist

- BFU: Y
- Backup: N
- Sysdiagnose: N

##  Application traces
path: /private/var/mobile/Library/Assistant/knowledgeC.db

path: /private/var/mobile/Library/CoreDuet/Knowledge/knowledgeC.db

- BFU: N
- Backup: N
- Sysdiagnose: N

path: /private/var/mobile/Library/com.apple.itunesstored/itunesstored2.sqlitedb

path: /private/var/mobile/Library/FrontBoard/applicationState.db

path: /private/var/mobile/Library/Keyboard/langlikelihood.dat

path: /private/var/mobile/Library/Preferences/addaily.plist

path: /private/var/mobile/Library/Preferences/com.apple.corespotlightui.plist

path: /private/var/root/Library/Caches/locationd/clients.plist

- BFU: Y
- Backup: Y
- Sysdiagnose: N


path: /private/var/mobile/Library/CoreDuet/People/interactionC.db

path: /private/var/mobile/Library/Logs/mobile_installation_helper.log*

path: /private/var/containers/Shared/SystemGroup/<GUID>/Library/Logs/mobile_installation_helper.log.*

- BFU: N
- Backup: Y
- Sysdiagnose: N

path: /private/var/wireless/Library/Databases/DataUsage.sqlite

path: /private/var/mobile/Library/AggregatedDictionary/ADDataStore.sqlitedb

- BFU: Y
- Backup: N
- Sysdiagnose: N

##  Installed Applications

path: /private/var/mobile/Library/com.apple.itunesstored/kvs.sqlitedb

- BFU: Y
- Backup: Y
- Sysdiagnose: N


##  Fitness Friends

path: /private/var/mobile/Library/Health/ActivitySharing/contacts2.dat

- BFU: N
- Backup: N
- Sysdiagnose: N


##  Step/Stride Cadence Pedometer Info

path: /private/var/mobile/Library/locationd/user.plist

- BFU: N
- Backup: Y
- Sysdiagnose: N

##  Installed Apps and Apps Path

path: /private/var/mobile/Library/Logs/AppConduit/

- BFU: Y
- Backup: N
- Sysdiagnose: Y


##  Information about Fitness Friends

path: /private/var/mobile/Library/Preferences/com.apple.ActivitySharing.plist

- BFU: Y
- Backup: Y
- Sysdiagnose: N

##  Last search on Apple Store

path: /private/var/mobile/Library/preferences/com.apple.AppStore.plist

- BFU: Y
- Backup: Y
- Sysdiagnose: N


##  Applications permissions

path: /private/var/mobile/Library/TCC/TCC.db

- BFU: Y
- Backup: Y
- Sysdiagnose: N

##  Network data usage per App

path: /private/var/networkd/netusage.sqlite

- BFU: N
- Backup: N
- Sysdiagnose: N



##  MobileContainerManager logs

path: /private/var/root/Library/Logs/MobileContainerManager

- BFU: Y
- Backup: N
- Sysdiagnose: Y

##  Installed Applications

path: /private/var/root/Library/MobileContainerManager/containers.sqlite3

- BFU: Y
- Backup: N
- Sysdiagnose: N




# Batter power

##  Battery life tracker

path: /private/var/containers/Shared/SystemGroup/<GUID>/Library/BatteryLife/CurrentPowerLog.PLSQL

- BFU: N
- Backup: N
- Sysdiagnose: Y

##  Powering Events

path: /private/var/mobile/Library/CoreDuet/coreduetd.db

0=unplugged
1=plugged in
- BFU: N
- Backup: N
- Sysdiagnose: N

##  Battery icon status

path: /private/var/mobile/Library/Preferences/com.apple.BatteryCenter.BatteryWidget.plist

- BFU: N
- Backup: Y
- Sysdiagnose: N

##  Battery Saver state

path: /private/var/mobile/Library/Preferences/com.apple.coreduetd.batterysaver.state.plist

- BFU: Y
- Backup: N
- Sysdiagnose: N

# Native applications

##  iCloud Notes

path: /private/var/mobile/Containers/Shared/AppGroup/<Apple_Notes_GUID>/NoteStore.sqlite

- BFU: N
- Backup: Y
- Sysdiagnose: N

##  Contacts

path: /private/var/mobile/Library/AddressBook/AddressBook.sqlitedb

- BFU: N
- Backup: y
- Sysdiagnose: N

##  Contact Images

path: /private/var/mobile/Library/AddressBook/AddressBookImages.sqlitedb

- BFU: N
- Backup: Y
- Sysdiagnose: N

##  Calendar

path: /private/var/mobile/Library/Calendar/Calendar.sqlitedb 

- BFU: N
- Backup: Y
- Sysdiagnose: N

##  Extras for Calendar

path: /private/var/mobile/Library/Calendar/Extras.db

- BFU: Y
- Backup: Y
- Sysdiagnose: N

##  Calendar entries

path: /private/var/mobile/Library/Calendar/Notifications.Calendar.Protected

- BFU: Y
- Backup: N
- Sysdiagnose: N

##  Mail and settings

path: /private/var/mobile/Library/Mail/

- BFU: N
- Backup: N
- Sysdiagnose: N

##  Notes

path: /private/var/mobile/Library/Notes/Library/Notes/notes.idx 

- BFU: N
- Backup: N
- Sysdiagnose: N

path: /private/var/mobile/Library/Notes/notes.sqlite

- BFU: N
- Backup: Y
- Sysdiagnose: N

path: /private/var/mobile/Library/Preferences/com.apple.mobilenotes.plist

- BFU: Y
- Backup: Y
- Sysdiagnose: N

##  Apple Passes

path: /private/var/mobile/Library/Passes/

- BFU: N
- Backup: Y
- Sysdiagnose: N



# - Backup

##  Activated state BT address and more

path: /Lockdown/device_values.plist

- BFU: N
- Backup: Y
- Sysdiagnose: N

##  Identifiers about iOS device (phone number version etc)

path: info.plist

- BFU: N
- Backup: Y
- Sysdiagnose: N

##  Encryption state installed apps and more

path: manifest.plist

- BFU: N
- Backup: Y
- Sysdiagnose: N

##  Last - Backup date and other identifiers

path: status.plist

- BFU: N
- Backup: Y
- Sysdiagnose: N

# Evidence destruction

##  Language Country info Device IDs

path: /private/var/mobile/Library/Preferences/com.apple.purplebuddy.plist

- BFU: Y
- Backup: Y
- Sysdiagnose: Y

##  Creation time stamp -> Device reset time

path: /private/var/root/.obliterated

- BFU: Y
- Backup: N
- Sysdiagnose: N

##  Restore information (timestamp local vs. iCloud)

path: /private/var/root/Library/Preferences/com.apple.Mobile- Backup.plist

- BFU: Y
- Backup: Y
- Sysdiagnose: Y
