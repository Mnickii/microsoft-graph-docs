---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
graphClient := msgraphsdk.NewGraphServiceClient(requestAdapter)

requestBody := msgraphsdk.New()
requestBody.SetAdditionalData(map[string]interface{}{
	"@odata.id": "https://graph.microsoft.com/beta/identityProviders/{id}",
}
options := &msgraphsdk.IdentityProviderRequestBuilderPostOptions{
	Body: requestBody,
}
b2cIdentityUserFlowId := "b2cIdentityUserFlow-id"
identityProviderId := "identityProvider-id"
graphClient.Identity().B2cUserFlowsById(&b2cIdentityUserFlowId).IdentityProvidersById(&identityProviderId).Post(options)


```