MySQL
======

MySQL is the world's most popular open source database. With its proven performance, reliability and ease-of-use, MySQL has become the leading database choice for web-based applications, covering the entire range from personal projects and websites, via e-commerce and information services. 
We have greatly simplified the parameters that you have to enter to create a product so that you can get started very quickly. The product launches in a matter of a few minutes and is ready to go.

Parameters
-----------

.. list-table:: 
   :widths: 50, 50
   :header-rows: 1

   * - Parameter
     - Details
   * - Product Name
     - Provide a name to help you easily identify this instance of the product. Only alphanumeric characters, dots, hyphens and underscores are allowed. Spaces and special characters are not allowed. Eg: MedicalResearch
   * - ConnectFromPort
     - Provide which Port has to be opened in the Security Group of the EC2 Instance to access MySQL Docker Container Eg: 3306
   * - KeyPair
     - Choose a KeyPair in the dropdown list. Note: If KeyPair is not available in the drop-down, click on the “+” button. A KeyPair creation form is opened. Fill the details in the form and click on the “Create KeyPair” button. Now that KeyPair is available in the list. Remember to save the private key file securely for future use. Do not share this file with others for the security of your account.
   * - ConnectToPort
     - Provide which Port has to be opened in the Security Group of the EC2 Instance to access MySQL Docker Container  Eg: 3306 
   * - LatestAmiId
     - LatestAmiId - Provide the location from where to pick the latest AMI on which the instance should be based. Valid values are: Amazon Linux 2 - /aws/service/ami-amazon-linux-latest/amzn2-ami-hvm-x86_64-gp2
   * - AllowedSSHLocation
     - This identifies the IP locations from where connections to this instance should be allowed. For the security of your instance, we recommend you allow connections only from your own location. You can find your IP using https://whatismyipaddress.com/
   * - InstanceType
     - Choose instance type in the drop-down list Eg: t2.small
   * - MasterPassword
     - Provide the root login password for MySQL DB.
   

.. image:: images/Mysql.png


Steps to launch
----------------

1. Click on the project on the “My Projects” page.
2. Navigate to the available products tab
3. Click the “Launch Now” button on the  “MySQL” product card. A product order form will open. Fill the details in the form and click the “Launch Now” button. You will see a MySQL product being created. In a few minutes, that product should appear in the “Active” state.

Estimated time to provision -  10 minutes

Steps to connect
----------------

You can connect to your EC2 instance through the RLCatalyst Research Gateway or via an external SSH client. If you are connecting from a Linux box use the following command:

If you are connecting from a Windows box you can use an SSH client like PuTTY.

1. Click on the project on the “My Projects” page.
2. Navigate to the “My Products” tab
3. Click on your instance in the My Products view. 
4. In the product details page, you will find the SSH/RDP button in the Connect pane on the right side. Click on the button to launch the SSH Launcher window in a separate tab of your browser. 
5. Select the Key file and click submit. The SSH window should open.
6. Confirm with Docker version (running) and Running MySQL Containers
7. Login to the MySQL shell using the command:  mysql -h<privateip-of-mysql-server-instance> -u root -p<MasterPassword>
8. Through the Explore action you can see the shared files with 1-click. Note: If project storage is not mounted you can’t see the explore action in the product details page.

If you are unable to connect, check your current IP address against the “AllowedSSHLocation” parameter provided at provisioning time.

Other considerations
---------------------

You can stop your instance using the “Stop” button in the product details page of your instance. The instance will incur lower costs when it is stopped than when it is running. Conversely, if the instance is stopped, use the “Start” button to get the instance “Running”.
