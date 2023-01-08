# Bash Script to host Website
## Prerequisite - VM with Vagrant Box
Navigate to the Root User and create a script direcotry
```
mkdir /opt/scripts
```
Now naviate to the scripts directory and create a script
```
vim websetup.sh
```
Now put the following code in script file and save
```
#!/bin/bash

# Installing Dependencies
echo "##################"
sudo yum install wget unzip httpd -y
echo

# Start and Enable Service
echo "##################"
echo "Start and Enable Service"
echo "##################"
sudo systemctl start httpd
sudo systemctl enable httpd
echo

#creating temp direcotry
echo "##################"
echo "Starting the Deployment"
echo "##################"
mkdir -p /tmp/webfiles
cd /tmp/webfiles
echo
Now before executing the script give the script execute permission
```
chmod +x websetup.sh
```

wget https://www.tooplate.com/zip-templates/2130_waso_strategy.zip
unzip 2130_waso_strategy.zip
sudo cp -r 2130_waso_strategy/* /var/www/html/
echo

#Bounce Service
echo "##################"
echo "Restarting HTTPD Service"
echo "##################"
systemctl restart httpd

#Clean up
echo "##################"
echo "Removing Temprary Files"
echo "##################"
rm -rf /tmp/webfiles
echo

```
Now run the file
```
./websetup.sh
```
Once script is running then check the IP Address of VM
```
ipconfig
```
Copy and Paste the IP address in the browser and you will your website live.
