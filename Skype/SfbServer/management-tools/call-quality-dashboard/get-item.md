---
title: Obtenir l’élément
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: e77bf649-d62a-4d94-80de-066ba47730cd
description: 'Résumé : Découvrez l’opération obtenir l’élément, qui fait partie de l’article de Service. L’article de Service fait partie de l’API de référentiel pour appeler le tableau de bord qualité. Tableau de bord qualité appel est un outil de Skype pour Business Server 2015.'
ms.openlocfilehash: 6e4ba82c804937025b72da2d443c2a828d92d98a
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="get-item"></a><span data-ttu-id="85c11-105">Obtenir l’élément</span><span class="sxs-lookup"><span data-stu-id="85c11-105">Get Item</span></span>
 
<span data-ttu-id="85c11-106">**Résumé :** Obtenir des informations sur l’opération obtenir l’élément, qui fait partie de l’article de Service.</span><span class="sxs-lookup"><span data-stu-id="85c11-106">**Summary:** Learn about the Get Item operation, which is part of the Item Service.</span></span> <span data-ttu-id="85c11-107">L’article de Service fait partie de l’API de référentiel pour appeler le tableau de bord qualité.</span><span class="sxs-lookup"><span data-stu-id="85c11-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="85c11-108">Tableau de bord qualité appel est un outil de Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="85c11-108">Call Quality Dashboard is a tool for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="85c11-109">L’opération obtenir l’élément fait partie de l’article Service dans l’API de référentiel pour appeler le tableau de bord qualité.</span><span class="sxs-lookup"><span data-stu-id="85c11-109">The Get Item operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-item"></a><span data-ttu-id="85c11-110">Obtenir l’élément</span><span class="sxs-lookup"><span data-stu-id="85c11-110">Get Item</span></span>

<span data-ttu-id="85c11-111">Obtenir élément renvoie un élément spécifique dans le référentiel.</span><span class="sxs-lookup"><span data-stu-id="85c11-111">Get Item returns a specific item in the repository.</span></span>
  
|<span data-ttu-id="85c11-112">**Méthode**</span><span class="sxs-lookup"><span data-stu-id="85c11-112">**Method**</span></span>|<span data-ttu-id="85c11-113">**URI de la demande**</span><span class="sxs-lookup"><span data-stu-id="85c11-113">**Request URI**</span></span>|<span data-ttu-id="85c11-114">**Version de HTTP**</span><span class="sxs-lookup"><span data-stu-id="85c11-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="85c11-115">Télécharger</span><span class="sxs-lookup"><span data-stu-id="85c11-115">GET</span></span>  <br/> |<span data-ttu-id="85c11-116">https://\<portal\>/QoERepositoryService/repository/article / {itemId}</span><span class="sxs-lookup"><span data-stu-id="85c11-116">https://\<portal\>/QoERepositoryService/repository/item/{itemId}</span></span>  <br/> |<span data-ttu-id="85c11-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="85c11-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="85c11-118">**Les paramètres URI** - None.</span><span class="sxs-lookup"><span data-stu-id="85c11-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="85c11-119">**En-têtes de requête** - aucun en-tête supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="85c11-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="85c11-120">**Corps de requête** - None.</span><span class="sxs-lookup"><span data-stu-id="85c11-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="85c11-121">**Réponse** : la réponse contient un code d’état HTTP et d’un ensemble d’en-têtes de réponse.</span><span class="sxs-lookup"><span data-stu-id="85c11-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="85c11-122">**Code d’état** - une opération réussie retourne un code d’état 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="85c11-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span> <span data-ttu-id="85c11-123">Si un ID de l’élément spécifié n’est pas trouvé, il renvoie le code d’état 404 (introuvable).</span><span class="sxs-lookup"><span data-stu-id="85c11-123">If a specified item ID is not found, it returns status code 404 (Not Found).</span></span>
  
 <span data-ttu-id="85c11-124">**En-têtes de réponse** - aucun en-tête supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="85c11-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="85c11-125">**Corps de la réponse** - Voici une charge utile d’exemple réponse au format JSON.</span><span class="sxs-lookup"><span data-stu-id="85c11-125">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
```
{
"itemId": 1652,
"userId": 0,
"content": "{\"Title\":\"All Audio Streams\",...}",
"type": "application/json",
"subItemIds": [1653, 1710]
}

```

 <span data-ttu-id="85c11-126">*itemId* - ID de l’élément.</span><span class="sxs-lookup"><span data-stu-id="85c11-126">*itemId*  - ID of the item.</span></span>
  
 <span data-ttu-id="85c11-127">*pseudo* - ID de l’utilisateur propriétaire de cet élément.</span><span class="sxs-lookup"><span data-stu-id="85c11-127">*userId*  - ID of the user who owns this item.</span></span>
  
 <span data-ttu-id="85c11-128">*contenu* - le contenu spécifique à l’application.</span><span class="sxs-lookup"><span data-stu-id="85c11-128">*content*  - The application-specific content.</span></span>
  
 <span data-ttu-id="85c11-129">*type* - le type de contenu.</span><span class="sxs-lookup"><span data-stu-id="85c11-129">*type*  - The type of the content.</span></span> <span data-ttu-id="85c11-130">Ce champ est défini par les applications.</span><span class="sxs-lookup"><span data-stu-id="85c11-130">This field is set by the applications.</span></span>
  
 <span data-ttu-id="85c11-131">*subItemIds* - l’ID des sous-éléments, le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="85c11-131">*subItemIds*  - The IDs of sub-Items, if any.</span></span> <span data-ttu-id="85c11-132">Il s’agit d’un court-circuit d’opération obtenir des sous-éléments pour enregistrer un appel.</span><span class="sxs-lookup"><span data-stu-id="85c11-132">This is a short-circuit of Get Sub-Items operation to save a call.</span></span> <span data-ttu-id="85c11-133">Les applications peuvent également obtenir les mêmes informations à l’aide d’opération d’obtenir les éléments de sous-menu.</span><span class="sxs-lookup"><span data-stu-id="85c11-133">Applications can alternatively obtain the same information using Get Sub-Items operation.</span></span>
  

