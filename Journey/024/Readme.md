# Table of contents

- [*Use Terraform outside of core workflow*](#use-terraform-outside-of-core-workflow)
  - [*Describe when to use `terraform import` to import existing infrastructure into your Terraform state*](#describe-when-to-use-terraform-import-to-import-existing-infrastructure-into-your-terraform-state)
  - [*Use ```terraform state``` to view Terraform state*](#use-terraform-state-to-view-terraform-state)
  - [*Customizing Terraform Behavior*](#customizing-terraform-behavior)
  - [*Describe when to enable verbose logging and what the outcome/value is.*](#describe-when-to-enable-verbose-logging-and-what-the-outcomevalue-is)

# *Use Terraform outside of core workflow*

Terraform's core workflow is typically used to plan, apply, and destroy infrastructure resources. However, there are instances where you may need to use Terraform outside of this core workflow, such as importing existing infrastructure, manipulating the Terraform state file, or performing advanced configurations.

## *Describe when to use `terraform import` to import existing infrastructure into your Terraform state*

Terraform import is a command used to bring existing infrastructure resources under Terraform management. It is typically used when you have already created infrastructure resources using other methods, such as the cloud provider's web console or manual configuration, and you want to start managing those resources using Terraform. You can even use import to recover a state file by importing the existing infrastructure resources.

```bash
terraform import aws_instance.my-instance i-0123456789abcdef0
```

## *Use ```terraform state``` to view Terraform state*

The `terraform state` command is a versatile tool for viewing and interacting with the Terraform state file. It provides a variety of options for examining the current state of your infrastructure resources, modifying state data, and performing advanced operations.

The most basic usage of `terraform state` is to view the current state of your infrastructure resources. To list all managed resources, use the terraform state list command.

```bash
terraform state list aws_
```
> View the current state of all AWS resources.

For more detailed information about a specific resource, use the terraform state show command followed by the resource type and identifier.

```bash
terraform state show aws_instance.my-instance
```
> View the state of an AWS EC2 instance named `my-instance`.

### *Modifying State Data*

In some cases, you may need to modify the Terraform state file directly. This can be useful for correcting errors, updating resource attributes, or removing resources that no longer exist. To modify state data, use the terraform state rm command to remove a resource from the state, or the terraform state mv command to move a resource to a different provider or configuration block.

### *Advanced Operations*

The `terraform state` command also offers advanced operations for manipulating the state file and performing troubleshooting. For example, the `terraform state lock` command can be used to acquire a lock on the state file to prevent concurrent modifications, while the `terraform state diff` command can display the differences between the current state and the state stored in the state file.

## *Customizing Terraform Behavior*

Terraform allows you to customize its behavior through environment variables, configuration files, and command-line options. For instance, you can set the `TF_VAR_FILE` environment variable to specify the path to a configuration file containing Terraform variables.

## *Describe when to enable verbose logging and what the outcome/value is.*

Verbose logging in Terraform provides a detailed record of the tool's actions and internal operations. This increased verbosity is beneficial for debugging and troubleshooting, understanding complex configurations, monitoring infrastructure changes, auditing and compliance, and identifying potential issues early on. However, it's important to enable verbose logging only when necessary to avoid overwhelming your system with excessive log data.