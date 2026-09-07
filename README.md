<title>Projektarbeit — IT-Infrastruktur mit 3-2-1-Cloudbackup</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=IBM+Plex+Mono:wght@400;500;600;700&family=IBM+Plex+Sans:wght@400;500;600;700&display=swap" rel="stylesheet">
<style>
  :root{
    --bg:#F5F7F6;
    --surface:#FFFFFF;
    --text:#16241F;
    --text-muted:#4B5A54;
    --accent:#0B6E4F;
    --accent-soft:#E3F1EC;
    --warm:#C46A2E;
    --warm-soft:#F7E9DE;
    --border:#D8DED9;
    --mono: 'IBM Plex Mono', ui-monospace, monospace;
    --sans: 'IBM Plex Sans', system-ui, sans-serif;
  }

  *{ box-sizing:border-box; }

  body{
    margin:0;
    background:var(--bg);
    color:var(--text);
    font-family:var(--sans);
    line-height:1.6;
    -webkit-font-smoothing:antialiased;
  }

  a{ color:var(--accent); }

  .wrap{
    max-width:760px;
    margin:0 auto;
    padding:0 24px 96px;
  }

  header.hero{
    border-bottom:1px solid var(--border);
    padding:64px 0 40px;
    margin-bottom:48px;
  }

  .kicker{
    font-family:var(--mono);
    font-size:13px;
    color:var(--accent);
    margin:0 0 14px;
  }

  h1{
    font-family:var(--mono);
    font-size:clamp(28px,5vw,42px);
    line-height:1.15;
    margin:0 0 18px;
    font-weight:700;
    letter-spacing:-0.01em;
  }

  .lede{
    font-size:17px;
    color:var(--text-muted);
    max-width:60ch;
    margin:0 0 24px;
  }

  .badges{
    display:flex;
    flex-wrap:wrap;
    gap:8px;
  }
  .badge{
    font-family:var(--mono);
    font-size:12px;
    padding:5px 10px;
    border:1px solid var(--border);
    border-radius:4px;
    color:var(--text-muted);
    background:var(--surface);
  }

  nav.toc{
    background:var(--surface);
    border:1px solid var(--border);
    border-radius:8px;
    padding:20px 24px;
    margin-bottom:56px;
  }
  nav.toc p{
    font-family:var(--mono);
    font-size:12px;
    text-transform:uppercase;
    letter-spacing:.04em;
    color:var(--text-muted);
    margin:0 0 10px;
  }
  nav.toc ul{
    margin:0;
    padding:0;
    list-style:none;
    columns:2;
    column-gap:24px;
  }
  nav.toc li{ margin-bottom:6px; font-size:14px; break-inside:avoid; }
  nav.toc li .n{ font-family:var(--mono); color:var(--accent); font-size:13px; margin-right:8px; }
  nav.toc a{ text-decoration:none; color:var(--text); }
  nav.toc a:hover{ color:var(--accent); }

  section{
    margin-bottom:56px;
    scroll-margin-top:24px;
  }

  h2{
    font-family:var(--mono);
    font-size:22px;
    margin:0 0 8px;
  }
  h2 .num{
    color:var(--accent);
    font-size:15px;
    margin-right:12px;
  }

  h3{
    font-family:var(--mono);
    font-size:16px;
    margin:28px 0 10px;
    color:var(--text);
  }

  p{ margin:0 0 14px; }

  .section-intro{ color:var(--text-muted); }

  ul, ol.plain{ padding-left:22px; margin:0 0 14px; }
  li{ margin-bottom:6px; }

  code{
    font-family:var(--mono);
    background:var(--accent-soft);
    color:var(--accent);
    padding:1px 6px;
    border-radius:4px;
    font-size:.9em;
  }

  .callout{
    border-left:3px solid var(--warm);
    background:var(--warm-soft);
    padding:14px 18px;
    border-radius:0 6px 6px 0;
    font-size:14.5px;
    color:#5c3a1a;
  }
  .callout strong{ color:#3f2811; }

  table{
    width:100%;
    border-collapse:collapse;
    font-size:14.5px;
    margin-bottom:8px;
  }
  th, td{
    text-align:left;
    padding:10px 12px;
    border-bottom:1px solid var(--border);
    vertical-align:top;
  }
  th{
    font-family:var(--mono);
    font-weight:500;
    font-size:12.5px;
    text-transform:uppercase;
    letter-spacing:.03em;
    color:var(--text-muted);
  }
  td code{ white-space:nowrap; }

  .tree{
    font-family:var(--mono);
    font-size:13.5px;
    background:var(--surface);
    border:1px solid var(--border);
    border-radius:8px;
    padding:20px 24px;
    overflow-x:auto;
    line-height:1.9;
    white-space:pre;
    margin:0;
  }
  .tree .comment{ color:var(--text-muted); }
  .tree .path{ color:var(--accent); font-weight:600; }

  .diagram{
    background:var(--surface);
    border:1px solid var(--border);
    border-radius:8px;
    padding:24px;
  }
  .diagram svg{ width:100%; height:auto; display:block; }
  .diagram-caption{
    font-family:var(--mono);
    font-size:12px;
    color:var(--text-muted);
    margin-top:12px;
    text-align:center;
  }

  .status-list{ list-style:none; padding:0; margin:0; }
  .status-list li{
    display:flex;
    align-items:flex-start;
    padding:10px 0;
    border-bottom:1px solid var(--border);
    font-size:14.5px;
  }
  .status-list li:last-child{ border-bottom:none; }
  .dot{
    flex:0 0 auto;
    width:9px; height:9px;
    border-radius:50%;
    margin-top:6px;
    margin-right:10px;
  }
  .dot.done{ background:var(--accent); }
  .dot.open{ background:var(--warm); }

  footer{
    border-top:1px solid var(--border);
    padding-top:24px;
    font-size:13px;
    color:var(--text-muted);
    font-family:var(--mono);
  }
</style>
</head>
<body>
<div class="wrap">

  <header class="hero">
    <p class="kicker">IHK Abschlussprüfung — Fachinformatiker/-in Systemintegration</p>
    <h1>IT-Infrastruktur mit cloudbasiertem 3-2-1-Backup für eine Zahnarztpraxis</h1>
    <p class="lede">Aufbau einer neuen IT-Infrastruktur (Windows Server, Active Directory, Dateifreigaben) inklusive einer redundanten, verschlüsselten 3-2-1-Backup-Strategie für besonders schutzwürdige Patientendaten.</p>
    <div class="badges">
      <span class="badge">Ausbildungsjahr: Sommerprüfung 2026</span>
      <span class="badge">Status: in Bearbeitung</span>
      <span class="badge">Umgebung: virtuelle Testumgebung</span>
    </div>
  </header>

  <nav class="toc" aria-label="Inhaltsverzeichnis">
    <p>Inhalt</p>
    <ul>
      <li><span class="n">01</span><a href="#ausgangslage">Ausgangslage &amp; Auftrag</a></li>
      <li><span class="n">02</span><a href="#ziele">Ziele</a></li>
      <li><span class="n">03</span><a href="#architektur">Zielarchitektur</a></li>
      <li><span class="n">04</span><a href="#technologien">Eingesetzte Technologien</a></li>
      <li><span class="n">05</span><a href="#struktur">Repository-Struktur</a></li>
      <li><span class="n">06</span><a href="#vorgehen">Vorgehensweise</a></li>
      <li><span class="n">07</span><a href="#datenschutz">Datenschutz</a></li>
      <li><span class="n">08</span><a href="#status">Projektstatus</a></li>
    </ul>
  </nav>

  <section id="ausgangslage">
    <h2><span class="num">01</span> Ausgangslage &amp; Auftrag</h2>
    <p>Der Kunde eröffnet eine neue Zahnarztpraxis mit mehreren Behandlungszimmern. Es existiert aktuell <strong>keine eigene IT-Infrastruktur</strong>: kein zentraler Server, keine strukturierte Benutzer- und Rechteverwaltung, keine zentrale Dateiablage und kein Datensicherungskonzept.</p>
    <p>Da die Praxis von Beginn an mit besonders schutzwürdigen Patientendaten arbeitet, besteht der Auftrag darin, eine vollständige IT-Infrastruktur neu aufzubauen und direkt mit einer zuverlässigen, revisionssicheren und DSGVO-konformen Datensicherung nach dem <strong>3-2-1-Prinzip</strong> zu versehen.</p>
  </section>

  <section id="ziele">
    <h2><span class="num">02</span> Ziele</h2>
    <ul>
      <li><strong>3 Kopien</strong> der Daten — Produktivdaten plus zwei Backups</li>
      <li><strong>2 unterschiedliche Speicherorte</strong> — lokales NAS am Praxisstandort und ein externer Server</li>
      <li><strong>1 externe Kopie</strong> — schützt auch bei Brand, Diebstahl oder Totalausfall vor Ort</li>
      <li>Automatisierte Sicherung: <strong>täglich inkrementell</strong>, <strong>wöchentlich voll</strong></li>
      <li>Verschlüsselung <strong>in transit und at rest</strong> gemäß Art. 9 DSGVO (Gesundheitsdaten)</li>
      <li>Nachweis der Wiederherstellbarkeit durch einen dokumentierten <strong>Restore-Test</strong></li>
    </ul>
  </section>

  <section id="architektur">
    <h2><span class="num">03</span> Zielarchitektur</h2>
    <p class="section-intro">Grobskizze der drei Datenkopien und ihrer Speicherorte. Der Windows Server bildet die Produktivumgebung, das NAS die lokale Zweitkopie, der externe Linux-Server die dritte, ausgelagerte Kopie.</p>
    <div class="diagram">
      <svg viewBox="0 0 720 300" xmlns="http://www.w3.org/2000/svg">
        <defs>
          <marker id="arrow" viewBox="0 0 10 10" refX="9" refY="5" markerWidth="7" markerHeight="7" orient="auto-start-reverse">
            <path d="M0,0 L10,5 L0,10 z" fill="#0B6E4F"/>
          </marker>
        </defs>

        <!-- Site boundary: Praxis -->
        <rect x="20" y="20" width="330" height="260" rx="10" fill="none" stroke="#D8DED9" stroke-width="1.5" stroke-dasharray="4 4"/>
        <text x="36" y="42" font-family="IBM Plex Mono, monospace" font-size="12" fill="#4B5A54">PRAXISSTANDORT</text>

        <!-- Windows Server box -->
        <rect x="48" y="70" width="270" height="72" rx="8" fill="#E3F1EC" stroke="#0B6E4F" stroke-width="1.5"/>
        <text x="66" y="98" font-family="IBM Plex Mono, monospace" font-size="13" font-weight="600" fill="#16241F">Windows Server</text>
        <text x="66" y="118" font-family="IBM Plex Mono, monospace" font-size="11" fill="#4B5A54">AD · Dateifreigaben</text>
        <text x="66" y="133" font-family="IBM Plex Mono, monospace" font-size="10" fill="#0B6E4F">1. Kopie — Produktivdaten</text>

        <!-- NAS box -->
        <rect x="48" y="188" width="270" height="72" rx="8" fill="#E3F1EC" stroke="#0B6E4F" stroke-width="1.5"/>
        <text x="66" y="216" font-family="IBM Plex Mono, monospace" font-size="13" font-weight="600" fill="#16241F">NAS</text>
        <text x="66" y="236" font-family="IBM Plex Mono, monospace" font-size="11" fill="#4B5A54">tägl. inkrementelles Backup</text>
        <text x="66" y="251" font-family="IBM Plex Mono, monospace" font-size="10" fill="#0B6E4F">2. Kopie — lokal, getrennt</text>

        <!-- arrow server -> nas -->
        <line x1="183" y1="142" x2="183" y2="186" stroke="#0B6E4F" stroke-width="1.5" marker-end="url(#arrow)"/>

        <!-- External site -->
        <rect x="400" y="20" width="300" height="260" rx="10" fill="none" stroke="#D8DED9" stroke-width="1.5" stroke-dasharray="4 4"/>
        <text x="416" y="42" font-family="IBM Plex Mono, monospace" font-size="12" fill="#4B5A54">EXTERNER STANDORT</text>

        <!-- Firewall/VPN -->
        <rect x="428" y="70" width="244" height="46" rx="8" fill="#F7E9DE" stroke="#C46A2E" stroke-width="1.5"/>
        <text x="446" y="98" font-family="IBM Plex Mono, monospace" font-size="12" font-weight="600" fill="#5c3a1a">Firewall · verschlüsselte Verbindung</text>

        <!-- Linux server -->
        <rect x="428" y="140" width="244" height="120" rx="8" fill="#E3F1EC" stroke="#0B6E4F" stroke-width="1.5"/>
        <text x="446" y="166" font-family="IBM Plex Mono, monospace" font-size="13" font-weight="600" fill="#16241F">Linux-Server</text>
        <text x="446" y="186" font-family="IBM Plex Mono, monospace" font-size="11" fill="#4B5A54">Docker · Portainer</text>
        <text x="446" y="203" font-family="IBM Plex Mono, monospace" font-size="11" fill="#4B5A54">Nginx Proxy Manager</text>
        <text x="446" y="220" font-family="IBM Plex Mono, monospace" font-size="11" fill="#4B5A54">Nextcloud</text>
        <text x="446" y="242" font-family="IBM Plex Mono, monospace" font-size="10" fill="#0B6E4F">3. Kopie — wöchentl. Vollbackup</text>

        <!-- arrow nas -> firewall -->
        <line x1="318" y1="224" x2="426" y2="150" stroke="#0B6E4F" stroke-width="1.5" marker-end="url(#arrow)"/>
        <!-- arrow firewall -> linux -->
        <line x1="550" y1="116" x2="550" y2="138" stroke="#C46A2E" stroke-width="1.5" marker-end="url(#arrow)"/>
      </svg>
      <p class="diagram-caption">Abb. 1 — 3-2-1-Backup: Produktivdaten (Windows Server) → NAS (2. Kopie) → verschlüsselt über Firewall zum externen Linux-/Nextcloud-Server (3. Kopie)</p>
    </div>
  </section>

  <section id="technologien">
    <h2><span class="num">04</span> Eingesetzte Technologien</h2>
    <table>
      <thead>
        <tr><th>Komponente</th><th>Rolle im Projekt</th></tr>
      </thead>
      <tbody>
        <tr><td><code>Windows Server</code></td><td>Active Directory, zentrale Benutzer-/Rechteverwaltung, Dateifreigaben (1. Kopie)</td></tr>
        <tr><td><code>NAS</code></td><td>Lokale zweite Kopie, tägliches inkrementelles Backup</td></tr>
        <tr><td><code>Linux (Ubuntu)</code></td><td>Betriebssystem des externen Servers für die dritte Kopie</td></tr>
        <tr><td><code>Docker / Portainer</code></td><td>Containerverwaltung auf dem externen Server</td></tr>
        <tr><td><code>Nextcloud</code></td><td>Ziel-System für die externe, dritte Backup-Kopie</td></tr>
        <tr><td><code>Nginx Proxy Manager</code></td><td>Verschlüsselte, reverse-proxied Anbindung an Nextcloud (TLS)</td></tr>
        <tr><td><code>Firewall</code></td><td>Absicherung der Verbindung zwischen Praxisstandort und externem Standort</td></tr>
      </tbody>
    </table>
  </section>

  <section id="struktur">
    <h2><span class="num">05</span> Repository-Struktur</h2>
    <p class="section-intro">Jeder Ordner enthält die Konfiguration bzw. Dokumentation der jeweiligen Komponente aus der Zielarchitektur oben.</p>
    <pre class="tree"><span class="path">/Docker</span>              <span class="comment"># Compose-Dateien &amp; Container-Konfiguration</span>
<span class="path">/Firewall</span>            <span class="comment"># Regelwerk und Konfiguration der Standortabsicherung</span>
<span class="path">/Linux</span>               <span class="comment"># Setup &amp; Härtung des externen Ubuntu-Servers</span>
<span class="path">/Nextcloud</span>           <span class="comment"># Installation &amp; Konfiguration (3. Kopie)</span>
<span class="path">/Nginx Proxy Manager</span> <span class="comment"># Reverse-Proxy- &amp; TLS-Konfiguration</span>
<span class="path">/Portainer</span>           <span class="comment"># Container-Verwaltungs-UI für den Linux-Server</span>
<span class="path">/Windows Server</span>      <span class="comment"># AD-, GPO- &amp; Dateifreigabe-Konfiguration</span>
<span class="path">/doc</span>                 <span class="comment"># Projektantrag, Dokumentation, Netzplan</span></pre>
  </section>

  <section id="vorgehen">
    <h2><span class="num">06</span> Vorgehensweise</h2>
    <ol class="plain">
      <li><strong>Planung</strong> — Ist-Analyse, Zielarchitektur, Auswahl der Backup-Lösung, Wirtschaftlichkeitsanalyse</li>
      <li><strong>Aufbau Praxisstandort</strong> — Windows Server, Active Directory, Dateifreigaben, NAS-Konfiguration</li>
      <li><strong>Aufbau externer Standort</strong> — Linux-Server, Docker/Portainer, Nextcloud, Nginx Proxy Manager</li>
      <li><strong>Absicherung</strong> — Firewall-Regeln, verschlüsselte Standortverbindung</li>
      <li><strong>Automatisierung</strong> — tägliche inkrementelle und wöchentliche Voll-Backups</li>
      <li><strong>Test</strong> — Restore-Test, Funktions- und Sicherheitstest</li>
    </ol>
  </section>

  <section id="datenschutz">
    <h2><span class="num">07</span> Datenschutz</h2>
    <div class="callout">
      <strong>Hinweis:</strong> Da im späteren Produktivbetrieb echte, besonders schutzwürdige Patientendaten verarbeitet werden, wird dieses Projekt nicht beim Kunden vor Ort, sondern vollständig in einer <strong>virtuellen Testumgebung mit ausschließlich anonymisierten Beispieldaten</strong> umgesetzt und dokumentiert.
    </div>
  </section>

  <section id="status">
    <h2><span class="num">08</span> Projektstatus</h2>
    <ul class="status-list">
      <li><span class="dot done"></span> Ist-Analyse &amp; Zielarchitektur geplant</li>
      <li><span class="dot done"></span> Projektantrag bei der IHK eingereicht</li>
      <li><span class="dot open"></span> Aufbau Windows Server &amp; Active Directory</li>
      <li><span class="dot open"></span> Aufbau externer Nextcloud-Server</li>
      <li><span class="dot open"></span> Restore-Test &amp; Dokumentation</li>
    </ul>
  </section>

  <footer>
    Projektarbeit · Fachinformatiker/-in Systemintegration · IHK München und Oberbayern
  </footer>

</div>
</body>
</html>
