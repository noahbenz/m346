# SSH-Key und Cloud-init (Beginner)

### Ausgangslage:
Sie wissen bereits, wie man auf AWS ein SSH Keypair erstellt und können sich mit diesem Key per SSH mit einer Instanz in der Cloud verbindet. Dieser Challenge geht nun etwas tiefer. Weil das Keypair von AWS und nicht von Ihnen erzeugt wurde, fehlt ihnen noch der Public-Key zu Ihrem bereits bei sich abgelegten Private Key (file.pem). Mit puttygen können Sie jederzeit den zugehörigen Public Key erzeugen. Diesen können Sie dann auf jeder beliebigen Instanz in der Cloud ablegen, um schnell darauf zuzugreifen.

Anleitung
Anstatt, dass Sie den SSH-Key im GUI auswählen, können Sie ihn auch im Cloud-Init mitgeben. Dies werden wir folgend tun.  Installieren Sie puttygen, falls Sie es noch nicht haben (unter Quellen finden Sie den Link). Extrahieren Sie den öffentlichen Schlüssel (für beide Keys) wie folgt.


### Verbinden mit Instanz

![public key inserted](publickeyinserted.png)


#### Key1
$ ssh ubuntu@18.232.112.230   -i noah-1.pem -o ServerAliveInterval=30
- Es funktioniert

#### Key2
$ ssh ubuntu@18.232.112.230   -i noah-3.pem -o ServerAliveInterval=30
![Key 2 try](key2try.png)

### Instanz
| Name  | Instance ID            | Instance state | Instance type | Status check          | Alarm status | Availability Zone | Public IPv4 DNS                          | Public IPv4 address | Elastic IP | IPv6 IPs | Monitoring | Security group name | Key name | Launch time             | Platform d  |
|-------|------------------------|----------------|---------------|-----------------------|--------------|-------------------|------------------------------------------|---------------------|------------|----------|------------|----------------------|----------|-------------------------|-------------|
| kn03c | i-04ed0718f830a1c6d    | Running        | t2.micro      | 2/2 checks passed     | No alarms    | us-east-1a        | ec2-54-146-59-31.compute-1.amazonaws.com | 54.146.59.31        | –          | –        | disabled   | launch-wizard-5      | noah-1   | 2023/09/22 10:06 GMT+2 | Linux/UNIX  |


 ### Was passiert?
 - Durch den generierten Key im Putty wird der zweite Schlüssel **noah-3.pem** überschrieben mit **noah-1.pem**
 - **Grund:** Das .yaml file welches wir bei additional settings eingefügt haben, hat den Key überschrieben.