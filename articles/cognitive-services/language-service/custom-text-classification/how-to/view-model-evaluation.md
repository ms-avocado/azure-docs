---
title: View a custom text classification model evaluation - Azure Cognitive Services
titleSuffix: Azure Cognitive Services
description: Learn how to view the evaluation scores for a custom text classification model
services: cognitive-services
author: aahill
manager: nitinme
ms.service: cognitive-services
ms.subservice: language-service
ms.topic: how-to
ms.date: 05/05/2022
ms.author: aahi
ms.custom: language-service-custom-classification, ignite-fall-2021, event-tier1-build-2022
---

# View your text classification model's evaluation and details

After your model has finished training, you can view the model performance and see the predicted classes for the documents in the test set. 

> [!NOTE]
> Using the **Automatically split the testing set from training data** option may result in different model evaluation result every time you [train a new model](train-model.md), as the test set is selected randomly from the data. To make sure that the evaluation is calculated on the same test set every time you train a model, make sure to use the **Use a manual split of training and testing data** option when starting a training job and define your **Test** documents when [tagging data](tag-data.md).

## Prerequisites

Before viewing model evaluation you need:

* [A custom text classification project](create-project.md) with a configured Azure blob storage account.
* Text data that has [been uploaded](design-schema.md#data-preparation) to your storage account.
* [Tagged data](tag-data.md)
* A successfully [trained model](train-model.md)

See the [project development lifecycle](../overview.md#project-development-lifecycle) for more information.

## Model details

### [Language studio](#tab/language-studio)

[!INCLUDE [View model details](../includes/language-studio/model-evaluation.md)]

### [REST APIs](#tab/rest-api)

### Single label classification
[!INCLUDE [Model evaluation](../includes/rest-api/model-evaluation-single-label.md)]

### Multi label classification 

[!INCLUDE [Model evaluation](../includes/rest-api/model-evaluation-multi-label.md)]

---

## Delete model

### [Language studio](#tab/language-studio)

[!INCLUDE [Delete model](../includes/language-studio/delete-model.md)]


### [REST APIs](#tab/rest-api)

[!INCLUDE [Delete model](../includes/rest-api/delete-model.md)]


---

## Next steps

As you review your how your model performs, learn about the [evaluation metrics](../concepts/evaluation-metrics.md) that are used. Once you know whether your model performance needs to improve, you can begin [improving the model](improve-model.md).
