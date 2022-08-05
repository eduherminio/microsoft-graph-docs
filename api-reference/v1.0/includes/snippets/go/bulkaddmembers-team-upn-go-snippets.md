---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
graphClient := msgraphsdk.NewGraphServiceClient(requestAdapter)

requestBody := graphmodels.NewAddPostRequestBody()


conversationMember := graphmodels.NewConversationMember()
"@odata.type" := "microsoft.graph.aadUserConversationMember"
conversationMember.Set"@odata.type"(&"@odata.type") 
roles := []string {

}
conversationMember.SetRoles(roles)
additionalData := map[string]interface{}{
	"user@odata.bind" : "https://graph.microsoft.com/v1.0/users('jacob@contoso.com')", 
}
conversationMember.SetAdditionalData(additionalData)
conversationMember1 := graphmodels.NewConversationMember()
"@odata.type" := "microsoft.graph.aadUserConversationMember"
conversationMember1.Set"@odata.type"(&"@odata.type") 
roles := []string {
	"owner",

}
conversationMember1.SetRoles(roles)
additionalData := map[string]interface{}{
	"user@odata.bind" : "https://graph.microsoft.com/v1.0/users('alex@contoso.com')", 
}
conversationMember1.SetAdditionalData(additionalData)

values := []graphmodels.Objectable {
	conversationMember,
	conversationMember1,

}
requestBody.SetValues(values)

result, err := graphClient.TeamsById("team-id").Members().Add().Post(requestBody)


```