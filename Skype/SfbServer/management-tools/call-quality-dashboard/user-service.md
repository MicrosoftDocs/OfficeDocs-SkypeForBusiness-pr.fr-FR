---
title: Service utilisateur pour le CQD
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
ms.assetid: abd5c828-42dd-4f48-bf87-29993193cb3a
description: 'Résumé : Découvrez le service utilisateur, qui fait partie de l’API référentiel pour le tableau de bord de qualité des appels. Le Tableau de bord de qualité des appels est un outil pour Skype Entreprise Server.'
ms.openlocfilehash: d9f4b771a1bf5efeece4f8fb87195d8567f0426e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803074"
---
# <a name="user-service-for-cqd"></a><span data-ttu-id="82aaa-104">Service utilisateur pour le CQD</span><span class="sxs-lookup"><span data-stu-id="82aaa-104">User Service for CQD</span></span>
 
<span data-ttu-id="82aaa-105">**Résumé :** Découvrez le service utilisateur, qui fait partie de l’API référentiel pour le tableau de bord de qualité des appels.</span><span class="sxs-lookup"><span data-stu-id="82aaa-105">**Summary:** Learn about the User Service, which is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="82aaa-106">Le Tableau de bord de qualité des appels est un outil pour Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="82aaa-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="82aaa-107">Le service utilisateur fait partie de l’API référentiel pour le tableau de bord de qualité des appels.</span><span class="sxs-lookup"><span data-stu-id="82aaa-107">The User Service is part of the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="user-service"></a><span data-ttu-id="82aaa-108">Service destiné aux utilisateurs</span><span class="sxs-lookup"><span data-stu-id="82aaa-108">User Service</span></span>

<span data-ttu-id="82aaa-109">L’API de référentiel fournit un modèle de gestion des utilisateurs simplifié dans lequel la mise en service des utilisateurs (création de comptes d’utilisateurs) est automatique et implicite.</span><span class="sxs-lookup"><span data-stu-id="82aaa-109">Repository API provides a simplified user management model where user provisioning (creating new user accounts) is automatic and implicit.</span></span> <span data-ttu-id="82aaa-110">Lorsqu’un utilisateur fait une demande par rapport à l’API du référentiel pour la première fois, le référentiel crée un nouvel enregistrement d’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="82aaa-110">When a user make a request against Repository API for the first time, the repository creates a new User record.</span></span> 
  
<span data-ttu-id="82aaa-111">Le Tableau de bord de qualité des appels crée également automatiquement des éléments dédiés par l’utilisateur pour le nouvel utilisateur.</span><span class="sxs-lookup"><span data-stu-id="82aaa-111">Call Quality Dashboard also automatically creates a user dedicated items for the new user.</span></span> <span data-ttu-id="82aaa-112">Les nouveaux éléments dédiés aux utilisateurs sont des clones complets des éléments de l’utilisateur système.</span><span class="sxs-lookup"><span data-stu-id="82aaa-112">The new user dedicated items are complete clones of system user's items.</span></span> <span data-ttu-id="82aaa-113">Ainsi, les utilisateurs commencent par leurs propres copies de rapports et de requêtes qu’ils peuvent immédiatement personnaliser.</span><span class="sxs-lookup"><span data-stu-id="82aaa-113">This way, users start with their own copies of Reports and Queries that they can immediately start customizing.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="82aaa-114">À l’aide du Tableau de bord de qualité des appels, les utilisateurs peuvent réinitialiser leurs éléments dédiés à tout moment.</span><span class="sxs-lookup"><span data-stu-id="82aaa-114">Using Call Quality Dashboard, users can reset their dedicated items anytime.</span></span> 
  
 <span data-ttu-id="82aaa-115">**ID d’utilisateur spéciaux**</span><span class="sxs-lookup"><span data-stu-id="82aaa-115">**Special User IDs**</span></span>
  
