D) Auftrennung von Web- und Datenbankserver (Advanced)

Ausgangslage:
Früher dominierten Monolithen als vorherrschende Architektur die IT. Hierbei wurde die gesamte Anwendung als eine einzige Einheit entwickelt, getestet und bereitgestellt. Dazu gehörten neben der Hardware auch das Betriebsssystem, Storage- und Datenbankanwendungen. Dabei entstanden oftmals komplexe und untrennbare Abhängigkeiten. Wenn z.B. ein Kernel-Patch installiert wurde, musste das gesamte System heruntergefahren. Das bedeutete oft Wochenendarbeit für die IT-Mitarbeiter und Downtime für die Applikation. Mit dem Aufkommen von komplexen und skalierbaren Anforderungen haben sich deshalb Microservices als Alternative etabliert und inzwischen durchgesetzt. Microservices zerlegen die Anwendung in unabhängige, spezialisierte Dienste, was eine verbesserte Skalierbarkeit, Wartbarkeit und Flexibilität ermöglicht. Diese Verschiebung markiert einen Wandel hin zu agileren und anpassungsfähigeren Ansätzen in der heutigen Softwarelandschaft.

Anleitung
In KN02 hatten Sie eine virtuelle Instanz installiert mit Web- und Datenbankserver. Sie haben gesehen, dass viele Befehle ausgeführt werden müssen und dass die gesamte Anwendung schlussendlich auf nur einer Instanz läuft. Wenn Sie nun dieselbe Anwendung nochmals installieren, müssten Sie sämtliche Schritte immer wieder von Hand (imperativ) durchführen. Cloud-init hilft Ihnen die Installation zu vereinfachen/automatisieren. Man spricht dann von der deklarativen Methode und von Infrastructure as Code. Beide Begriffe werden Sie in ihrer Laufbahn als Plattformentwickler noch des öfteren hören und lesen.
Die drei wichtigsten Vorteile von Cloud-init sind:


Automatisierte Bereitstellung: Cloud-init ermöglicht die automatische Konfiguration und Initialisierung von virtuellen Maschinen, wodurch die Bereitstellung beschleunigt und vereinfacht wird.

Skalierbarkeit: Durch die Anwendung von identischen Konfigurationen auf mehreren Instanzen können Ressourcen leicht skaliert werden, um auf steigende Anforderungen zu reagieren.

Zentrale Verwaltung und Aktualisierung: Cloud-init ermöglicht eine zentrale Verwaltung von Konfigurationen und erleichtert die Aktualisierung und Wartung von VM-Instanzen, was Konsistenz und Wartbarkeit fördert.


![Alt text](mariadbconnect.png)