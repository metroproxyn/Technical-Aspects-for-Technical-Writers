What is cloud computing

Cloud computing is the delivery of computing services over the internet. Computing services include common IT infrastructure such as virtual machines, storage, databases, and networking. Cloud services also expand the traditional IT offerings to include things like Internet of Things (IoT), machine learning (ML), and artificial intelligence (AI).

Because cloud computing uses the internet to deliver these services, it doesn’t have to be constrained by physical infrastructure the same way that a traditional datacenter is. That means if you need to increase your IT infrastructure rapidly, you don’t have to wait to build a new datacenter; you can use the cloud to rapidly expand your IT footprint.

## Describe Infrastructure as a Service

The shared responsibility model defines who is responsible for what in a cloud deployment. It divides responsibilities between the cloud provider and the customer.

**Key comparison:**
- In on-premises environments: The organization is responsible for **everything** (physical infrastructure, operating systems, applications, data, and security).
- In IaaS: Provider handles physical infrastructure; customer handles OS, apps, data, security.
- In PaaS: Provider handles infrastructure + OS + middleware; customer handles apps, data, security.
- In SaaS: Provider handles **everything**; customer handles only data usage.

[Image description: A layered diagram showing responsibility shifting as you move up the service models. Bottom layer (on-premises) is fully customer-controlled. Arrows or color coding (blue = provider, green = customer) show how more responsibility moves to the provider in IaaS → PaaS → SaaS. Educational purpose: Illustrates how customers have less to manage (and less risk) as they adopt higher cloud services.]

| Layer       | Provider Responsibility                  | Customer Responsibility                  |
|-------------|------------------------------------------|------------------------------------------|
| On-Premises | None                                     | All (hardware, OS, apps, data, security) |
| IaaS        | Physical infrastructure, facilities      | OS, apps, data, security                 |
| PaaS        | Physical infrastructure, OS, middleware  | Apps, data, security                     |
| SaaS        | Everything (infrastructure, OS, apps)    | Data usage                               |

## Define cloud models
Cloud models describe the type of cloud environment used.

[Image description: Comparison diagram with icons (globe for public, lock for private, bridge for hybrid) and arrows showing data/application flow between environments. Educational purpose: Helps visualize when to choose each model.]

| Model   | Description                                                                 | Use cases                              | Pros                                      | Cons                                      |
|---------|-----------------------------------------------------------------------------|----------------------------------------|-------------------------------------------|-------------------------------------------|
| Public  | Resources provided over the public internet and shared among organizations | Web apps, storage, databases           | Cost-effective, highly scalable           | Less control, potential security concerns |
| Private | Dedicated infrastructure for one organization (on-prem or hosted)          | Sensitive data, compliance workloads   | More control, better security             | Higher cost, less scalable                |
| Hybrid  | Combines public + private clouds; data/apps can move between them          | Burst capacity, gradual migration      | Flexibility, optimized costs              | Complexity in management                  |

## Describe the consumption-based model
Cloud pricing is consumption-based (pay only for what you use) instead of traditional upfront investments.

**CapEx vs OpEx:**
- CapEx = Capital Expenditure (big upfront hardware/software costs — typical for on-premises).
- OpEx = Operational Expenditure (ongoing usage-based costs — typical for cloud).

**Benefits:** No large upfront costs, automatic scaling, reduced waste.

[Image description: Side-by-side diagram comparing CapEx (large fixed upfront circle/spike) vs OpEx (flexible, step-by-step bar graph that grows only with usage). Arrows show cost over time — OpEx starts lower and scales efficiently. Educational purpose: Shows why cloud is financially more predictable and efficient.]

This module covers:
- What cloud computing is and its benefits
- The shared responsibility model (why cloud is easier than on-prem)
- Public, private, and hybrid cloud models
- Consumption-based (pay-as-you-go) pricing vs traditional CapEx

**Official resources:**  
- Full module: https://learn.microsoft.com/en-us/training/modules/describe-cloud-compute/
- Azure Fundamentals learning path