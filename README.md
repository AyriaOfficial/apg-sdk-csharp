# com.ayriaplatform.apg - the C# library for the APG API

This is a APG (Ayria Payment Gateway) API SDK.

This C# SDK is automatically generated by the [OpenAPI Generator](https://openapi-generator.tech) project:

- API version: 1.0.1
- SDK version: 1.0.0
- Build package: org.openapitools.codegen.languages.CSharpClientCodegen

## Frameworks supported


- .NET 4.0 or later
- Windows Phone 7.1 (Mango)

## Dependencies


- [RestSharp](https://www.nuget.org/packages/RestSharp) - 105.1.0 or later
- [Json.NET](https://www.nuget.org/packages/Newtonsoft.Json/) - 7.0.0 or later
- [JsonSubTypes](https://www.nuget.org/packages/JsonSubTypes/) - 1.2.0 or later

The DLLs included in the package may not be the latest version. We recommend using [NuGet](https://docs.nuget.org/consume/installing-nuget) to obtain the latest version of the packages:

```
Install-Package RestSharp
Install-Package Newtonsoft.Json
Install-Package JsonSubTypes
```

NOTE: RestSharp versions greater than 105.1.0 have a bug which causes file uploads to fail. See [RestSharp#742](https://github.com/restsharp/RestSharp/issues/742)

## Installation

Run the following command to generate the DLL

- [Mac/Linux] `/bin/sh build.sh`
- [Windows] `build.bat`

Then include the DLL (under the `bin` folder) in the C# project, and use the namespaces:

```csharp
using com.ayriaplatform.apg.Api;
using com.ayriaplatform.apg.Client;
using com.ayriaplatform.apg.Model;

```


## Packaging

A `.nuspec` is included with the project. You can follow the Nuget quickstart to [create](https://docs.microsoft.com/en-us/nuget/quickstart/create-and-publish-a-package#create-the-package) and [publish](https://docs.microsoft.com/en-us/nuget/quickstart/create-and-publish-a-package#publish-the-package) packages.

This `.nuspec` uses placeholders from the `.csproj`, so build the `.csproj` directly:

```
nuget pack -Build -OutputDirectory out com.ayriaplatform.apg.csproj
```

Then, publish to a [local feed](https://docs.microsoft.com/en-us/nuget/hosting-packages/local-feeds) or [other host](https://docs.microsoft.com/en-us/nuget/hosting-packages/overview) and consume the new package via Nuget as usual.


## Getting Started

```csharp
using System.Collections.Generic;
using System.Diagnostics;
using com.ayriaplatform.apg.Api;
using com.ayriaplatform.apg.Client;
using com.ayriaplatform.apg.Model;

namespace Example
{
    public class Example
    {
        public static void Main()
        {

            Configuration.Default.BasePath = "https://api.ayria.club/apg/v1";
            // Configure API key authorization: APG-API-KEY
            Configuration.Default.ApiKey.Add("APG-API-KEY", "YOUR_API_KEY");
            // Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
            // Configuration.Default.ApiKeyPrefix.Add("APG-API-KEY", "Bearer");

            var apiInstance = new PaymentApi(Configuration.Default);
            var APG_WALLET_ID = APG_WALLET_ID_example;  // string | 
            var referenceCode = referenceCode_example;  // string | ReferenceCode of payment to return

            try
            {
                // Find payment with referenceCode
                AyriaPaymentV1DTO result = apiInstance.GetPaymentByReferenceCode(APG_WALLET_ID, referenceCode);
                Debug.WriteLine(result);
            }
            catch (ApiException e)
            {
                Debug.Print("Exception when calling PaymentApi.GetPaymentByReferenceCode: " + e.Message );
                Debug.Print("Status Code: "+ e.ErrorCode);
                Debug.Print(e.StackTrace);
            }

        }
    }
}
```

## Documentation for API Endpoints

All URIs are relative to *https://api.ayria.club/apg/v1*

Class | Method | HTTP request | Description
------------ | ------------- | ------------- | -------------
*PaymentApi* | [**GetPaymentByReferenceCode**](docs/PaymentApi.md#getpaymentbyreferencecode) | **GET** /get/{referenceCode} | Find payment with referenceCode
*PaymentApi* | [**GetPayments**](docs/PaymentApi.md#getpayments) | **GET** /list | List of payments between given dates
*PaymentApi* | [**PaymentCancel**](docs/PaymentApi.md#paymentcancel) | **POST** /cancel | Cancel a  payment
*PaymentApi* | [**PaymentCreate**](docs/PaymentApi.md#paymentcreate) | **POST** /create | Add a new payment


## Documentation for Models

 - [Model.AyriaPaymentV1CancelCommand](docs/AyriaPaymentV1CancelCommand.md)
 - [Model.AyriaPaymentV1Command](docs/AyriaPaymentV1Command.md)
 - [Model.AyriaPaymentV1DTO](docs/AyriaPaymentV1DTO.md)
 - [Model.AyriaPaymentV1KalaDTO](docs/AyriaPaymentV1KalaDTO.md)


## Documentation for Authorization


### APG-API-KEY

- **Type**: API key

- **API key parameter name**: APG-API-KEY
- **Location**: HTTP header

