# Using reusable workflows

Reference workflows by a tag or immutable commit SHA from an application repository.
Grant only the permissions required by the called workflow and explicitly pass required
secrets. Configure GitHub environments such as `prod` with required reviewers.

```yaml
jobs:
  validate:
    uses: raja1417/github-actions-workflows/.github/workflows/terraform-validate.yml@v1
    with:
      working-directory: infrastructure
```

Reusable workflows run in the caller repository, so checkout, paths, pull-request
comments, artifacts, and environments refer to that repository. See the category
documents for each workflow's inputs and secrets.
