# Table of contents

- [*Interact with Terraform modules*](#interact-with-terraform-modules)
- [*Contrast and use different module source options including the public Terraform Module Registry*](#contrast-and-use-different-module-source-options-including-the-public-terraform-module-registry)
- [*Interact with module inputs and outputs*](#interact-with-module-inputs-and-outputs)
  - [*Describe variable scope within modules/child modules*](#describe-variable-scope-within-moduleschild-modules)
  - [*Set module version*](#set-module-version)

# *Interact with Terraform modules*

Terraform modules provide a mechanism to package and reuse infrastructure configurations. They allow you to organize complex infrastructure setups into manageable components and share them with others. You can obtain modules from the Terraform Registry or Private Repositories.

# *Contrast and use different module source options including the public Terraform Module Registry*

| Module Source Option | Description | Advantages | Disadvantages |
|---|---|---|---|
| Terraform Registry (terraform.io/modules) | A central repository for publicly available Terraform modules | Easy to find and use. Modules are well-maintained and updated regularly. | May not have modules for all specific needs. |
| Private Registry (e.g., GitLab, Bitbucket) | A private repository for storing and managing Terraform modules | Provides control over module access and versions. Can include custom modules developed internally. | Requires additional setup and maintenance. |
| Local Directory (e.g., `./modules`) | Modules stored within the Terraform project directory | Convenient for local development and testing. | Requires manual updates and version control. |
| URL (e.g., `github.com/hashicorp/terraform-aws-modules/archive/refs/tags/v3.13.0.tar.gz`) | Modules hosted on a public or private URL | Can access modules from various sources, including GitHub repositories. | Requires manual maintenance and version control. |
| Remote Module (e.g., `git@github.com:hashicorp/terraform-aws-modules.git`) | Modules stored in a Git repository | Allows for direct integration with Git repositories. | Requires Git access and knowledge. |

# *Interact with module inputs and outputs*

Module inputs are parameters used to customize the behavior of a Terraform module. They are declared within the module's configuration and can be passed to the module when it is instantiated in your Terraform configuration. 

Let's say you're building a house, and you're using a pre-designed blueprint for a specific type of house. This blueprint is like a Terraform module – it provides a general structure for the house, but you may need to customize it to fit your specific needs.

Module inputs are like the knobs and switches you use to adjust the features of the pre-designed house. You can set the number of bedrooms, the size of the kitchen, or even the color of the walls. Similarly, module inputs allow you to control the behavior of a Terraform module.

When you use a Terraform module in your configuration, you can pass these input values to the module, just like you would set the knobs and switches on a pre-designed house. This lets you customize the module to fit your specific infrastructure needs.

To pass input values to a module, use the `source `block's `vars` attribute. For example, to pass an input variable named `vpc_id` to a module named `aws_vpc`, you would use the following syntax:

```Terraform
module "vpc" {
  source = "terraform-aws-modules/vpc/aws"

  vars {
    vpc_id = "vpc-12345678"
  }
}
```

Module outputs are values produced by a Terraform module that can be used in other parts of your Terraform configuration. To access a module's output, use the module's name followed by the output variable name. For instance, to access an output variable named `subnet_ids` from a module named `aws_vpc`, you would use the following syntax:

```Terraform
resource "aws_instance" "example" {
  ami           = "ami-0c55b159cbfafe1f0"
  instance_type = "t2.micro"

  subnet_id = module.vpc.output.subnet_id
}
```
> The output variable needs to be defined before being called.

## *Describe variable scope within modules/child modules*

Variable scope in Terraform refers to the visibility and accessibility of variables within different parts of your infrastructure configuration. 

### *Variable scope in modules*

Within a single Terraform module, variables have local scope. This means that variables are only visible and accessible within the module itself. They cannot be directly accessed or modified from outside the module. This helps to maintain the modularity and encapsulation of Terraform modules, preventing unintended modifications to variables that might affect the module's behavior.

### *Variable scope in child modules*

When a module calls another module, referred to as a child module, the child module does not have direct access to variables defined in the parent module. This is because the child module has its own local scope, and variables declared in the parent module are considered external to the child module.

To pass variables from a parent module to a child module, you need to explicitly declare the variables as inputs in the child module's configuration and provide their values when calling the child module. This ensures that the child module has access to the necessary configuration information from the parent module.

## *Set module version*

Specifying the version of a Terraform module ensures that you are using the desired release of the module and prevents unintended behavior or compatibility issues. You can use version constraints that allows you to define a range of acceptable versions for a module. For example, `~> 3.12.0` uses the latest version of the module that is greater than or equal to 3.12.0. You can also use a explicit version number for a module, `3.13.0`.

To update the version of a Terraform module, simply modify the `version` attribute within the `module` block to the desired version constraint or explicit version number. Then, run the `terraform init` command to update the installed module version.