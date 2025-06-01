---
marp: true
paginate: true
theme: my-theme
---


# NServiceBus

A messaging platform for building **reliable**, **decoupled**, and **asynchronous** .NET systems.

- Supports **Commands**, **Events**, **Retries**, **Sagas**, and more
- Focus today: Commands, Endpoints, Retries

---

# Commands & Endpoints

**Command** = intent to do something (e.g. `UpdateBasicHealthInsuranceCommand`)
- Sent by one service, handled by one receiver
- Ensures **strong consistency** for workflows

**Endpoint** = logical service that sends/receives messages
- Runs a handler for commands or events
- You can scale endpoints independently

Think of endpoints as services, and commands as directed tasks.

---

# Retries in NServiceBus

**Automatic Retries:**
- *Immediate Retries*: run again in-memory
- *Delayed Retries*: put back into the queue with delay

**Why?**
- If can go wrong... it will go wrong

If retries fail repeatedly → message goes to **error queue**


