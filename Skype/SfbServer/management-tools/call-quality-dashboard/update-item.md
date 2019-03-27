---
title: Mettre à jour un élément
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b1c15c56-cdae-4f3e-838a-52f0940cf729
description: 'Résumé : Découvrez l’opération élément mise à jour, qui fait partie du Service de l’élément. Le Service de l’élément fait partie de l’API de référentiel pour appeler le tableau de bord qualité. Tableau de bord de qualité des appels est un outil de Skype pour Business Server.'
ms.openlocfilehash: 3ac56b8761f565663ffaa689c666e285b2347ed5
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30887948"
---
# <a name="update-item"></a><span data-ttu-id="320a8-105">Mettre à jour un élément</span><span class="sxs-lookup"><span data-stu-id="320a8-105">Update Item</span></span>
 
<span data-ttu-id="320a8-106">**Résumé :** Obtenir des informations sur l’opération élément mise à jour, qui fait partie du Service de l’élément.</span><span class="sxs-lookup"><span data-stu-id="320a8-106">**Summary:** Learn about the Update Item operation, which is part of the Item Service.</span></span> <span data-ttu-id="320a8-107">Le Service de l’élément fait partie de l’API de référentiel pour appeler le tableau de bord qualité.</span><span class="sxs-lookup"><span data-stu-id="320a8-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="320a8-108">Tableau de bord de qualité des appels est un outil de Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="320a8-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="320a8-109">L’opération de mise à jour élément fait partie du Service d’élément dans l’API de référentiel pour appeler le tableau de bord qualité.</span><span class="sxs-lookup"><span data-stu-id="320a8-109">The Update Item operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="update-item"></a><span data-ttu-id="320a8-110">Mettre à jour un élément</span><span class="sxs-lookup"><span data-stu-id="320a8-110">Update Item</span></span>

<span data-ttu-id="320a8-111">Élément de la mise à jour met à jour un élément spécifique dans le référentiel.</span><span class="sxs-lookup"><span data-stu-id="320a8-111">Update Item updates a specific item in the repository.</span></span>
  

|<span data-ttu-id="320a8-112">**Méthode**</span><span class="sxs-lookup"><span data-stu-id="320a8-112">**Method**</span></span>|<span data-ttu-id="320a8-113">**URI de la demande**</span><span class="sxs-lookup"><span data-stu-id="320a8-113">**Request URI**</span></span>|<span data-ttu-id="320a8-114">**Version HTTP**</span><span class="sxs-lookup"><span data-stu-id="320a8-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="320a8-115">PUT</span><span class="sxs-lookup"><span data-stu-id="320a8-115">PUT</span></span>  <br/> |<span data-ttu-id="320a8-116">https://\<portal\>/QoERepositoryService/référentiel/élément / {itemId}</span><span class="sxs-lookup"><span data-stu-id="320a8-116">https://\<portal\>/QoERepositoryService/repository/item/{itemId}</span></span>  <br/> |<span data-ttu-id="320a8-117">HTTP/1.1.</span><span class="sxs-lookup"><span data-stu-id="320a8-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="320a8-118">**Paramètres d’URI** - None.</span><span class="sxs-lookup"><span data-stu-id="320a8-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="320a8-119">**En-têtes de demande** -Content-Type : application/json.</span><span class="sxs-lookup"><span data-stu-id="320a8-119">**Request Headers** -Content-Type: application/json.</span></span>
  
 <span data-ttu-id="320a8-120">**Corps de requête** - JSON.</span><span class="sxs-lookup"><span data-stu-id="320a8-120">**Request Body** - JSON.</span></span>
  
<span data-ttu-id="320a8-121">Charge utile de demande exemple :</span><span class="sxs-lookup"><span data-stu-id="320a8-121">Sample request payload:</span></span>
  
```
{
  content : "{ 'Product' : 'New Product Name'",
  type: "application/json"
}
```

 <span data-ttu-id="320a8-122">*contenu*  JSON mise en forme des données sont stockées en tant que le nouveau contenu d’un élément existant de sous-sites.</span><span class="sxs-lookup"><span data-stu-id="320a8-122">*content*  JSON formatted data to be stored as the new content of an existing sub-Item.</span></span> <span data-ttu-id="320a8-123">Techniquement, un référentiel peut stocker le contenu d’un schéma, mais lorsqu’il est utilisé pour appeler le tableau de bord qualité, il doit être un rapport ou une requête.</span><span class="sxs-lookup"><span data-stu-id="320a8-123">Technically, a repository can store any content of any schema, but when used for Call Quality Dashboard, it should be either a report or a query.</span></span> <span data-ttu-id="320a8-124">*type*  Toujours spécifier « application/json » pour appeler le tableau de bord qualité.</span><span class="sxs-lookup"><span data-stu-id="320a8-124">*type*  Always specify "application/json" for Call Quality Dashboard.</span></span>
  
 <span data-ttu-id="320a8-125">**Réponse** - la réponse inclut un code d’état HTTP et un ensemble d’en-têtes de réponse.</span><span class="sxs-lookup"><span data-stu-id="320a8-125">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="320a8-126">**Code d’état** - une opération réussie renvoie le code d’état 204 (sans contenu).</span><span class="sxs-lookup"><span data-stu-id="320a8-126">**Status Code** - A successful operation returns status code 204 (No Content).</span></span> <span data-ttu-id="320a8-127">Si un ID de l’élément spécifié est introuvable, elle renvoie le code d’état 404 (introuvable).</span><span class="sxs-lookup"><span data-stu-id="320a8-127">If a specified item ID is not found, it returns status code 404 (Not Found).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="320a8-128">« Aucun contenu » n’est pas un état d’erreur.</span><span class="sxs-lookup"><span data-stu-id="320a8-128">"No Content" is not an error status.</span></span> <span data-ttu-id="320a8-129">Cela signifie qu’une réponse n’a pas renvoyé rien dans le corps (à l’inverse, 200 renvoie OK contenus dans le corps).</span><span class="sxs-lookup"><span data-stu-id="320a8-129">It means that a response did not return anything in the body (in contrast, 200 OK returns content in Body).</span></span> <span data-ttu-id="320a8-130">Il indique que l’élément a été correctement mis à jour.</span><span class="sxs-lookup"><span data-stu-id="320a8-130">It indicates that the Item was successfully updated.</span></span> 
  
 <span data-ttu-id="320a8-131">**En-têtes de réponse** - None.</span><span class="sxs-lookup"><span data-stu-id="320a8-131">**Response Headers** - None.</span></span>
  
 <span data-ttu-id="320a8-132">**Corps de réponse** - None.</span><span class="sxs-lookup"><span data-stu-id="320a8-132">**Response Body** - None.</span></span>
  

