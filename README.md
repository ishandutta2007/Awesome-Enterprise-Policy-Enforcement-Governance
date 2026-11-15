# Awesome-Enterprise-Policy-Enforcement-Governance

# Top Enterprise Policy Enforcement & Governance Ecosystem

**Curated List of SaaS Platforms & Open-Source GitHub Projects**  
*Focused on Policy-as-Code, Admission Control & Cloud Governance Engines*  
**Last updated: March 2026**

This repository tracks notable **SaaS platforms** and **open-source projects** for **Enterprise Policy Enforcement & Governance**. These tools help organizations codify security and compliance rules as version-controlled, testable artifacts—covering everything from general-purpose policy engines like Open Policy Agent to Kubernetes-native admission controllers and cloud resource governance frameworks.

**Examples** include Open Policy Agent (OPA), Kyverno, Cloud Custodian, HashiCorp Sentinel, Checkov, Datree, 42Crunch, Prisma Cloud, and Styra (the category leaders).

**Open-source emphasis**: This section highlights every major active project for self-hosted policy enforcement, open-source admission control, and community-driven cloud governance—ideal for organizations seeking data sovereignty and avoiding per-resource or per-credit enterprise licensing. The open-source landscape is genuinely mature: **OPA** remains the general-purpose heavyweight despite the "Rego Tax" , **Kyverno** dominates Kubernetes with YAML-native policies , and **Cloud Custodian** provides a decade-proven cloud resource governance DSL .

Contributions welcome! Open an PR to add/update entries. Keep descriptions factual and link to official sites.

