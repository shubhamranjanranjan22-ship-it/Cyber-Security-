# Telnet Blocker and Firewall Profile Analyzer

## Objective
- To identify and display the active Windows Defender Firewall profiles.
- To block the Telnet port (TCP Port 23) to prevent unauthorized or insecure remote access.
- To improve the basic security posture of Windows systems.
- To automate firewall configuration checks and security settings.
- To provide users with an easy method for implementing essential firewall hardening practices.
## Problem Statement
Many Windows systems are left with insecure or misconfigured firewall settings. Users are often unaware of which firewall profiles are active and whether insecure network services such as Telnet are blocked. Since Telnet transmits data without encryption, it poses significant security risks if left accessible. There is a need for a simple tool that can analyze Windows Defender Firewall profiles and enforce basic security measures by blocking Telnet-related ports.
## Research Findings
- Telnet is an outdated remote access protocol that sends information in plain text, making it vulnerable to - interception.
- Windows Defender Firewall provides separate profiles (Domain, Private, and Public) that can be configured independently.
- Misconfigured or disabled firewall profiles increase the risk of network-based attacks.
- Blocking unused or insecure ports is considered a fundamental cybersecurity best practice.
- Security hardening through proper firewall configuration significantly reduces attack surfaces in Windows environments.
## Methodology
Step 1: Study Windows Defender Firewall architecture and security profiles.

Step 2: Retrieve the status of active firewall profiles using PowerShell or Command Prompt.

Step 3: Analyze whether the firewall is enabled for Domain, Private, and Public networks.

Step 4: Configure firewall rules to block TCP Port 23 (Telnet).

Step 5: Verify that the Telnet port has been successfully blocked.

Step 6: Display the current firewall configuration and generate a security status report.

Step 7: Test the implemented configurations on a Windows system to ensure proper functionality.
## Tools Used
- Windows PowerShell – Used to execute the security audit script and interact with Windows networking and firewall components.
- Windows Defender Firewall – Used to retrieve information about firewall profiles and their configuration.
- PowerShell Networking Cmdlets:
  - Get-NetTCPConnection – Retrieves all listening TCP ports on the system.
  - Get-NetFirewallProfile – Retrieves the status of Windows Firewall profiles.
  - Export-Csv – Generates the compliance report in CSV format.
- Windows Operating System (Windows 10/11) – Provides the environment for executing the script.
- CSV Report File – Stores the audit results for further analysis and documentation.

## Implementation

1. Opened Windows Firewall configuration tool.
2. Viewed existing inbound firewall rules.
3. Created a new inbound rule to block TCP Port 23 (Telnet).
4. Verified that the rule was successfully added.
5. Removed the rule to restore the firewall to its original state.
6. TCP Port Scanning:

   - The script scans all listening TCP ports using the Get-NetTCPConnection cmdlet.
   - It collects details such as local address, port number, connection state, and owning process.
7. Firewall Profile Analysis:

   - The script retrieves information about the Windows Defender Firewall profiles (Domain, Private, and Public).
   - It checks whether each profile is enabled or disabled and obtains its default inbound and outbound actions.
8. Compliance Report Generation:
   - The collected information is organized into custom PowerShell objects.
   - The results are exported into a CSV file named Security_Audit_Report.csv.
   - The generated report provides a consolidated view of open ports and firewall profile configurations.

## Screenshots
- Firewall main window
- Existing inbound rules
- Block Port 23 rule creation
- Rule verification
- Rule removal
- Image_of_code
- audit_run_statement
- CSV_Report_Output

## Result
The PowerShell script successfully:

- Identifies all currently listening TCP ports on the system.
- Detects the status of Windows Defender Firewall profiles.
- Displays whether firewall profiles are enabled or disabled.
- Generates an automated compliance report in CSV format.
- Provides a quick overview of the system's network exposure and firewall configuration.
- Helps administrators perform basic Windows security auditing efficiently.
## Challenges Faced
- Administrative privileges may be required to retrieve certain network and firewall configurations.
- Differences in Windows versions can affect the availability of PowerShell cmdlets.
- Some system or security policies may restrict access to networking information.
- Handling exceptions and command failures is necessary for reliable script execution.
- The script performs auditing only and does not automatically remediate security issues.
- The generated report requires manual interpretation for security decision-making.
## Future Scope
- Add automatic blocking of insecure ports such as TCP Port 23 (Telnet).
- Implement firewall rule creation and modification directly through the script.
- Include real-time monitoring of newly opened ports.
- Generate reports in multiple formats such as PDF and HTML.
- Develop a graphical user interface (GUI) for easier use.
- Integrate security recommendations based on the audit results.
- Extend support for remote system auditing across a network.
- Incorporate scheduled security scans and automated notifications.
## Conclusion
The Automated Windows Security Audit Script provides an effective method for auditing Windows network and firewall configurations. By identifying listening TCP ports and analyzing active firewall profiles, the script assists users in assessing the security posture of their systems. The automated generation of a compliance report simplifies security analysis and improves system administration practices. With additional features such as automatic port blocking and real-time monitoring, the project can be further developed into a comprehensive Windows security auditing and firewall management tool.
