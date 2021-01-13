---
title: Obtenir les ancêtres d’élément
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
ms.assetid: d39b1dbc-1514-43ec-8593-9f23b3fcae62
description: 'Résumé : Découvrez l’opération Obtenir des ancêtres d’élément, qui fait partie du service d’élément. Le service d’élément fait partie de l’API de référentiel pour le tableau de bord de qualité des appels. Le Tableau de bord de qualité des appels est un outil pour Skype Entreprise Server.'
ms.openlocfilehash: 59fcd10f620b32151346e8732e67ae6151a258ff
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832574"
---
# <a name="get-item-ancestors"></a><span data-ttu-id="1980c-105">Obtenir les ancêtres d’élément</span><span class="sxs-lookup"><span data-stu-id="1980c-105">Get Item Ancestors</span></span>
 
<span data-ttu-id="1980c-106">**Résumé :** Découvrez l’opération Obtenir des ancêtres d’élément, qui fait partie du service d’élément.</span><span class="sxs-lookup"><span data-stu-id="1980c-106">**Summary:** Learn about the Get Item Ancestors operation, which is part of the Item Service.</span></span> <span data-ttu-id="1980c-107">Le service d’élément fait partie de l’API de référentiel pour le tableau de bord de qualité des appels.</span><span class="sxs-lookup"><span data-stu-id="1980c-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="1980c-108">Le Tableau de bord de qualité des appels est un outil pour Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="1980c-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="1980c-109">L’opération Obtenir des ancêtres d’élément fait partie du service d’élément dans l’API référentiel pour le tableau de bord de qualité des appels.</span><span class="sxs-lookup"><span data-stu-id="1980c-109">The Get Item Ancestors operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-item-ancestors"></a><span data-ttu-id="1980c-110">Obtenir les ancêtres d’élément</span><span class="sxs-lookup"><span data-stu-id="1980c-110">Get Item Ancestors</span></span>

<span data-ttu-id="1980c-111">Obtenir des ancêtres d’élément renvoie des ancêtres d’éléments spécifiques à partir du référentiel.</span><span class="sxs-lookup"><span data-stu-id="1980c-111">Get Item Ancestors returns a specific items ancestors from the repository.</span></span>
  

|<span data-ttu-id="1980c-112">**Méthode**</span><span class="sxs-lookup"><span data-stu-id="1980c-112">**Method**</span></span>|<span data-ttu-id="1980c-113">**URI de demande**</span><span class="sxs-lookup"><span data-stu-id="1980c-113">**Request URI**</span></span>|<span data-ttu-id="1980c-114">**HTTP Version**</span><span class="sxs-lookup"><span data-stu-id="1980c-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1980c-115">GET</span><span class="sxs-lookup"><span data-stu-id="1980c-115">GET</span></span>  <br/> |<span data-ttu-id="1980c-116">https:// \<portal\> /QoERepositoryService/repository/itemAncestors/{itemId}</span><span class="sxs-lookup"><span data-stu-id="1980c-116">https://\<portal\>/QoERepositoryService/repository/itemAncestors/{itemId}</span></span>  <br/> |<span data-ttu-id="1980c-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="1980c-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="1980c-118">**Paramètres d’URI** - Aucun.</span><span class="sxs-lookup"><span data-stu-id="1980c-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="1980c-119">**En-têtes de requête** : aucun en-tête supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="1980c-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="1980c-120">**Corps de la** demande - Aucun.</span><span class="sxs-lookup"><span data-stu-id="1980c-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="1980c-121">**Réponse** : la réponse inclut un code d’état HTTP et un ensemble d’en-têtes de réponse.</span><span class="sxs-lookup"><span data-stu-id="1980c-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="1980c-122">**Code d’état** : une opération réussie renvoie le code d’état 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="1980c-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span> <span data-ttu-id="1980c-123">Si un ID utilisateur spécifié est in trouvé, il renvoie le code d’état 404 (In trouvé).</span><span class="sxs-lookup"><span data-stu-id="1980c-123">If a specified user ID is not found, it returns status code 404 (Not Found).</span></span>
  
 <span data-ttu-id="1980c-124">**En-têtes de réponse** : aucun en-tête supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="1980c-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="1980c-125">**Corps de la** réponse : voici un exemple de charge utile de réponse dans JSON.</span><span class="sxs-lookup"><span data-stu-id="1980c-125">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
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

 <span data-ttu-id="1980c-126">*Item1*  : ID de l’élément.</span><span class="sxs-lookup"><span data-stu-id="1980c-126">*Item1*  - ID of the item.</span></span>
  
 <span data-ttu-id="1980c-127">*Élément2*  : la profondeur est la distance à partir de l’élément.</span><span class="sxs-lookup"><span data-stu-id="1980c-127">*Item2*  - Depth is the distance from the Item.</span></span> <span data-ttu-id="1980c-128">0 est le parent immédiat.</span><span class="sxs-lookup"><span data-stu-id="1980c-128">0 is the immediate parent.</span></span>
  
 <span data-ttu-id="1980c-129">*Item3*  : titre de l’élément.</span><span class="sxs-lookup"><span data-stu-id="1980c-129">*Item3*  - Title of the item.</span></span>
  

