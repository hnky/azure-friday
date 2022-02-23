!pip install azure-cognitiveservices-vision-computervision 
!pip install pillow

az group create -n AZConf_RG -l westeurope
az cognitiveservices account create \
    --name demo-ComputerVision \
    --resource-group AZConf_RG \
    --kind ComputerVision \
    --sku S1 \
    --location westeurope \
    --yes
az cognitiveservices account keys list --name demo-ComputerVision --resource-group AZConf_RG
az cognitiveservices account show --name demo-ComputerVision --resource-group AZConf_RG --query properties.endpoint

#custom vision
!pip install azure-cognitiveservices-vision-customvision

az group create --name <resource-group-name> --location <location>
az cognitiveservices account create --name <name> --kind CustomVision.Training --sku s1 --resource-group <resource-group-name> --location <location> --yes

az cognitiveservices account keys list --name <name> --resource-group <resource-group-name> 
az cognitiveservices account show --name <name> --resource-group <resource-group-name> -o json --query properties.endpoint

# speech services
!pip install azure-cognitiveservices-speech