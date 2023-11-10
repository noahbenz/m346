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

### Snapshots:

Momentaufnahme eines EBS-Volumes zu einem bestimmten Zeitpunkt.
Speichert nach dem ersten Snapshot nur die Änderungen (inkrementell).
Beschränkt auf EBS-Volumes.
Verwaltung kann manuell oder automatisiert erfolgen.
Geringere Flexibilität, da es sich hauptsächlich auf EBS-Volumes bezieht.
Geeignet für schnelle und effiziente Sicherung von EBS-bezogenen Daten.

### Backups:
Vollständige Sicherung von AWS-Ressourcen, einschließlich Konfigurationen.
Kann mehr Zeit und Speicher in Anspruch nehmen, da es umfassender ist.
Enthält verschiedene Ressourcen wie EC2-Instanzen, Datenbanken, S3-Buckets und mehr.
Zentralisiert und verwaltet durch den AWS Backup Service.
Bietet höhere Flexibilität und Kontrolle über die Sicherungsobjekte.
Geeignet für komplexe Sicherungsstrategien und Disaster Recovery.