# terraform_bundle
This repo contains code that creates a terraform bundle

# What is this repo for.

This repo is intended to show how to build terraform bundle. Bundle that contains  both terraform version and provider plugins that are needed.

# Why use this repo .

You may need to test how to create a terraform bundle to use it when terraform is deployed in a network which for one reason or another does not have access to the plugins repository

# How to use this repo .

 * Install Terraform
 ```
 https://www.terraform.io/downloads.html
 ```
 
 * Clone this repository
 
 ```
 cd ~
 git clone https://github.com/yordanivh/terraform_bundle
 ```
 
 * Change directory
 
 ```
 cd terraform_bundle
 ```

 * You will have to install the go programing language
 
 ```
 brew install go
 ```
 
 * Add these two lines to your ~/.bash_profile file
 
 ```
 export PATH=$PATH:$(go env GOPATH)/bin
 export GOPATH=$(go env GOPATH)
 ```
 save the file and exit
 
 * Reload the bash_profile file
 
 ```
 source ~/.bash_profile
 ```
 * Clone the repository that contains the terraform-bundle tool
 
 ```
 cd ~
 git clone git@github.com:hashicorp/terraform.git
 ```
 
 * Chande directory 
 
 ```
 cd terraform 
 ```
 * Put in the following command which will install the terraform_bundle tool
 
 ```
 go install ./tools/terraform-bundle
 ```
 
 * Move back to the terraform_bundle folder
 
 ```
 cd ~/terraform_bundle
 ```
 The hcl file contains the terraform version and necessary plugins to bundle
 
 * Run the command to bundle plugins
 
 ```
 terraform-bundle package terraform-bundle.hcl
 ```
 Here is a sample output
 ```
terraform_bundle $ terraform-bundle package terraform-bundle.hcl
Fetching Terraform 0.12.0 core package...
Fetching 3rd party plugins in directory: ./plugins
- Resolving "aws" provider (~> 2.0)...
- Checking for provider plugin on https://releases.hashicorp.com...
- Downloading plugin for provider "aws" (hashicorp/aws) 2.42.0...
- Resolving "google" provider (~> 2.0)...
- Checking for provider plugin on https://releases.hashicorp.com...
- Downloading plugin for provider "google" (hashicorp/google) 2.20.1...
Creating terraform_0.12.0-bundle2019121711_darwin_amd64.zip ...
All done!
```
* After all this you should have a zip file with all the plugins and terraform installation

```
-rwxr-xr-x   1 yhalachev  staff  67449356 Dec 17 13:33 terraform_0.12.0-bundle2019121711_darwin_amd64.zip
```

 
 
