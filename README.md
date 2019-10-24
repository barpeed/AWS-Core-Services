# AWS-Core-Services

En el script de ejemplo siguiente, crea y configura nuestro servidor web.

<https://us-east-1.console.aws.amazon.com/cloud9/ide/6d52eb8b012a4bb99a722ac23102ab10>

```bash
#!/bin/bash
yum update -y
sudo yum install -y httpd24 php70 mysql56-server php70-mysqlnd
sudo service httpd start
sudo chkconfig httpd on
sudo usermod -a -G apache ec2-user
sudo chown -R ec2-user:apache /var/www
sudo chmod 2775 /var/www
find /var/www -type d -exec sudo chmod 2775 {} \;
find /var/www -type f -exec sudo chmod 0664 {} \;
echo "<?php phpinfo(); ?>" > /var/www/html/phpinfo.php
echo "<html><h1>Hola AWS</h1></html>" > /var/www/html/index.php

```

```bash
git clone https://github.com/barpeed/AWS-Core-Services.git



chmod 400 ImmersionDayCoreServices.pem

ssh -i "ImmersionDayCoreServices.pem" ec2-user@ec2-3-86-185-53.compute-1.amazonaws.com


```
