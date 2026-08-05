# Software Requirements Specification (SRS)

# PeerMesh
### Offline Mesh Communication System

**Version:** 1.0

**Prepared By:** Ajesh CV

**Date:** July 2026

---

# Revision History

| Version | Date | Author | Description |
|----------|------|--------|-------------|
| 1.0 | July 2026 | Ajesh CV | Initial SRS Document |

---

# Table of Contents

1. Introduction
2. Overall Description
3. System Features
4. External Interface Requirements
5. Functional Requirements
6. Non-Functional Requirements
7. System Models
8. Database Requirements
9. Security Requirements
10. Constraints
11. Assumptions
12. Future Enhancements
13. References

---

# 1. Introduction

## 1.1 Purpose

The purpose of this Software Requirements Specification (SRS) is to define the functional and non-functional requirements for **PeerMesh**, an offline mesh communication system designed to enable secure messaging without relying on internet connectivity or cellular networks.

This document serves as a reference for developers, testers, project supervisors, and stakeholders by clearly describing the system's objectives, features, constraints, and expected behavior. It provides a structured foundation for the design, implementation, testing, and maintenance of the PeerMesh application.

---

## 1.2 Scope

PeerMesh is an Android-based mobile application that allows users to communicate through a decentralized peer-to-peer mesh network using Bluetooth and Wi-Fi Direct technologies.

Unlike conventional messaging applications that depend on centralized servers, PeerMesh enables nearby devices to communicate directly and relay messages across intermediate devices using multi-hop routing. This ensures reliable communication even in environments where internet access or cellular networks are unavailable.

The system is intended for use in educational institutions, disaster recovery operations, remote locations, industrial environments, public events, and emergency response scenarios.

Future versions may introduce optional cloud synchronization while preserving the application's core offline capabilities.

---

## 1.3 Objectives

The primary objectives of PeerMesh are:

- Develop a reliable offline communication platform.
- Enable peer-to-peer messaging without internet connectivity.
- Implement automatic mesh network formation.
- Support multi-hop message forwarding.
- Provide secure encrypted communication.
- Allow offline file and media sharing.
- Build a scalable and modular software architecture.
- Deliver a user-friendly Android application.

---

## 1.4 Intended Audience

This document is intended for:

- Project Supervisor
- Software Developers
- Android Developers
- Test Engineers
- System Designers
- Database Designers
- Future Maintainers
- MCA Project Evaluation Committee

---

## 1.5 Product Perspective

PeerMesh is designed as a standalone decentralized communication system.

Instead of relying on centralized cloud servers, the application forms a local mesh network where each connected device functions as both a communication endpoint and a relay node.

The system consists of several independent software modules, including:

- User Management Module
- Device Discovery Module
- Mesh Networking Module
- Routing Module
- Messaging Module
- File Sharing Module
- Local Database Module
- Security Module
- Settings Module

Each module is loosely coupled to improve maintainability, scalability, and future expansion.

---

## 1.6 Product Functions

The PeerMesh system provides the following core functionalities:

### User Management

- User profile creation
- Profile editing
- Device identification

### Communication

- One-to-one messaging
- Group messaging
- Offline messaging
- Message synchronization
- Message history

### Networking

- Bluetooth discovery
- Wi-Fi Direct discovery
- Automatic nearby device detection
- Automatic peer connection
- Mesh network formation

### Routing

- Dynamic route discovery
- Multi-hop message forwarding
- Relay node management
- Automatic path optimization

### File Sharing

- Image sharing
- Video sharing
- Audio sharing
- Document sharing

### Security

- End-to-end encryption
- Local database encryption
- Secure device authentication

### Storage

- Offline message storage
- Contact storage
- File management
- Chat history

---

## 1.7 Definitions, Acronyms and Abbreviations

