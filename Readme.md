# Jenkins

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

# Deploy Site on Docker 

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


# Install Docker Engine

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




