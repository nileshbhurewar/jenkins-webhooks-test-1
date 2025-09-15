# Jenkins Pipeline with GitHub Webhooks

This guide describes how to automate your website deployments using Jenkins, GitHub webhooks, and Nginx.

## Jenkins Pipeline Setup

Create a Jenkins Pipeline job and configure it with your website's GitHub repository using webhooks.

## GitHub Webhook Setup

1. Go to your GitHub repository **Settings** → **Webhooks** → **Add webhook**
2. Set Payload URL to:

http://<your-jenkins-server>:8080/github-webhook/

text
3. Select `application/json` as content type.
4. Choose to send a webhook for **push events**.

## Provide Jenkins Root Privileges

Give Jenkins user passwordless sudo access for automation tasks:

sudo visudo

text

Add the following line at the end:

jenkins ALL=(ALL) NOPASSWD: ALL

text

Restart Jenkins to apply changes:

sudo systemctl restart jenkins

text

## Install Nginx Server

Install Nginx on your server as follows:

sudo apt update
sudo apt install nginx -y
