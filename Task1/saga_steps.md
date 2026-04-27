| Transaction      | Description                                | Type              | Compensation     |
|------------------|--------------------------------------------|-------------------|------------------|
| Request_Payment  | Requests payment for order                 | Compensatable (T) | Notify_Unsuccess |
| Hold_Payment     | Hold funds from customer to seller         | Compensatable (T) | Release_Payment  |
| Analyze_Payment  | Send payment request to anti fraud service | Retryable (T) [I] |                  |
| Process_Payment  | Complete payment from customer to seller   | Pivot (T)         |                  |
| Notify_Success   | Payment completed successful notification  | Retryable (T) [I] |                  |
| Notify_Unsuccess | Payment aborted notification               | Retryable (C) [I] |                  |
| Release_Payment  | Release hold of funds                      | Pivot (C)         |                  |