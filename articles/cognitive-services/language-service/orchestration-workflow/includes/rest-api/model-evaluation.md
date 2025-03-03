---
services: cognitive-services
author: aahill
manager: nitinme
ms.service: cognitive-services
ms.subservice: language-service
ms.topic: include
ms.date: 05/20/2022
ms.author: aahi
---

Create a **GET** request using the following URL, headers, and JSON body to get trained model evaluation summary.


### Request URL

```rest
{ENDPOINT}/language/analyze-conversations/projects/{projectName}/models/{trainedModelLabel}/evaluation/summary-result?api-version={API-VERSION}
```

|Placeholder  |Value  | Example |
|---------|---------|---------|
|`{ENDPOINT}`     | The endpoint for authenticating your API request.   | `https://<your-custom-subdomain>.cognitiveservices.azure.com` |
|`{PROJECT-NAME}`     | The name for your project. This value is case-sensitive.   | `myProject` |
|`{trainedModelLabel}`     | The name for your trained model. This value is case-sensitive.   | `Model1` |
|`{API-VERSION}`     | The version of the API you are calling. The value referenced here is for the latest released [model version](../../../concepts/model-lifecycle.md#choose-the-model-version-used-on-your-data). | `2022-03-01-preview` |


### Headers

Use the following header to authenticate your request. 

|Key|Value|
|--|--|
|`Ocp-Apim-Subscription-Key`| The key to your resource. Used for authenticating your API requests.|
|`Content-Type` | application/json |

### Response Body

Once you send the request, you will get the following response.

```json
{
  "entitiesEvaluation": {
    "confusionMatrix": {
      "additionalProp1": {
        "additionalProp1": {
          "normalizedValue": 0,
          "rawValue": 0
        },
        "additionalProp2": {
          "normalizedValue": 0,
          "rawValue": 0
        },
        "additionalProp3": {
          "normalizedValue": 0,
          "rawValue": 0
        }
      },
      "additionalProp2": {
        "additionalProp1": {
          "normalizedValue": 0,
          "rawValue": 0
        },
        "additionalProp2": {
          "normalizedValue": 0,
          "rawValue": 0
        },
        "additionalProp3": {
          "normalizedValue": 0,
          "rawValue": 0
        }
      },
      "additionalProp3": {
        "additionalProp1": {
          "normalizedValue": 0,
          "rawValue": 0
        },
        "additionalProp2": {
          "normalizedValue": 0,
          "rawValue": 0
        },
        "additionalProp3": {
          "normalizedValue": 0,
          "rawValue": 0
        }
      }
    },
    "entities": {
      "additionalProp1": {
        "f1": 0,
        "precision": 0,
        "recall": 0,
        "truePositivesCount": 0,
        "trueNegativesCount": 0,
        "falsePositivesCount": 0,
        "falseNegativesCount": 0
      },
      "additionalProp2": {
        "f1": 0,
        "precision": 0,
        "recall": 0,
        "truePositivesCount": 0,
        "trueNegativesCount": 0,
        "falsePositivesCount": 0,
        "falseNegativesCount": 0
      },
      "additionalProp3": {
        "f1": 0,
        "precision": 0,
        "recall": 0,
        "truePositivesCount": 0,
        "trueNegativesCount": 0,
        "falsePositivesCount": 0,
        "falseNegativesCount": 0
      }
    },
    "microF1": 0,
    "microPrecision": 0,
    "microRecall": 0,
    "macroF1": 0,
    "macroPrecision": 0,
    "macroRecall": 0
  },
  "intentsEvaluation": {
    "confusionMatrix": {
      "additionalProp1": {
        "additionalProp1": {
          "normalizedValue": 0,
          "rawValue": 0
        },
        "additionalProp2": {
          "normalizedValue": 0,
          "rawValue": 0
        },
        "additionalProp3": {
          "normalizedValue": 0,
          "rawValue": 0
        }
      },
      "additionalProp2": {
        "additionalProp1": {
          "normalizedValue": 0,
          "rawValue": 0
        },
        "additionalProp2": {
          "normalizedValue": 0,
          "rawValue": 0
        },
        "additionalProp3": {
          "normalizedValue": 0,
          "rawValue": 0
        }
      },
      "additionalProp3": {
        "additionalProp1": {
          "normalizedValue": 0,
          "rawValue": 0
        },
        "additionalProp2": {
          "normalizedValue": 0,
          "rawValue": 0
        },
        "additionalProp3": {
          "normalizedValue": 0,
          "rawValue": 0
        }
      }
    },
    "intents": {
      "additionalProp1": {
        "f1": 0,
        "precision": 0,
        "recall": 0,
        "truePositivesCount": 0,
        "trueNegativesCount": 0,
        "falsePositivesCount": 0,
        "falseNegativesCount": 0
      },
      "additionalProp2": {
        "f1": 0,
        "precision": 0,
        "recall": 0,
        "truePositivesCount": 0,
        "trueNegativesCount": 0,
        "falsePositivesCount": 0,
        "falseNegativesCount": 0
      },
      "additionalProp3": {
        "f1": 0,
        "precision": 0,
        "recall": 0,
        "truePositivesCount": 0,
        "trueNegativesCount": 0,
        "falsePositivesCount": 0,
        "falseNegativesCount": 0
      }
    },
    "microF1": 0,
    "microPrecision": 0,
    "microRecall": 0,
    "macroF1": 0,
    "macroPrecision": 0,
    "macroRecall": 0
  },
  "evaluationOptions": {
    "kind": "percentage",
    "trainingSplitPercentage": 0,
    "testingSplitPercentage": 0
  }
}

```
