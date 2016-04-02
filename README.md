## Misc Repository

* Ubuntu
* Tomcat 7
* Autoscaling with auto scaling groups
* 2 instances
* Alert based autoscaling up to 4 instances
  * if (cpu.avg(10) > 70%) then spawn more instances (not tested)

### CloudFormation
* Create ELB
* Create 2 instances (with ClojureLaunchConfig)
  * Bootstrap process via UserData
    * apt-get update
    * install ansible latest version from PPA
    * Setup /root/.ssh/config and /root/.ssh/dpkey1.pem for accessing this repository. This key provides read only access
    * git clone git@github-drn88:DRN88/misc.git /root/repoclone
    * remote /etc/ansible folder
    * Create symbolic link from repo to /etc/ansible
    * Run site based Ansible playbook as root: ansible-playbook /etc/ansible/site.yml
* Create autoscaling group
* Create ScaleUpPolicy
* Create CPUAlarmHigh trigger

### Ansible
* apt-get install tomcat7
* in tomcat7 role
  * Download/Deploy clojure-collector-1.1.0-standalone.war to /var/lib/tomcat8/webapps/clojure-collector-1.1.0-standalone.war
  * Fix permission on the war file for tomcat7 user and group
  * Restart tomcat to start the app

### Usage
* Get the LoadBalancer URL
* Run curl to test
``` bash
dorian@drnvm:~$ curl http://abc-ClojureELB-1AKHHFH4F7FQ5-499782227.eu-central-1.elb.amazonaws.com:8080/clojure-collector-1.1.0-standalone/i
GIF89a����!�,D;dorian@drnvm:~$
```
* PROFIT
