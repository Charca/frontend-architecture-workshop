# Order Placement Sequence

```mermaid
sequenceDiagram
    title Order Placement Sequence
    participant Customer
    participant Web App
    participant Core API
    participant DB
    participant Payments System

    Customer->>Web App: Click order button
    Web App->>Core API: Sends Order ID and <br /> payment information
    Core API->>DB: Get total by order ID
    DB-->>Core API: Return order total
    Core API->>Payments System: Send payment request
    Payments System-->>Core API: Return payment confirmation
    Core API-->>Web App: Return confirmation
    Web App-->>Customer: Show confirmation message
```

## Mermaid Live URL

https://mermaid.live/edit#pako:eNptUkuPmzAQ_iuWz3nZJBCsKtJmqaqcGjWHSlUuBjtgLWBqD21plP9eAybqbsLJzHyvGc0VZ1pIzLCVP1tZZzJRPDe8OtfIfaCglOirEdKgY8kzWcka0MlDR0zDDahMNdx1XlsLupLmsfNdpuilaZ5QtJHo5Xh47CT7x9qRd30Ei06dBelSjpDJd77beSOGXkuVvSE9ZE9bAO2xHuCgkzVzE9XC-jkPCeK1QJ9Sg5Y7Zz4YIlVftKk4qElmIjudZM_QFwkINPASpZ03PSQjMtnP35l9k9Ca2oMGzoPihzHHgPcspt-_hZH1AfrUaiJmur6o51P8vznPekRPq-s9_MZdtEL_fodFlbSW5xLPsANUXAl3Xtde4YyhcCd0xsw9BTdvZ3yubw7HW9Cnrs4wA9PKGW4bwWE6RcwuvLT36mehQJt7sdTc7RGzK4au6Q85Vxac5JAo7-utKV25AGgsWy779iJXULTpItPV0ipRuAMrfsXhMqThltNAhlHAN0EgspTE2wtdk4uIVoRyfLvNsLvDXvUPZoQEi3hL400Urkm8opt4hjvM5pQsAhputiQOwiAgQRA52l-t3SRkQcmW0nAVbUhE13Q96P0Yen4go9u88H-3f0QMLqc

![Sequence Diagram](../assets/sequence-diagram-1.png)
