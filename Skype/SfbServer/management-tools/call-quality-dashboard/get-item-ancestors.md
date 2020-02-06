---
title: Obtenir les ancêtres d’élément
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d39b1dbc-1514-43ec-8593-9f23b3fcae62
description: 'Résumé : en savoir plus sur l’opération obtenir les ancêtres de l’élément, qui fait partie du service d’élément. Le service d’élément fait partie de l’API du référentiel pour le tableau de bord de qualité des appels. Le tableau de bord de qualité des appels est un outil pour Skype entreprise Server.'
ms.openlocfilehash: 7beaffbb670f664ec7181482dbceb120a8b7d9e8
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816803"
---
# <a name="get-item-ancestors"></a><span data-ttu-id="ad8ab-105">Obtenir les ancêtres d’élément</span><span class="sxs-lookup"><span data-stu-id="ad8ab-105">Get Item Ancestors</span></span>
 
<span data-ttu-id="ad8ab-106">**Résumé :** En savoir plus sur l’opération obtenir les ancêtres de l’élément, qui fait partie du service d’élément.</span><span class="sxs-lookup"><span data-stu-id="ad8ab-106">**Summary:** Learn about the Get Item Ancestors operation, which is part of the Item Service.</span></span> <span data-ttu-id="ad8ab-107">Le service d’élément fait partie de l’API du référentiel pour le tableau de bord de qualité des appels.</span><span class="sxs-lookup"><span data-stu-id="ad8ab-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="ad8ab-108">Le tableau de bord de qualité des appels est un outil pour Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="ad8ab-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="ad8ab-109">L’opération obtenir les ancêtres de l’élément fait partie du service d’élément dans l’API du référentiel pour le tableau de bord de qualité des appels.</span><span class="sxs-lookup"><span data-stu-id="ad8ab-109">The Get Item Ancestors operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-item-ancestors"></a><span data-ttu-id="ad8ab-110">Obtenir les ancêtres d’élément</span><span class="sxs-lookup"><span data-stu-id="ad8ab-110">Get Item Ancestors</span></span>

<span data-ttu-id="ad8ab-111">Obtenir les ancêtres renvoie les ancêtres d’éléments spécifiques du référentiel.</span><span class="sxs-lookup"><span data-stu-id="ad8ab-111">Get Item Ancestors returns a specific items ancestors from the repository.</span></span>
  

|<span data-ttu-id="ad8ab-112">**Méthode**</span><span class="sxs-lookup"><span data-stu-id="ad8ab-112">**Method**</span></span>|<span data-ttu-id="ad8ab-113">**URI de la requête**</span><span class="sxs-lookup"><span data-stu-id="ad8ab-113">**Request URI**</span></span>|<span data-ttu-id="ad8ab-114">**Version HTTP**</span><span class="sxs-lookup"><span data-stu-id="ad8ab-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ad8ab-115">Télécharger</span><span class="sxs-lookup"><span data-stu-id="ad8ab-115">GET</span></span>  <br/> |<span data-ttu-id="ad8ab-116">https://\<Portal\>/QoERepositoryService/Repository/itemAncestors/{ItemId}</span><span class="sxs-lookup"><span data-stu-id="ad8ab-116">https://\<portal\>/QoERepositoryService/repository/itemAncestors/{itemId}</span></span>  <br/> |<span data-ttu-id="ad8ab-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="ad8ab-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="ad8ab-118">**Paramètres d’URI** -aucun.</span><span class="sxs-lookup"><span data-stu-id="ad8ab-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="ad8ab-119">**En-têtes de requête** -aucun en-tête supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="ad8ab-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="ad8ab-120">Le corps de la **requête** .</span><span class="sxs-lookup"><span data-stu-id="ad8ab-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="ad8ab-121">**Réponse** : la réponse comprend un code d’État http et un ensemble d’en-têtes de réponse.</span><span class="sxs-lookup"><span data-stu-id="ad8ab-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="ad8ab-122">**Code d’État** -une opération réussie renvoie le code d’état 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="ad8ab-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span> <span data-ttu-id="ad8ab-123">Si vous n’avez pas trouvé d’ID utilisateur spécifié, le code d’État 404 (introuvable) est renvoyé.</span><span class="sxs-lookup"><span data-stu-id="ad8ab-123">If a specified user ID is not found, it returns status code 404 (Not Found).</span></span>
  
 <span data-ttu-id="ad8ab-124">**En-têtes de réponse** : aucun en-tête supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="ad8ab-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="ad8ab-125">Le corps de la **réponse** : Voici un exemple de charge utile de réponse dans JSON.</span><span class="sxs-lookup"><span data-stu-id="ad8ab-125">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
```json
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

 <span data-ttu-id="ad8ab-126">*Item1* -ID de l’article.</span><span class="sxs-lookup"><span data-stu-id="ad8ab-126">*Item1*  - ID of the item.</span></span>
  
 <span data-ttu-id="ad8ab-127">*Item2* -profondeur correspond à la distance de l’élément.</span><span class="sxs-lookup"><span data-stu-id="ad8ab-127">*Item2*  - Depth is the distance from the Item.</span></span> <span data-ttu-id="ad8ab-128">0 est le parent immédiat.</span><span class="sxs-lookup"><span data-stu-id="ad8ab-128">0 is the immediate parent.</span></span>
  
 <span data-ttu-id="ad8ab-129">*Item3* -titre de l’article.</span><span class="sxs-lookup"><span data-stu-id="ad8ab-129">*Item3*  - Title of the item.</span></span>
  

