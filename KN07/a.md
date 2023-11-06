A) Theorie: Recherche Datensicherung

| Kriterium       | Snapshots                                                   | Backups                                                      |
|-----------------|-------------------------------------------------------------|--------------------------------------------------------------|
| Definition      | Momentaufnahme eines EBS-Volumes zu einem bestimmten Zeitpunkt. | Vollständige Sicherung von AWS-Ressourcen.                   |
| Effizienz       | Speichert nach dem ersten Snapshot nur die Änderungen (inkrementell). | Kann mehr Zeit und Speicher beanspruchen, da es umfassender ist. |
| Wiederherstellung | Stellt den Zustand eines EBS-Volumes wieder her.               | Stellt verschiedene Ressourcen inklusive Konfigurationen wieder her. |
| Ressourcen      | Beschränkt auf EBS-Volumes.                                  | EC2-Instanzen, Datenbanken, S3-Buckets und mehr.             |
| Verwaltung      | Manuell oder automatisiert durch Amazon Data Lifecycle Manager. | Zentralisiert durch AWS Backup Service.                       |
| Flexibilität    | Weniger flexibel, da es nur für EBS-Volumes gilt.             | Höhere Flexibilität und Kontrolle über die Sicherungsobjekte. |
| Anwendungsfall  | Schnelle und effiziente Sicherung für EBS-bezogene Daten.     | Komplexe Sicherungsstrategien und Disaster Recovery.          |
