---
title: Obtenir un élément
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: e77bf649-d62a-4d94-80de-066ba47730cd
description: 'Résumé : Découvrez l’opération obtenir un élément, qui fait partie du Service de l’élément. Le Service de l’élément fait partie de l’API de référentiel pour appeler le tableau de bord qualité. Tableau de bord de qualité des appels est un outil de Skype pour Business Server.'
ms.openlocfilehash: cd72eb583ff0e0813e4197031b119200ecf4b2fc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33926078"
---
# <a name="get-item"></a><span data-ttu-id="db131-105">Obtenir un élément</span><span class="sxs-lookup"><span data-stu-id="db131-105">Get Item</span></span>
 
<span data-ttu-id="db131-106">**Résumé :** Obtenir des informations sur l’opération obtenir un élément, qui fait partie du Service de l’élément.</span><span class="sxs-lookup"><span data-stu-id="db131-106">**Summary:** Learn about the Get Item operation, which is part of the Item Service.</span></span> <span data-ttu-id="db131-107">Le Service de l’élément fait partie de l’API de référentiel pour appeler le tableau de bord qualité.</span><span class="sxs-lookup"><span data-stu-id="db131-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="db131-108">Tableau de bord de qualité des appels est un outil de Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="db131-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="db131-109">L’opération obtenir un élément fait partie du Service d’élément dans l’API de référentiel pour appeler le tableau de bord qualité.</span><span class="sxs-lookup"><span data-stu-id="db131-109">The Get Item operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-item"></a><span data-ttu-id="db131-110">Obtenir un élément</span><span class="sxs-lookup"><span data-stu-id="db131-110">Get Item</span></span>

<span data-ttu-id="db131-111">Obtenir élément renvoie un élément spécifique dans le référentiel.</span><span class="sxs-lookup"><span data-stu-id="db131-111">Get Item returns a specific item in the repository.</span></span>
  
|<span data-ttu-id="db131-112">**Méthode**</span><span class="sxs-lookup"><span data-stu-id="db131-112">**Method**</span></span>|<span data-ttu-id="db131-113">**URI de la demande**</span><span class="sxs-lookup"><span data-stu-id="db131-113">**Request URI**</span></span>|<span data-ttu-id="db131-114">**Version HTTP**</span><span class="sxs-lookup"><span data-stu-id="db131-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="db131-115">Avoir</span><span class="sxs-lookup"><span data-stu-id="db131-115">GET</span></span>  <br/> |<span data-ttu-id="db131-116">https://\<portal\>/QoERepositoryService/référentiel/élément / {itemId}</span><span class="sxs-lookup"><span data-stu-id="db131-116">https://\<portal\>/QoERepositoryService/repository/item/{itemId}</span></span>  <br/> |<span data-ttu-id="db131-117">HTTP/1.1.</span><span class="sxs-lookup"><span data-stu-id="db131-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="db131-118">**Paramètres d’URI** - None.</span><span class="sxs-lookup"><span data-stu-id="db131-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="db131-119">**En-têtes de demande** - aucun en-tête supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="db131-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="db131-120">**Corps de requête** - None.</span><span class="sxs-lookup"><span data-stu-id="db131-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="db131-121">**Réponse** - la réponse inclut un code d’état HTTP et un ensemble d’en-têtes de réponse.</span><span class="sxs-lookup"><span data-stu-id="db131-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="db131-122">**Code d’état** - une opération réussie retourne un code d’état 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="db131-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span> <span data-ttu-id="db131-123">Si un ID de l’élément spécifié est introuvable, elle renvoie le code d’état 404 (introuvable).</span><span class="sxs-lookup"><span data-stu-id="db131-123">If a specified item ID is not found, it returns status code 404 (Not Found).</span></span>
  
 <span data-ttu-id="db131-124">**En-têtes de réponse** - aucun en-tête supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="db131-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="db131-125">**Corps de réponse** - vous trouverez ci-dessous une charge utile d’exemple réponse au format JSON.</span><span class="sxs-lookup"><span data-stu-id="db131-125">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
```
{
"itemId": 1652,
"userId": 0,
"content": "{\"Title\":\"All Audio Streams\",...}",
"type": "application/json",
"subItemIds": [1653, 1710]
}
```

 <span data-ttu-id="db131-126">*itemId* - ID de l’élément.</span><span class="sxs-lookup"><span data-stu-id="db131-126">*itemId*  - ID of the item.</span></span>
  
 <span data-ttu-id="db131-127">*userId* - ID de l’utilisateur qui possède cet article.</span><span class="sxs-lookup"><span data-stu-id="db131-127">*userId*  - ID of the user who owns this item.</span></span>
  
 <span data-ttu-id="db131-128">*contenu* - le contenu spécifique à l’application.</span><span class="sxs-lookup"><span data-stu-id="db131-128">*content*  - The application-specific content.</span></span>
  
 <span data-ttu-id="db131-129">*type* : le type de contenu.</span><span class="sxs-lookup"><span data-stu-id="db131-129">*type*  - The type of the content.</span></span> <span data-ttu-id="db131-130">Ce champ est défini par les applications.</span><span class="sxs-lookup"><span data-stu-id="db131-130">This field is set by the applications.</span></span>
  
 <span data-ttu-id="db131-131">*subItemIds* - identifiants des sous-éléments, le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="db131-131">*subItemIds*  - The IDs of sub-Items, if any.</span></span> <span data-ttu-id="db131-132">Il s’agit d’un court-circuit d’opération obtenir les sous-éléments pour enregistrer un appel.</span><span class="sxs-lookup"><span data-stu-id="db131-132">This is a short-circuit of Get Sub-Items operation to save a call.</span></span> <span data-ttu-id="db131-133">Les applications peuvent également obtenir les mêmes informations à l’aide d’opération obtenir les sous-éléments.</span><span class="sxs-lookup"><span data-stu-id="db131-133">Applications can alternatively obtain the same information using Get Sub-Items operation.</span></span>
  

