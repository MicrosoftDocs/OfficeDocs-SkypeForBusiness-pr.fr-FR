---
title: Service d’élément de tableau de bord qualité appel (CQD)
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 6/8/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b6d7b02a-a34e-4fef-986c-ca442e18fa0c
description: 'Résumé : En savoir plus sur le Service de l’article, qui fait partie de l’API de référentiel pour appeler le tableau de bord qualité. Tableau de bord qualité appel est un outil de Skype pour Business Server 2015.'
ms.openlocfilehash: 218fdb4f2c4b3d73fb4e7f78b5679b66eecf34cc
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="item-service-for-call-quality-dashboard-cqd"></a><span data-ttu-id="19634-104">Service d’élément de tableau de bord qualité appel (CQD)</span><span class="sxs-lookup"><span data-stu-id="19634-104">Item Service for Call Quality Dashboard (CQD)</span></span>
 
<span data-ttu-id="19634-105">**Résumé :** Obtenir des informations sur le Service de l’article, qui fait partie de l’API de référentiel pour appeler le tableau de bord qualité.</span><span class="sxs-lookup"><span data-stu-id="19634-105">**Summary:** Learn about the Item Service, which is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="19634-106">Tableau de bord qualité appel est un outil de Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="19634-106">Call Quality Dashboard is a tool for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="19634-107">L’article de Service fait partie de l’API de référentiel pour appeler le tableau de bord qualité.</span><span class="sxs-lookup"><span data-stu-id="19634-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="item-service"></a><span data-ttu-id="19634-108">Service d’article</span><span class="sxs-lookup"><span data-stu-id="19634-108">Item Service</span></span>

<span data-ttu-id="19634-109">API de référentiel offre un service de gestion de contenu simple, connu en tant que service d’élément, qui peut être utilisé pour le stockage de contenu défini par l’application pour les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="19634-109">Repository API offers a simple content management service, known as item service, that can be used for storing any application-defined contents for users.</span></span> 
  
<span data-ttu-id="19634-110">Le contenu du système est appartenant à l’utilisateur du système et partagé par tous les utilisateurs disposant d’un accès en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="19634-110">The system contents are owned by the system user and shared by all users with read-only access.</span></span> <span data-ttu-id="19634-111">Utilisateur dédié contenu appartiennent à des utilisateurs réguliers et seuls les propriétaires peuvent modifier ou les supprimer, mais tous les utilisateurs ont toujours accès en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="19634-111">Dedicated user contents are owned by regular users, and only the owners can modify or delete them, but all users still have read-only access to them.</span></span>
  
> [!NOTE]
> <span data-ttu-id="19634-112">Cette documentation de l’API traite des opérations en lecture seule de l’API de référentiel.</span><span class="sxs-lookup"><span data-stu-id="19634-112">This API documentation covers read-only operations of Repository API.</span></span> 
  
<span data-ttu-id="19634-113">Tableau de bord qualité appel enregistre des rapports et des requêtes en tant qu’éléments dans la base de données de référentiel.</span><span class="sxs-lookup"><span data-stu-id="19634-113">Call Quality Dashboard saves Reports and Queries as Items in the repository database.</span></span> <span data-ttu-id="19634-114">Un élément peut avoir des sous-éléments facultatifs, et appelez le tableau de bord qualité organise des rapports et des requêtes dans une structure hiérarchique à l’aide de la fonctionnalité de sous-éléments.</span><span class="sxs-lookup"><span data-stu-id="19634-114">An Item can have optional sub-Items, and Call Quality Dashboard organizes Reports and Queries in an hierarchical structure using sub-Items feature.</span></span>
  
<span data-ttu-id="19634-115">Service d’article comprend les concepts suivants :</span><span class="sxs-lookup"><span data-stu-id="19634-115">Item service includes the following concepts:</span></span>
  
- <span data-ttu-id="19634-116">**Article** - l’élément de base du référentiel.</span><span class="sxs-lookup"><span data-stu-id="19634-116">**Item** - the basic element of repository.</span></span> <span data-ttu-id="19634-117">Chaque élément est détenu par un seul utilisateur.</span><span class="sxs-lookup"><span data-stu-id="19634-117">Each Item is owned by exactly one User.</span></span>
    
