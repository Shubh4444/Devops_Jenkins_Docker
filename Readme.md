# J

## step 1
```
sudo apt update
```
-----------
```
sudo apt install openjdk-8-jdk
```

## step 2
```
curl -fsSL https://pkg.jenkins.io/debian-stable/jenkins.io.key | sudo tee /usr/share/keyrings/jenkins-keyring.asc > /dev/null
```

## step 3
```
sudo apt update
```
-------------
```
sudo apt install jenkins
```

-------------------
```
sudo systemctl status jenkins
```

## step 4 

```
sudo ufw allow 8080
```

------------------------------
```
sudo ufw status
```

------------------------------
```
sudo ufw enable
```

## step 5
```
http://ip_address_or_domain:8080
```

----------------
```
http://localhost:8080
```

------------------------------
```
sudo cat /var/lib/jenkins/secrets/initialAdminPassword
```


-----------
Finally 
3. The system returns an alphanumeric code. Enter that code, then click Continue.

4. Next, you are prompted to either Install suggested plugins or Select plugins to install. It’s fine to simply install the suggested plugins. 

5. Then you will be prompted to Create First Admin User. 

Enter the credentials you want to use for your Jenkins administrator, then Save and Continue.

6. After this, you should set up the Instance Configuration. This is the preferred network address for this Jenkins installation. Confirm the address you want to use for your server. This is most likely the same address you used to get to this configuration page. When you’re satisfied, click Save and Finish.

7. You should see a page that says Jenkins is ready! 

# S 

## Step 1 - Create a Directory for the Website

Make sure that you have your HTML files already in the current directory.

## Step 2 - Create a file called Dockerfile

Place the following contents into the Dockerfile
```
FROM nginx:alpine
COPY . /usr/share/nginx/html
```

These lines of code represent the image we're going to use along with copying the contents of the current directory into the container.

## Step 3 - Build the Docker Image for the HTML Server

Run the following command:
```
docker build -t html-server-image:v1 .
```

You can confirm that this has worked by running the command:

docker images

## Step 4 - Run the Docker Container

Run the following command to run the HTML container server:
```
docker run -d -p 80:80 html-server-image:v1
```
## Step 5 - Test the Port with cURL

Run the following command to ensure the server is running:
```
curl localhost:80
```


# D

## 
------------
```
 sudo apt-get update

 sudo apt-get install docker-ce docker-ce-cli containerd.io docker-compose-plugin
 ```

---------------
```
apt-cache madison docker-ce
```
------------------

```
sudo apt-get install docker-ce=<VERSION_STRING> docker-ce-cli=<VERSION_STRING> containerd.io docker-compose-plugin
```
---------

```
sudo docker run hello-world
```






# E
## step 1 Installing Email Extension Plugin.

Open Jenkins using the following URL: http://localhost:8080/ on any browser (in this tutorial port 8071 is used).

Click on Manage Jenkins.

Click on Manage Plugins.

Select Email Extension and Email Extension Template Plugin and click Install Without Restart.

## step 2 Configure Email Notifications

    Click on Manage Jenkins and then Configure system
    
    Scroll below till E-mail Notification and click on advanced. Setup up as shown in below screenshot and save it.

You can test configurations by entering recipient email address and clicking on test configuration. If all is good it will show a message - Email sent successfully. You may get error while testing configurations, below is possible errors and solution to it.

Note: **In step 4 you will see the steps to configure email content and set triggers using Extended Email Notification. **

## Step 3 — Configuring Email-Notification in our jobs or pipeline

   1.  Go to your Jenkins home page and click on the created job (Here its gradlerun)

2) Click on Manage Plugins

3) Once your job configuration opens, scroll down to add post-build action and select Email Notifications.

4) Enter recipients and check Send Email for every unstable build and save it.

## Step 4 - Configure Extended Email Notification

From step 2, scroll below till Extended E-mail Notification and setup as shown in the screenshot. You can set your own triggers also, every option or setting in self-explanatory, configure it as per your requirement.

That's it you have successfully configured email settings, Lets set this up in our pipeline or jobs.

## Step 5 — Configure Extended Email Notification in Jenkins job

From step 3 in add post-build action and select Editable Email Notifications.

Once it is added in build action save it.
