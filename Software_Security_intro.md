# Software Security Engineering

---

## 1. Introduction (30 minutes)

**Title:** Secure Software Engineering: From Code to Cloud

### 1.1 Why Security Is a Developer Problem (5 min)

- Modern applications depend on:
  - Open-source libraries
  - CI/CD pipelines
  - Cloud infrastructure
- Common breach causes:
  - Vulnerable dependencies (According to [SecurityScorecard](https://securityscorecard.com/wp-content/uploads/2025/03/SSC-Third-Party-Breach-Report_031225_03.pdf?utm_source=chatgpt.com), ~30 % of all data breaches involved a third-party or external vendor, up significantly from prior years.)
    - [Slopsquatting](https://en.wikipedia.org/wiki/Slopsquatting)
    - Typosquatting
    - Dependency Confusion
  - Hardcoded secrets ([40% increase in public repos that use co-pilot](https://www.gitguardian.com/files/the-state-of-secrets-sprawl-report-2025))
  - Misconfigured infrastructure
- Shift-Left Security overview

**Key message:** Developers are the first security control.

---

### 1.2 Secure Software Development Lifecycle (SSDLC) (5 min)

- Security across the lifecycle:
  - Design
  - Development
  - Build
  - Deployment
- Security feedback loops vs security gates
- Developer-friendly security tooling

---

### 1.3 Application Security Tooling Overview (10 min)

| Tool Type | Purpose | Typical Findings | Open source tooling |
| --------- | -------- | ----------------- | ------------------ |
| SCA | Dependency vulnerabilities | CVEs, outdated libraries | OWASP Dependecycheck, |
| SAST | Code vulnerabilities | SQLi, XSS, auth flaws | Semgrep, |
| Secrets Scanning | Credential leaks | API keys, tokens | Trufflehog, |
| IaC Scanning | Cloud misconfigurations | Public storage, open ports | Trivy, |

- False positives vs false negatives
- Where tools fit in CI/CD
- No single scanner is sufficient

---

### 1.4 Developer Security Mindset (10 min)

- Secure-by-default development
- Fix early, fix cheap
- Ownership: teams fix what they ship
- Security as engineering feedback

---

## 2. Hands-On Labs

### Lab 1: Software Composition Analysis (SCA)

**Goal:** Identify and remediate vulnerable dependencies

- Scan a sample project
- Identify CVEs and severity
- Upgrade or replace vulnerable libraries

**Outcome:** Understanding dependency risk and CVE data

---

### Lab 2: Static Application Security Testing (SAST)

**Goal:** Detect code-level vulnerabilities

- Scan application source code
- Trace findings to vulnerable code
- Fix and re-scan

**Outcome:** Ability to interpret and remediate SAST findings

---

### Lab 3: Secrets Scanning

**Goal:** Prevent credential exposure

- Scan repository for leaked secrets
- Remove secrets and rotate credentials
- Add pre-commit or CI protection

**Outcome:** Secure secret handling practices

---

### Lab 4: Infrastructure as Code (IaC) Scanning

**Goal:** Prevent insecure cloud deployments

- Scan Terraform/Kubernetes manifests
- Identify risky configurations
- Fix and validate security improvements

**Outcome:** Secure cloud infrastructure before deployment

---

## 3. Closing Talk (15 minutes)

**Title:** Measuring Security & Winning as a Developer Team

### 3.1 Security Metrics That Matter

- Mean Time To Remediation (MTTR)
- Average Age Alive
- Vulnerabilities per release
- % critical issues fixed pre-production
- Dependency freshness

**Avoid:**

- Raw vulnerability counts ?? It has its places.
- Number of scans

---

### 3.2 Practical Tips

- Use severity thresholds
- Automate in CI/CD
- Keep feedback fast
- Focus on developer experience

---

### 3.3 Final Takeaway

Secure software is built by empowered developers, not gated by security teams.
