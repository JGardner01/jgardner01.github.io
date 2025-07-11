---
title: "WebRTC Peer-to-Peer Communication Platform"
layout: post
date: 2024-03-22 00:00
tag: 
- university year 3
- javascript
- node.js
- html
- css
- webrtc
image: null
headerImage: false
projects: true
hidden: false 
description: "This is an overview of my third year project."
category: project
author: James Gardner 
externalLink: false
---
## Overview
This project, named Do You Expect Me To Talk?, is my third year project that I developed at Lancaster University. This project addresses key challenges in modern digital communication by creating an intuitive, no app based system that prioritises privacy, ensures universal accessibility, and provides a user friendly experience. The project provides users with a platform to engage in voice, video and text based communication as well as the ability to share files over a local network, all without requiring personal information or relying on centralised servers.

Created using HTML, CSS, JavaScript, Node.js and WebRTC, and then deployed on Heroku, the application enables multiple devices to form a Personal Area Network (PAN), allowing seamless peer to peer communication. This includes the exchange of messages, media files and real time video and voice streams. By using WebRTC to facilitate the media streams and data transfer, the system ensures that all data remains private, as it is transmitted directly between devices over a peer to peer connection without passing through a centralised servers.

**The key aims of the project focus on the following aspects:**
1.	**Functionality:** Allow users to securely create and manage a Personal Area Network (PAN) and enable communication within the network via text, voice, video and file sharing between trusted devices.
2.	**Privacy:** No personal information is required to use the application. The communication remains completely peer to peer, ensuring no data is stored on external servers.
3.	**Universal Accessibility:** A no app based system that is available to all digital devices given they have a web browser, removing the need for software installation and making the platform easily and widely accessible.
4.	**Enhanced Usability:** A user friendly interface that focuses on simple navigation and allowing the functionality to be performed effortlessly, addressing common frustrations with other third-party applications.

By focusing on these aims the project was able to provide a comprehensive, privacy focused and accessible solution to many of the complexities of modern communication systems.

<p align="center">
  <img src="../assets/projectPostContent/doYouExpectMeToTalkTYP/WebRTCConfig.png" alt="System's WebRTC Configuration" />
  <br/>
  <em>System's WebRTC Configuration</em>
</p>

## Demo
Here is a demonstration of using the platform where multiple devices (desktop, laptop and mobile) join a Personal Area Network (PAN) and interact over WebRTC peer to peer connections through text messaging, file sharing and real time video calls.
<p align="center">
    <iframe width="854" height="480" src="https://www.youtube.com/embed/6wUoPsU0N2Q?si=BgbIMbSAhIHeGntG" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>
</p>

## Project Features
#### Personal Area Network Creation and Management:
- **Dynamic Creation:** Users can easily create a Personal Area Network (PAN) by adding multiple devices into single group. This allows the added devices to securely communicate via peer to peer connections between the devices.
- **Customised PAN Names and Device Names:** PAN names are randomly generated upon creation but, users have the option to assign custom names to both the Personal Area Network (PAN) and each connected device, improving usability and identification of trusted devices. Users can also specify the device type (desktop, laptop, tablet or mobile) to provide additional clarity for device management.
- **Group Leaders and Management:** Each PAN has one device that is assigned as the leader, where the user can manage device connections and permissions. The leader has the authority to approve or reject new devices, as well as remove unwanted devices and transfer leadership.
- **Scalable:** The system is designed to support the addition of many devices to the PAN, allowing for flexible and scalable use, without performance degradation.

#### Real Time Peer To Peer Communication:
- **Voice, Video, and Text Based Communication:** The platform supports secure, real time peer to peer communication between devices, including voice and video calls, as well as text-based messaging. Users can engage in both one on one and group conversations within the PAN.
- **Direct Peer To Peer Connections:** WebRTC is used to establish direct communication links between devices, bypassing the need for a central server and ensuring fast, private communication. Video and voice calls are sent using WebRTC media streams and text based messages use WebRTC data channels.