## Table of Contents
- [SaaS/Hosted Platforms](#saas-products)
- [Open-Source GitHub Projects](#open-source-github-projects)
- [How to Contribute](#how-to-contribute)
- [Disclaimer](#disclaimer)

## SaaS/Hosted Platforms

| Product | Description | Pricing (Starting) | Free Tier / Trial Limits |
|---------|-------------|-------------------|--------------------------|
| **[Styra (OPA Enterprise)](https://www.styra.com/)** | Commercial control plane for Open Policy Agent. Centralized policy lifecycle management, decision logging, and compliance reporting across Kubernetes, Terraform, and microservices. | Quote-only (enterprise contract) | No free tier; demo via sales |
| **[HashiCorp Sentinel](https://www.hashicorp.com/sentinel)** | Policy-as-code framework embedded in HCP Terraform. **Requires Standard tier or above**—not available on Essentials . Sentinel policy sets are organized by provider, target domain, and environment with version-controlled repositories. | Included with HCP Terraform Standard+ (quote-only) | No standalone free tier; requires Terraform Standard+ subscription |
| **[42Crunch](https://42crunch.com/)** | API security platform with **unlimited API Security Audits and Vulnerability Scans** on paid tiers. **Starter: $375/month** (5 users, 75 endpoints); **Growth: $1,150/month** (15 users, 250 endpoints); **Scale: $12,800/month** (100 users, 2,500 endpoints) . **Free tier**: single user, 100 operations/month each for Contract Generator, Audit, and Scan—IDE access only, no platform account . | Starter: **$375/month** ($4,125/year); Free tier available | **Free**: single user, 100 ops/month per tool, IDE only  |
| **[Prisma Cloud (Palo Alto)](https://www.paloaltonetworks.com/prisma/cloud)** | Comprehensive CNAPP with IaC scanning via **acquired Bridgecrew/Checkov technology** . **No published pricing**—both Business and Enterprise editions are quote-only via a **credit model** where modules burn credits at different rates. Credits sold in annual blocks; no public per-credit rate to verify consumption . | Quote-only (credit-based, annual blocks) | No free tier; demo via sales . |
| **[Postman Enterprise Governance](https://www.postman.com/)** | API governance within Postman Enterprise. API Catalog, governance rules, and workspace controls. **Enterprise: $800/user/month** (annual) . | Enterprise: **$800/user/month** (annual) | No free tier; 30-day trial available |

## Open-Source GitHub Projects

| Project | Star Badge | Description |
|---------|------------|-------------|
| **[Open Policy Agent (OPA)](https://github.com/open-policy-agent/opa)** | [![Stars](https://img.shields.io/github/stars/open-policy-agent/opa?style=social&color=white)](https://github.com/open-policy-agent/opa/stargazers) | **The undisputed heavyweight champion of general-purpose policy-as-code.** Apache-2.0. **Domain-agnostic**—evaluate declarative rules against arbitrary JSON/YAML to block public S3 buckets in Terraform, prevent `:latest` tags in Dockerfiles, or enforce mTLS in Envoy. **The "Rego Tax" is real**: Rego (Datalog-inspired) requires a paradigm shift for engineers accustomed to imperative languages, causing operational bottlenecks where a tiny subset of specialists becomes the bottleneck . **Best for organizations needing one engine across diverse infrastructure**—accept the Rego learning curve for maximum flexibility. |
| **[Kyverno](https://github.com/kyverno/kyverno)** | [![Stars](https://img.shields.io/github/stars/kyverno/kyverno?style=social&color=white)](https://github.com/kyverno/kyverno/stargazers) | **Kubernetes-native policy engine that rejects bespoke languages entirely.** CNCF project, Apache-2.0. **Policies written in native Kubernetes YAML**—no new DSL to learn for teams already fluent in manifests. **Established a massive stronghold in Kubernetes** by eliminating the Rego learning curve . **Validates, mutates, and generates resources**; **background scanning** detects pre-existing violations (unlike native CEL VAP). Benchmark: **+7.6ms median admission latency** at 15 policies . **Best for Kubernetes-first teams** wanting policy enforcement without a new language. |
| **[Cloud Custodian](https://github.com/cloudcustodian/cloud-custodian)** | [![Stars](https://img.shields.io/github/stars/cloudcustodian/cloud-custodian?style=social&color=white)](https://github.com/cloudcustodian/cloud-custodian/stargazers) | **CNCF-incubating cloud governance engine, 10 years in production.** Apache-2.0. **Stateless policy engine** managing AWS, Azure, GCP, OCI, Kubernetes, and Terraform through a **unified YAML DSL**. **Real-time enforcement** via cloud provider control planes; **cost management** (off-hours shutdown, garbage collection); **shift-left** integration with Terraform (Alpha) . **Vendor-neutral**—consistent governance across clouds prevents fragmented postures . **Best for cloud resource governance** (security, FinOps, compliance) at scale. |
| **[Checkov](https://github.com/bridgecrewio/checkov)** | [![Stars](https://img.shields.io/github/stars/bridgecrewio/checkov?style=social&color=white)](https://github.com/bridgecrewio/checkov/stargazers) | **Graph-based static analysis scanner for IaC.** Apache-2.0. Scans **Terraform, OpenTofu, CloudFormation, Kubernetes, Helm, and Bicep** with **built-in CIS and regulatory control mappings** . **Acquired by Palo Alto and powers Prisma Cloud's IaC scanning** . **Best for shift-left IaC security** without a full policy engine. |
| **[KICS (Keeping Infrastructure as Code Secure)](https://github.com/Checkmarx/kics)** | [![Stars](https://img.shields.io/github/stars/Checkmarx/kics?style=social&color=white)](https://github.com/Checkmarx/kics/stargazers) | **Open-source static scanner powered by OPA Rego queries.** Apache-2.0. Detects security misconfigurations across IaC providers using a **Rego-based query engine**—combines OPA's flexibility with pre-built security checks . **Best for teams already invested in OPA/Rego** wanting IaC scanning with the same policy language. |
| **[Datree](https://github.com/datreeio/datree)** | [![Stars](https://img.shields.io/github/stars/datreeio/datree?style=social&color=white)](https://github.com/datreeio/datree/stargazers) | **Policy-as-code for Kubernetes manifests.** Open-source CLI. **Policies defined in YAML** (`policies.yaml`) with rules like `CONTAINERS_MISSING_IMAGE_VALUE_VERSION` and `DEPLOYMENT_MISSING_LABEL_ENV_VALUE` . **Publish policies via CLI** (`datree publish policies.yaml`)—once PaC mode is enabled, the dashboard is read-only . **Best for Kubernetes CI/CD gates** without a full admission controller. |

### Additional Strong Open-Source Options

| Project | Star Badge | Description |
|---------|------------|-------------|
| **[Kubewarden](https://github.com/kubewarden/kubewarden-controller)** | [![Stars](https://img.shields.io/github/stars/kubewarden/kubewarden-controller?style=social&color=white)](https://github.com/kubewarden/kubewarden-controller/stargazers) | **Kubernetes admission controller using WebAssembly policies.** CNCF project. Policies can be written in **Rust, Go, CEL, or Rego**—compiled to Wasm for safe, portable execution . **Best for teams wanting language flexibility** in admission policies without being locked to Rego or YAML. |
| **[CloudFormation Guard (cfn-guard)](https://github.com/aws-cloudformation/cloudformation-guard)** | [![Stars](https://img.shields.io/github/stars/aws-cloudformation/cloudformation-guard?style=social&color=white)](https://github.com/aws-cloudformation/cloudformation-guard/stargazers) | **Rust-based Policy-as-Code DSL for CloudFormation, Terraform JSON plans, and Kubernetes manifests.** Apache-2.0. AWS-maintained validator with a simple declarative syntax . **Best for AWS-centric teams** wanting policy validation without Rego. |
| **[Conftest](https://github.com/open-policy-agent/conftest)** | [![Stars](https://img.shields.io/github/stars/open-policy-agent/conftest?style=social&color=white)](https://github.com/open-policy-agent/conftest/stargazers) | **Test runner for OPA/Rego policies against configuration files.** Apache-2.0. Write tests for your policies and run them in CI . **Best for teams already using OPA** wanting to test policy logic before deployment. |

**Frameworks for building custom systems**: Choose **OPA** for one engine across diverse infrastructure (accepting the Rego Tax) , **Kyverno** for Kubernetes-native YAML policies with background scanning , or **Cloud Custodian** for cloud resource governance with real-time remediation —all without per-resource or per-credit enterprise licensing.

## How to Contribute

1. Fork the repo.
2. Add/edit entries in `README.md` (follow existing format).
3. Include: name, link, 1–2 sentence description, and whether it's SaaS or open-source.
4. Submit PR with a short explanation.

Star the repo if you find it useful!

## Disclaimer

- This is a **community-curated** list — not exhaustive and not an endorsement.
- Policy enforcement platforms govern infrastructure and access decisions; **policy bugs can either block legitimate deployments or allow security violations**—test policies in audit mode before enforcement.
- **The "Rego Tax" is the defining cost of general-purpose policy-as-code.** OPA's flexibility comes at the price of a steep learning curve—platform teams report that **a tiny subset of specialized engineers becomes the bottleneck**, stalling security initiatives . **Kyverno eliminates this for Kubernetes** by using native YAML, but is Kubernetes-specific . **Cloud Custodian provides a decade-proven alternative** for cloud resource governance with a simpler DSL . **Commercial platforms are quote-only and opaque**: Prisma Cloud's credit model has **no public per-credit rate**, making consumption impossible to forecast . **42Crunch publishes transparent API security tiers** ($375–$12,800/month) with a genuine free tier . **Open-source is genuinely free in licenses but costs engineering time**—realistically **0.5 to 1 full-time engineer for the first two quarters** and ongoing maintenance . **Validate whether you need Kubernetes admission (Kyverno), cloud governance (Custodian), or general-purpose policy (OPA)** before committing.

---

**Made for platform engineers, security architects, and organizations building policy-driven infrastructure.**  
Let's make enterprise policy enforcement more open, testable, and governable.
