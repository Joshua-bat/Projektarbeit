<h1>IT-Infrastruktur mit cloudbasiertem 3-2-1-Backup für eine Zahnarztpraxis</h1>
<h2>Projektbeschreibung</h2>
<p>
  Im Rahmen meiner Abschlussprüfung zum IT-Spezialisten für Systemintegration
  (<em>Fachinformatiker für Systemintegration</em>) plane, konzipiere und implementiere ich eine
  IT-Infrastruktur für eine Zahnarztpraxis mit besonderem Fokus auf eine zuverlässige und
  revisionssichere Datensicherung. Da die Praxis sensible Patientendaten verarbeitet, müssen sowohl
  der laufende Betrieb als auch die Datensicherung höchsten Anforderungen an Verfügbarkeit,
  Datenschutz und Ausfallsicherheit genügen.
</p>
<p>Kernstück dieses Projekts ist die Umsetzung einer <strong>3-2-1-Cloud-Backup-Strategie</strong>:</p>
<ul>
  <li><strong>3</strong> Kopien der Daten (Produktivdaten + 2 Backups)</li>
  <li><strong>2</strong> unterschiedliche Speichermedien/-orte (z. B. lokales NAS und Cloud-Speicher)</li>
  <li><strong>1</strong> Kopie, die extern/in der Cloud gespeichert wird, um die Wiederherstellbarkeit
    auch bei lokalen Vorfällen (Brand, Diebstahl, Hardwareausfall) sicherzustellen</li>
</ul>
<h2>Projektziele</h2>
<ul>
  <li>Aufbau/Optimierung der bestehenden Netzwerk- und Serverinfrastruktur der Praxis</li>
  <li>Implementierung einer automatisierten, mehrstufigen Backup-Lösung nach dem 3-2-1-Prinzip</li>
  <li>Auswahl und Integration eines geeigneten Cloud-Backup-Anbieters unter Berücksichtigung der
    DSGVO-Anforderungen sowie praxisspezifischer Vorgaben (z. B. Aufbewahrungsfristen, Anforderungen
    an Gesundheitsdaten)</li>
  <li>Sicherstellung der Datenverschlüsselung sowohl bei der Übertragung als auch im Ruhezustand
    (in transit und at rest)</li>
  <li>Dokumentation eines Wiederherstellungskonzepts (Disaster-Recovery-Plan) inklusive
    Restore-Tests</li>
  <li>Durchführung einer Wirtschaftlichkeitsanalyse der gewählten Lösung im Vergleich zu
    Alternativen</li>
</ul>
<h2>Ist-Zustand</h2>
<p>
  Die IT-Infrastruktur der Praxis ist bereits vollständig virtualisiert, und ein Netzwerkdiagramm
  der bestehenden Umgebung wurde bereits erstellt. Darauf aufbauend wird die 3-2-1-Backup-Strategie
  wie folgt umgesetzt:
</p>
<ul>
  <li><strong>2</strong> – eine zweite Kopie der Daten wird auf einer separaten Festplatte
    gespeichert</li>
  <li><strong>1</strong> – eine zusätzliche, externe Kopie wird auf einem Nextcloud-Server
    gespeichert</li>
</ul>
<h2>Vorgehensweise</h2>
<ol>
  <li><strong>Analyse</strong> der bestehenden Infrastruktur und Anforderungen</li>
  <li><strong>Planung</strong> der Zielarchitektur, einschließlich Netzwerk-, Server- und
    Backup-Konzept</li>
  <li><strong>Auswahl</strong> geeigneter Hard-/Software sowie eines Cloud-Anbieters</li>
  <li><strong>Implementierung</strong> der Backup-Strategie und Integration in die bestehende
    Umgebung</li>
  <li><strong>Test</strong> der Wiederherstellbarkeit (Restore-Test)</li>
  <li><strong>Dokumentation</strong> und Übergabe an die Praxis</li>
</ol>
<h2>Eingesetzte Technologien</h2>
<p><em>(z. B. Veeam, Synology NAS, Microsoft 365 / Azure, Wasabi, AWS S3, VPN usw. – entsprechend
  dem tatsächlichen Aufbau ausfüllen)</em></p>
<h2>Datenschutzhinweis</h2>
<p>
  Sämtliche Inhalte dieses Repositorys (Screenshots, Konfigurationen, Dokumentation) wurden
  anonymisiert oder mit Beispieldaten erstellt. Es werden keine echten Patienten- oder
  Praxisdaten veröffentlicht.
</p>
<hr>
<p><em>Dieses Projekt wurde im Rahmen der Abschlussprüfung zum Fachinformatiker für
  Systemintegration (IHK) erstellt.</em></p>
