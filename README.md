> 📚 For more info on all the possible docker variables, please check [the official Jira dockerhub page](https://hub.docker.com/r/atlassian/jira-software).

> ⚠️ I highly recommend using PostgreSQL as your DB backend as MariaDB was giving me all sorts of issues with Atlassian software. <br/>[View Jira PostgreSQL setup info](https://confluence.atlassian.com/adminjiraserver/connecting-jira-applications-to-postgresql-938846851.html).

By default this docker template is setup to access via https proxy (e.g. Letsencrypt) and a domain.

**Jira Home**  
*Container Path: /var/atlassian/application-data/jira*  
This is where Jira stores its appdata.  
**Default:** `/mnt/user/appdata/jira/`  

**Host Port 1**  
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
Controls whether non secure is allowed. Setting this to `false`  
**Default:** `true`  

**Proxy Port**  
If using something like Letsencrypt (highly recommended) you must specify the proxy port being used here, commonly `443`.  
*Container Variable: ATL_PROXY_PORT*  
**Default:** `443`  
