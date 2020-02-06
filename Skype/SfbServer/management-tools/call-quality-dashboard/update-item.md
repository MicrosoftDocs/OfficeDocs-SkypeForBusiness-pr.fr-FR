---
title: Mettre à jour un élément
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
ms.assetid: b1c15c56-cdae-4f3e-838a-52f0940cf729
description: 'Résumé : Découvrez l’opération de mise à jour des éléments, qui fait partie du service d’élément. Le service d’élément fait partie de l’API du référentiel pour le tableau de bord de qualité des appels. Le tableau de bord de qualité des appels est un outil pour Skype entreprise Server.'
ms.openlocfilehash: 460e6b26375bba28887d170c9827864bfc600138
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816673"
---
# <a name="update-item"></a><span data-ttu-id="de280-105">Mettre à jour un élément</span><span class="sxs-lookup"><span data-stu-id="de280-105">Update Item</span></span>
 
<span data-ttu-id="de280-106">**Résumé :** En savoir plus sur l’opération de mise à jour des éléments, qui fait partie de l’élément service.</span><span class="sxs-lookup"><span data-stu-id="de280-106">**Summary:** Learn about the Update Item operation, which is part of the Item Service.</span></span> <span data-ttu-id="de280-107">Le service d’élément fait partie de l’API du référentiel pour le tableau de bord de qualité des appels.</span><span class="sxs-lookup"><span data-stu-id="de280-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="de280-108">Le tableau de bord de qualité des appels est un outil pour Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="de280-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="de280-109">L’opération de mise à jour des éléments fait partie du service d’élément dans l’API du référentiel pour le tableau de bord de qualité des appels.</span><span class="sxs-lookup"><span data-stu-id="de280-109">The Update Item operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="update-item"></a><span data-ttu-id="de280-110">Mettre à jour un élément</span><span class="sxs-lookup"><span data-stu-id="de280-110">Update Item</span></span>

<span data-ttu-id="de280-111">Mettre à jour l’élément met à jour un élément spécifique du référentiel.</span><span class="sxs-lookup"><span data-stu-id="de280-111">Update Item updates a specific item in the repository.</span></span>
  

|<span data-ttu-id="de280-112">**Méthode**</span><span class="sxs-lookup"><span data-stu-id="de280-112">**Method**</span></span>|<span data-ttu-id="de280-113">**URI de la requête**</span><span class="sxs-lookup"><span data-stu-id="de280-113">**Request URI**</span></span>|<span data-ttu-id="de280-114">**Version HTTP**</span><span class="sxs-lookup"><span data-stu-id="de280-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="de280-115">PORT</span><span class="sxs-lookup"><span data-stu-id="de280-115">PUT</span></span>  <br/> |<span data-ttu-id="de280-116">https://\<Portal\>/QoERepositoryService/Repository/Item/{ItemId}</span><span class="sxs-lookup"><span data-stu-id="de280-116">https://\<portal\>/QoERepositoryService/repository/item/{itemId}</span></span>  <br/> |<span data-ttu-id="de280-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="de280-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="de280-118">**Paramètres d’URI** -aucun.</span><span class="sxs-lookup"><span data-stu-id="de280-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="de280-119">**En-têtes de requête** -type de contenu : application/JSON.</span><span class="sxs-lookup"><span data-stu-id="de280-119">**Request Headers** -Content-Type: application/json.</span></span>
  
 <span data-ttu-id="de280-120">**Demander le corps** JSON.</span><span class="sxs-lookup"><span data-stu-id="de280-120">**Request Body** - JSON.</span></span>
  
<span data-ttu-id="de280-121">Exemple de charge utile de requête :</span><span class="sxs-lookup"><span data-stu-id="de280-121">Sample request payload:</span></span>
  
```json
{
  content : "{ 'Product' : 'New Product Name'",
  type: "application/json"
}
```

 <span data-ttu-id="de280-122">*content (contenu* )  Les données au format JSON doivent être stockées en tant que nouveau contenu d’un sous-élément existant.</span><span class="sxs-lookup"><span data-stu-id="de280-122">*content*  JSON formatted data to be stored as the new content of an existing sub-Item.</span></span> <span data-ttu-id="de280-123">Techniquement, un référentiel peut stocker tout contenu de tout schéma, mais lorsqu’il est utilisé pour le tableau de bord de qualité des appels, il doit s’agir d’un État ou d’une requête.</span><span class="sxs-lookup"><span data-stu-id="de280-123">Technically, a repository can store any content of any schema, but when used for Call Quality Dashboard, it should be either a report or a query.</span></span> <span data-ttu-id="de280-124">*taper*  Spécifiez toujours « application/JSON » pour le tableau de bord de qualité des appels.</span><span class="sxs-lookup"><span data-stu-id="de280-124">*type*  Always specify "application/json" for Call Quality Dashboard.</span></span>
  
 <span data-ttu-id="de280-125">**Réponse** : la réponse comprend un code d’État http et un ensemble d’en-têtes de réponse.</span><span class="sxs-lookup"><span data-stu-id="de280-125">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="de280-126">**Code d’État** -une opération réussie renvoie le code d’État 204 (sans contenu).</span><span class="sxs-lookup"><span data-stu-id="de280-126">**Status Code** - A successful operation returns status code 204 (No Content).</span></span> <span data-ttu-id="de280-127">Si aucun ID d’élément spécifié n’est trouvé, il renvoie le code d’État 404 (introuvable).</span><span class="sxs-lookup"><span data-stu-id="de280-127">If a specified item ID is not found, it returns status code 404 (Not Found).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="de280-128">Le message « aucun contenu » n’est pas un état d’erreur.</span><span class="sxs-lookup"><span data-stu-id="de280-128">"No Content" is not an error status.</span></span> <span data-ttu-id="de280-129">Cela signifie que la réponse n’a rien retourné dans le corps (en revanche, 200 OK renvoie du contenu dans corps).</span><span class="sxs-lookup"><span data-stu-id="de280-129">It means that a response did not return anything in the body (in contrast, 200 OK returns content in Body).</span></span> <span data-ttu-id="de280-130">Le message indiquant que l’élément a été correctement mis à jour s’affiche.</span><span class="sxs-lookup"><span data-stu-id="de280-130">It indicates that the Item was successfully updated.</span></span> 
  
 <span data-ttu-id="de280-131">**En-têtes de réponse** -aucun.</span><span class="sxs-lookup"><span data-stu-id="de280-131">**Response Headers** - None.</span></span>
  
 <span data-ttu-id="de280-132">**Corps** de la réponse : aucun.</span><span class="sxs-lookup"><span data-stu-id="de280-132">**Response Body** - None.</span></span>
  

