# Hey, I'm Ekaette 👋

Cloud engineer building and securing **Terraform-provisioned infrastructure at IL5** across Azure Government and AWS GovCloud for Department of Defense programs.

Day to day that means: infrastructure as code, STIG hardening and the automation that keeps it hardened, GitLab CI/CD pipelines, and the SOPs that keep a team building the same way twice. This profile is where I work the same problems in the open.

**Active TS/SCI** · **Security+ CE (DoD 8570 IAT II)**

---

## 🔧 What I Work With

**Cloud**
`Azure Government` `AWS GovCloud` `Azure` `AWS` `AKS` `EKS` `ECS` `ECR` `Entra ID` `Key Vault` `Log Analytics` `Microsoft Sentinel`

**Infrastructure as Code**
`Terraform` `Modular multi-environment projects` `Remote state + locking` `Checkov` `OIDC federation`

**CI/CD**
`GitLab CI` `GitLab administration & migration` `GitHub Actions` `Policy gates` `Shift-left scanning`

**Security & Compliance**
`DISA STIG` `Compliance drift automation` `NIST SP 800-53` `NIST 800-171` `FedRAMP High` `IL4 / IL5` `Zero Trust` `ABAC` `PIM` `CAC / PKI`

**Containers & GitOps**
`Docker` `Kubernetes` `ArgoCD` `Kustomize` `Trivy` `Pod Security Standards`

**Languages & Runtimes**
`Python` `PowerShell` `Bash` `HCL` `KQL`

---

## 🚀 Public Projects

### 🛡️ Azure DevSecOps Pipeline
`Terraform` `Checkov` `GitHub Actions` `OIDC` `Azure RBAC` `Defender for Storage`

A shift-left pipeline that blocks insecure Terraform before it reaches Azure. Every PR triggers a Checkov scan against CIS/NIST controls; branch protection makes the gate hard enforcement rather than advisory. Clean code deploys through passwordless OIDC federation to an RG-scoped least-privilege identity, with state in an Azure blob backend using AzureAD auth — no access keys anywhere.

- 11 Checkov controls validated per run; three soft-failed with documented justification
- OIDC federation (GitHub ↔ Entra ID) — no stored secrets in the pipeline
- Terraform state with `use_azuread_auth` + `use_oidc`, no account keys
- Defender for Storage for runtime behavioral monitoring; Sentinel unified to Defender XDR

**Repo:** [`devsecops-azure-pipeline`](https://github.com/ekaumoh/devsecops-azure-pipeline)

---

## 🔒 Private Work

Several projects live in private repos — some because they mirror patterns from cleared environments, some because they are still being hardened before I open them. Happy to walk through any of these in an interview.

| Project | Stack |
|---|---|
| Secure EKS Platform — GitOps & runtime defense | EKS 1.30 · Terraform · ArgoCD · Kustomize · Trivy · IRSA |
| AWS Container Platform — ECS Fargate | Terraform · ECS · ECR · ALB · split task/execution IAM roles |
| AWS DevSecOps Pipeline | Terraform · Checkov · OIDC · AWS Config · CloudTrail · GuardDuty |
| Azure Cowrie SSH Honeypot | Terraform · Cowrie · AMA · DCR · Log Analytics · Sentinel · KQL |
| Zero Trust Conditional Access Stack | Terraform `azuread` · Entra ID · 11 CA policies as code |
| User Lifecycle Automation | PowerShell · Microsoft Graph API · Azure Automation |

---

## 📄 Currently Building

- [ ] GitLab CI equivalent of the Checkov gate — `.gitlab-ci.yml` with Terraform plan/apply stages and policy enforcement
- [ ] STIG remediation automation — scripted hardening with before/after compliance evidence
- [ ] Terraform module library targeting Azure Government and AWS GovCloud endpoints
- [ ] Zero Trust Identity Platform — SAML/OIDC federation, OPA ABAC enforcement, NIST 800-53 / 800-63 control mapping

---

## 📚 Background

Service desk → cloud engineering → DoD platform work. Along the way:

- **Identity:** Entra ID, ABAC with custom security attributes, PIM, Conditional Access as code, Microsoft Graph API automation, CAC/PKI credentialing in IL5
- **Platform:** M365 GCC High multi-tenant administration, domain controllers and GPO migration, KASM server builds with LDAPS-backed AD auth
- **Automation:** PowerShell and Python against Graph and REST APIs — bulk identity operations, reporting, and a GitLab migration client that moves projects and issue histories across a disconnected boundary
- **Documentation:** runbooks, SOPs, and onboarding guides that let a team survive personnel changes — the work I am most consistently told is missing elsewhere

---

> *"Security gates belong early in the delivery pipeline. Catching issues pre-deploy is cheaper and less disruptive than post-deploy remediation."*