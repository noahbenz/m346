# Lab: Auto Scaling Group erstellen und anwenden

## Template erstellen

1. Klicken Sie auf "Startvorlage erstellen".
2. Geben Sie folgende Informationen ein:
   - Name: M346-BEN-WebAccess
   - Betriebssystem: Amazon Linux 2
   - Instanztyp: t2.micro
   - Schlüsselpaar: Nicht in Startvorlage aufnehmen
   - Netzwerkeinstellungen:
     - Subnetz: Nicht in Startvorlage aufnehmen
     - Sicherheitsgruppe: M346-BEN-WebAcc
   - User Data: (Hier kommt das Bash-Skript)
     ```bash
     #!/bin/bash
     yum update -y
     yum install -y httpd
     systemctl start httpd
     systemctl enable httpd
     EC2AZ=$(TOKEN=`curl -X PUT "http://169.254.169.254/latest/api/token" -H "X-aws-ec2-metadata-token-ttl-seconds: 21600"` && curl -H "X-aws-ec2-metadata-token: $TOKEN" -v http://169.254.169.254/latest/meta-data/placement/availability-zone)
     echo '<center><h1 style="background-color:powderblue;">M346 KN06 C - Diese EC2 Instanz ist in der AZ: AZID </h1></center>' > /var/www/html/index.txt
     sed "s/AZID/$EC2AZ/" /var/www/html/index.txt > /var/www/html/index.html
     ```
3. Erstellen Sie die Auto Scaling-Gruppe und nutzen Sie sie später beim Erstellen von neuen Instanzen.

Wenn Sie den Auto Scaler mit Load Balancer kombinieren, erhält der dahinterliegende Service eine höhere Verfügbarkeit.

## Auto Scaling Group erstellen

1. In der linken Navigation unter "Auto Scaling" auf "Auto Scaling-Gruppen" klicken.
2. Klicken Sie oben auf "Auto-Scaling-Gruppe erstellen".
3. Geben Sie folgende Informationen ein:
   - **Name**: KN06_FAN_AutoScalingGroup
   - **Startvorlage**: M346-FAN-Template
4. Klicken Sie auf "Weiter".
5. Geben Sie die Netzwerkeinstellungen ein:
   - VPC
   - Public us-east-1a
   - Public us-east-1b
6. Geben Sie die Gruppengröße ein:
   - Mindestanzahl: 2
   - Gewünschte Anzahl: 2
   - Maximale Anzahl: 2
7. Klicken Sie auf "Auto-Scaling-Gruppe erstellen".

### Aufgaben des Auto Scalers:

- Starten und Beenden von EC2-Instanzen dynamisch (horizontales Skalieren - Scale Out).
- Unterstützt Elasticity und Scalability.
- Reagiert auf EC2-Statusüberprüfungen und CloudWatch-Metriken.
- Skaliert bedarfsgerecht (Performance) und/oder nach Plan (z. B. wenn bekannt ist, dass am Sonntagabend ein Backup-Job viel Ressourcen benötigt).

## Auto Scaling-Gruppe erstellt

![Alt text](image-14.png)

**Vergessen Sie nicht, "Public IP-v4" in den Public Subnets freizuschalten.**

### Probleme

- Funktioniert bei mir nicht, der Grund ist unbekannt :/
- Die URL kann nicht aufgerufen werden.
- Es wurde sowohl HTTP als auch HTTPS versucht.
- DNS und IPV4 wurden versucht, scheinen jedoch nicht zu funktionieren.
- Mit dem Lehrer überprüft und besprochen.