- <span data-ttu-id="19634-118">**Sous-élément** - les mécanismes d’organisation de base du référentiel.</span><span class="sxs-lookup"><span data-stu-id="19634-118">**Sub-Item** - the basic organizational mechanics of repository.</span></span> <span data-ttu-id="19634-119">Article peut y avoir zéro, un ou plusieurs des éléments subordonnés.</span><span class="sxs-lookup"><span data-stu-id="19634-119">Item can have zero, one, or more subordinate Items.</span></span>
    
- <span data-ttu-id="19634-120">**Ancêtres de l’élément** - la liste des éléments, en commençant à partir de l’élément au premier plan, qui est la valeur par défaut de l’élément de l’utilisateur, conduisant à un élément donné.</span><span class="sxs-lookup"><span data-stu-id="19634-120">**Item Ancestors** - the list of Items, beginning from the top-most Item, which is the default Item of the User, leading to a given Item.</span></span>
    
- <span data-ttu-id="19634-121">**Contenu de l’élément** - le contenu spécifique à l’application stocké dans les éléments.</span><span class="sxs-lookup"><span data-stu-id="19634-121">**Item Content** - the application-specific content stored in Items.</span></span> <span data-ttu-id="19634-122">Appel de tableau de bord qualité enregistre la représentation JSON des rapports et des requêtes dans le contenu.</span><span class="sxs-lookup"><span data-stu-id="19634-122">Call Quality Dashboard saves JSON representations of Reports and Queries in Contents.</span></span>
    
<span data-ttu-id="19634-123">Les opérations de repos sont incluses dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="19634-123">The REST operations are included in the following table.</span></span>
  

|<span data-ttu-id="19634-124">**Opération**</span><span class="sxs-lookup"><span data-stu-id="19634-124">**Operation**</span></span>|<span data-ttu-id="19634-125">**Description**</span><span class="sxs-lookup"><span data-stu-id="19634-125">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="19634-126">Obtenir des éléments</span><span class="sxs-lookup"><span data-stu-id="19634-126">Get Items</span></span>](get-items.md) <br/> |<span data-ttu-id="19634-127">Obtenir les éléments retourne tous les éléments dans le référentiel.</span><span class="sxs-lookup"><span data-stu-id="19634-127">Get Items returns all Items in the repository.</span></span>  <br/> |
|[<span data-ttu-id="19634-128">Obtenir l’élément</span><span class="sxs-lookup"><span data-stu-id="19634-128">Get Item</span></span>](get-item.md) <br/> |<span data-ttu-id="19634-129">Obtenir élément renvoie un élément spécifique.</span><span class="sxs-lookup"><span data-stu-id="19634-129">Get Item returns a specific Item.</span></span>  <br/> |
|[<span data-ttu-id="19634-130">Obtenir des éléments de sous-menu</span><span class="sxs-lookup"><span data-stu-id="19634-130">Get Sub-Items</span></span>](get-sub-items.md) <br/> |<span data-ttu-id="19634-131">Obtenir les sous-éléments retourne les sous-éléments d’un élément spécifique.</span><span class="sxs-lookup"><span data-stu-id="19634-131">Get Sub-Items returns a specific Item's sub-Items.</span></span>  <br/> |
|[<span data-ttu-id="19634-132">Obtenir les ancêtres de l’élément</span><span class="sxs-lookup"><span data-stu-id="19634-132">Get Item Ancestors</span></span>](get-item-ancestors.md) <br/> |<span data-ttu-id="19634-133">Ancêtres d’élément Get retourne les ancêtres d’un élément spécifique.</span><span class="sxs-lookup"><span data-stu-id="19634-133">Get Item Ancestors returns a specific Item's ancestors.</span></span>  <br/> |
|[<span data-ttu-id="19634-134">Élément de mise à jour</span><span class="sxs-lookup"><span data-stu-id="19634-134">Update Item</span></span>](update-item.md) <br/> |<span data-ttu-id="19634-135">Mettre à jour un élément spécifique dans le référentiel.</span><span class="sxs-lookup"><span data-stu-id="19634-135">Update a specific item in the repository.</span></span>  <br/> |
   

