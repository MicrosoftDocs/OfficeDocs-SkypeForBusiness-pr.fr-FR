---
title: Mettre à jour un élément
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
ms.assetid: b1c15c56-cdae-4f3e-838a-52f0940cf729
description: 'Résumé : Découvrez l’opération Mettre à jour l’élément, qui fait partie du service d’élément. Le service d’élément fait partie de l’API de référentiel pour le tableau de bord de qualité des appels. Le Tableau de bord de qualité des appels est un outil pour Skype Entreprise Server.'
ms.openlocfilehash: 78da2fa414b4ba266f9e6aba4feac5ff73150062
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803084"
---
# <a name="update-item"></a><span data-ttu-id="d3605-105">Mettre à jour un élément</span><span class="sxs-lookup"><span data-stu-id="d3605-105">Update Item</span></span>
 
<span data-ttu-id="d3605-106">**Résumé :** Découvrez l’opération Mettre à jour l’élément, qui fait partie du service d’élément.</span><span class="sxs-lookup"><span data-stu-id="d3605-106">**Summary:** Learn about the Update Item operation, which is part of the Item Service.</span></span> <span data-ttu-id="d3605-107">Le service d’élément fait partie de l’API de référentiel pour le tableau de bord de qualité des appels.</span><span class="sxs-lookup"><span data-stu-id="d3605-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="d3605-108">Le Tableau de bord de qualité des appels est un outil pour Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="d3605-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="d3605-109">L’opération Mettre à jour un élément fait partie du service d’élément dans l’API de référentiel pour le tableau de bord de qualité des appels.</span><span class="sxs-lookup"><span data-stu-id="d3605-109">The Update Item operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="update-item"></a><span data-ttu-id="d3605-110">Mettre à jour un élément</span><span class="sxs-lookup"><span data-stu-id="d3605-110">Update Item</span></span>

<span data-ttu-id="d3605-111">L’élément de mise à jour met à jour un élément spécifique dans le référentiel.</span><span class="sxs-lookup"><span data-stu-id="d3605-111">Update Item updates a specific item in the repository.</span></span>
  

|<span data-ttu-id="d3605-112">**Méthode**</span><span class="sxs-lookup"><span data-stu-id="d3605-112">**Method**</span></span>|<span data-ttu-id="d3605-113">**URI de demande**</span><span class="sxs-lookup"><span data-stu-id="d3605-113">**Request URI**</span></span>|<span data-ttu-id="d3605-114">**HTTP Version**</span><span class="sxs-lookup"><span data-stu-id="d3605-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d3605-115">PUT</span><span class="sxs-lookup"><span data-stu-id="d3605-115">PUT</span></span>  <br/> |<span data-ttu-id="d3605-116">https:// \<portal\> /QoERepositoryService/repository/item/{itemId}</span><span class="sxs-lookup"><span data-stu-id="d3605-116">https://\<portal\>/QoERepositoryService/repository/item/{itemId}</span></span>  <br/> |<span data-ttu-id="d3605-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="d3605-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="d3605-118">**Paramètres d’URI** - Aucun.</span><span class="sxs-lookup"><span data-stu-id="d3605-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="d3605-119">**En-têtes de requête** -Content-Type: application/json.</span><span class="sxs-lookup"><span data-stu-id="d3605-119">**Request Headers** -Content-Type: application/json.</span></span>
  
 <span data-ttu-id="d3605-120">**Corps de la** demande - JSON.</span><span class="sxs-lookup"><span data-stu-id="d3605-120">**Request Body** - JSON.</span></span>
  
<span data-ttu-id="d3605-121">Exemple de charge utile de demande :</span><span class="sxs-lookup"><span data-stu-id="d3605-121">Sample request payload:</span></span>
  
```json
{
  content : "{ 'Product' : 'New Product Name'",
  type: "application/json"
}
```

 <span data-ttu-id="d3605-122">*content*  Données au format JSON à stocker en tant que nouveau contenu d’un sous-élément existant.</span><span class="sxs-lookup"><span data-stu-id="d3605-122">*content*  JSON formatted data to be stored as the new content of an existing sub-Item.</span></span> <span data-ttu-id="d3605-123">Techniquement, un référentiel peut stocker n’importe quel contenu de n’importe quel schéma, mais lorsqu’il est utilisé pour le Tableau de bord de qualité des appels, il doit s’agit d’un rapport ou d’une requête.</span><span class="sxs-lookup"><span data-stu-id="d3605-123">Technically, a repository can store any content of any schema, but when used for Call Quality Dashboard, it should be either a report or a query.</span></span> <span data-ttu-id="d3605-124">*type*  Spécifiez toujours « application/json » pour le Tableau de bord de qualité des appels.</span><span class="sxs-lookup"><span data-stu-id="d3605-124">*type*  Always specify "application/json" for Call Quality Dashboard.</span></span>
  
 <span data-ttu-id="d3605-125">**Réponse** : la réponse inclut un code d’état HTTP et un ensemble d’en-têtes de réponse.</span><span class="sxs-lookup"><span data-stu-id="d3605-125">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="d3605-126">**Code d’état** : une opération réussie renvoie le code d’état 204 (Aucun contenu).</span><span class="sxs-lookup"><span data-stu-id="d3605-126">**Status Code** - A successful operation returns status code 204 (No Content).</span></span> <span data-ttu-id="d3605-127">Si un ID d’élément spécifié est in trouvé, il renvoie le code d’état 404 (In trouvé).</span><span class="sxs-lookup"><span data-stu-id="d3605-127">If a specified item ID is not found, it returns status code 404 (Not Found).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="d3605-128">« Aucun contenu » n’est pas un état d’erreur.</span><span class="sxs-lookup"><span data-stu-id="d3605-128">"No Content" is not an error status.</span></span> <span data-ttu-id="d3605-129">Cela signifie qu’une réponse n’a rien renvoyé dans le corps (en revanche, 200 OK renvoie du contenu dans le corps).</span><span class="sxs-lookup"><span data-stu-id="d3605-129">It means that a response did not return anything in the body (in contrast, 200 OK returns content in Body).</span></span> <span data-ttu-id="d3605-130">Il indique que l’élément a été mis à jour avec succès.</span><span class="sxs-lookup"><span data-stu-id="d3605-130">It indicates that the Item was successfully updated.</span></span> 
  
 <span data-ttu-id="d3605-131">**En-têtes de réponse** - Aucun.</span><span class="sxs-lookup"><span data-stu-id="d3605-131">**Response Headers** - None.</span></span>
  
 <span data-ttu-id="d3605-132">**Corps de la** réponse - Aucun.</span><span class="sxs-lookup"><span data-stu-id="d3605-132">**Response Body** - None.</span></span>
  

