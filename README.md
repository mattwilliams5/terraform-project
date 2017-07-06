# terraform-project
Deploys wordpress site to aws with terraform once you clone and run this code you will need to go to the dev site that you set up before prod!! This way you can configure/install wordpress. I will add another prod script here in the near future!


## Create AWS account and IAM user before doing the following



1. get python
	python --version

2. get pip
	curl -O https://bootstrap.pypa.io/get-pip.py

3. Install pip
	python get-pip.py

4. Get aws cli
	pip install awscli

5. aws configure use your downloaded credentials from AWS IAM!

6. vim ~/.aws/credentials (optional change default to custom title in case you manage multiple environments)

7. export AWS_DEFAULT_PROFILE=your_new_name   (if you did the above step them export the new name!)

8. create keys for terraform/ansible
	ssh-keygen

9. Add new keys
	ssh-add ~/.ssh/your new key

10. Get terraform
	wget https://releases.hashicorp.com/terraform/0.7.10/terraform_0.7.10_linux_amd64.zip

11. Install terraform
	mkdir terraform 
	unzip terraform_0.7.10_linux_amd64.zip  -d ~/terraform

12. Move terraform to /usr/bin
	mv terraform /usr/bin/

13. Install ansible
	yum -y install ansible

14. Get a delegation-set
	[root@matt-williams-56 ~]# aws route53 create-reusable-delegation-set --caller-reference 12345
    {
    	"Location": "https://route53.amazonaws.com/2013-04-01/delegationset/NYQJ8QLPQ3KIM",
    	"DelegationSet": {
        	"NameServers": [
            	"ns-345.awsdns-43.com",
            	"ns-1166.awsdns-17.org",
            	"ns-980.awsdns-58.net",
            	"ns-1906.awsdns-46.co.uk"
        	],
        	"CallerReference": "12345",
        	"Id": "/delegationset/NYQJ8QLPQ3KIM"
    	}
	}
	
15. Get an IP
	[root@matt-williams-56 ~]# curl canhazip.com
	new IP addy
