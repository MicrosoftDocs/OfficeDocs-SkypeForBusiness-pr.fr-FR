---
title: Service d’élément pour le tableau de bord de qualité des appels (CQD)
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
ms.assetid: b6d7b02a-a34e-4fef-986c-ca442e18fa0c
description: 'Résumé : Découvrez le service d’élément, qui fait partie de l’API référentiel pour le tableau de bord de qualité des appels. Le Tableau de bord de qualité des appels est un outil pour Skype Entreprise Server.'
ms.openlocfilehash: b904f814a837af13e4015af5fbaca924739b8997
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827704"
---
# <a name="item-service-for-call-quality-dashboard-cqd"></a><span data-ttu-id="27f13-104">Service d’élément pour le tableau de bord de qualité des appels (CQD)</span><span class="sxs-lookup"><span data-stu-id="27f13-104">Item Service for Call Quality Dashboard (CQD)</span></span>
 
<span data-ttu-id="27f13-105">**Résumé :** Découvrez le service d’élément, qui fait partie de l’API référentiel pour le tableau de bord de qualité des appels.</span><span class="sxs-lookup"><span data-stu-id="27f13-105">**Summary:** Learn about the Item Service, which is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="27f13-106">Le Tableau de bord de qualité des appels est un outil pour Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="27f13-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="27f13-107">Le service d’élément fait partie de l’API de référentiel pour le tableau de bord de qualité des appels.</span><span class="sxs-lookup"><span data-stu-id="27f13-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="item-service"></a><span data-ttu-id="27f13-108">Service d’article</span><span class="sxs-lookup"><span data-stu-id="27f13-108">Item Service</span></span>

<span data-ttu-id="27f13-109">L’API de référentiel offre un service de gestion de contenu simple, appelé service d’élément, qui peut être utilisé pour stocker tout contenu défini par l’application pour les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="27f13-109">Repository API offers a simple content management service, known as item service, that can be used for storing any application-defined contents for users.</span></span> 
  
<span data-ttu-id="27f13-110">Le contenu du système appartient à l’utilisateur système et est partagé par tous les utilisateurs avec un accès en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="27f13-110">The system contents are owned by the system user and shared by all users with read-only access.</span></span> <span data-ttu-id="27f13-111">Le contenu des utilisateurs dédiés appartient à des utilisateurs réguliers et seuls les propriétaires peuvent les modifier ou les supprimer, mais tous les utilisateurs y ont toujours accès en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="27f13-111">Dedicated user contents are owned by regular users, and only the owners can modify or delete them, but all users still have read-only access to them.</span></span>
  
> [!NOTE]
> <span data-ttu-id="27f13-112">Cette documentation de l’API couvre les opérations en lecture seule de l’API référentiel.</span><span class="sxs-lookup"><span data-stu-id="27f13-112">This API documentation covers read-only operations of Repository API.</span></span> 
  
<span data-ttu-id="27f13-113">Le Tableau de bord de qualité des appels enregistre les rapports et les requêtes en tant qu’éléments dans la base de données du référentiel.</span><span class="sxs-lookup"><span data-stu-id="27f13-113">Call Quality Dashboard saves Reports and Queries as Items in the repository database.</span></span> <span data-ttu-id="27f13-114">Un élément peut avoir des sous-éléments facultatifs, et le Tableau de bord de qualité des appels organise les rapports et les requêtes dans une structure hiérarchique à l’aide de la fonctionnalité sous-éléments.</span><span class="sxs-lookup"><span data-stu-id="27f13-114">An Item can have optional sub-Items, and Call Quality Dashboard organizes Reports and Queries in an hierarchical structure using sub-Items feature.</span></span>
  
<span data-ttu-id="27f13-115">Le service d’élément comprend les concepts suivants :</span><span class="sxs-lookup"><span data-stu-id="27f13-115">Item service includes the following concepts:</span></span>
  
- <span data-ttu-id="27f13-116">**Item** - élément de base du référentiel.</span><span class="sxs-lookup"><span data-stu-id="27f13-116">**Item** - the basic element of repository.</span></span> <span data-ttu-id="27f13-117">Chaque élément appartient exactement à un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="27f13-117">Each Item is owned by exactly one User.</span></span>
    
