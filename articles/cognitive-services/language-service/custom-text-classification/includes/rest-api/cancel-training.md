---
author: aahill
manager: nitinme
ms.service: cognitive-services
ms.subservice: language-service
ms.custom: event-tier1-build-2022
ms.topic: include
ms.date: 05/05/2022
ms.author: aahi
---


Create a **POST** request using the following URL, headers, and JSON body to cancel a training job. 

### Request URL

Use the following URL when creating your API request. Replace the placeholder values below with your own values. 

```rest
{ENDPOINT}/language/analyze-text/projects/{PROJECT-NAME}/train/jobs/{JOB-ID}/:cancel?api-version={API-VERSION}
```

|Placeholder  |Value  | Example |
|---------|---------|---------|
|`{ENDPOINT}`     | The endpoint for authenticating your API request.   | `https://<your-custom-subdomain>.cognitiveservices.azure.com` |
|`{PROJECT-NAME}`     | The name for your project. This value is case-sensitive.   | `EmailApp` |
|`{JOB-ID}          | This is the training job ID|                                  |`XXXXX-XXXXX-XXXX-XX|
|`{API-VERSION}`     | The version of the API you are calling. The value referenced here is for the latest version released. Learn more about other available [API versions](../../../concepts/model-lifecycle.md#choose-the-model-version-used-on-your-data)  | `2022-03-01-preview` |

### Headers

Use the following header to authenticate your request. 

|Key|Value|
|--|--|
|`Ocp-Apim-Subscription-Key`| The key to your resource. Used for authenticating your API requests.|
 
Once you send your API request, you will receive a 204 response indicating success, which means your training job has been canceled.
