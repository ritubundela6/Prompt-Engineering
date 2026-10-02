# Container Technology Research Report

Author: Ritu Bundela

Project: Prompt engineering assignment

Evidence checked: 2 October 2026

# Background Fact Sheet

This sheet compiles documentation facts without recommendations. It was consolidated during this project; no separately generated Exercise 1 fact-sheet file was supplied.

## Kubernetes
- Architecture: nodes running Kubernetes agents are managed by a control plane. [web:3]
- Scale: the retrieved page specifies no more than 5,000 nodes, 110 pods per node, 150,000 total pods, and 300,000 total containers, with all criteria applying together. [web:3]
- Version qualification: the retrieved page labels these statements Kubernetes v1.37. Its release status was not independently checked; this is a record of the retrieved documentation, not a claim about the latest stable release. [web:3]
- Operational requirements: large clusters require adequate control-plane compute, cloud resource quotas, and appropriately sized add-ons. Node creation can be subject to provider rate limits. [web:3]
- Cost: the reviewed large-cluster page does not provide a universal deployment price. A total-cost estimate remains unresolved without hosting, sizing, service, and operational assumptions.

## Docker Swarm
- Architecture: a swarm consists of Docker Engine nodes acting as managers or workers. Managers maintain state, schedule services, and expose management API endpoints. [web:4]
- State: managers use internal Raft consensus; workers do not participate in the Raft distributed state. [web:4]
- Availability: three managers tolerate one manager failure; five tolerate two simultaneous manager failures. Docker recommends an odd manager count and a maximum of seven managers. [web:4]
- Scale limitation: seven is a manager recommendation, not a maximum total-node count. The reviewed page does not establish a universal worker-node ceiling. Adding managers does not increase scalability or performance. [web:4]
- Operational dependency: a worker requires at least one manager; managers are also workers by default. [web:4]
- Cost: the reviewed node-architecture page does not establish a complete hosting or operational price.

## AWS Fargate
- Architecture: compute is provided for Amazon ECS tasks and Amazon EKS pods. Fargate is not a standalone orchestration substitute. [web:2]
- Resource constraints: supported CPU and memory combinations are defined by AWS. The pricing page is not a substitute for service-specific task/pod sizing and account-quota documentation. [web:2]
- Billing dimensions: requested vCPU, memory, operating system, CPU architecture, and applicable storage. [web:2]
- Duration: image downloading to task/pod termination, rounded up to the nearest second; Linux has a one-minute minimum and Windows containers have a five-minute minimum. [web:2]
- Storage and extras: the pricing page states that 20 GB of ephemeral storage is included by default; additional configured storage, logging, data transfer, and public IPv4 addresses can produce additional charges. [web:2]
- Service qualification: the pricing page states that Windows and ARM configurations are currently available for ECS; ECS/EKS features must not be assumed identical. [web:2]

## Evidence boundaries
No independently verified adoption statistics, performance benchmarks, universal Swarm worker limit, or project-specific cost estimates were obtained. Setup complexity and suitability are architectural assessments, not absolute documentation facts.

---

# Corrected Comparison Report

## Introduction
Kubernetes, Docker Swarm, and AWS Fargate support containerized workloads but operate at different layers. Kubernetes uses a control plane and nodes; Swarm uses Docker Engine managers and workers; Fargate provides compute for ECS tasks and EKS pods. Kubernetes and Fargate can be combined through EKS. [web:3][web:4][web:2]

This report distinguishes documentation facts from architectural judgments. It does not establish project-specific pricing, performance, or account quotas.

## Tech Overviews
### Kubernetes
Kubernetes manages nodes through a control plane. Its retrieved large-cluster documentation specifies configurations satisfying all of these criteria: at most 5,000 nodes, 110 pods per node, 150,000 total pods, and 300,000 total containers. Large clusters also require sufficient control-plane resources, cloud quotas, and add-on capacity. [web:3]

The source labels these statements v1.37; release status was not separately verified. The bounds should not be presented as guarantees for every distribution or hosted service. [web:3]

### Docker Swarm
Managers maintain cluster state and schedule services; workers execute containers. Internal Raft maintains manager state. Docker recommends an odd manager count and no more than seven managers. Three managers tolerate one failure; five tolerate two. Managers can also execute workloads unless configured otherwise. [web:4]

The seven-manager recommendation is not a maximum cluster-node limit. Increasing manager count does not improve scalability or performance. [web:4]

### AWS Fargate
Fargate supplies resource-configured compute for ECS tasks or EKS pods. Its pricing reflects requested CPU, memory, operating system, CPU architecture, and applicable storage. ECS and EKS must be assessed separately because their supported configurations are not necessarily identical. [web:2]

## Detailed Comparison
### Architecture
Kubernetes and Swarm manage clusters; Fargate is a compute option within an ECS or EKS design. Consequently, a decision about Fargate does not by itself settle the orchestration choice. [web:3][web:4][web:2]

### Scalability and availability
Kubernetes' four documented bounds apply simultaneously. Infrastructure quotas, control-plane capacity, and add-on sizing can impose additional practical constraints. [web:3]

Swarm manager quorum determines management fault tolerance. This audit does not establish a universal Swarm worker ceiling. Docker's manager recommendation must not be used as a workload-capacity figure. [web:4]

