Transaction Flow Design
Example Scenario

User A (KPay)

ပို့ငွေ

10,000 MMK

↓

User B (WavePay)

Flow
1. Client sends transfer request

        |
        v

2. Gateway validates request

        |
        v

3. Switch creates transaction

Status:
PENDING

        |
        v

4. Routing Engine identifies receiver wallet

        |
        v

5. Saga starts


        |
        v

6. Debit KPay

Status:
DEBITED


        |
        v

7. Credit WavePay

Status:
COMPLETED


        |
        v

8. Response returned

Failure Flow
Debit Success

       |

Credit Failed

       |

Compensation

       |

Reverse Debit

       |

Transaction = REVERSED