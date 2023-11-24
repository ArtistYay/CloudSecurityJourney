# Table of contents

- [*Understand Terraform basics*](#understand-terraform-basics)
  - [*Plugin-based architecture*](#plugin-based-architecture)
  - [*How does Terraform find and fetches providers*](#how-does-terraform-find-and-fetches-providers)
  
# *Understand Terraform basics*

**Declarative Language**: Terraform uses HashiCorp Configuration Language (HCL), a simple and easy-to-learn language that allows you to describe the desired state of your infrastructure. Terraform then takes care of figuring out how to create the resources needed to reach that desired state.

**Modules**: Terraform's module system allows you to organize and reuse infrastructure configurations. Modules are essentially self-contained packages of infrastructure code that can be included in other Terraform configurations. This modularity makes it easy to share and reuse infrastructure components across different projects and teams.

**State**: Stores information about the infrastructure resources it manages in a state file. This state file keeps track of the current state of your infrastructure and allows Terraform to make idempotent changes, meaning that applying the same configuration multiple times will not result in duplicate or inconsistent resource creation.

**Provider Plugins**: Uses provider plugins to interact with different cloud providers or infrastructure platforms. Each provider plugin provides an interface for creating, updating, and destroying resources on a specific platform.

**Versioning**: Supports versioning of provider plugins, allowing you to specify which version of a provider plugin you want to use for a particular configuration. This ensures that your infrastructure is provisioned and managed using the desired version of the provider plugin.

## *Plugin-based architecture*

Plugin-based architecture is a software design pattern that allows for the addition of new functionalities to an application without modifying the core code. Plugins are essentially independent modules that provide specific features or capabilities and can be easily added, removed, or updated without affecting the main application.

To illustrate the concept, imagine you have a basic text editor application. This application provides essential text editing functions like cut, copy, paste, and save. Now, you want to add advanced features like spell checking, grammar checking, and translation. Instead of modifying the core code of the text editor, you can create separate plugins for each of these features.

## *How does Terraform find and fetches providers*

The `terraform init` command is the primary method for Terraform to find and fetch providers. It consults the root configuration directory to determine the required provider plugins based on the specified provider blocks. Searches the local plugin cache for the specified provider plugins and attempts to use them if they are present, If the required provider plugins are not found in the local cache, Terraform downloads them from the Terraform Registry. Installs the downloaded provider plugins in the appropriate plugin directory, making them available for use. Even creates a lock file, typically named `.terraform.lock.hcl`, which records the versions and hashes of the installed provider plugins. This lock file ensures that subsequent terraform init commands will use the same versions of the plugins, maintaining consistency and reproducibility.