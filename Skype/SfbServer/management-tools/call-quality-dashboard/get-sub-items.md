---
title: Obtenir les sous-éléments
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 0542eba9-3dda-40de-bba8-095d22825e4e
description: 'Résumé : Découvrez l’opération obtenir les sous-éléments, qui fait partie du Service de l’élément. Le Service de l’élément fait partie de l’API de référentiel pour appeler le tableau de bord qualité. Tableau de bord de qualité des appels est un outil de Skype pour Business Server 2015.'
ms.openlocfilehash: f125a10ac9d3f608216ea23d17f614d0bff88af7
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/13/2018
ms.locfileid: "26295938"
---
# <a name="get-sub-items"></a><span data-ttu-id="3402e-105">Obtenir les sous-éléments</span><span class="sxs-lookup"><span data-stu-id="3402e-105">Get Sub-Items</span></span>
 
<span data-ttu-id="3402e-106">**Résumé :** Obtenir des informations sur l’opération obtenir les sous-éléments, qui fait partie du Service de l’élément.</span><span class="sxs-lookup"><span data-stu-id="3402e-106">**Summary:** Learn about the Get Sub-Items operation, which is part of the Item Service.</span></span> <span data-ttu-id="3402e-107">Le Service de l’élément fait partie de l’API de référentiel pour appeler le tableau de bord qualité.</span><span class="sxs-lookup"><span data-stu-id="3402e-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="3402e-108">Tableau de bord de qualité des appels est un outil de Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="3402e-108">Call Quality Dashboard is a tool for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="3402e-109">L’opération obtenir les sous-éléments fait partie du Service d’élément dans l’API de référentiel pour appeler le tableau de bord qualité.</span><span class="sxs-lookup"><span data-stu-id="3402e-109">The Get Sub-Items operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-sub-items"></a><span data-ttu-id="3402e-110">Obtenir les sous-éléments</span><span class="sxs-lookup"><span data-stu-id="3402e-110">Get Sub-Items</span></span>

<span data-ttu-id="3402e-111">Obtenez les sous-éléments renvoie les sous-éléments d’un élément spécifique.</span><span class="sxs-lookup"><span data-stu-id="3402e-111">Get Sub-Items returns a specific Item's sub-items.</span></span>
  

|<span data-ttu-id="3402e-112">**Méthode**</span><span class="sxs-lookup"><span data-stu-id="3402e-112">**Method**</span></span>|<span data-ttu-id="3402e-113">**URI de la demande**</span><span class="sxs-lookup"><span data-stu-id="3402e-113">**Request URI**</span></span>|<span data-ttu-id="3402e-114">**Version HTTP**</span><span class="sxs-lookup"><span data-stu-id="3402e-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="3402e-115">Télécharger</span><span class="sxs-lookup"><span data-stu-id="3402e-115">GET</span></span>  <br/> |<span data-ttu-id="3402e-116">https://\<portal\>/QoERepositoryService/référentiel/élément / {itemId} / sous-éléments</span><span class="sxs-lookup"><span data-stu-id="3402e-116">https://\<portal\>/QoERepositoryService/repository/item/{itemId}/subitem</span></span>  <br/> |<span data-ttu-id="3402e-117">HTTP/1.1.</span><span class="sxs-lookup"><span data-stu-id="3402e-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="3402e-118">**Paramètres d’URI** - None.</span><span class="sxs-lookup"><span data-stu-id="3402e-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="3402e-119">**En-têtes de demande** - aucun en-tête supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="3402e-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="3402e-120">**Corps de requête** - None.</span><span class="sxs-lookup"><span data-stu-id="3402e-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="3402e-121">**Réponse** - la réponse inclut un code d’état HTTP et un ensemble d’en-têtes de réponse.</span><span class="sxs-lookup"><span data-stu-id="3402e-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="3402e-122">**Code d’état** - une opération réussie retourne un code d’état 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="3402e-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span> <span data-ttu-id="3402e-123">Si un utilisateur spécifié QU'ID est introuvable, elle renvoie le code d’état 404 (introuvable).</span><span class="sxs-lookup"><span data-stu-id="3402e-123">If a specified user ID is not found, it returns status code 404 (Not Found).</span></span>
  
 <span data-ttu-id="3402e-124">**En-têtes de réponse** - aucun en-tête supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="3402e-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="3402e-125">**Corps de réponse** - vous trouverez ci-dessous une charge utile d’exemple réponse au format JSON.</span><span class="sxs-lookup"><span data-stu-id="3402e-125">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
> [!NOTE]
> <span data-ttu-id="3402e-126">Un tableau de l’objet Item est renvoyé.</span><span class="sxs-lookup"><span data-stu-id="3402e-126">An array of Item object is returned.</span></span> 
  
```
[{
"itemId": 1653,
"userId": 0,
"type": "application/json"
},
{
"itemId": 1710,
"userId": 0,
"type": "json"
}]
```

<span data-ttu-id="3402e-127">L’objet renvoyé par opération sous-éléments contient uniquement les trois champs suivants.</span><span class="sxs-lookup"><span data-stu-id="3402e-127">The Item object returned by Sub-Items operation only contains the following three fields.</span></span> 
  
 <span data-ttu-id="3402e-128">*itemId* - ID de l’élément.</span><span class="sxs-lookup"><span data-stu-id="3402e-128">*itemId*  - ID of the item.</span></span>
  
 <span data-ttu-id="3402e-129">*userId* - ID de l’utilisateur qui possède cet article.</span><span class="sxs-lookup"><span data-stu-id="3402e-129">*userId*  - ID of the User who owns this Item.</span></span>
  
 <span data-ttu-id="3402e-130">*type* : le type de contenu.</span><span class="sxs-lookup"><span data-stu-id="3402e-130">*type*  - The type of the content.</span></span> <span data-ttu-id="3402e-131">Ce champ est défini par les applications.</span><span class="sxs-lookup"><span data-stu-id="3402e-131">This field is set by the applications.</span></span>
  
> [!NOTE]
>  <span data-ttu-id="3402e-132">`Content`et `subItems` champs ne sont pas inclus dans la réponse afin de réduire la quantité de données transmises via le réseau.</span><span class="sxs-lookup"><span data-stu-id="3402e-132">`Content` and `subItems` fields are not included in the response to reduce the amount of data transmitted over the network.</span></span>
  

