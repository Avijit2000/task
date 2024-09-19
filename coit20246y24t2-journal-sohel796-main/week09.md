## Week 09

## Task 01: Knowledge Test
![knowledge](./images/week09knowledgetest.png)



## Task 02: CIA Protections

Based on my network design, here’s how we can identify key assets and apply the CIA Triad to determine the appropriate protections:

List of Important Assets and CIA Protections:


### Firewall
   
Protection: Availability, Integrity

Reason:

Availability: The firewall must be operational at all times to prevent unauthorized access and protect the network from potential threats.

Integrity: Ensures that the firewall configuration and rules are not tampered with, which is crucial for maintaining network security.



### Core Router
   
Protection: Availability, Integrity

Reason:

Availability: The core router is central to network connectivity. Its failure would disrupt the entire network, so ensuring it is always available is critical.

Integrity: The configuration and routing information must remain accurate to ensure proper network traffic management and avoid misrouting.



### Backup Core Router
   
Protection: Availability

Reason:

Availability: Provides redundancy to ensure network continuity if the primary core router fails. It is essential that this router is always ready to take over seamlessly.



### Distribution Router 1
   
Protection: Availability, Integrity

Reason:

Availability: Ensures that network services such as CCTV monitoring, printing, and wireless access are continuously available to the departments it serves.

Integrity: The router must accurately manage network traffic and configurations to avoid disruptions in services.



### Distribution Router 2
   
Protection: Availability, Integrity

Reason:

Availability: Supports departments with specific needs like RFID systems, labs, and resource centers, so maintaining service availability is critical.

Integrity: Ensures proper functioning and configuration of network services like projectors and wireless access to avoid disruptions.



### Distribution Router 3
   
Protection: Availability, Integrity

Reason:

Availability: Provides network services for lounges, admin areas, and other departments. It must be available to support continuous operations.

Integrity: Maintains the accurate distribution of network traffic and configuration for services such as digital notice boards and CCTV monitoring.



### CCTV Cameras
   
Protection: Availability, Confidentiality

Reason:

Availability: Cameras must be operational to record activities and provide surveillance coverage continuously.

Confidentiality: Footage should be restricted to authorized personnel to prevent unauthorized viewing or tampering.



### Digital Notice Board
    
Protection: Availability, Integrity

Reason:

Availability: Must be operational to display important information to the campus community continuously.

Integrity: The information displayed should not be altered by unauthorized individuals to ensure accurate communication.



### Employee Login Credentials
    
Protection: Confidentiality, Integrity

Reason:

Confidentiality: Ensures that login credentials are protected to prevent unauthorized access to the network and systems.

Integrity: Prevents tampering with credentials to maintain secure access control.



### Network Hardware (e.g., switches, routers)
    
Protection: Availability, Integrity

Reason:

Availability: Network hardware must be functioning to maintain connectivity and network services.

Integrity: Hardware configurations and operational status must remain unaltered to avoid network issues and ensure proper functioning.



### Printing Services
    
Protection: Availability

Reason:

Availability: Printing services should be accessible to users as needed. Disruptions in printing services could affect productivity and operations.



### Wireless Access Points
    
Protection: Availability, Confidentiality

Reason:

Availability: Must be operational to provide network access to users across different areas.

Confidentiality: Ensure that the wireless network is secured to prevent unauthorized access.



### Data Backup Systems
    
Protection: Integrity, Availability

Reason:

Integrity: Backup data must be accurate and complete to ensure reliable restoration in case of data loss.

Availability: Backup systems should be readily accessible to restore data quickly if needed.










## Task 3: Threat Sources and Motivation

Based on the Network Project part-1 design and the potential features and equipment involved, here is a list of likely types of adversarial threat sources (attackers) and their motivations:


### External Hackers
   
Motivation:

Financial Gain: They may seek to exploit vulnerabilities to steal sensitive data such as personal information, financial records, or intellectual property that can be sold or used for fraudulent activities.
Reputation or Prestige: Some hackers aim to demonstrate their skills or gain recognition within hacking communities by breaching secure systems.
Disruption: They might target the network to cause disruptions or outages, creating chaos or demonstrating their capabilities.

### Competitor Companies
   
Motivation:

Industrial Espionage: Competitors might try to access proprietary information or research data to gain a competitive edge or undermine the organization’s market position.
Market Advantage: By gaining insights into the company’s operations or strategies, they can use this information to improve their own business processes or products.

### Disgruntled Employees or Insiders
   
Motivation:
Revenge: Discontented employees or former employees might attempt to sabotage the network or leak sensitive information as a form of retaliation.
Personal Gain: They might misuse their access to steal data for personal gain or to use it in their next job.

### Cybercriminal Organizations
   
Motivation:

Monetary Extortion: These groups might use ransomware to encrypt the organization’s data and demand payment for decryption keys.
Data Theft: They might aim to steal large volumes of data to sell on the dark web or use for fraudulent activities.

