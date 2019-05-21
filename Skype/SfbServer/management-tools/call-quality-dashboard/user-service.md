---
title: Service utilisateur pour bord
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: abd5c828-42dd-4f48-bf87-29993193cb3a
description: 'Résumé: Découvrez le service utilisateur, qui fait partie de l’API du référentiel pour le tableau de bord de qualité des appels. Le tableau de bord de qualité des appels est un outil pour Skype entreprise Server.'
ms.openlocfilehash: 3ef76d26faa27034d3f092608b52676332b254a1
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274519"
---
# <a name="user-service-for-cqd"></a><span data-ttu-id="0f886-104">Service utilisateur pour bord</span><span class="sxs-lookup"><span data-stu-id="0f886-104">User Service for CQD</span></span>
 
<span data-ttu-id="0f886-105">**Résumé:** Découvrez le service utilisateur, qui fait partie de l’API du référentiel pour le tableau de bord de qualité des appels.</span><span class="sxs-lookup"><span data-stu-id="0f886-105">**Summary:** Learn about the User Service, which is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="0f886-106">Le tableau de bord de qualité des appels est un outil pour Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="0f886-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="0f886-107">Le service d’utilisateur fait partie de l’API du référentiel pour le tableau de bord de qualité des appels.</span><span class="sxs-lookup"><span data-stu-id="0f886-107">The User Service is part of the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="user-service"></a><span data-ttu-id="0f886-108">Service destiné aux utilisateurs</span><span class="sxs-lookup"><span data-stu-id="0f886-108">User Service</span></span>

<span data-ttu-id="0f886-109">L’API du référentiel fournit un modèle de gestion des utilisateurs simplifié dans lequel la mise en service des utilisateurs (création de nouveaux comptes d’utilisateur) est automatique et implicite.</span><span class="sxs-lookup"><span data-stu-id="0f886-109">Repository API provides a simplified user management model where user provisioning (creating new user accounts) is automatic and implicit.</span></span> <span data-ttu-id="0f886-110">Lorsqu’un utilisateur effectue une demande concernant l’API du référentiel pour la première fois, le référentiel crée un nouvel enregistrement utilisateur.</span><span class="sxs-lookup"><span data-stu-id="0f886-110">When a user make a request against Repository API for the first time, the repository creates a new User record.</span></span> 
  
<span data-ttu-id="0f886-111">Le tableau de bord de qualité des appels crée automatiquement un élément dédié aux utilisateurs pour le nouvel utilisateur.</span><span class="sxs-lookup"><span data-stu-id="0f886-111">Call Quality Dashboard also automatically creates a user dedicated items for the new user.</span></span> <span data-ttu-id="0f886-112">Le nouvel utilisateur éléments dédiés sont des clones complète des éléments de l’utilisateur système.</span><span class="sxs-lookup"><span data-stu-id="0f886-112">The new user dedicated items are complete clones of system user's items.</span></span> <span data-ttu-id="0f886-113">De cette façon, les utilisateurs commencent par leurs propres copies de rapports et de requêtes qu’ils peuvent lancer immédiatement.</span><span class="sxs-lookup"><span data-stu-id="0f886-113">This way, users start with their own copies of Reports and Queries that they can immediately start customizing.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="0f886-114">Le tableau de bord de qualité des appels permet aux utilisateurs de réinitialiser leurs éléments dédiés à tout moment.</span><span class="sxs-lookup"><span data-stu-id="0f886-114">Using Call Quality Dashboard, users can reset their dedicated items anytime.</span></span> 
  
 <span data-ttu-id="0f886-115">**ID d’utilisateur spéciaux**</span><span class="sxs-lookup"><span data-stu-id="0f886-115">**Special User IDs**</span></span>
  
