<h1>Portainer Configuration</h1>

<h2>New Portainer Installation</h2>

<p>After starting Portainer for the first time, you will be prompted to set up an admin account.</p>

<h3>Step 1 — Create Admin Account</h3>

<p>Open Portainer in your browser and fill in the setup form:</p>

<ul>
  <li><strong>Username</strong> — choose a username for the admin account</li>
  <li><strong>Password</strong> — use a strong, secure password</li>
  <li><strong>Initial Setup Token</strong> — required for the first login; find it in the server logs (see below)</li>
</ul>

<img src="https://github.com/Joshua-bat/IHK-FISI-2026/blob/d1e6f823fc7a0672d40ed8ea47e2dcb750dfcec3/doc/images/New_Portainer_Installation.png" width="700" />

<hr />

<h3>Step 2 — Retrieve the Setup Token from Server Logs</h3>

<p>The initial setup token is generated automatically when Portainer starts for the first time.<br />
To find it, check the container logs:</p>

<pre><code>docker logs portainer</code></pre>

<p>Look for a line containing the token in the output.</p>

<img src="https://github.com/Joshua-bat/IHK-FISI-2026/blob/d1e6f823fc7a0672d40ed8ea47e2dcb750dfcec3/doc/images/Portainer_logs.png" width="700" />

<hr />

<blockquote>
<strong>⚠️ Note:</strong> The setup token is only valid for the <strong>first startup</strong>.
If you miss it, restart the Portainer container to regenerate it.
</blockquote>

<h2>Quick Setup</h2>

<p>the Quick Setup wizard is easy to understand,just press Get Startet ater that you see the Dashboard from youre local Docker service</p>

<img src="https://github.com/Joshua-bat/IHK-FISI-2026/blob/d1e6f823fc7a0672d40ed8ea47e2dcb750dfcec3/doc/images/Quick_setup.png" width="700" />

<h1>Dashboard</h1>
