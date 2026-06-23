# Hey, I'm Ekaette 👋

Cloud engineer transitioning into **cloud security and platform engineering** building production-grade infrastructure on AWS and Azure with a focus on DevSecOps, GitOps, and compliance-aligned platforms.

I learn by building. Every project here is hands-on, documented, and designed to reflect real-world engineering decisions.

---

## 🔧 What I Work With

**Cloud**
`AWS` `Azure` `EKS` `AKS` `ECS` `ECR` `S3` `IAM` `Lambda` `EventBridge` `Azure Functions` `App Services` `Cosmos DB` `Key Vault` `Log Analytics` `Microsoft Sentinel`

**Infrastructure as Code**
`Terraform` `Modular multi-environment projects` `Checkov` `GitHub Actions OIDC`

**Containers & GitOps**
`Docker` `Kubernetes` `ArgoCD` `Kustomize` `Trivy` `Pod Security Standards`

**Security & Compliance**
`NIST SP 800-53` `STIG hardening` `ATO readiness` `IRSA` `Workload Identity` `Entra ID` `ABAC` `Shift-left security`

**Languages & Runtimes**
`Python` `Node.js` `Bash` `KQL` `HCL`

---

## 🚀 Featured Projects

### 🛡️ Secure EKS Platform | GitOps, Policy Gates & Runtime Defense
`AWS` `EKS` `Terraform` `ArgoCD` `Kustomize` `Trivy` `GitHub Actions` `OIDC` `ECR`

A full-stack portfolio piece covering platform engineering and cloud security end to end.

- Provisioned a private EKS 1.30 cluster with VPC, Spot worker nodes, IRSA, and AWS Load Balancer Controller
- Enforced Pod Security Standards (`baseline`/`restricted`), ResourceQuota, and LimitRange at the namespace level
- Built a GitOps pipeline across three repos (`eks-infra` / `eks-platform` / `eks-manifests`) with clean separation of concerns — Terraform owns cloud infra, ArgoCD owns everything inside the cluster
- CI pipeline performs Docker build → Trivy image scan (hard-block on CRITICAL/HIGH CVEs) → ECR push → Kustomize manifest update via fine-grained PAT
- ArgoCD watches `eks-manifests` with auto-sync, prune, and self-heal enabled

**Repos:** [`eks-infra`](https://github.com/ekaumoh/eks-infra) · [`eks-platform`](https://github.com/ekaumoh/eks-platform) · [`eks-manifests`](https://github.com/ekaumoh/eks-manifests)

---

### 🪖 DoD Container Modernization Platform
`Azure` `AKS` `Terraform` `NIST SP 800-53` `GitHub Actions` `OIDC`

Terraform project targeting Azure AKS with IL2–IL4 compliance alignment and a GovCloud migration path.

- Six reusable modules: networking, AKS, ACR, Key Vault, monitoring, and Azure Policy
- Hub-spoke VNet topology with Azure Firewall (Standard dev / Premium + IDPS prod)
- Private AKS cluster with Entra ID RBAC, Workload Identity, Defender for Containers
- HSM-backed CMK keys, ACR Premium with content trust, Log Analytics with KQL alert rules
- Azure Policy enforces the built-in NIST SP 800-53 Rev 5 initiative across environments

**Repo:** [`devsecops-azure-pipeline`](https://github.com/ekaumoh/devsecops-azure-pipeline)

---

### 🍯 Azure Cowrie SSH Honeypot
`Azure` `Terraform` `Log Analytics` `AMA` `DCR` `KQL` `Azure Monitor Workbooks` `Microsoft Sentinel`

A deliberately exposed honeypot designed to attract real-world SSH attack traffic and surface attacker behavior through Azure-native observability tooling.

- Ubuntu 22.04 VM with iptables NAT rules routing port 22 → Cowrie on port 2222
- Logs shipped via rsyslog → Azure Monitor Agent → DCR → Log Analytics Workspace
- Azure Monitor Workbook with GeoIP attack map and hourly attempt charts built from KQL
- Microsoft Sentinel integration planned: onboarding resource + scheduled analytic rule for credential spray detection

**Repo:** [`lets-build`](https://github.com/ekaumoh/lets-build)

---

## 📚 Background

Before going deep on cloud security and platform engineering, I built hands-on experience across:

- **Azure identity and access**: Entra ID, ABAC with custom security attributes, Workload Identity, Microsoft Graph API for automated group management
- **Serverless on Azure**: Azure Functions (Node.js + Python), Logic Apps, Cosmos DB, App Services including production debugging of deployment failures, native dependency issues, and storage account key rotation
- **Linux fundamentals**: filesystem hierarchy, systemd, user/permission management, bash scripting, log analysis, and STIG-flavored security hardening
- **DevSecOps pipelines**: GitHub Actions CI/CD on both AWS (OIDC → ECR → ECS) and Azure (service principal + OIDC → AKS), Checkov IaC scanning with `.checkov.yaml` configuration, Trivy image scanning

---

## 📄 Currently Building

- [ ] End-to-end EKS pipeline test with ArgoCD Application objects
- [ ] Microsoft Sentinel integration for Cowrie honeypot (credential spray analytic rule)
- [ ] Architecture Decision Records for IL-environment design choices

---

> *"Security gates belong early in the delivery pipeline. Catching issues pre-deploy is cheaper and less disruptive than post-deploy remediation."*