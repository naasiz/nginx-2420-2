**Setting up Nginx Server on Arch Linux**

This tutorial will guide you through setting up a fresh Arch Linux server on DigitalOcean to serve a demo document using Nginx.
**Installing Necessary Software
First, let's install the necessary software packages, including Vim and Nginx:

```
sudo pacman -Sy vim       # Install Vim text editor
sudo pacman -Sy nginx     # Install Nginx web server
```

**Create Project Directory**
Create a directory to store our website documents:
`sudo mkdir -p /web/html/nginx-2420`

**Create Nginx Configuration File**
Create a new configuration file for our project:
`sudo vim /etc/nginx/conf.d/nginx-2420.conf`

Add the following server block configuration:
```
server {
    listen 80;
    server_name your_server_ip;

    root /web/html/nginx-2420;
    index index.html;

}
```

**Create the HTML document**

Create a new file named "index.html" inside the "/web/html/nginx-2420" directory:
`sudo vim /web/html/nginx-2420/index.html`
and paste this html document into it:
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>2420</title>
    <style>
        * {
            color: #db4b4b;
            background: #16161e;
        }
        body {
            display: flex;
            align-items: center;
            justify-content: center;
            height: 100vh;
            margin: 0;
        }
        h1 {
            text-align: center;
            font-family: sans-serif;
        }
    </style>
</head>
<body>
    <h1>All your base are belong to us</h1>
</body>
</html>


**Restart Nginx Service**
Restart the Nginx service to apply the changes:
`sudo systemctl restart nginx`

**Start Nginx Service**
Start the Nginx service to serve our website:
`sudo systemctl start nginx`

**Lastly**
search your ip address in your browser and you should be able to see the content of the html file
