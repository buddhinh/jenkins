1. In Jenkins -> download Gitlab pugin and Gitlab API pluggin 

2. Create Gitlab access token 

![image-1](./images/access_token.png)

http://gitlab.local:8090/-/profile/personal_access_tokens 

![image-2](./images/access_token_2.png)

3. In Jenkins configure Gitlab access token-> Manage Jenkins>System 

http://jenkins.local:8080/manage/configure 

![image-3](./images/gitlab_token.png)

4. Create Access token in Jenkins 

Profile>configure 

![image-4](./images/jenkins_configure.png)
http://jenkins.local:8080/user/admin/configure 

![image-5](./images/api_token.png)

5. Create Jenkins Job 

In SCM, provide Git URL and credentials 

![image-6](./images/scm.png)

 

In Build triggers section, provide when to trigger. 

![image-7](./images/build_trigger.png)

6. In Gitlab project, go to settings>webhooks and add new webhook 

 

http://gitlab.local:8090/jenkins/maven/-/hooks 

URL should be in following format: 

http://<jenkins-user>:<jenkins_api_token>@<jenkins_base_url>:<port>/project/<project_name>/ 

Eg: http://admin:11e4310a9f6ac981ea11f921474c102602@jenkins:8080/project/maven-job/ 

 
Then test 

Note: if error occurs if jenkins URL is localhost, follow this path in Gitlab 

Allow requests to the local network from web hooks and services” in the “Outbound requests” section inside the Admin Area > Settings (/admin/application_settings/network): Go to Outbound requests section and allow requests to the local network from webhooks and integrations 
