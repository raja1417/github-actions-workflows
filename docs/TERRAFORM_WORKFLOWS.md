# Terraform workflows

All Terraform workflows accept a `working-directory`; configure cloud credentials in
the caller and pass backend configuration as a secret where required.

- `terraform-validate.yml` runs init without a backend, validate, and format checks.
- `terraform-plan.yml` creates `tfplan` and JSON artifacts, summarizes changes, and
  comments on pull requests.
- `terraform-apply.yml` downloads the named plan artifact and applies it. Set
  `environment: prod` to use the caller's protected production environment.
- `terraform-destroy.yml` is callable and manually dispatchable. It requires
  `confirm: DESTROY` and supports environment protection.
- `terraform-cost-estimate.yml` uses `INFRACOST_API_KEY` to publish an Infracost report.

Plan and apply must use the same `artifact-name`; application callers should run plan
and apply in the same workflow run.