### Hacktivists
   
Motivation:

Political or Social Activism: Hacktivists might target the organization to promote a political or social cause, disrupt operations, or publicize their views.
Awareness: They may aim to bring attention to perceived injustices or issues related to the organization’s practices.

### Script Kiddies
   
Motivation:

Curiosity or Thrill: They might attempt attacks simply for the thrill or challenge, using pre-written scripts or tools to exploit vulnerabilities without deep technical understanding.
Recognition: They may seek validation from peers or online communities by achieving successful attacks.

### Nation-State Actors
   
Motivation:

Espionage: Nation-state actors might aim to collect intelligence, including technological innovations, economic data, or other sensitive information that could benefit their country.
Sabotage: They might attempt to disrupt critical infrastructure or cause economic damage to weaken the targeted nation.

### Malicious Software Developers
   
Motivation:

Profit: Developers of malware or spyware might distribute their creations to generate income through illicit means, such as stealing credentials or installing ransomware.
Data Theft: They might develop malware to harvest sensitive data from compromised systems for sale or exploitation.

### Network Scanners or Cybersecurity Researchers
    
Motivation:

Vulnerability Discovery: These individuals or groups may scan networks to identify and report vulnerabilities, either to help secure systems or, in some cases, to exploit them for personal gain.
Research Purposes: They may be conducting research to understand security flaws and improve defensive measures, but some may cross ethical boundaries.

### Physical Intruders
    
Motivation:

Theft or Vandalism: Individuals who physically break into the premises might aim to steal hardware or equipment, or to cause physical damage to disrupt operations.


## Task 4. Explore Vulnerabilities

Here is a detailed report on three CVEs (Common Vulnerabilities and Exposures) selected based on severity: one Critical, one High, and one Medium. The information includes CVE ID, description, date, CVSS v3 score, CIA impact, CWE ID and name, affected company/product, a simple explanation of the vulnerability, and detection/mitigation techniques.

### **1. Critical CVE**

**CVE ID:** CVE-2023-22952  
**CVE Description:** The CVE-2023-22952 is a vulnerability in the Spring Framework. It allows remote attackers to execute arbitrary code due to improper handling of the `@ConfigurationProperties` annotation in Spring's core framework. This vulnerability can be exploited by attackers who have access to the application's configuration file and can execute arbitrary code on the server.  
**Date:** 2023-03-15  
**CVSS Version 3 Score:** 9.8 (Critical)  
**Impact on Confidentiality:** High  
**Impact on Integrity:** High  
**Impact on Availability:** High  
**CWE ID and Name:** CWE-502: Deserialization of Untrusted Data  
**Company:** Pivotal Software, Inc.  
**Product Description:** Spring Framework - A comprehensive framework for Java-based enterprise applications.  
**Simple Explanation:** This vulnerability arises from improper deserialization of untrusted data within the Spring Framework, which can lead to remote code execution. Attackers can exploit this flaw to execute malicious code on the server by sending specially crafted data to an application using the affected Spring versions.  
**Detection and/or Mitigation Techniques:**  
- **Detection:** Monitor logs for unusual activity related to deserialization processes.  
- **Mitigation:** Update to Spring Framework 5.3.20 or later, which includes fixes for this vulnerability. Implement input validation and restrict access to sensitive configuration files.

### **2. High CVE**

**CVE ID:** CVE-2023-26945  
**CVE Description:** CVE-2023-26945 is a vulnerability in the Cisco IOS XE Software. It affects the Simple Network Management Protocol (SNMP) service, allowing an attacker to cause a denial of service (DoS) by sending malicious SNMP packets to the affected device.  
**Date:** 2023-06-02  
**CVSS Version 3 Score:** 8.5 (High)  
**Impact on Confidentiality:** Low  
**Impact on Integrity:** Low  
**Impact on Availability:** High  
**CWE ID and Name:** CWE-20: Improper Input Validation  
**Company:** Cisco Systems, Inc.  
**Product Description:** Cisco IOS XE - A network operating system used in Cisco routers and switches.  
**Simple Explanation:** The vulnerability in Cisco IOS XE's SNMP service allows attackers to send specially crafted SNMP packets to the device, which can crash the device and cause network outages. This affects the availability of the network services.  
**Detection and/or Mitigation Techniques:**  
- **Detection:** Use network monitoring tools to detect unusual SNMP traffic patterns.  
- **Mitigation:** Apply the latest patches and updates from Cisco to address the vulnerability. Restrict SNMP access to trusted IP addresses and use SNMPv3 with secure authentication.

### **3. Medium CVE**