#### File Sharing:
- **File Transfers:** Users can securely share files and media directly with other devices in the PAN via WebRTC data channels, ensuring that all transfers are peer-to-peer and remain private.
- **Support for Large Files:** The project supports the transfer of large files by dividing them into smaller chunks for efficient and reliable transmission.

#### Interface:
- **Intuitive, User Friendly Design:** The interface is designed to be clean and easy to navigate, prioritising usability. Key features such as text, video, and file sharing options are easy to access through easy to find menus.
- **Dynamic User Feedback:** When a new device attempts to join a PAN, the system provides clear, on screen notifications to the PAN leader, allowing them to promptly accept or reject the request.
- **Real Time Updates Reflected On Connected Devices:** Changes such as new device connections or change in media streams are reflected in real time across connected devices.
- **Device Recognition and Display:** Each device is represented with a custom device type icon and name, making it easier for users to manage their personal area network. This visual identification ensures the users can clearly see which device is performing specific actions within the PAN.
- **Collapsible and Adaptive Design Elements:** Elements such as video streams and chat windows can be collapsed or expanded according to user preferences, providing flexibility and ensuring the best experience regardless of the device being used.

#### No App Based System:
- **Browser Based Solution:** This project provides a fully browser based solution that eliminates the need for any additional software installation or third party applications. This ensures universal accessibility across all devices that can run a modern web browser and therefore, simplifying the user experience and reducing common security risks commonly associated with third-party applications.

#### Privacy and Security:
- **End-to-End Encryption:** WebRTC’s built-in encryption ensures that all voice, video, and data streams are fully protected from interception, safeguarding communications across peer to peer connections.
- **No Data Stored or Passed Through Centralised Servers:** The system operates on a peer to peer architecture when communicating with other devices, meaning that no personal information, communication logs, or media files are stored or pass through external servers, keeping user data private and secure.
- **No App Downloads Required:** Users can access the platform directly through their web browser, without the need to download or install any third-party applications, reducing common security risks associated with software installations.
- **No Personal Data Required:** The system does not require users to input any personal data to make use of its functionalities, maintaining privacy and ensuring that no sensitive information is shared or stored.

## System Structure
The system is designed to enable secure, real time communication through the use of WebRTC. It allows devices to form Personal Area Networks (PANs) and communicate directly without the need for central servers. The architecture of the system revolves around a client side application that utilises WebRTC, which is served by a Node.js Express server, along with a Node.js signalling server. STUN servers assist in NAT traversal and WebRTC handles encrypted peer-to-peer communication including media streams and data channels.

### Key Components
#### Client Application Server
The client application server, developed using Node.js and Express, is responsible for serving the client side application to the user when requested via a browser. This server acts as the gateway for users to access the application, delivering the necessary HTML, CSS and JavaScript files required to run the user interface and interact with the system.
#### Client Side Application
The client side application, created using HTML, CSS and JavaScript, is the user facing part of the system, allowing users to create and manage PANs, then engage in real time communication and media sharing. The application processes user input and interaction, enabling connections and communication with the signalling server through sockets. It also is responsible for creating offers, answers and ICE candidates to initiate WebRTC peer-to-peer connections with other devices enabling communication and sharing to occur.
#### Signalling Server
The Node.js signalling server is used for managing the signalling process that enables devices to exchange offers, answers and ICE candidates in order to establish WebRTC peer-to-peer connections. This server is also responsible for the creation and management of Personal Area Networks by transmitting and dealing with management messages such as new device connections, requests and device disconnects. The signalling server is used to manage PANs as it is more reliable than managing the PANs through only peer-to-peer connections, especially when handling device disconnects. Using SocketIO, the server automatically assigns user IDs, sets relevant non-personally identifiable information used later for PAN management. Importantly, no personal communication or media data is shared through the signalling server.
#### WebRTC Connections
- Real Time Encrypted Peer-To-Peer Communication: Using WebRTC ensures all communication between devices is encrypted and avoids the need for centralised servers to handle communication.
- STUN: Google’s STUN servers are used to facilitate NAT traversal, enabling the discovery of public IP addresses, allowing devices behind different networks to connect directly.
- TURN: TURN servers are not used within this project to prioritise privacy by avoiding relaying media streams and data through external servers.
- Media Streams: Voice and video streams are transmitted using WebRTC’s media stream capabilities.
- Data Channels: Text messages and file transfers are sent securely through WebRTC data channels.

