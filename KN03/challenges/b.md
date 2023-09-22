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



 ### Was passiert?
 - Durch den generierten Key im Putty wird der zweite Schlüssel **noah-3.pem** überschrieben mit **noah-1.pem**
 - **Grund:** Das .yaml file welches wir bei additional settings eingefügt haben, hat den Key überschrieben.