# Immutable Linux Auditor - Roadmap

This document outlines the development roadmap for the Immutable Linux Auditor project.

## Project Vision

A comprehensive security auditing tool for immutable Linux distributions (Fedora Silverblue/Kinoite, NixOS, openSUSE MicroOS, Endless OS, Vanilla OS, etc.), focusing on configuration drift detection, compliance validation, and security posture assessment.

---

## Phase 1: Foundation & Infrastructure

### Completed
- [x] Repository initialization
- [x] Hub-and-spoke SCM mirroring (GitHub, GitLab, Codeberg, Bitbucket)
- [x] CI/CD pipeline security hardening
  - SSH known_hosts verification (MITM protection)
  - Job timeout limits
  - Concurrency controls
  - Strict error handling (`set -euo pipefail`)
  - Minimal permissions model

### In Progress
- [ ] Security policy documentation (SECURITY.md)
- [ ] Contributing guidelines
- [ ] License file (AGPL-3.0-or-later)

### Planned
- [ ] Development environment setup (devcontainer/Nix flake)
- [ ] Code quality tooling (linters, formatters, pre-commit hooks)
- [ ] Automated release workflow
- [ ] Dependency scanning (Dependabot/Renovate)
- [ ] CodeQL/SAST integration

---

## Phase 2: Core Auditing Engine

### System Detection
- [ ] Auto-detect immutable Linux distribution type
- [ ] Parse OSTree/rpm-ostree configuration
- [ ] Parse NixOS configuration.nix
- [ ] Parse Flatpak/Snap overlay configurations
- [ ] Detect container runtime configurations (Podman/Docker)

### Configuration Drift Detection
- [ ] Baseline snapshot capture
- [ ] File system integrity monitoring
- [ ] Configuration change detection
- [ ] OSTree deployment comparison
- [ ] Layered package tracking

### Audit Modules
- [ ] Boot integrity verification (Secure Boot, TPM, measured boot)
- [ ] Filesystem permissions audit
- [ ] SELinux/AppArmor policy validation
- [ ] Network configuration audit
- [ ] Service/systemd hardening check
- [ ] User/group permission audit
- [ ] SSH configuration audit
- [ ] Firewall rules validation

---

## Phase 3: Compliance & Reporting

### Compliance Frameworks
- [ ] CIS Benchmark support (distribution-specific)
- [ ] STIG compliance checking
- [ ] Custom policy definition (YAML/TOML)
- [ ] Policy-as-code integration

### Reporting
- [ ] JSON/YAML structured output
- [ ] Human-readable terminal reports
- [ ] HTML/PDF report generation
- [ ] SARIF output for GitHub Advanced Security
- [ ] Prometheus metrics export
- [ ] Integration with vulnerability databases (CVE, OSV)

---

## Phase 4: Advanced Features

### Continuous Monitoring
- [ ] Daemon mode for real-time monitoring
- [ ] Webhook/alerting integration (Slack, Teams, PagerDuty)
- [ ] systemd timer/cron scheduling
- [ ] Centralized logging support (journald, syslog, cloud)

### Multi-System Management
- [ ] Remote system auditing via SSH
- [ ] Ansible/Salt integration
- [ ] Fleet-wide compliance dashboard
- [ ] Kubernetes node auditing

### Remediation
- [ ] Guided remediation suggestions
- [ ] Auto-fix for common issues (with user consent)
- [ ] Rollback recommendations (OSTree/NixOS generations)

---

## Phase 5: Ecosystem & Distribution

### Packaging
- [ ] Native packages (RPM, DEB, PKG)
- [ ] Flatpak distribution
- [ ] Container image (distroless)
- [ ] NixOS flake/overlay
- [ ] Homebrew formula

### Documentation
- [ ] User documentation
- [ ] API documentation
- [ ] Architecture decision records (ADRs)
- [ ] Security audit documentation

---

## Security Considerations

Throughout development, the following security practices will be maintained:

1. **Supply Chain Security**
   - Pinned dependencies with hash verification
   - SBOM generation
   - Signed releases (GPG/Sigstore)
   - Reproducible builds where possible

2. **Code Security**
   - No execution of untrusted input
   - Minimal privilege operation
   - Memory-safe language consideration (Rust preferred)
   - Regular security audits

3. **Operational Security**
   - Audit logs for all operations
   - No persistent credentials storage
   - Integration with system secret stores (systemd-creds, libsecret)

---

## Contributing

This project welcomes contributions. Priority areas:
- Distribution-specific audit modules
- Compliance framework implementations
- Documentation improvements
- Bug reports and security disclosures

---

## Version History

| Version | Date | Milestone |
|---------|------|-----------|
| 0.0.1 | 2025-12 | Initial SCM infrastructure |

---

*Last updated: 2025-12-17*
