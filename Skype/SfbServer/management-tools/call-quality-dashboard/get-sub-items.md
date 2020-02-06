---
title: Obtenir des sous-éléments
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
ms.assetid: 0542eba9-3dda-40de-bba8-095d22825e4e
description: 'Résumé : Découvrez l’opération obtenir les sous-éléments, qui fait partie du service d’éléments. Le service d’élément fait partie de l’API du référentiel pour le tableau de bord de qualité des appels. Le tableau de bord de qualité des appels est un outil pour Skype entreprise Server.'
ms.openlocfilehash: 523a6050065680550685337dabfec72c87f30bf7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816763"
---
# <a name="get-sub-items"></a><span data-ttu-id="15d1e-105">Obtenir des sous-éléments</span><span class="sxs-lookup"><span data-stu-id="15d1e-105">Get Sub-Items</span></span>
 
<span data-ttu-id="15d1e-106">**Résumé :** En savoir plus sur l’opération obtenir les sous-éléments, qui fait partie du service d’élément.</span><span class="sxs-lookup"><span data-stu-id="15d1e-106">**Summary:** Learn about the Get Sub-Items operation, which is part of the Item Service.</span></span> <span data-ttu-id="15d1e-107">Le service d’élément fait partie de l’API du référentiel pour le tableau de bord de qualité des appels.</span><span class="sxs-lookup"><span data-stu-id="15d1e-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="15d1e-108">Le tableau de bord de qualité des appels est un outil pour Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="15d1e-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="15d1e-109">L’opération obtenir des sous-éléments fait partie du service d’élément dans l’API du référentiel pour le tableau de bord de qualité des appels.</span><span class="sxs-lookup"><span data-stu-id="15d1e-109">The Get Sub-Items operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-sub-items"></a><span data-ttu-id="15d1e-110">Obtenir des sous-éléments</span><span class="sxs-lookup"><span data-stu-id="15d1e-110">Get Sub-Items</span></span>

<span data-ttu-id="15d1e-111">L’option obtenir des sous-éléments renvoie les sous-éléments d’un élément spécifiques.</span><span class="sxs-lookup"><span data-stu-id="15d1e-111">Get Sub-Items returns a specific Item's sub-items.</span></span>
  

|<span data-ttu-id="15d1e-112">**Méthode**</span><span class="sxs-lookup"><span data-stu-id="15d1e-112">**Method**</span></span>|<span data-ttu-id="15d1e-113">**URI de la requête**</span><span class="sxs-lookup"><span data-stu-id="15d1e-113">**Request URI**</span></span>|<span data-ttu-id="15d1e-114">**Version HTTP**</span><span class="sxs-lookup"><span data-stu-id="15d1e-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="15d1e-115">Télécharger</span><span class="sxs-lookup"><span data-stu-id="15d1e-115">GET</span></span>  <br/> |<span data-ttu-id="15d1e-116">https://\<Portal\>/QoERepositoryService/Repository/Item/{ItemId}/SubItem</span><span class="sxs-lookup"><span data-stu-id="15d1e-116">https://\<portal\>/QoERepositoryService/repository/item/{itemId}/subitem</span></span>  <br/> |<span data-ttu-id="15d1e-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="15d1e-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="15d1e-118">**Paramètres d’URI** -aucun.</span><span class="sxs-lookup"><span data-stu-id="15d1e-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="15d1e-119">**En-têtes de requête** -aucun en-tête supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="15d1e-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="15d1e-120">Le corps de la **requête** .</span><span class="sxs-lookup"><span data-stu-id="15d1e-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="15d1e-121">**Réponse** : la réponse comprend un code d’État http et un ensemble d’en-têtes de réponse.</span><span class="sxs-lookup"><span data-stu-id="15d1e-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="15d1e-122">**Code d’État** -une opération réussie renvoie le code d’état 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="15d1e-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span> <span data-ttu-id="15d1e-123">Si vous n’avez pas trouvé d’ID utilisateur spécifié, le code d’État 404 (introuvable) est renvoyé.</span><span class="sxs-lookup"><span data-stu-id="15d1e-123">If a specified user ID is not found, it returns status code 404 (Not Found).</span></span>
  
 <span data-ttu-id="15d1e-124">**En-têtes de réponse** : aucun en-tête supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="15d1e-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="15d1e-125">Le corps de la **réponse** : Voici un exemple de charge utile de réponse dans JSON.</span><span class="sxs-lookup"><span data-stu-id="15d1e-125">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
> [!NOTE]
> <span data-ttu-id="15d1e-126">Un tableau d’objet Item est retourné.</span><span class="sxs-lookup"><span data-stu-id="15d1e-126">An array of Item object is returned.</span></span> 
  
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

<span data-ttu-id="15d1e-127">L’objet Item renvoyé par une opération de sous-éléments contient uniquement les trois champs suivants.</span><span class="sxs-lookup"><span data-stu-id="15d1e-127">The Item object returned by Sub-Items operation only contains the following three fields.</span></span> 
  
 <span data-ttu-id="15d1e-128">ID *de l'* élément.</span><span class="sxs-lookup"><span data-stu-id="15d1e-128">*itemId*  - ID of the item.</span></span>
  
 <span data-ttu-id="15d1e-129">ID *d’utilisateur de* l’utilisateur propriétaire de cet élément.</span><span class="sxs-lookup"><span data-stu-id="15d1e-129">*userId*  - ID of the User who owns this Item.</span></span>
  
 <span data-ttu-id="15d1e-130">*tapez* le type du contenu.</span><span class="sxs-lookup"><span data-stu-id="15d1e-130">*type*  - The type of the content.</span></span> <span data-ttu-id="15d1e-131">Ce champ est défini par les applications.</span><span class="sxs-lookup"><span data-stu-id="15d1e-131">This field is set by the applications.</span></span>
  
> [!NOTE]
>  <span data-ttu-id="15d1e-132">`Content`et `subItems` les champs ne sont pas inclus dans la réponse afin de réduire la quantité de données transmises sur le réseau.</span><span class="sxs-lookup"><span data-stu-id="15d1e-132">`Content` and `subItems` fields are not included in the response to reduce the amount of data transmitted over the network.</span></span>
  

