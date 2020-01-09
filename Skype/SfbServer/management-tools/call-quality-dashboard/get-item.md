---
title: Obtenir un élément
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: e77bf649-d62a-4d94-80de-066ba47730cd
description: 'Résumé : en savoir plus sur l’opération obtenir un élément qui fait partie du service d’article. Le service d’élément fait partie de l’API du référentiel pour le tableau de bord de qualité des appels. Le tableau de bord de qualité des appels est un outil pour Skype entreprise Server.'
ms.openlocfilehash: 208ad3d1852ab58b7fcd0d01eeb440097328f733
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992671"
---
# <a name="get-item"></a><span data-ttu-id="3651b-105">Obtenir un élément</span><span class="sxs-lookup"><span data-stu-id="3651b-105">Get Item</span></span>
 
<span data-ttu-id="3651b-106">**Résumé :** En savoir plus sur l’opération obtenir l’élément, qui fait partie du service d’élément.</span><span class="sxs-lookup"><span data-stu-id="3651b-106">**Summary:** Learn about the Get Item operation, which is part of the Item Service.</span></span> <span data-ttu-id="3651b-107">Le service d’élément fait partie de l’API du référentiel pour le tableau de bord de qualité des appels.</span><span class="sxs-lookup"><span data-stu-id="3651b-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="3651b-108">Le tableau de bord de qualité des appels est un outil pour Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="3651b-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="3651b-109">L’opération obtenir l’élément fait partie du service d’élément dans l’API du référentiel pour le tableau de bord de qualité des appels.</span><span class="sxs-lookup"><span data-stu-id="3651b-109">The Get Item operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-item"></a><span data-ttu-id="3651b-110">Obtenir un élément</span><span class="sxs-lookup"><span data-stu-id="3651b-110">Get Item</span></span>

<span data-ttu-id="3651b-111">Obtient l’élément renvoie un élément spécifique du référentiel.</span><span class="sxs-lookup"><span data-stu-id="3651b-111">Get Item returns a specific item in the repository.</span></span>
  
|<span data-ttu-id="3651b-112">**Méthode**</span><span class="sxs-lookup"><span data-stu-id="3651b-112">**Method**</span></span>|<span data-ttu-id="3651b-113">**URI de la requête**</span><span class="sxs-lookup"><span data-stu-id="3651b-113">**Request URI**</span></span>|<span data-ttu-id="3651b-114">**Version HTTP**</span><span class="sxs-lookup"><span data-stu-id="3651b-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="3651b-115">Télécharger</span><span class="sxs-lookup"><span data-stu-id="3651b-115">GET</span></span>  <br/> |<span data-ttu-id="3651b-116">https://\<Portal\>/QoERepositoryService/Repository/Item/{ItemId}</span><span class="sxs-lookup"><span data-stu-id="3651b-116">https://\<portal\>/QoERepositoryService/repository/item/{itemId}</span></span>  <br/> |<span data-ttu-id="3651b-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="3651b-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="3651b-118">**Paramètres d’URI** -aucun.</span><span class="sxs-lookup"><span data-stu-id="3651b-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="3651b-119">**En-têtes de requête** -aucun en-tête supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="3651b-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="3651b-120">Le corps de la **requête** .</span><span class="sxs-lookup"><span data-stu-id="3651b-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="3651b-121">**Réponse** : la réponse comprend un code d’État http et un ensemble d’en-têtes de réponse.</span><span class="sxs-lookup"><span data-stu-id="3651b-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="3651b-122">**Code d’État** -une opération réussie renvoie le code d’état 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="3651b-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span> <span data-ttu-id="3651b-123">Si aucun ID d’élément spécifié n’est trouvé, il renvoie le code d’État 404 (introuvable).</span><span class="sxs-lookup"><span data-stu-id="3651b-123">If a specified item ID is not found, it returns status code 404 (Not Found).</span></span>
  
 <span data-ttu-id="3651b-124">**En-têtes de réponse** : aucun en-tête supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="3651b-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="3651b-125">Le corps de la **réponse** : Voici un exemple de charge utile de réponse dans JSON.</span><span class="sxs-lookup"><span data-stu-id="3651b-125">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
```json
{
"itemId": 1652,
"userId": 0,
"content": "{\"Title\":\"All Audio Streams\",...}",
"type": "application/json",
"subItemIds": [1653, 1710]
}
```

 <span data-ttu-id="3651b-126">ID *de l'* élément.</span><span class="sxs-lookup"><span data-stu-id="3651b-126">*itemId*  - ID of the item.</span></span>
  
 <span data-ttu-id="3651b-127">ID *d’utilisateur de* l’utilisateur propriétaire de cet élément.</span><span class="sxs-lookup"><span data-stu-id="3651b-127">*userId*  - ID of the user who owns this item.</span></span>
  
 <span data-ttu-id="3651b-128">*content* : contenu spécifique à l’application.</span><span class="sxs-lookup"><span data-stu-id="3651b-128">*content*  - The application-specific content.</span></span>
  
 <span data-ttu-id="3651b-129">*tapez* le type du contenu.</span><span class="sxs-lookup"><span data-stu-id="3651b-129">*type*  - The type of the content.</span></span> <span data-ttu-id="3651b-130">Ce champ est défini par les applications.</span><span class="sxs-lookup"><span data-stu-id="3651b-130">This field is set by the applications.</span></span>
  
 <span data-ttu-id="3651b-131">*subItemIds* -ID des sous-éléments, le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="3651b-131">*subItemIds*  - The IDs of sub-Items, if any.</span></span> <span data-ttu-id="3651b-132">Il s’agit d’un court-circuit d’opération de commande de sous-éléments permettant d’enregistrer un appel.</span><span class="sxs-lookup"><span data-stu-id="3651b-132">This is a short-circuit of Get Sub-Items operation to save a call.</span></span> <span data-ttu-id="3651b-133">Les applications peuvent également obtenir les mêmes informations à l’aide de l’opération utiliser les sous-éléments.</span><span class="sxs-lookup"><span data-stu-id="3651b-133">Applications can alternatively obtain the same information using Get Sub-Items operation.</span></span>
  

