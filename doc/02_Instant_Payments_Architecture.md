# Instant Payments Architecture

This document provides a **logical, non-technical architecture view** of a SEPA Instant Credit Transfer (SCT Inst) service, tailored to support:

* ICT risk identification
* DORA impact analysis
* GRC-focused discussions (not solution design)

The objective is to understand **where operational and cyber risks concentrate**, rather than how systems are implemented in detail.

---

## 1. Instant Payments – Business Flow

An instant payment service enables customers to transfer funds **24/7/365**, with near-real-time clearing and settlement (typically under 10 seconds).

At a business level, the flow is:

1. Customer initiates instant payment
2. Bank validates transaction and customer
3. Payment is routed to clearing & settlement mechanism
4. Receiving bank confirms acceptance or rejection
5. Funds are settled and customer is notified

This entire flow is **time-critical**, making availability, resilience, and rapid incident handling the dominant ICT risk drivers.

---

## 2. Logical Architecture Components

## 2.0 Overview
Overview of the instant payment architecture:
1. Customer Channels
2. Channel Integration Layer
3. Authentication & Authorization Services
4. Core Banking System
5. Instant Payments Engine
6. Clearing & Settlement Interface
7. Fraud Monitoring & Transaction Screening
8. Logging, Monitoring & Incident Management

This component view abstracts from implementation details and focuses on **functional dependencies relevant for DORA**.

![Instant Payments Architecture](/images/instant_payments_architecture.png)

### 2.1 Customer Channels

**Examples:**

* Mobile banking application
* Online banking portal
* API channels (for corporate clients)

**Security relevance:**

* Authentication and authorization
* Fraud detection triggers
* Entry point for denial-of-service and abuse

From a DORA perspective, these channels are **ICT assets supporting a critical business service**.

---

### 2.2 Channel Integration Layer

**Function:**

* Routes payment requests from channels to backend systems
* Performs format validation and basic business checks

**Examples:**

* API gateway
* Enterprise service bus (ESB)

**Security relevance:**

* Single point of failure
* Exposure to volumetric attacks
* Dependency on real-time processing capacity

---

### 2.3 Authentication & Authorization Services

**Function:**

* Strong customer authentication (SCA)
* Session and token management

**Examples:**

* IAM platform
* Authentication servers

**Security relevance:**

* Direct impact on fraud risk
* High availability requirement
* Dependency on cryptographic services

A failure here typically means **complete service outage** for instant payments.

---

### 2.4 Core Banking System

**Function:**

* Account validation
* Balance checks
* Posting of transactions

**Security relevance:**

* Integrity of balances
* Availability under peak load
* Legacy dependencies (common in banks)

From a DORA view, this is a **critical internal ICT system** with systemic impact.

---

### 2.5 Instant Payments Engine

**Function:**

* Orchestrates instant payment logic
* Applies scheme rules (SCT Inst)
* Manages timeouts and exceptions

**Security relevance:**

* Highly time-sensitive processing
* Dependency on accurate clocks and messaging
* Failure results in regulatory breaches (SLA violations)

Often provided by a **third-party vendor**, increasing DORA relevance.

---

### 2.6 Clearing & Settlement Interface

**Examples:**

* TIPS (TARGET Instant Payment Settlement)
* RT1 (EBA Clearing)

**Security relevance:**

* External dependency
* Network connectivity resilience
* Contractual SLAs and exit strategies

This is typically a **critical third-party ICT service** under DORA.

---

### 2.7 Fraud Monitoring & Transaction Screening

**Function:**

* Real-time fraud detection
* Sanctions and AML checks

**Security relevance:**

* Balancing speed vs control effectiveness
* False positives causing service disruption

Failures here can create **regulatory and reputational risk**, not just ICT risk.

---

### 2.8 Logging, Monitoring & Incident Management

**Function:**

* Transaction logging
* System health monitoring
* Alerting and escalation

**Security relevance:**

* Detection of ICT incidents
* Evidence for regulatory reporting

These capabilities are central to **DORA incident management requirements**.

---

## 3. Key ICT Dependencies (DORA-Relevant)

| Dependency Type                 | Examples                    | DORA Relevance               |
| ------------------------------- | --------------------------- | ---------------------------- |
| Internal systems                | Core banking, IAM           | Critical ICT assets          |
| Third-party vendors             | Payment engine, fraud tools | Third-party ICT risk         |
| Financial market infrastructure | TIPS / RT1                  | Critical external dependency |
| Network & connectivity          | MPLS, VPNs                  | Availability & resilience    |

---

## 4. Key Risk Concentration Areas

From a GRC perspective, instant payments concentrate risk in:

1. **Availability** – near-zero tolerance for downtime
2. **Third-party dependency** – limited substitutability
3. **Incident response speed** – regulatory timelines
4. **Change management** – small errors have immediate impact
5. **Fraud vs resilience trade-offs** – security controls can disrupt service

