# System Architecture

# PeerMesh
### Offline Mesh Communication System

**Version:** 1.0

---

# 1. Introduction

## 1.1 Purpose

This document describes the overall architecture of the PeerMesh system. It explains how the application is organized into different layers, modules, and components, and how these components interact to provide secure offline communication through a decentralized mesh network.

The architecture is designed to be modular, scalable, maintainable, and extensible, allowing future enhancements such as cloud synchronization, voice communication, and cross-platform support.

---

# 2. Architectural Goals

The architecture has been designed with the following goals:

- Modular design
- Scalability
- Maintainability
- Security
- Offline-first communication
- Low resource consumption
- High reliability
- Easy testing
- Extensibility

---

# 3. Architectural Style

PeerMesh follows a layered architecture with modular components.

```
+------------------------------------------------+
|                Presentation Layer              |
|          (Activities / Fragments / UI)         |
+------------------------------------------------+
|               ViewModel Layer                  |
|          (Business State Management)           |
+------------------------------------------------+
|              Repository Layer                  |
|     (Data Coordination & Abstraction)          |
+------------------------------------------------+
|          Communication Layer                   |
| Bluetooth | Wi-Fi Direct | Mesh Routing        |
+------------------------------------------------+
|               Database Layer                   |
|             Room Local Database                |
+------------------------------------------------+
|             Android Hardware Layer             |
| Bluetooth | Wi-Fi | Storage | Notifications    |
+------------------------------------------------+
```

---

# 4. High-Level Architecture

The system consists of five major layers:

1. Presentation Layer
2. Business Logic Layer
3. Communication Layer
4. Data Layer
5. Hardware Layer

Each layer has clearly defined responsibilities and communicates only with adjacent layers.

---

# 5. Presentation Layer

## Responsibilities

- Display user interface
- Receive user input
- Display nearby devices
- Display chats
- Display notifications
- Display connection status

### Components

- Splash Screen
- Home Screen
- Chat Screen
- Group Screen
- Nearby Devices Screen
- Settings Screen
- Profile Screen

---

# 6. Business Logic Layer

This layer contains the application's core logic.

Responsibilities include:

- Message processing
- Route selection
- User management
- Group management
- File transfer coordination
- Notification handling

Main components:

- Chat Manager
- Device Manager
- Routing Manager
- Group Manager
- File Manager
- Settings Manager

---

# 7. Communication Layer

This is the heart of PeerMesh.

It handles communication between devices.

Components include:

## Bluetooth Manager

Responsibilities

- Device discovery
- Connection establishment
- Small message transfer

---

## Wi-Fi Direct Manager

Responsibilities

- High-speed communication
- File transfer
- Peer discovery

---

## Mesh Routing Engine

Responsibilities

- Route discovery
- Multi-hop routing
- Relay node selection
- Route maintenance

---

## Connection Manager

Responsibilities

- Establish connections
- Maintain active connections
- Disconnect inactive devices
- Automatic reconnection

---

# 8. Data Layer

Stores all application data locally.

Uses:

- Room Database

Tables include:

- Users
- Devices
- Chats
- Messages
- Groups
- Group Members
- Shared Files
- Settings

Responsibilities

- CRUD operations
- Offline persistence
- Cache management

---

# 9. Hardware Layer

PeerMesh directly interacts with Android hardware.

Components

- Bluetooth Adapter
- Wi-Fi Adapter
- Storage
- Camera
- Gallery
- Notification Manager

---

# 10. Core Modules

## User Module

Functions

- Create Profile
- Edit Profile
- Manage Identity

---

## Discovery Module

Functions

- Bluetooth Discovery
- Wi-Fi Discovery
- Device Availability

---

## Messaging Module

Functions

- Send Messages
- Receive Messages
- Store Messages

---

## Routing Module

Functions

- Route Discovery
- Multi-Hop Routing
- Route Optimization

---

## File Sharing Module

Functions

- Send Images
- Send Videos
- Send Documents

---

## Security Module

Functions

- Encryption
- Authentication
- Secure Storage

---

# 11. Data Flow

```
User

↓

UI

↓

ViewModel

↓

Repository

↓

Communication Layer

↓

Bluetooth / Wi-Fi Direct

↓

Nearby Device

↓

Receiver
```

---

# 12. Message Flow

```
Sender

↓

Create Message

↓

Encrypt

↓

Find Route

↓

Relay Device

↓

Relay Device

↓

Destination

↓

Decrypt

↓

Store Message

↓

Display Chat
```

---

# 13. Mesh Communication Flow

```
A

↓

B

↓

C

↓

D
```

If A cannot directly reach D, the message travels through B and C.

Each intermediate device acts as a relay node.

---

# 14. Security Architecture

PeerMesh implements multiple security mechanisms.

### Authentication

- Device identity verification

### Encryption

- Secure message transmission

### Storage Protection

- Protected local database

### Permission Management

- Bluetooth
- Nearby Devices
- Wi-Fi
- Notifications
- Storage

---

# 15. Error Handling

The architecture supports graceful error handling.

Examples:

- Connection timeout
- Device unavailable
- Bluetooth disabled
- File transfer interruption
- Route failure

Recovery mechanisms:

- Retry connection
- Route recalculation
- Message queue
- Automatic reconnection

---

# 16. Scalability

The architecture supports future additions including:

- Voice calling
- Video calling
- Cloud synchronization
- Desktop client
- iOS application
- Smartwatch support
- Emergency broadcast

---

# 17. Deployment Architecture

```
+----------------------+
|   Android Device A   |
|      PeerMesh        |
+----------+-----------+
           |
Bluetooth / Wi-Fi Direct
           |
+----------+-----------+
|   Android Device B   |
|      PeerMesh        |
+----------+-----------+
           |
Bluetooth / Wi-Fi Direct
           |
+----------+-----------+
|   Android Device C   |
|      PeerMesh        |
+----------------------+
```

Every device acts as both:

- Client
- Relay Node

No central server is required for core communication.

---

# 18. Architectural Advantages

- Fully decentralized
- Offline-first design
- Modular components
- Easy maintenance
- High scalability
- Secure communication
- Reduced dependency on infrastructure
- Better fault tolerance

---

# 19. Conclusion

The PeerMesh architecture follows a modular layered design that separates presentation, business logic, communication, data management, and hardware interaction. This structure simplifies development, testing, and maintenance while providing a scalable foundation for future enhancements. By combining Bluetooth, Wi-Fi Direct, and mesh routing, PeerMesh delivers reliable offline communication without relying on centralized infrastructure.