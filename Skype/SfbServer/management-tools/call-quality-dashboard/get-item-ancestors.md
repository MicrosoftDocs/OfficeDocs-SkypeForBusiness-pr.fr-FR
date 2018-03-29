---
title: Obtenir les ancêtres de l’élément
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d39b1dbc-1514-43ec-8593-9f23b3fcae62
description: 'Résumé : Découvrez l’opération obtenir les ancêtres article, qui fait partie de l’article de Service. L’article de Service fait partie de l’API de référentiel pour appeler le tableau de bord qualité. Tableau de bord qualité appel est un outil de Skype pour Business Server 2015.'
ms.openlocfilehash: ab5cc9dd388d1192922430e2a728bb8073b3e0d7
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="get-item-ancestors"></a><span data-ttu-id="bfd1c-105">Obtenir les ancêtres de l’élément</span><span class="sxs-lookup"><span data-stu-id="bfd1c-105">Get Item Ancestors</span></span>
 
<span data-ttu-id="bfd1c-106">**Résumé :** Obtenir des informations sur l’opération obtenir les ancêtres article, qui fait partie de l’article de Service.</span><span class="sxs-lookup"><span data-stu-id="bfd1c-106">**Summary:** Learn about the Get Item Ancestors operation, which is part of the Item Service.</span></span> <span data-ttu-id="bfd1c-107">L’article de Service fait partie de l’API de référentiel pour appeler le tableau de bord qualité.</span><span class="sxs-lookup"><span data-stu-id="bfd1c-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="bfd1c-108">Tableau de bord qualité appel est un outil de Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="bfd1c-108">Call Quality Dashboard is a tool for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="bfd1c-109">L’opération obtenir les ancêtres élément fait partie de l’article Service dans l’API de référentiel pour appeler le tableau de bord qualité.</span><span class="sxs-lookup"><span data-stu-id="bfd1c-109">The Get Item Ancestors operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-item-ancestors"></a><span data-ttu-id="bfd1c-110">Obtenir les ancêtres de l’élément</span><span class="sxs-lookup"><span data-stu-id="bfd1c-110">Get Item Ancestors</span></span>

<span data-ttu-id="bfd1c-111">Obtenir les ancêtres de l’élément renvoie un ancêtres des éléments spécifiques à partir du référentiel.</span><span class="sxs-lookup"><span data-stu-id="bfd1c-111">Get Item Ancestors returns a specific items ancestors from the repository.</span></span>
  

|<span data-ttu-id="bfd1c-112">**Méthode**</span><span class="sxs-lookup"><span data-stu-id="bfd1c-112">**Method**</span></span>|<span data-ttu-id="bfd1c-113">**URI de la demande**</span><span class="sxs-lookup"><span data-stu-id="bfd1c-113">**Request URI**</span></span>|<span data-ttu-id="bfd1c-114">**Version de HTTP**</span><span class="sxs-lookup"><span data-stu-id="bfd1c-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="bfd1c-115">Télécharger</span><span class="sxs-lookup"><span data-stu-id="bfd1c-115">GET</span></span>  <br/> |<span data-ttu-id="bfd1c-116">https://\<portal\>/QoERepositoryService/repository/itemAncestors / {itemId}</span><span class="sxs-lookup"><span data-stu-id="bfd1c-116">https://\<portal\>/QoERepositoryService/repository/itemAncestors/{itemId}</span></span>  <br/> |<span data-ttu-id="bfd1c-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="bfd1c-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="bfd1c-118">**Les paramètres URI** - None.</span><span class="sxs-lookup"><span data-stu-id="bfd1c-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="bfd1c-119">**En-têtes de requête** - aucun en-tête supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="bfd1c-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="bfd1c-120">**Corps de requête** - None.</span><span class="sxs-lookup"><span data-stu-id="bfd1c-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="bfd1c-121">**Réponse** : la réponse contient un code d’état HTTP et d’un ensemble d’en-têtes de réponse.</span><span class="sxs-lookup"><span data-stu-id="bfd1c-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="bfd1c-122">**Code d’état** - une opération réussie retourne un code d’état 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="bfd1c-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span> <span data-ttu-id="bfd1c-123">Si un utilisateur spécifié QU'ID n’est pas trouvé, il renvoie le code d’état 404 (introuvable).</span><span class="sxs-lookup"><span data-stu-id="bfd1c-123">If a specified user ID is not found, it returns status code 404 (Not Found).</span></span>
  
 <span data-ttu-id="bfd1c-124">**En-têtes de réponse** - aucun en-tête supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="bfd1c-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="bfd1c-125">**Corps de la réponse** - Voici une charge utile d’exemple réponse au format JSON.</span><span class="sxs-lookup"><span data-stu-id="bfd1c-125">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
```
[{
"item1": 1653,
"item2": 0,
"item3": "Audio Streams Monthly Trend"
},
{
"item1": 1652,
"item2": 1,
"item3": "All Audio Streams"
}]

```

 <span data-ttu-id="bfd1c-126">*Item1* - ID de l’élément.</span><span class="sxs-lookup"><span data-stu-id="bfd1c-126">*Item1*  - ID of the item.</span></span>
  
 <span data-ttu-id="bfd1c-127">*Item2* - profondeur est la distance à partir de l’élément.</span><span class="sxs-lookup"><span data-stu-id="bfd1c-127">*Item2*  - Depth is the distance from the Item.</span></span> <span data-ttu-id="bfd1c-128">0 est le parent immédiat.</span><span class="sxs-lookup"><span data-stu-id="bfd1c-128">0 is the immediate parent.</span></span>
  
 <span data-ttu-id="bfd1c-129">*Item3* - titre de l’élément.</span><span class="sxs-lookup"><span data-stu-id="bfd1c-129">*Item3*  - Title of the item.</span></span>
  

