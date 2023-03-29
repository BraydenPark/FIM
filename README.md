# FIM
INSTALLATION STEPS:
1) Move FIM.py to desired location
2) Open terminal
3) type "sudo chmod +x FIM.py"
4) type "sudo ./FIM.py" to start Program

CAUTIONS & WARNINGS:
- Make sure to limit write privileges to FIM.py Because the FIM has to be run with elevated privileges. Code could be modified and run as root.
- It is recommended that FIM.py only have write privileges: "sudo chmod 644" (R+W,R,R)
- It is recommended that the secondsUntilUpdateHashes (default time is 2 minutes) is a longer time compared to secondsUntilReVerify (The default time is 10 seconds)
- **DO NOT USE THIS IN ANY ENTERPRISE PRODUCTION ENVIRONMENT as it has not been extensibly tested. Brayden Park is not responsible for any damage that may/is done towards you or your organization while using this product. USE AT YOUR OWN RISK** 

NOTES:
- The log file, the hash database, and the config file automatically get created and placed into /etc/FIM/
- The program can only monitor one directory at a time. I am still working on recursive directory scanning.
- This program is only run on Linux 

CONFIG DESCRIPTIONS:
- fileExtensions: Any file extensions included here will be monitored and any file extensions not included will not be included. You can include all file extensions by leaving a "*" character. 
- secondsUntilReVerify: Time delay between each verification cycle. Essentially it will take X seconds until it reverifies the current hash with the hash stored in the database
- secondsUntilUpdateHashes: Time delay between each update cycle. Essentially it will take X seconds until it updates the hashes in the database file
- loggingOutput: This can be set as "True" or "False" (case sensitive). If "False", the program will log nothing to the log file. If "True" then program will be allowed to log output. Output would depend on the variables below (loggingAlerts, loggingVerification, and loggingHashUpdates). 
- loggingAlerts: This can be set as "True" or "False" (case sensitive). If "True", the program will log alert outputs. This would be if/when a file has changed, the program would log this. If "False", the program won't log alerts.  
- loggingVerification: This can be set as "True" or "False" (case sensitive). If "True", the program will log verification outputs. This would be if/when a file hasn't been changed. If "False", the program won't log verification alerts. 
- loggingHashUpdates: This can be set as "True" or "False" (case sensitive). If "True", the program will log anytime a hash is updated and recalculated. If "False", the program won't log anytime a hash is updated and recalculated.
- maxLogFileDays: This is the total amount of DAYS that the log file will be allowed to be on the system before being cleared. The default is 10 days. So 10 days after it is created, it will be cleared when the program is first run. 
- ScanPath: This is the absolute path that the FIM will be monitoring. "Default is /home/kali/Desktop/scanned" 
