---
title: Obtenir des sous-éléments
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
ms.assetid: 0542eba9-3dda-40de-bba8-095d22825e4e
description: 'Résumé : Découvrez l’opération Get Sub-Items, qui fait partie du service d’élément. Le service d’élément fait partie de l’API de référentiel pour le tableau de bord de qualité des appels. Le Tableau de bord de qualité des appels est un outil pour Skype Entreprise Server.'
ms.openlocfilehash: defb0b898c5101513cbb4f6da4382a8bb43bce6e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832504"
---
# <a name="get-sub-items"></a><span data-ttu-id="0816f-105">Obtenir des sous-éléments</span><span class="sxs-lookup"><span data-stu-id="0816f-105">Get Sub-Items</span></span>
 
<span data-ttu-id="0816f-106">**Résumé :** Découvrez l’opération Get Sub-Items, qui fait partie du service d’élément.</span><span class="sxs-lookup"><span data-stu-id="0816f-106">**Summary:** Learn about the Get Sub-Items operation, which is part of the Item Service.</span></span> <span data-ttu-id="0816f-107">Le service d’élément fait partie de l’API de référentiel pour le tableau de bord de qualité des appels.</span><span class="sxs-lookup"><span data-stu-id="0816f-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="0816f-108">Le Tableau de bord de qualité des appels est un outil pour Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="0816f-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="0816f-109">L’opération Get Sub-Items fait partie du service d’élément dans l’API référentiel pour le tableau de bord de qualité des appels.</span><span class="sxs-lookup"><span data-stu-id="0816f-109">The Get Sub-Items operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-sub-items"></a><span data-ttu-id="0816f-110">Obtenir des sous-éléments</span><span class="sxs-lookup"><span data-stu-id="0816f-110">Get Sub-Items</span></span>

<span data-ttu-id="0816f-111">Obtenir Sub-Items renvoie les sous-éléments d’un élément spécifique.</span><span class="sxs-lookup"><span data-stu-id="0816f-111">Get Sub-Items returns a specific Item's sub-items.</span></span>
  

|<span data-ttu-id="0816f-112">**Méthode**</span><span class="sxs-lookup"><span data-stu-id="0816f-112">**Method**</span></span>|<span data-ttu-id="0816f-113">**URI de demande**</span><span class="sxs-lookup"><span data-stu-id="0816f-113">**Request URI**</span></span>|<span data-ttu-id="0816f-114">**HTTP Version**</span><span class="sxs-lookup"><span data-stu-id="0816f-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="0816f-115">GET</span><span class="sxs-lookup"><span data-stu-id="0816f-115">GET</span></span>  <br/> |<span data-ttu-id="0816f-116">https:// \<portal\> /QoERepositoryService/repository/item/{itemId}/fairem</span><span class="sxs-lookup"><span data-stu-id="0816f-116">https://\<portal\>/QoERepositoryService/repository/item/{itemId}/subitem</span></span>  <br/> |<span data-ttu-id="0816f-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="0816f-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="0816f-118">**Paramètres d’URI** - Aucun.</span><span class="sxs-lookup"><span data-stu-id="0816f-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="0816f-119">**En-têtes de requête** : aucun en-tête supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="0816f-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="0816f-120">**Corps de la** demande - Aucun.</span><span class="sxs-lookup"><span data-stu-id="0816f-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="0816f-121">**Réponse** : la réponse inclut un code d’état HTTP et un ensemble d’en-têtes de réponse.</span><span class="sxs-lookup"><span data-stu-id="0816f-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="0816f-122">**Code d’état** : une opération réussie renvoie le code d’état 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="0816f-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span> <span data-ttu-id="0816f-123">Si un ID utilisateur spécifié est in trouvé, il renvoie le code d’état 404 (In trouvé).</span><span class="sxs-lookup"><span data-stu-id="0816f-123">If a specified user ID is not found, it returns status code 404 (Not Found).</span></span>
  
 <span data-ttu-id="0816f-124">**En-têtes de réponse** : aucun en-tête supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="0816f-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="0816f-125">**Corps de la** réponse : voici un exemple de charge utile de réponse dans JSON.</span><span class="sxs-lookup"><span data-stu-id="0816f-125">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0816f-126">Un tableau d’objets Item est renvoyé.</span><span class="sxs-lookup"><span data-stu-id="0816f-126">An array of Item object is returned.</span></span> 
  
```json
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

<span data-ttu-id="0816f-127">L’objet Item renvoyé par Sub-Items opération contient uniquement les trois champs suivants.</span><span class="sxs-lookup"><span data-stu-id="0816f-127">The Item object returned by Sub-Items operation only contains the following three fields.</span></span> 
  
 <span data-ttu-id="0816f-128">*itemId*  : ID de l’élément.</span><span class="sxs-lookup"><span data-stu-id="0816f-128">*itemId*  - ID of the item.</span></span>
  
 <span data-ttu-id="0816f-129">*userId*  - ID de l’utilisateur propriétaire de cet élément.</span><span class="sxs-lookup"><span data-stu-id="0816f-129">*userId*  - ID of the User who owns this Item.</span></span>
  
 <span data-ttu-id="0816f-130">*type*  : type du contenu.</span><span class="sxs-lookup"><span data-stu-id="0816f-130">*type*  - The type of the content.</span></span> <span data-ttu-id="0816f-131">Ce champ est définie par les applications.</span><span class="sxs-lookup"><span data-stu-id="0816f-131">This field is set by the applications.</span></span>
  
> [!NOTE]
>  <span data-ttu-id="0816f-132">`Content` et les champs ne sont pas inclus dans la réponse pour réduire la quantité de données `subItems` transmises sur le réseau.</span><span class="sxs-lookup"><span data-stu-id="0816f-132">`Content` and `subItems` fields are not included in the response to reduce the amount of data transmitted over the network.</span></span>
  

