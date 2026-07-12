# BurmaSwitch Architecture Decisions

## Decision 001: Use PostgreSQL as Primary Database

### Context

BurmaSwitch handles financial transactions where data consistency and transaction integrity are critical.

### Decision

We choose PostgreSQL as the primary database.

### Reason

- Strong ACID transaction support
- Reliable concurrency control
- Row-level locking support
- Suitable for financial data
- Supports complex SQL queries

### Alternatives Considered

MongoDB

Reason rejected:
- Less suitable for strict financial transaction consistency
- Relational ledger structure fits better with SQL databases


Status:
Accepted

## Decision 002: Use FastAPI as Backend Framework

### Context

The system requires multiple independent backend services.

### Decision

FastAPI will be used for all backend microservices.

### Reason

- Modern Python framework
- Async support
- High performance
- Automatic API documentation

### Alternatives Considered

Django

Reason rejected:
- More monolithic
- Less suitable for lightweight microservices

Status:
Accepted

## Decision 003: Use Raw SQL for Financial Operations

### Context

Financial systems require precise control over queries and transactions.

### Decision

Critical ledger and balance operations will use Raw SQL.

### Reason

- Better understanding of database operations
- Explicit query control
- Easier optimization
- Suitable for financial calculations

### Alternatives Considered

Full ORM approach

Reason rejected:
- Hides important SQL behavior
- Less control over critical transaction logic

Status:
Accepted

## Decision 004: Use Saga Pattern for Distributed Transactions

### Context

A transaction involves multiple independent wallet services.

### Decision

Saga Pattern will manage distributed transaction workflows.

### Reason

- Handles partial failures
- Supports compensation actions
- Suitable for microservice architecture

### Alternatives Considered

Two-phase commit (2PC)

Reason rejected:
- Higher coupling
- Less flexible in distributed systems

Status:
Accepted

## Decision 005: Wallet Services are Simulation Services

### Context

The main goal is building interoperability infrastructure, not rebuilding complete wallet applications.

### Decision

KPay and WavePay services will simulate core wallet behavior only.

### Included

- Account management
- Balance checking
- Debit
- Credit
- Ledger

### Excluded

- QR payment
- KYC
- Merchant features
- User interface

### Reason

Focus development effort on Central Switch architecture.

Status:
Accepted

## Decision 006: Use Monorepo Structure

### Context

Multiple services share common libraries and documentation.

### Decision

All services will exist in a single repository.

### Reason

- Easier dependency management
- Shared code reuse
- Easier project management

Alternatives Considered:

Multiple repositories

Reason rejected:
- More complex for a single developer project

Status:
Accepted

## Decision 007: Use Celery for Background Processing

### Context

Long-running transaction workflows should not block HTTP requests.

### Decision

Transaction execution will use background workers.

### Reason

- Better reliability
- Retry support
- Decoupled processing

Status:
Accepted