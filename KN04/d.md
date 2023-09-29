# AWS Storage-Optionen

## 1. EBS (Elastic Block Store) - Block-Storage
- **Persistenz:** Ja
- **Geschwindigkeit:** Hoch
- **Sicherheit:** Zugriff nur durch gebundene EC2-Instanz; Verschlüsselung möglich.
- **Standort:** Regionsspezifisch
- **Besonderheiten:** Verschiedene Volume-Typen, Snapshots, anpassbare Größe.
- **Anwendungsbeispiel:** Datenbanken und Anwendungen, die schnellen Zugriff benötigen.

## 2. S3 (Simple Storage Service) - Object-Storage
- **Persistenz:** Ja
- **Geschwindigkeit:** Variabel
- **Sicherheit:** Feingranulare Zugriffskontrollen, Versionierung, Objektverschlüsselung.
- **Standort:** Global
- **Besonderheiten:** Lebenszyklus-Policies, Ereignisbenachrichtigungen, unlimitierte Datenspeicherung.
- **Anwendungsbeispiel:** Web-Hosting, Backups, Data Lakes.

## 3. EFS (Elastic File System) - File-Storage
- **Persistenz:** Ja
- **Geschwindigkeit:** Hoch
- **Sicherheit:** NFS-Zugriff, Verschlüsselung.
- **Standort:** Regionsspezifisch
- **Besonderheiten:** Skalierbar, gleichzeitiger Multi-Zugriff, Pay-as-you-go.
- **Anwendungsbeispiel:** Content Management und Entwicklungs-Workflows.

---

*Hinweis:* Die Wahl zwischen diesen Storage-Optionen hängt von den spezifischen Anforderungen ab. Es ist wichtig, ihre Stärken und Schwächen zu verstehen.
