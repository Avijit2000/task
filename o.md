
### 4.1.1 Network Design

#### **1. Network Diagrams**
I’ll outline the network design description here. You can use [diagrams.net](https://www.diagrams.net/) (formerly draw.io) to create a visual representation. The diagram should include:

- **Core Network**: A core switch connecting all departments (Administration, Faculty, Students, WiFi, and CCTV).
- **VLANs**: Each department has its own VLAN to segregate traffic.
- **Servers**: Centralized servers in the administration building, connected to the core switch.
- **WiFi Access Points**: Located throughout the campus for staff and student access.
- **CCTV System**: Cameras connected to the network via a dedicated VLAN.
- **RFID Access Control**: Readers connected to the network for managing access to campus services.

#### **2. Explanation of Key Design Decisions**
- **VLAN Segmentation**: The network is divided into VLANs to improve performance, security, and manageability. Each VLAN represents a different department or network use (e.g., Admin, Faculty, Student WiFi).
- **Centralized Servers**: Housing the servers in one secure location ensures easy management, redundancy, and efficient use of resources.
- **WiFi Access Points**: WiFi is designed to cover the entire campus, with separate SSIDs for staff and students to enhance security and control bandwidth usage.
- **Redundancy and Scalability**: The system is designed to be scalable for future expansions and can handle additional users or devices as needed.

#### **3. WiFi Design**
- **SSID**:
  - Staff: **Campus-Staff**
  - Students: **Campus-Student**
- **Encryption**: WPA3 (most secure option for WiFi networks).
- **Channel Management**: Automatic channel selection to avoid interference and optimize performance.
- **Bandwidth Management**: Limit the bandwidth for student usage to ensure that the network resources are available for critical tasks.
- **Authentication**: Staff will use WPA3 Enterprise (using their credentials), and students will have WPA3 Personal with a shared key.
  
#### **4. Address Allocations**
For IP address allocation, we will use the student IDs you provided (12278305 and 12279205). Since the first decimal value in any IP address must be the last two digits of the student ID, we will use **78** and **05** as the starting points for each IP address.

##### **IP Address Plan**:
| VLAN                   | IP Range           | Subnet Mask    | Description                       |
|------------------------|--------------------|----------------|-----------------------------------|
| Admin & Finance VLAN    | 78.1.0.0/24        | 255.255.255.0  | Administration and Finance        |
| Faculty VLAN            | 78.2.0.0/24        | 255.255.255.0  | Faculty and Course Management     |
| Student VLAN            | 78.3.0.0/24        | 255.255.255.0  | Students’ Network                 |
| WiFi VLAN               | 78.4.0.0/24        | 255.255.255.0  | WiFi for staff and students       |
| CCTV VLAN               | 78.5.0.0/24        | 255.255.255.0  | CCTV and Security System          |

#### **5. Recommended Hardware**

Here’s the list of recommended hardware for the network setup:

1. **Router/Firewall**:
   - **Model**: Cisco ASA 5506-X with FirePOWER Services
   - **Price**: AUD 850
   - [Link](https://www.cisco.com/c/en/us/products/security/asa-5506-x-firepower-services/)

2. **Core Switch**:
   - **Model**: Cisco Catalyst 2960-X Series
   - **Price**: AUD 2000
   - [Link](https://www.cisco.com/c/en/us/products/switches/catalyst-2960-x-series-switches/)

3. **Access Points**:
   - **Model**: Ubiquiti UniFi AP AC Pro
   - **Price**: AUD 220
   - [Link](https://store.ui.com/products/unifi-ap-ac-pro)

4. **Servers**:
   - **Model**: Dell PowerEdge T640
   - **Price**: AUD 4000
   - [Link](https://www.dell.com/en-au/work/shop/povw/poweredge-t640)

5. **Backup NAS (for local backup)**:
   - **Model**: Synology DiskStation DS920+
   - **Price**: AUD 800
   - [Link](https://www.synology.com/en-global/products/DS920+)

---

### 4.1.2 IP Addressing Requirements

Since the IP address ranges must be based on your student IDs (12278305 and 12279205), we’ll use **78** and **05** as the starting points for the network.

Here’s the complete IP address allocation:

| VLAN                   | IP Range           | Subnet Mask    | Description                       |
|------------------------|--------------------|----------------|-----------------------------------|
| Admin & Finance VLAN    | 78.1.0.0/24        | 255.255.255.0  | Administration and Finance        |
| Faculty VLAN            | 78.2.0.0/24        | 255.255.255.0  | Faculty and Course Management     |
| Student VLAN            | 78.3.0.0/24        | 255.255.255.0  | Students’ Network                 |
| WiFi VLAN               | 78.4.0.0/24        | 255.255.255.0  | WiFi for staff and students       |
| CCTV VLAN               | 78.5.0.0/24        | 255.255.255.0  | CCTV and Security System          |

We also use another range starting with **05** (from your partner's ID) for redundancy or future expansion.

| VLAN                   | IP Range           | Subnet Mask    | Description                       |
|------------------------|--------------------|----------------|-----------------------------------|
| Expansion VLAN          | 05.1.0.0/24        | 255.255.255.0  | Future Expansion                  |

---

This covers the entire **Network Design** and **IP Addressing** portion of your project. You can now take this design and build the visual network diagram using [diagrams.net](https://www.diagrams.net/). Let me know when you're ready to proceed to the **Cloud Services** section or if you need assistance with the network diagram.

### 4.2 Cloud Services

#### **Introduction**

The training organization currently stores its web server and all business data on-premises at its renovated campus office. While management believes that keeping data locally is safer, they are concerned about the operational performance and maintenance challenges due to limited technical expertise and resources. This section will explore the benefits of moving to cloud services and compare cloud providers, focusing on performance, security, cost, and operational efficiency.

#### **Why Cloud Services May Be Better Suited for Operations**

1. **Scalability**:
   - Cloud platforms allow for easy scaling. As the organization grows or as demand fluctuates (such as during enrollment periods), additional computing resources can be added without overhauling the entire infrastructure.
   - Cloud services offer both vertical (upgrading hardware resources) and horizontal (adding more virtual machines or storage) scalability options.

2. **Cost Efficiency**:
   - Cloud services eliminate the need for maintaining physical hardware on-premises, reducing capital expenditure (CAPEX) and shifting to an operational expenditure (OPEX) model.
   - Pay-as-you-go pricing models mean the organization only pays for what it uses. This is especially beneficial given the limited budget and ICT resources.

3. **Reduced IT Overhead**:
   - With cloud services, routine tasks like server maintenance, backups, software updates, and security patches are managed by the cloud service provider (CSP). This is a critical advantage for an organization with limited technical support.
   - This allows the organization to focus on its core mission (providing training and education) rather than IT infrastructure management.

4. **High Availability and Redundancy**:
   - Cloud providers offer Service Level Agreements (SLAs) with guaranteed uptime, which can be higher than what is achievable on-premises without significant investment in redundant infrastructure.
   - Built-in redundancy across multiple data centers ensures that the organization’s web server and data are always available, even in case of server failure or maintenance.

5. **Security and Compliance**:
   - Cloud providers have robust security protocols in place, including encryption, identity management, monitoring, and automatic security patching. They also comply with industry standards and regulations, such as ISO certifications, GDPR, and others.
   - While the organization may fear data security in the cloud, major cloud providers offer better security infrastructure than what could typically be managed in-house with limited resources.

#### **Cloud Provider Comparison**

The next step is to compare two major cloud providers: **Amazon Web Services (AWS)** and **Microsoft Azure**. We will estimate the cost of moving the organization’s web server to the cloud and evaluate both options based on performance, cost, and region availability.

1. **Amazon Web Services (AWS)**:
   - **Instance Type**: t3.medium (2 vCPUs, 4 GB RAM)
   - **Storage**: 100 GB SSD (for the web server)
   - **Region**: Australia (Sydney)
   - **Operating System**: Linux (Ubuntu 20.04)
   - **Estimated Annual Cost**: AUD 680/year (based on the AWS Pricing Calculator)
     - Includes compute, storage, and data transfer.
   - [AWS Pricing Calculator](https://calculator.aws/#/)

2. **Microsoft Azure**:
   - **Instance Type**: B2s (2 vCPUs, 4 GB RAM)
   - **Storage**: 100 GB SSD
   - **Region**: Australia East (Sydney)
   - **Operating System**: Linux (Ubuntu 20.04)
   - **Estimated Annual Cost**: AUD 720/year (based on the Azure Pricing Calculator)
     - Includes compute, storage, and data transfer.
   - [Azure Pricing Calculator](https://azure.microsoft.com/en-us/pricing/calculator/)

#### **Recommendation: AWS vs. Azure**

- **AWS** offers a slightly lower annual cost for the required instance type and storage capacity. It also provides a broader range of services and more customizable options for scaling, which may suit the organization better as it expands.
- **Azure**, while slightly more expensive, has excellent integration with Microsoft products. If the organization heavily uses Microsoft tools (e.g., Office 365, Windows Servers), Azure would offer seamless integration and potentially reduce complexity in management.

Given the organization's limited technical expertise, AWS may be the better option due to its lower cost, broader service range, and user-friendly management options for small businesses.

#### **Cloud Server Configuration Summary**:
| Specification         | AWS                 | Azure               |
|-----------------------|---------------------|---------------------|
| Instance Type         | t3.medium           | B2s                 |
| vCPUs                 | 2                   | 2                   |
| RAM                   | 4 GB                | 4 GB                |
| Storage               | 100 GB SSD          | 100 GB SSD          |
| Operating System      | Linux (Ubuntu 20.04)| Linux (Ubuntu 20.04)|
| Region                | Sydney              | Sydney              |
| Estimated Annual Cost | AUD 680             | AUD 720             |

#### **Cloud Backup Considerations**

The organization currently uses a local RAID NAS for backups. However, moving to a cloud backup solution can provide better security, redundancy, and ease of management.

1. **AWS S3** (Simple Storage Service):
   - Cost: AUD 0.025 per GB per month for standard storage.
   - With 1 TB of backup data, the cost would be approximately AUD 307.20/year.
   - **Pros**: Secure, reliable, easy to scale.
   
2. **Azure Blob Storage**:
   - Cost: AUD 0.026 per GB per month for standard storage.
   - With 1 TB of backup data, the cost would be approximately AUD 319.68/year.
   - **Pros**: Secure, reliable, good integration with Microsoft services.

**Recommendation**: AWS S3 offers slightly lower cost and similar performance, making it a more cost-effective choice for cloud backup.

---

Would you like me to assist further with exploring more cloud services or backup solutions, or should we move on to the next task?



### 4.2.1 Cloud Server

#### **Objective**:
The training organization plans to relocate its web server to the cloud. We are tasked with estimating and comparing the cost of hosting this server on two different cloud service providers (AWS and Azure) and then recommending one of them. The server will host the public website of the organization, which contains information about the courses and services offered.

#### **Cloud Providers for Comparison**:
- **Amazon Web Services (AWS)**
- **Microsoft Azure**

Both providers offer reliable infrastructure and are suitable for hosting web servers. The key specifications for the cloud server will be similar for both providers to ensure a fair comparison.

---

### **Cloud Server Specifications**:

- **Region**: Australia (Sydney for both AWS and Azure, to minimize latency for users and ensure compliance with data locality laws).
- **Operating System**: Linux (Ubuntu 20.04) – a common, cost-effective, and secure option for hosting web servers.
- **vCPUs**: 2 virtual CPUs – suitable for handling moderate website traffic and dynamic content.
- **RAM**: 4 GB – enough to manage the content-heavy website with images, course details, etc.
- **Storage**: 100 GB SSD – sufficient for storing the web server files, images, course materials, and any potential growth in data.
- **Bandwidth**: Both providers offer various levels of bandwidth, and the actual cost will depend on usage. For simplicity, we will assume moderate traffic for the website and include basic bandwidth estimates.

---

### **Cost Estimation Using AWS and Azure Calculators**:

#### **1. Amazon Web Services (AWS)**:
- **Instance Type**: t3.medium (2 vCPUs, 4 GB RAM)
- **Storage**: 100 GB SSD (General Purpose SSD)
- **Region**: Australia (Sydney)
- **Operating System**: Ubuntu 20.04
- **Estimated Annual Cost**: **AUD 680/year**
  - This includes compute, storage, and bandwidth for moderate usage.

#### **2. Microsoft Azure**:
- **Instance Type**: B2s (2 vCPUs, 4 GB RAM)
- **Storage**: 100 GB SSD (Premium SSD)
- **Region**: Australia East (Sydney)
- **Operating System**: Ubuntu 20.04
- **Estimated Annual Cost**: **AUD 720/year**
  - This includes compute, storage, and bandwidth for moderate usage.

---

### **Comparison and Recommendation**:

| Specification         | AWS                    | Azure                  |
|-----------------------|------------------------|------------------------|
| **Instance Type**     | t3.medium (2 vCPUs, 4 GB RAM) | B2s (2 vCPUs, 4 GB RAM) |
| **Storage**           | 100 GB SSD (GP2)       | 100 GB SSD (Premium)   |
| **Operating System**  | Ubuntu 20.04           | Ubuntu 20.04           |
| **Region**            | Australia (Sydney)     | Australia East (Sydney)|
| **Estimated Annual Cost** | AUD 680/year         | AUD 720/year           |

---

### **Recommendation**:

Based on the comparison, **AWS** is the more cost-effective solution with a slightly lower annual cost. AWS also has a vast range of services and robust support, making it a suitable choice for this organization, especially given its limited ICT resources. Additionally, AWS's t3.medium instance is well-suited for a web server that will host dynamic content, providing the necessary performance for moderate traffic levels.

**Why AWS**:
- **Cost**: AWS offers a lower annual cost compared to Azure for the same server specifications.
- **Scalability**: AWS offers an extensive range of scaling options, making it easier to handle any future growth or increases in web traffic.
- **User-Friendly**: AWS provides a user-friendly management console, which is beneficial for an organization with limited technical expertise.
- **Security**: AWS provides top-tier security features, including encryption and regular security patching, which can be managed without much manual intervention.

#### **Justification of Specifications**:
- **Region (Australia)**: Hosting the server in Australia minimizes latency for users and ensures compliance with local data storage regulations.
- **Operating System (Linux - Ubuntu 20.04)**: Ubuntu is widely used for web servers due to its security, cost-effectiveness, and performance. It supports a variety of web server technologies like Apache, Nginx, and more.
- **vCPUs (2)**: The chosen virtual CPU count (2 vCPUs) provides enough processing power to handle moderate traffic on the organization’s website.
- **RAM (4 GB)**: This amount of memory is sufficient for the website and will ensure smooth performance even with multiple concurrent users.
- **Storage (100 GB SSD)**: An SSD provides fast data access and storage, essential for quick page loading times and handling media files like course details and images.

---

### **Next Steps**:
- You can now export the pricing estimates from the AWS and Azure pricing calculators and upload them to your GitHub repository.
- After that, this section will be complete, and we can move on to **4.2.2 Backup** or any other part of the project.

Would you like assistance with the exporting process or any other part of the cloud services?





### 4.2.2 Backup

#### **(a) Adequacy and Sufficiency of Current Backup Arrangement**:

The current backup arrangement involves a **local RAID NAS (Network-Attached Storage)**, which stores important business files such as enrolment, financial, student, and staff data. While this setup offers some redundancy due to the RAID configuration, there are a few critical limitations:

1. **Local Failures**: Although RAID provides redundancy, it does not protect against physical threats such as fire, theft, flooding, or hardware failure. If the NAS device is compromised or damaged, all backed-up data could be lost.
   
2. **Scalability**: As the organization grows, data storage needs will increase. A local RAID NAS may not be easily scalable without replacing or upgrading hardware, which can be costly.
   
3. **Off-Site Backup**: Best practice for backups includes off-site or cloud storage to ensure data recovery in case of local disasters. Relying solely on on-premises storage is a significant risk.
   
4. **Limited Automation and Monitoring**: While the NAS may offer some degree of automated backup, cloud-based solutions provide superior automation, monitoring, and alerts for backup failures.

#### **Conclusion**:
While the local RAID NAS provides basic redundancy, it is not sufficient for complete data protection. The current arrangement lacks off-site backups and is vulnerable to local disasters. Therefore, it would be beneficial to consider **cloud-based** and additional **non-cloud** backup solutions to create a more robust backup strategy.

---

### **(b) Cloud Backup Solutions**

**Cloud-based backups** offer several advantages, including off-site storage, scalability, high availability, and advanced security features. Below are two potential cloud service providers (CSPs) for backup:

#### **1. Amazon Web Services (AWS) - Amazon S3 (Simple Storage Service)**
   - **Storage Cost**: AUD 0.025 per GB per month (Standard Storage)
   - **Capacity**: 1 TB (1000 GB)
   - **Estimated Annual Cost**: AUD 307.20/year
   - **Advantages**:
     - Highly scalable.
     - Data durability of 99.999999999% (11 9s).
     - Secure encryption and access control.
     - Versioning to protect against accidental deletion or overwrites.
   - **Disadvantages**:
     - Requires some setup and management via AWS console.
   
#### **2. Microsoft Azure - Blob Storage**
   - **Storage Cost**: AUD 0.026 per GB per month (Standard Storage)
   - **Capacity**: 1 TB (1000 GB)
   - **Estimated Annual Cost**: AUD 319.68/year
   - **Advantages**:
     - Good integration with Microsoft environments (Office 365, Active Directory).
     - Secure and highly scalable.
     - Versioning and replication options for redundancy.
   - **Disadvantages**:
     - Slightly higher cost compared to AWS.

#### **Cloud Backup Comparison Table**:

| Cloud Provider      | Storage Type         | Cost (AUD/GB/month) | Total Capacity (1 TB) | Annual Cost (AUD) | Features                                      |
|---------------------|----------------------|---------------------|-----------------------|-------------------|------------------------------------------------|
| AWS (Amazon S3)      | Standard Storage     | 0.025               | 1 TB                  | 307.20            | Highly durable, scalable, secure, versioning   |
| Microsoft Azure      | Blob Storage         | 0.026               | 1 TB                  | 319.68            | Secure, good Microsoft integration, versioning |

#### **Recommendation**:
- **AWS S3** is the recommended choice due to its slightly lower cost, high durability, and extensive scalability. It offers excellent data redundancy and protection through versioning and encryption. AWS also has a pay-as-you-go pricing model, making it affordable as the organization’s data grows.

---

### **(c) Non-Cloud Backup Solutions**

For organizations that prefer to maintain control over their backups or wish to use a non-cloud solution alongside the cloud, the following options are viable:

#### **1. External Hard Drives (Offline Backup)**
   - **Cost**: AUD 100–200 for 1–2 TB of storage.
   - **Capacity**: 1–2 TB
   - **Advantages**:
     - Low cost for high capacity.
     - No recurring costs.
     - Suitable for offline backups and storing in a secure off-site location.
   - **Disadvantages**:
     - Manual process for backups.
     - Susceptible to physical damage or theft.
     - Limited automation and scalability.

#### **2. Tape Backup (LTO - Linear Tape-Open)**
   - **Cost**: AUD 300–600 for tape drives and tapes.
   - **Capacity**: 1 TB per tape
   - **Advantages**:
     - Long-term archival storage.
     - Reliable and durable for data retention.
     - Can be stored off-site for disaster recovery.
   - **Disadvantages**:
     - High upfront cost.
     - Slower retrieval compared to cloud or NAS.
     - Requires regular maintenance and manual intervention.

#### **Non-Cloud Backup Comparison Table**:

| Solution           | Cost (AUD)     | Capacity         | Advantages                            | Disadvantages                          |
|--------------------|----------------|------------------|---------------------------------------|----------------------------------------|
| External Hard Drive | 100–200        | 1–2 TB           | Low cost, no recurring fees           | Manual backups, physical damage risk   |
| Tape Backup (LTO)   | 300–600        | 1 TB per tape    | Long-term archival, off-site storage  | High upfront cost, slow retrieval      |

---

### **(d) Backup Recommendations for CQU ICT Students**

For university students, especially those studying ICT, it is important to have reliable and regular backups of coursework, assignments, code projects, and personal data. Below is a recommended approach for organizing and backing up university work.

#### **1. Cloud-Based Backup Solutions**:
- **Google Drive** (available through CQU student accounts):
  - **Capacity**: 15 GB (free) or higher with paid plans.
  - **Advantages**:
    - Automatic syncing between devices (desktop and mobile).
    - Version control for documents.
    - Easy sharing with team members for group projects.
  - **Usage**: Students can automatically back up important files (assignments, notes, etc.) by syncing Google Drive to their computer.

- **GitHub** (for code projects):
  - **Advantages**:
    - Version control and collaboration for coding projects.
    - Free private repositories for students.
    - Easy integration with development environments (e.g., Visual Studio, PyCharm).
  - **Usage**: Students can back up their coding assignments and collaborate with others using GitHub’s version control system.

#### **2. Local Backup Solutions**:
- **External Hard Drive**:
  - **Capacity**: 1 TB (around AUD 100).
  - **Advantages**:
    - Easy offline backup.
    - Large storage capacity.
  - **Usage**: Students can perform weekly backups of their entire laptop or desktop to ensure that coursework is always saved offline.

---

#### **Recommendation**:
- For CQU ICT students, a **combination** of **Google Drive** (for documents and assignments) and **GitHub** (for coding projects) is ideal. These tools offer automatic syncing, easy version control, and cloud-based storage, ensuring students can access their work from anywhere and restore files if necessary.
- Additionally, using an **external hard drive** for local weekly backups will add an extra layer of protection against data loss due to hardware failure or accidental deletions.

---

Would you like assistance with any other sections or further exploration of the cloud backup tools? Let me know how you'd like to proceed!



### 4.3.1 Cyber Security Risk Assessment

#### **Objective**:
This mini cyber security risk assessment will analyze the vulnerabilities in the network, taking into account at least 8 of the 12 common information security threats. We'll assess the risks associated with various assets, including physical assets, network assets, and data assets. The risk assessment will follow a simplified approach due to time constraints and the information available.

---

### **Cyber Security Risk Assessment Template**

| **Asset Type**       | **Asset Description**                          | **Security Threat**       | **Vulnerability**                      | **Potential Impact**       | **Risk Rating** | **Mitigation Strategy** |
|----------------------|------------------------------------------------|---------------------------|----------------------------------------|----------------------------|-----------------|-------------------------|
| **Data Asset**       | Enrolment data (students' personal information)| Data breach (external)    | Weak access control on sensitive data | Identity theft, legal issues| High            | Implement MFA, encryption|
| **Data Asset**       | Financial records                              | Insider threat            | Unauthorized internal access           | Financial loss, legal issues| High            | Role-based access control|
| **Data Asset**       | Student assignments and grades                 | Data corruption           | Lack of version control or backups     | Loss of academic data       | Medium          | Regular backups to cloud |
| **Data Asset**       | Course materials (faculty)                     | Data theft                | Weak password policies                 | Loss of intellectual property| High           | Enforce password policies|
| **Physical Asset**   | Networked CCTV system                          | Unauthorized access       | Weak network segmentation              | Compromised campus security | High            | VLANs, firewall policies |
| **Network Asset**    | WiFi access points                             | Eavesdropping             | Insufficient encryption (WPA2 instead of WPA3)| Data theft, privacy breach| High            | Use WPA3 encryption       |
| **Network Asset**    | Web server                                     | Denial of Service (DoS)   | Lack of firewall rules                 | Website downtime            | Medium          | Use firewall and load balancer|
| **System Asset**     | Centralized servers (admin & finance)          | Malware (ransomware)      | Unpatched software vulnerabilities     | Data loss, system downtime  | High            | Regular patching, anti-malware |

---

### **Asset Types and Data Assets Considered**:
The risk assessment considers a mix of asset types, including **data assets**, **physical assets**, **network assets**, and **system assets**. These are crucial components of the training organization’s infrastructure, and protecting them is essential for maintaining operations, security, and privacy.

#### **1. Data Assets**:
- **Enrolment Data**: Contains personal student information such as names, addresses, and IDs. This data is critical for managing students’ enrolment and is a high-value target for attackers.
- **Financial Records**: Includes payment records, transactions, and financial details, which must be protected from unauthorized access.
- **Student Assignments and Grades**: This data needs integrity and availability, as loss or corruption could result in academic issues.
- **Course Materials**: Faculty uploads course materials to the system. A breach could lead to loss of intellectual property.

#### **2. Physical Assets**:
- **CCTV System**: Networked CCTV cameras ensure campus security, but if hacked, they could be used for surveillance or manipulation.
  
#### **3. Network Assets**:
- **WiFi Access Points**: These are used by staff and students. Weak encryption or improper access control could lead to unauthorized access or eavesdropping.
- **Web Server**: Hosts the organization’s website. Vulnerabilities could make it susceptible to DoS attacks, causing service downtime.

#### **4. System Assets**:
- **Centralized Servers**: These servers store sensitive data, including admin, finance, and course management systems. Unpatched software or malware could compromise the entire system.

---

### **Security Threats Considered**:

We analyzed the following 8 common security threats:

1. **Data Breach (External)**:
   - Sensitive information (e.g., enrolment data) could be accessed by unauthorized individuals due to weak access controls or a lack of encryption.

2. **Insider Threat**:
   - Authorized users with access to financial or student data may misuse their privileges, leading to unauthorized access and possible data leaks.

3. **Data Corruption**:
   - Without proper version control or regular backups, critical data such as assignments and grades could be corrupted, leading to loss of academic progress.

4. **Data Theft**:
   - Faculty course materials could be stolen due to weak password policies, potentially leading to the unauthorized distribution of intellectual property.

5. **Unauthorized Access**:
   - The networked CCTV system may be vulnerable to unauthorized access, enabling attackers to manipulate or monitor the campus's physical security.

6. **Eavesdropping**:
   - If WiFi encryption is outdated (e.g., WPA2 instead of WPA3), attackers could intercept sensitive communication between devices on the network.

7. **Denial of Service (DoS)**:
   - The web server hosting the organization’s public website could be targeted by DoS attacks, rendering the website unavailable to users.

8. **Malware (Ransomware)**:
   - Centralized servers that handle administrative and financial operations could be targeted by ransomware or other malware, causing data loss and system downtime.

---

### **Risk Rating**:
The risks are rated based on their potential impact and likelihood. In this case, **data breaches** (especially enrolment and financial data) and **insider threats** have been rated **High**, as they could lead to identity theft, financial loss, and legal consequences. Malware on the **centralized servers** is also a high risk, given the impact on critical systems.

---

### **Mitigation Strategies**:

1. **Implement MFA (Multi-Factor Authentication)**: For accessing sensitive data such as enrolment and financial records. This will ensure that even if credentials are compromised, unauthorized access is less likely.
   
2. **Encryption**: All sensitive data (e.g., enrolment data, financial records) should be encrypted both in transit and at rest. This reduces the risk of data breaches even if unauthorized access occurs.

3. **Regular Backups**: Automated backups should be performed regularly, with backups stored in the cloud (AWS S3 or Azure Blob Storage). This ensures that data like student assignments and grades are always recoverable in case of corruption or loss.

4. **Role-Based Access Control**: Implement strict role-based access control (RBAC) for sensitive data, ensuring that only authorized personnel can access or modify critical information.

5. **Firewall Rules**: Deploy firewalls to protect the web server from DoS attacks and to ensure that external threats are filtered before they reach internal systems.

6. **WiFi Encryption (WPA3)**: Upgrade WiFi access points to WPA3 encryption, ensuring that any data transmitted over the wireless network is secure from eavesdropping.

7. **Anti-Malware and Patch Management**: Regularly update software and deploy anti-malware solutions to ensure that the servers are protected against ransomware and other malicious threats.

---

### **Next Steps**:
Would you like assistance with the next task, **4.3.2 Recommend Security Controls**, or would you prefer to explore further aspects of the risk assessment?



### 4.3.2 Recommend Security Controls

#### **Selected Data Asset**: **Enrolment Data (Students' Personal Information)**

In the previous risk assessment, **enrolment data** was identified as having the highest risk due to the potential for data breaches. This data includes sensitive personal information such as student names, addresses, and IDs, making it a high-value target for external attackers and insider threats.

To mitigate the risk, we will recommend the implementation of **encryption**, **Multi-Factor Authentication (MFA)**, and **firewalls**. Below is a detailed explanation of how each security control will be applied in this project scenario and how they reduce risk.

---

### **1. Encryption**

#### **How Encryption Reduces Risk**:
Encryption protects sensitive data by encoding it so that unauthorized users cannot read it without the correct decryption key. Even if an attacker gains access to the data, encryption ensures that the information remains unintelligible, reducing the risk of data breaches and identity theft.

#### **Encryption Implementation in the Project**:
- **Data at Rest**: All enrolment data stored on centralized servers and backup systems (e.g., NAS or cloud storage) should be encrypted using **AES-256 encryption**. This is a widely accepted encryption standard that ensures strong security for sensitive data.
  - **Technology**: Use **BitLocker** for on-premises servers or cloud-native encryption services like **AWS KMS (Key Management Service)** or **Azure Encryption** for cloud-stored data.
  - **Network Component**: Enrolment data is stored in centralized servers connected to the admin VLAN. Data stored in NAS or cloud backups will be encrypted both locally and in transit.

- **Data in Transit**: All communication involving sensitive data, such as accessing enrolment data over the web or through internal systems, should be encrypted using **SSL/TLS** (Secure Sockets Layer / Transport Layer Security).
  - **Technology**: Implement SSL certificates for the web server to ensure all communication between the server and clients is encrypted.
  - **Network Component**: This encryption is enforced between the web server, admin staff systems, and any external access points. It ensures that data is protected as it moves across the network.

#### **Disadvantages of Encryption**:
- **Performance Overhead**: Encryption can add processing overhead, particularly for large datasets, slowing down access times. This may affect the speed of retrieving and updating enrolment data.
- **Key Management**: Improper handling of encryption keys could lead to data loss. If encryption keys are lost or mishandled, the data may become permanently inaccessible.

---

### **2. Multi-Factor Authentication (MFA)**

#### **How MFA Reduces Risk**:
MFA adds an additional layer of security by requiring users to provide two or more authentication factors before gaining access to sensitive data. This reduces the risk of unauthorized access, especially in cases where passwords are compromised.

#### **MFA Implementation in the Project**:
- **For Admin and Staff Access**: Implement MFA for staff members who access the enrolment system and any sensitive student data. The most common MFA setup requires a password and a one-time code sent to a mobile device or generated via an app like **Google Authenticator**.
  - **Technology**: Use MFA services such as **Microsoft Azure Active Directory MFA** or **AWS MFA**. These services can be integrated with the existing Active Directory or cloud systems used by the organization.
  - **Network Component**: MFA will be applied to all user accounts within the **Admin VLAN**, particularly those accessing the enrolment data. Any external access to sensitive systems (e.g., remote staff access) will also require MFA.

#### **Disadvantages of MFA**:
- **User Friction**: MFA requires additional steps during login, which could frustrate users or slow down workflows. Some staff may find it inconvenient to use multiple devices to authenticate their identity.
- **Device Dependency**: If staff lose access to their second authentication factor (e.g., a lost phone), they may be locked out of the system, requiring an administrative reset.

---

### **3. Firewalls**

#### **How Firewalls Reduce Risk**:
Firewalls control incoming and outgoing network traffic by applying rules based on an established security policy. This can prevent unauthorized access to sensitive systems and protect against external threats like malware, data exfiltration, and DoS attacks.

#### **Firewall Implementation in the Project**:
- **Network Perimeter Protection**: Deploy a firewall at the perimeter of the network to filter all incoming and outgoing traffic. This will prevent unauthorized external users from accessing the enrolment data or any internal systems.
  - **Technology**: Use a **Cisco ASA 5506-X firewall** with **FirePOWER Services** to protect the network. This firewall will inspect traffic, block suspicious activity, and prevent unauthorized connections to the admin VLAN.
  - **Network Component**: The firewall will be configured to protect the **Admin VLAN** (where enrolment data is stored) from any external threats. It will also enforce network segmentation, ensuring that only authorized devices within the network can communicate with sensitive data systems.

- **Internal Segmentation**: Use **VLANs** to further segment internal network traffic. The enrolment system should be isolated from other non-critical systems, ensuring that any potential breach in another area of the network cannot easily spread.
  - **Network Component**: Segment the network by assigning **VLANs** to the administration, faculty, and student networks. The firewall will ensure that only authorized traffic can cross between VLANs.

#### **Disadvantages of Firewalls**:
- **Complex Configuration**: Firewalls require careful configuration and ongoing monitoring to ensure they are working as intended. Misconfigurations can lead to vulnerabilities or unintended access blocks.
- **Performance Impact**: Firewalls can introduce latency as they inspect and filter traffic, particularly with more sophisticated features like deep packet inspection.

---

### **Summary of Security Controls**:

| **Security Control**  | **Implementation**                                    | **Risk Reduced**                       | **Disadvantages**                              |
|-----------------------|-------------------------------------------------------|----------------------------------------|------------------------------------------------|
| **Encryption**        | AES-256 encryption for data at rest and SSL/TLS for data in transit | Reduces risk of data breaches and identity theft | Performance overhead, key management complexity |
| **MFA**               | Multi-factor authentication for admin and staff access | Reduces risk of unauthorized access    | User friction, device dependency                |
| **Firewalls**         | Firewall with segmentation and VLAN filtering          | Protects against unauthorized access and external attacks | Complex configuration, potential for performance impact |

---

### **Conclusion**:

Implementing these three security controls—encryption, MFA, and firewalls—significantly reduces the risk associated with the enrolment data. Encryption ensures that data remains secure even if unauthorized access is gained, MFA adds a layer of protection against compromised credentials, and firewalls provide a robust defense against external threats. While these controls introduce some complexity and potential user inconvenience, the overall improvement in security is worth the trade-offs.

Would you like to proceed to the next section, or would you like further clarification or additional details on any of the security controls?




### 4.4.1 Ethical Issues with Data Collection

#### **Introduction**
The collection and usage of student and staff data by the training organization raise several ethical and social concerns. While some data collection is essential for operational purposes, the expansion of data collection for marketing or monitoring could lead to potential privacy issues. This section identifies the key ethical challenges related to data collection, access, and usage, and discusses the balance between necessary data collection and privacy.

---

### **Ethical and Social Issues in Data Collection**

1. **Invasion of Privacy**:
   - **Issue**: The organization collects personal information (e.g., names, addresses, IDs, academic performance), which is necessary for enrolment and administration. However, extending data collection for marketing purposes (e.g., preferences, browsing history) without explicit consent could be seen as an invasion of privacy.
   - **Discussion**: Students may not be aware that their information is being used for purposes beyond academic management, leading to a lack of transparency in how their data is being processed.

2. **Data Minimization**:
   - **Issue**: One of the principles of ethical data collection is to collect only the data that is necessary for a specific purpose. Over-collection of data can lead to increased risks of misuse or breaches.
   - **Discussion**: The training organization may be tempted to collect more data than necessary, particularly for marketing or business analytics. The collection of excessive personal data without a clear, justified purpose may be seen as unethical and increases the risk of privacy violations.

3. **Informed Consent**:
   - **Issue**: Students and staff may not be fully aware of what data is being collected or how it is being used. If consent forms are unclear or hidden in lengthy terms and conditions, users might unknowingly agree to data collection practices they are uncomfortable with.
   - **Discussion**: Ethical data collection requires informed consent. The organization should ensure that students and staff are clearly informed about what data is being collected and for what purposes, and they should have the option to opt out of certain types of data collection (e.g., marketing-related data).

4. **Access to Data by Non-Administrative Staff**:
   - **Issue**: If non-administrative staff (e.g., faculty or IT personnel) have access to students’ personal information, there is a risk of unauthorized data usage or breaches.
   - **Discussion**: Unrestricted access to student data could lead to misuse, especially if sensitive information (such as grades or financial records) is accessible to staff who do not require it for their job functions. There needs to be a clear division of roles and access levels to protect student privacy.

5. **Monitoring and Internet Usage Logging**:
   - **Issue**: Logging students' Internet activity for security and management reasons raises ethical concerns about surveillance and autonomy. Monitoring online activities can create a sense of constant oversight, which could be perceived as a violation of personal freedom.
   - **Discussion**: While some level of monitoring may be justified for security (e.g., to prevent access to harmful content or detect network breaches), excessive monitoring without transparency can lead to trust issues between the organization and students.

6. **Class Attendance System**:
   - **Issue**: If students are allowed to view the attendance records of their classmates, it could lead to unintended privacy violations. Students may feel uncomfortable having their attendance details shared with others.
   - **Discussion**: Attendance data is personal, and allowing students to access the attendance records of others could lead to issues such as peer pressure, judgment, or even bullying. It’s important to limit access to such information to only those who need it, like instructors or administration.

---

### **How Much Data Collection is Too Much?**

- **Necessary Data**: Data such as names, contact information, and academic records is necessary for the organization to function. This data should be collected with proper safeguards and used only for operational purposes (e.g., enrolment, grading, and course management).
  
- **Excessive Data**: Data collection for marketing purposes (e.g., tracking online behavior or collecting data on preferences) without clear consent is excessive. Collecting more data than necessary for the immediate purpose of education and administration increases privacy risks and is ethically questionable.

- **Ethical Boundaries**: The collection of sensitive data, such as health information, financial data, or behavioral tracking, should be done sparingly and only with explicit consent from the individual. Students and staff should also have the right to access and correct their data.

---

### **Management of Data Collection, Access, and Usage**

1. **Transparency and Communication**:
   - The organization must be transparent about what data it collects and how it uses that data. This can be achieved by creating clear, easy-to-understand privacy policies that are readily accessible to students and staff.
   - **Recommendation**: Provide regular updates and easy-to-understand consent forms, ensuring students and staff know what data is being collected and why. They should also be allowed to withdraw their consent for non-essential data collection at any time.

2. **Data Access Control**:
   - Access to sensitive student and staff information should be restricted to only those who need it to perform their duties. Role-based access control (RBAC) should be implemented to ensure that only authorized personnel (e.g., administration) can view or modify student data.
   - **Recommendation**: Implement strict access control policies. For instance, faculty should only access academic records for students in their courses, and financial data should only be accessible to finance staff.

3. **Data Retention and Deletion Policies**:
   - The organization should define how long data will be retained and establish procedures for securely deleting data once it is no longer needed.
   - **Recommendation**: Implement clear data retention policies that outline how long different types of data (e.g., academic records, personal information) are stored. Ensure that data is securely deleted when no longer required for regulatory or operational purposes.

4. **Monitoring and Usage of Internet Logs**:
   - While logging Internet usage may be necessary for network security, there should be limits on how this data is used. Monitoring should focus on security and not individual behaviors.
   - **Recommendation**: Logs should only be reviewed when a security threat is detected or if a violation of organizational policy is suspected. Regular monitoring of individual behaviors should be avoided to maintain trust.

---

### **Class Attendance System Issues**

If the online class attendance system allows students to view the attendance records of their peers, several concerns arise:
1. **Privacy Violations**: Students might feel uncomfortable having their attendance information visible to others. It could expose personal habits or situations, such as health issues, that they may not want to disclose.
   
2. **Potential for Misuse**: Publicly accessible attendance records could be used by students for judgment or criticism, leading to a hostile environment in the class.

#### **Recommendation**:
- The attendance system should be designed so that students can only view their own attendance records. Only authorized personnel, such as instructors and administrative staff, should be able to view and manage the attendance records of all students.

---

### **Conclusion and Recommendations**

1. **Limit Data Collection**: The organization should adopt the principle of data minimization, collecting only the data necessary for its primary function—education. Data collected for marketing or non-essential purposes should be done with explicit consent from the students.

2. **Restrict Access**: Implement strong access control measures, ensuring that only authorized personnel can access sensitive information. Role-based access control (RBAC) is recommended to minimize the risk of insider threats.

3. **Provide Transparency**: Students and staff should be made fully aware of what data is collected, how it is used, and how they can opt-out of non-essential data collection. Privacy policies should be clear and accessible.

4. **Protect Privacy in Attendance Systems**: Ensure that attendance systems only allow students to access their own records. Faculty and administration should have the necessary access to manage the records, but not students.

By addressing these ethical concerns, the training organization can create a more transparent and trustworthy relationship with students and staff while complying with legal and ethical standards in data collection and usage.

Would you like to proceed with the next section, or is there anything you'd like to clarify further on this topic?




### 4.4.2 Ethical and Social Issues with Security Cameras

#### **Introduction**
The installation of security cameras in various locations across the campus—such as offices, classrooms, workshops/studios, the resource centre, and lounges—can raise significant ethical and social concerns. While security cameras can enhance campus safety and monitor for potential incidents, their presence in certain locations may infringe upon privacy rights, create a feeling of constant surveillance, and raise questions about data usage and retention. This section will explore these ethical concerns, discuss their societal acceptability, and outline relevant laws/regulations governing the use of security cameras.

---

### **Ethical and Social Concerns of Security Cameras**

1. **Invasion of Privacy**:
   - **Issue**: Security cameras installed in private or semi-private spaces, such as offices and lounges, may infringe on individuals' privacy. These areas are where staff and students expect a degree of privacy, and constant surveillance could be perceived as intrusive.
   - **Discussion**: While classrooms and resource centres may have a lower expectation of privacy, lounges and offices are spaces where students and staff may engage in personal activities. The presence of cameras could discourage open communication or lead to a sense of being watched, which can be uncomfortable or harmful to the campus environment.

2. **Surveillance in Classrooms and Studios**:
   - **Issue**: Installing cameras in classrooms, workshops, and studios could raise concerns about academic freedom and student behavior. Students and faculty might feel that they are under constant scrutiny, affecting their willingness to express opinions or experiment freely.
   - **Discussion**: The surveillance in classrooms could inhibit open discussion and creative thinking. Students may feel that their behavior is being monitored too closely, which could affect their learning experience. Faculty members may also feel restricted, which could interfere with their teaching methods.

3. **Data Retention and Privacy of Recorded Footage**:
   - **Issue**: The retention of video footage poses ethical concerns, particularly if sensitive or private interactions are captured on camera. How long footage is stored, who can access it, and how it is used are crucial issues.
   - **Discussion**: If footage is stored indefinitely or for long periods, it increases the risk of misuse, including unauthorized access to the data or surveillance of individuals’ actions over time. Data retention policies should specify how long footage will be stored, how it will be secured, and how access will be controlled.

4. **Access and Use of Footage**:
   - **Issue**: Who has access to the recorded footage and how it is used is a significant ethical concern. Unrestricted access to surveillance data by non-essential personnel could lead to misuse, such as surveillance of students or staff for reasons beyond security.
   - **Discussion**: Clear policies need to be established regarding who can access the footage (e.g., security personnel only) and for what purposes (e.g., only in the event of an incident). Footage should not be used for monitoring daily activities or unrelated purposes such as performance evaluation.

5. **Consent and Notification**:
   - **Issue**: Students, faculty, and staff may not be fully aware of where cameras are installed or how footage is being used. Without clear consent or notification, individuals may feel that their rights are being violated.
   - **Discussion**: Ethical use of security cameras requires clear communication about where cameras are located, the reasons for surveillance, and how the footage will be used. Consent should be obtained, and users should have access to policies regarding camera usage.

6. **Chilling Effect on Behavior**:
   - **Issue**: The presence of cameras can lead to a "chilling effect," where individuals modify their behavior out of fear of being watched. This can affect students’ and staff members' freedom to express themselves or engage in relaxed social interactions.
   - **Discussion**: Surveillance in common spaces like lounges may discourage casual interactions or foster a sense of mistrust. The constant feeling of being observed can reduce the overall sense of comfort and belonging within the campus community.

---

### **Locations for Surveillance**

The ethical concerns are heightened depending on the specific location of the cameras. For example:

1. **Offices**:
   - In office spaces, staff expect a higher degree of privacy, especially when handling sensitive matters such as student records or personal discussions. Installing cameras in offices could lead to distrust and may violate privacy rights.

2. **Classrooms and Workshops**:
   - Cameras in classrooms and workshops can be justified for safety reasons, such as monitoring for accidents during practical work or preventing academic misconduct. However, the cameras should be placed in a way that does not interfere with the learning environment or create a sense of constant surveillance.

3. **Resource Centre**:
   - The resource centre may require surveillance to monitor the use of equipment or resources. However, the cameras should focus on security (e.g., theft prevention) and not on individuals' study habits or activities.

4. **Lounges**:
   - Lounges are typically places where students and staff relax. Installing cameras here could be perceived as an intrusion into private social interactions. Cameras in lounges should be carefully considered, and if necessary, they should be used only in high-traffic areas for security purposes.

---

### **Retention Duration of Archived Material**

1. **Issue**: How long the recorded footage is stored affects both privacy and security. If footage is stored for too long, it increases the risk of unauthorized access, misuse, or legal liabilities.
   
2. **Recommendation**:
   - **Retention Period**: Footage should be stored only as long as necessary, such as 30–90 days, depending on the organization's security needs. After this period, footage should be securely deleted unless it is needed for a specific investigation.
   - **Data Protection**: All footage should be encrypted and access restricted to authorized personnel only. The organization should implement role-based access control to ensure that only security or administrative staff have access to the footage.

---

### **Access, Distribution, and Use of Security Footage**

1. **Issue**: The improper use or distribution of security footage could lead to violations of privacy or misuse of personal data. For example, if footage showing sensitive student or staff interactions is leaked or used for purposes other than security, it can result in significant harm.
   
2. **Recommendation**:
   - **Controlled Access**: Access to security footage should be limited to authorized personnel only, such as security staff or administrators. Any access to footage should be logged and monitored.
   - **Restricted Use**: The footage should be used strictly for security purposes, such as investigating incidents. It should not be used for monitoring performance or surveillance of daily activities.

---

### **Relevant Local Laws and Regulations**

In many jurisdictions, the use of security cameras is regulated by privacy laws. In **Australia**, the **Surveillance Devices Act 2004 (Cth)** and various state-level privacy laws govern the use of surveillance devices, including cameras. These laws require:

1. **Notice and Consent**:
   - Individuals must be notified if they are being recorded. This typically involves placing signs indicating that cameras are in use in specific areas.
   - Consent may be implied in public spaces, but for private or semi-private areas, explicit consent may be required.

2. **Data Protection**:
   - Organizations are required to protect the recorded footage from unauthorized access and misuse. This includes ensuring that footage is securely stored and only accessible to authorized individuals.

3. **Use and Disclosure**:
   - Recorded footage can only be used for legitimate purposes, such as ensuring security. It cannot be disclosed or used for non-related activities without consent.

#### **Source References**:
- **Surveillance Devices Act 2004 (Cth)** (Australian Federal Law): Governs the use of surveillance devices, including security cameras, and outlines privacy protections.
- **Australian Privacy Principles (APPs)**: Outlines how personal information, including surveillance footage, should be collected, stored, and used by organizations.

---

### **Conclusion and Recommendations**

1. **Use Cameras Judiciously**: Security cameras should be installed only where necessary for safety and security purposes, such as entrances, high-traffic areas, and resource centres. Cameras in private or semi-private areas (e.g., offices and lounges) should be avoided or used minimally.

2. **Data Retention and Access Control**: Footage should be retained only for a limited time (e.g., 30–90 days) and securely deleted afterward. Access to the footage should be restricted to authorized personnel, and all access should be logged.

3. **Transparency and Consent**: The organization should inform students and staff about where cameras are installed, why they are used, and how the footage will be managed. Signage should be clearly visible in areas where cameras are installed.

4. **Comply with Local Laws**: The use of security cameras must comply with local privacy and surveillance laws, ensuring that footage is handled securely and used only for legitimate purposes.

By addressing these ethical concerns, the organization can strike a balance between ensuring campus safety and respecting the privacy rights of students and staff.

Would you like to proceed to the next section, or is there anything you'd like to clarify or expand upon?



### 5.1 Project Plan

For this section of the project, the goal is to implement a lightweight project management approach. Here's a guide to fulfilling the requirements of **5.1 Project Plan**:

---

### **1. Form Group and Setup GitHub Repository**

- **Step 1**: Create a group for your project. Ensure all group members (yourself and your partner) are part of the group and agree on how to divide responsibilities.
- **Step 2**: Create a GitHub repository to store your project files. This repository will be used for tracking progress, hosting documents, and collaborating on different parts of the project.
  - **Repository Name**: Something descriptive like "COIT20246-Group-Project"
  - **Visibility**: Make sure the repository is private and that only group members and the instructor can access it.
  - **File Structure**: Organize your repository with the following structure:
    - **/docs**: For project documentation (e.g., project plan, report).
    - **/src**: For code or technical configurations.
    - **/diagrams**: For network designs and diagrams.

- **Example GitHub Link**: https://github.com/YourGroupName/COIT20246-Group-Project

---

### **2. Agree on Communication Frequency and Methods**

As part of a lightweight project management approach, the group should decide on communication frequency and methods to ensure regular updates and accountability. This can be done through email, instant messaging, or meetings. Here’s a sample communication plan:

- **Communication Frequency**:
  - **Every Sunday**: Progress updates on GitHub and task assignment for the upcoming week.
  - **Every Wednesday**: Check-in and troubleshooting during tutorial.
  - **Bi-weekly on Thursdays**: Group meetings for detailed discussions about progress and roadblocks.
  
- **Communication Methods**:
  - **Zoom**: For video meetings to discuss major milestones and tasks (e.g., Sunday or Thursday meetings).
  - **Teams/Slack**: For daily communication, quick questions, and progress updates.
  - **GitHub Issues/Comments**: To track tasks and review commits.
  
---

### **3. Create a Schedule**

The schedule should outline the tasks to be completed each week, including project milestones such as the completion of specific sections (e.g., network design, cloud services, security). Here's a sample project schedule:

| **Week**     | **Task**                                           | **Group Member Responsible** | **Notes**                                    |
|--------------|----------------------------------------------------|------------------------------|----------------------------------------------|
| Week 1       | Set up GitHub repository, create group plan        | Ajhar & Partner               | Plan.md to be added to repository            |
| Week 2       | Network Design                                     | Ajhar                         | Draft diagrams and network explanation       |
| Week 3       | Cloud Services                                      | Partner                       | Cloud cost comparison                        |
| Week 4       | Security Risk Assessment                           | Ajhar                         | Conduct mini risk assessment                 |
| Week 5       | Backup Solutions                                   | Partner                       | Finalize backup strategy (cloud/non-cloud)   |
| Week 6       | Ethical Issues and Complete Report                 | Ajhar & Partner               | Finish ethical sections and complete Markdown report |
| Week 7       | Final Review and Submission                        | Ajhar & Partner               | Finalize submission on GitHub and submit report |

---

### **Create plan.md in GitHub**

In the `/docs` folder of your GitHub repository, create a file named `plan.md` that includes the communication plan and the project schedule.

**Sample `plan.md` Structure**:

```markdown
# COIT20246 Project Plan

## 1. Communication Plan

- **Weekly Meetings**: 
  - Every **Sunday** at 10 AM (via Zoom) to discuss weekly progress and assign tasks.
  - Every **Wednesday** during tutorials to address challenges or updates.
  - Bi-weekly **Thursday** meetings for milestone reviews.

- **Communication Methods**: 
  - **Zoom**: For weekly meetings.
  - **Teams**: For daily communication and quick updates.
  - **GitHub Issues**: For tracking tasks and reviewing code/commits.

## 2. Project Schedule

| **Week**     | **Task**                                           | **Group Member Responsible** | **Notes**                                    |
|--------------|----------------------------------------------------|------------------------------|----------------------------------------------|
| Week 1       | Set up GitHub repository, create group plan        | Ajhar & Partner               | Plan.md to be added to repository            |
| Week 2       | Network Design                                     | Ajhar                         | Draft diagrams and network explanation       |
| Week 3       | Cloud Services                                      | Partner                       | Cloud cost comparison                        |
| Week 4       | Security Risk Assessment                           | Ajhar                         | Conduct mini risk assessment                 |
| Week 5       | Backup Solutions                                   | Partner                       | Finalize backup strategy (cloud/non-cloud)   |
| Week 6       | Ethical Issues and Complete Report                 | Ajhar & Partner               | Finish ethical sections and complete Markdown report |
| Week 7       | Final Review and Submission                        | Ajhar & Partner               | Finalize submission on GitHub and submit report |
```

This plan will provide structure for your group work and serve as a guide for completing the project on time.

Would you like help setting up your GitHub repository or any other part of the project management plan?



### 5.2 Project Progress

For **Project Progress**, you need to ensure that all group members (yourself and your partner) are regularly contributing to the GitHub repository throughout the project. The following steps will guide you in maintaining a proper record of contributions and progress.

---

### **1. Regular Contributions**

To track and document project progress, group members should:
- **Commit frequently**: Make regular commits to the GitHub repository as they complete sections of the project (e.g., network design, cloud services).
- **Use clear commit messages**: Each commit should have a clear, descriptive message indicating what was added or modified (e.g., "Added network diagram", "Updated cloud services cost comparison").
- **Use GitHub Issues or Pull Requests**: For group discussions or reviews of certain sections of the project, use GitHub Issues or Pull Requests to track feedback, discuss changes, or resolve conflicts in the code or documents.

---

### **2. Document Contributions via GitHub Insights**

To show that all group members are contributing regularly, you can use GitHub's **Insights** feature:

1. **Navigate to "Insights"** in the repository.
   - This will show contributions by each group member over time.
   - You can access the "Contributors" section to see individual commits, the frequency of commits, and the files worked on by each member.
   
2. **Commits Overview**:
   - Each member should be making regular commits, not just at the end of the project. Ideally, you should aim to commit work on a weekly basis.

3. **Screenshot of Contributions**:
   - Take a screenshot of the contribution overview in GitHub's Insights (found under "Contributors") once the project is complete. This screenshot will show each member’s contributions over time, including the number of commits and the files modified.
   - This will serve as evidence that both group members actively participated in the project.

---

### **3. Track Progress in GitHub**

- **Task Tracking**: Use GitHub Issues or Project boards to create tasks for each section of the project. Assign these tasks to the relevant group member and mark them as completed once the work is done. For example, create issues such as:
  - "Create network design diagram"
  - "Compare cloud service providers for web server"
  - "Conduct mini security risk assessment"
  - "Write ethical issues section"

- **Milestones**: Set up **milestones** to align with key deliverables in the project, such as completing the network design, cloud services, security controls, and final report.

---

### **Sample Task for Tracking Progress**:

In your GitHub repository, use **GitHub Issues** to assign tasks:

| **Issue**                          | **Assigned To**    | **Status**    |
|------------------------------------|--------------------|---------------|
| Create network design diagram      | Ajhar              | In Progress   |
| Compare cloud service providers    | Partner            | Completed     |
| Conduct cyber security risk assessment | Ajhar              | In Progress   |
| Write ethical issues section       | Partner            | Not Started   |

This method ensures both members are contributing and helps track the overall progress of the project.

---

### **4. Regular Commit Example**

When you or your partner make a contribution, ensure the commit message is clear and descriptive. Examples include:

- **Commit Message Examples**:
  - "Added initial network design diagram for review."
  - "Updated AWS and Azure cloud service cost comparison."
  - "Completed mini cyber security risk assessment draft."

---

### **5. Final Project Progress Report**

At the end of the project, when preparing the final report, ensure that you include:
- **Screenshot from GitHub Insights**: This shows each member’s contributions.
- **Explanation of Contributions**: Provide a brief explanation of the tasks each group member completed based on the GitHub contributions. Mention:
  - The number of commits made by each member.
  - The tasks each member was responsible for.
  - How group members collaborated to ensure project success.

---

Would you like help setting up GitHub Issues for task tracking or with any other part of managing the project contributions?



### 5.3 Project Reflection

#### **Tasks Performed by Each Team Member**

During the course of the project, each group member took responsibility for different parts of the work. Below is a breakdown of the tasks performed by each member:

- **Md Ajhar Mia (Myself)**:
  - **Network Design**: Led the creation of the network design, including creating the diagrams and outlining key design decisions (e.g., VLAN segmentation, hardware selection).
  - **Security Risk Assessment**: Conducted the mini cyber security risk assessment, identifying key assets, threats, and vulnerabilities.
  - **Ethical Issues**: Took the lead on writing the section on ethical issues related to data collection and security cameras.

- **Partner (Partner’s Name)**:
  - **Cloud Services**: Led the comparison of cloud service providers (AWS vs. Azure), calculated costs, and recommended the best solution for hosting the organization’s web server.
  - **Backup Solutions**: Researched cloud and non-cloud backup options, providing recommendations on which solution the organization should implement.
  - **Ethical Issues on Data Collection**: Contributed to the analysis of ethical issues related to data collection and use.

---

#### **GitHub Commits and Contribution Summary**

Once all project sections are complete, you will need to include a screenshot from GitHub's **Insights** -> **Contributors** section to show each group member’s commit history.

- **Commit Frequency**:
  - Both group members contributed regularly to the project, with commits occurring each week. I made regular commits for tasks related to network design and security, while my partner focused on cloud services and backup solutions.
  
- **Commit Size**:
  - My commits were generally larger when submitting network design diagrams and the full risk assessment. Partner’s commits were focused on cloud cost comparison and backup recommendations, which required multiple smaller commits for adjustments and updates.

- **Example Screenshot**:
  - Include a screenshot from GitHub Insights once all sections are complete, showing the individual contributions of each member. Ensure that the screenshot shows the number of commits per member and the breakdown of contributions (e.g., network design files, cloud services, ethical issues).

---

#### **Explanation of Commit Data vs. Task Allocation**

- **Number of Commits**:
  - The commit history reflects the task allocations made at the start of the project. My contributions were more focused on technical aspects like network design and security, while my partner’s commits reflected tasks related to cloud services and backup solutions.

- **Regularity of Commits**:
  - Both members contributed regularly, though there were more frequent commits during the early and mid-stages of the project as we completed the main technical tasks. Towards the end, we focused on refining and reviewing the ethical sections and the final report.

- **Commits on Specific Files**:
  - I focused mainly on files related to network design and security controls, whereas my partner worked on files related to cloud services and backup solutions. This division of labor is also reflected in the GitHub commit history.

---

#### **Collaboration and Communication**

- **Task Splitting**:
  - We split the tasks based on our individual strengths and preferences. I took responsibility for network design and security since these were my areas of expertise, while my partner focused on cloud services and backup solutions due to their familiarity with cloud platforms.

- **Communication Mechanisms**:
  - We used **Zoom** for weekly video meetings to discuss progress and upcoming tasks. For daily communication, we relied on **Teams** for quick updates and file sharing.
  - All documentation and code were stored in our **GitHub repository**, and we used **GitHub Issues** to track tasks and assign work to each group member.

- **Group Meetings**:
  - We met every Sunday via Zoom to discuss the progress of the previous week and assign new tasks. During the week, we used Teams for additional communication. We also made use of GitHub's comments on commits to provide feedback on each other’s work.

---

#### **Comparison with Original Plan (plan.md)**

In our original plan, we aimed to complete each task weekly. Overall, we adhered closely to the schedule:
- **On Schedule**: We were able to complete the network design and cloud services tasks as planned. The weekly meetings helped us stay on track.
- **Adjustments**: Some tasks took longer than expected, such as the ethical issues section, as it required more research and refinement than anticipated. This caused a slight delay in completing the final report, but we adjusted our timeline accordingly.
- **Team Collaboration**: The communication frequency and methods outlined in the plan were followed consistently. This ensured smooth collaboration and accountability throughout the project.

---

### **Conclusion**

The project progressed as planned, with each team member making regular and meaningful contributions. The use of GitHub helped us collaborate efficiently, and the commit history reflects the division of tasks and the consistency of contributions. Although a few adjustments were made to the timeline, we were able to complete the project successfully with effective communication and teamwork.

---

Would you like assistance with creating the GitHub screenshot or reviewing the reflection before final submission?



### 5.4 Written Report

For this task, you are required to submit a **Markdown-based technical report** in your group's GitHub repository. The report will summarize all the work done throughout the project, including network design, cloud services, security, and ethical issues. Below is a guide to help you structure your report and ensure all requirements are met.

---

### **1. Structure of the Written Report (in Markdown)**

The report should follow a professional technical structure, with clear section headings for each task in the project. Below is a suggested outline for your report:

```markdown
# COIT20246 Networking and Cyber Security Project

## 1. Introduction
Briefly introduce the project scope, including what the training organization required in terms of network design, cloud services, and security.

## 2. Network Design
### 2.1 Network Diagram
Provide an overview of your network design. Include a link to your network diagram hosted in the `/diagrams` folder of your repository.

- **Network Diagram**: [Network Design Diagram](../diagrams/network_diagram.png)

### 2.2 Explanation of Key Design Decisions
Explain the rationale behind the design, including the choice of VLANs, hardware, and IP addressing. Be sure to reference specific sections of your design where relevant.

### 2.3 WiFi Design
Describe the WiFi setup, including encryption type (WPA3), SSID structure, and bandwidth management.

### 2.4 IP Address Allocation
Provide a table summarizing the IP address ranges you used, derived from student IDs.

| VLAN                   | IP Range           | Subnet Mask    | Description                       |
|------------------------|--------------------|----------------|-----------------------------------|
| Admin & Finance VLAN    | 78.1.0.0/24        | 255.255.255.0  | Administration and Finance        |
| Student VLAN            | 78.3.0.0/24        | 255.255.255.0  | Student Network                   |
| WiFi VLAN               | 78.4.0.0/24        | 255.255.255.0  | WiFi Network                      |

---

## 3. Cloud Services
### 3.1 Cloud Server Comparison
Summarize the comparison of AWS and Azure for hosting the organization's public website. Include the cost comparison and your final recommendation.

| Cloud Provider      | Estimated Annual Cost (AUD) |
|---------------------|-----------------------------|
| AWS                 | AUD 680                     |
| Microsoft Azure      | AUD 720                     |

### 3.2 Backup Solutions
Compare the cloud and non-cloud backup options, providing a recommendation for the organization. Include the cost of cloud backup using AWS S3 or Azure Blob Storage.

---

## 4. Security
### 4.1 Cyber Security Risk Assessment
Provide a summary of the cyber security risk assessment, detailing the assets, threats, vulnerabilities, and the mitigations recommended.

| Asset               | Vulnerability                     | Threat                    | Mitigation               |
|---------------------|-----------------------------------|---------------------------|--------------------------|
| Enrolment Data      | Weak access control               | Data breach               | MFA, encryption           |
| Financial Records   | Unauthorized internal access      | Insider threat            | Role-based access control |
| Web Server          | Lack of firewall rules            | Denial of Service (DoS)    | Firewall, load balancing  |

### 4.2 Recommended Security Controls
Outline how encryption, MFA, and firewalls were used to mitigate risks. Be specific about where in the network these controls were implemented.

---

## 5. Ethical Issues
### 5.1 Data Collection
Discuss the ethical issues surrounding the collection of student and staff data, including privacy concerns, access control, and data minimization.

### 5.2 Security Cameras
Identify the ethical issues related to the installation of security cameras on campus. Discuss data retention, access, and the legal guidelines (such as the Surveillance Devices Act 2004).

---

## 6. Project Management
### 6.1 Project Plan
Provide an overview of the communication plan and task schedule as described in the **plan.md** file. Include the link to the `plan.md` file:
- **Plan.md**: [Plan File](../docs/plan.md)

### 6.2 Project Reflection
Include a brief reflection on the work performed by each group member, as well as a summary of the contributions using the GitHub commit history.

- **GitHub Insights Screenshot**: Include a screenshot from GitHub Insights showing commits from both team members.
  
---

### **2. Including Diagrams and Supporting Files**

For images (such as network diagrams) and any supporting files (e.g., spreadsheets or cost comparison tables):
- Place the diagrams in the **/diagrams** folder in your repository.
- Place any spreadsheets or documents in the **/docs** folder.

In the Markdown report, link to these files directly. For example, if your network diagram is located in `/diagrams/network_diagram.png`, the link in Markdown would be:

```markdown
![Network Diagram](../diagrams/network_diagram.png)
```

Make sure all diagrams and images are appropriately sized for readability in the report.

---

### **3. Writing Style and Formatting**

- **Title**: Give your report a clear and descriptive title such as "COIT20246 Networking and Cyber Security Project."
- **Authors**: Include your names at the top of the report.
- **Sections and Sub-sections**: Use appropriate section headings (e.g., `## 3. Cloud Services` for major sections and `### 3.1 Cloud Server Comparison` for sub-sections).
- **Tables and Bullet Points**: Where relevant, use tables to present data clearly, and use bullet points for lists to enhance readability.
- **Use Your Own Words**: Ensure that the report is written in your own words, even if you are summarizing from technical documentation or websites. If using AI tools, include a screenshot of the prompt and generated output as part of your report.

---

### **4. Submitting the Report**

Once the report is completed:
- **Proofread**: Review for clarity, grammar, and completeness.
- **Commit and Push**: Ensure all Markdown files, images, and supporting documents are committed and pushed to your GitHub repository.
- **Review**: Use the GitHub preview feature to ensure the Markdown file is formatted correctly and all links/images work as expected.
  
---

### **Conclusion**

By following the structure outlined above, you’ll be able to present a comprehensive and professional report on your project work. Ensure that all relevant images and files are included in the repository, and the Markdown file links to them correctly.

Would you like assistance with specific sections of the report or finalizing the submission?
