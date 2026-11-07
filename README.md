# Azure Terraform Modules

Reusable, reviewable Terraform building blocks for Azure platform engineering. This repository starts with a typed Network Security Group module and a small caller example.

## What is included

- `modules/network-security-group` — configurable NSG rules, input validation, and outputs.
- `examples/basic` — a minimal caller configuration for a resource group you own.
- `.github/workflows/validate.yml` — formatting and configuration checks that do not require Azure credentials.
- `docs/` — module contract, security considerations, and release guidance.

## Quick start

Requirements: Terraform 1.9+ and AzureRM provider 4.x. Authenticate using your approved Azure identity and review the plan before applying. The example creates Azure resources and can incur charges.

```bash
cd examples/basic
terraform init
terraform validate
terraform plan
```

## Design principles

- Keep resource-group ownership with the calling platform team.
- Use stable, named rule keys and explicit priorities for reviewable plans.
- Validate inputs early and keep cloud credentials out of pull-request checks.
- Pin provider and action versions in production pipelines; review upgrades deliberately.

## Production adoption

Treat this as a reference implementation. Add organization-specific naming, policy, diagnostics, network associations, and deployment controls before production use. No license has been selected; reuse rights are not granted by this repository.
