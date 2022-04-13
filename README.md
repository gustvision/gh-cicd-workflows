# gh-cicd-workflows

## Description

This repository contains reusable CI/CD GitHub workflows for our organization.

## How to use

### Example with `cd-terraform`

```yaml
jobs:
  # Terraform plan only
  terraform-plan:
    uses: gustvision/gh-cicd-workflows/.github/workflows/cd-terraform.yml@main
    with:
      tf_folder: "path/to/your/terraform/folder"
    secrets:
      aws_access_key_id: ${{ secrets.AWS_ACCESS_KEY_ID }}
      aws_secret_access_key: ${{ secrets.AWS_SECRET_ACCESS_KEY }}
      token: ${{ secrets.ORG_PRIVATE_REPOSITORY_READ_ACCESS_TOKEN }}

  # Terraform plan + apply
  terraform-apply:
    uses: gustvision/gh-cicd-workflows/.github/workflows/cd-terraform.yml@main
    with:
      tf_folder: "path/to/your/terraform/folder"
      tf_apply: true
    secrets:
      aws_access_key_id: ${{ secrets.AWS_ACCESS_KEY_ID }}
      aws_secret_access_key: ${{ secrets.AWS_SECRET_ACCESS_KEY }}
      token: ${{ secrets.ORG_PRIVATE_REPOSITORY_READ_ACCESS_TOKEN }}
```
