---
title: "Face Python client library quickstart"
description: Use the Face client library for Python to detect faces and identify faces (facial recognition search).
#services: cognitive-services
author: PatrickFarley
manager: nitinme
ms.service: azure-ai-vision
ms.subservice: azure-ai-face
ms.custom:
  - ignite-2023
ms.topic: include
ms.date: 05/03/2022
ms.author: pafarley
---

Get started with facial recognition using the Face client library for Python. Follow these steps to install the package and try out the example code for basic tasks. The Face service provides you with access to advanced algorithms for detecting and recognizing human faces in images. Follow these steps to install the package and try out the example code for basic face identification using remote images.

[Reference documentation](/python/api/azure-ai-vision-face/azure.ai.vision.face) | [Library source code](https://github.com/Azure/azure-sdk-for-python/tree/main/sdk/face/azure-ai-vision-face/azure/ai/vision/face) | [Package (PiPy)](https://pypi.org/project/azure-ai-vision-face/) | [Samples](https://github.com/Azure/azure-sdk-for-python/tree/main/sdk/face/azure-ai-vision-face/samples)

## Prerequisites

* Azure subscription - [Create one for free](https://azure.microsoft.com/free/cognitive-services/)
* [Python 3.8+](https://www.python.org/)
  * Your Python installation should include [pip](https://pip.pypa.io/en/stable/). You can check if you have pip installed by running `pip --version` on the command line. Get pip by installing the latest version of Python.
* [!INCLUDE [contributor-requirement](../../../includes/quickstarts/contributor-requirement.md)]
* Once you have your Azure subscription, <a href="https://portal.azure.com/#create/Microsoft.CognitiveServicesFace"  title="Create a Face resource"  target="_blank">create a Face resource</a> in the Azure portal to get your key and endpoint. After it deploys, select **Go to resource**.
    * You'll need the key and endpoint from the resource you create to connect your application to the Face API.
    * You can use the free pricing tier (`F0`) to try the service, and upgrade later to a paid tier for production.



[!INCLUDE [create environment variables](../environment-variables.md)]

## Identify and verify faces

1. Install the client library

    After installing Python, you can install the client library with:

    ```console
    python -m pip install azure-ai-vision-face
    ```

1. Create a new Python application

    Create a new Python script&mdash;*quickstart-file.py*, for example. Then open it in your preferred editor or IDE and paste in the following code.

    > [!NOTE]
    > If you haven't received access to the Face service using the [intake form](https://aka.ms/facerecognition), some of these functions won't work.

    [!code-python[](~/cognitive-services-quickstart-code/python/Face/FaceQuickstart-single.py?name=snippet_single)]


1. Run your face recognition app from the application directory with the `python` command.

    ```console
    python quickstart-file.py
    ```

    > [!TIP]
    > The Face API runs on a set of pre-built models that are static by nature (the model's performance will not regress or improve as the service is run). The results that the model produces might change if Microsoft updates the model's backend without migrating to an entirely new model version. To take advantage of a newer version of a model, you can retrain your **PersonGroup**, specifying the newer model as a parameter with the same enrollment images.



## Output

```console
Person group: dbd92bf0-8b74-43fc-a27a-b127c1bb1b66
face 1d09b50e-0fb6-430c-a47c-9bb235761c17 added to person ea92a5d5-5250-44db-88fb-3b32e1a1ecaf
face 74e1807a-6c86-4c74-b497-a3bcdda8c631 added to person ea92a5d5-5250-44db-88fb-3b32e1a1ecaf
face 512cc8ff-e18a-4702-9413-3c83af9a0915 added to person f03219b3-c2dc-4ad6-b00b-bd71792686ac
face 899bbe8e-2d03-4941-8221-d087911df21b added to person f03219b3-c2dc-4ad6-b00b-bd71792686ac
face dfc0d142-36b0-4d90-982b-b51570ead5a8 added to person 8697d263-be7b-4d78-ba40-b55305dbbeb6
face 29939a66-9da2-46f2-b572-abbe4e0d754a added to person 8697d263-be7b-4d78-ba40-b55305dbbeb6
Train the person group dbd92bf0-8b74-43fc-a27a-b127c1bb1b66
The person group dbd92bf0-8b74-43fc-a27a-b127c1bb1b66 is trained successfully.
Pausing for 10 seconds to avoid triggering rate limit on free account...
Identifying faces in image
Person is identified for face ID 5779a986-238c-499d-b22a-d2a7cec92e88 in image, with a confidence of 0.96725.
verification result: True. confidence: 0.96725
Person is identified for face ID a28a4997-600e-4595-be39-d7a7d0f8afc8 in image, with a confidence of 0.96921.
verification result: True. confidence: 0.96921
No person identified for face ID 02a56d35-f3a4-43eb-a295-f23a1b772de9 in image.
Person is identified for face ID 5de2019a-c4d3-4021-b8d0-9a3b86adceb7 in image, with a confidence of 0.92886.
verification result: True. confidence: 0.92886

The person group dbd92bf0-8b74-43fc-a27a-b127c1bb1b66 is deleted.

End of quickstart.
```



## Clean up resources

If you want to clean up and remove an Azure AI services subscription, you can delete the resource or resource group. Deleting the resource group also deletes any other resources associated with it.

* [Portal](../../../multi-service-resource.md?pivots=azportal#clean-up-resources)
* [Azure CLI](../../../multi-service-resource.md?pivots=azcli#clean-up-resources)

To delete the **PersonGroup** you created in this quickstart, run the following code in your script:

[!code-python[](~/cognitive-services-quickstart-code/python/Face/FaceQuickstart.py?name=snippet_deletegroup)]

## Next steps

In this quickstart, you learned how to use the Face client library for Python to do basic face identification. Next, learn about the different face detection models and how to specify the right model for your use case.

> [!div class="nextstepaction"]
> [Specify a face detection model version](../../how-to/specify-detection-model.md)

* [What is the Face service?](../../overview-identity.md)
* More extensive sample code can be found on [GitHub](https://github.com/Azure-Samples/cognitive-services-quickstart-code/blob/master/python/Face/FaceQuickstart.py).
