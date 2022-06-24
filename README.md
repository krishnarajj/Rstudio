# Rstudio IAC using Aws cloudformation

# Important.
 please run this cloudfromation template in ap-south-1 region the api mentioned in the template is intented to run in ap-south-1 region U can customize the ami based on supported region. 
# ---
RStudio Workbench, formerly RStudio Server Pro 1, is the preferred data analysis and integrated development experience for professional R users and data science teams who use R and Python.
The template uses AWS Amazon Machine Images (AMIs) that already have the products installed.

The created infrastructure consists of one EC2 Instance and one Security Group for each of the following:

RStudio Workbench
RStudio Connect
RStudio Package Manager

# Prerequisites
AWS account 

AWS Virtual Private Cloud (VPC)

Subnet inside the selected VPC (If the subnet that you select is not in the VPC that is selected, then your deployment will fail)

AWS Key pair

Permissions to create security groups

Permissions to create EC2 instances

# Step1
Navigate to aws cloudformation console .
Click on create stack 
upload the Rstudio Yaml file 
Click next
# Global configuration
In the parameters Select the vpc that you want to launch the resourse.

![net](https://user-images.githubusercontent.com/96655654/175560807-e0bf9a43-d23d-41b3-ba48-45fd00aa9981.png)


Select the subnet In which your Rstudio instance will be created . Make sure to check it is a public subnet.
![global](https://user-images.githubusercontent.com/96655654/175560879-bd085bad-39a3-4711-8a79-73c4090b66ba.png)


In the above IAC template considering the Testing environment I have used t2.micro instance type.But the adviseble instance type is m5.large.Make sure to change that when you launch your stack in your production environment.


Root Volume Size (default and minimum: 50 GB or 120 GB for RSPM

Make the to the changes Options page changes that you require for your stack and click Next. The Review page displays.

The final parameters will look like this .
![para](https://user-images.githubusercontent.com/96655654/175561147-5ea454d9-ff89-4b15-a06d-20c0ebe44ce8.png)

Click create stack.

Connect to RStudio products#
From the AWS CloudFormation page:

Locate and select your stack’s corresponding check box.

Verify that your deployment is complete from the Status column.

Once your deployment is complete, select the Outputs tab.

Click the RStudio UI link to open the RStudio Professional products in the browser.

# Default User and password
The default user for Rstudio workbench is rstudio
The default password for Rstudio workbench is Instance ID
# Rconnect
To use the Rconnect . click the Rconnect UI link in the Outputs tab.
