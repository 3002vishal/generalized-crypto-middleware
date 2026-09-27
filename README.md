# Generalized Crypto Middleware

A **Spring Boot PKCS#11 REST API** that exposes cryptographic-token operations through a structured backend service.

## Features

- Discover PKCS#11 vendors and connected tokens
- Login/logout and session handling
- Key-pair generation
- CSR generation
- Certificate enrollment workflows
- Private-key discovery
- Digital signing operations
- REST endpoints for token and cryptographic operations

## Tech Stack

- Java 17
- Spring Boot 3.5
- JNA
- Bouncy Castle
- Maven
- PKCS#11
- REST APIs

## Architecture

```text
REST Controller
      |
      v
Service Layer
      |
      v
PKCS#11 Manager / JNA
      |
      v
Vendor PKCS#11 Library
      |
      v
Cryptographic Token / HSM
```

## Main API Areas

- Token discovery
- Login / logout
- Key generation
- CSR generation
- Enrollment
- Signing

## Build & Run

```bash
./mvnw spring-boot:run
```

or:

```bash
mvn spring-boot:run
```

## Security

Token PINs and other secrets should be handled only in memory for the shortest possible time and must never be committed to source control. Production deployments should also restrict local API access and validate the PKCS#11 library being loaded.

## Purpose

The project explores how **Java/Spring Boot applications can provide a clean service layer over PKCS#11 hardware-token functionality**.