| Term | Description |
|------|-------------|
| BLE | Bluetooth Low Energy |
| Wi-Fi Direct | Device-to-device wireless communication technology |
| Mesh Network | A decentralized network where devices relay messages for one another |
| Multi-Hop Routing | Forwarding messages through intermediate devices |
| Peer Node | Any participating device in the mesh network |
| Relay Node | A device responsible for forwarding messages |
| Endpoint | The final destination device for a message |
| Android | Mobile operating system developed by Google |
| Room Database | Local SQLite abstraction library for Android |
| SRS | Software Requirements Specification |
| UI | User Interface |
| API | Application Programming Interface |

---

## 1.8 Operating Environment

PeerMesh is designed to operate under the following environment:

### Hardware

- Android Smartphone
- Bluetooth Adapter
- Wi-Fi Adapter
- Minimum 3 GB RAM
- Minimum Android 10

### Software

- Android OS 10+
- Android Studio
- Java 17
- Room Database
- Git
- GitHub

---

## 1.9 Constraints

The following constraints apply to the system:

- Internet connection is not required.
- Communication range depends on Bluetooth and Wi-Fi Direct capabilities.
- Mesh routing depends on the availability of nearby relay devices.
- Battery usage may increase during continuous mesh communication.
- Device compatibility depends on Android hardware support.

---

## 1.10 Assumptions and Dependencies

The system assumes that:

- Nearby devices have Bluetooth or Wi-Fi Direct enabled.
- Users grant all required permissions.
- Devices remain powered during communication.
- Android devices support the required networking features.
- Sufficient storage is available for offline data.

---

## 1.11 References

The following references were considered during system planning:

- IEEE Software Requirements Specification Standard
- Android Developer Documentation
- Bluetooth SIG Documentation
- Wi-Fi Direct Documentation
- Material Design Guidelines
- Java SE Documentation

---

# 2. Overall Description

## 2.1 Product Perspective

PeerMesh is a standalone Android application designed to facilitate offline communication through a decentralized mesh network. Unlike traditional messaging applications that rely on cloud servers and internet connectivity, PeerMesh enables devices to communicate directly using Bluetooth and Wi-Fi Direct.

The application dynamically forms a mesh network where each participating device can function as both a communication endpoint and a relay node. If two users are outside each other's direct communication range, messages can be forwarded through one or more intermediate devices until they reach the intended recipient.

The system follows a modular architecture, allowing individual components such as networking, routing, messaging, storage, and security to be developed, tested, and maintained independently. This architecture also supports future enhancements such as cloud synchronization, voice communication, and cross-platform compatibility.

---

## 2.2 System Overview

PeerMesh consists of several interconnected modules that work together to provide reliable offline communication.

### Major Modules

### 1. User Management Module

Responsible for maintaining user information and application settings.

Functions include:

- Create user profile
- Edit profile
- Manage device identity
- Store local preferences

---

### 2. Device Discovery Module

Discovers nearby devices capable of participating in the mesh network.

Functions include:

- Bluetooth discovery
- Wi-Fi Direct discovery
- Peer identification
- Connection requests
- Device availability monitoring

---

### 3. Mesh Networking Module

Responsible for establishing and maintaining the decentralized mesh network.

Functions include:

- Peer connection
- Node management
- Network topology maintenance
- Automatic reconnection
- Mesh formation

---

### 4. Routing Module

Determines the best available path for message delivery.

Functions include:

- Route discovery
- Multi-hop routing
- Relay selection
- Route optimization
- Failed route recovery

---

### 5. Messaging Module

Handles all messaging operations.

Functions include:

- Send messages
- Receive messages
- Store messages
- Read receipts
- Delivery acknowledgements
- Message synchronization

---

### 6. File Sharing Module

Enables users to exchange files without internet access.

Supported files include:

- Images
- Videos
- Audio
- Documents
- PDFs

---

### 7. Local Database Module

Stores application data securely on the device.

Data includes:

- Users
- Chats
- Messages
- Contacts
- Device information
- Shared files
- Application settings

---

### 8. Security Module

Ensures secure communication between devices.

