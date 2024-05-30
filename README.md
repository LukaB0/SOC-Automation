# SOC Automation Project

## Objective

This SOC Automation Project aimed to gain hands-on experience setting up a controlled environment for simualting and detecting cyber attacks. The primary focus was to streamline incident response processes and enhance threat detection capabilities through the implementation of automated workflows and tools. This initiative aims to reduce manual intervention, increase efficiency, and bolster the overall security posture of digital assets.

### Skills Learned

- Virtualization setup and management: Understanding of virtualization platforms like VirtualBox, including creating and managing virtual machines, networks, and snapshots.
  
- Network architecture design: Knowledge of network protocols, segmentation, and routing to design a lab network that mirrors production environments, ensuring realistic testing scenarios.

- Scripting for automation (Python, PowerShell, etc.): Proficiency in scripting languages to automate repetitive tasks, such as deploying and configuring security tools, managing logs, and executing response actions.

- Configuration of security tools (SIEM, IDS/IPS, EDR): Ability to configure and customize security tools for optimal performance, including tuning alert thresholds, defining correlation rules, and integrating with other systems.
  
- Security policy configuration: Understanding of security policies and best practices to configure access controls, encryption, authentication mechanisms, and other security settings to protect lab resources.

- Collaboration and documentation skills: Ability to communicate effectively with team members and stakeholders, as well as document lab setup procedures, configurations, and troubleshooting steps for future reference.

### Tools Used

- Draw.io for designing the topology for the SOC Automation Project.
  
- Virtual Box for installing Windows 10.

- Sysmon for enhancing security monitoring and incident response capabilites.
  
- Digital Ocean for setting up the cloud servers for Wazuh and TheHive. 

- Wazuh for SIEM capabilities.

- TheHive for the aggregation of security alerts on a collaborative platform.

- Shuffler.io for streamling workflows and automating security operations.

- SOAR for the integration of security tools and orchestrating response actions.

- VirusTotal for analysis of suspicious files or URLS.

## Steps

### 1: Topology Design
Designing a topology for a SOC Autoamtion Project is the initial step, enabling understanding of requirements, effective resource allocation, risk mitigation, integration planning, and provision of a testing environment.

![SOC Automation Diagram2 drawio](https://github.com/LukaB0/SOC-Automation/assets/169913850/0de526bd-0818-484b-acd4-45b9daadd196)

It establishes the foundation for an efficiently deployed and strategically aligned security environment, ensuring scalability and flexibility to address evolving needs.
 
### 2: Components Installation

#### Windows 10 & Sysmon

Setting up Windows 10 on a VirtualBox machine begins with creating a virtual environment and installing the Windows 10 operating system. Once Windows 10 is running, installing Sysmon enhances security by providing advanced monitoring and logging capabilities, aiding in the detection of malicious activities and threats within the virtualized environment.

#### Wazuh

Deploying a Wazuh server on DigitalOcean involves provisioning a cloud instance, selecting appropriate specifications, and installing the Wazuh manager software. Configuration includes setting up necessary firewall rules and network access controls, ensuring secure communication with monitored endpoints. Once configured, the Wazuh server provides centralized security monitoring, log analysis, and threat detection capabilities for the cloud environment, enhancing overall security posture and incident response readiness.

![Firewall Rules](https://github.com/LukaB0/SOC-Automation/assets/169913850/60800287-0d7d-4f3c-a783-0da85f7723f4)

![Adding Servers to Firewall](https://github.com/LukaB0/SOC-Automation/assets/169913850/abdba46f-0489-4d16-9d35-1b24d80a7f50)

### TheHive

Setting up TheHive on DigitalOcean entails provisioning a cloud instance, selecting suitable specifications, and installing TheHive platform. Configuration involves securing access with strong authentication measures and configuring integration with other security tools for enhanced incident response capabilities. Once deployed, TheHive serves as a centralized platform for case management, collaboration, and automated response actions, streamlining security operations and improving incident resolution efficiency within the cloud environment.

### 3: Servers & Endpoints Configurations

#### Wazuh



#### TheHive



### 4: Telemtry Generation

Generating telemetry on a Windows 10 machine involves enabling logging features such as Windows Event Logs and Sysmon to capture security-relevant events. Configuring Wazuh agents on the Windows 10 machine ensures that this telemetry data is collected, encrypted, and securely transmitted to the Wazuh server for analysis and correlation. By ingesting this telemetry data, Wazuh provides real-time visibility into security events on the Windows 10 machine, facilitating threat detection and incident response within the monitored environment.

#### Windows 10

![ossec configuration](https://github.com/LukaB0/SOC-Automation/assets/169913850/12519805-f48a-476f-9c0d-9c2e7fd95851)

![og mimikatz filename](https://github.com/LukaB0/SOC-Automation/assets/169913850/c255b524-526e-4569-934d-afe742b22b3c)

#### Wazuh

![Wazuh Dashboard](https://github.com/LukaB0/SOC-Automation/assets/169913850/edd0f5db-71bf-4506-8529-197bcdc1c1ee)

![Custom Rule](https://github.com/LukaB0/SOC-Automation/assets/169913850/5b04f3fb-5cc5-4d58-82e6-262360e4692a)

![Mimikatz Detection](https://github.com/LukaB0/SOC-Automation/assets/169913850/04303769-a13d-42ed-b3d7-eaadeb9b856b)

#### TheHive

![TheHive ORG](https://github.com/LukaB0/SOC-Automation/assets/169913850/192bbb12-a17c-42c6-8ec9-67196c9336aa)

#### Rule Creation

### 5: SOAR Setup & Full Integration

Creating a workflow on Shuffler involves configuring integration between a SOAR (Security Orchestration, Automation, and Response) platform and TheHive. This entails defining trigger conditions in Shuffler to initiate actions based on specific events detected by TheHive. By linking these platforms, security teams can automate incident response processes, streamline case management, and orchestrate remediation actions efficiently, enhancing overall security operations and reducing response times.

![Shuffler and SOAR](https://github.com/LukaB0/SOC-Automation/assets/169913850/6ddd4a24-9f21-4b34-9606-e572e9eaa31d)

![Shuffle Wazuh Conf](https://github.com/LukaB0/SOC-Automation/assets/169913850/b082d652-ce79-4284-8d4b-7175a882a1b0)

![Virustotal Hash Report conf](https://github.com/LukaB0/SOC-Automation/assets/169913850/fac500cc-c031-42f5-8214-b0c1011d8f3c)

![Email Conf](https://github.com/LukaB0/SOC-Automation/assets/169913850/07fc2de6-abc4-4a74-9df7-7cd150e724dd)

![Email Notificaiton](https://github.com/LukaB0/SOC-Automation/assets/169913850/83d646ec-a8ca-4cdf-982d-b9a2c2e29961)


drag & drop screenshots here or use imgur and reference them using imgsrc

Every screenshot should have some text explaining what the screenshot is about.

Example below.

*Ref 1: Network Diagram*
