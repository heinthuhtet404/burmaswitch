System Architecture Design
High Level Architecture

                         Client
                           |
                           |
                    API Gateway
                           |
             ---------------------------
             |
             |
       Central Switch Engine
             |
    -------------------------
    |                       |
    |                       |
KPay Simulator       WavePay Simulator
    |                       |
PostgreSQL            PostgreSQL


             |
             |
          Redis
             |
          Celery
             |
       Background Workers


             |
             |
Reconciliation Service


Component Responsibilities
1. Gateway

တာဝန်:

API Entry Point
Authentication
Rate Limit
Request Logging
Request ID Generation
2. Central Switch

ဒီ Project ရဲ့ Main Brain

တာဝန်:

Transaction Routing
Transaction State Management
Saga Orchestration
Idempotency
Partner Communication
3. Wallet Simulator

တာဝန်:

Account Management
Debit
Credit
Ledger
4. Reconciliation Service

တာဝန်:

Daily checking
Ledger comparison
Mismatch detection