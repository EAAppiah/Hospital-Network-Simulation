# Hospital Network Simulation ✨

A resource-efficient GNS3 simulation of a hospital network infrastructure using Cisco devices.

## Overview

This project provides a comprehensive hospital network topology simulated in GNS3, focusing on resource efficiency. It demonstrates essential networking concepts including segmentation, routing, security, and services required in a healthcare environment while minimizing computational resource requirements.

## Network Topology

[![Hospital Network Topology](https://i.imgur.com/4XQyNOa.png "Hospital Network Simulation")]

The network consists of several key components:

- **Edge Layer**: FortiGate Firewall and Cisco 7200 Router
- **Core Layer**: Cisco 7200 Router (Layer 3 routing)
- **Access Layer**: Cisco IOU L2 switches for departments
- **Simulated Wireless**: Dedicated L2 switch with VLANs

## Network Segmentation

| Segment | VLAN | Subnet | Purpose |
|---------|------|--------|---------|
| Medical Department | 100 | 10.1.0.0/24 | Clinical staff and devices |
| Administrative | 200 | 10.2.0.0/24 | Administrative staff and systems |
| Server Infrastructure | 300 | 10.7.0.0/24 | Medical servers (DICOM, HL7) |
| Staff Wireless | 410 | 10.6.1.0/24 | Staff wireless access |
| Patient Wireless | 420 | 10.6.2.0/24 | Patient wireless access |
| Management | 999 | 10.254.0.0/24 | Device administration |
| Edge Router Link | - | 10.0.1.0/30 | Connection to Internet |

## Technologies Implemented

- **Routing**: OSPF for internal routing
- **Switching**: VLANs with 802.1Q trunking
- **Security**: ACLs, firewall policies
- **Loop Prevention**: Spanning Tree Protocol (STP)
- **Services**: DHCP for client addressing
- **Security Segregation**: Separate patient and staff networks
- **Healthcare Integration**: Support for medical systems (DICOM, HL7)

## Hardware Requirements

- **CPU**: 2+ cores recommended
- **RAM**: 4GB minimum, 8GB recommended
- **Storage**: 1GB free space
- **OS**: Windows, macOS, or Linux with GNS3 2.2.0+

## Required GNS3 Appliances

🖧 Cisco 7200 Router v12.4(24)T5

🔀 Cisco IOU L2 Switches V15.1

🔐 FortiGate VM v7.0.9

💻 VPCS (for endpoints)

## Installation 🚀


1. 📥 Clone this repository
2. 📂 Import the `.gns3project` file into GNS3
3. 📦 Ensure you have the required appliance images
4. 🚀 Start the devices according to the recommended sequence in the documentation

## Usage

### Starting the Network

1. Start the FortiGate and Edge Router first
2. Start the Core Router
3. Start the department switches
4. Start the endpoint devices

### Testing Connectivity

Test commands are included in the documentation to verify:
- Inter-VLAN routing
- Internet connectivity
- Security policies
- DHCP functionality

## Key Features

- **Resource Efficiency**: Optimized for systems with limited RAM
- **Security Implementation**: Demonstrates healthcare network security best practices
- **Realistic Segmentation**: Models actual hospital network design principles
- **Scalability**: Can be extended with additional departments or services