Responsibilities include:

- Device authentication
- Encryption
- Data integrity
- Secure storage
- Session management

---

## 2.3 Product Features

PeerMesh provides the following major features.

### Communication Features

- One-to-one messaging
- Group messaging
- Offline messaging
- Multi-hop communication
- Automatic message forwarding
- Chat history
- Message synchronization
- Read receipts
- Delivery status

---

### Networking Features

- Bluetooth communication
- Bluetooth Low Energy (BLE)
- Wi-Fi Direct communication
- Automatic nearby device discovery
- Mesh network formation
- Dynamic routing
- Automatic reconnection

---

### File Sharing Features

- Image sharing
- Video sharing
- Audio sharing
- PDF sharing
- Document sharing

---

### User Features

- User profile
- Contact management
- Device management
- Notification settings
- Dark mode
- Application preferences

---

### Security Features

- End-to-end encryption
- Local database encryption
- Secure authentication
- Secure communication channel
- Data confidentiality

---

## 2.4 User Classes and Characteristics

The application is intended for a wide variety of users.

### Students

Students can communicate across classrooms, campuses, or hostels even when internet access is unavailable.

---

### Emergency Response Teams

Emergency personnel can exchange information during disasters where communication infrastructure has failed.

---

### Travelers

Users travelling in remote areas can remain connected without relying on mobile networks.

---

### Event Participants

Attendees at festivals, concerts, or conferences can communicate despite network congestion.

---

### Industrial Workers

Employees working in factories, warehouses, or construction sites can exchange operational information using local connectivity.

---

## 2.5 Operating Environment

PeerMesh requires the following operating environment.

### Mobile Device

- Android Smartphone
- Bluetooth Support
- Wi-Fi Direct Support
- GPS (optional)
- Minimum 3 GB RAM

---

### Operating System

- Android 10 or higher

---

### Development Environment

- Android Studio
- Java 17
- Room Database
- Git
- GitHub

---

## 2.6 Design Constraints

The system must operate within the following constraints.

### Hardware Constraints

- Bluetooth range limitations
- Wi-Fi Direct hardware compatibility
- Battery consumption
- Device memory limitations

---

### Software Constraints

- Android operating system compatibility
- Java programming language
- Room Database
- Android permissions model

---

### Network Constraints

- No internet dependency
- Limited communication range
- Dynamic device availability
- Variable network topology

---

## 2.7 User Characteristics

Users are expected to have basic smartphone knowledge.

They should be able to:

- Install Android applications
- Enable Bluetooth
- Enable Wi-Fi Direct
- Send messages
- Share files
- Accept connection requests

No advanced technical knowledge is required.

---

## 2.8 Assumptions

The following assumptions are made during system development.

- Bluetooth is enabled.
- Wi-Fi Direct is available.
- Devices remain powered during communication.
- Necessary permissions are granted.
- Storage space is available.
- Nearby devices are running PeerMesh.

---

## 2.9 Dependencies

PeerMesh depends on the following technologies.

### Hardware

- Bluetooth adapter
- Wi-Fi adapter
- Android device

---

### Software

- Android SDK
- Java Runtime
- Room Database
- Android Bluetooth APIs
- Android Wi-Fi Direct APIs

---

## 2.10 Limitations

The current version has the following limitations.

- Android devices only
- No iOS support
- Voice and video calling are not supported
- Communication distance depends on relay devices
- Internet synchronization is not available in the current release

---

## 2.11 Future Scope

Future versions of PeerMesh may include:

- Voice calling
- Video calling
- Offline location sharing
- Emergency SOS broadcasting
- Cloud synchronization
- Cross-platform support
- Desktop application
- Mesh network analytics
- AI-assisted routing optimization
- IoT device communication

---

# 3. System Features

This chapter describes the major functional features of the PeerMesh application. Each feature includes its purpose, inputs, outputs, preconditions, postconditions, and functional requirements.

---

# 3.1 User Management

## Description

