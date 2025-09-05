# Network Intrusion Detection Lab

## Overview

A comprehensive cybersecurity lab environment simulating real-world corporate network infrastructure, phishing attacks, lateral movement, and incident response scenarios. This lab demonstrates enterprise-level security monitoring and threat detection capabilities using modern SIEM technologies and vulnerability assessment tools.

## Lab Architecture

### Network Topology
- **Virtualization Platform**: Oracle VirtualBox with NAT Network
- **Network Range**: 10.0.0.0/24 (10.0.0.1 - 10.0.0.254)
- **DHCP Scope**: 10.0.0.100 - 10.0.0.200
- **Network Name**: project-x-nat

### Infrastructure Components

| Hostname | IP Address | Role | Operating System |
|----------|------------|------|------------------|
| project-x-dc | 10.0.0.5 | Domain Controller | Windows Server 2025 |
| project-x-admin | 10.0.0.8 | Corporate Server | Ubuntu Server 22.04 |
| project-x-sec-box | 10.0.0.10 | Security Server | Ubuntu Desktop 22.04 |
| project-x-win-client | 10.0.0.100 (DHCP) | Windows Workstation | Windows 11 Enterprise |
| project-x-linux-client | 10.0.0.101 (DHCP) | Linux Workstation | Ubuntu Desktop 22.04 |
| project-x-sec-work | 10.0.0.103 (DHCP) | Security Playground | Security Onion |
| project-x-attacker | Dynamic | Attack Platform | Kali Linux 2024.4 |

## Technology Stack

### Security & Monitoring
- **SIEM Platform**: Wazuh (centralized security monitoring and incident response)
- **Network Monitoring**: Security Onion (intrusion detection and log analysis)
- **Domain Services**: Microsoft Active Directory (identity management and authentication)
- **Email Testing**: MailHog (SMTP capture for phishing simulation)

### Attack Simulation Tools
- **Remote Access**: Evil-WinRM (Windows Remote Management exploitation)
- **Password Attacks**: Hydra (brute-force and dictionary attacks)
- **Wordlists**: SecLists (comprehensive penetration testing resources)
- **Network Exploitation**: NetExec (lateral movement and privilege escalation)
- **Remote Desktop**: XFreeRDP (RDP connections for post-exploitation)

## Lab Scenarios

### 1. Initial Access Simulation
- **Phishing Campaign**: Credential harvesting via fake web portal
- **Social Engineering**: Multi-vector attack simulation
- **Payload Delivery**: PowerShell reverse shell deployment

### 2. Lateral Movement & Persistence
- **Network Reconnaissance**: Host discovery and service enumeration
- **Privilege Escalation**: Local and domain-level privilege abuse
- **Persistence Mechanisms**: Maintaining access across reboots

### 3. Detection & Response
- **Real-time Monitoring**: Wazuh agent deployment and log correlation
- **Incident Investigation**: Security Onion packet analysis
- **Threat Hunting**: Proactive security monitoring techniques

## System Requirements

### Virtual Machine Specifications
| VM | CPU Cores | RAM | Storage | Purpose |
|----|-----------|-----|---------|---------|
| Domain Controller | 2 | 4 GB | 50 GB | Windows Server 2025 |
| Windows Client | 2 | 4 GB | 80 GB | Windows 11 Enterprise |
| Linux Client | 1 | 2 GB | 80 GB | Ubuntu Desktop 22.04 |
| Security Workstation | 1 | 2 GB | 55 GB | Security Onion |
| Security Server | 2 | 4 GB | 80 GB | Ubuntu Desktop 22.04 |
| Corporate Server | 1 | 2 GB | 25 GB | Ubuntu Server 22.04 |
| Attacker Machine | 1 | 2 GB | 55 GB | Kali Linux 2024.4 |

### Host System Requirements
- **Minimum**: 16 GB RAM, 8-core CPU, 500 GB available storage
- **Recommended**: 32 GB RAM, 12+ core CPU, 1 TB SSD storage
- **Hypervisor**: VirtualBox 7.0+ or VMware Workstation Pro

## Installation & Setup

### 1. ISO Downloads
Required operating system images:
- Windows Server 2025 (Microsoft Evaluation Center)
- Windows 11 Enterprise (Microsoft Evaluation Center)
- Ubuntu Desktop/Server 22.04 LTS
- Security Onion (latest stable release)
- Kali Linux 2024.4

