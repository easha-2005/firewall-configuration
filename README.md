# firewall-configuration
🔐 Cyber Security Internship — Task 4
🔧 Setup and Use a Firewall on Windows
📌 Objective
To configure and test basic firewall rules on Windows to allow or block specific network traffic using Windows Defender Firewall and Telnet Client.

🛠️ Steps Performed
✅ 1. Enabled Telnet Client (Optional Tool for Testing)
Opened Command Prompt as Administrator.

Ran the following command to enable Telnet Client:

bash
Copy
Edit
dism /online /Enable-Feature /FeatureName:TelnetClient
Result:
✅ Telnet Client installed successfully.
📸 Screenshot:

✅ 2. Configured Windows Defender Firewall to Block Port 23
Opened Windows Defender Firewall with Advanced Security (wf.msc).

Navigated to Inbound Rules > New Rule.

Created a Port Rule:

Type: TCP

Port: 23

Action: Block the connection

Profile: Domain, Private, Public

Name: Block Port 23 (Telnet)

✅ 3. Tested the Firewall Rule
Opened Command Prompt.

Ran the Telnet test to localhost:

bash
Copy
Edit
telnet 127.0.0.1 23
Result:
❌ Connection failed as expected.

This indicates that the firewall is successfully blocking inbound traffic on port 23.

Message shown:

pgsql
Copy
Edit
Could not open connection to the host, on port 23: Connect failed
📸 Screenshot:

✅ 4. (Optional) Removed Firewall Rule
Went back to Windows Defender Firewall > Inbound Rules.

Located the rule named Block Port 23 (Telnet).

Right-clicked and chose Delete to restore the original state.

🧠 Key Learnings
Windows Firewall allows you to control traffic based on port and protocol.

Blocking port 23 is a common security practice, since Telnet is outdated and insecure.

Telnet is useful for manually testing open ports.

Firewalls act as the first line of defense in network security by filtering unwanted or harmful traffic.

📁 Deliverables
✅ Telnet installation confirmation.

✅ Firewall rule creation.

✅ Telnet test result (failed to connect).

✅ Rule removal for cleanup.

📎 Interview Questions - Sample Answers
What is a firewall?
A firewall is a network security device or software that monitors and controls incoming and outgoing network traffic based on predefined security rules.

Difference between stateful and stateless firewall?

Stateful: Tracks the state of active connections and makes decisions based on the context.

Stateless: Filters packets based solely on predefined rules without tracking connection state.

Why block port 23 (Telnet)?
Telnet transmits data, including passwords, in plain text. It is outdated and insecure, and often blocked to reduce vulnerabilities.
