# misc

* Ubuntu
* Tomcat 8
* Autoscaling with auto scaling groups
* 2 instances
* Alerts


CloudFormation
    Create instances
    Create autoscaling group
    AWS::CloudFormation::Init
        PACKAGES ansible git
        FILES ssh config with deployment key for ansible using github
        COMMANDS Checkout ansible code. Start ansible code
    Autoscaling Group

Ansible
    dist-upgrade
    download tomcat8 debs install them one by one
    install ansible latest form ubuntu PPA: ppa:ansible/ansible
    TOMCAT8
        # template for: /etc/tomcat8/tomcat-users.xml
        # restart tomcat
    get WAR clojure WAR file: download it to: /var/lib/tomcat8/webapps/clojure-collector-1.1.0-standalone.war
    Deploy war file by restarting tomcat8
