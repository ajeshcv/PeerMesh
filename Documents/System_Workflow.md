# System Workflow

# PeerMesh
### Offline Mesh Communication System

**Version:** 1.0

---

# 1. Introduction

## 1.1 Purpose

This document describes the operational workflow of the PeerMesh system. It explains how the application behaves from launch to message delivery, including device discovery, mesh formation, routing, communication, file sharing, and error handling.

The workflow illustrates the sequence of actions performed by users and the internal operations carried out by the application.

---

# 2. Overall Workflow

The complete system workflow is shown below.

```
Launch Application
        │
        ▼
Load User Profile
        │
        ▼
Initialize Bluetooth & Wi-Fi Direct
        │
        ▼
Request Required Permissions
        │
        ▼
Scan Nearby Devices
        │
        ▼
Build Mesh Network
        │
        ▼
Display Nearby Devices
        │
        ▼
User Selects Device
        │
        ▼
Establish Connection
        │
        ▼
Send / Receive Messages
        │
        ▼
Share Files (Optional)
        │
        ▼
Maintain Connection
        │
        ▼
Disconnect
```

---

# 3. Application Startup Workflow

### Step 1 – Launch Application

The user launches PeerMesh.

The application performs the following tasks:

- Initialize application components
- Load local configuration
- Load saved profile
- Initialize local database

---

### Step 2 – Load User Profile

The application checks whether a profile already exists.

If no profile exists:

```
Create Profile
```

Otherwise:

```
Continue to Home Screen
```

---

### Step 3 – Permission Verification

PeerMesh checks the required Android permissions.

Permissions include:

- Bluetooth
- Nearby Devices
- Wi-Fi
- Notifications
- Storage (for file sharing)

If any permission is missing, the application requests it before continuing.

---

# 4. Device Discovery Workflow

After initialization:

```
Start Bluetooth Scan

↓

Start Wi-Fi Direct Discovery

↓

Detect Nearby Devices

↓

Update Device List

↓

Refresh Every Few Seconds
```

Each discovered device is verified to determine whether it is running PeerMesh before it is shown to the user.

---

# 5. Mesh Network Formation

When two or more PeerMesh devices are available:

```
Device A

↓

Device B

↓

Device C

↓

Device D
```

Every device can:

- Send messages
- Receive messages
- Relay messages

No central server is required.

---

# 6. Connection Workflow

When the user selects a nearby device:

```
Select Device

↓

Send Connection Request

↓

Peer Accepts

↓

Authentication

↓

Connection Established

↓

Ready for Communication
```

If the connection fails:

```
Retry

or

Select Another Device
```

---

# 7. Message Sending Workflow

```
Open Chat

↓

Type Message

↓

Press Send

↓

Encrypt Message

↓

Find Best Route

↓

Transmit Message

↓

Relay Through Intermediate Devices (if required)

↓

Receiver Gets Message

↓

Decrypt

↓

Store in Database

↓

Display Chat

↓

Send Delivery Confirmation
```

---

# 8. Multi-Hop Routing Workflow

If the destination is outside direct communication range:

```
Sender

↓

Relay Node 1

↓

Relay Node 2

↓

Relay Node 3

↓

Receiver
```

Each relay node:

- Receives the message
- Verifies the route
- Forwards the message
- Does not modify the message content

---

# 9. File Sharing Workflow

```
Open Chat

↓

Select Attachment

↓

Choose File

↓

Compress (if required)

↓

Encrypt

↓

Transfer

↓

Relay Through Mesh

↓

Receiver Downloads File

↓

Verify Integrity

↓

Store File
```

Supported file types:

- Images
- Videos
- Audio
- Documents
- PDF files

---

# 10. Group Messaging Workflow

```
Create Group

↓

Select Members

↓

Create Group Database Entry

↓

Send Invitation

↓

Members Accept

↓

Group Created

↓

Broadcast Messages

↓

Members Receive Messages
```

---

# 11. Message Delivery Workflow

The system tracks the status of each outgoing message.

Possible states:

```
Pending

↓

Sent

↓

Delivered

↓

Read
```

If delivery is not immediately possible:

- The message remains queued locally.
- The system retries delivery when a valid route becomes available.

---

# 12. Error Handling Workflow

### Bluetooth Disabled

```
Detect Disabled Bluetooth

↓

Prompt User

↓

Enable Bluetooth

↓

Continue
```

---

### Wi-Fi Direct Disabled

```
Detect Disabled Wi-Fi

↓

Prompt User

↓

Enable Wi-Fi Direct

↓

Continue
```

---

### Connection Failure

```
Retry Connection

↓

Search Alternate Route

↓

Queue Message

↓

Notify User
```

---

### File Transfer Failure

```
Pause Transfer

↓

Retry

↓

Resume

↓

Notify User
```

---

# 13. Database Workflow

Whenever a message is sent or received:

```
Create Message Object

↓

Validate

↓

Store in Room Database

↓

Update Chat History

↓

Refresh UI
```

---

# 14. Notification Workflow

When a new message arrives:

```
Receive Message

↓

Store Message

↓

Generate Notification

↓

Display Notification

↓

User Opens Chat

↓

Mark as Read
```

---

# 15. Shutdown Workflow

When the application closes:

The system:

- Saves unsynchronized data
- Closes active connections
- Releases Bluetooth resources
- Releases Wi-Fi Direct resources
- Saves settings
- Terminates background services gracefully

---

# 16. Exception Handling

The application handles unexpected situations gracefully.

Examples:

- Lost connection
- Message timeout
- Relay node unavailable
- File corruption
- Insufficient storage
- Permission denied

Recovery mechanisms include automatic retries, message queuing, route recalculation, and user notifications.

---

# 17. Complete Workflow Summary

```
Launch App
      │
      ▼
Load Profile
      │
      ▼
Request Permissions
      │
      ▼
Initialize Bluetooth & Wi-Fi Direct
      │
      ▼
Discover Nearby Devices
      │
      ▼
Create Mesh Network
      │
      ▼
Connect to Peer
      │
      ▼
Send / Receive Messages
      │
      ▼
Share Files (Optional)
      │
      ▼
Store Data Locally
      │
      ▼
Display Notifications
      │
      ▼
Close Application
```

---

# 18. Conclusion

The PeerMesh workflow demonstrates how the application enables decentralized offline communication using Bluetooth and Wi-Fi Direct. Through automatic device discovery, mesh network formation, multi-hop routing, secure messaging, and local data storage, the system provides reliable communication without requiring internet connectivity. The modular workflow also supports future enhancements while maintaining a clear and maintainable operational design.