The User Management module is responsible for creating, maintaining, and updating user information stored on the device. Since PeerMesh operates offline, users are identified locally rather than through cloud-based accounts.

---

### Inputs

- Username
- Profile Picture (Optional)
- Device Name

---

### Outputs

- User Profile
- Updated User Information

---

### Preconditions

- Application installed
- Required permissions granted

---

### Postconditions

- User profile stored locally
- Profile available throughout the application

---

### Functional Requirements

| ID | Requirement |
|----|-------------|
| FR-1 | The system shall allow users to create a profile. |
| FR-2 | The system shall allow users to edit their profile. |
| FR-3 | The system shall store profile information locally. |
| FR-4 | The system shall display the user's profile information. |

---

# 3.2 Device Discovery

## Description

The Device Discovery module continuously scans for nearby PeerMesh devices using Bluetooth and Wi-Fi Direct.

---

### Inputs

- Bluetooth status
- Wi-Fi Direct status

---

### Outputs

- Nearby device list

---

### Preconditions

- Bluetooth enabled
- Wi-Fi Direct enabled

---

### Postconditions

- Nearby devices displayed

---

### Functional Requirements

| ID | Requirement |
|----|-------------|
| FR-5 | The system shall discover nearby devices automatically. |
| FR-6 | The system shall refresh the nearby device list. |
| FR-7 | The system shall detect device availability. |
| FR-8 | The system shall remove unavailable devices. |

---

# 3.3 Peer Connection

## Description

This feature establishes secure communication between nearby devices.

---

### Inputs

- Selected nearby device

---

### Outputs

- Connected device

---

### Preconditions

- Device discovered

---

### Postconditions

- Secure connection established

---

### Functional Requirements

| ID | Requirement |
|----|-------------|
| FR-9 | The system shall establish peer-to-peer connections. |
| FR-10 | The system shall reconnect automatically when possible. |
| FR-11 | The system shall terminate inactive connections safely. |

---

# 3.4 Mesh Network Formation

## Description

The application automatically creates a decentralized mesh network among participating devices.

---

### Inputs

- Connected devices

---

### Outputs

- Active mesh network

---

### Preconditions

- Multiple devices available

---

### Postconditions

- Mesh network established

---

### Functional Requirements

| ID | Requirement |
|----|-------------|
| FR-12 | The system shall automatically form a mesh network. |
| FR-13 | The system shall add newly discovered devices. |
| FR-14 | The system shall remove disconnected devices. |
| FR-15 | The system shall maintain network topology. |

---

# 3.5 Routing

## Description

The Routing Module determines the most efficient path for message transmission.

---

### Inputs

- Destination device
- Active network topology

---

### Outputs

- Selected communication route

---

### Preconditions

- Mesh network available

---

### Postconditions

- Route generated

---

### Functional Requirements

| ID | Requirement |
|----|-------------|
| FR-16 | The system shall calculate communication routes. |
| FR-17 | The system shall support multi-hop routing. |
| FR-18 | The system shall select the shortest available route. |
| FR-19 | The system shall reroute messages when paths fail. |

---

# 3.6 One-to-One Messaging

## Description

Allows direct communication between two users.

---

### Inputs

- Text message
- Destination user

---

### Outputs

- Delivered message

---

### Preconditions

- Destination reachable

---

### Postconditions

- Message stored locally

---

### Functional Requirements

| ID | Requirement |
|----|-------------|
| FR-20 | The system shall send text messages. |
| FR-21 | The system shall receive text messages. |
| FR-22 | The system shall display delivery status. |
| FR-23 | The system shall display read receipts. |

---

# 3.7 Group Messaging

## Description

Enables communication among multiple users within a group.

---

### Inputs

- Group members
- Group message

---

### Outputs

- Group conversation

---

### Preconditions

- Group created

---

### Postconditions

- Message delivered to reachable members

---

### Functional Requirements

