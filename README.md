# SOC Automation Project

## Objective

This SOC Automation Project aimed to gain hands-on experience setting up a controlled environment for simualting and detecting cyber attacks. The primary focus was to streamline incident response processes and enhance threat detection capabilities through the implementation of automated workflows and tools. This initiative aims to reduce manual intervention, increase efficiency, and bolster the overall security posture of digital assets.

### Skills Learned

- Virtualization setup and management: Understanding of virtualization platforms like VirtualBox, including creating and managing virtual machines and networks.
  
- Network architecture design: Knowledge of network protocols, segmentation, and routing to design a lab network that mirrors production environments, ensuring realistic testing scenarios.

- Scripting for automation (Python, PowerShell, etc.): Proficiency in scripting languages to automate repetitive tasks, such as deploying and configuring security tools, managing logs, and executing response actions.

- Configuration of security tools (SIEM, IDS/IPS, EDR): Ability to configure and customize security tools for optimal performance, including tuning alert thresholds, defining correlation rules, and integrating with other systems.
  
- Security policy configuration: Understanding of security policies and best practices to configure access controls, encryption, authentication mechanisms, and other security settings to protect lab resources.

- Documentation skills: Ability to document lab setup procedures, configurations, and troubleshooting steps for future reference.

### Tools Used

- Draw.io for designing the topology for the SOC Automation Project.
  
- Virtual Box for installing Windows 10.

- Sysmon for enhancing security monitoring and incident response capabilites.
  
- Digital Ocean for setting up the cloud servers for Wazuh and TheHive. 

- Wazuh for SIEM capabilities.

- TheHive for the aggregation of security alerts on a collaborative platform.

- Shuffle for streamling workflows and automating security operations.

- SOAR for the integration of security tools and orchestrating response actions.

- VirusTotal for analysis of suspicious files or URLs.

## Steps

### 1: Topology Design
Designing a topology for a SOC Autoamtion Project is the initial step, enabling understanding of requirements, effective resource allocation, risk mitigation, integration planning, and provision of a testing environment.

