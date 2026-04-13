# Module 18: IoT and OT Hacking

## 1. IoT Hacking

### 1.1 IoT Concepts and Attacks

**Definition:**  
IoT (Internet of Things) is a network of physical devices connected to the internet for sensing, communication, and automation.

**Examples:**  
- Smart cameras
- Smart TVs
- Smart locks
- Wearables
- Industrial sensors

### IoT Architecture

| Layer | Description |
|------|-------------|
| Device Layer | Sensors and actuators that collect or perform actions. |
| Communication Layer | Connectivity such as Wi-Fi, Bluetooth, Zigbee, and MQTT. |
| Cloud Layer | Data storage, analytics, and remote processing. |
| Application Layer | Mobile apps, dashboards, and web interfaces used to control devices. |

### IoT Protocols

| Protocol | Use Case | Risk |
|---------|----------|------|
| MQTT | Lightweight messaging for IoT devices | No encryption by default |
| CoAP | REST-based communication for constrained devices | UDP-based, spoofing risk |
| Zigbee | Smart home and mesh networks | Weak key management |
| Bluetooth | Short-range communication | Sniffing and pairing attacks |

### IoT Attack Surface

Common weaknesses in IoT environments include:
- Weak passwords
- Open ports
- Insecure APIs
- Firmware vulnerabilities
- Lack of encryption
- Default credentials

### Common IoT Attacks

#### 1. Botnet Attacks
Devices are infected and later used for large-scale attacks such as DDoS.  
Example: Mirai botnet.

#### 2. Device Hijacking
An attacker gains control of the device and can change settings, spy on users, or use it for further attacks.

#### 3. Data Interception
Traffic between the device and server is intercepted using man-in-the-middle techniques.

#### 4. Firmware Exploitation
Attackers reverse engineer firmware, find weaknesses, and inject malicious code.

#### 5. Physical Attacks
Direct access to the hardware through interfaces like UART or JTAG.

#### 6. Replay Attacks
Previously captured packets are reused to perform unauthorized actions.

#### 7. Cloud Attacks
Attackers exploit weak backend APIs or cloud misconfigurations linked to the IoT system.

### 1.2 IoT Hacking Methodology

#### Phase 1: Reconnaissance
Identify devices on the network and gather information about them.

Common tools and sources:
- Nmap
- Shodan
- Wireshark

#### Phase 2: Scanning
Check for open ports, running services, and firmware versions.

#### Phase 3: Enumeration
Identify default credentials, API endpoints, and supported protocols.

#### Phase 4: Exploitation
Use weaknesses such as:
- Weak authentication
- Command injection
- Buffer overflow
- Firmware vulnerabilities

#### Phase 5: Post Exploitation
Maintain access, pivot into the network, and extract useful data.

#### Phase 6: Communication Analysis
Analyze packets and decode protocols such as MQTT and CoAP.

### 1.3 IoT Attack Countermeasures

#### Device Security
- Change default credentials
- Disable unused services
- Enable secure boot

#### Network Security
- Segment IoT devices from the main network
- Use VLANs
- Deploy firewalls

#### Encryption
- Use TLS/SSL
- Protect communication channels

#### Firmware Updates
- Patch devices regularly

#### Monitoring
- Integrate with SIEM
- Analyze logs
- Detect anomalies

## 2. OT Hacking

### 2.1 OT Concepts and Attacks

**Definition:**  
OT (Operational Technology) refers to systems that control physical processes in industrial environments.

**Examples:**  
- Power plants
- Water treatment systems
- Manufacturing plants
- Oil and gas pipelines

### Key OT Components

| Component | Description |
|----------|-------------|
| PLC | Programmable Logic Controller |
| SCADA | Supervisory Control and Data Acquisition |
| HMI | Human Machine Interface |
| RTU | Remote Terminal Unit |

### OT vs IT

| Feature | IT | OT |
|---------|----|----|
| Focus | Data | Processes |
| Priority | Confidentiality | Safety and availability |
| Patching | Frequent | Rare and carefully controlled |
| Protocols | Modern standard protocols | Legacy industrial protocols |

### OT Protocols

| Protocol | Risk |
|---------|------|
| Modbus | No authentication |
| DNP3 | Weak encryption |
| OPC | Misconfigurations |

### Real-World OT Attacks

#### 1. Stuxnet
Targeted Iranian nuclear facilities and manipulated PLCs using advanced exploitation techniques.

#### 2. Industroyer / CrashOverride
Targeted power grid systems.

#### 3. Triton
Targeted safety systems used in industrial environments.

### Common OT Attacks
- Unauthorized command execution
- PLC manipulation
- Network sniffing
- DoS against control systems
- Insider threats

### 2.2 OT Hacking Methodology

#### Phase 1: Reconnaissance
Map the ICS environment and identify PLCs, SCADA systems, and connected devices.

#### Phase 2: Scanning
Active scanning must be done carefully because it can disrupt or damage OT systems.

#### Phase 3: Enumeration
Analyze protocols such as Modbus and DNP3 and identify device configuration details.

#### Phase 4: Exploitation
Send malicious commands, modify PLC logic, or replay captured control commands.

#### Phase 5: Persistence
Maintain access through backdoors in control systems.

#### Phase 6: Impact
Shutdown plants, damage equipment, or create safety hazards.

### 2.3 OT Attack Countermeasures

#### Network Segmentation
- Separate IT and OT networks
- Use a DMZ between them

#### Access Control
- Role-based access control
- Multi-factor authentication

#### Monitoring
- ICS-aware SIEM
- Protocol monitoring

#### Patch Management
- Apply carefully tested updates

#### Incident Response
- Use OT-specific playbooks

#### Physical Security
- Restrict access to controllers and devices

## 3. Important Exam Point

**Most common OT attack:** PLC manipulation

**Most important IoT attack:** Botnet-based attacks such as Mirai

**Key difference:**  
IoT attacks usually focus on device compromise and large-scale misuse, while OT attacks can lead to physical damage and safety risks.
