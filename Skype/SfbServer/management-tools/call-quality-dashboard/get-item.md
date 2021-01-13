---
title: Obtenir l’élément
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: e77bf649-d62a-4d94-80de-066ba47730cd
description: 'Résumé : Découvrez l’opération Obtenir un élément, qui fait partie du service d’élément. Le service d’élément fait partie de l’API de référentiel pour le tableau de bord de qualité des appels. Le Tableau de bord de qualité des appels est un outil pour Skype Entreprise Server.'
ms.openlocfilehash: 896540c4572fb3991356ce055f01690ed702c6f2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832564"
---
# <a name="get-item"></a><span data-ttu-id="42c3c-105">Obtenir l’élément</span><span class="sxs-lookup"><span data-stu-id="42c3c-105">Get Item</span></span>
 
<span data-ttu-id="42c3c-106">**Résumé :** Découvrez l’opération Obtenir un élément, qui fait partie du service d’élément.</span><span class="sxs-lookup"><span data-stu-id="42c3c-106">**Summary:** Learn about the Get Item operation, which is part of the Item Service.</span></span> <span data-ttu-id="42c3c-107">Le service d’élément fait partie de l’API de référentiel pour le tableau de bord de qualité des appels.</span><span class="sxs-lookup"><span data-stu-id="42c3c-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="42c3c-108">Le Tableau de bord de qualité des appels est un outil pour Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="42c3c-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="42c3c-109">L’opération Obtenir un élément fait partie du service d’élément dans l’API référentiel pour le tableau de bord de qualité des appels.</span><span class="sxs-lookup"><span data-stu-id="42c3c-109">The Get Item operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-item"></a><span data-ttu-id="42c3c-110">Obtenir l’élément</span><span class="sxs-lookup"><span data-stu-id="42c3c-110">Get Item</span></span>

<span data-ttu-id="42c3c-111">Obtenir l’élément renvoie un élément spécifique dans le référentiel.</span><span class="sxs-lookup"><span data-stu-id="42c3c-111">Get Item returns a specific item in the repository.</span></span>
  
|<span data-ttu-id="42c3c-112">**Méthode**</span><span class="sxs-lookup"><span data-stu-id="42c3c-112">**Method**</span></span>|<span data-ttu-id="42c3c-113">**URI de demande**</span><span class="sxs-lookup"><span data-stu-id="42c3c-113">**Request URI**</span></span>|<span data-ttu-id="42c3c-114">**HTTP Version**</span><span class="sxs-lookup"><span data-stu-id="42c3c-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="42c3c-115">GET</span><span class="sxs-lookup"><span data-stu-id="42c3c-115">GET</span></span>  <br/> |<span data-ttu-id="42c3c-116">https:// \<portal\> /QoERepositoryService/repository/item/{itemId}</span><span class="sxs-lookup"><span data-stu-id="42c3c-116">https://\<portal\>/QoERepositoryService/repository/item/{itemId}</span></span>  <br/> |<span data-ttu-id="42c3c-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="42c3c-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="42c3c-118">**Paramètres d’URI** - Aucun.</span><span class="sxs-lookup"><span data-stu-id="42c3c-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="42c3c-119">**En-têtes de requête** : aucun en-tête supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="42c3c-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="42c3c-120">**Corps de la** demande - Aucun.</span><span class="sxs-lookup"><span data-stu-id="42c3c-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="42c3c-121">**Réponse** : la réponse inclut un code d’état HTTP et un ensemble d’en-têtes de réponse.</span><span class="sxs-lookup"><span data-stu-id="42c3c-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="42c3c-122">**Code d’état** : une opération réussie renvoie le code d’état 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="42c3c-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span> <span data-ttu-id="42c3c-123">Si un ID d’élément spécifié est in trouvé, il renvoie le code d’état 404 (In trouvé).</span><span class="sxs-lookup"><span data-stu-id="42c3c-123">If a specified item ID is not found, it returns status code 404 (Not Found).</span></span>
  
 <span data-ttu-id="42c3c-124">**En-têtes de réponse** : aucun en-tête supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="42c3c-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="42c3c-125">**Corps de la** réponse : voici un exemple de charge utile de réponse dans JSON.</span><span class="sxs-lookup"><span data-stu-id="42c3c-125">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
```json
{
"itemId": 1652,
"userId": 0,
"content": "{\"Title\":\"All Audio Streams\",...}",
"type": "application/json",
"subItemIds": [1653, 1710]
}
```

 <span data-ttu-id="42c3c-126">*itemId*  : ID de l’élément.</span><span class="sxs-lookup"><span data-stu-id="42c3c-126">*itemId*  - ID of the item.</span></span>
  
 <span data-ttu-id="42c3c-127">*userId*  : ID de l’utilisateur propriétaire de cet élément.</span><span class="sxs-lookup"><span data-stu-id="42c3c-127">*userId*  - ID of the user who owns this item.</span></span>
  
 <span data-ttu-id="42c3c-128">*content*  - Contenu propre à l’application.</span><span class="sxs-lookup"><span data-stu-id="42c3c-128">*content*  - The application-specific content.</span></span>
  
 <span data-ttu-id="42c3c-129">*type*  : type du contenu.</span><span class="sxs-lookup"><span data-stu-id="42c3c-129">*type*  - The type of the content.</span></span> <span data-ttu-id="42c3c-130">Ce champ est définie par les applications.</span><span class="sxs-lookup"><span data-stu-id="42c3c-130">This field is set by the applications.</span></span>
  
 <span data-ttu-id="42c3c-131">*subItemIds*  : ID des sous-éléments, le cas cas.</span><span class="sxs-lookup"><span data-stu-id="42c3c-131">*subItemIds*  - The IDs of sub-Items, if any.</span></span> <span data-ttu-id="42c3c-132">Il s’agit d’un court-circuit de l’opération Get Sub-Items pour enregistrer un appel.</span><span class="sxs-lookup"><span data-stu-id="42c3c-132">This is a short-circuit of Get Sub-Items operation to save a call.</span></span> <span data-ttu-id="42c3c-133">Les applications peuvent également obtenir les mêmes informations à l’aide de l’opération Get Sub-Items.</span><span class="sxs-lookup"><span data-stu-id="42c3c-133">Applications can alternatively obtain the same information using Get Sub-Items operation.</span></span>
  

