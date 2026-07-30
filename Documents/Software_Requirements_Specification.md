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