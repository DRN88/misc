## Misc Repository

* Ubuntu
* Tomcat 8
* Autoscaling with auto scaling groups
* 2 instances
* Alerts

### CloudFormation
* Create instances
* Create autoscaling group
* AWS::CloudFormation::Init
  * PACKAGES install ansible latest form ubuntu PPA: ppa:ansible/ansible and git
  * FILES ssh config with deployment key for ansible using github
  * COMMANDS Checkout ansible code. Start ansible code
  * Autoscaling Group

### Ansible
* download tomcat8 debs install them one by one
* TOMCAT7
  * Download/Deploy clojure-collector-1.1.0-standalone.war to /var/lib/tomcat8/webapps/clojure-collector-1.1.0-standalone.war
  * Restarting tomcat to start the app
