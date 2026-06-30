<h1>IT Infrastructure with Cloud-Based 3-2-1 Backup for a Dental Practice</h1>

<h2>Project Description</h2>
<p>
  As part of my final exam to become an IT Specialist for System Integration
  (<em>Fachinformatiker für Systemintegration</em>), I am planning, designing, and implementing
  an IT infrastructure for a dental practice with a particular focus on reliable and audit-proof
  data backup. Since the practice processes sensitive patient data, both day-to-day operations
  and data backup must meet the highest standards of availability, data protection, and resilience.
</p>
<p>The core of this project is the implementation of a <strong>3-2-1 Cloud backup strategy</strong>:</p>
<ul>
  <li><strong>3</strong> copies of the data (production data + 2 backups)</li>
  <li><strong>2</strong> different storage media/locations (e.g., local NAS and cloud storage)</li>
  <li><strong>1</strong> copy stored off-site/in the cloud, ensuring recoverability even in the event of local incidents (fire, theft, hardware failure)</li>
</ul>

<h2>Project Goals</h2>
<ul>
  <li>Building/optimizing the practice's existing network and server infrastructure</li>
  <li>Implementing an automated, multi-tier backup solution based on the 3-2-1 principle</li>
  <li>Selecting and integrating a suitable cloud backup provider, taking into account GDPR requirements as well as practice-specific regulations (e.g., retention periods, healthcare data requirements)</li>
  <li>Ensuring data encryption both in transit and at rest</li>
  <li>Documenting a recovery concept (disaster recovery plan) including restore testing</li>
  <li>Conducting a cost-effectiveness analysis of the chosen solution compared to alternatives</li>
</ul>

<h2>Current Situation</h2>
<p>
  The practice's IT infrastructure is already fully virtualized, and a network diagram of the
  existing environment has already been created. Building on this, the 3-2-1 backup strategy
  is implemented as follows:
</p>
<ul>
  <li><strong>2</strong> – a second copy of the data is stored on a separate hard drive</li>
  <li><strong>1</strong> – an additional, off-site copy is stored on a Nextcloud server</li>
</ul>

<h2>Approach</h2>
<ol>
  <li><strong>Analysis</strong> of the existing infrastructure and requirements</li>
  <li><strong>Planning</strong> the target architecture, including network, server, and backup concepts</li>
  <li><strong>Selection</strong> of suitable hardware/software and a cloud provider</li>
  <li><strong>Implementation</strong> of the backup strategy and integration into the existing environment</li>
  <li><strong>Testing</strong> recoverability (restore test)</li>
  <li><strong>Documentation</strong> and handover to the practice</li>
</ol>

<h2>Technologies Used</h2>
<p><em>(e.g., Veeam, Synology NAS, Microsoft 365 / Azure, Wasabi, AWS S3, VPN, etc. – fill in based on actual setup)</em></p>

<h2>Data Protection Notice</h2>
<p>
  All content in this repository (screenshots, configurations, documentation) has been anonymized
  or created using sample data. No real patient or practice data is published.
</p>

<hr>

<p><em>This project was created as part of the final examination for IT Specialist for System Integration (IHK, Germany).</em></p>
