# Monitoring-Linux-File-Integrity-using-Auditd-

#Demonstrates how to use the Linux Audit daemon (auditd) to monitor and detect unauthorized file modifications in a protected directory. Custom audit rules are configured to track changes to specific files, and attack scripts are run to simulate file tampering. By analyzing the audit logs with ausearch, we can identify which files were modified and trace the changes back to the responsible scripts. This project showcases practical filesystem monitoring and auditing techniques to enhance security.

#Run this command to download the starter project files wget https://github.com/codepath/project2/archive/main.zip

#Unzip the Downloaded Files unzip main.zip

#Navigate to the Project Directory cd project2-main

#Set Permissions for Attack Scripts #Make the Attack Scripts Executable chmod u+x attack-a attack-b attack-c

#Configure Audit Rules to Monitor File Changes sudo systemctl start auditd

#Write Audit Rules

Watch car_sales.csv for write operations
-w /home/codepath/project2-main/protected_files/car_sales.csv -p w -k file_watch_car_sales

Watch cloudia.txt for write operations
-w /home/codepath/project2-main/protected_files/cloudia.txt -p w -k file_watch_cloudia

Watch dolly.txt for write operations
-w /home/codepath/project2-main/protected_files/dolly.txt -p w -k file_watch_dolly

Watch earthquakes.csv for write operations
-w /home/codepath/project2-main/protected_files/earthquakes.csv -p w -k file_watch_earthquakes

Watch loggy.txt for write operations
-w /home/codepath/project2-main/protected_files/loggy.txt -p w -k file_watch_loggy

Watch oakley.txt for write operations
-w /home/codepath/project2-main/protected_files/oakley.txt -p w -k file_watch_oakley

Watch precipitation.csv for write operations
-w /home/codepath/project2-main/protected_files/precipitation.csv -p w -k file_watch_precipitation

Watch squeaky.txt for write operations
-w /home/codepath/project2-main/protected_files/squeaky.txt -p w -k file_watch_squeaky

Watch tosty.txt for write operations
-w /home/codepath/project2-main/protected_files/tosty.txt -p w -k file_watch_tosty

Watch website.js for write operations
-w /home/codepath/project2-main/protected_files/website.js -p w -k file_watch_website

#Restart Auditd sudo systemctl restart auditd

#Run the Attack Scripts #Execute the Attack Scripts

./attack-a ./attack-b ./attack-c

#Analyze Audit Logs to Identify Changes sudo ausearch -k file_watch1