### 2. VM Deployment Order
1. **Domain Controller** (Windows Server 2025)
2. **Windows Client** (Windows 11 Enterprise)
3. **Linux Workstations** (Ubuntu Desktop)
4. **Security Infrastructure** (Security Onion, Wazuh Server)
5. **Attack Platform** (Kali Linux)

## Key Learning Objectives

### Network Security Fundamentals
- **Network Segmentation**: VLAN configuration and micro-segmentation
- **Access Control**: Role-based permissions and least privilege
- **Monitoring**: Real-time threat detection and log analysis

### Incident Response Workflow
- **Detection**: Automated alerting and anomaly detection
- **Analysis**: Forensic investigation and root cause analysis
- **Containment**: Threat isolation and damage limitation
- **Recovery**: System restoration and lessons learned

### Compliance & Standards
- **Framework Alignment**: NIST Cybersecurity Framework implementation
- **Log Management**: Centralized logging and retention policies
- **Documentation**: Incident response playbooks and procedures

## Attack Simulation Exercises

### Exercise 1: Credential Harvesting
- Deploy phishing website with credential capture
- Simulate user interaction and credential submission
- Monitor detection capabilities and response timing

### Exercise 2: Network Reconnaissance
- Perform network scanning and service enumeration
- Test network segmentation and access controls
- Evaluate monitoring and alerting effectiveness

### Exercise 3: Lateral Movement
- Exploit compromised credentials for system access
- Attempt privilege escalation and persistence
- Assess detection and containment capabilities

## Real-World Applications

### Enterprise Security Operations
- **SOC Analyst Training**: Hands-on experience with enterprise SIEM platforms
- **Incident Response**: Practical application of cybersecurity frameworks
- **Threat Hunting**: Proactive security monitoring techniques

### Compliance & Audit Preparation
- **Security Controls**: Implementation of industry-standard security measures
- **Documentation**: Comprehensive logging and audit trail maintenance
- **Risk Assessment**: Vulnerability identification and remediation planning

## Documentation & Resources

### Reference Materials
- **ProjectSecurity.io Course**: [Enterprise 101 - E101 Overview](https://docs.projectsecurity.io/e101/overview/)
- **Network+ Study Materials**: CompTIA N10-009 certification preparation
- **Cybersecurity Frameworks**: NIST

## Lessons Learned

### Technical Challenges & Solutions

**VirtualBox Infrastructure Management**
- **Challenge**: Managing 366GB lab environment across multiple storage devices
- **Solution**: Implemented systematic VM migration using rsync for large-scale data transfers
- **Learning**: Proper resource planning and backup strategies are critical for complex lab environments

**Network Connectivity Troubleshooting**
- **Challenge**: Domain controller network isolation issues (split-brain DNS scenarios)
- **Solution**: Applied Network+ troubleshooting methodology to diagnose virtual network adapter misconfiguration
- **Learning**: Layer-by-layer network diagnostics are essential even in virtualized environments

**System Recovery & Data Protection**
- **Challenge**: VirtualBox corruption during file operations with external storage
- **Solution**: Developed backup-of-backup system using .vbox-prev files for configuration recovery
- **Learning**: Multiple backup strategies and understanding hypervisor configuration files prevents total data loss

### Operational Insights

**Lab Performance Optimization**
- External drive performance limitations identified during high-I/O operations
- Future planning includes 4TB SSD upgrade to eliminate storage bottlenecks
- Resource allocation balancing across 7 simultaneous VMs requires careful CPU and memory management

**Security Monitoring Effectiveness**
- Wazuh SIEM integration provides comprehensive log correlation across enterprise environment
- Security Onion packet analysis capabilities enhance threat detection accuracy
- Real-time monitoring reduces incident response time significantly

**Enterprise Environment Simulation**
- Active Directory integration creates authentic corporate network behavior
- Multi-OS environment (Windows Server, Ubuntu, Kali) reflects real-world heterogeneous networks
- Attack simulation scenarios provide practical incident response training

## Author

Built as part of comprehensive cybersecurity education, demonstrating enterprise-level security operations and incident response capabilities.

---

*This lab environment simulates real-world corporate network intrusion scenarios for educational and professional development purposes. All attack simulations are contained within isolated virtual environments.*
