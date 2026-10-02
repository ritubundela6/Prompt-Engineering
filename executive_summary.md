# Executive Summary

This project evaluates Kubernetes, Docker Swarm, and AWS Fargate through background research, an ERA prompt, and a four-question Chain of Verification audit. Kubernetes and Swarm orchestrate containers, while Fargate supplies compute for Amazon ECS tasks or Amazon EKS pods. Kubernetes documents simultaneous bounds of 5,000 nodes, 110 pods per node, 150,000 pods, and 300,000 containers. Swarm managers maintain state using Raft; Docker recommends an odd manager count and no more than seven managers. Fargate charges for requested resources and duration, with a one-minute Linux minimum and a five-minute Windows minimum. These findings correct overly broad scalability and billing statements. The comparison matrix uses subjective scores rather than measured benchmarks. Kubernetes merits evaluation for cluster control, Swarm for straightforward Docker orchestration, and Fargate for AWS compute integration. No universal winner is justified without workload sizing, deployment requirements, service quotas, regional pricing, and operational effort. Further project-specific validation remains necessary before selection.

---

Source note (excluded from the 150-word count): Kubernetes scale figures [web:3]; Swarm manager rules [web:4]; Fargate dependencies and billing [web:2]. Matrix scores are judgments.