<span data-ttu-id="82aaa-116">L’API de référentiel inclut les UR DE L’API REST qui s’attendent à ce qu’une valeur d’ensemble spécifie un utilisateur particulier.</span><span class="sxs-lookup"><span data-stu-id="82aaa-116">Repository API includes REST API URIs that expects an integer value to specify a particular user.</span></span> <span data-ttu-id="82aaa-117">Exemple :  `https://<portal>/QoERepositoryService/repository/user/{userId}` .</span><span class="sxs-lookup"><span data-stu-id="82aaa-117">Example:  `https://<portal>/QoERepositoryService/repository/user/{userId}`.</span></span> <span data-ttu-id="82aaa-118">Ici, {userId} doit être remplacé par une valeur de type 0, 1, etc.</span><span class="sxs-lookup"><span data-stu-id="82aaa-118">Here, {userId} should be replaced by an integer value such as 0, 1, etc.</span></span>
  
<span data-ttu-id="82aaa-119">En outre, l’API de référentiel accepte deux ID d’utilisateur spéciaux sur {userId} dans les UR.</span><span class="sxs-lookup"><span data-stu-id="82aaa-119">Moreover, Repository API will accept two special user IDs at {userId} in URIs.</span></span>
  
-  <span data-ttu-id="82aaa-120">*par*  défaut : représente l’utilisateur qui interagit actuellement avec l’API.</span><span class="sxs-lookup"><span data-stu-id="82aaa-120">*default*  - represents the user who is currently interacting with the API.</span></span> <span data-ttu-id="82aaa-121">Cela permet aux applications d’accéder au contenu de l’utilisateur actuel sans suivre la valeur réelle de l’ID utilisateur.</span><span class="sxs-lookup"><span data-stu-id="82aaa-121">This allows applications to access current user's contents without keeping track of the actual user ID value.</span></span> <span data-ttu-id="82aaa-122">Exemple : `https://<portal>/QoERepositoryService/repository/user/default`.</span><span class="sxs-lookup"><span data-stu-id="82aaa-122">Example: `https://<portal>/QoERepositoryService/repository/user/default`.</span></span>
    
-  <span data-ttu-id="82aaa-123">*system*  - représente l’utilisateur système.</span><span class="sxs-lookup"><span data-stu-id="82aaa-123">*system*  - represents the system user.</span></span> <span data-ttu-id="82aaa-124">Cela permet aux applications d’accéder au contenu de l’utilisateur système sans connaître la valeur réelle de l’ID utilisateur.</span><span class="sxs-lookup"><span data-stu-id="82aaa-124">This allows applications to access the system user's contents without knowing the actual user ID value.</span></span> <span data-ttu-id="82aaa-125">Exemple : `https://<portal>/QoERepositoryService/repository/user/system`.</span><span class="sxs-lookup"><span data-stu-id="82aaa-125">Example: `https://<portal>/QoERepositoryService/repository/user/system`.</span></span>
    
<span data-ttu-id="82aaa-126">Sauf indication contraire, les ID d’utilisateur spéciaux peuvent être utilisés à l’adresse {userId} dans les UR.</span><span class="sxs-lookup"><span data-stu-id="82aaa-126">Unless otherwise noted, the special user IDs can be used at {userId} in URIs.</span></span> 
  
<span data-ttu-id="82aaa-127">Les opérations REST sont incluses dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="82aaa-127">The REST operations are included in the following table.</span></span>
  
|<span data-ttu-id="82aaa-128">**Opération**</span><span class="sxs-lookup"><span data-stu-id="82aaa-128">**Operation**</span></span>|<span data-ttu-id="82aaa-129">**Description**</span><span class="sxs-lookup"><span data-stu-id="82aaa-129">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="82aaa-130">Obtenir les utilisateurs</span><span class="sxs-lookup"><span data-stu-id="82aaa-130">Get Users</span></span>](get-users.md) <br/> |<span data-ttu-id="82aaa-131">Renvoie une liste d’utilisateurs dans le référentiel.</span><span class="sxs-lookup"><span data-stu-id="82aaa-131">Returns a list of users in the repository.</span></span>  <br/> |
|[<span data-ttu-id="82aaa-132">Obtenir un utilisateur</span><span class="sxs-lookup"><span data-stu-id="82aaa-132">Get User</span></span>](get-user.md) <br/> |<span data-ttu-id="82aaa-133">Renvoie un enregistrement utilisateur.</span><span class="sxs-lookup"><span data-stu-id="82aaa-133">Returns a user record.</span></span>  <br/> |
   

