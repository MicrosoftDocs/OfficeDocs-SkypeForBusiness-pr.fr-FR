---
title: Service utilisateur pour CQD
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: abd5c828-42dd-4f48-bf87-29993193cb3a
description: 'Résumé : En savoir plus sur le Service de l’utilisateur, qui fait partie de l’API de référentiel pour appeler le tableau de bord qualité. Tableau de bord qualité appel est un outil de Skype pour Business Server 2015.'
ms.openlocfilehash: c4bb2395ea3fa4541140a7966bbfb554ef53c168
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="user-service-for-cqd"></a><span data-ttu-id="3eae7-104">Service utilisateur pour CQD</span><span class="sxs-lookup"><span data-stu-id="3eae7-104">User Service for CQD</span></span>
 
<span data-ttu-id="3eae7-105">**Résumé :** Obtenir des informations sur le Service de l’utilisateur, qui fait partie de l’API de référentiel pour appeler le tableau de bord qualité.</span><span class="sxs-lookup"><span data-stu-id="3eae7-105">**Summary:** Learn about the User Service, which is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="3eae7-106">Tableau de bord qualité appel est un outil de Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="3eae7-106">Call Quality Dashboard is a tool for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="3eae7-107">Le Service de l’utilisateur est la partie de l’API de référentiel pour appeler le tableau de bord qualité.</span><span class="sxs-lookup"><span data-stu-id="3eae7-107">The User Service is part of the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="user-service"></a><span data-ttu-id="3eae7-108">Service de l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="3eae7-108">User Service</span></span>

<span data-ttu-id="3eae7-109">API de référentiel fournit un modèle de gestion d’utilisateur simplifiée où approvisionnement (création de comptes d’utilisateur) de l’utilisateur est automatique et implicite.</span><span class="sxs-lookup"><span data-stu-id="3eae7-109">Repository API provides a simplified user management model where user provisioning (creating new user accounts) is automatic and implicit.</span></span> <span data-ttu-id="3eae7-110">Lorsqu’un utilisateur effectuer une requête par rapport à l’API de référentiel pour la première fois, le référentiel crée un nouvel enregistrement d’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="3eae7-110">When a user make a request against Repository API for the first time, the repository creates a new User record.</span></span> 
  
<span data-ttu-id="3eae7-111">Appel de que tableau de bord qualité crée également automatiquement un utilisateur dédié des éléments pour le nouvel utilisateur.</span><span class="sxs-lookup"><span data-stu-id="3eae7-111">Call Quality Dashboard also automatically creates a user dedicated items for the new user.</span></span> <span data-ttu-id="3eae7-112">Les nouveaux éléments utilisateur dédiée sont des clones complètes d’éléments de l’utilisateur du système.</span><span class="sxs-lookup"><span data-stu-id="3eae7-112">The new user dedicated items are complete clones of system user's items.</span></span> <span data-ttu-id="3eae7-113">De cette façon, les utilisateurs démarrent avec leurs propres copies des rapports et des requêtes qu’ils peuvent immédiatement commencer à personnaliser.</span><span class="sxs-lookup"><span data-stu-id="3eae7-113">This way, users start with their own copies of Reports and Queries that they can immediately start customizing.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="3eae7-114">À l’aide d’appeler le tableau de bord qualité, utilisateurs peuvent réinitialiser leurs éléments dédiés à tout moment.</span><span class="sxs-lookup"><span data-stu-id="3eae7-114">Using Call Quality Dashboard, users can reset their dedicated items anytime.</span></span> 
  
 <span data-ttu-id="3eae7-115">**ID utilisateur spécial**</span><span class="sxs-lookup"><span data-stu-id="3eae7-115">**Special User IDs**</span></span>
  
