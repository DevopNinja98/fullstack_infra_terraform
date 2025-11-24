This GitHub Actions workflow (.github/workflows/terraform-cicd.yml) designed to automate the provisioning and management of infrastructure on Amazon Web Services (AWS) using Terraform and Kubernetes. This workflow aligns with the diagram illustrating the infrastructure deployment process. Let's break down the code step-by-step:
<img width="1280" height="720" alt="image" src="https://github.com/user-attachments/assets/5e8c8f06-0319-4a80-ad05-c069e0046019" />
**1. Workflow Trigger (on):**

- The workflow is set to run automatically whenever there's a push to the `main` branch of the repository. Additionally, it can be triggered manually through the "Run workflow" button in the GitHub Actions interface (`workflow_dispatch`).

**2. Permissions (permissions):**

- The workflow requests the `id-token: write` permission to authenticate with GitHub and the `contents: read` permission to access the repository's contents.

**3. Job Definition (jobs):**

- A single job named `terraform` is defined.
- It runs on the `ubuntu-latest` virtual environment provided by GitHub Actions.
- The `environment: production` line specifies that this job targets the production environment.

**4. Steps:**

- **Checkout:** This step checks out the code from your repository to the runner.
- **Setup Terraform:** This step installs Terraform on the runner, using the specified version (1.8.1).
- **Configure AWS Credentials:** This step securely retrieves your AWS credentials (Access Key ID and Secret Access Key) from GitHub Secrets and configures the AWS region (`ap-south-1`).
- **Terraform Init:** This step initializes the Terraform working directory by downloading providers and modules.
- **Terraform Plan:** This step creates an execution plan, showing what changes Terraform will make to your infrastructure. The `continue-on-error` flag allows the workflow to proceed even if the plan fails, which is useful for debugging.
- **Terraform Apply:** This step applies the changes to your AWS infrastructure based on the plan. The `auto-approve` flag skips the confirmation prompt.
- **Install EBS CSI Driver:** This step sets up the AWS EBS CSI driver, which allows Kubernetes to use EBS volumes for persistent storage.
- **Clone Manifests:** This step clones a repository containing Kubernetes manifests for a 3-tier application.
- **Apply Kubernetes Manifests:** It then applies these manifests to deploy the frontend, backend, database, and associated services and secrets to the EKS cluster.
