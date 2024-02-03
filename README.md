
# PROJECT-1 Deploy Wordpress website on AWS using Elastic Beanstalk

Created a simple web app which displays 
“Hello GUVI GEEK”.



## Step 1 : Git clone

 - [Github Project link](https://github.com/shreegs123/Project-1.git)
 


## Launch RDS database →

Step 1 → Search RDS on aws console and then click on create database

Step 2 → Choose standard create and then mysql engine

![App Screenshot](https://github.com/shreegs123/Project-1/blob/main/ss1.png?raw=true)

Step 3 → Set your master name and password 

![App Screenshot](https://github.com/shreegs123/Project-1/blob/main/ss2.png?raw=true)

Step 4 →  Give the name to your database in the additional configuration and remain everything as it is and click on create database it takes up to 3 to 4 minutes to configure everything.

![App Screenshot](https://github.com/shreegs123/Guvi_Interview_Task/blob/main/T1.png)

## Launch Elastic Beanstalk  →

Step 1 → Search Elastic beanstalk on aws console and then click on create application

Step 2 → Choose web server environment and then give name to your application

![App Screenshot](https://github.com/shreegs123/Project-1/blob/main/ss3.png?raw=true)

Step 3 → Choose php from managed platform and then click next

![App Screenshot](https://github.com/shreegs123/Project-1/blob/main/ss4.png?raw=true)

Step 4 → In service role click create and use new service role and select aws-elasticbeanstalk-service-role from it

Step 5 → Choose your ec2 keypair and your ec2 instance profile to ec2accessdemoapp

![App Screenshot](https://github.com/shreegs123/Project-1/blob/main/ss5.png?raw=true)

Step 6 → In VPC choose default vpc and then select your instance subnet and database subnets

![App Screenshot](https://github.com/shreegs123/Project-1/blob/main/ss6.png?raw=true)

![App Screenshot](https://github.com/shreegs123/Project-1/blob/main/ss7.png?raw=true)

click next

Step 7 → Select the default security group from the options and click next

![App Screenshot](https://github.com/shreegs123/Project-1/blob/main/ss8.png?raw=true)

Step 8 → in health reporting choose basic and untick the manged updates options

Step 9 → Now connect your database by adding environment properties

1. RDS_HOSTNAME

The hostname of the DB instance.

where to find →On the Connectivity & security tab on the Amazon RDS console: Endpoint.

2. RDS_PORT

The port where the DB instance accepts connections. The default value varies among DB engines.

where to find →On the Connectivity & security tab on the Amazon RDS console: Port.

3. RDS_DB_NAME

The database name, ebdb.

where to find →On the Configuration tab on the Amazon RDS console: DB Name.

4. RDS_USERNAME

The username that you configured for your database.

where to find →On the Configuration tab on the Amazon RDS console: Master username.

5. RDS_PASSWORD

The password that you configured for your database.

Not available for reference in the Amazon RDS console.

![App Screenshot](https://github.com/shreegs123/Project-1/blob/main/ss9.png?raw=true)

Step 10 → review your configuration and click on sumbit

## Click on url provided by elastic beanstalk you will find a page like this

![App Screenshot](https://github.com/shreegs123/Project-1/blob/main/ss10.png?raw=true)


## Download the Wordpress app to deploy on elasticbeanstalk

Step1 : On Ubuntu terminal Create a folder using mkdir 
mkdir Wordpress
cd Wordpress

Step2 : git clone project url : https://github.com/shreegs123/Project-1/blob/main/wordpress.zip

Step3 : Download the Zip file to local machine using scp command on powershell

scp -i <keypair/path> <ubuntu@dns/public/ipadd>:<pathofwordpresszipfolfer> <folderpath/of/localmachine> 

## Upload and deploy →

step 1 → On elastic beanstalk console select upload and deploy option choose your wordpress file that you just downloaded and click on deploy

It also takes around 5 min to deploy the application

After it successful deployment click on url of the elasticbeanstalk page

If you find an error 404 ngnix not found, then

launch the ec2 instance created by elastic beanstalk

And follow these steps

cd /var/www/html/

#the location where the actual file is present that you uploaded from console

mv wordpress/* /var/www/html/ 

#this command will move the entire files from from wordpress folder

rm -rf wordpress

#this command will delete the wordpress folder

now again click on url you will find a web page where you wordpress application running

![App Screenshot](https://github.com/shreegs123/Project-1/blob/main/output.png?raw=true)







## Documentation

[Documentation](https://linktodocumentation)

