---
title: Service d’élément de tableau de bord qualité appel (CQD)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b6d7b02a-a34e-4fef-986c-ca442e18fa0c
description: 'Résumé : En savoir plus sur le Service de l’élément, qui fait partie de l’API de référentiel pour appeler le tableau de bord qualité. Tableau de bord de qualité des appels est un outil de Skype pour Business Server.'
ms.openlocfilehash: cbebdcfcac62eae375c13785b8d9866d055c2b50
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33897498"
---
# <a name="item-service-for-call-quality-dashboard-cqd"></a><span data-ttu-id="d16b3-104">Service d’élément de tableau de bord qualité appel (CQD)</span><span class="sxs-lookup"><span data-stu-id="d16b3-104">Item Service for Call Quality Dashboard (CQD)</span></span>
 
<span data-ttu-id="d16b3-105">**Résumé :** Obtenir des informations sur le Service de l’élément, qui fait partie de l’API de référentiel pour appeler le tableau de bord qualité.</span><span class="sxs-lookup"><span data-stu-id="d16b3-105">**Summary:** Learn about the Item Service, which is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="d16b3-106">Tableau de bord de qualité des appels est un outil de Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="d16b3-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="d16b3-107">Le Service de l’élément fait partie de l’API de référentiel pour appeler le tableau de bord qualité.</span><span class="sxs-lookup"><span data-stu-id="d16b3-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="item-service"></a><span data-ttu-id="d16b3-108">Service d’article</span><span class="sxs-lookup"><span data-stu-id="d16b3-108">Item Service</span></span>

<span data-ttu-id="d16b3-109">API de référentiel offre un service de gestion de contenu simple, appelé service d’élément, qui peut être utilisé pour le stockage de contenu défini par l’application pour les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="d16b3-109">Repository API offers a simple content management service, known as item service, that can be used for storing any application-defined contents for users.</span></span> 
  
<span data-ttu-id="d16b3-110">Le contenu du système est détenus par l’utilisateur du système et partagé par tous les utilisateurs avec accès en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="d16b3-110">The system contents are owned by the system user and shared by all users with read-only access.</span></span> <span data-ttu-id="d16b3-111">Contenu utilisateur dédié appartiennent par les utilisateurs standard et seuls les propriétaires peuvent modifier ou supprimer les, mais tous les utilisateurs ont toujours accès en lecture seule pour les.</span><span class="sxs-lookup"><span data-stu-id="d16b3-111">Dedicated user contents are owned by regular users, and only the owners can modify or delete them, but all users still have read-only access to them.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d16b3-112">Cette documentation de l’API traite des opérations en lecture seule de l’API de référentiel.</span><span class="sxs-lookup"><span data-stu-id="d16b3-112">This API documentation covers read-only operations of Repository API.</span></span> 
  
<span data-ttu-id="d16b3-113">Tableau de bord qualité appel enregistre des rapports et des requêtes en tant qu’éléments dans la base de données de référentiel.</span><span class="sxs-lookup"><span data-stu-id="d16b3-113">Call Quality Dashboard saves Reports and Queries as Items in the repository database.</span></span> <span data-ttu-id="d16b3-114">Un élément peut avoir les sous-éléments facultatifs, et appelez le tableau de bord qualité organise des rapports et des requêtes dans une structure hiérarchique à l’aide de la fonctionnalité sous-éléments.</span><span class="sxs-lookup"><span data-stu-id="d16b3-114">An Item can have optional sub-Items, and Call Quality Dashboard organizes Reports and Queries in an hierarchical structure using sub-Items feature.</span></span>
  
<span data-ttu-id="d16b3-115">Élément comprend les concepts suivants :</span><span class="sxs-lookup"><span data-stu-id="d16b3-115">Item service includes the following concepts:</span></span>
  
- <span data-ttu-id="d16b3-116">**Élément** - l’élément de base du référentiel.</span><span class="sxs-lookup"><span data-stu-id="d16b3-116">**Item** - the basic element of repository.</span></span> <span data-ttu-id="d16b3-117">Chaque élément appartient à un seul utilisateur.</span><span class="sxs-lookup"><span data-stu-id="d16b3-117">Each Item is owned by exactly one User.</span></span>
    