Fargate has defined resource configurations and should not be described as unlimited compute. Concurrent task/pod capacity, deployment region, and account quotas remain outside this audit. [web:2]

### Setup complexity
The following are architectural judgments, not benchmark results. Swarm's Docker Engine manager/worker model may suit teams seeking a direct cluster arrangement, but availability planning remains necessary. Kubernetes planning includes control-plane resources and add-on capacity. Fargate changes the compute layer while retaining ECS or EKS configuration responsibilities. Relative effort depends on the selected deployment and the team's capabilities. [web:4][web:3][web:2]

### Cost structures
No defensible monthly Kubernetes or Swarm price follows from the provided baseline: workload sizing, hosting, and operating assumptions are missing. No cheapest-platform conclusion is made.

Fargate billing begins when image downloading starts and ends when the task/pod terminates, rounded up to the nearest second. Linux has a one-minute minimum; Windows containers have a five-minute minimum. Requested resources, not CPU utilization alone, determine the resource charge. [web:2]

The pricing page includes 20 GB of ephemeral storage by default and charges for additional configured storage. Logging, data transfer, public IPv4 addresses, and other supporting services can add charges. Region-specific calculations are still required. [web:2]

## Final Verdict
No universal winner is justified. As conditional architectural judgments, Kubernetes merits evaluation when its cluster-control model fits the requirements; Swarm merits evaluation when Docker Engine's manager/worker model fits; Fargate merits evaluation when AWS container compute and resource-based billing fit. These are suitability judgments rather than measured rankings. [web:3][web:4][web:2]

Before selection, define workload sizes, availability needs, orchestration preferences, team capabilities, account quotas, and regional total costs. Verification here is limited to the four audited claim groups, not every implementation detail.

---

# Four-Step CoVe Log

## Step 1: Preserve the baseline
Input: the original ERA comparison in this conversation, from Introduction through Final Verdict. No baseline_draft.txt attachment was supplied. The original conversation is the baseline record; this document does not claim a separate uploaded file was examined.

Key audited claims: Kubernetes' published scale numbers; Swarm's Raft architecture and manager recommendation; Fargate's ECS/EKS dependency; Fargate's unqualified one-minute billing minimum.

## Step 2: Formulate exactly four questions
1. What node, per-node pod, total pod, and total container bounds does Kubernetes document, and must all four criteria be satisfied simultaneously?
2. How do Docker Swarm managers maintain cluster state, what manager count does Docker recommend, and how many manager failures can three- and five-manager clusters tolerate?
3. Does AWS Fargate provide compute for both Amazon ECS tasks and Amazon EKS pods, rather than functioning as an independent orchestrator?
4. Which requested resources determine Fargate pricing, when does billable duration begin and end, and what minimum durations apply to Linux and Windows containers?

## Step 3: Answer independently from documentation
The documentation was consulted directly rather than treating the baseline as evidence. “Independent” means independent source checking, not a separate human review or a separate ChatGPT session.

### Answer 1: Kubernetes bounds
The retrieved page documents no more than 5,000 nodes, 110 pods per node, 150,000 total pods, and 300,000 total containers. All four criteria apply together. These are documented configuration bounds, not throughput guarantees. The retrieved page names v1.37; this audit does not independently verify that version's release status or managed-service limits. [web:3]

Baseline disposition: retain the figures; clarify simultaneous applicability and avoid universal hard-ceiling language.

### Answer 2: Swarm managers
Managers use internal Raft to maintain consistent cluster state. Docker recommends an odd manager count and a maximum of seven managers. Three managers tolerate one failure; five tolerate two simultaneous failures. Adding managers does not increase scalability or performance. [web:4]

Baseline disposition: retain the architecture and recommendation; distinguish manager count from total node capacity. No universal worker ceiling is established by the reviewed page.

### Answer 3: Fargate dependencies
AWS describes ECS tasks and EKS pods running on Fargate. Fargate supplies compute rather than replacing those services' orchestration role. Kubernetes through EKS can therefore be used with Fargate. [web:2]

Baseline disposition: retain the orchestration-versus-compute distinction and assess ECS/Fargate and EKS/Fargate separately.

### Answer 4: Fargate billing
Pricing uses requested CPU, memory, operating system, architecture, and applicable storage. Duration starts with image downloading and ends at task/pod termination, rounded up to the nearest second. Linux has a one-minute minimum; Windows containers have a five-minute minimum. Additional storage and supporting services may add charges. [web:2]

Baseline disposition: correct the unqualified one-minute minimum. Do not equate compute pricing with total deployment cost.

## Step 4: Apply corrections
Output: the Corrected Comparison Report in this document.

Changes: clarify Kubernetes' simultaneous criteria and version scope; distinguish Swarm managers from total nodes; preserve Fargate's compute/orchestration distinction; correct Windows billing to a five-minute minimum; identify supporting-service charges and unverified quotas/costs.

REQ-003 / TR-002 evidence: baseline identification, four questions, official-source answers, correction decisions, and the corrected report are included. Full accuracy beyond these checks is not claimed.

## Official Sources

- [Kubernetes: Considerations for large clusters](https://kubernetes.io/docs/setup/best-practices/cluster-large/)
- [Docker: How nodes work](https://docs.docker.com/engine/swarm/how-swarm-mode-works/nodes/)
- [AWS: Fargate pricing](https://aws.amazon.com/fargate/pricing/)
