# Terraform App Service Provision
Automate Azure App Service Creation using Terraform

The necessary steps and code may be found at:

https://learn.microsoft.com/en-us/azure/app-service/provision-resource-terraform

## Prerequisites

For app service automation, configuring Terraform in cloud shell is very helpful.

I would reccomend using Azure powershell over windows powershell as it can be a little easier to navigate Azure directories.

If one wants to use terraform with windows, look to this link: https://learn.microsoft.com/en-us/azure/developer/terraform/get-started-windows-powershell?tabs=bash VS code, along with terraform packages are needed. 

Using Azure Powershell the commands should be:

```
curl -O https://releases.hashicorp.com/terraform/1.4.6/terraform_1.4.6_linux_amd64.zip
```

```
unzip terraform_1.4.6_linux_amd64.zip
```

```
mkdir bin
```

```
mv terraform bin/
```

This creates the directory "bin" and moves the unzipped terraform files into that directory.


## Implementation

1. Create a directory in which to test and run the sample Terraform code and make it the current directory.
```
mkdir appservice_tf_quickstart

cd appservice_tf_quickstart
```

2. Create a file named main.tf and paste the code from https://learn.microsoft.com/en-us/azure/app-service/provision-resource-terraform

```
code main.tf
```

Note that any changes you want to make should be done now. "resource" used in the privisioning of resources may not be appropriate if existing infrastructure exists. The service plan can be changed manually in azure API or in code. Save any relevant changes.

3. Initialize Terraform 

```
terraform init
```

4. Create Terraform plan

```
terraform plan
```

5. Finalize creation of Azure Web App. Before applying make sure that main.tf reflects final vision for web app.

```
terraform apply
```
