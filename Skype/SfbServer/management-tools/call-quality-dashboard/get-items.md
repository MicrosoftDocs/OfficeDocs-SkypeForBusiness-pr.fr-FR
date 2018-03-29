---
title: Obtenir des éléments
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 9e189a48-4944-4f93-88d7-9d56b56770a6
description: 'Résumé : Découvrez l’opération obtenir les éléments, qui fait partie de l’article de Service. L’article de Service fait partie de l’API de référentiel pour appeler le tableau de bord qualité. Tableau de bord qualité appel est un outil de Skype pour Business Server 2015.'
ms.openlocfilehash: 526d578d65ded98a6cd1a5cfc09a6749319683c3
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="get-items"></a><span data-ttu-id="1acbf-105">Obtenir des éléments</span><span class="sxs-lookup"><span data-stu-id="1acbf-105">Get Items</span></span>
 
<span data-ttu-id="1acbf-106">**Résumé :** Obtenir des informations sur l’opération obtenir les éléments, qui fait partie de l’article de Service.</span><span class="sxs-lookup"><span data-stu-id="1acbf-106">**Summary:** Learn about the Get Items operation, which is part of the Item Service.</span></span> <span data-ttu-id="1acbf-107">L’article de Service fait partie de l’API de référentiel pour appeler le tableau de bord qualité.</span><span class="sxs-lookup"><span data-stu-id="1acbf-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="1acbf-108">Tableau de bord qualité appel est un outil de Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="1acbf-108">Call Quality Dashboard is a tool for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="1acbf-109">L’opération obtenir les éléments fait partie de l’article Service dans l’API de référentiel pour appeler le tableau de bord qualité.</span><span class="sxs-lookup"><span data-stu-id="1acbf-109">The Get Items operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-items"></a><span data-ttu-id="1acbf-110">Obtenir des éléments</span><span class="sxs-lookup"><span data-stu-id="1acbf-110">Get Items</span></span>

<span data-ttu-id="1acbf-111">Obtenir les éléments retourne tous les éléments dans le référentiel.</span><span class="sxs-lookup"><span data-stu-id="1acbf-111">Get Items returns all Items in the repository.</span></span>
  
|<span data-ttu-id="1acbf-112">**Méthode**</span><span class="sxs-lookup"><span data-stu-id="1acbf-112">**Method**</span></span>|<span data-ttu-id="1acbf-113">**URI de la demande**</span><span class="sxs-lookup"><span data-stu-id="1acbf-113">**Request URI**</span></span>|<span data-ttu-id="1acbf-114">**Version de HTTP**</span><span class="sxs-lookup"><span data-stu-id="1acbf-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1acbf-115">Télécharger</span><span class="sxs-lookup"><span data-stu-id="1acbf-115">GET</span></span>  <br/> |<span data-ttu-id="1acbf-116">https://\<portal\>/QoERepositoryService/repository/item</span><span class="sxs-lookup"><span data-stu-id="1acbf-116">https://\<portal\>/QoERepositoryService/repository/item</span></span>  <br/> |<span data-ttu-id="1acbf-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="1acbf-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="1acbf-118">**Les paramètres URI** - None.</span><span class="sxs-lookup"><span data-stu-id="1acbf-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="1acbf-119">**En-têtes de requête** - aucun en-tête supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="1acbf-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="1acbf-120">**Corps de requête** - None.</span><span class="sxs-lookup"><span data-stu-id="1acbf-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="1acbf-121">**Réponse** : la réponse contient un code d’état HTTP et d’un ensemble d’en-têtes de réponse.</span><span class="sxs-lookup"><span data-stu-id="1acbf-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="1acbf-122">**Code d’état** - une opération réussie retourne un code d’état 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="1acbf-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="1acbf-123">**En-têtes de réponse** - aucun en-tête supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="1acbf-123">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="1acbf-124">**Corps de la réponse** - Voici une charge utile d’exemple réponse au format JSON.</span><span class="sxs-lookup"><span data-stu-id="1acbf-124">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1acbf-125">Un tableau d’objets d’élément est retourné.</span><span class="sxs-lookup"><span data-stu-id="1acbf-125">An array of Item objects is returned.</span></span> <span data-ttu-id="1acbf-126">Pour plus d’informations sur l’objet de l’élément, consultez obtenir l’élément.</span><span class="sxs-lookup"><span data-stu-id="1acbf-126">For details about Item object, see Get Item.</span></span> 
  
```
[{
"itemId": 1652,
"userId": 0,
"type": "application/json"
},
{
"itemId": 1653,
"userId": 0,
"type": "application/json"
},
{
"itemId": 1654,
"userId": 0,
"type": "application/json"
}]

```


