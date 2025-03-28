<h1>Brute-Force SSH Attack (Attack from Kali, Defend on Ubuntu)</h1>
<img src="https://i.ibb.co/6RV9sjrM/What-Is-a-Brute-Force-Attack-in-Cyber-Security-SSL-Dragon.jpg" width="1000" height="500">

<h2>Description</h2>
<b>The Brute-Force SSH Attack project demonstrates the process of attacking an SSH service using a brute-force attack from a Kali Linux machine while defending against the attack on an Ubuntu machine. It shows how attackers can exploit weak passwords and how defenders can protect their systems through various security measures, such as monitoring logs, using Fail2Ban, and enforcing strong authentication policies.</b>

<h2>Utilities Used</h2>
<ul>
  <li><b>Python</b></li>
  <li><b>Hydra</b></li>
  <li><b>SSH</b></li>
  <li><b>Fail2Ban</b></li>
  <li><b>Ubuntu</b></li>
  <li><b>Kali Linux</b></li>
</ul>

<h2>Environments Used</h2>
<ul>
  <li><b>Ubuntu</b></li>
  <li><b>Kali Linux</b></li>
  <li><b>VS Code</b></li>
</ul>

<h2>Program Features</h2>

<h3>1. SSH Setup on Ubuntu (Target Machine)</h3>
<ul>
  <li><b>SSH is commonly targeted by hackers because it allows remote access to a system.</b></li>
  <li><b>By enabling SSH, we create a real-world attack surface to test our security defenses.</b></li>
</ul>

<img src="https://i.ibb.co/GvsH6YXF/ubuntu-2.png" alt="Ubuntu SSH Setup">
<p><b>🔹 <code>sudo apt update</code> – Updates package lists to ensure the latest software is installed.</b></p>
<p><b>🔹 Remember to enter your password (it won’t be visible while typing).</b></p>

<img src="https://i.ibb.co/jPgV7Zct/ubuntu-3.png" alt="Ubuntu SSH Enable">
<p><b>🔹 <code>enable</code> – Ensures SSH starts automatically when the system boots.</b></p>
<p><b>🔹 <code>start</code> – Starts the SSH service so it’s running and accessible.</b></p>

<img src="https://i.ibb.co/WC6y3VF/ubuntu-4.png" alt="Ubuntu IP Display">
<p><b>🔹 Displays the IP address of the Ubuntu machine. (You can type <code>hostname -I</code> to quickly get the IP.)</b></p>
<p><b>The attacker (Kali Linux) needs this IP to target the machine.</b></p>

<h3>2. Launch a Brute-Force Attack from Kali (Attacker Machine)</h3>
<p><b>Brute-force attacks are one of the most common attack types. Attackers try to guess user passwords using wordlists and automation. In organizations, SOC analysts are responsible for detecting and blocking these attempts.</b></p>

<img src="https://i.ibb.co/d0dmWZMj/kali-1.png" alt="Hydra Installation">
<p><b>🔹 Installs Hydra, a popular brute-force attack tool.</b></p>

<img src="https://i.ibb.co/Gvgtc6ts/kali-2.png" alt="Hydra Attack Command">
<p><b>🔹 <code>-l [ubuntu username]</code> – Specifies the username.</b></p>
<p><b>🔹 <code>-P /usr/share/wordlists/rockyou.txt</code> – Uses a password list (RockYou is a leaked real-world password list).</b></p>
<p><b>🔹 <code>ssh://[Your Ubuntu IP]</code> – Targets the Ubuntu machine via SSH.</b></p>

<h3>3. Detect & Defend with Fail2Ban on Ubuntu</h3>
<p><b>Now, we check if the attack was executed.</b></p>

<img src="https://i.ibb.co/yFSN0K89/ubuntu-5.png" alt="Ubuntu Logs">
<p><b>🔹 <code>sudo cat /var/log/auth.log | grep "Failed password"</code> – Filters logs to show failed SSH login attempts, proving a brute-force attack.</b></p>

<img src="https://i.ibb.co/G3dvk5t9/brut.png" alt="Failed SSH Attempts">
<p><b>As seen above, multiple login attempts were made from <code>10.0.2.15</code> (the attacker's IP).</b></p>
<p><b>Now, let's use our skills to defend the system.</b></p>

<img src="https://i.ibb.co/XfLfymqM/ubuntu-7.png" alt="Fail2Ban Installation">
<p><b>Fail2Ban is an intrusion prevention system that monitors logs and bans attackers after repeated failed login attempts. Let's install it.</b></p>

<img src="https://i.ibb.co/3mzQbhpr/ubuntu-8.png" alt="Fail2Ban Activation">
<p><b>Fail2Ban will now monitor for repeated failed login attempts and block suspicious IPs using firewall rules.</b></p>

<img src="https://i.ibb.co/DP3hyG6h/ubuntu-9.png" alt="Fail2Ban Logs">
<p><b>This checks the Fail2Ban log files where activities are recorded and banned IPs are stored.</b></p>

<img src="https://i.ibb.co/rGdfJT8y/ubuntu-10.png" alt="Fail2Ban Captured Logs">
<p><b>As seen above, Fail2Ban has captured logs from <code>10.0.2.15</code> (the attacker's IP) and has banned it.</b></p>

<img src="https://i.ibb.co/pNhkrtG/ubuntu-add-3.png" alt="Fail2Ban Status">
<p><b>The command below interacts with the Fail2Ban service, displaying detected authentication failures and listing blocked IPs.</b></p>

<img src="https://i.ibb.co/23V2hZqt/ubuntu-add-4.png" alt="Banned Attacker IP">
<p><b>As seen here, the attacker's IP has been successfully banned.</b></p>

<img src="https://i.ibb.co/N6Cm7qnc/ububtu-add-1.png" alt="Fail2Ban Configuration">
<p><b><code>nano</code> → Opens the Nano text editor.</b></p>
<p><b>The configuration file allows customization of Fail2Ban settings, such as ban duration and filtering rules.</b></p>

<img src="https://i.ibb.co/m5zRCHgs/ubuntu-add-2.png" alt="Fail2Ban Custom Settings">
<p><b>Here, I configured Fail2Ban to activate for SSH, allowing only 3 login attempts before banning the IP for 300 seconds (5 minutes).</b></p>

<p><b>That's the end of this project. Thank you!</b></p>