- <span data-ttu-id="d16b3-118">**Sous-élément** - les mécanismes d’organisation de base du référentiel.</span><span class="sxs-lookup"><span data-stu-id="d16b3-118">**Sub-Item** - the basic organizational mechanics of repository.</span></span> <span data-ttu-id="d16b3-119">Élément peut avoir zéro, une ou plusieurs des éléments subordonnés.</span><span class="sxs-lookup"><span data-stu-id="d16b3-119">Item can have zero, one, or more subordinate Items.</span></span>
    
- <span data-ttu-id="d16b3-120">**Élément ancêtres** - la liste des éléments, en commençant à partir de l’élément de niveau supérieur, qui est la valeur par défaut de l’élément de l’utilisateur, conduisant à un élément donné.</span><span class="sxs-lookup"><span data-stu-id="d16b3-120">**Item Ancestors** - the list of Items, beginning from the top-most Item, which is the default Item of the User, leading to a given Item.</span></span>
    
- <span data-ttu-id="d16b3-121">**Contenu de l’élément** - le contenu spécifique à l’application stocké dans les éléments.</span><span class="sxs-lookup"><span data-stu-id="d16b3-121">**Item Content** - the application-specific content stored in Items.</span></span> <span data-ttu-id="d16b3-122">Tableau de bord qualité appel enregistre représentations JSON de rapports et de requêtes de contenu.</span><span class="sxs-lookup"><span data-stu-id="d16b3-122">Call Quality Dashboard saves JSON representations of Reports and Queries in Contents.</span></span>
    
<span data-ttu-id="d16b3-123">Les opérations REST sont incluses dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="d16b3-123">The REST operations are included in the following table.</span></span>
  

|<span data-ttu-id="d16b3-124">**Opération**</span><span class="sxs-lookup"><span data-stu-id="d16b3-124">**Operation**</span></span>|<span data-ttu-id="d16b3-125">**Description**</span><span class="sxs-lookup"><span data-stu-id="d16b3-125">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="d16b3-126">Obtenir des éléments</span><span class="sxs-lookup"><span data-stu-id="d16b3-126">Get Items</span></span>](get-items.md) <br/> |<span data-ttu-id="d16b3-127">Obtenir les éléments renvoie tous les éléments dans le référentiel.</span><span class="sxs-lookup"><span data-stu-id="d16b3-127">Get Items returns all Items in the repository.</span></span>  <br/> |
|[<span data-ttu-id="d16b3-128">Obtenir un élément</span><span class="sxs-lookup"><span data-stu-id="d16b3-128">Get Item</span></span>](get-item.md) <br/> |<span data-ttu-id="d16b3-129">Obtenir élément renvoie un élément spécifique.</span><span class="sxs-lookup"><span data-stu-id="d16b3-129">Get Item returns a specific Item.</span></span>  <br/> |
|[<span data-ttu-id="d16b3-130">Obtenir des sous-éléments</span><span class="sxs-lookup"><span data-stu-id="d16b3-130">Get Sub-Items</span></span>](get-sub-items.md) <br/> |<span data-ttu-id="d16b3-131">Obtenez les sous-éléments renvoie les sous-éléments d’un élément spécifique.</span><span class="sxs-lookup"><span data-stu-id="d16b3-131">Get Sub-Items returns a specific Item's sub-Items.</span></span>  <br/> |
|[<span data-ttu-id="d16b3-132">Obtenir les ancêtres d’élément</span><span class="sxs-lookup"><span data-stu-id="d16b3-132">Get Item Ancestors</span></span>](get-item-ancestors.md) <br/> |<span data-ttu-id="d16b3-133">Get élément ancêtres renvoie ancêtres d’un élément spécifique.</span><span class="sxs-lookup"><span data-stu-id="d16b3-133">Get Item Ancestors returns a specific Item's ancestors.</span></span>  <br/> |
|[<span data-ttu-id="d16b3-134">Mettre à jour un élément</span><span class="sxs-lookup"><span data-stu-id="d16b3-134">Update Item</span></span>](update-item.md) <br/> |<span data-ttu-id="d16b3-135">Mettre à jour un élément spécifique dans le référentiel.</span><span class="sxs-lookup"><span data-stu-id="d16b3-135">Update a specific item in the repository.</span></span>  <br/> |
   

