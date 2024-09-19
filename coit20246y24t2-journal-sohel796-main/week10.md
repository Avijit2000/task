## Week 09

## Task 01: Knowledge Test
![knowledge](./images/week10knowledgetest.png)




## Task 2. Select Security Objectives

For our network design scenario, here are the selected sub-categories from the NIST Cybersecurity Framework (CSF) and their explanations:

### 1. **Function: Protect**  
   **Category: PR.AC (Access Control)**  
   **Sub-category: PR.AC-1**  
   **Description:** "Identities and credentials are managed for users, devices, and processes."  
   **Importance:** Proper management of identities and credentials ensures that only authorized individuals and devices can access specific network resources. In a network with multiple routers and features like wireless access and CCTV monitoring, managing credentials helps prevent unauthorized access to critical systems and data.  
   **Mitigates:** Vulnerabilities associated with unauthorized access and insider threats. For instance, it helps protect against attacks where an unauthorized user gains access to sensitive data or controls system functions improperly.

### 2. **Function: Protect**  
   **Category: PR.DS (Data Security)**  
   **Sub-category: PR.DS-5**  
   **Description:** "Data integrity is maintained and protected."  
   **Importance:** Ensuring data integrity means that data is protected from unauthorized alteration or corruption, which is crucial for maintaining the accuracy and reliability of information across your network. In departments handling sensitive data, such as labs and resource centers, data integrity is vital for operational reliability and trust.  
   **Mitigates:** Risks associated with data corruption or tampering, such as attacks that involve altering critical data to disrupt operations or mislead users.

### 3. **Function: Detect**  
   **Category: DE.AE (Anomalies and Events)**  
   **Sub-category: DE.AE-2**  
   **Description:** "Anomalous activity is detected and analyzed."  
   **Importance:** Detecting and analyzing anomalies in network activity helps identify potential security incidents early. In a network with multiple departments and features like RFID systems and digital notice boards, early detection of unusual behavior is crucial to preventing or mitigating security breaches.  
   **Mitigates:** Risks of undetected security incidents, such as insider threats or external attacks that could exploit system vulnerabilities before being noticed.

### 4. **Function: Detect**  
   **Category: DE.CM (Continuous Monitoring)**  
   **Sub-category: DE.CM-8**  
   **Description:** "Monitoring for unauthorized personnel, connections, devices, and software is performed."  
   **Importance:** Continuously monitoring the network for unauthorized personnel, connections, and devices ensures that any attempts to introduce rogue elements or unauthorized access are promptly detected. This is particularly important in a complex network setup with various routers and connected devices.  
   **Mitigates:** Risks associated with unauthorized access and potential breaches caused by rogue devices or unauthorized software, which could compromise network security and functionality.

### Summary for Journal:

1. **PR.AC-1: Identities and credentials are managed for users, devices, and processes.**  
   **Importance:** Ensures only authorized access to network resources, protecting against unauthorized access and insider threats.  
   **Mitigates:** Unauthorized access and insider threats.

2. **PR.DS-5: Data integrity is maintained and protected.**  
   **Importance:** Protects data from unauthorized alteration, ensuring accuracy and reliability.  
   **Mitigates:** Data corruption and tampering.

3. **DE.AE-2: Anomalous activity is detected and analyzed.**  
   **Importance:** Helps in identifying and responding to potential security incidents early.  
   **Mitigates:** Undetected security incidents and exploitation of vulnerabilities.

4. **DE.CM-8: Monitoring for unauthorized personnel, connections, devices, and software is performed.**  
   **Importance:** Detects and addresses unauthorized access or rogue devices, maintaining network security.  
   **Mitigates:** Unauthorized access and breaches from rogue devices or software.

By implementing these sub-categories, you can enhance your network’s protection and detection capabilities, ensuring a robust security posture for your organization.





## Task 3. Create Asset Inventory


To comprehensively document and manage the assets in your network design, we'll organize the assets into tables based on their types. Each table will include relevant identifying information and CIA Triad protections. For Data assets, we'll include classifications based on value and access.

### 1. **Data Assets**

