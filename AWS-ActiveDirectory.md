AWS Active Directory
==========================

Active Directory is one of the most popular directory service developed by Microsoft
The server running the AD service is called as the domain computer and it can authenticate and authorize the users and computers which are associated to it
 
### Challenges with Active Directory

For those who have setup a directory before knows this can be challenging and time consuming process
Some of the challenges involved can be:
Provisioning the infrastructure
Installing the directory software
Getting replication setup between domain controllers for HA
Monitoring / Patching and many more
 
AWS Directory Service is a managed service based on cloud that allows us to create directories and let AWS experts handle and manage the other parts like HA, monitoring, backups, recovery and others.
There are 3 important components:
Active Directory Service with Microsoft AD
Simple AD
AD Connector
 
 
### AWS Directory Service with Microsoft AD


AWS Directory Service for Microsoft AD is powered by an actual Microsoft Windows Server AD in the AWS Cloud
There are 2 types:
Standard Edition – For small and midsize(up to 5000 users)
Enterprise Edition – For larger deployments
 
### AD Connector

It is a proxy service that provides easy way to connect applications in cloud to your existing on-premise Microsoft AD
When users log in to the applications, AD Connector forwards sign-in requests to your on-premises AD domain controllers for authentication
 
### Simple AD

Simple AD is a Microsoft AD – compatible directory from AWS Directory Service that is powered by Samba 4
Simple AD supports basic Active Directory features such as user accounts, group memberships, joining a Linux domain or Windows based EC2 instances, Kerberos-based SSO, and group policies. AWS provides monitoring, daily snapshots, and recovery as part of the service
Simple AD does not support trust relationship, DNS dynamic update, schema extensions, multi-factor authentication, communication over LDAPS, PowerShell AD…..FSMO role transfer.
 
 
### Domain Joining the EC2 Linux Instance with Directory Service

    yum -y install sshd realmd krb5-workstation
    realm join -U administrator@simplead.bob.jp simplead.bob.jp –verbose
    vi /etc/ssh/ssh_config ; Enable PasswordAuthentification yes
    service sshd restart
    nano /etc/sudoers -> %Domain\Admins@example.com ALL=(ALL:ALL) ALL
    service sshd restart


