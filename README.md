Linux User Management Lab – Kali Linux

## Lab Title
Linux User and Group Management with File Permissions
 Objective
The objective of this lab is to learn how to manage users, groups, and file permissions in Kali Linux. This includes creating users, assigning groups, managing file ownership, and configuring secure file permissions for both individual and shared access environments.

Tools Used
- Kali Linux
- Linux Terminal
- Bash Shell
- GitHub (Documentation)
- 
 Scenario
I was assigned as a System Administrator at TechCorp Solutions. My responsibility was to configure secure user accounts and file access permissions for two departments:
- Marketing Department (Private user files)
- IT Department (Shared collaborative file)
 Part 1: Marketing Department Setup
Step 1: Create marketing group
sudo groupadd marketing
Step 2: Create users
sudo useradd -m alice_m
sudo useradd -m bob_m
sudo useradd -m carol_m
sudo useradd -m david_m
sudo useradd -m emma_m
Step 3: Add users to group
sudo usermod -aG marketing alice_m
sudo usermod -aG marketing bob_m
sudo usermod -aG marketing carol_m
sudo usermod -aG marketing david_m
sudo usermod -aG marketing emma_m
Step 4: Create shared directory
sudo mkdir -p /home/shared/marketing
Step 5: Create personal files
sudo touch /home/shared/marketing/alice_report.txt
sudo touch /home/shared/marketing/bob_report.txt
sudo touch /home/shared/marketing/carol_report.txt
sudo touch /home/shared/marketing/david_report.txt
sudo touch /home/shared/marketing/emma_report.txt
Step 6: Assign ownership
sudo chown alice_m /home/shared/marketing/alice_report.txt
sudo chown bob_m /home/shared/marketing/bob_report.txt
sudo chown carol_m /home/shared/marketing/carol_report.txt
sudo chown david_m /home/shared/marketing/david_report.txt
sudo chown emma_m /home/shared/marketing/emma_report.txt
Step 7: Set permissions
sudo chmod 700 /home/shared/marketing/*.txt
Part 2: IT Department Setup
Step 1: Create group
sudo groupadd itdept
Step 2: Create users
sudo useradd -m frank_it
sudo useradd -m grace_it
sudo useradd -m henry_it
sudo useradd -m iris_it
sudo useradd -m jack_it
Step 3: Add users to group
sudo usermod -aG itdept frank_it
sudo usermod -aG itdept grace_it
sudo usermod -aG itdept henry_it
sudo usermod -aG itdept iris_it
sudo usermod -aG itdept jack_it
Step 4: Create shared directory and file
sudo mkdir -p /home/shared/itdept
sudo touch /home/shared/itdept/project_specs.txt
Step 5: Set ownership and permissions
sudo chown root:itdept /home/shared/itdept/project_specs.txt
sudo chmod 770 /home/shared/itdept/project_specs.txt
Verification Commands
Verify users
cat /etc/passwd
Verify groups
getent group marketing
getent group itdept
Verify file permissions
ls -l /home/shared/marketing
ls -l /home/shared/itdept
Results
Successfully created:
10 users
2 groups
Secure individual files
Secure shared group file
Proper ownership and permissions
Key Observations

Linux uses user IDs (UID) and group IDs (GID) to manage access
chmod controls file permissions
chown changes ownership
Groups allow collaborative access control
Permission 700 ensures maximum privacy

Lessons Learned
Linux user management is essential for cybersecurity
Proper file permissions prevent unauthorized access
Group management simplifies access control
Linux security is based on least privilege principle

Examples:
User creation
Group creation
File permissions
Verification commands

Conclusion
This lab improved my practical skills in Linux administration, user management, and file security. These skills are essential for cybersecurity professionals and system administrators
