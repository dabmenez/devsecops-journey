
# 🌍 Terraform Notes

## 📘 What is Terraform?

Terraform is an **Infrastructure as Code (IaC)** tool developed by HashiCorp that allows you to define and provision infrastructure using a high-level configuration language (HCL - HashiCorp Configuration Language).

## 🚀 Key Concepts

- **IaC (Infrastructure as Code)**: Infrastructure is written and managed as code.
- **Version Control**: Changes to infrastructure are trackable just like software code.
- **Multi-cloud Support**: Manage infrastructure across multiple providers (AWS, Azure, GCP, etc).
- **Automation**: Integrates with CI/CD to automate infrastructure creation and destruction.
- **Reusability**: Modules can be reused across environments.
- **Idempotency**: Running the same code multiple times results in the same infrastructure.

## ⚙️ Common Terraform Commands

```bash
terraform init       # Initialize the Terraform project
terraform plan       # Preview infrastructure changes
terraform apply      # Apply the infrastructure changes
terraform destroy    # Destroy the infrastructure
```

## 🧪 Testing Terraform Code

Use static analysis tools to test Terraform code:

- `tfsec`
- `Checkov`
- `terrascan`

These tools help identify security misconfigurations and best practices violations.

## 🔐 Security Best Practices

- **Never hardcode secrets**:
  - Use environment variables
  - Use secret managers like AWS Secrets Manager or Azure Key Vault

```hcl
variable "ARM_CLIENT_SECRET" {
  description = "Azure client secret"
  type        = string
  sensitive   = true
}
```

- **Avoid plaintext secrets in code or state files**
- **Use `.gitignore` and `.terraformignore` files appropriately**

## 📌 Pin Provider Versions

Pin versions of providers to avoid unexpected upgrades:

```hcl
terraform {
  required_providers {
    azurerm = {
      source  = "hashicorp/azurerm"
      version = "=2.96.0"
    }
  }
}
```

This ensures pipeline stability. Update manually when ready.

## 👥 Least Privilege Principle

Use dedicated, least-privilege accounts for Terraform in cloud providers:

- **AWS**: Create a dedicated IAM role with minimum permissions.
- **Azure**: Create a service principal with minimal RBAC role.

## ✅ Benefits of Using Terraform

- Safe and repeatable infrastructure deployments
- Reduced human error
- Scalable infrastructure as your needs grow
- Works across multiple environments (dev/stage/prod)