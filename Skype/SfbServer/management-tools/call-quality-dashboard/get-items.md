---
title: Extraire des éléments
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 9e189a48-4944-4f93-88d7-9d56b56770a6
description: 'Résumé : Découvrez l’opération obtenir les éléments, ce qui fait partie du Service de l’élément. Le Service de l’élément fait partie de l’API de référentiel pour appeler le tableau de bord qualité. Tableau de bord de qualité des appels est un outil de Skype pour Business Server.'
ms.openlocfilehash: d3b0812232b25b412a23dba3a7270eda5a01077b
ms.sourcegitcommit: b680505c5dad435d98fbd0b235e0e7c67b9d8c9c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/07/2018
ms.locfileid: "26035546"
---
# <a name="get-items"></a><span data-ttu-id="eddd9-105">Extraire des éléments</span><span class="sxs-lookup"><span data-stu-id="eddd9-105">Get Items</span></span>
 
<span data-ttu-id="eddd9-106">**Résumé :** Obtenir des informations sur l’opération obtenir les éléments, ce qui fait partie du Service de l’élément.</span><span class="sxs-lookup"><span data-stu-id="eddd9-106">**Summary:** Learn about the Get Items operation, which is part of the Item Service.</span></span> <span data-ttu-id="eddd9-107">Le Service de l’élément fait partie de l’API de référentiel pour appeler le tableau de bord qualité.</span><span class="sxs-lookup"><span data-stu-id="eddd9-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="eddd9-108">Tableau de bord de qualité des appels est un outil de Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="eddd9-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="eddd9-109">L’opération obtenir les éléments fait partie du Service d’élément dans l’API de référentiel pour appeler le tableau de bord qualité.</span><span class="sxs-lookup"><span data-stu-id="eddd9-109">The Get Items operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-items"></a><span data-ttu-id="eddd9-110">Extraire des éléments</span><span class="sxs-lookup"><span data-stu-id="eddd9-110">Get Items</span></span>

<span data-ttu-id="eddd9-111">Obtenir les éléments renvoie tous les éléments dans le référentiel.</span><span class="sxs-lookup"><span data-stu-id="eddd9-111">Get Items returns all Items in the repository.</span></span>
  
|<span data-ttu-id="eddd9-112">**Méthode**</span><span class="sxs-lookup"><span data-stu-id="eddd9-112">**Method**</span></span>|<span data-ttu-id="eddd9-113">**URI de la demande**</span><span class="sxs-lookup"><span data-stu-id="eddd9-113">**Request URI**</span></span>|<span data-ttu-id="eddd9-114">**Version HTTP**</span><span class="sxs-lookup"><span data-stu-id="eddd9-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="eddd9-115">Télécharger</span><span class="sxs-lookup"><span data-stu-id="eddd9-115">GET</span></span>  <br/> |<span data-ttu-id="eddd9-116">https://\<portal\>/QoERepositoryService/repository/item</span><span class="sxs-lookup"><span data-stu-id="eddd9-116">https://\<portal\>/QoERepositoryService/repository/item</span></span>  <br/> |<span data-ttu-id="eddd9-117">HTTP/1.1.</span><span class="sxs-lookup"><span data-stu-id="eddd9-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="eddd9-118">**Paramètres d’URI** - None.</span><span class="sxs-lookup"><span data-stu-id="eddd9-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="eddd9-119">**En-têtes de demande** - aucun en-tête supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="eddd9-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="eddd9-120">**Corps de requête** - None.</span><span class="sxs-lookup"><span data-stu-id="eddd9-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="eddd9-121">**Réponse** - la réponse inclut un code d’état HTTP et un ensemble d’en-têtes de réponse.</span><span class="sxs-lookup"><span data-stu-id="eddd9-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="eddd9-122">**Code d’état** - une opération réussie retourne un code d’état 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="eddd9-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="eddd9-123">**En-têtes de réponse** - aucun en-tête supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="eddd9-123">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="eddd9-124">**Corps de réponse** - vous trouverez ci-dessous une charge utile d’exemple réponse au format JSON.</span><span class="sxs-lookup"><span data-stu-id="eddd9-124">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
> [!NOTE]
> <span data-ttu-id="eddd9-125">Un tableau d’objets d’élément est renvoyé.</span><span class="sxs-lookup"><span data-stu-id="eddd9-125">An array of Item objects is returned.</span></span> <span data-ttu-id="eddd9-126">Pour plus d’informations sur l’objet d’élément, voir obtenir un élément.</span><span class="sxs-lookup"><span data-stu-id="eddd9-126">For details about Item object, see Get Item.</span></span> 
  
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