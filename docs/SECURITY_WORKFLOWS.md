# Security workflows

- `tfsec-scan.yml` scans Terraform and publishes SARIF.
- `trivy-scan.yml` scans an image, produces a CycloneDX SBOM, and uploads both reports.
- `checkov-scan.yml` scans Terraform, CloudFormation, Dockerfile, or all supported source.
- `helm-validate.yml` can render Helm charts to YAML and optionally run Checkov on the rendered manifests with `checkov-framework: all`.

Security workflows need `security-events: write` in the caller to upload SARIF. Their
reports are retained as workflow artifacts even when the scanner fails. Use `soft-fail`
or `fail-on-vulnerability` only for transitional reporting; enforce findings in protected
branches once baselines are addressed.
