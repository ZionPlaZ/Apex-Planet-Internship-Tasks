#### Cybersecurity Fundamentals & Threat Landscape

- **The CIA Triad**
    
    - **Confidentiality:** Ensures sensitive data is inaccessible to unauthorized entities. Mechanisms include symmetric/asymmetric encryption (AES-256), access control lists (ACLs), role-based access control (RBAC), and data classification.
        
    - **Integrity:** Guarantees data has not been altered, tampered with, or forged in transit or storage. Mechanisms include cryptographic hash functions (SHA-256), digital signatures, and file integrity monitoring (FIM).
        
    - **Availability:** Ensures systems, services, and data are consistently accessible to authorized users when needed. Mechanisms include high availability clustering, Redundant Arrays of Independent Disks (RAID), load balancing, off-site backups, and DDoS mitigation strategies.
        
- **Core Threat Vectors & Taxonomy**
    
    - **Phishing:** Social engineering attacks where attackers impersonate legitimate entities via email or messaging to deceive targets into revealing credentials, executing malicious payloads, or transferring assets.
        
    - **Malware:** Malicious software engineered to compromise, damage, or gain unauthorized control over an endpoint (includes Trojans, Rootkits, Spyware, and Worms).
        
    - **DDoS (Distributed Denial of Service):** Exhausting host or network bandwidth and compute resources by swarming the target with coordinated packet floods (SYN floods, UDP amplification, HTTP flood) from distributed botnets.
        
    - **SQL Injection (SQLi):** Exploiting unvalidated user input strings within SQL database queries, allowing attackers to bypass authentication, read or modify database records, and execute administrative operations.
        
    - **Brute Force:** Systematic submission of password and passphrase combinations until the correct cryptographic key or credential match is discovered.
        
    - **Ransomware:** Cryptovirological malware that systematically encrypts a victim’s filesystem and demands ransom payments in exchange for decryption keys.
        
- **Primary Attack Vectors**
    
    - **Social Engineering:** Pretexting, baiting, shoulder surfing, and credential harvesting that exploit human psychology rather than software flaws.
        
    - **Wireless Attacks:** Exploitation of weak Wi-Fi encryption (WEP/WPA2-PSK handshake capture), Rogue Access Points (Evil Twin), deauthentication floods, and packet injection.
        
    - **Insider Threats:** Malicious or negligent behavior from verified actors within an organization possessing legitimate system access.
        

#### Networking Architecture & Protocols

- **The OSI 7-Layer Model vs. TCP/IP Stack**
    

| **Layer #** | **OSI Layer** | **Primary Function**                                  | **Data Unit (PDU)**            | **Core Protocols / Standards**                  |
| ----------- | ------------- | ----------------------------------------------------- | ------------------------------ | ----------------------------------------------- |
| **7**       | Application   | Network access for end-user applications              | Data                           | HTTP, HTTPS, DNS, SSH, FTP, SMTP                |
| **6**       | Presentation  | Syntax conversion, data compression, encryption       | Data                           | TLS/SSL, ASCII, JPEG, MPEG                      |
| **5**       | Session       | Inter-host communication management                   | Data                           | RPC, NetBIOS, PPTP                              |
| **4**       | Transport     | End-to-end connections, reliability, flow control     | Segment (TCP) / Datagram (UDP) | TCP (connection-oriented), UDP (connectionless) |
| **3**       | Network       | Logical addressing, routing across internetworks      | Packet                         | IPv4, IPv6, ICMP, IPsec, OSPF, BGP              |
| **2**       | Data Link     | Physical addressing, node-to-node frame transfer      | Frame                          | Ethernet (802.3), Wi-Fi (802.11), ARP, MAC      |
| **1**       | Physical      | Binary transmission over physical transmission medium | Bit                            | RJ-45, Cat6, Fiber Optic, RF signals            |

- **DNS Resolution Flow:**
    
    1. Client queries local DNS resolver cache (`/etc/hosts`, browser cache).
        
    2. Resolving Name Server queries Root DNS Servers (`.`).
        
    3. Root refers query to Top-Level Domain (TLD) servers (e.g., `.com`, `.in`).
        
    4. TLD refers to the Authoritative Name Server managing the specific domain record.
        
    5. Authoritative server returns resource record (e.g., `A` record with IPv4 address) back through the resolver to the client.
        
- **HTTP vs. HTTPS (TLS Handshake):**
    
    - **HTTP (Port 80):** Transmits plaintext data vulnerable to packet interception and eavesdropping.
        
    - **HTTPS (Port 443):** Encapsulates HTTP within an encrypted Transport Layer Security (TLS) channel. The client and server perform asymmetric key exchange (RSA or ECDHE) to agree on cipher suites and establish a temporary symmetric session key for high-speed symmetric data encryption.
        
- **IP Addressing, Subnetting, and NAT:**
    
    - **IPv4 Subnetting:** Divides network addresses into subnetworks using a subnet mask. In a `/24` network (`255.255.255.0`), 8 bits remain for host addressing ($2^8 - 2 = 254$ usable hosts).
        
    - **Network Address Translation (NAT):** Translates private RFC 1918 IPv4 ranges (`10.0.0.0/8`, `172.16.0.0/12`, `192.168.0.0/16`) to a single public IP address via Port Address Translation (PAT), preserving the global IPv4 address space.
        

#### Cryptographic Architectures

- **Symmetric vs. Asymmetric Encryption**
    
    - **Symmetric Encryption (e.g., AES-256, ChaCha20):** Employs a single secret key for both data encryption and decryption. Very fast computationally; requires secure out-of-band key distribution.
        
    - **Asymmetric Encryption (e.g., RSA-2048/4096, ECC/Ed25519):** Uses a cryptographically linked key pair: a public key for encryption and a private key for decryption. Solves key distribution challenges but incurs high compute overhead.
        
- **Cryptographic Hashing:**
    
    - One-way deterministic mathematical algorithms mapping arbitrary data inputs to fixed-size bitstrings.
        
    - **MD5:** 128-bit hash. Cryptographically broken due to collision vulnerabilities.
        
    - **SHA-256:** 256-bit hash (part of SHA-2 family). Standard for zero-knowledge data integrity verification, password hashing (with salts), and digital signatures.
        
- **Public Key Infrastructure (PKI) & Digital Certificates:**
    
    - X.509 digital certificates bind a public key to an entity’s identity, signed cryptographically by a trusted Certificate Authority (CA) to prevent Man-in-the-Middle (MitM) spoofing.