## D) Auftrennung von Web- und Datenbankserver (Advanced)

Früher basierte IT auf monolithischen Systemen mit komplexen Abhängigkeiten, die bei Änderungen zu Downtimes führten. Heute dominieren Microservices, die für mehr Skalierbarkeit und Flexibilität sorgen und den Trend zu agileren Softwareansätzen zeigen. Bei der Installation von Anwendungen wie in KN02 können durch Cloud-init Automatisierungen statt manuellen Wiederholungen erreicht werden. Dies fällt unter die Konzepte der deklarativen Methode und "Infrastructure as Code".

### Instanzbilder:

1. **DB and Web Instance**  
   ![DB and Web Instance](dbandweb.png)

2. **Inbound Rule to DB**  
   ![Inbound Rule to DB](image-1.png)

3. **Inbound Rule to Web**  
   ![Inbound Rule to Web](image-2.png)

4. **Connecting to DB with Command**  
   ![Connecting to DB](command.png)

5. **MySQL Connection**  
   - Command: `sudo mysql -u admin -p`
   - Entered password: 'password'  
     ![MySQL Connection](mariadbconnect.png)

6. **Telnet Configuration**  
   ![Telnet](image-3.png)

### Webseiten aufrufen:

1.  ### **Index.html**  
   ![Index.html](image-4.png)

2.  ### **PHP Page**  
   ![PHP](image-5.png)

3.  ### **Database Page**  
   ![DB](image-6.png)

4.  ### **Adminer Connection**  
   ![Adminer](image-7.png)

5. ### **Zu DB**  
   ![Zu DB](image-8.png)  
   Hinweis: Ich musste mich mit dem Login und der IP vom Db Server verbinden.
- In dieser URL befinde ich mich: http://3.94.54.92/adminer/?server=172.31.82.68&username=admin&db=mysql