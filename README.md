<h1>Brute-Force SSH Attack (Attack from Kali, Defend on Ubuntu)</h1> 
<img src="https://i.ibb.co/xSznyqc/image.jpg" alt="Brute-Force SSH Attack" width="1000" height="500">

<h2>Description</h2> 
<b>The Brute-Force SSH Attack project demonstrates the process of attacking an SSH service using a brute-force attack from a Kali Linux machine, while defending against the attack on an Ubuntu machine. It shows how attackers can exploit weak passwords, and how defenders can protect their systems through various security measures, such as monitoring logs, using fail2ban, and enforcing strong authentication policies.</b> 

<h2>Utilities Used</h2>

- <b>Python</b>
- <b>Hydra</b>
- <b>SSH</b>
- <b>fail2ban</b>
- <b>Ubuntu</b>
- <b>Kali Linux</b>

<h2>Environments Used</h2>

- <b>Ubuntu 20.04</b>
- <b>Kali Linux</b>
- <b>VS Code</b>

<h2>Program Features:</h2>

<p>1. Brute-Force Attack</p>
From the Kali Linux machine, use Hydra to attempt a brute-force attack on the SSH service running on the Ubuntu machine.
<a href="https://ibb.co/GQfBWMJn"><img src="https://i.ibb.co/LdDbxgPY/kali-1.png" alt="kali-1" width= "1000" height= "500"></a>
<img src="https://i.ibb.co/LdDbxgPY/kali-1.png" alt="kali-1" border="0">

<p>2. SSH Server Configuration</p>
Ensure the SSH service on Ubuntu is properly configured to allow remote login attempts and understand potential vulnerabilities.
<img src="https://i.ibb.co/JkX4hcg/veiw-bug.png" alt="ssh-config" border="0">

<p>3. Defending Against Brute-Force Attacks</p>
Implement **fail2ban** on Ubuntu to protect against multiple failed SSH login attempts by banning the attacking IP.
<img src="https://i.ibb.co/9WH1pG3/bug-status.png" alt="fail2ban-config" border="0">

<p>4. Log Monitoring</p>
Monitor the logs on the Ubuntu machine for failed login attempts and track the progress of the attack.
<img src="https://i.ibb.co/5RzWXn4/add-bugs.png" alt="log-monitoring" border="0">

<p>5. SSH Key Authentication</p>
After the brute-force attack is stopped, configure SSH key authentication for more secure access to Ubuntu.
<img src="https://i.ibb.co/JkX4hcg/veiw-bug.png" alt="ssh-key-auth" border="0">

<p>6. Preventive Measures</p>
Learn how to configure SSH to only accept strong passwords or even switch to key-based authentication to prevent brute-force attacks.
<img src="https://i.ibb.co/9WH1pG3/bug-status.png" alt="ssh-prevention" border="0">

<h2>Program Walkthrough:</h2>

<p>Initiating Brute-Force Attack:</p>
The Kali Linux machine launches a brute-force attack using Hydra against an SSH server on the Ubuntu machine.
<img src="https://i.ibb.co/NYwxCT8/3.png" alt="attack-initializing" border="0">

<p>Monitoring Logs:</p>
View the Ubuntu machine’s log to detect brute-force attempts and identify the attacking IP.
<img src="https://i.ibb.co/5RzWXn4/add-bugs.png" alt="log-monitoring" border="0">

<p>Implementing Fail2ban:</p>
Once the brute-force attack is detected, use **fail2ban** to block the IP address that initiated the attack.
<img src="https://i.ibb.co/9WH1pG3/bug-status.png" alt="fail2ban-config" border="0">

<p>Strengthening SSH Authentication:</p>
Configure SSH to use key-based authentication to further secure the system from brute-force attacks.
<img src="https://i.ibb.co/F7xCg4w/gui2.png" alt="ssh-key-auth" border="0">

<p>That's the end of this project, thank you!</p>
