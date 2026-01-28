# Introduction to Cloud Computing

This guide is for technical writers who want to understand the basics of cloud computing – the technology behind many modern applications, services, and infrastructures that you may need to document.

## What is Cloud Computing?

Cloud computing means accessing things like servers, storage, and software over the internet instead of keeping everything on your own machines. Rather than investing in physical servers, companies rent computing power from cloud providers and adjust their usage as their needs change.

**Core characteristics (NIST definition):**
- On-demand self-service
- Broad network access
- Resource pooling
- Rapid elasticity (scalability)
- Measured service (pay-as-you-go)

## Cloud Service Models

Cloud services are divided into three main layers, each offering a different level of control and responsibility.

- **IaaS (Infrastructure as a Service)**  
  You rent virtual machines, storage, and networking. You manage OS, middleware, runtime, and applications.  
  Examples: AWS EC2, Azure Virtual Machines, Google Compute Engine.  
  Use case for documentation: describing VM provisioning, networking setup (VPCs), storage types.

- **PaaS (Platform as a Service)**  
  Provider manages infrastructure + OS + runtime. You focus only on your application code and data.  
  Examples: AWS Elastic Beanstalk, Google App Engine, Azure App Service, Heroku.  
  Use case: documenting deployment pipelines, buildpacks, scaling rules.

- **SaaS (Software as a Service)**  
  Fully managed application delivered over the internet. You just use it.  
  Examples: Google Workspace, Microsoft 365, Salesforce, Dropbox.  
  Use case: writing user guides, admin consoles, API references.

Most documentation you write will fall somewhere in PaaS/SaaS, but understanding IaaS helps when explaining underlying infrastructure.

## Cloud Deployment Models

- **Public Cloud** — Shared infrastructure owned by a provider (AWS, Azure, GCP). Lowest cost, highest scalability.  
- **Private Cloud** — Dedicated infrastructure for one organization (on-premises or hosted). Better for compliance/security.  
- **Hybrid Cloud** — Combination of public and private. Used for bursting (scale to public during peaks) or sensitive workloads.  
- **Multi-Cloud** — Using services from multiple providers to avoid vendor lock-in or use best-of-breed tools.

## Major Cloud Providers

The market is dominated by three hyperscalers:
- **Amazon Web Services (AWS)** — oldest and largest market share
- **Microsoft Azure** — strong integration with Windows/Office ecosystem
- **Google Cloud Platform (GCP)** — excels in data analytics, AI, and Kubernetes

Others: Alibaba Cloud (strong in Asia), Oracle Cloud, IBM Cloud.

## Advantages and Disadvantages

**Advantages:**

- Pay only for what you use (no upfront hardware costs)
- Elastic scalability
- Global availability and disaster recovery
- Faster time-to-market
- Managed services reduce operational burden

**Disadvantages:**

- Vendor lock-in
- Potential security and compliance risks
- Cost overruns if not monitored
- Shared responsibility model (you are responsible for what you control)

## Implications for Technical Writers

When documenting cloud-based products:

- Always clarify the **shared responsibility model** — what the provider secures vs. what the customer must secure.
- Use consistent terminology (AWS calls it “VPC”, Azure — “Virtual Network”, GCP — “VPC network”).
- Include screenshots of consoles, CLI commands, and API examples.
- Explain cost implications of choices (e.g., instance types, storage classes).
- Document security best practices (IAM roles, encryption, logging).
- Write for different audiences: developers (infrastructure code), DevOps (CI/CD integration), end-users (SaaS interfaces).

## Next Steps: Roadmap for Deeper Knowledge

Once you have the basics, focus on topics that frequently appear in documentation:

1. **Choose one provider and get hands-on**  
   Start with the free tier:  
   - AWS Cloud Practitioner Essentials  
   - Azure Fundamentals (AZ-900)  
   - Google Cloud Digital Leader  

2. **Containerization & Orchestration**  
   Docker → Kubernetes (you already have these in the repo) — most cloud-native apps use them.

3. **Serverless Computing**  
   AWS Lambda, Azure Functions, Google Cloud Functions. No servers to manage.

4. **Cloud Networking & Security**  
   VPCs, subnets, security groups, IAM, encryption at rest/in transit, compliance (GDPR, HIPAA, SOC).

5. **Infrastructure as Code (IaC)**  
   Terraform, AWS CloudFormation, Azure ARM, Pulumi — very common in modern docs.

6. **Observability & Monitoring**  
   CloudWatch (AWS), Azure Monitor, Google Operations Suite, Prometheus + Grafana.

7. **CI/CD in the Cloud**  
   GitHub Actions + cloud integration, AWS CodePipeline, Azure DevOps, Google Cloud Build.

8. **Advanced Topics**  
   - Cloud-native architecture (12-factor app)  
   - Microservices & service mesh  
   - Edge computing & CDNs  
   - AI/ML services in the cloud

Start small: pick one provider, deploy a simple app, and write documentation for the process. That will give you real insight into what users need to know.