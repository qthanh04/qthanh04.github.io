---
layout: page
title: Nemi Tool - Facebook Ads Management Platform
description: Backend Developer
img: assets/img/12.jpg
importance: 1
category: work
related_publications: true
---

## 📌 Project Overview

Developed a comprehensive Spring Boot synchronization system supporting multiple client applications for managing Facebook Ads data with real-time updates and scalable architecture.

---

## 🏗️ Nemi Architecture (Infrastructure on AWS EKS)

The platform is deployed using the Nemi architecture on AWS EKS, focusing on reliability, scalability, and security for the Facebook Ads data synchronization system.

<div class="row justify-content-sm-center">
    <div class="col-sm-10 mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/ha_tang_eks_nemi.png" title="Nemi architecture on EKS" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-12 mt-2">
        <div class="caption">Nemi infrastructure overview: EKS with ALB/NLB Ingress, private node groups, ECR, ArgoCD (GitOps), Secrets Manager/ACM, RDS in private subnets, and public DNS routing.</div>
    </div>
</div>

### Core Components and Flow

- **EKS Cluster**: ALB/NLB Ingress distributes traffic across multiple availability zones
- **Container Management**: Private node groups pull images from ECR without internet exposure
- **GitOps Deployment**: ArgoCD synchronizes manifests from repository to enforce desired state
- **Security**: Secrets managed via AWS Secrets Manager; TLS certificates through ACM
- **Data Layer**: Internal services access RDS instances in private subnets
- **DNS and CI/CD**: Domain mapping to Ingress; automated image builds to ECR before ArgoCD deployment

---

## 🔹 Microservices Architecture

Designed and implemented domain-driven microservices including user management, communication, ads management, product management, system configuration, and worker services.

<div class="row justify-content-sm-center">
    <div class="col-sm-10 mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/microservice_eks.png" title="Nemi Microservice" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-12 mt-2">
        <div class="caption">Nemi Microservice.</div>
    </div>
</div>

### 🏗️ Architecture

- **Microservices**: Split domains into separate services:

  - User Service (user, company, permission management)
  - Communication Service (email, notification, push)
  - Ads Service (Facebook account, BM, domain, pixel)
  - Product Service (POS, product, reporting)
  - System Service (custom view, exchange rate, audit log)
  - Worker Service (background jobs, data sync)

- **Data Flow**:

  - Facebook Graph API + Webhooks → Kafka → Processing Pipelines → PostgreSQL (RDS) → REST/GraphQL API → Client UI
  - Notifications → FCM / Email

- **Deployment**:
  - GitLab CI/CD → Docker Image → ECR → EKS (Helm + ArgoCD)

---

## ⚙️ Tech Stack

- **Backend**: Java 17, Spring Boot 3
- **Database**: PostgreSQL (AWS RDS), Flyway migration
- **Messaging**: Apache Kafka (10+ topics, 1K+ events/day)
  <div class="row justify-content-sm-center">
    <div class="col-sm-10 mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/kafka_info" title="Nemi Kafka" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-12 mt-2">
        <div class="caption">Nemi Kafka.</div>
    </div>
</div>
- **Infrastructure**: AWS EKS, EC2, ECR, Secrets Manager, ACM, Terraform
- **DevOps**: Docker, Helm, GitLab CI/CD, ArgoCD
- **API**: REST, GraphQL, gRPC (internal)
- **Security**: Keycloak (OAuth2/OIDC, JWT), RBAC
- **Observability**: Prometheus, Grafana, OpenTelemetry, Jaeger, Sentry
- **Notifications**: Firebase Cloud Messaging (FCM), Email Service

---

## 🚀 Key Features

- Real-time synchronization from Facebook Graph API & Webhooks
- Kafka pipelines ensuring **exactly-once processing**
- RESTful APIs & GraphQL endpoints for client applications
- Push notifications to thousands of daily users (FCM)
- Full audit logging, multi-tenant authentication/authorization
- Zero-downtime deployment on AWS EKS

---

## 💡 Responsibilities (Backend Developer)

- Designed & implemented **microservices** with Spring Boot 3
- Built asynchronous data pipelines with Kafka, monitored consumer lag, and enabled auto-scaling
- Developed REST/GraphQL APIs with validation, pagination, and filtering
- Integrated Facebook Graph API & Webhooks with retry & dead-letter queue mechanisms
- Implemented authentication & authorization with OAuth2/OIDC, JWT, and Keycloak
- Integrated FCM for push notifications (mobile + web)
- Automated CI/CD pipelines (build, test, scan, deploy) with GitLab & ArgoCD
- Managed database schema & migration with Flyway, optimized queries for large datasets
- Added logs, metrics, and distributed tracing with OpenTelemetry, Prometheus, and Grafana
