# Kubernetes and Helm workflows

Pass kubeconfig through the required `kubeconfig` secret. It is written with restrictive
permissions to the runner temporary directory and never uploaded.

- `helm-validate.yml` lints, renders, and schema-validates a chart.
- `helm-diff.yml` records the proposed release diff as an artifact.
- `helm-deploy.yml` upgrades or installs atomically and returns the Helm revision.
- `helm-rollback.yml` rolls back to the specified revision.
- `k8s-manifest-deploy.yml` server-side applies manifests and waits for rollout.

Use the `environment` input on deploy, rollback, and manifest workflows to activate
caller-managed approval rules.