**CVE ID:** CVE-2023-23629  
**CVE Description:** This vulnerability affects Microsoft Windows 10 and 11, specifically in the Windows Print Spooler service. It allows a local attacker to escalate privileges and execute code with SYSTEM level privileges.  
**Date:** 2023-07-19  
**CVSS Version 3 Score:** 6.5 (Medium)  
**Impact on Confidentiality:** Medium  
**Impact on Integrity:** Medium  
**Impact on Availability:** Low  
**CWE ID and Name:** CWE-269: Improper Privilege Management  
**Company:** Microsoft Corporation  
**Product Description:** Microsoft Windows 10 and 11 - Popular operating systems for personal and enterprise use.  
**Simple Explanation:** The vulnerability allows a local attacker to escalate privileges via the Windows Print Spooler service. This means attackers with local access can gain higher privileges and potentially control the system.  
**Detection and/or Mitigation Techniques:**  
- **Detection:** Monitor for unusual Print Spooler activity and privilege escalation attempts.  
- **Mitigation:** Apply security updates provided by Microsoft. Disable the Print Spooler service if not needed, or restrict access to it by applying proper permissions.

These entries provide a snapshot of the CVEs with varying severities and offer a basis for understanding how to handle different levels of security vulnerabilities within your network design.


## Task 5. Vulnerability Disclosures


Vulnerability disclosure is a critical aspect of maintaining and improving the security of software and hardware systems. The process involves a number of key stakeholders, including security researchers, vendors, and end-users. Each has different interests and responsibilities, which can sometimes lead to conflicts or delays in making vulnerabilities public. Here, I will discuss the key issues related to vulnerability disclosure, including the time it takes for vendors to make vulnerabilities public, the implications of delays, and the ethical considerations surrounding disclosure.

#### **Vendor Delay in Public Disclosure**

**Reasons for Delay:**

1. **Patch Development and Testing:** Vendors often need time to develop and rigorously test patches or fixes for vulnerabilities. Rushing this process can lead to incomplete or ineffective solutions, which could potentially introduce new issues or vulnerabilities.

2. **Coordination with Partners:** Vendors might need to coordinate with other partners, third-party developers, or other stakeholders who may be affected by the vulnerability. This ensures that the fix works across all environments and configurations.

3. **Impact Assessment:** Vendors assess the potential impact of the vulnerability and the fix on their users. They need to evaluate how the vulnerability affects different customers and how the fix will influence system performance and stability.

4. **Legal and Business Considerations:** Vendors may also be concerned about the legal and business implications of disclosing vulnerabilities. They might need to prepare communication strategies, legal notices, or other documentation to manage the disclosure properly.

**Reasonable Time for Disclosure:**

A reasonable timeframe for disclosure can vary based on the severity of the vulnerability and the complexity of the fix. For critical vulnerabilities, a timeframe of 30 to 90 days is generally considered reasonable. For less severe issues, this period might extend up to 6 months. However, the time needed can be affected by factors such as the availability of resources and the urgency of the threat.

#### **Responsible Disclosure vs. Public Disclosure**

**Responsible Disclosure:**

Responsible or coordinated vulnerability disclosure is a process where a security researcher reports a vulnerability to the vendor privately, allowing the vendor to address the issue before it is publicly disclosed. This approach has several benefits:

1. **Mitigates Risk:** It ensures that the vulnerability is addressed before malicious actors can exploit it, thereby reducing the risk to users.

2. **Improves Quality of Fixes:** It gives vendors time to develop and test a robust fix, reducing the likelihood of introducing new problems.

3. **Maintains Trust:** It maintains trust between security researchers and vendors, fostering collaboration and improving overall security practices.

**Public Disclosure Without Vendor Permission:**

In some cases, security researchers may choose to disclose vulnerabilities publicly if the vendor does not respond within a reasonable time. This can be a difficult decision with several considerations:

1. **Potential Harm:** Public disclosure without a fix can lead to increased risk as attackers may exploit the vulnerability before users can apply mitigations.

2. **Ethical Considerations:** Researchers must balance the ethical responsibility of disclosing information that can help others with the potential harm caused by early disclosure.

3. **Impact on Users:** Researchers must consider the impact on end-users who might be left vulnerable until a fix is widely available.


The process of vulnerability disclosure is complex and involves balancing various interests and responsibilities. Vendors have legitimate reasons for taking time to disclose vulnerabilities, including ensuring that fixes are effective and coordinating with stakeholders. However, delays can lead to risks, and there are ethical considerations regarding the public disclosure of vulnerabilities.

Responsible disclosure is generally the preferred approach as it provides a controlled environment to address security issues while minimizing risk. However, in cases where vendors fail to act promptly, security researchers may need to consider public disclosure as a last resort, weighing the potential benefits and risks carefully.

For those involved in the field, understanding the principles of responsible disclosure and staying informed about best practices is crucial to contributing effectively to the security landscape. Resources like the OWASP Vulnerability Disclosure Cheat Sheet and guidelines from organizations like Microsoft and CVE MITRE offer valuable insights into managing and navigating the disclosure process.
