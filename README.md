# BurmaSwitch

## FinTech P2P Interoperability Switch Simulator

![Project Status](https://img.shields.io/badge/status-in%20development-blue)

---

## Overview

BurmaSwitch is a production-inspired FinTech P2P interoperability switch simulator designed to demonstrate how independent digital wallet systems can securely communicate and process cross-wallet transactions through a centralized switching infrastructure.

The project simulates a payment network layer that connects multiple wallet providers and manages transaction routing, security, distributed transaction processing, and financial reconciliation.

The main focus of this project is not building a complete wallet application, but designing and implementing a reliable payment switching architecture similar to real-world financial infrastructure.

---

# Problem Statement

Digital payment ecosystems usually consist of multiple independent wallet providers. Without an interoperability layer, users from different platforms cannot easily transfer value between different wallet networks.

Globally, payment switches solve this problem by providing a secure transaction routing and processing infrastructure between financial systems.

BurmaSwitch aims to simulate such an interoperability platform by implementing:

- Secure wallet communication
- Cross-wallet transaction routing
- Distributed transaction management
- Failure recovery mechanisms
- Ledger integrity
- Transaction reconciliation

---

# Project Objectives

The main objectives of BurmaSwitch are:

- Build a centralized P2P payment switching engine
- Understand financial transaction processing architecture
- Implement distributed transaction patterns
- Handle failures in distributed systems
- Maintain transaction consistency and integrity
- Apply production-level backend engineering practices

---

# System Architecture

High-level architecture:

                Client
                  |
                  |
            API Gateway
                  |
                  |
         Central Switch Engine
                  |
    -----------------------------
    |                           |
    |                           |
KPay Wallet Simulator WavePay Wallet Simulator
    |
    |
PostgreSQL + Redis + Celery
    |
    |
Reconciliation Service


---

# Core Components

## API Gateway

Responsible for:

- Request authentication
- HMAC signature verification
- Rate limiting
- Request logging
- Request routing


## Central Switch Engine

The core component of BurmaSwitch.

Responsibilities:

- Transaction routing
- Wallet discovery
- Transaction lifecycle management
- Saga orchestration
- Idempotency handling


## Wallet Simulators

Simulated wallet services representing independent payment providers.

Implemented features:

- Account management
- Balance inquiry
- Debit operation
- Credit operation
- Ledger management


## Reconciliation Service

Responsible for:

- Transaction verification
- Ledger comparison
- Detecting financial inconsistencies

---

# Technology Stack

## Backend

- Python
- FastAPI

## Database

- PostgreSQL

## Cache

- Redis

## Background Processing

- Celery

## Containerization

- Docker

## Testing

- Pytest
- Locust

## Documentation

- Markdown
- Mermaid
- OpenAPI / Swagger

---

# Key Engineering Concepts

This project demonstrates:

## Financial Data Management

- Double-entry ledger
- Decimal precision handling
- Database constraints


## Distributed Systems

- Saga Pattern
- Compensation transactions
- Async processing
- Retry mechanisms


## Reliability

- Idempotency
- Concurrency control
- Failure recovery


## Security

- HMAC authentication
- Request validation
- Secure communication


## Observability

- Structured logging
- Transaction tracing
- Error tracking

---

# Project Structure
burmaswitch/

├── gateway/
│
├── central-switch/
│
├── wallet-kpay/
│
├── wallet-wavepay/
│
├── shared-libs/
│
├── reconciliation-service/
│
├── infrastructure/
│
├── docs/
│
└── README.md


---

# Development Status

Currently under active development.

Completed:

- Project architecture design
- Technology selection
- Documentation foundation


Upcoming:

- Environment setup
- Database implementation
- Wallet simulator development
- Switch engine implementation
- Distributed transaction workflow

---

# Scope Limitations

This project is a simulation and does not implement:

- Real money processing
- Banking integration
- KYC verification
- AML monitoring
- Mobile applications
- Production payment certification

---

# Learning Goals

Through this project, the developer aims to gain practical experience in:

- FinTech backend architecture
- Payment switching systems
- Distributed transaction design
- Database engineering
- Secure API development
- Production software engineering practices

---

# Documentation

Detailed documentation:

- [Problem Statement](docs/01-problem-statement.md)
- [Project Scope](docs/02-scope.md)
- [Architecture Design](docs/03-architecture.md)
- [Transaction Flow](docs/04-transaction-flow.md)
- [Database Design](docs/05-database-design.md)
- [Technology Stack](docs/06-technology-stack.md)
- [Architecture Decisions](docs/decisions.md)

---

# License

This project is created for educational and engineering learning purposes.