<span data-ttu-id="3eae7-116">API de référentiel inclut d’autres API URIs qui attend un nombre entier pour spécifier un utilisateur particulier.</span><span class="sxs-lookup"><span data-stu-id="3eae7-116">Repository API includes REST API URIs that expects an integer value to specify a particular user.</span></span> <span data-ttu-id="3eae7-117">Exemple : `https://<portal>/QoERepositoryService/repository/user/{userId}`.</span><span class="sxs-lookup"><span data-stu-id="3eae7-117">Example:  `https://<portal>/QoERepositoryService/repository/user/{userId}`.</span></span> <span data-ttu-id="3eae7-118">Ici, {ID utilisateur} doit être remplacé par une valeur entière, telle que 0, 1, etc..</span><span class="sxs-lookup"><span data-stu-id="3eae7-118">Here, {userId} should be replaced by an integer value such as 0, 1, etc.</span></span>
  
<span data-ttu-id="3eae7-119">En outre, les API de référentiel accepte deux ID utilisateur spécial à {ID} utilisateur URI.</span><span class="sxs-lookup"><span data-stu-id="3eae7-119">Moreover, Repository API will accept two special user IDs at {userId} in URIs.</span></span>
  
-  <span data-ttu-id="3eae7-120">*par défaut* - représente l’utilisateur qui est en train d’interagir avec l’API.</span><span class="sxs-lookup"><span data-stu-id="3eae7-120">*default*  - represents the user who is currently interacting with the API.</span></span> <span data-ttu-id="3eae7-121">Cela permet aux applications d’accéder à des matières de l’utilisateur actuel sans assurer le suivi de la valeur de l’ID réel de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="3eae7-121">This allows applications to access current user's contents without keeping track of the actual user ID value.</span></span> <span data-ttu-id="3eae7-122">Exemple : ` https://<portal>/QoERepositoryService/repository/user/default`.</span><span class="sxs-lookup"><span data-stu-id="3eae7-122">Example: ` https://<portal>/QoERepositoryService/repository/user/default`.</span></span>
    
-  <span data-ttu-id="3eae7-123">*système* - représente l’utilisateur du système.</span><span class="sxs-lookup"><span data-stu-id="3eae7-123">*system*  - represents the system user.</span></span> <span data-ttu-id="3eae7-124">Cela permet aux applications d’accéder aux contenu de l’utilisateur sans connaître la valeur de l’ID réel de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="3eae7-124">This allows applications to access the system user's contents without knowing the actual user ID value.</span></span> <span data-ttu-id="3eae7-125">Exemple : `https://<portal>/QoERepositoryService/repository/user/system`.</span><span class="sxs-lookup"><span data-stu-id="3eae7-125">Example: `https://<portal>/QoERepositoryService/repository/user/system`.</span></span>
    
<span data-ttu-id="3eae7-126">Sauf mention contraire, les ID utilisateur spéciaux peuvent être utilisé à {utilisateur} dans les URI.</span><span class="sxs-lookup"><span data-stu-id="3eae7-126">Unless otherwise noted, the special user IDs can be used at {userId} in URIs.</span></span> 
  
<span data-ttu-id="3eae7-127">Les opérations de repos sont incluses dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="3eae7-127">The REST operations are included in the following table.</span></span>
  
|<span data-ttu-id="3eae7-128">**Opération**</span><span class="sxs-lookup"><span data-stu-id="3eae7-128">**Operation**</span></span>|<span data-ttu-id="3eae7-129">**Description**</span><span class="sxs-lookup"><span data-stu-id="3eae7-129">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="3eae7-130">Obtenir les utilisateurs</span><span class="sxs-lookup"><span data-stu-id="3eae7-130">Get Users</span></span>](get-users.md) <br/> |<span data-ttu-id="3eae7-131">Retourne une liste d’utilisateurs dans le référentiel.</span><span class="sxs-lookup"><span data-stu-id="3eae7-131">Returns a list of users in the repository.</span></span>  <br/> |
|[<span data-ttu-id="3eae7-132">Obtenir l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="3eae7-132">Get User</span></span>](get-user.md) <br/> |<span data-ttu-id="3eae7-133">Retourne un enregistrement d’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="3eae7-133">Returns a user record.</span></span>  <br/> |
   

