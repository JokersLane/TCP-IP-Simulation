# HTTP-SWISS-CHEESE inc.

Members of this team are:

Joseph Woller, 
Keegan Eggert, 
Lane Brickman

# Network Infrastructure & TCP/IP Stack Simulator (C++)
A complete, five-layer TCP/IP protocol stack simulation tool engineered from scratch in C++ using Visual Studio 2022. This application models the end-to-end journey of network data encapsulation, illustrating how an HTTP request transforms into raw physical signals to traverse a network.

## Project Overview
This software acts as a comprehensive testing and educational tool to study the behavior of individual network components under varying conditions. It programmatically simulates the architectural boundaries, processing behaviors, and information flow between the core networking layers.

### **The 5-Layer Stack Simulation:**
1. **Application Layer:** Parses input HTTP data to handle standard request methods.
2. **Transport (TCP) Layer:** Manages port assignments, tracking variables, and TCP segment headers.
3. **Network Layer:** Handles IPv4 packet creation and source/destination IP routing.
4. **Data Link Layer:** Implements Ethernet (802.3) frame structures and MAC addressing.
5. **Physical Layer:** Executes object serialization to output raw transmitted signals.

# My Role & Contributions
This project was a collaborative team effort where the development responsibilities were divided cleanly by architecture layers. **I personally owned the implementation of the Application Layer and the Transport (TCP) Layer.**

### **Key Features I Implemented:**
* **HTTP File Parser:** Built robust logic to read formatted files, parse request data, and successfully process and error-handle HTTP GET and POST request message objects.
* **Queue-Based Message Buffering:** Designed a custom buffer using a thread-safe Queue structure to fluidly manage communication, sequencing, and notifications between the Application and Transport processes.
* **Dynamic Port Generation:** Coded mechanisms to automatically generate and validate unique source and destination port numbers (greater than 1024) within compliant network ranges.
* **TCP Segment Encapsulation:** Programmed the complete structural creation of the standard TCP segment header—initializing fields for sequence numbers, acknowledgment numbers, data offsets, flags, window sizes, and checksums—and wrapped the HTTP payload safely inside.
* 
## Tech Stack & Environment
* **Language:** C++
* **IDE:** Microsoft Visual Studio 2022
* **Architecture:** Object-Oriented Programming (OOP), Custom Buffers (Queues/Maps)
* **Standards Modeled:** HTTP, TCP, IPv4, Ethernet (802.3)
---
## Implementation Pipeline (How Data Flows)
1. **Application Layer** processes a GET/POST request and places the message object into the queue buffer.
2. **TCP Layer** retrieves the payload, assigns random valid ports, constructs the TCP segment header, and pushes it to the next buffer.
3. **Network Layer** encapsulates the segment with IPv4 header fields and source/destination IP addresses.
4. **Data Link Layer** attaches MAC addressing and packages the data into an Ethernet/Wi-Fi frame structure.
5. **Physical Layer** serializes the entire framework, translating the binary packet into hexadecimal data, and outputs it to a local text log file.
