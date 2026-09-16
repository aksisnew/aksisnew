<h1 align="center">Version Control & Git Configuration Guide</h1>

<p align="center">
  Comprehensive guide for installing, configuring, updating, and removing Git in Termux.
</p>

<hr/>

<table width="100%" cellspacing="0" cellpadding="14">
<tr>
<td bgcolor="#451a03">

<h3>⚠️ CRITICAL DISCLAIMER: USE AT YOUR OWN RISK</h3>
<p>
All commands, setups, and operations provided in this guide are shared strictly for educational and workflow reference. <b>Proceed entirely at your own risk.</b>
</p>
<p>
Executing package modifications, repository resets, or file removals can lead to unexpected errors, broken environments, or lost work. I take no responsibility for data loss or system issues caused by following these steps.
</p>

</td>
</tr>
</table>

<br/>

<table width="100%" cellspacing="0" cellpadding="14">
<tr>
<td bgcolor="#7f1d1d">

<h3>🚨 DATA LOSS & REPOSITORY CORRUPTION WARNING</h3>
<p>
<b>Important Precautions for Version Control:</b>
</p>
<ul>
  <li><b>Always back up unpushed work:</b> Ensure your local changes are committed or stashed before running destructive Git commands like <code>git reset --hard</code> or <code>git clean</code>.</li>
  <li><b>Never commit confidential data:</b> Keep API keys, passwords, and private environment files (<code>.env</code>) out of version control by adding them to your <code>.gitignore</code> file.</li>
  <li><b>Double-check targeted paths:</b> Running file cleanup commands can permanently delete untracked files without sending them to a trash bin.</li>
</ul>

</td>
</tr>
</table>

<br/>

<table width="100%" cellspacing="0" cellpadding="14">
<tr>
<td bgcolor="#0f172a">

<h3>📥 1️⃣ Installing Git</h3>
<p>
Update the package repository index and install Git inside Termux:
</p>

<p><b>Update Package Repositories</b></p>
<pre><code>pkg update &amp;&amp; pkg upgrade -y</code></pre>

<p><b>Install Git</b></p>
<pre><code>pkg install git -y</code></pre>

<p><b>Verify Installation</b></p>
<pre><code>git --version</code></pre>

</td>
</tr>
</table>

<br/>

<table width="100%" cellspacing="0" cellpadding="14">
<tr>
<td bgcolor="#1f2937">

<h3>⚙️ 2️⃣ Initial Git Configuration</h3>
<p>
Set up your global username, email address, and default branch:
</p>

<p><b>Set Global User Details</b></p>
<pre><code>git config --global user.name "Your Name"</code></pre>
<pre><code>git config --global user.email "your.email@example.com"</code></pre>

<p><b>Set Default Branch Name</b></p>
<pre><code>git config --global init.defaultBranch main</code></pre>

<p><b>Check Current Configuration</b></p>
<pre><code>git config --list</code></pre>

</td>
</tr>
</table>

<br/>

<table width="100%" cellspacing="0" cellpadding="14">
<tr>
<td bgcolor="#111827">

<h3>🔄 3️⃣ Updating & Removing Git</h3>
<p>
Commands for updating or completely removing Git from your Termux system:
</p>

<p><b>Update Git Package</b></p>
<pre><code>pkg update &amp;&amp; pkg upgrade git -y</code></pre>

<p><b>Completely Remove Git</b></p>
<pre><code>pkg remove git -y</code></pre>

<p><b>Clean Package Cache After Removal</b></p>
<pre><code>pkg autoclean</code></pre>

</td>
</tr>
</table>

<br/>

<table width="100%" cellspacing="0" cellpadding="14">
<tr>
<td bgcolor="#3b0764">

<h3>⚡ 4️⃣ Essential Git Commands</h3>
<p>
Standard commands for everyday version control operations:
</p>

<p><b>Initialize a New Repository</b></p>
<pre><code>git init</code></pre>

<p><b>Check Repository Status</b></p>
<pre><code>git status</code></pre>

<p><b>Stage Changes</b></p>
<pre><code>git add .</code></pre>

<p><b>Commit Changes</b></p>
<pre><code>git commit -m "feat: initial commit"</code></pre>

<p><b>View Commit History</b></p>
<pre><code>git log --oneline</code></pre>

<p><b>Undo Uncommitted Local File Changes</b></p>
<pre><code>git checkout -- filename.ext</code></pre>

<p><b>Remove Untracked Files (Use with caution)</b></p>
<pre><code>git clean -fd</code></pre>

</td>
</tr>
</table>
