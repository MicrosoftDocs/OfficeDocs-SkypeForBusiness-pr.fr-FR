---
title: Obtenir l’élément ancêtres
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
description: 'Résumé : Découvrez l’opération obtenir des ancêtres élément, qui fait partie du Service de l’élément. Le Service de l’élément fait partie de l’API de référentiel pour appeler le tableau de bord qualité. Tableau de bord de qualité des appels est un outil de Skype pour Business Server 2015.'
ms.openlocfilehash: 60d77ff1fd14a994d55a42516cd686891a56595f
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/05/2018
ms.locfileid: "19569200"
---
# <a name="get-item-ancestors"></a><span data-ttu-id="1257d-105">Obtenir l’élément ancêtres</span><span class="sxs-lookup"><span data-stu-id="1257d-105">Get Item Ancestors</span></span>
 
<span data-ttu-id="1257d-106">**Résumé :** Obtenir des informations sur l’opération obtenir des ancêtres élément, qui fait partie du Service de l’élément.</span><span class="sxs-lookup"><span data-stu-id="1257d-106">**Summary:** Learn about the Get Item Ancestors operation, which is part of the Item Service.</span></span> <span data-ttu-id="1257d-107">Le Service de l’élément fait partie de l’API de référentiel pour appeler le tableau de bord qualité.</span><span class="sxs-lookup"><span data-stu-id="1257d-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="1257d-108">Tableau de bord de qualité des appels est un outil de Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="1257d-108">Call Quality Dashboard is a tool for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="1257d-109">L’opération obtenir des ancêtres élément fait partie du Service d’élément dans l’API de référentiel pour appeler le tableau de bord qualité.</span><span class="sxs-lookup"><span data-stu-id="1257d-109">The Get Item Ancestors operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-item-ancestors"></a><span data-ttu-id="1257d-110">Obtenir l’élément ancêtres</span><span class="sxs-lookup"><span data-stu-id="1257d-110">Get Item Ancestors</span></span>

<span data-ttu-id="1257d-111">Get élément ancêtres renvoie une ancêtres des éléments spécifiques à partir du référentiel.</span><span class="sxs-lookup"><span data-stu-id="1257d-111">Get Item Ancestors returns a specific items ancestors from the repository.</span></span>
  

|<span data-ttu-id="1257d-112">**Méthode**</span><span class="sxs-lookup"><span data-stu-id="1257d-112">**Method**</span></span>|<span data-ttu-id="1257d-113">**URI de la demande**</span><span class="sxs-lookup"><span data-stu-id="1257d-113">**Request URI**</span></span>|<span data-ttu-id="1257d-114">**Version HTTP**</span><span class="sxs-lookup"><span data-stu-id="1257d-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1257d-115">Télécharger</span><span class="sxs-lookup"><span data-stu-id="1257d-115">GET</span></span>  <br/> |<span data-ttu-id="1257d-116">https://\<portal\>/QoERepositoryService/référentiel/itemAncestors / {itemId}</span><span class="sxs-lookup"><span data-stu-id="1257d-116">https://\<portal\>/QoERepositoryService/repository/itemAncestors/{itemId}</span></span>  <br/> |<span data-ttu-id="1257d-117">HTTP/1.1.</span><span class="sxs-lookup"><span data-stu-id="1257d-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="1257d-118">**Paramètres d’URI** - None.</span><span class="sxs-lookup"><span data-stu-id="1257d-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="1257d-119">**En-têtes de demande** - aucun en-tête supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="1257d-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="1257d-120">**Corps de requête** - None.</span><span class="sxs-lookup"><span data-stu-id="1257d-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="1257d-121">**Réponse** - la réponse inclut un code d’état HTTP et un ensemble d’en-têtes de réponse.</span><span class="sxs-lookup"><span data-stu-id="1257d-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="1257d-122">**Code d’état** - une opération réussie retourne un code d’état 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="1257d-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span> <span data-ttu-id="1257d-123">Si un utilisateur spécifié QU'ID est introuvable, elle renvoie le code d’état 404 (introuvable).</span><span class="sxs-lookup"><span data-stu-id="1257d-123">If a specified user ID is not found, it returns status code 404 (Not Found).</span></span>
  
 <span data-ttu-id="1257d-124">**En-têtes de réponse** - aucun en-tête supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="1257d-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="1257d-125">**Corps de réponse** - vous trouverez ci-dessous une charge utile d’exemple réponse au format JSON.</span><span class="sxs-lookup"><span data-stu-id="1257d-125">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
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

 <span data-ttu-id="1257d-126">*Item1* - ID de l’élément.</span><span class="sxs-lookup"><span data-stu-id="1257d-126">*Item1*  - ID of the item.</span></span>
  
 <span data-ttu-id="1257d-127">*Item2* - profondeur est la distance à partir de l’élément.</span><span class="sxs-lookup"><span data-stu-id="1257d-127">*Item2*  - Depth is the distance from the Item.</span></span> <span data-ttu-id="1257d-128">0 est le parent immédiat.</span><span class="sxs-lookup"><span data-stu-id="1257d-128">0 is the immediate parent.</span></span>
  
 <span data-ttu-id="1257d-129">*Item3* - titre de l’élément.</span><span class="sxs-lookup"><span data-stu-id="1257d-129">*Item3*  - Title of the item.</span></span>
  

