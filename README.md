## Azure Functions - AzureAd PowerShell Module
This is a basic sample of how to use the azuread PowerShell module within azure functions

### Consumption Plan Function timeout Increase

Update `host.json` setting
```json
{
    "functionTimeout": "00:10:00"
}
```

### Only install relevant Az module(s) as full Az module takes ages to initialise

Update `requirements.psd1`

```powershell
@{
    # For latest supported version, go to 'https://www.powershellgallery.com/packages/Az'. 
    # To use the Az module in your function app, please uncomment the line below.
    'Az.Accounts' = '2.5.4'
    'AzureAD' = '2.*'
}
```

### Assign Identity to your FunctionApp in the Portal
![System Assigned Identity](https://user-images.githubusercontent.com/24279339/140054297-68a22179-259e-4445-b5dc-1c37dc380ba1.png)

### Assign User Administrator Role to Identity in AzureAD
