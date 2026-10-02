# Prompt Documentation

## Parameters
- Technologies: Kubernetes (K8s), Docker Swarm, AWS Fargate (Serverless Containers).
- ERA expectation: detailed report with the four named H2 sections; no summary tables.
- ERA role: Lead Systems Architect.
- ERA action input: the completed background fact sheet, not the instruction used to generate it.
- CoVe baseline input: original ERA draft.
- CoVe question count: exactly four.
- CoVe evidence: official developer documentation.
- CoVe correction input: original baseline plus verified answers.

## Exercise 1: Generated Knowledge Prompt
```text
Generate a factual summary detailing the core architecture, scalability limits,
setup complexity, and cost structures of the following three technologies:
Kubernetes, Docker Swarm, and AWS Fargate. Focus on raw specifications, documentation
facts, and industry statistics. Do not write a comparison or recommendations yet.
Keep your focus on compiling background knowledge.
```

## ERA Research Prompt
The substantive ERA parameters are preserved. The BACKGROUND FACTS slot is corrected to accept the Exercise 1 output, rather than repeat the generation instruction.

```text
[EXPECTATION]: I expect a detailed comparison report comparing Kubernetes, Docker
Swarm, and AWS Fargate. Structure the response with H2 headers for: Introduction,
Tech Overviews, Detailed Comparison, and Final Verdict. Do not write summary tables yet.
[ROLE]: Act as a Lead Systems Architect.
[ACTION]: Write the comparison report based on the following background facts:
=== BACKGROUND FACTS ===
[Insert the factual summary generated in Exercise 1.]
=== END BACKGROUND FACTS ===
```

## CoVe Question Formulation Prompt
Exact assignment template:

```text
Read the baseline draft comparison below. Formulate a list of exactly four specific
verification questions that can be answered with absolute facts to audit the claims,
numbers, and limitations stated in the text (e.g. check version limits, specific
scalability numbers, or operational dependencies).
[BASELINE DRAFT]:
[Insert the text from baseline_draft.txt]
```

## CoVe Question Answering Prompt
Exact assignment template:

```text
Answer each of the following verification questions one-by-one. Rely strictly on
verified developer documentation facts:
[Insert the four questions generated in the previous step]
```

## CoVe Correction Prompt
Exact assignment template:

```text
Review the original baseline draft. Rewrite the report incorporating the verified
corrections below. Ensure the final report is fully accurate and resolved.
[BASELINE DRAFT]: [Insert baseline_draft.txt]
[VERIFIED CORRECTIONS]: [Insert the answers from the previous step]
```

## Execution Qualifications
The templates above preserve the assignment wording. “Absolute facts” and “fully accurate” are goals, not guarantees. For execution, scope claims to the source/version/service; distinguish recommendations from hard limits; cite documentation; and flag unresolved details rather than inventing them.

The four CoVe stages used here are baseline preservation, question formulation, independent documentation answering, and correction. This package was produced in this assistant conversation; it does not claim a separate execution inside ChatGPT.

## Executed Questions
1. What node, per-node pod, total pod, and total container bounds does Kubernetes document, and must all four criteria be satisfied simultaneously?
2. How do Docker Swarm managers maintain cluster state, what manager count does Docker recommend, and how many manager failures can three- and five-manager clusters tolerate?
3. Does AWS Fargate provide compute for both Amazon ECS tasks and Amazon EKS pods, rather than functioning as an independent orchestrator?
4. Which requested resources determine Fargate pricing, when does billable duration begin and end, and what minimum durations apply to Linux and Windows containers?

## Input/Output Mapping
- Background facts: Background Fact Sheet in research_report.md.
- Original baseline: the initial ERA comparison in the conversation; no separate file was supplied.
- Verified answers: Step 3 of the CoVe log in research_report.md.
- Corrected output: Corrected Comparison Report in research_report.md.
- Summary and matrix: downstream deliverables; the matrix is outside the no-summary-table restriction on the ERA report.