| ID | Requirement |
|----|-------------|
| FR-24 | The system shall create groups. |
| FR-25 | The system shall allow users to join groups. |
| FR-26 | The system shall allow users to leave groups. |
| FR-27 | The system shall deliver group messages. |

---

# 3.8 File Sharing

## Description

Allows users to exchange files over the mesh network.

---

### Supported Files

- Images
- Videos
- Audio
- PDF
- Documents

---

### Functional Requirements

| ID | Requirement |
|----|-------------|
| FR-28 | The system shall send images. |
| FR-29 | The system shall send videos. |
| FR-30 | The system shall send documents. |
| FR-31 | The system shall store shared files locally. |

---

# 3.9 Local Database

## Description

Stores application data securely for offline use.

---

### Stored Data

- User Profile
- Messages
- Contacts
- Groups
- Files
- Settings

---

### Functional Requirements

| ID | Requirement |
|----|-------------|
| FR-32 | The system shall store messages locally. |
| FR-33 | The system shall retrieve chat history. |
| FR-34 | The system shall store user preferences. |
| FR-35 | The system shall support offline access. |

---

# 3.10 Notifications

## Description

Notifies users about incoming messages and important events.

---

### Functional Requirements

| ID | Requirement |
|----|-------------|
| FR-36 | The system shall notify users of new messages. |
| FR-37 | The system shall notify users when nearby devices are discovered. |
| FR-38 | The system shall notify users of file transfer completion. |

---

# 3.11 Security

## Description

Provides secure communication and protects stored data.

---

### Functional Requirements

| ID | Requirement |
|----|-------------|
| FR-39 | The system shall encrypt transmitted messages. |
| FR-40 | The system shall encrypt locally stored data where appropriate. |
| FR-41 | The system shall authenticate peer devices before communication. |
| FR-42 | The system shall prevent unauthorized access to user data. |

---

# 3.12 Settings

## Description

Allows users to customize application behavior.

---

### Functional Requirements

| ID | Requirement |
|----|-------------|
| FR-43 | The system shall allow users to enable or disable notifications. |
| FR-44 | The system shall support light and dark themes. |
| FR-45 | The system shall allow users to update application preferences. |

---

# Summary of Functional Requirements

| Module | Requirement IDs |
|---------|-----------------|
| User Management | FR-1 – FR-4 |
| Device Discovery | FR-5 – FR-8 |
| Peer Connection | FR-9 – FR-11 |
| Mesh Networking | FR-12 – FR-15 |
| Routing | FR-16 – FR-19 |
| Messaging | FR-20 – FR-27 |
| File Sharing | FR-28 – FR-31 |
| Local Database | FR-32 – FR-35 |
| Notifications | FR-36 – FR-38 |
| Security | FR-39 – FR-42 |
| Settings | FR-43 – FR-45 |

---

# 4. External Interface Requirements

This chapter defines the external interfaces through which users, hardware, software components, and communication protocols interact with the PeerMesh system.

---

# 4.1 User Interface (UI)

## Overview

PeerMesh provides a clean, responsive, and user-friendly interface following Android Material Design guidelines. The interface is designed to minimize user interaction while providing quick access to messaging, nearby devices, and network status.

The application supports both Light Mode and Dark Mode and is optimized for smartphones running Android 10 or later.

---

## UI Design Principles

- Simple and intuitive navigation
- Consistent design across all screens
- Responsive layout for different screen sizes
- Accessibility-friendly controls
- Minimal user interaction for network setup
- Fast response time
- Material Design components

---

## Main Screens

### Splash Screen

Purpose:
- Display application logo
- Initialize system components
- Load user settings

---

### Welcome Screen

Features:

- Application introduction
- Create profile
- Continue to application

---

### Home Screen

Features:

- Nearby Devices
- Recent Chats
- Group Chats
- Network Status
- Search
- Navigation Menu

---

### Nearby Devices Screen

Features:

- Scan nearby devices
- Device availability
- Connection status
- Connect button
- Refresh device list

