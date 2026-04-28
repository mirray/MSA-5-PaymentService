| Current State      | Next State             | Trigger                      |
|--------------------|------------------------|------------------------------|
| CREATED            | HOLD                   | PaymentHold                  |
| CREATED            | UNSUFFICIENT_FUNDS [P] | PaymentHoldRejected          |
| HOLD               | AWAITING_APPROVE       | PaymentCheck                 |
| AWAITING_APPROVE   | APPROVED               | AntiFraudApproved            |
| APPROVED           | COMPLETED [P]          | PaymentCompleted             |
| AWAITING_APPROVE   | REJECTED               | AntiFraudDenied              |
| AWAITING_APPROVE   | PENDING_CHECK          | AntiFraudManualCheckRequired |
| PENDING_CHECK      | APPROVED               | AntiFraudApproved            |
| PENDING_CHECK      | REJECTED               | AntiFraudDenied              |
| PENDING_CHECK      | REJECTED               | AntiFraudTimedOut            |
| APPROVED           | DENIED                 | PaymentCompletionRejected    |
| DENIED             | REVERTED [P]           | PaymentHoldReleased          |
| REJECTED           | REVERTED [P]           | PaymentHoldReleased          |
