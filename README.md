# Unraid Jira App Template

<img src="https://craftassets.unraid.net/uploads/_1200x630_crop_center-center_82_none/seo-unraid.png" width="700"/> <img src="https://github.com/Zerreth/UnraidJira/raw/master/Jira.png" width="128"/> 

> 📦 **Unraid Docker Template:** 🌐 [Jira.xml](https://github.com/Zerreth/UnraidJira/blob/master/Jira.xml)  
> ❤️ **Unraid Forum:** 🌐 [Visit Support Thread](https://forums.unraid.net/topic/94621-support-zerreth-jira/)  

## Setup Info

> 📚 For more info on all the possible docker variables, please 🌐 [Check the official Jira dockerhub page](https://hub.docker.com/r/atlassian/jira-software).

> ⚠️ I highly recommend using **PostgreSQL** (Postgres11 + PGAdmin4) as your DB backend as **MariaDB isn't supported** and was giving me all sorts of issues with Atlassian software.
🌐 [View Jira compatibility info](https://confluence.atlassian.com/jseng/supported-platforms-881686453.html) / 
🌐 [View Jira PostgreSQL setup info](https://confluence.atlassian.com/adminjiraserver/connecting-jira-applications-to-postgresql-938846851.html)

> ▶️ By default this docker template is setup to access via https proxy (e.g. Letsencrypt) and a domain. Check out this video by Spaceinvader One on Youtube how to set this up:

[![SpaceInvader One Letsencrypt Setup](http://img.youtube.com/vi/I0lhZc25Sro/0.jpg)](http://www.youtube.com/watch?v=I0lhZc25Sro)

> 📦 **LetsEncrypt Proxy-Conf Template:** 🌐 [JiraProxy.conf](https://github.com/Zerreth/UnraidJira/blob/master/JiraProxy.conf)  
\\\UNRAIDSERVER\Appdata\letsencrypt\nginx\proxy-confs\JiraProxy.conf **(Typical Letsencrypt Proxy-Conf location)**


## Docker Container Variables

> ⚠️ The official documentation defines the ATL parameters in uppercase, whilst the actual internal xlm defines them in lowercase. Some users have reported that these are case sensitive and only respond to the lowercase values.

**Jira Home**  
*Container Path: /var/atlassian/application-data/jira*  
This is where Jira stores its appdata.  
**Default:** `/mnt/user/appdata/jira/`  

**Jira Port**  
*Container Port: 8080*  
The port used to access Jira's web interface.  
**Default:** `9080`  

**Proxy Fully Qualified Hostname**  
*Container Variable: ATL_PROXY_NAME*  
The subdomain/domain used to access Jira. This must be specified for HTTPS access to work.  
**Default:** `please.replace.me`  

**Proxy Protocol Scheme**  
*Container Variable: ATL_TOMCAT_SCHEME*  
Switch between `http` or `https` for access.  
**Default:** `https`  

**Proxy Require HTTPS for Login**  
*Container Variable: ATL_TOMCAT_SECURE*  
Enforces secure login (https). Setting this to `false` will allow users to login using insecure connections (http).  
**Default:** `true`  

**Proxy Port**  
If using something like Letsencrypt (highly recommended) you must specify the proxy port being used here, commonly `443`.  
*Container Variable: ATL_PROXY_PORT*  
**Default:** `443`  
