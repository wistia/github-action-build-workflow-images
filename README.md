# github-action-build-workflow-images
Dispatchery V2 GitHub Action - build workflow images

## Usage

In `.github/workflows/ci.yml`:

    jobs:
      process-workflows:
        runs-on: ubuntu-latest
        steps:
          - name: Build Docker images that Argo workflows depend on
            uses: wistia/github-actions-build-workflow-images
            with:
              repo_name: ${{ github.event.repository.name }}
              git_ref: ${{ github.ref }}
              git_sha: ${{ github.sha }}
              ecr_hostname: <aws_account>.dkr.ecr.<region>.amazonaws.com
