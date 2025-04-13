# 🔐 Automated Security Scanning Pipeline

This repo contains GitHub Actions workflows for performing continuous security scanning across application code, container files, and infrastructure as code (IaC) using open-source tools. We love open source and we don't care who knows!

---

## Tools Used

| Tool        | Purpose                                | Output   |
|-------------|----------------------------------------|----------|
| **Trivy**   | Scans file system & Dockerfiles        | SARIF    |
| **Checkov** | Scans Terraform IaC for misconfigs     | SARIF    |
| **Bandit**  | Scans Python code for insecure usage   | Console  |
| **OWASP DC**| Scans dependencies for known CVEs      | HTML     |

---

## Runs:

- On any push or PR involving:
  - Dockerfiles
  - Terraform (`.tf`) files
- Can also be triggered manually via the **Actions** tab

---

## Results

| Tool        | Where to View                            |
|-------------|------------------------------------------|
| Trivy, Checkov | [Security → Code Scanning Alerts](../../security/code-scanning) |
| Bandit      | GitHub Actions logs (console output)     |
| OWASP DC    | Downloadable HTML report (in artifacts)  |

---

## Workflow Files

| File | Description |
|------|-------------|
| `.github/workflows/security-scan-sarif.yml` | Runs Bandit & Trivy |
| `.github/workflows/docker-terraform-sarif.yml` | Runs Trivy & Checkov with SARIF |

---

## Roadmap?

- 💬 Add Slack or PR comments for findings
- 🔒 Enforce severity thresholds (fail build on critical issues)
- ⚙️ Add `.trivyignore` or `.checkov.yaml` config files for tuning

---

## License

MIT — use freely, improve freely!
