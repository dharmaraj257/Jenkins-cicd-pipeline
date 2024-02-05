
# Jenkins Projects

Automate Project deployment the usage of Jenkins, GitHub Webhooks & set up on Apache and nginx server

## Step 1: Install Jenkins on AWS by following the steps mentioned in the link below:

1.	Install Java 
2.	Install Jenkins 

https://www.jenkins.io/doc/book/installing/linux/
&nbsp;


## Step 2: Log into Jenkins port and Create a pipeline.

1.	Click new item, give the name Automated- pipeline, and select freestyle project click ok. 
2.	Give a description and select source code management as git.
3.	Copy your project GitHub repository link and paste it then select the branch GitHub repository.
4.	In build triggers and select GitHub hook trigger for GitScm Polling click apply button.

&nbsp;

## Step 3: Add a Web hook.

1.	Log in to GitHub and click the project repository.
2.	Then go to settings find webhooks and click webhooks.
3.	Click Add webhook and if ask to log in then enter your GitHub credentials.
4.	Copy your Jenkins URL in the section of the payload URL then add it after url/github-webhook/ ().
5.	Select content type application/json.
6.	In which events would you like to trigger this webhook? Select option let me select individual events.
7.	In this option you have to select 2 triggers and click add webhook.

 &nbsp;1. Pull requests

&nbsp;2. Pushes

8.	In Jenkins first save pipeline. Go to the repository section. Create a text file to its working or not.
9.	Automatically built will start to work.


## Step 4: Install server Apache and nginx.
```
1. sudo apt install apache2
````
    2. sudo apt install nginx.


## Step 5: Configure the pipeline and add build steps. We can copy content from the workspace folder to our Apache or Nginx server.

1.	In Jenkins go to pipeline click configure and in build steps select Execute shell.
2.	Add commands 

```
rm  /var/www/html/index.html
cp -r  *  /var/www/html
```
Now your application is deployed in the server to check copy paste your instance public IP.

# Output:

![Screenshot (125)](https://github.com/dharmaraj257/Jenkinscicd-pipeline/assets/100831265/ff1b42a3-d0f3-45fd-aa70-5097f58ffc86)