### Personal Area Networks (PANs)
Personal Area Networks form a core functionality of the Do You Expect Me To Talk? system, allowing users to securely connect multiple devices within their trusted network for real time communication and data sharing. Each PAN is dynamically created and managed through the client side application and the signalling server.
#### How Personal Area Networks work:
- **Creation:** When a user loads the application or leaves another PAN, a new PAN is automatically created. This simplifies the process of connecting with other devices. Once created, the PAN Node.js server is sent a message from the client side application to generate a unique PAN ID. The Node.js server then stores information such as who the PAN leader is and if a custom name has been assigned. A PAN join code is generated and returned to the client side application allowing other devices to join.
- **Device Connections:** Devices can join a PAN by entering the unique PAN code displayed in the client side application of any PAN member. Before devices are allowed to connect and join the PAN, the requesting client application sends a request, through the signalling server, to the PAN leader, giving the user the option to approve or reject the connection. If accepted a message is sent through the signalling server telling the requesting device to create a WebRTC connection offer to all other PAN members and begin the WebRTC connection process. If rejected the requesting device is informed that their request was declined and they return back to their PAN alone.
- **Management:** Each PAN has a leader device (unless changed – the device that created the PAN), responsible for managing the network. The leader can approve or deny device connection requests as well as remove devices or transfer leadership to another device. Once connected, all devices within the PAN establish WebRTC peer-to-peer connections with all other devices, allowing them to communicate directly.
- **Real Time Updates:** Any changes in the network such as new device connections, disconnections or voice, video or text group communication are reflected across all connected devices. This dynamic update mechanism ensures seamless collaboration within the PAN.
- **Device Disconnection:** When a device leaves the PAN, the signalling server broadcasts the disconnection event to all remaining devices in the network. The disconnected device’s peer connections are gracefully closed, and its user interface elements are removed from the other devices. If the PAN leader disconnects, leadership is automatically transferred to another device within the PAN, allowing the network to remain operational without disruption. If a device disconnects unintentionally the clients socket disconnects from the signalling server and the signalling server broadcasts the message to initiate device disconnection from the PAN.

### Communication Methods
- **Voice and Video Communication:** Voice and video communication are facilitated via WebRTC media streams, which allow for real time peer-to-peer calls between devices. Peer-to-peer connections may need to be renegotiated after enabling/disabling streams, ensuring that the connections remain seamless.
- **Text Based Communication:** Text messaging is facilitated through WebRTC data channels, which are JSONified to allow structured message passing.
- **File Sharing:** File transfers are handled through WebRTC data channels. To support the transfer of large files, files are broken down into chunks then sent across the peer connection and reassembled on the receiving end after every chunk has been received.

### Deployment
The system is deployed on Heroku, utilising mono-repo build packs to manage both the frontend and backend within a single repository. This setup streamlines the deployment process, making it easier to push updates and manage both aspects of the application from one central location. The system also uses Node.js build packs to facilitate the deployment of the Node.js Express server and then Node.js signalling server.

## Conclusion
The project successfully demonstrates a privacy-focused, no-app communication system built on modern web technologies like WebRTC, Node.js, and Express. By creating secure and dynamic Personal Area Networks (PANs), the system allows users to communicate in real time via voice, video, text, and file sharing, without the need for centralized servers or personal data storage. Overall, this project has deepened my understanding of JavaScript and WebRTC and expanded my knowledge about project development.