---

### Chat Screen

Features:

- Text messaging
- Emoji support
- File sharing
- Image preview
- Message status
- Read receipts

---

### Group Chat Screen

Features:

- Group messages
- Group information
- Member list
- Shared media

---

### File Sharing Screen

Features:

- Select files
- File preview
- Transfer progress
- Transfer history

---

### Settings Screen

Features:

- Profile settings
- Notifications
- Theme
- Bluetooth
- Wi-Fi Direct
- About
- Privacy

---

## Navigation Flow

```
Splash Screen
      │
      ▼
Welcome Screen
      │
      ▼
Home Screen
 ├── Nearby Devices
 ├── Chats
 ├── Groups
 ├── File Sharing
 └── Settings
```

---

# 4.2 Hardware Interface

PeerMesh interacts with the following hardware components.

## Bluetooth Adapter

Purpose:

- Device discovery
- Peer communication
- Message transfer

---

## Wi-Fi Direct Adapter

Purpose:

- High-speed communication
- File transfer
- Mesh communication

---

## Device Storage

Purpose:

- Store messages
- Store contacts
- Store shared files
- Store settings

---

## Camera (Optional)

Purpose:

- Capture images
- Share photos

---

## Gallery

Purpose:

- Select images
- Select videos
- Select documents

---

## Battery

The application monitors battery usage to avoid excessive power consumption during continuous mesh networking.

---

# 4.3 Software Interface

PeerMesh communicates with the following software components.

## Android Operating System

Responsibilities:

- Activity management
- Permissions
- Notifications
- Background services

---

## Android Bluetooth API

Purpose:

- Bluetooth discovery
- Device pairing
- Communication

---

## Android Wi-Fi Direct API

Purpose:

- Peer discovery
- Group formation
- Data transfer

---

## Room Database

Purpose:

- Local storage
- Message persistence
- Offline access

---

## Android Notification Manager

Purpose:

- Display notifications
- Background alerts
- Message notifications

---

## File System

Purpose:

- File storage
- Media access
- Document sharing

---

# 4.4 Communication Interface

PeerMesh communicates using short-range wireless technologies.

---

## Bluetooth

Functions:

- Nearby device discovery
- Text messaging
- Low-bandwidth communication

Advantages:

- Low power consumption
- Wide device compatibility

---

## Wi-Fi Direct

Functions:

- High-speed communication
- Large file transfer
- Group communication

Advantages:

- Faster than Bluetooth
- Higher bandwidth

---

## Mesh Communication

Functions:

- Multi-hop routing
- Automatic forwarding
- Relay communication

Benefits:

- Extended communication range
- Improved reliability
- Decentralized communication

---

# 4.5 External Device Interface

The system communicates with nearby Android devices running PeerMesh.

Each connected device may perform one or more of the following roles:

- Sender
- Receiver
- Relay Node

Every participating device contributes to the mesh network by forwarding messages when required.

---

# 4.6 Database Interface

The application uses a local Room Database.

Major tables include:

- Users
- Contacts
- Devices
- Chats
- Messages
- Groups
- Group Members
- Shared Files
- Settings

The database operates entirely offline.

---

# 4.7 Security Interface

The application provides several security mechanisms.

### Authentication

- Local device identity
- Trusted peer verification

---

### Encryption

- Encrypted message transmission
- Encrypted local storage

---

### Permissions

Required Android permissions include:

- Bluetooth
- Nearby Devices
- Wi-Fi
- Storage
- Notifications
- Camera (optional)

The application requests permissions only when necessary.

---

# 4.8 Error Handling Interface

The application provides informative messages for common situations.

Examples include:

| Situation | Response |
|-----------|----------|
| Bluetooth Disabled | Prompt user to enable Bluetooth |
| Wi-Fi Direct Disabled | Prompt user to enable Wi-Fi Direct |
| Device Not Found | Display "No nearby devices found." |
| Connection Failed | Display retry option |
| File Transfer Failed | Retry or cancel transfer |
| Storage Full | Notify user about insufficient storage |

