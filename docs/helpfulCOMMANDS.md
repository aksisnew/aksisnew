<h1 align="center">Helpful Commands & System Maintenance Guide</h1>

<p align="center">
  A quick-reference guide for switching Node.js versions, performing major updates, managing backups, and keeping your Termux development environment clean and functional.
</p>

<hr/>

<table width="100%" cellspacing="0" cellpadding="14">
<tr>
<td bgcolor="#451a03">

<h3>⚠️ CRITICAL DISCLAIMER: USE AT YOUR OWN RISK</h3>
<p>
All commands, setups, and scripts provided in this repository are shared strictly for educational and personal workflow reference. <b>Proceed entirely at your own risk.</b>
</p>
<p>
Modifying system packages, running package updates, or executing storage commands can lead to unintended bugs, corrupted dependencies, broken environments, or unexpected system behavior. I take no responsibility for lost data, broken setups, or system instability caused by following these steps.
</p>

</td>
</tr>
</table>

<br/>

<table width="100%" cellspacing="0" cellpadding="14">
<tr>
<td bgcolor="#7f1d1d">

<h3>🚨 DATA LOSS & ENVIRONMENT CORRUPTION WARNING</h3>
<p>
Major package upgrades (such as updating Node.js LTS versions) or clearing package caches can break native binary bindings inside your <code>node_modules</code> directory.
</p>
<p>
<b>Important Precautions:</b>
</p>
<ul>
  <li>Always push your code commits to remote Git repositories (e.g., GitHub, GitLab) before performing upgrades.</li>
  <li>Back up important databases, local environment files (<code>.env</code>), and key configuration scripts independently.</li>
  <li>Never run destructive file removal commands (e.g., <code>rm -rf</code>) without carefully double-checking the working directory path.</li>
</ul>

</td>
</tr>
</table>

<br/>

<table width="100%" cellspacing="0" cellpadding="14">
<tr>
<td bgcolor="#0f172a">

<h3>🔄 Switching Node.js Versions (Fixing Accidental Non-LTS Installation)</h3>
<p>
If you accidentally installed the non-LTS (<code>nodejs</code>) package instead of LTS (<code>nodejs-lts</code>), use these commands to swap them safely:
</p>

<p><b>Step 1: Completely Uninstall Current Node.js Package</b></p>
<pre><code>pkg remove nodejs -y</code></pre>

<p><b>Step 2: Clean Package Cache</b></p>
<pre><code>pkg autoclean</code></pre>

<p><b>Step 3: Install Node.js LTS Package</b></p>
<pre><code>pkg install nodejs-lts -y</code></pre>

<p><b>Step 4: Verify Correct LTS Installation</b></p>
<pre><code>node -v</code></pre>

</td>
</tr>
</table>

<br/>

<table width="100%" cellspacing="0" cellpadding="14">
<tr>
<td bgcolor="#1f2937">

<h3>🚀 Upgrading to a New Major LTS Release</h3>
<p>
When a new major Node.js LTS release arrives in the Termux repositories, use one of the two upgrade strategies below:
</p>

<h4>Option 1: Standard Repository Upgrade (Recommended)</h4>

<p><b>Update Termux Repositories Index</b></p>
<pre><code>pkg update</code></pre>

<p><b>Upgrade All Packages (Includes nodejs-lts)</b></p>
<pre><code>pkg upgrade -y</code></pre>

<p><b>Rebuild Native Project Dependencies (Run inside your project directory)</b></p>
<pre><code>npm rebuild</code></pre>

<h4>Option 2: Clean Reinstall Strategy (Use if native modules fail to load after upgrade)</h4>

<p><b>Remove Existing Node.js LTS Package</b></p>
<pre><code>pkg remove nodejs-lts -y</code></pre>

<p><b>Re-install Latest LTS Release</b></p>
<pre><code>pkg install nodejs-lts -y</code></pre>

<p><b>Re-install Global NPM Packages</b></p>
<pre><code>npm install -g vite esbuild tailwindcss pnpm</code></pre>

<p><b>Clean Project node_modules and Reinstall (Run inside project root)</b></p>
<pre><code>rm -rf node_modules package-lock.json</code></pre>
<pre><code>npm install</code></pre>

</td>
</tr>
</table>

<br/>

<table width="100%" cellspacing="0" cellpadding="14">
<tr>
<td bgcolor="#3b0764">

<h3>📦 Termux Environment Backup & Restore</h3>

<p><b>Grant Storage Permissions</b></p>
<pre><code>termux-setup-storage</code></pre>

<p><b>⚠️ Caution when running <code>termux-setup-storage</code>:</b></p>
<ul>
  <li>Executing this command grants Termux full read/write access to your device's shared internal storage (<code>/sdcard</code>).</li>
  <li>Be extremely cautious when running untrusted npm packages or scripts with lifecycle hooks (e.g., <code>postinstall</code>), as buggy or malicious scripts could alter or delete files on your phone's storage.</li>
  <li>It is strongly advised to enable shared storage permissions only on a secondary, dedicated development device.</li>
</ul>

<p><b>Create Full Environment Backup (Saves to Shared Internal Storage)</b></p>
<pre><code>tar -zcvf /sdcard/termux_dev_backup.tar.gz -C /data/data/com.termux/files home usr</code></pre>

<p><b>Restore Full Environment Backup</b></p>
<pre><code>tar -zxvf /sdcard/termux_dev_backup.tar.gz -C /data/data/com.termux/files</code></pre>

</td>
</tr>
</table>

<br/>

<table width="100%" cellspacing="0" cellpadding="14">
<tr>
<td bgcolor="#111827">

<h3>🧹 System Maintenance & Disk Space Cleanup Commands</h3>
<p>
Run these utility commands periodically to free up device storage and keep Termux fast:
</p>

<p><b>Clean Termux Package Cache (.deb files)</b></p>
<pre><code>pkg clean</code></pre>

<p><b>Clear NPM Global Cache</b></p>
<pre><code>npm cache clean --force</code></pre>

<p><b>List All Installed Termux Packages</b></p>
<pre><code>pkg list-installed</code></pre>

<p><b>Remove Unused System Dependencies</b></p>
<pre><code>apt autoremove -y</code></pre>

<p><b>Check Available Disk Space in Termux</b></p>
<pre><code>df -h $HOME</code></pre>

</td>
</tr>
</table>
