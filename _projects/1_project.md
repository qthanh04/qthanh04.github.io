---
layout: page
title: Nemi Tool - Facebook Ads Management Platform
description: Backend Developer
img: assets/img/12.jpg
importance: 1
category: work
related_publications: true
---

**Project Overview**: Developed a comprehensive Spring Boot synchronization system supporting multiple client applications for managing Facebook Ads data with real-time updates and scalable architecture.

## Nemi Architecture

The platform is deployed using the Nemi architecture on AWS EKS, focusing on reliability, scalability, and security for the Facebook Ads data synchronization system.

<div class="row justify-content-sm-center">
    <div class="col-sm-10 mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="_projects/ha_tang_eks_nemi.png" title="Nemi architecture on EKS" class="img-fluid rounded z-depth-1" %}
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

## Professional Experience

### Nemi Tool — Facebook Ads Management Platform
**Backend Developer** · March 2024 – Present

**Project Overview**: Built a robust, real-time data synchronization and campaign management platform utilizing Facebook Marketing APIs, designed for multi-tenant operation, comprehensive observability, and zero-downtime deployments.

<div class="mt-2 mb-1"><strong>Technology Stack</strong>:</div>
<div>
    <span class="badge badge-primary">Java 17</span>
    <span class="badge badge-primary">Spring Boot 3</span>
    <span class="badge badge-info">PostgreSQL (RDS)</span>
    <span class="badge badge-dark">AWS (EKS, ECR, ALB/NLB, ACM, Secrets Manager)</span>
    <span class="badge badge-warning">Apache Kafka</span>
    <span class="badge badge-secondary">Docker</span>
    <span class="badge badge-success">GraphQL</span>
    <span class="badge badge-secondary">GitLab CI/CD</span>
    <span class="badge badge-info">Keycloak</span>
    <span class="badge badge-success">FCM</span>
    <span class="badge badge-secondary">Prometheus/Grafana</span>
    <span class="badge badge-secondary">OpenTelemetry</span>
    <span class="badge badge-secondary">Redis</span>
    <span class="badge badge-secondary">Flyway</span>
    <span class="badge badge-secondary">Testcontainers</span>
    <span class="badge badge-secondary">WireMock</span>
    <span class="badge badge-secondary">REST API</span>
    <span class="badge badge-secondary">gRPC</span>
    <span class="badge badge-secondary">ArgoCD</span>
    <span class="badge badge-secondary">Terraform</span>
    <span class="badge badge-secondary">SonarQube</span>
    <span class="badge badge-secondary">CodeQL</span>
    <span class="badge badge-secondary">Sentry</span>
    <span class="badge badge-secondary">Jaeger</span>
    <span class="badge badge-secondary">Helm</span>
</div>

#### Scale and Reliability Highlights
- **High Throughput**: Processes 100K+ events daily via Kafka across 10+ topics with consumer lag monitoring and auto-scaling
- **Performance**: Maintains P99 API latency under 250ms for core read operations
- **Availability**: Achieves 99.9% service availability with multi-AZ EKS nodes and health-driven rollouts
- **Deployment**: Zero-downtime blue/green releases on EKS infrastructure

#### Key Responsibilities
- **Microservices Architecture**: Designed and implemented domain-driven microservices for ads, campaigns, ad sets, and insights aggregation
- **API Integration**: Built resilient Facebook Graph API and Webhooks integrations with circuit breakers, retry mechanisms, and dead-letter queues
- **Database Design**: Modeled relational schemas and migrations using Flyway; optimized queries and indexes for large datasets
- **API Development**: Implemented GraphQL and REST APIs with strict validation, pagination, and field-level filtering
- **Observability**: Added distributed tracing, metrics, and logging using OpenTelemetry, Prometheus, Grafana, and Jaeger with SLO dashboards
- **Event Processing**: Created fault-tolerant Kafka consumers/producers with idempotency and exactly-once processing semantics
- **Security**: Implemented OAuth2/OIDC via Keycloak, JWT propagation, and role/permission models for multi-tenant architecture
- **Testing**: Developed comprehensive test suites including unit, contract, and integration tests using Testcontainers and WireMock

#### Technical Achievements
- **Real-time Synchronization**: Implemented Facebook Graph API + Webhooks integration with exponential back-off and replay mechanisms for eventual consistency
- **Performance Optimization**: Reduced end-to-end sync time by ~40% through Kafka pipeline optimizations while maintaining delivery guarantees
- **Infrastructure Scaling**: Delivered horizontal scalability on EKS with HPA/VPA and PodDisruptionBudgets, reducing incident MTTR by 60% through SLO-based alerting
- **DevOps Pipeline**: Automated GitLab CI/CD with static analysis (CodeQL/SonarQube), test gates, image building, and Helm deployment via ArgoCD
- **Security Hardening**: Enhanced security posture with AWS Secrets Manager rotation, ACM TLS enforcement, and ingress-level rate limiting
- **Mobile Integration**: Implemented FCM push notifications delivering thousands of daily messages to mobile and web clients

#### Architecture Design
- **Infrastructure**: AWS EKS-based deployment with ingress controllers, GitOps workflows, and comprehensive secrets management
- **Communication**: Service-to-service communication via REST/GraphQL APIs with selective gRPC for high-throughput internal operations
- **Caching Strategy**: Redis-based caching for read-heavy endpoints and background job scheduling via Quartz/Spring Scheduling

#### DevOps and Operations
- **Git Workflow**: Trunk-based development with protected branches, mandatory code reviews, and quality gates
- **Deployment Strategy**: Canary and blue/green deployments with automated rollback on health check failures
- **Database Management**: Backward-compatible database migrations with proper gating mechanisms
- **Monitoring**: Observability-first approach tracking golden signals and business KPIs with maintained on-call runbooks

#### Security and Compliance
- **Access Control**: Principle of least privilege across AWS IAM and database roles with CSI driver-mounted secrets
- **Input Validation**: Comprehensive input validation and output encoding to prevent injection attacks
- **Audit Trail**: Complete audit logging for administrative actions and user activities
- **Supply Chain Security**: Regular dependency scanning, container image signing, and SBOM generation for each release

**Team Collaboration**: Worked within a 10-member cross-functional team including Product Owner, Designer, QA, DevOps, Backend, and Frontend developers. Maintained close collaboration with product and data teams to refine requirements and deliver increments on a two-week sprint cadence.