| **Asset Name**         | **Classification** | **Value**   | **Access Level** | **CIA Protections**  |
|------------------------|---------------------|-------------|------------------|----------------------|
| Employee Records       | High                | Critical    | Restricted        | Confidentiality, Integrity, Availability |
| Financial Reports      | High                | Critical    | Restricted        | Confidentiality, Integrity, Availability |
| Network Configuration Files | Medium         | Important   | Restricted        | Confidentiality, Integrity |
| CCTV Footage           | Medium              | Important   | Restricted        | Confidentiality, Availability |
| Digital Notice Board Content | Low          | Low         | Public            | Integrity, Availability |
| Email Archives         | High                | Critical    | Restricted        | Confidentiality, Integrity, Availability |

**Notes:**
- **Classification:** Based on the sensitivity and importance of the data.
- **Value:** Indicates how critical the data is to the organization.
- **Access Level:** Indicates who can access the data (e.g., public, restricted).

### 2. **Hardware Assets**

| **Asset Name**         | **Type**          | **Serial Number** | **MAC Address** | **Location**    | **CIA Protections**  |
|------------------------|-------------------|-------------------|-----------------|-----------------|----------------------|
| Firewall               | Security Device   | FW-0011223344      | 00:1A:2B:3C:4D:5E| Data Center     | Availability, Integrity |
| Core Router            | Network Device    | CR-2233445566      | 00:1F:2E:3D:4C:5B| Data Center     | Availability, Integrity |
| Backup Core Router     | Network Device    | BCR-3344556677     | 00:2A:3B:4C:5D:6E| Data Center     | Availability         |
| Distribution Router 1  | Network Device    | DR1-4455667788     | 00:3C:4D:5E:6F:7A| Main Building   | Availability, Integrity |
| Distribution Router 2  | Network Device    | DR2-5566778899     | 00:4E:5F:6A:7B:8C| Main Building   | Availability, Integrity |
| Distribution Router 3  | Network Device    | DR3-6677889900     | 00:5F:6G:7B:8C:9D| Main Building   | Availability, Integrity |
| CCTV Camera 1          | Surveillance Device| CCTV-001122        | N/A             | Entrance Hall   | Availability, Confidentiality |
| Digital Notice Board   | Display Device    | DNB-112233         | N/A             | Admin Office    | Availability, Integrity |

**Notes:**
- **Type:** Categorizes the hardware asset (e.g., security device, network device).
- **Serial Number:** Unique identifier for the hardware.
- **MAC Address:** Unique network hardware identifier (for network devices).
- **Location:** Physical location of the asset.

### 3. **Software Assets**

| **Asset Name**        | **Version**     | **License Key**    | **Vendor**     | **Installation Location** | **CIA Protections**  |
|-----------------------|-----------------|-------------------|----------------|--------------------------|----------------------|
| Operating System      | 2024 Edition    | OS-XYZ-1234-ABCD  | Acme Corp      | Server Room              | Availability, Integrity |
| Antivirus Software    | 2024 Pro        | AV-ABC-5678-DEFG  | SecureSoft     | All Workstations          | Confidentiality, Integrity |
| Database Management   | 12.3.4          | DB-1234-XYZ567    | DataSoft       | Data Center              | Confidentiality, Integrity |
| Email Client          | 2024 Enterprise | EC-7890-HIJK123   | MailSolutions  | All Workstations          | Confidentiality, Availability |

**Notes:**
- **Version:** Indicates the version of the software.
- **License Key:** Unique identifier for the software license.
- **Vendor:** Company that provides the software.
- **Installation Location:** Where the software is installed.

### 4. **Network Assets**

| **Asset Name**         | **Type**          | **IP Address**     | **MAC Address** | **Location**    | **CIA Protections**  |
|------------------------|-------------------|-------------------|-----------------|-----------------|----------------------|
| Firewall               | Security Device   | 192.168.1.1       | 00:1A:2B:3C:4D:5E| Data Center     | Confidentiality, Integrity |
| Core Switch            | Network Switch    | 192.168.1.2       | 00:1F:2E:3D:4C:5B| Data Center     | Availability, Integrity |
| Access Point 1         | Wireless Device   | 192.168.1.10      | 00:2A:3B:4C:5D:6E| Main Building   | Availability, Confidentiality |
| Access Point 2         | Wireless Device   | 192.168.1.11      | 00:2B:3C:4D:5E:6F| Main Building   | Availability, Confidentiality |

**Notes:**
- **Type:** Categorizes the network asset (e.g., security device, network switch).
- **IP Address:** Network identifier for the asset.
- **MAC Address:** Unique network hardware identifier.

### 5. **Human Resources**

