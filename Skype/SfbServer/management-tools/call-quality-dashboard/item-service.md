---
title: Service d’article pour le tableau de bord de qualité des appels (bord)
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
ms.assetid: b6d7b02a-a34e-4fef-986c-ca442e18fa0c
description: 'Résumé : en savoir plus sur le service des éléments, qui fait partie de l’API du référentiel pour le tableau de bord de qualité des appels. Le tableau de bord de qualité des appels est un outil pour Skype entreprise Server.'
ms.openlocfilehash: 5fdf2aedcb1a5e8d7d1929d7af70c5911cae46f0
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816713"
---
# <a name="item-service-for-call-quality-dashboard-cqd"></a><span data-ttu-id="5c5cf-104">Service d’article pour le tableau de bord de qualité des appels (bord)</span><span class="sxs-lookup"><span data-stu-id="5c5cf-104">Item Service for Call Quality Dashboard (CQD)</span></span>
 
<span data-ttu-id="5c5cf-105">**Résumé :** En savoir plus sur le service d’élément, qui fait partie de l’API de référentiel pour le tableau de bord de qualité des appels.</span><span class="sxs-lookup"><span data-stu-id="5c5cf-105">**Summary:** Learn about the Item Service, which is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="5c5cf-106">Le tableau de bord de qualité des appels est un outil pour Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="5c5cf-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="5c5cf-107">Le service d’élément fait partie de l’API du référentiel pour le tableau de bord de qualité des appels.</span><span class="sxs-lookup"><span data-stu-id="5c5cf-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="item-service"></a><span data-ttu-id="5c5cf-108">Service d’article</span><span class="sxs-lookup"><span data-stu-id="5c5cf-108">Item Service</span></span>

<span data-ttu-id="5c5cf-109">L’API du référentiel propose un service de gestion de contenu simple, connu sous le nom de service des éléments, qui peut être utilisé pour stocker des contenus définis par l’application pour les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="5c5cf-109">Repository API offers a simple content management service, known as item service, that can be used for storing any application-defined contents for users.</span></span> 
  
<span data-ttu-id="5c5cf-110">Le contenu du système appartient à l’utilisateur système et est partagé par tous les utilisateurs disposant d’un accès en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="5c5cf-110">The system contents are owned by the system user and shared by all users with read-only access.</span></span> <span data-ttu-id="5c5cf-111">Le contenu utilisateur dédié est possédé par des utilisateurs normaux et seuls les propriétaires peuvent modifier ou supprimer des éléments, mais tous les utilisateurs disposent toujours d’un accès en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="5c5cf-111">Dedicated user contents are owned by regular users, and only the owners can modify or delete them, but all users still have read-only access to them.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5c5cf-112">Cette documentation sur les API décrit les opérations en lecture seule de l’API du référentiel.</span><span class="sxs-lookup"><span data-stu-id="5c5cf-112">This API documentation covers read-only operations of Repository API.</span></span> 
  
<span data-ttu-id="5c5cf-113">Le tableau de bord de qualité des appels enregistre des rapports et des requêtes en tant qu’éléments dans la base de données du référentiel.</span><span class="sxs-lookup"><span data-stu-id="5c5cf-113">Call Quality Dashboard saves Reports and Queries as Items in the repository database.</span></span> <span data-ttu-id="5c5cf-114">Un élément peut avoir des sous-éléments facultatifs et le tableau de bord de qualité des appels organise les rapports et les requêtes dans une structure hiérarchique à l’aide de la fonctionnalité sous-éléments.</span><span class="sxs-lookup"><span data-stu-id="5c5cf-114">An Item can have optional sub-Items, and Call Quality Dashboard organizes Reports and Queries in an hierarchical structure using sub-Items feature.</span></span>
  
<span data-ttu-id="5c5cf-115">Le service des éléments inclut les concepts suivants :</span><span class="sxs-lookup"><span data-stu-id="5c5cf-115">Item service includes the following concepts:</span></span>
  
- <span data-ttu-id="5c5cf-116">**Élément** : élément de base du référentiel.</span><span class="sxs-lookup"><span data-stu-id="5c5cf-116">**Item** - the basic element of repository.</span></span> <span data-ttu-id="5c5cf-117">Chaque élément est possédé par un seul utilisateur.</span><span class="sxs-lookup"><span data-stu-id="5c5cf-117">Each Item is owned by exactly one User.</span></span>
    
