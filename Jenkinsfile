pipeline {
  agent any
  stages {
    stage('Create Storage Account') {
      steps {
        script {
          def storageAccountName = "PritomJenkinsAzureCLI" // Replace with your desired Storage Account name
          def resourceGroup = "pritomjenkins" // Replace with your desired resource group name
          def location = "eastus" // Replace with your desired location
          def sku = "Standard_LRS" // Replace with your desired Storage Account SKU

          // Log in to Azure CLI
          sh 'az login --service-principal --username "8e460660-9e89-4352-8344-980cf05df3a9" --password "tEL8Q~GEQTnVjWiKV8DXZ4An3QzpcvOOOXN5XaxK" --tenant "1cc10bb8-8d8f-4f8d-85c7-cc68e771b9c7"'

          // Create a Storage Account
          sh "az storage account create --name ${storageAccountName} --resource-group ${resourceGroup} --location ${location} --sku ${sku} --kind StorageV2 --access-tier Hot"
        }
      }
    }
  }
}
