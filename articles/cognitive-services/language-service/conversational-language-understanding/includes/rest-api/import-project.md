---
services: cognitive-services
author: aahill
manager: nitinme
ms.service: cognitive-services
ms.subservice: language-service
ms.topic: include
ms.date: 01/27/2022
ms.author: aahi
ms.custom: ignite-fall-2021
---

Submit a **POST** request using the following URL, headers, and JSON body to import your project.

### Request URL

Use the following URL when creating your API request. Replace the placeholder values below with your own values. 

```rest
{ENDPOINT}/language/authoring/analyze-conversations/projects/{PROJECT-NAME}/:import?api-version={API-VERSION}
```

|Placeholder  |Value  | Example |
|---------|---------|---------|
|`{ENDPOINT}`     | The endpoint for authenticating your API request.   | `https://<your-custom-subdomain>.cognitiveservices.azure.com` |
|`{PROJECT-NAME}`     | The name for your project. This value is case-sensitive.   | `myProject` |
|`{API-VERSION}`     | The version of the API you're calling. The value referenced here is for the latest released [model version](../../../concepts/model-lifecycle.md#choose-the-model-version-used-on-your-data).  | `2022-03-01-preview` |

### Headers

Use the following header to authenticate your request. 

|Key|Value|
|--|--|
|`Ocp-Apim-Subscription-Key`| The key to your resource. Used for authenticating your API requests.|

### Body

Use the following sample JSON as your body.

```json
{
  "api-version":"{API-VERSION}" ,
    "stringIndexType": "Utf16CodeUnit",
    "metadata": {
        "projectKind": "conversation",
        "settings": {
            "confidenceThreshold": 0.7
        },
        "projectName": "{PROJECT-NAME}",
        "multilingual": true,
        "description": "Trying out CLU",
        "language": "{LANGUAGE-CODE}"
    },
  "assets": {
    "intents": [
      {
        "category": "Read"
      },
      {
        "category": "Delete"
      }
    ],
    "entities": [
      {
        "category": "Sender"
      }
    ],
    "utterances": [
      {
        "text": "Open Blake's email",
        "language": "{LANGUAGE-CODE}",
        "dataset": "{DATASET}",
        "intent": "Read",
        "entities": [
          {
            "category": "Sender",
            "offset": 5,
            "length": 5
          }
        ]
      },
      {
        "text": "Delete last email",
        "language": "{LANGUAGE-CODE}",
        "dataset": "{DATASET}",
        "intent": "Attach",
        "entities": []
      }
    ]
  }
}

```

|Key  |Placeholder  |Value  | Example |
|---------|---------|----------|--|
| api-version | `{API-VERSION}` | The version of the API you're calling. The version used here must be the same API model version in the URL. See the [model version](../../../concepts/model-lifecycle.md#choose-the-model-version-used-on-your-data) article to learn more.  | `2022-03-01-preview` |
| `projectName` | `{PROJECT-NAME}` | The name of your project. This value is case-sensitive. | `EmailApp` |
| `language` | `{LANGUAGE-CODE}` |  A string specifying the language code for the utterances used in your project. If your project is a multilingual project, choose the [language code](../../language-support.md) of the majority of the utterances. |`en-us`|
| `multilingual` | `true`| A boolean value that enables you to have documents in multiple languages in your dataset. When your model is deployed, you can query the model in any [supported language](../../language-support.md#multi-lingual-option). This includes languages that aren't included in your training documents.  | `true`|
| `dataset` | `{DATASET}` |  See [how to train a model](../../how-to/tag-utterances.md) for information on splitting your data between a testing and training set. Possible values for this field are `Train` and `Test`.      |`Train`|

