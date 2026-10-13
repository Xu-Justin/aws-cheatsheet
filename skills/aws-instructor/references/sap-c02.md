# SAP-C02 exam map and study focus

Use this to steer sessions toward what the exam actually weights and toward the
learner's blind spots. The structure below reflects the official exam guide, but
AWS revises the guide — before quoting weightings as fact, confirm against the
current official guide:
https://docs.aws.amazon.com/aws-certification/latest/examguides/solutions-architect-professional-02.html

## Format (verify current details before stating)

As of the current guide (SAP-C02, guide version 1.2): 75 questions (65 scored +
10 unscored), 180 minutes, scaled score 100–1000, pass at 750, compensatory
scoring (you don't need to pass each domain individually). Multiple choice (one
of four) and multiple response (two or more of five+). No penalty for guessing,
so never leave a blank. Re-check the question count, time, and fee before you
assert them — these change.

## Domains and weightings

| # | Domain | Weight |
|---|--------|--------|
| 1 | Design Solutions for Organizational Complexity | 26% |
| 2 | Design for New Solutions | 29% |
| 3 | Continuous Improvement for Existing Solutions | 25% |
| 4 | Accelerate Workload Migration and Modernization | 20% |

The weights are close enough that no domain can be skipped. Domain 1 is what
separates Professional from Associate: it assumes many accounts, hybrid
connectivity, and central governance.

### Domain 1 — Organizational complexity (26%)
Multi-account design, AWS Organizations, SCPs, centralized network
connectivity (Transit Gateway, VPC peering, PrivateLink, Direct Connect,
Site-to-Site VPN), cross-account IAM and identity federation, centralized
logging/monitoring, cost visibility and allocation across accounts.
**Heavy on security and IAM.** Prioritize if those are weak.

### Domain 2 — New solutions (29%, largest)
Greenfield design against requirements: deployment strategies, business
continuity / DR (backup-restore, pilot light, warm standby, multi-site),
security controls per requirement, reliability, performance, and cost. Broad;
touches most services.

### Domain 3 — Continuous improvement (25%)
Improving existing workloads: finding and fixing reliability, performance,
security, and cost issues; observability; refactoring toward managed/serverless.

### Domain 4 — Migration and modernization (20%)
Discovery and planning, moving data (Snow family, DataSync, Storage Gateway,
Transfer Family, DMS), moving compute (MGN / Application Migration Service),
and modernizing (containers, serverless, decoupling).

## Calibrating to the learner

Find out which areas the learner is already strong in. There, reason
peer-to-peer and don't over-explain. Lean on those areas as anchors when
introducing new services.

These areas are heavily tested and commonly weak. Invest the most teaching
effort in whichever of them the learner is weak in:

- **IAM & identity:** policy evaluation logic (explicit deny > allow, boundaries,
  SCPs, session policies), roles vs. resource-based policies, cross-account
  assume-role, permission boundaries, IAM Identity Center / federation, STS.
  This underpins Domain 1 and shows up everywhere.
- **Security:** KMS and encryption (at rest / in transit, key policies, grants),
  Secrets Manager vs. Parameter Store, GuardDuty, Security Hub, Macie, Inspector,
  WAF/Shield, Config, CloudTrail, network security (SGs vs. NACLs), data
  perimeter concepts.
- **Analytics:** the data pipeline shape and where each service fits — Kinesis
  Data Streams vs. Firehose vs. Managed Service for Apache Flink (contrast with
  SQS/EventBridge if the learner knows them), MSK, S3 + Athena, Glue (ETL + catalog),
  Lake Formation, Redshift, OpenSearch, QuickSight, EMR. Focus on "which service
  for which ingestion/processing/query need," not deep internals.

Bias practice questions and scenario reviews toward the learner's weak areas
unless the user asks for something specific.

## Grounding sources (official first)

- AWS documentation: https://docs.aws.amazon.com/ (source of truth)
- Well-Architected Framework — the exam is written against its pillars
- Service FAQs and the official exam guide / AWS Skill Builder Exam Prep
- re:Invent talks and AWS blogs — useful, but confirm specifics against docs

Third-party guides and question banks are fine for practice and intuition, but
unofficial: verify anything load-bearing against the docs, and never reproduce
real/braindump exam questions.
