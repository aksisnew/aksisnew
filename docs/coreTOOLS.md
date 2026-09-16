<h1 align="center">Core Tools Installation Guide</h1>

<p align="center">
  Development setup guide for Node.js, native build tools, package managers, environment variables, and essential web libraries in Termux.
</p>

<hr/>

<table width="100%" cellspacing="0" cellpadding="14">
<tr>
<td bgcolor="#451a03">

<h3>⚠️ CAUTION & DISCLAIMER</h3>
<p>
Please verify all official download sources and repositories independently before running installation commands. Official maintainers, package repositories, and software distributions may change over time.
</p>
<p>
<i>Disclaimer:</i> I do not maintain Node.js, Termux, or any of the open-source tools listed below. I am simply a user sharing my personal development workflow.
</p>

</td>
</tr>
</table>

<br/>

<table width="100%" cellspacing="0" cellpadding="14">
<tr>
<td bgcolor="#0f172a">

<h3>📌 Node.js Selection: LTS vs. Non-LTS</h3>
<p>
Termux provides two official versions of Node.js:
</p>
<ul>
  <li><b>nodejs-lts (Recommended):</b> Long-Term Support version. Highly stable, reliable, and best suited for development environments.</li>
  <li><b>nodejs (Non-LTS / Current):</b> Contains the latest features and experimental updates, but may occasionally introduce breaking changes or bugs.</li>
</ul>
<p>
<b>Important:</b> Only one Node.js package can be active on your system at a time. It is strongly recommended to install <b><code>nodejs-lts</code></b>.
</p>

</td>
</tr>
</table>

<br/>

<table width="100%" cellspacing="0" cellpadding="14">
<tr>
<td bgcolor="#111827">

<h3>1️⃣ Prerequisites: Build Tools & Native Compilation Dependencies</h3>
<p>
Some Node.js packages compile native C/C++ addons during installation via <code>node-gyp</code>. Installing the official build tools prevents compilation errors.
</p>

<p><b>Option A: Full Toolchain Installation (Recommended)</b></p>
<pre><code>pkg update &amp;&amp; pkg upgrade -y</code></pre>
<pre><code>pkg install python build-essential binutils clang make -y</code></pre>

<p><b>Option B: Minimal Setup (If low on storage space)</b></p>
<pre><code>pkg install python make clang -y</code></pre>

</td>
</tr>
</table>

<br/>

<table width="100%" cellspacing="0" cellpadding="14">
<tr>
<td bgcolor="#1f2937">

<h3>2️⃣ Node.js (LTS) & Package Managers Installation</h3>

<p><b>Option A: Install Node.js LTS (Recommended)</b></p>
<pre><code>pkg install nodejs-lts -y</code></pre>

<p><b>Option B: Install Node.js Current / Non-LTS (Experimental)</b></p>
<pre><code>pkg install nodejs -y</code></pre>

<p><b>Install Yarn Package Manager</b></p>
<pre><code>pkg install yarn -y</code></pre>

<p><b>Install pnpm Package Manager</b></p>
<pre><code>npm install -g pnpm</code></pre>

</td>
</tr>
</table>

<br/>

<table width="100%" cellspacing="0" cellpadding="14">
<tr>
<td bgcolor="#3b0764">

<h3>⚙️ Important Environment Variables</h3>
<p>
Set these key environment variables in your terminal profile (<code>~/.bashrc</code> or <code>~/.zshrc</code>) to ensure smooth build processes and avoid node-gyp build failures on Android ARM architectures.
</p>

<p><b>Set Node Environment Mode</b></p>
<pre><code>export NODE_ENV=development</code></pre>

<p><b>Specify Python Path for Native Compilation (node-gyp)</b></p>
<pre><code>export PYTHON=$(which python)</code></pre>

<p><b>Configure Custom NPM Global Directory (Prevents Root Permission Issues)</b></p>
<pre><code>export NPM_CONFIG_PREFIX="$HOME/.npm-global"</code></pre>

<pre><code>export PATH="$HOME/.npm-global/bin:$PATH"</code></pre>

</td>
</tr>
</table>

<br/>

<table width="100%" cellspacing="0" cellpadding="14">
<tr>
<td bgcolor="#451a03">

<h3>⚠️ CAUTION & KNOWN ISSUES WITH ENV VARIABLES</h3>
<p>
<b>Known Issues & Warnings:</b>
</p>
<ul>
  <li><b>`NODE_ENV=production`:</b> Setting this globally will cause <code>npm install</code> to skip <code>devDependencies</code> (like Vite or Tailwind CLI). Keep it set to <code>development</code> for local workflows.</li>
  <li><b>C++ Compilation Errors:</b> If <code>node-gyp</code> fails during native package installation, ensure the <code>PYTHON</code> environment variable points to Python 3.</li>
  <li><b>PATH Conflicts:</b> If globally installed npm packages are not recognized, ensure <code>$HOME/.npm-global/bin</code> is added to your <code>PATH</code> before running commands.</li>
</ul>

</td>
</tr>
</table>

<br/>

<table width="100%" cellspacing="0" cellpadding="14">
<tr>
<td bgcolor="#0f172a">

<h3>3️⃣ System & Version Verification Commands</h3>

<p><b>Verify Active Node.js Version</b></p>
<pre><code>node -v</code></pre>

<p><b>Verify Binary Location on PATH</b></p>
<pre><code>which node</code></pre>

<p><b>Check Package Manager Versions</b></p>
<pre><code>npm -v</code></pre>
<pre><code>yarn -v</code></pre>
<pre><code>pnpm -v</code></pre>

<p><b>Check Runtime Execution & Environment Info</b></p>
<pre><code>node -e "console.log(process.versions)"</code></pre>

</td>
</tr>
</table>

<br/>

<table width="100%" cellspacing="0" cellpadding="14">
<tr>
<td bgcolor="#111827">

<h3>4️⃣ Required Stack & Libraries Setup</h3>

<p><b>Global Tools & Bundlers Installation</b></p>
<pre><code>npm install -g vite</code></pre>
<pre><code>npm install -g esbuild</code></pre>
<pre><code>npm install -g tailwindcss</code></pre>

<p><b>Project Initialization</b></p>
<pre><code>mkdir my-app &amp;&amp; cd my-app</code></pre>
<pre><code>npm init -y</code></pre>

<p><b>Backend Framework Setup</b></p>
<pre><code>npm install express</code></pre>

<p><b>Frontend UI Libraries Setup (Choose Options Based on Needs)</b></p>

<p><b>Option A: React</b></p>
<pre><code>npm install react react-dom</code></pre>

<p><b>Option B: Vue</b></p>
<pre><code>npm install vue</code></pre>

<p><b>Option C: Svelte</b></p>
<pre><code>npm install svelte</code></pre>

</td>
</tr>
</table>
