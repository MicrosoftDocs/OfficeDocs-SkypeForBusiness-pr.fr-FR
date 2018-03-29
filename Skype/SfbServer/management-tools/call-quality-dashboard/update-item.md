---
title: Élément de mise à jour
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 6/8/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b1c15c56-cdae-4f3e-838a-52f0940cf729
description: 'Résumé : Découvrez l’opération de l’élément de mise à jour, qui fait partie de l’article de Service. L’article de Service fait partie de l’API de référentiel pour appeler le tableau de bord qualité. Tableau de bord qualité appel est un outil de Skype pour Business Server 2015.'
ms.openlocfilehash: 04a0ebf29537bbc2e62e6d5b35008fe9e329ab4f
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="update-item"></a><span data-ttu-id="0faea-105">Élément de mise à jour</span><span class="sxs-lookup"><span data-stu-id="0faea-105">Update Item</span></span>
 
<span data-ttu-id="0faea-106">**Résumé :** Obtenir des informations sur l’opération de l’élément de mise à jour, qui fait partie de l’article de Service.</span><span class="sxs-lookup"><span data-stu-id="0faea-106">**Summary:** Learn about the Update Item operation, which is part of the Item Service.</span></span> <span data-ttu-id="0faea-107">L’article de Service fait partie de l’API de référentiel pour appeler le tableau de bord qualité.</span><span class="sxs-lookup"><span data-stu-id="0faea-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="0faea-108">Tableau de bord qualité appel est un outil de Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="0faea-108">Call Quality Dashboard is a tool for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="0faea-109">L’opération de l’élément de mise à jour fait partie de l’article Service dans l’API de référentiel pour appeler le tableau de bord qualité.</span><span class="sxs-lookup"><span data-stu-id="0faea-109">The Update Item operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="update-item"></a><span data-ttu-id="0faea-110">Élément de mise à jour</span><span class="sxs-lookup"><span data-stu-id="0faea-110">Update Item</span></span>

<span data-ttu-id="0faea-111">Élément de mise à jour met à jour un élément spécifique dans le référentiel.</span><span class="sxs-lookup"><span data-stu-id="0faea-111">Update Item updates a specific item in the repository.</span></span>
  

|<span data-ttu-id="0faea-112">**Méthode**</span><span class="sxs-lookup"><span data-stu-id="0faea-112">**Method**</span></span>|<span data-ttu-id="0faea-113">**URI de la demande**</span><span class="sxs-lookup"><span data-stu-id="0faea-113">**Request URI**</span></span>|<span data-ttu-id="0faea-114">**Version de HTTP**</span><span class="sxs-lookup"><span data-stu-id="0faea-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="0faea-115">PUT</span><span class="sxs-lookup"><span data-stu-id="0faea-115">PUT</span></span>  <br/> |<span data-ttu-id="0faea-116">https://\<portal\>/QoERepositoryService/repository/article / {itemId}</span><span class="sxs-lookup"><span data-stu-id="0faea-116">https://\<portal\>/QoERepositoryService/repository/item/{itemId}</span></span>  <br/> |<span data-ttu-id="0faea-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="0faea-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="0faea-118">**Les paramètres URI** - None.</span><span class="sxs-lookup"><span data-stu-id="0faea-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="0faea-119">**En-têtes de requête** -Content-Type : application/json.</span><span class="sxs-lookup"><span data-stu-id="0faea-119">**Request Headers** -Content-Type: application/json.</span></span>
  
 <span data-ttu-id="0faea-120">**Corps de requête** - JSON.</span><span class="sxs-lookup"><span data-stu-id="0faea-120">**Request Body** - JSON.</span></span>
  
<span data-ttu-id="0faea-121">Charge utile de demande exemple :</span><span class="sxs-lookup"><span data-stu-id="0faea-121">Sample request payload:</span></span>
  
```
{
  content : "{ 'Product' : 'New Product Name'",
  type: "application/json"
}
```

 <span data-ttu-id="0faea-122">*contenu*  JSON mis en forme les données à stocker en tant que le nouveau contenu d’un élément de sous-menu existant.</span><span class="sxs-lookup"><span data-stu-id="0faea-122">*content*  JSON formatted data to be stored as the new content of an existing sub-Item.</span></span> <span data-ttu-id="0faea-123">Techniquement, un référentiel peut stocker n’importe quel contenu de n’importe quel schéma, mais lorsqu’il est utilisé pour appeler le tableau de bord qualité, il doit être une requête ou un état.</span><span class="sxs-lookup"><span data-stu-id="0faea-123">Technically, a repository can store any content of any schema, but when used for Call Quality Dashboard, it should be either a report or a query.</span></span> <span data-ttu-id="0faea-124">*type de*  Spécifiez toujours « application/json » pour appeler le tableau de bord qualité.</span><span class="sxs-lookup"><span data-stu-id="0faea-124">*type*  Always specify "application/json" for Call Quality Dashboard.</span></span>
  
 <span data-ttu-id="0faea-125">**Réponse** : la réponse contient un code d’état HTTP et d’un ensemble d’en-têtes de réponse.</span><span class="sxs-lookup"><span data-stu-id="0faea-125">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="0faea-126">**Code d’état** - une opération réussie retourne un code d’état 204 (sans contenu).</span><span class="sxs-lookup"><span data-stu-id="0faea-126">**Status Code** - A successful operation returns status code 204 (No Content).</span></span> <span data-ttu-id="0faea-127">Si un ID de l’élément spécifié n’est pas trouvé, il renvoie le code d’état 404 (introuvable).</span><span class="sxs-lookup"><span data-stu-id="0faea-127">If a specified item ID is not found, it returns status code 404 (Not Found).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="0faea-128">« Aucun contenu » n’est pas un état d’erreur.</span><span class="sxs-lookup"><span data-stu-id="0faea-128">"No Content" is not an error status.</span></span> <span data-ttu-id="0faea-129">Cela signifie qu’une réponse n’a pas renvoyé quoi que ce soit dans le corps (à l’inverse, les contenus de 200 renvoie OK dans le corps).</span><span class="sxs-lookup"><span data-stu-id="0faea-129">It means that a response did not return anything in the body (in contrast, 200 OK returns content in Body).</span></span> <span data-ttu-id="0faea-130">Il indique que l’élément a été correctement mis à jour.</span><span class="sxs-lookup"><span data-stu-id="0faea-130">It indicates that the Item was successfully updated.</span></span> 
  
 <span data-ttu-id="0faea-131">**En-têtes de réponse** - None.</span><span class="sxs-lookup"><span data-stu-id="0faea-131">**Response Headers** - None.</span></span>
  
 <span data-ttu-id="0faea-132">**Corps de la réponse** - None.</span><span class="sxs-lookup"><span data-stu-id="0faea-132">**Response Body** - None.</span></span>
  