---

# 4.9 Accessibility Requirements

PeerMesh is designed to support accessibility features.

Supported features include:

- Large touch targets
- Readable fonts
- High-contrast themes
- Screen rotation support
- Dark Mode
- Descriptive icons
- Responsive layouts

---

# 4.10 Performance Expectations

The user interface should satisfy the following expectations.

| Parameter | Requirement |
|-----------|-------------|
| App Launch Time | Less than 3 seconds |
| Screen Transition | Less than 500 milliseconds |
| Message Display | Immediate after reception |
| Device Discovery Refresh | Within 5–10 seconds |
| File Transfer Progress | Real-time updates |
| Database Access | Less than 200 milliseconds |

---

# Chapter Summary

This chapter defined the external interfaces required for PeerMesh, including user interface requirements, hardware and software interfaces, communication mechanisms, database interactions, security interfaces, accessibility considerations, and expected system performance.


---

# 5. Non-Functional Requirements

Non-functional requirements specify the quality attributes, performance characteristics, security measures, and operational constraints that PeerMesh must satisfy. These requirements ensure that the system is reliable, secure, efficient, and easy to use.

---

# 5.1 Performance Requirements

The application shall provide fast and responsive communication even in offline environments.

### Requirements

| ID | Requirement |
|----|-------------|
| NFR-1 | The application shall start within **3 seconds** under normal conditions. |
| NFR-2 | The system shall display screen transitions within **500 milliseconds**. |
| NFR-3 | Messages shall be processed immediately after being received. |
| NFR-4 | Nearby device discovery should refresh within **5–10 seconds**. |
| NFR-5 | The application shall support simultaneous communication with multiple nearby devices. |
| NFR-6 | File transfer progress shall be displayed in real time. |

---

# 5.2 Reliability Requirements

PeerMesh should continue operating correctly despite changing network conditions.

### Requirements

| ID | Requirement |
|----|-------------|
| NFR-7 | The application shall recover automatically from temporary connection failures whenever possible. |
| NFR-8 | Messages shall remain stored locally until successfully delivered or removed by the user. |
| NFR-9 | The application shall prevent message corruption during transmission. |
| NFR-10 | Unexpected application termination shall not result in permanent message loss. |

---

# 5.3 Availability Requirements

The system should remain available whenever the required hardware is enabled.

### Requirements

| ID | Requirement |
|----|-------------|
| NFR-11 | The application shall function without internet connectivity. |
| NFR-12 | The application shall remain usable whenever Bluetooth or Wi-Fi Direct is available. |
| NFR-13 | The application shall restore communication automatically after temporary interruptions whenever possible. |

---

# 5.4 Security Requirements

Security is essential because users exchange personal messages and files.

### Requirements

| ID | Requirement |
|----|-------------|
| NFR-14 | Messages shall be encrypted during transmission. |
| NFR-15 | Sensitive local data should be protected from unauthorized access. |
| NFR-16 | The application shall verify peer devices before establishing communication. |
| NFR-17 | The system shall request only the Android permissions necessary for its features. |
| NFR-18 | Users shall have control over shared files and conversations stored on their device. |

---

# 5.5 Privacy Requirements

The application shall respect user privacy.

### Requirements

| ID | Requirement |
|----|-------------|
| NFR-19 | Personal information shall remain on the user's device unless intentionally shared. |
| NFR-20 | The application shall not require internet access for normal messaging operations. |
| NFR-21 | The system shall not collect unnecessary personal information. |

---

# 5.6 Usability Requirements

PeerMesh should be easy to learn and operate.

### Requirements

| ID | Requirement |
|----|-------------|
| NFR-22 | The interface shall follow Android Material Design guidelines. |
| NFR-23 | Navigation shall remain consistent across all screens. |
| NFR-24 | Common messaging tasks should require only a few user interactions. |
| NFR-25 | Error messages shall be clear and understandable. |
| NFR-26 | The application shall support both Light Mode and Dark Mode. |

