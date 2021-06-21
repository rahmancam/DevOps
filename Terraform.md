## What is Terraform ?
    - It allows you to automate and manage your infrastructure
    - your platform
    - and services that run on that platform
    - Open source
    - Declarative (define what end result you want)
    - Terraform is a tool for infrastructure provisioning

### AWS (Tasks)
    -   Prepare infrastructure
        - private network space
        - ec2 server instances
        - install docker and other tools
        - security (firewalls and policies)
    - Deploy applications
    - 2 separate teams (Infra and development)
        - Infra Team - Provisioning infrastructure
        - Dev Team - Deploy applications
### Terraform
    - It is used for Provisioning Infrastrcture (In correct order)
        - Create VPC
        - spin-up servers
        - create AWS users and permissions
        - install Docker

### Ansible vs Terraform
    - Similiarities
        - Both are Infrastructure as as Code
        - Both provisioning, configuring, and managing the infrastrcture
    - Differences
        - Terraform is mainly infrastrcture provisioning tool
        - Terraform has the possibility to deploy apps with other tools in infrastrcture
        - Ansible is mainly a configuration tool
            - configure that infrastructure
            - deploy apps
            - install/ update software
        - Ansible is more mature
        - Terraform is more advanced in orchestration
        - Terraform is better for provisioning infrastrcture
        - Ansible is better for configuring that infrastrcture
    - DevOps use combination of these tools to cover end-to-end
### Managing Infrastructure with Terraform
    - Create infrastrcture
    - Changes to infrastructure
    - Replicating infrastrcture
        - DEV environment -> PROD environment

### How does Terraform work ?
    - Terraform Core
        - TF-Config (What to create/ configure)
        - Terraform State (current state of setup)
        - compare current state vs desired state (config file) and creates a execution plan for what needs to be created/updated/destroyed
    - Providers
        - AWS | Azure | [IaaS]
        - Kubernetes | [PaaS]
        - Fastly | [SaaS]
    - Terraform supports 100+ providers
    - Through providers you get access to resources
    - Once the `core` creates execution plan, it uses providers of specific technolgoies (to execute the plan with Providers)

Example Terraform configuration file (AWS)
```
# Configure the AWS provider
provider "aws" {
    version = "~> 2.0"
    region = "us-east-1"
}

# Create a VPC
resource "aws_vpc" "example" {
    cidr_block = "10.0.0.0/16"
}
```
Example configuration file for Kubernetes Provider
```
# Configure the Kubernetes Provider
provider "kubernetes" {
    config_context_auth_info = "ops"
    config_context_cluster = "mycluster"
}

resource "kubernetes_namespace" "example" {
    metadata {
        name = "my-first-namespace"
    }
}
```

### Declarative vs Imperative
    - Declarative
        - you define the end state in your config file
            - 5 servers with the following network config
            - AWS user with following permissions
        - define the desired state in configuration file
            - 7 servers
            - this firewall config
            - User with following permissions
        - figure out yourself what needs to be done
        - adjust old configuration file and re-execute
        - clean and small config file
        - always know the current setup
    - Imperative
        - you define exact steps - HOW
        - you give instructions
            - remove 2 servers
            - add firewall config
            - add permissions to AWS user

### Terraform commands stages
    - Refresh
        - Query the infrastructure provider to get current state
    - Plan
        - Create an execution plan
        - Just a preview, no changes to real resources
    - apply
        - execute the plan
    - destroy
        - destroy the resources/ infrastructure





