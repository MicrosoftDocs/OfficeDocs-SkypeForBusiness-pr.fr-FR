---
title: Extraire des éléments
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
description: 'Résumé : Découvrez l’opération obtenir les éléments, ce qui fait partie du Service de l’élément. Le Service de l’élément fait partie de l’API de référentiel pour appeler le tableau de bord qualité. Tableau de bord de qualité des appels est un outil de Skype pour Business Server 2015.'
ms.openlocfilehash: 628dd1e40014dc819ca926af6ea09a9475cb6efe
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/05/2018
ms.locfileid: "19569427"
---
# <a name="get-items"></a><span data-ttu-id="0f29f-105">Extraire des éléments</span><span class="sxs-lookup"><span data-stu-id="0f29f-105">Get Items</span></span>
 
<span data-ttu-id="0f29f-106">**Résumé :** Obtenir des informations sur l’opération obtenir les éléments, ce qui fait partie du Service de l’élément.</span><span class="sxs-lookup"><span data-stu-id="0f29f-106">**Summary:** Learn about the Get Items operation, which is part of the Item Service.</span></span> <span data-ttu-id="0f29f-107">Le Service de l’élément fait partie de l’API de référentiel pour appeler le tableau de bord qualité.</span><span class="sxs-lookup"><span data-stu-id="0f29f-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="0f29f-108">Tableau de bord de qualité des appels est un outil de Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="0f29f-108">Call Quality Dashboard is a tool for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="0f29f-109">L’opération obtenir les éléments fait partie du Service d’élément dans l’API de référentiel pour appeler le tableau de bord qualité.</span><span class="sxs-lookup"><span data-stu-id="0f29f-109">The Get Items operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-items"></a><span data-ttu-id="0f29f-110">Extraire des éléments</span><span class="sxs-lookup"><span data-stu-id="0f29f-110">Get Items</span></span>

<span data-ttu-id="0f29f-111">Obtenir les éléments renvoie tous les éléments dans le référentiel.</span><span class="sxs-lookup"><span data-stu-id="0f29f-111">Get Items returns all Items in the repository.</span></span>
  
|<span data-ttu-id="0f29f-112">**Méthode**</span><span class="sxs-lookup"><span data-stu-id="0f29f-112">**Method**</span></span>|<span data-ttu-id="0f29f-113">**URI de la demande**</span><span class="sxs-lookup"><span data-stu-id="0f29f-113">**Request URI**</span></span>|<span data-ttu-id="0f29f-114">**Version HTTP**</span><span class="sxs-lookup"><span data-stu-id="0f29f-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="0f29f-115">Télécharger</span><span class="sxs-lookup"><span data-stu-id="0f29f-115">GET</span></span>  <br/> |<span data-ttu-id="0f29f-116">https://\<portal\>/QoERepositoryService/repository/item</span><span class="sxs-lookup"><span data-stu-id="0f29f-116">https://\<portal\>/QoERepositoryService/repository/item</span></span>  <br/> |<span data-ttu-id="0f29f-117">HTTP/1.1.</span><span class="sxs-lookup"><span data-stu-id="0f29f-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="0f29f-118">**Paramètres d’URI** - None.</span><span class="sxs-lookup"><span data-stu-id="0f29f-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="0f29f-119">**En-têtes de demande** - aucun en-tête supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="0f29f-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="0f29f-120">**Corps de requête** - None.</span><span class="sxs-lookup"><span data-stu-id="0f29f-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="0f29f-121">**Réponse** - la réponse inclut un code d’état HTTP et un ensemble d’en-têtes de réponse.</span><span class="sxs-lookup"><span data-stu-id="0f29f-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="0f29f-122">**Code d’état** - une opération réussie retourne un code d’état 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="0f29f-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="0f29f-123">**En-têtes de réponse** - aucun en-tête supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="0f29f-123">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="0f29f-124">**Corps de réponse** - vous trouverez ci-dessous une charge utile d’exemple réponse au format JSON.</span><span class="sxs-lookup"><span data-stu-id="0f29f-124">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0f29f-125">Un tableau d’objets d’élément est renvoyé.</span><span class="sxs-lookup"><span data-stu-id="0f29f-125">An array of Item objects is returned.</span></span> <span data-ttu-id="0f29f-126">Pour plus d’informations sur l’objet d’élément, voir obtenir un élément.</span><span class="sxs-lookup"><span data-stu-id="0f29f-126">For details about Item object, see Get Item.</span></span> 
  
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