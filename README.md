# Terraform-code
#Terraform code for rsource group Block/ storage account block/ Module Block


terraform {
  required_providers {
    azurerm = {
      source = "hashicorp/azurerm"
      version = "4.26.0"
    }
  }
  backend "azurerm" {
    resource_group_name  = "rgName1"
    storage_account_name = "Namestorage1989"
    container_name       = "tfstate"
    key                 = "Name.terraform.tfstate"
    
  }
}

provider "azurerm" {
  features {}
  subscription_id = "xxxx-xxxx-xxxxxx"
  
}

module "rgsan2" {
    source = "C:\\Devopsengg\\Name\\resource_group"

  
}

module "sanstorage" {

  depends_on = [ module.rgsan2 ]  
    source = "C:\\Devopsengg\\Name\\Storage_account"
  
}