<span data-ttu-id="0f886-116">L’API du référentiel inclut des URI REST qui attendent une valeur entière pour spécifier un utilisateur particulier.</span><span class="sxs-lookup"><span data-stu-id="0f886-116">Repository API includes REST API URIs that expects an integer value to specify a particular user.</span></span> <span data-ttu-id="0f886-117">Par exemple `https://<portal>/QoERepositoryService/repository/user/{userId}`:.</span><span class="sxs-lookup"><span data-stu-id="0f886-117">Example:  `https://<portal>/QoERepositoryService/repository/user/{userId}`.</span></span> <span data-ttu-id="0f886-118">Dans cet exemple, {Id_utilisateur} doit être remplacé par une valeur de type entier (par exemple, 0, 1, etc.).</span><span class="sxs-lookup"><span data-stu-id="0f886-118">Here, {userId} should be replaced by an integer value such as 0, 1, etc.</span></span>
  
<span data-ttu-id="0f886-119">Par ailleurs, l’API du référentiel accepte deux ID utilisateur spéciaux à la fois à l’adresse de l’URI.</span><span class="sxs-lookup"><span data-stu-id="0f886-119">Moreover, Repository API will accept two special user IDs at {userId} in URIs.</span></span>
  
-  <span data-ttu-id="0f886-120">*par défaut* : représente l’utilisateur qui interagit actuellement avec l’API.</span><span class="sxs-lookup"><span data-stu-id="0f886-120">*default*  - represents the user who is currently interacting with the API.</span></span> <span data-ttu-id="0f886-121">Cela permet aux applications d’accéder au contenu actuel de l’utilisateur sans suivre la valeur de l’IDENTIFIant utilisateur réel.</span><span class="sxs-lookup"><span data-stu-id="0f886-121">This allows applications to access current user's contents without keeping track of the actual user ID value.</span></span> <span data-ttu-id="0f886-122">Par exemple ` https://<portal>/QoERepositoryService/repository/user/default`:.</span><span class="sxs-lookup"><span data-stu-id="0f886-122">Example: ` https://<portal>/QoERepositoryService/repository/user/default`.</span></span>
    
-  <span data-ttu-id="0f886-123">*System* -correspond à l’utilisateur système.</span><span class="sxs-lookup"><span data-stu-id="0f886-123">*system*  - represents the system user.</span></span> <span data-ttu-id="0f886-124">Cela permet aux applications d’accéder au contenu de l’utilisateur système sans connaître la valeur de l’IDENTIFIant utilisateur réel.</span><span class="sxs-lookup"><span data-stu-id="0f886-124">This allows applications to access the system user's contents without knowing the actual user ID value.</span></span> <span data-ttu-id="0f886-125">Par exemple `https://<portal>/QoERepositoryService/repository/user/system`:.</span><span class="sxs-lookup"><span data-stu-id="0f886-125">Example: `https://<portal>/QoERepositoryService/repository/user/system`.</span></span>
    
<span data-ttu-id="0f886-126">Sauf indication contraire, il est possible d’utiliser les ID d’utilisateur spéciaux au niveau de {Id_utilisateur} dans les URI.</span><span class="sxs-lookup"><span data-stu-id="0f886-126">Unless otherwise noted, the special user IDs can be used at {userId} in URIs.</span></span> 
  
<span data-ttu-id="0f886-127">Les opérations REST sont comprises dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="0f886-127">The REST operations are included in the following table.</span></span>
  
|<span data-ttu-id="0f886-128">**Opération**</span><span class="sxs-lookup"><span data-stu-id="0f886-128">**Operation**</span></span>|<span data-ttu-id="0f886-129">**Description**</span><span class="sxs-lookup"><span data-stu-id="0f886-129">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="0f886-130">Obtenir les utilisateurs</span><span class="sxs-lookup"><span data-stu-id="0f886-130">Get Users</span></span>](get-users.md) <br/> |<span data-ttu-id="0f886-131">Renvoie une liste des utilisateurs du référentiel.</span><span class="sxs-lookup"><span data-stu-id="0f886-131">Returns a list of users in the repository.</span></span>  <br/> |
|[<span data-ttu-id="0f886-132">Obtenir un utilisateur</span><span class="sxs-lookup"><span data-stu-id="0f886-132">Get User</span></span>](get-user.md) <br/> |<span data-ttu-id="0f886-133">Renvoie un enregistrement utilisateur.</span><span class="sxs-lookup"><span data-stu-id="0f886-133">Returns a user record.</span></span>  <br/> |
   

