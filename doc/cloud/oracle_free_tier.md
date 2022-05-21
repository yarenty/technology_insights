

https://docs.oracle.com/en-us/iaas/Content/FreeTier/freetier_topic-Always_Free_Resources.htm#Details_of_the_Always_Free_Compute_instance__a1_flex


VM.Standard.A1.Flex shape (Arm-based Ampere A1 Compute): Because the VM.Standard.A1.Flex shape is a flexible shape, you can customize the number of OCPUs and amount of memory that are allocated when you create or resize an instance. You can use all of the Always Free OCPUs and memory to create a single instance, or create multiple smaller instances that each use a portion of the resources.

Processor: 4 OCPUs total, which you can allocate flexibly
Memory: 24 GB total, which you can allocate flexibly
Networking: The network bandwidth and number of VNICs scale proportionately with the number of OCPUs. For details, see Flexible Shapes.
Image: Your choice of one of the following Always Free-eligible images:

Oracle Linux Cloud Developer

Oracle Linux Cloud Developer provides the latest development tools, languages and Oracle Cloud Infrastructure software development kits (SDKs) to rapidly launch a comprehensive development environment. The Oracle Linux Cloud Developer image requires at least 8 GB of memory.

Oracle Linux
Ubuntu
For steps to create an Always Free-eligible compute instance, see Tutorial - Launching Your First Linux Instance.

 Tip

The Linux images labeled "Always Free Eligible" in the Console are compatible with Always Free compute instances and incur no licensing fees. These images are also compatible with paid resources and are available to users of paid accounts. To provision a compute instance with an image that is not Always Free-eligible, you must have a paid account or a Free Trial account with available credits.
Block Volume
All tenancies receive a total of 200 GB of Block Volume storage, and five volume backups included in the Always Free resources. These amounts apply to both boot volumes and block volumes combined. When you provision a compute instance, the instance automatically receives a 50 GB boot volume for storage. You can also create and attach block volumes to expand the storage capacity of a compute instance. For more information, see Creating a Volume and Attaching a Volume.

Details of the Always Free Block Volume resources
Object and Archive Storage
All tenancies get a total of 20 GB of Always Free Object Storage.

Details of the Always Free Object Storage resources
Vault
All master encryption keys protected by software are free. All tenancies get 20 key versions of master encryption keys protected by a hardware security module (HSM) and 150 Always Free Vault secrets. You can spread these keys or secrets across any number of vaults in the tenancy, although virtual private vaults are not included in the Always Free resources.

Details of the Always Free Vault resources
Resource Manager
All tenancies get a set of Always Free resources in the Resource Manager service that allow you to automate the process of provisioning infrastructure using Terraform. See Quickly Launch Your Always Free Resources Using Resource Manager for instructions on using Resource Manager to create your Always Free resources.

Details of the Always Free Resource Manager resources
Database
All tenancies get two Always Free Oracle Autonomous Databases. You can use these databases for transaction processing, data warehousing, Oracle APEX application development, or JSON-based application development. For current regional availability, see the Always Free Cloud Services table in Cloud Regions—Infrastructure and Platform Services.

All tenancies also get an Oracle NoSQL Database with up to 133 million reads per month, 133 million writes per month, and 3 tables with 25 GB storage per table. Learn more about Oracle NoSQL Database.

Details of the Always Free Oracle Autonomous Database instance


## Apache and PHP

https://docs.oracle.com/en-us/iaas/developer-tutorials/tutorials/apache-on-ubuntu/01oci-ubuntu-apache-summary.htm




3. Enable Internet Access
The Create a VM Instance wizard automatically creates a VCN for your VM. You add an ingress rule to your subnet to allow internet connections on port 80.

Create an Ingress Rule for your VCN
Follow these steps to select your VCN's public subnet and add the ingress rule.

Open the navigation menu and click Networking, and then click Virtual Cloud Networks.
Select the VCN you created with your compute instance.
With your new VCN displayed, click <your-subnet-name> subnet link.
The public subnet information is displayed with the Security Lists at the bottom of the page. A link to the Default Security List for your VCN is displayed.

Click the Default Security List link.
The default Ingress Rules for your VCN are displayed.

Click Add Ingress Rules.
An Add Ingress Rules dialog is displayed.

Fill in the ingress rule with the following information.
Fill in the ingress rule as follows:

Stateless: Checked
Source Type: CIDR
Source CIDR: 0.0.0.0/0
IP Protocol: TCP
Source port range: (leave-blank)
Destination Port Range: 80
Description: Allow HTTP connections
Click Add Ingress Rules. Now HTTP connections are allowed. Your VCN is configured for Apache server.

Click Add Ingress Rules.
Now HTTP connections are allowed. Your VCN is configured for Apache server.
You have successfully created an ingress rule that makes your instance available from the internet.
4. Set up Apache and PHP
Next install and configure Apache web server and PHP to run on your Ubuntu Linux instance.

Install and Configure Apache and PHP
To install and set up Apache and PHP, perform the following steps:

Open the navigation menu and click Compute. Under Compute, click Instances.
Click the link to the instance you created in the previous step.
From the Instance Details page look under the Instance Access section, the Public IP Address field. Write down the public IP address the system created for you. You use this IP address to connect to your instance.

Open a Terminal or Command Prompt window.
Change into the directory where you stored the ssh encryption keys you created before.
Connect to your instance with this SSH command.
Copy
ssh -i <your-private-key-file> ubuntu@<x.x.x.x>
Since you identified your public key when you created the instance, this command logs you into your instance. You can now issue sudo commands to install and start your server.

Install Apache Server.
Copy
sudo apt update
sudo apt -y install apache2
Next start Apache.
Copy
sudo systemctl restart apache2
Update firewall settings.
The Ubuntu firewall is disabled by default. However, you still need to update your iptables configuration to allow HTTP traffic. Update iptables with the following commands.

Copy
sudo iptables -I INPUT 6 -m state --state NEW -p tcp --dport 80 -j ACCEPT
sudo netfilter-persistent save
The commands add a rule to allow HTTP traffic and saves the changes to the iptables configuration files.

You can now test your server.
You can test your server from the command line with curl localhost. Or, you can connect your browser to your public IP address assigned to your instance: http://<x.x.x.x>. The page looks similar to: Apache Server Test Page

Install PHP 7 with the following commands.
Copy
sudo apt -y install php libapache2-mod-php
Verify installation and restart Apache.
Copy
$ php -v
$ sudo systemctl restart apache2
Add a PHP test file to your instance.
Create the file:

Copy
sudo vi /var/www/html/info.php
In the file, input the following text and save the file:
Copy
<?php
phpinfo();
?>
Connect to http://<your-public-ip-address>/info.php.
The browser produces a listing of PHP configuration on your instance similar to the following.

PHP configuration Page
Note

After you are done testing, remove info.php from your system.
Congratulations! You have successfully installed Apache and PHP 7 on your Oracle Cloud Infrastructure instance.

