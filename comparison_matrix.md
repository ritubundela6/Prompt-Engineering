# Scored Comparison Matrix

## Scoring Method
Scores are subjective architectural judgments, not documentation facts, benchmark measurements, or verified industry rankings. Higher is more favorable for the stated criterion: 1 = limited fit, 2 = below-average fit, 3 = moderate fit, 4 = strong fit, 5 = very strong fit.

Comparison assumptions: self-managed Kubernetes; self-managed Docker Swarm; ECS with Fargate for the Fargate column. EKS with Fargate is a different configuration and is not assigned these same scores. No production workload has been specified.

| Criterion | Kubernetes | Docker Swarm | AWS Fargate (ECS) | Basis and qualification |
|---|---:|---:|---:|---|
| Direct cluster management control | 5 | 4 | 2 | Kubernetes has a control-plane/node model; Swarm exposes manager/worker roles; Fargate is compute under ECS/EKS. Scores interpret these roles, not measured flexibility. [web:3][web:4][web:2] |
| Initial setup simplicity | 2 | 4 | 4 | Assumes self-management for Kubernetes/Swarm and an existing AWS environment for ECS/Fargate. This is a judgment, not a documented effort estimate. [web:3][web:4][web:2] |
| Reduced customer-managed cluster-state infrastructure | 2 | 2 | 5 | Kubernetes and Swarm expose cluster management components; Fargate supplies compute through ECS. Assessment is specific to the assumed deployment models. [web:3][web:4][web:2] |
| Documentation clarity for the audited scale question | 5 | 3 | 3 | Kubernetes states joint cluster bounds; Docker states manager rules but no universal worker ceiling on the reviewed page; Fargate pricing states resource configurations, not complete task/pod quotas. This scores evidence clarity, not actual maximum scalability. [web:3][web:4][web:2] |
| Explicit usage-based compute billing model | 2 | 2 | 5 | Fargate documents requested-resource and duration billing. Kubernetes/Swarm costs depend on the hosting arrangement. This does not mean Fargate is cheapest. [web:2] |

## Interpretation
No total or overall winner is calculated. The criteria measure different dimensions; summing them without user priorities would imply an unsupported preference. Cost efficiency and performance are not scored because workload and regional pricing evidence are missing.

A final selection requires workload sizing, availability targets, quotas, team capability, and total-cost analysis. The matrix is a transparent discussion aid, not an empirical evaluation.

## Official Sources

- [Kubernetes: Considerations for large clusters](https://kubernetes.io/docs/setup/best-practices/cluster-large/)
- [Docker: How nodes work](https://docs.docker.com/engine/swarm/how-swarm-mode-works/nodes/)
- [AWS: Fargate pricing](https://aws.amazon.com/fargate/pricing/)
