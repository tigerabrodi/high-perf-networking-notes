# Chapter 4: Transport Layer Security (TLS)

## Core TLS Principles

TLS (Transport Layer Security) is designed with three primary security goals:

1. **Encryption** - Protecting data from eavesdropping
2. **Authentication** - Verifying the identity of communicating parties
3. **Data Integrity** - Ensuring data hasn't been tampered with during transmission

## The Foundation of TLS

### Cryptographic Keys and the TLS Handshake

TLS relies on a combination of cryptographic techniques. The handshake process establishes secure parameters before actual data transmission begins.

### Message Authentication Code (MAC)

MACs verify data integrity by creating a cryptographic checksum that can detect if any modifications occurred during transit.

## HTTPS Dominance

HTTPS (HTTP over TLS) has become the standard for web communication, with most major websites and services requiring it. This shift provides security benefits but adds complexity and potential performance costs.

## How TLS Works with TCP

TLS runs on top of TCP, requiring a complete TCP connection before the TLS handshake can begin. This means:

1. TCP three-way handshake completes first
2. Then the TLS handshake begins
3. Only after both complete can application data be exchanged

## TLS Handshake Process

When a TCP connection is established, the TLS handshake follows:

1. Client sends specifications in plaintext (supported cipher suites, TLS version)
2. Server selects the TLS protocol version and cipher suite
3. Authentication and key exchange occur

## Key Exchange Methods

### RSA

Traditional approach where the server's public key directly encrypts session information.

### Diffie-Hellman

More modern approach allowing secure key agreement without transmitting the actual key. Provides "forward secrecy" which RSA doesn't.

## Performance Considerations

TLS involves trade-offs between security and performance:

- **Public Key Cryptography** (asymmetric): Secure but computationally expensive
- **Symmetric Key Cryptography**: Much faster but requires securely exchanging keys first

TLS uses both: asymmetric for the initial handshake, then symmetric for ongoing data transmission.

## TLS Optimization Techniques

### ALPN (Application Layer Protocol Negotiation)

Allows protocol negotiation during the TLS handshake, avoiding additional roundtrips to determine which protocol to use (e.g., HTTP/1.1 vs HTTP/2).

### Server Name Indication (SNI)

Enables a server to host multiple TLS certificates on the same IP address by having the client specify which hostname it's connecting to during the handshake.

### Session Management

- **Session Identifiers**: Allow resuming previous connections without repeating the full handshake
- **Session Tickets**: Enable stateless session resumption

### Certificate Handling

- **Certificate Revocation**: Process for invalidating compromised certificates
- **Online Certificate Status Protocol (OCSP)**: Real-time verification of certificate validity

## TLS Performance Optimization Best Practices

1. **Enable 1-RTT TLS Handshakes**: Minimize connection setup time
2. **Optimize Connection Reuse**: Avoid unnecessary handshakes
3. **Implement Session Caching and Stateless Resumption**: Speed up reconnections
4. **Optimize TLS Record Size**: Balance between latency and throughput
