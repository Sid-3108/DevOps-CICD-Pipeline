Jenkins — Setup & Maven Build

This guide explains how Jenkins was installed and configured to build the **hello-world Java app**.

---

🔑 Unlock Jenkins
 Open Jenkins in browser:

 Enter the initial admin password:
bash
ssh ubuntu@<JENKINS_IP>
sudo cat /var/lib/jenkins/secrets/initialAdminPassword



🔌 Plugins

Maven Integration Plugin

(Optional) Unleash Maven Plugin

Install via: Manage Jenkins → Manage Plugins → Available tab

BUILD/ARTIFACT OUTPUT PATH:

/var/lib/jenkins/workspace/hello-world/target/


🐱‍🏍 (Optional) Deploy to Tomcat on same Jenkins server

Install Tomcat:

sudo apt install -y tomcat9 tomcat9-admin


Change port 8080 → 9999 in /etc/tomcat9/server.xml
(since 8080 is used by Jenkins):

sudo sed -i 's/8080/9999/' /etc/tomcat9/server.xml
sudo systemctl restart tomcat9


Copy the .war from Jenkins workspace:

sudo cp /var/lib/jenkins/workspace/hello-world/target/hello-world-war-1.0.0.war /var/lib/tomcat9/webapps/


BROWSER ACCESS WITH YOUR RESPECTIVE JENKINS IP

http://<JENKINS_IP>:9999/hello-world-war-1.0.0/