- <span data-ttu-id="27f13-118">**Sous-élément :** mécanismes d’organisation de base du référentiel.</span><span class="sxs-lookup"><span data-stu-id="27f13-118">**Sub-Item** - the basic organizational mechanics of repository.</span></span> <span data-ttu-id="27f13-119">L’élément peut avoir zéro, un ou plusieurs éléments subordonnés.</span><span class="sxs-lookup"><span data-stu-id="27f13-119">Item can have zero, one, or more subordinate Items.</span></span>
    
- <span data-ttu-id="27f13-120">**Ancêtres** d’élément : liste des éléments, en commençant par l’élément le plus haut, qui est l’élément par défaut de l’utilisateur, menant à un élément donné.</span><span class="sxs-lookup"><span data-stu-id="27f13-120">**Item Ancestors** - the list of Items, beginning from the top-most Item, which is the default Item of the User, leading to a given Item.</span></span>
    
- <span data-ttu-id="27f13-121">**Contenu d’élément** : contenu propre à l’application stocké dans les éléments.</span><span class="sxs-lookup"><span data-stu-id="27f13-121">**Item Content** - the application-specific content stored in Items.</span></span> <span data-ttu-id="27f13-122">Le Tableau de bord de qualité des appels enregistre les représentations JSON des rapports et des requêtes dans le contenu.</span><span class="sxs-lookup"><span data-stu-id="27f13-122">Call Quality Dashboard saves JSON representations of Reports and Queries in Contents.</span></span>
    
<span data-ttu-id="27f13-123">Les opérations REST sont incluses dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="27f13-123">The REST operations are included in the following table.</span></span>
  

|<span data-ttu-id="27f13-124">**Opération**</span><span class="sxs-lookup"><span data-stu-id="27f13-124">**Operation**</span></span>|<span data-ttu-id="27f13-125">**Description**</span><span class="sxs-lookup"><span data-stu-id="27f13-125">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="27f13-126">Obtenir des éléments</span><span class="sxs-lookup"><span data-stu-id="27f13-126">Get Items</span></span>](get-items.md) <br/> |<span data-ttu-id="27f13-127">Get Items renvoie tous les éléments du référentiel.</span><span class="sxs-lookup"><span data-stu-id="27f13-127">Get Items returns all Items in the repository.</span></span>  <br/> |
|[<span data-ttu-id="27f13-128">Obtenir un élément</span><span class="sxs-lookup"><span data-stu-id="27f13-128">Get Item</span></span>](get-item.md) <br/> |<span data-ttu-id="27f13-129">Obtenir l’élément renvoie un élément spécifique.</span><span class="sxs-lookup"><span data-stu-id="27f13-129">Get Item returns a specific Item.</span></span>  <br/> |
|[<span data-ttu-id="27f13-130">Obtenir des sous-éléments</span><span class="sxs-lookup"><span data-stu-id="27f13-130">Get Sub-Items</span></span>](get-sub-items.md) <br/> |<span data-ttu-id="27f13-131">Obtenir Sub-Items renvoie les sous-éléments d’un élément spécifique.</span><span class="sxs-lookup"><span data-stu-id="27f13-131">Get Sub-Items returns a specific Item's sub-Items.</span></span>  <br/> |
|[<span data-ttu-id="27f13-132">Obtenir les ancêtres d’élément</span><span class="sxs-lookup"><span data-stu-id="27f13-132">Get Item Ancestors</span></span>](get-item-ancestors.md) <br/> |<span data-ttu-id="27f13-133">Obtenir des ancêtres d’élément renvoie les ancêtres d’un élément spécifique.</span><span class="sxs-lookup"><span data-stu-id="27f13-133">Get Item Ancestors returns a specific Item's ancestors.</span></span>  <br/> |
|[<span data-ttu-id="27f13-134">Mettre à jour un élément</span><span class="sxs-lookup"><span data-stu-id="27f13-134">Update Item</span></span>](update-item.md) <br/> |<span data-ttu-id="27f13-135">Mettez à jour un élément spécifique dans le référentiel.</span><span class="sxs-lookup"><span data-stu-id="27f13-135">Update a specific item in the repository.</span></span>  <br/> |
   