---

# 5.7 Maintainability Requirements

The system shall be easy to modify and maintain.

### Requirements

| ID | Requirement |
|----|-------------|
| NFR-27 | The application shall follow a modular software architecture. |
| NFR-28 | Source code shall be documented using meaningful comments where appropriate. |
| NFR-29 | Individual modules shall be independently testable. |
| NFR-30 | New features should be added with minimal impact on existing functionality. |

---

# 5.8 Scalability Requirements

The application should support growth in functionality and network size.

### Requirements

| ID | Requirement |
|----|-------------|
| NFR-31 | The architecture shall support future feature expansion. |
| NFR-32 | The system should accommodate additional communication capabilities such as voice and video in future versions. |
| NFR-33 | The design should support larger mesh networks within hardware limitations. |

---

# 5.9 Portability Requirements

PeerMesh should remain compatible with supported Android devices.

### Requirements

| ID | Requirement |
|----|-------------|
| NFR-34 | The application shall support Android 10 and above. |
| NFR-35 | The application should function across different Android manufacturers where Bluetooth and Wi-Fi Direct are supported. |

---

# 5.10 Compatibility Requirements

The application should integrate with Android platform services.

### Requirements

| ID | Requirement |
|----|-------------|
| NFR-36 | The application shall use Android Bluetooth APIs. |
| NFR-37 | The application shall use Android Wi-Fi Direct APIs. |
| NFR-38 | The application shall integrate with Android Notification Manager. |
| NFR-39 | The application shall use Room Database for local persistence. |

---

# 5.11 Resource Requirements

The application should use device resources efficiently.

### Requirements

| ID | Requirement |
|----|-------------|
| NFR-40 | Battery consumption shall be minimized during background operation. |
| NFR-41 | The application shall manage memory efficiently to prevent unnecessary resource usage. |
| NFR-42 | Temporary files should be cleaned up after successful transfers where appropriate. |

---

# 5.12 Backup and Recovery Requirements

Although PeerMesh is primarily offline, it should recover gracefully from failures.

### Requirements

| ID | Requirement |
|----|-------------|
| NFR-43 | Chat history stored locally should remain available after restarting the application. |
| NFR-44 | The application shall recover from unexpected shutdowns without corrupting stored data. |
| NFR-45 | Failed message transfers should allow the user to retry when possible. |

---

# 5.13 Legal and Ethical Requirements

The system should be developed responsibly.

### Requirements

| ID | Requirement |
|----|-------------|
| NFR-46 | The application shall respect user privacy. |
| NFR-47 | The application shall comply with Android platform policies. |
| NFR-48 | Open-source libraries used in the project shall comply with their respective licenses. |

---

# 5.14 Summary of Non-Functional Requirements

| Category | Requirement IDs |
|----------|-----------------|
| Performance | NFR-1 – NFR-6 |
| Reliability | NFR-7 – NFR-10 |
| Availability | NFR-11 – NFR-13 |
| Security | NFR-14 – NFR-18 |
| Privacy | NFR-19 – NFR-21 |
| Usability | NFR-22 – NFR-26 |
| Maintainability | NFR-27 – NFR-30 |
| Scalability | NFR-31 – NFR-33 |
| Portability | NFR-34 – NFR-35 |
| Compatibility | NFR-36 – NFR-39 |
| Resource Usage | NFR-40 – NFR-42 |
| Backup & Recovery | NFR-43 – NFR-45 |
| Legal & Ethical | NFR-46 – NFR-48 |

---

# Chapter Summary

This chapter defined the non-functional requirements that determine the overall quality of PeerMesh. These requirements cover performance, reliability, availability, security, privacy, usability, maintainability, scalability, portability, compatibility, efficient resource utilization, backup and recovery, and legal considerations. Together, they establish the quality standards that the system must satisfy throughout development and deployment.