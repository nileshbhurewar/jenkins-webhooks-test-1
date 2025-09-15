Jenkins Pipeline with GitHub Webhooks
Create a Jenkins Pipeline job and configure it with your website's GitHub repository using webhooks.

GitHub Webhook Setup
Go to your GitHub repository Settings → Webhooks → Add webhook

Set Payload URL to:
http://<your-jenkins-server>:8080/github-webhook/
Select application/json as content type.

Choose to send a webhook for push events.

Provide Jenkins Root Privileges
Give Jenkins user passwordless sudo access for automation tasks:

sudo visudo
Add the following line at the end:

jenkins ALL=(ALL) NOPASSWD: ALL
Restart Jenkins to apply changes:

sudo systemctl restart jenkins
Install Nginx Server
Install Nginx on your server as follows:

bash
sudo apt update
sudo apt install nginx -y