| **Asset Name**        | **Role**         | **Employee ID**    | **Department** | **Location**    | **CIA Protections**  |
|-----------------------|------------------|--------------------|----------------|-----------------|----------------------|
| Network Administrator | IT Specialist    | EMP1234            | IT             | Main Building   | Confidentiality, Integrity |
| Data Analyst          | Data Specialist  | EMP5678            | Analytics       | Main Building   | Confidentiality, Integrity |
| System Administrator  | IT Specialist    | EMP9101            | IT             | Data Center     | Confidentiality, Integrity |

**Notes:**
- **Role:** Job title or position.
- **Employee ID:** Unique identifier for the employee.
- **Department:** Department where the employee works.
- **Location:** Physical location within the organization.

### 6. **Facilities**

| **Asset Name**        | **Type**            | **Location**         | **Description**                | **CIA Protections**  |
|-----------------------|---------------------|----------------------|--------------------------------|----------------------|
| Server Room           | Physical Facility   | Data Center          | Houses critical network hardware| Availability, Integrity |
| Data Center           | Physical Facility   | Main Building        | Central location for IT systems | Availability, Integrity |
| Admin Office          | Physical Facility   | Admin Building       | Office for administrative work  | Availability, Integrity |

**Notes:**
- **Type:** Categorizes the facility (e.g., physical facility).
- **Description:** Brief description of the facility's purpose.

These tables provide a structured overview of the important assets in your network design, ensuring that each asset type is covered, and detailing the protections needed based on the CIA Triad.



## Task 4. Conduct a Risk Analysis

To conduct a risk analysis for your network design project, you can use a risk assessment template to identify potential risks, evaluate their impact, and determine appropriate mitigation strategies. Here's a general approach to performing a risk analysis, which you can follow when filling out your risk assessment template spreadsheet:

### 1. **Identify Assets and Threats**

First, list all critical assets in your network design, which may include:

- Firewall
- Core Router
- Backup Core Router
- Distribution Routers (1, 2, 3)
- CCTV Cameras
- Digital Notice Board
- Employee Login Credentials
- Network Hardware
- Printing Services
- Wireless Access Points
- Data Backup Systems

Next, identify potential threats to these assets. Common threats might include:

- Unauthorized access
- Hardware failure
- Network attacks (e.g., DDoS, malware)
- Data breaches
- Physical damage (e.g., fire, flood)
- Human error

### 2. **Assess Risks**

For each asset-threat combination, evaluate the following:

1. **Likelihood:** How probable is it that the threat will exploit the vulnerability? This can be categorized as Low, Medium, or High.
2. **Impact:** If the threat materializes, what will be the impact on the asset? This can also be categorized as Low, Medium, or High.
3. **Risk Level:** Combine likelihood and impact to determine the overall risk level. This can be categorized as Low, Medium, or High.

### 3. **Determine Mitigation Strategies**

For each identified risk, propose mitigation strategies to reduce the likelihood or impact of the risk. Mitigation strategies may include:

- Implementing additional security controls (e.g., intrusion detection systems)
- Regularly updating and patching systems
- Performing regular backups and testing restoration procedures
- Conducting staff training on security best practices
- Ensuring physical security measures (e.g., access controls, fire suppression systems)

### 4. **Document the Risk Assessment**

Use the following template format to document your risk assessment in the spreadsheet:

| **Asset**                 | **Threat**             | **Likelihood** | **Impact** | **Risk Level** | **Mitigation Strategy**                  |
|---------------------------|------------------------|----------------|------------|----------------|------------------------------------------|
| Firewall                  | Unauthorized Access    | Medium         | High       | High           | Implement strong access controls and regular audits. |
| Core Router               | Hardware Failure       | Low            | High       | Medium         | Set up redundant hardware and regular maintenance. |
| Distribution Router 1     | Network Attack         | Medium         | Medium     | Medium         | Deploy firewall rules and IDS/IPS systems. |
| CCTV Cameras              | Physical Damage        | Low            | High       | Medium         | Use protective enclosures and install in secure locations. |
| Employee Login Credentials| Data Breach            | High           | High       | High           | Implement multi-factor authentication and strong password policies. |
| Digital Notice Board      | Data Integrity Issue   | Low            | Medium     | Low            | Regularly verify data accuracy and access controls. |


Regularly review and update the risk assessment as new threats emerge or as changes are made to the network design or operational procedures.

By systematically identifying assets, evaluating risks, and planning mitigations, you can effectively manage and reduce potential risks to your network design. This approach will help ensure that your network operates securely and efficiently.
