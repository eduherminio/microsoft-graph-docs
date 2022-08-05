---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
graphClient := msgraphsdk.NewGraphServiceClient(requestAdapter)

headers := map[string]string{
	"User-Agent": "ContosoLOBApp/1.0",
}
configuration := &graphconfig.EvaluateRemovalRequestBuilderPostRequestConfiguration{
	Headers: headers,
}
requestBody := graphmodels.NewEvaluateRemovalPostRequestBody()
contentInfo := graphmodels.NewContentInfo()
"@odata.type" := "#microsoft.graph.security.contentInfo"
contentInfo.Set"@odata.type"(&"@odata.type") 
identifier := null
contentInfo.SetIdentifier(&identifier) 
state := graphmodels.REST_CONTENTSTATE 
contentInfo.SetState(&state) 


keyValuePair := graphmodels.NewKeyValuePair()
name := "MSIP_Label_836ff34f-b604-4a62-a68c-d6be4205d569_Enabled"
keyValuePair.SetName(&name) 
value := "True"
keyValuePair.SetValue(&value) 
keyValuePair1 := graphmodels.NewKeyValuePair()
name := "MSIP_Label_836ff34f-b604-4a62-a68c-d6be4205d569_Method"
keyValuePair1.SetName(&name) 
value := "Standard"
keyValuePair1.SetValue(&value) 
keyValuePair2 := graphmodels.NewKeyValuePair()
name := "MSIP_Label_836ff34f-b604-4a62-a68c-d6be4205d569_SetDate"
keyValuePair2.SetName(&name) 
value := "1/1/0001 12:00:00 AM"
keyValuePair2.SetValue(&value) 
keyValuePair3 := graphmodels.NewKeyValuePair()
"@odata.type" := "#microsoft.graph.security.keyValuePair"
keyValuePair3.Set"@odata.type"(&"@odata.type") 
name := "MSIP_Label_836ff34f-b604-4a62-a68c-d6be4205d569_SiteId"
keyValuePair3.SetName(&name) 
value := "cfa4cf1d-a337-4481-aa99-19d8f3d63f7c"
keyValuePair3.SetValue(&value) 
keyValuePair4 := graphmodels.NewKeyValuePair()
"@odata.type" := "#microsoft.graph.security.keyValuePair"
keyValuePair4.Set"@odata.type"(&"@odata.type") 
name := "MSIP_Label_836ff34f-b604-4a62-a68c-d6be4205d569_Name"
keyValuePair4.SetName(&name) 
value := "LabelScopedToBob_Tests"
keyValuePair4.SetValue(&value) 
keyValuePair5 := graphmodels.NewKeyValuePair()
"@odata.type" := "#microsoft.graph.security.keyValuePair"
keyValuePair5.Set"@odata.type"(&"@odata.type") 
name := "MSIP_Label_836ff34f-b604-4a62-a68c-d6be4205d569_ContentBits"
keyValuePair5.SetName(&name) 
value := "0"
keyValuePair5.SetValue(&value) 
keyValuePair6 := graphmodels.NewKeyValuePair()
"@odata.type" := "#microsoft.graph.security.keyValuePair"
keyValuePair6.Set"@odata.type"(&"@odata.type") 
name := "MSIP_Label_836ff34f-b604-4a62-a68c-d6be4205d569_ActionId"
keyValuePair6.SetName(&name) 
value := "00000000-0000-0000-0000-000000000000"
keyValuePair6.SetValue(&value) 

metadata := []graphmodels.KeyValuePairable {
	keyValuePair,
	keyValuePair1,
	keyValuePair2,
	keyValuePair3,
	keyValuePair4,
	keyValuePair5,
	keyValuePair6,

}
contentInfo.SetMetadata(metadata)
requestBody.SetContentInfo(contentInfo)
downgradeJustification := graphmodels.NewDowngradeJustification()
justificationMessage := "The information has been declassified."
downgradeJustification.SetJustificationMessage(&justificationMessage) 
isDowngradeJustified := true
downgradeJustification.SetIsDowngradeJustified(&isDowngradeJustified) 
requestBody.SetDowngradeJustification(downgradeJustification)

result, err := graphClient.UsersById("user-id").Security().InformationProtection().SensitivityLabels().EvaluateRemoval().PostWithRequestConfigurationAndResponseHandler(requestBody, configuration, nil)


```