![SOC Automation Diagram2 drawio](https://github.com/LukaB0/SOC-Automation/assets/169913850/0de526bd-0818-484b-acd4-45b9daadd196)
*Ref 1: SOC Automation Diagram*

It establishes the foundation for an efficiently deployed and strategically aligned security environment, ensuring scalability and flexibility to address evolving needs.
 
### 2: Components Installation

#### Windows 10 & Sysmon

First Windows 10 was installed on a virtual machine. After it was set up, sysmon was installed for advanced monitoring and logging capabilities, aiding in the detection of malicious activities and threats within the virtualized environment.

#### Wazuh

Digital Ocean's cloud instance was used to deploy a Wazuh server. After selecting the appropriate specifications and installing the software, it was vital to configure the firewall to only allow access from the specified Windows 10 virtual machine. Once configured, the Wazuh server provides centralized security monitoring, log analysis, and threat detection capabilities for the cloud environment, enhancing overall security posture and incident response readiness.

#### TheHive

Digital Ocean's cloud services were used for TheHive server as well. Once deployed, TheHive serves as a centralized platform for case management, collaboration, and automated response actions, streamlining security operations and improving incident resolution efficiency within the cloud environment. TheHive server was also added to the firewall rules below.

#### Firewall

Rules were added to allow TCP and UDP traffic from a speicified IP address through port 9000.
![Firewall Rules](https://github.com/LukaB0/SOC-Automation/assets/169913850/6d66d7ce-042b-4eb0-96dc-b90d13512494)
*Ref 2: Firewall Rules*

Below shows the two cloud servers added to the firewall.
![Adding Servers to Firewall](https://github.com/LukaB0/SOC-Automation/assets/169913850/dd0c3881-0a10-4fd4-aba2-7d04a05a82b2)
*Ref 3: Adding Servers to Firewall*

### 3: Servers & Endpoints Configurations

#### Wazuh



#### TheHive



### 4: Telemtry Generation

Generating telemetry on a Windows 10 machine involves enabling logging features such as Windows Event Logs and Sysmon to capture security-relevant events. Configuring Wazuh agents on the Windows 10 machine ensures that this telemetry data is collected, encrypted, and securely transmitted to the Wazuh server for analysis and correlation. By ingesting this telemetry data, Wazuh provides real-time visibility into security events on the Windows 10 machine, facilitating threat detection and incident response within the monitored environment.

#### Windows 10

![ossec configuration](https://github.com/LukaB0/SOC-Automation/assets/169913850/12519805-f48a-476f-9c0d-9c2e7fd95851)
*Ref 4: ossec configuration*

#### Wazuh

The Wazuh Dashboard below shows the number of alerts and potential type of attack 
![Wazuh Dashboard](https://github.com/LukaB0/SOC-Automation/assets/169913850/edd0f5db-71bf-4506-8529-197bcdc1c1ee)
*Ref 5: Wazuh Dashboard*

![Custom Rule](https://github.com/LukaB0/SOC-Automation/assets/169913850/5b04f3fb-5cc5-4d58-82e6-262360e4692a)
*Ref 6: Custom Rule*

#### TheHive

![TheHive ORG](https://github.com/LukaB0/SOC-Automation/assets/169913850/192bbb12-a17c-42c6-8ec9-67196c9336aa)
*Ref 7: TheHive Org*

#### Rule Creation

To ensure that mimikatz would still be detected even if the filename is changed a rule was created to detect the original filename.

![og mimikatz filename](https://github.com/LukaB0/SOC-Automation/assets/169913850/c255b524-526e-4569-934d-afe742b22b3c)
*Ref 8: Original Filename Rule*

The screenshot below shows the alert in Wazuh as a Mimikatz detection.

![Mimikatz Detection](https://github.com/LukaB0/SOC-Automation/assets/169913850/24709c52-b2bc-4c27-a84d-125631d2bcf3)
*Ref 9: Mimikatz Detection*

### 5: SOAR Setup & Full Integration

Creating a workflow on Shuffle involves configuring integration between a SOAR (Security Orchestration, Automation, and Response) platform and TheHive. This entails defining trigger conditions in Shuffler to initiate actions based on specific events detected by TheHive. By linking these platforms, security teams can automate incident response processes, streamline case management, and orchestrate remediation actions efficiently, enhancing overall security operations and reducing response times.

![Shuffler and SOAR](https://github.com/LukaB0/SOC-Automation/assets/169913850/6ddd4a24-9f21-4b34-9606-e572e9eaa31d)
*Ref 10: Shuffle Workflow*

![Shuffle Wazuh Conf](https://github.com/LukaB0/SOC-Automation/assets/169913850/b082d652-ce79-4284-8d4b-7175a882a1b0)
*Ref 11: Shuffle Wazuh Configuration*

![Virustotal Hash Report conf](https://github.com/LukaB0/SOC-Automation/assets/169913850/fac500cc-c031-42f5-8214-b0c1011d8f3c)
*Ref 12: Virustotal Hash Report Configuration*

![Email Conf](https://github.com/LukaB0/SOC-Automation/assets/169913850/07fc2de6-abc4-4a74-9df7-7cd150e724dd)
*Ref 13: Email Configuration*

![Email Notificaiton](https://github.com/LukaB0/SOC-Automation/assets/169913850/83d646ec-a8ca-4cdf-982d-b9a2c2e29961)
*Ref 14: Email Notification*

## Conclusion & Future Thoughts

I had a lot of fun with this project. I had previously encountered the Wazuh and TheHive tools through my training with TryHackMe so it was fun to see behind the scenes on how these services actually get set up to be used in SOC environment. It was really fun configuring the custom rules to specifically detect Mimikatz usage on the Windows 10 machine. However, I would have to say my favorite part was automating all of the tools to work together seamlessly. It was satisfying to see the email notification pop up in my inbox, alerting me of the attack. What I found very useful was integrating VirusTotal within the SOAR instance to pull its own report of the file's hash.

In the future I would like to add some more rules to catch different types of attack tools used by threat actors. Also, I would like to try some attacks myself on the machine such as bruteforcing to see if that would be picked up as well.
