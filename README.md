# jenkins
### Install
https://www.jenkins.io/doc/book/installing/

### jenkins when run via systemd
1. /etc/systemd/system/jenkins.service
This file is managed by systemd(1). Do NOT edit this file manually!
   ```
    systemcatl cat jenkins.service
   ```

2. To override these settings, run:  
   ```  
    systemctl edit jenkins
   ```

If you edit the drop-in unit without systemctl(1), you need to run systemctl daemon-reload for the changes to take effect.

The override.conf file is stored at /etc/systemd/system/jenkins.service.d/override.conf

- Debian
/lib/systemd/system/jenkins.service

- Red Hat
/usr/lib/systemd/system/jenkins.service

- openSUSE
/usr/lib/systemd/system/jenkins.service

3. For more information about drop-in files, see:
    https://www.freedesktop.org/software/systemd/man/systemd.unit.html



### run in local jenkins-cli
   ```
export JENKINS_USER_ID=devops
export JENKINS_API_TOKEN=112a494f1c96d19dd64d877ed6f7fdb220
export JENKINS_URL=http://192.168.59.10:8085/
locate jenkins-cli.jar
wget -P ~/bin ${JENKINS_URL}/jnlpJars/jenkins-cli.jar
alias jenkins-cli='java -jar ~/bin/jenkins-cli.jar -s ${JENKINS_URL}'
jenkins-cli
   ```

### Add the auth file
alias jenkins-cli='java -jar ~/bin/jenkins-cli.jar -s ${JENKINS_URL}' -auth @/Users/mark.honomichl/.jenkins-cli

### Single-quotes and double-quotes
def name = 'Jenkins'
echo "Hello, ${name}!"  // Output: Hello, Jenkins!
echo 'Hello, ${name}!'  // Output: Hello, ${name}!
