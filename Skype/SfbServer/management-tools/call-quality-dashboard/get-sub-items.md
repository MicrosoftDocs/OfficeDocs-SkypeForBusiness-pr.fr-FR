---
title: Obtenir des éléments de sous-menu
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
description: 'Résumé : Découvrez l’opération obtenir les éléments de sous-menu, qui fait partie de l’article de Service. L’article de Service fait partie de l’API de référentiel pour appeler le tableau de bord qualité. Tableau de bord qualité appel est un outil de Skype pour Business Server 2015.'
ms.openlocfilehash: 8b9ec0c1c849e22f285ef1b5bbb2db806a153b76
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="get-sub-items"></a><span data-ttu-id="c2adc-105">Obtenir des éléments de sous-menu</span><span class="sxs-lookup"><span data-stu-id="c2adc-105">Get Sub-Items</span></span>
 
<span data-ttu-id="c2adc-106">**Résumé :** Obtenir des informations sur l’opération obtenir les éléments de sous-menu, qui fait partie de l’article de Service.</span><span class="sxs-lookup"><span data-stu-id="c2adc-106">**Summary:** Learn about the Get Sub-Items operation, which is part of the Item Service.</span></span> <span data-ttu-id="c2adc-107">L’article de Service fait partie de l’API de référentiel pour appeler le tableau de bord qualité.</span><span class="sxs-lookup"><span data-stu-id="c2adc-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="c2adc-108">Tableau de bord qualité appel est un outil de Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="c2adc-108">Call Quality Dashboard is a tool for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="c2adc-109">L’opération obtenir les sous-éléments fait partie de l’article Service dans l’API de référentiel pour appeler le tableau de bord qualité.</span><span class="sxs-lookup"><span data-stu-id="c2adc-109">The Get Sub-Items operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-sub-items"></a><span data-ttu-id="c2adc-110">Obtenir des éléments de sous-menu</span><span class="sxs-lookup"><span data-stu-id="c2adc-110">Get Sub-Items</span></span>

<span data-ttu-id="c2adc-111">Obtenir les sous-éléments retourne les sous-éléments d’un élément spécifique.</span><span class="sxs-lookup"><span data-stu-id="c2adc-111">Get Sub-Items returns a specific Item's sub-items.</span></span>
  

|<span data-ttu-id="c2adc-112">**Méthode**</span><span class="sxs-lookup"><span data-stu-id="c2adc-112">**Method**</span></span>|<span data-ttu-id="c2adc-113">**URI de la demande**</span><span class="sxs-lookup"><span data-stu-id="c2adc-113">**Request URI**</span></span>|<span data-ttu-id="c2adc-114">**Version de HTTP**</span><span class="sxs-lookup"><span data-stu-id="c2adc-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c2adc-115">Télécharger</span><span class="sxs-lookup"><span data-stu-id="c2adc-115">GET</span></span>  <br/> |<span data-ttu-id="c2adc-116">https://\<portal\>/QoERepositoryService/repository/article / {itemId} / de sous-éléments</span><span class="sxs-lookup"><span data-stu-id="c2adc-116">https://\<portal\>/QoERepositoryService/repository/item/{itemId}/subitem</span></span>  <br/> |<span data-ttu-id="c2adc-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="c2adc-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="c2adc-118">**Les paramètres URI** - None.</span><span class="sxs-lookup"><span data-stu-id="c2adc-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="c2adc-119">**En-têtes de requête** - aucun en-tête supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="c2adc-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="c2adc-120">**Corps de requête** - None.</span><span class="sxs-lookup"><span data-stu-id="c2adc-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="c2adc-121">**Réponse** : la réponse contient un code d’état HTTP et d’un ensemble d’en-têtes de réponse.</span><span class="sxs-lookup"><span data-stu-id="c2adc-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="c2adc-122">**Code d’état** - une opération réussie retourne un code d’état 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="c2adc-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span> <span data-ttu-id="c2adc-123">Si un utilisateur spécifié QU'ID n’est pas trouvé, il renvoie le code d’état 404 (introuvable).</span><span class="sxs-lookup"><span data-stu-id="c2adc-123">If a specified user ID is not found, it returns status code 404 (Not Found).</span></span>
  
 <span data-ttu-id="c2adc-124">**En-têtes de réponse** - aucun en-tête supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="c2adc-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="c2adc-125">**Corps de la réponse** - Voici une charge utile d’exemple réponse au format JSON.</span><span class="sxs-lookup"><span data-stu-id="c2adc-125">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c2adc-126">Un tableau d’élément objet est retourné.</span><span class="sxs-lookup"><span data-stu-id="c2adc-126">An array of Item object is returned.</span></span> 
  
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

<span data-ttu-id="c2adc-127">L’objet retourné par l’opération de sous-éléments ne contient que les trois champs suivants.</span><span class="sxs-lookup"><span data-stu-id="c2adc-127">The Item object returned by Sub-Items operation only contains the following three fields.</span></span> 
  
 <span data-ttu-id="c2adc-128">*itemId* - ID de l’élément.</span><span class="sxs-lookup"><span data-stu-id="c2adc-128">*itemId*  - ID of the item.</span></span>
  
 <span data-ttu-id="c2adc-129">*pseudo* - ID de l’utilisateur propriétaire de cet élément.</span><span class="sxs-lookup"><span data-stu-id="c2adc-129">*userId*  - ID of the User who owns this Item.</span></span>
  
 <span data-ttu-id="c2adc-130">*type* - le type de contenu.</span><span class="sxs-lookup"><span data-stu-id="c2adc-130">*type*  - The type of the content.</span></span> <span data-ttu-id="c2adc-131">Ce champ est défini par les applications.</span><span class="sxs-lookup"><span data-stu-id="c2adc-131">This field is set by the applications.</span></span>
  
> [!NOTE]
>  <span data-ttu-id="c2adc-132">`Content`et `subItems` champs ne sont pas inclus dans la réponse afin de réduire la quantité de données transmises sur le réseau.</span><span class="sxs-lookup"><span data-stu-id="c2adc-132">`Content` and `subItems` fields are not included in the response to reduce the amount of data transmitted over the network.</span></span>
  

