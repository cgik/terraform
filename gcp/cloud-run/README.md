# Terraform for cloud run

## Example usage:
```
terraform {
  cloud {
    organization = "org-example"

    workspaces {
      name = "workspace-example"
    }
  }
}

provider "google" {
  project     = ""
  region      = "us-central1"
}

module "cloud-run" {
    source = "github.com/cgik/terraform/gcp/cloud-run"

    project_id = ""
    application_name = "application"
    application_port = "8080"
    application_image = "gcr.io/container:v1"
    url = "mywebsite.local"
    region = "us-central1"
}
```