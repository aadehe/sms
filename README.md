# Financial Transaction SMS Alert Notification System  
*Kotlin & Ktor Implementation*

## Overview

This project is a **production-grade SMS Alert Notification System** built using **Kotlin** and **Ktor**, designed for financial institutions to reliably notify customers of debit and credit transactions in real time.

The system addresses critical shortcomings commonly observed in third-party SMS alert solutions, including missed alerts, lack of retries, tight coupling with transaction processing, and poor observability.

This repository serves as a **portfolio-quality reference implementation** demonstrating backend engineering best practices for **banks, fintech companies, and regulated financial environments**.

---

## Business Context

In modern banking systems, SMS alerts are a **customer trust and compliance requirement**, not merely a convenience. Failures in alert delivery can lead to:

- Customer complaints and reputational damage
- Increased fraud exposure
- Regulatory scrutiny
- Operational overhead for support teams

This system is architected to meet **enterprise-grade expectations** around reliability, auditability, and extensibility.

---

## Core Objectives

- Ensure **reliable delivery** of SMS alerts after financial transactions
- Decouple transaction processing from notification delivery
- Provide **observable, auditable, and retryable** SMS workflows
- Support multiple SMS providers with failover capability
- Demonstrate Kotlin-based backend expertise using Ktor

---

## Key Features

- Real-time debit and credit SMS alerts
- Event-driven, asynchronous architecture
- Idempotent message processing
- Automatic retries with exponential backoff
- Dead-letter queue for failed messages
- Pluggable SMS provider abstraction
- Secure handling of sensitive financial data
- Full audit trail for SMS delivery events

---

## High-Level Architecture

### System Flow

```mermaid
flowchart LR
    A[Core Banking / Transaction Service]
    B[Event Publisher]
    C[Message Broker]
    D[SMS Notification Service (Ktor)]
    E[SMS Gateway Provider]
    F[Customer Mobile Device]

    A --> B
    B --> C
    C --> D
    D --> E
    E --> F

