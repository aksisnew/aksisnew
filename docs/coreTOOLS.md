<h1 align="center">Core Tools Installation Guide</h1>

<p align="center">
  Development setup guide for Node.js, native build tools, package managers, and essential web libraries.
</p>

<hr/>

<table width="100%" cellspacing="0" cellpadding="14">
<tr>
<td bgcolor="#451a03">

<h3>⚠️ CAUTION & DISCLAIMER</h3>
<p>
Please verify all official download sources, packages, and repositories independently before executing installation commands. Official maintainers, package names, and software distributions may change over time.
</p>
<p>
<i>Disclaimer:</i> I do not maintain Node.js, Termux, or any of the third-party libraries listed below. I am simply a user sharing my personal development workflow.
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
There are two primary versions of Node.js available in package repositories:
</p>
<ul>
  <li><b>nodejs-lts (Recommended):</b> Long-Term Support release. Highly stable, reliable, and recommended for most development setups.</li>
  <li><b>nodejs (Non-LTS / Current):</b> Features latest updates and experimental features, but can occasionally introduce breaking changes or instability.</li>
</ul>
<p>
<b>Note:</b> You can only have one active Node.js installation on your system at a time. It is strongly recommended to install the LTS version.
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
Certain Node.js modules compile native C/C++ code during installation using <code>node-gyp</code>. Installing these official tools ensures native package builds work properly:
</p>

<pre><code># Update repository indices
pkg update &amp;&amp; pkg upgrade -y

# Install official Python, C/C++ build toolchain, and utilities
pkg install python build-essential binutils clang make -y</code></pre>

</td>
</tr>
</table>

<br/>

<table width="100%" cellspacing="0" cellpadding="14">
<tr>
<td bgcolor="#1f2937">

<h3>2️⃣ Node.js (LTS) & Package Managers Installation</h3>
<p>
Install the Node.js LTS release along with alternative package managers:
</p>

<pre><code># Install Node.js LTS version
pkg install nodejs-lts -y

# Install Yarn package manager
pkg install yarn -y

# Install pnpm globally using npm
npm install -g pnpm</code></pre>

</td>
</tr>
</table>

<br/>

<table width="100%" cellspacing="0" cellpadding="14">
<tr>
<td bgcolor="#0f172a">

<h3>3️⃣ Verification Commands</h3>
<p>
Run the following commands to verify installed versions, binary locations, and runtime details:
</p>

<pre><code># Verify active binary location
which node
which npm

# Check versions
node -v
npm -v
yarn -v
pnpm -v

# Print detailed Node runtime build details
node -e "console.log(process.versions)"</code></pre>

</td>
</tr>
</table>

<br/>

<table width="100%" cellspacing="0" cellpadding="14">
<tr>
<td bgcolor="#111827">

<h3>4️⃣ Required Stack & Libraries Setup</h3>
<p>
Commands to set up Vite, esbuild, Tailwind CSS, backend, and frontend frameworks:
</p>

<h4>Global Tools & Build Engines</h4>
<pre><code># Install Vite, Tailwind CSS CLI, and esbuild globally
npm install -g vite esbuild tailwindcss</code></pre>

<h4>Project Frameworks & Backend Setup</h4>
<pre><code># Create project directory and initialize
mkdir my-app &amp;&amp; cd my-app
npm init -y

# Backend framework
npm install express

# Frontend UI Frameworks (install as needed for your project)
npm install react react-dom
npm install vue
npm install svelte</code></pre>

</td>
</tr>
</table>
