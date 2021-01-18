#### login to azure 
``` az login ```
#### Create a resource group
``` az group create --name newresourcegroup1 --location "Central US" ```

#### create a temp variable
```template_file="/Users/swainsa1/development/azure/azure-arm/azuredeploy.json"```


#### create an empty template 
+ add the following content to the azuredeploy.json file
    ```json 
    {
        "$schema": "https://schema.management.azure.com/schemas/2019-04-01/deploymentTemplate.json#",
        "contentVersion": "1.0.0.0",
        "resources": []
    } 
    ```
+ Run deployment from command line
```
az deployment group create \
  --name blanktemplate \
  --resource-group myresourcegroup1 \
  --template-file $template_file
  ```


#### create an storage account 
+ Update and run the command
```json 
    {
        "$schema": "https://schema.management.azure.com/schemas/2019-04-01/deploymentTemplate.json#",
        "contentVersion": "1.0.0.0",
        "resources": [
        
            {
                "type": "Microsoft.Storage/storageAccounts",
                "apiVersion": "2019-04-01",
                "name": "storageaccountswainsa1",
                "location": "westus",
                "sku": {
                "name": "Standard_LRS"
            },
        "kind": "StorageV2",
        "properties": 
            {
                "supportsHttpsTrafficOnly": true
            }
        }
    ]
  }
  ```












