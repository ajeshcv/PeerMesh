# PeerMesh – Offline Mesh Communication System

## Project Overview

### Project Title
**PeerMesh – Offline Mesh Communication System**

---

# Introduction

PeerMesh is a decentralized offline communication system that enables users to exchange messages without relying on the internet or cellular networks. The application creates a peer-to-peer mesh network using Bluetooth and Wi-Fi Direct, allowing nearby devices to communicate directly and relay messages through intermediate devices when direct communication is not possible.

Unlike traditional messaging applications that depend on centralized servers, PeerMesh operates in a distributed environment where each connected device acts as both a communication endpoint and a relay node. This approach extends communication range, improves reliability, and ensures connectivity even during internet outages, natural disasters, remote travel, or large public gatherings.

Designed using software engineering principles, PeerMesh follows a modular architecture that separates networking, messaging, security, storage, and user interface components, making the system scalable, maintainable, and extensible.

---

# Problem Statement

Most messaging applications require internet connectivity or mobile networks to function. During emergencies, natural disasters, rural deployments, or network failures, users often lose the ability to communicate.

There is a need for a secure, decentralized communication platform that enables reliable messaging without depending on external network infrastructure.

---

# Proposed Solution

PeerMesh establishes an offline mesh network by automatically discovering nearby devices using Bluetooth and Wi-Fi Direct. Messages can be transmitted directly or forwarded through neighboring devices using multi-hop routing, enabling communication beyond the normal wireless range.

The system provides encrypted messaging, automatic routing, local data storage, file sharing, and group communication while operating entirely offline.

---

# Objectives

## Primary Objectives

- Develop a fully offline messaging application.
- Enable peer-to-peer communication without internet access.
- Implement mesh networking with multi-hop message forwarding.
- Ensure secure communication through encryption.
- Provide reliable and efficient message delivery.
- Design a scalable and modular software architecture.

---

## Secondary Objectives

- Support file and media sharing.
- Enable group messaging.
- Discover nearby devices automatically.
- Select optimal communication routes dynamically.
- Synchronize messages locally.
- Support future cloud synchronization when internet becomes available.

---

# Scope of the Project

PeerMesh is intended for environments where internet connectivity is unavailable or unreliable. The system can be used in:

- Educational institutions
- Disaster recovery operations
- Rural and remote communities
- Emergency response teams
- Military communication
- Large public events
- Industrial environments
- Camping and outdoor expeditions

Future versions may include cloud synchronization, voice communication, and cross-platform support.

---

# Key Features

## Communication

- One-to-one messaging
- Group messaging
- Offline messaging
- Multi-hop communication
- Automatic message forwarding

---

## Networking

- Bluetooth communication
- Wi-Fi Direct communication
- Automatic nearby device discovery
- Dynamic mesh routing
- Automatic reconnection

---

## Security

- End-to-end encrypted messaging
- Secure device authentication
- Encrypted local database
- Secure message transmission

---

## User Features

- User profile
- Contact management
- Chat history
- File and media sharing
- Dark mode
- Notifications

---

# Target Users

- Students
- Educational institutions
- Disaster management agencies
- Emergency responders
- Travelers
- Event organizers
- NGOs
- Industrial workers
- Military personnel

---

# Technologies

## Mobile Application

- Java
- Android Studio
- Material Design
- Room Database

## Networking

- Bluetooth Classic
- Bluetooth Low Energy (BLE)
- Wi-Fi Direct
- Mesh Routing Algorithm

## Backend (Future Enhancement)

- Spring Boot
- PostgreSQL
- REST APIs
- JWT Authentication

---

# Expected Outcomes

The completed PeerMesh system will provide:

- Reliable offline communication.
- Secure peer-to-peer messaging.
- Automatic mesh network formation.
- Multi-hop message routing.
- Efficient local data management.
- Improved communication during network outages.

---

# Benefits

- Works without internet.
- No dependency on cellular networks.
- Secure decentralized communication.
- Low operational cost.
- Extended communication range through relay devices.
- Reliable messaging during emergencies.
- Privacy-focused architecture.

---

# Future Enhancements

- Voice calling
- Video calling
- Emergency SOS broadcasting
- Offline location sharing
- Cross-platform support
- Cloud synchronization
- Mesh performance analytics
- AI-assisted route optimization
- IoT integration

---

# Conclusion

PeerMesh is an offline mesh communication system that enables secure and reliable peer-to-peer messaging without internet connectivity. By leveraging Bluetooth and Wi-Fi Direct, the application forms a decentralized mesh network where devices can communicate directly or relay messages across multiple nodes. Built with a modular software engineering architecture, PeerMesh provides a scalable foundation for secure offline communication and has the potential to support emergency response, education, industrial collaboration, and remote connectivity scenarios.