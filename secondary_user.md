## Enabling Seedvault for a secondary user
Seedvault is generally not enabled in secondary users. It is possible to use adb to enable seedvault in secondary users. 
To find the numeric ID (eg. 10) of the user profile currently in focus use -  
`adb shell am get-current-user`  
Use this number in the place of [ID] in the following commands  
`adb shell bmgr --user [ID] activate true`  
`adb shell bmgr --user [ID] transport com.stevesoltys.seedvault.transport.ConfigurableBackupTransport`  
You can check that the commands were successful using-  
`adb shell bmgr --user [ID] list transports`  
Seedvault can then be setup as usual in the secondary profile.
## Restore backup to a secondary user profile
It is possible manually activate the Seedvault restore activity.
You can do this using the [Activity Launcher app](https://github.com/butzist/ActivityLauncher), or when connected by adb it is possible to use -  
`adb shell am start-activity -a com.stevesoltys.seedvault.RESTORE_BACKUP`