- <span data-ttu-id="5c5cf-118">**Sous-élément** : la mécanique de base du référentiel.</span><span class="sxs-lookup"><span data-stu-id="5c5cf-118">**Sub-Item** - the basic organizational mechanics of repository.</span></span> <span data-ttu-id="5c5cf-119">Un élément peut avoir zéro, un ou plusieurs éléments subordonnés.</span><span class="sxs-lookup"><span data-stu-id="5c5cf-119">Item can have zero, one, or more subordinate Items.</span></span>
    
- <span data-ttu-id="5c5cf-120">**Ancêtres d’élément** : liste d’éléments, à partir de l’élément le plus élevé, qui est l’élément par défaut de l’utilisateur, conduisant à un élément donné.</span><span class="sxs-lookup"><span data-stu-id="5c5cf-120">**Item Ancestors** - the list of Items, beginning from the top-most Item, which is the default Item of the User, leading to a given Item.</span></span>
    
- <span data-ttu-id="5c5cf-121">**Contenu** de l’élément : contenu spécifique à l’application stocké dans les éléments.</span><span class="sxs-lookup"><span data-stu-id="5c5cf-121">**Item Content** - the application-specific content stored in Items.</span></span> <span data-ttu-id="5c5cf-122">Le tableau de bord de qualité des appels enregistre les représentations JSON des rapports et des requêtes dans le contenu.</span><span class="sxs-lookup"><span data-stu-id="5c5cf-122">Call Quality Dashboard saves JSON representations of Reports and Queries in Contents.</span></span>
    
<span data-ttu-id="5c5cf-123">Les opérations REST sont comprises dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="5c5cf-123">The REST operations are included in the following table.</span></span>
  

|<span data-ttu-id="5c5cf-124">**Opération**</span><span class="sxs-lookup"><span data-stu-id="5c5cf-124">**Operation**</span></span>|<span data-ttu-id="5c5cf-125">**Description**</span><span class="sxs-lookup"><span data-stu-id="5c5cf-125">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="5c5cf-126">Obtenir des éléments</span><span class="sxs-lookup"><span data-stu-id="5c5cf-126">Get Items</span></span>](get-items.md) <br/> |<span data-ttu-id="5c5cf-127">Get renvoie tous les éléments du référentiel.</span><span class="sxs-lookup"><span data-stu-id="5c5cf-127">Get Items returns all Items in the repository.</span></span>  <br/> |
|[<span data-ttu-id="5c5cf-128">Obtenir un élément</span><span class="sxs-lookup"><span data-stu-id="5c5cf-128">Get Item</span></span>](get-item.md) <br/> |<span data-ttu-id="5c5cf-129">Obtenir renvoie un élément spécifique.</span><span class="sxs-lookup"><span data-stu-id="5c5cf-129">Get Item returns a specific Item.</span></span>  <br/> |
|[<span data-ttu-id="5c5cf-130">Obtenir des sous-éléments</span><span class="sxs-lookup"><span data-stu-id="5c5cf-130">Get Sub-Items</span></span>](get-sub-items.md) <br/> |<span data-ttu-id="5c5cf-131">L’option obtenir des sous-éléments renvoie les sous-éléments d’un élément spécifiques.</span><span class="sxs-lookup"><span data-stu-id="5c5cf-131">Get Sub-Items returns a specific Item's sub-Items.</span></span>  <br/> |
|[<span data-ttu-id="5c5cf-132">Obtenir les ancêtres d’élément</span><span class="sxs-lookup"><span data-stu-id="5c5cf-132">Get Item Ancestors</span></span>](get-item-ancestors.md) <br/> |<span data-ttu-id="5c5cf-133">Obtient les ancêtres qui renvoient les ancêtres des éléments spécifiques.</span><span class="sxs-lookup"><span data-stu-id="5c5cf-133">Get Item Ancestors returns a specific Item's ancestors.</span></span>  <br/> |
|[<span data-ttu-id="5c5cf-134">Mettre à jour un élément</span><span class="sxs-lookup"><span data-stu-id="5c5cf-134">Update Item</span></span>](update-item.md) <br/> |<span data-ttu-id="5c5cf-135">Mettre à jour un élément spécifique du référentiel.</span><span class="sxs-lookup"><span data-stu-id="5c5cf-135">Update a specific item in the repository.</span></span>  <br/> |
   

