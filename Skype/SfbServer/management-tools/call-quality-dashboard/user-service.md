---
title: Service utilisateur pour CQD
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: abd5c828-42dd-4f48-bf87-29993193cb3a
description: 'Résumé : En savoir plus sur le Service de l’utilisateur, qui fait partie de l’API de référentiel pour appeler le tableau de bord qualité. Tableau de bord de qualité des appels est un outil de Skype pour Business Server.'
ms.openlocfilehash: 4ee4594e86b14655c94472b516b9e04da674e3f0
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32217641"
---
# <a name="user-service-for-cqd"></a><span data-ttu-id="b68fe-104">Service utilisateur pour CQD</span><span class="sxs-lookup"><span data-stu-id="b68fe-104">User Service for CQD</span></span>
 
<span data-ttu-id="b68fe-105">**Résumé :** Obtenir des informations sur le Service de l’utilisateur, qui fait partie de l’API de référentiel pour appeler le tableau de bord qualité.</span><span class="sxs-lookup"><span data-stu-id="b68fe-105">**Summary:** Learn about the User Service, which is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="b68fe-106">Tableau de bord de qualité des appels est un outil de Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="b68fe-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="b68fe-107">Le Service de l’utilisateur fait partie de l’API de référentiel pour appeler le tableau de bord qualité.</span><span class="sxs-lookup"><span data-stu-id="b68fe-107">The User Service is part of the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="user-service"></a><span data-ttu-id="b68fe-108">Service destiné aux utilisateurs</span><span class="sxs-lookup"><span data-stu-id="b68fe-108">User Service</span></span>

<span data-ttu-id="b68fe-109">API de référentiel fournit un modèle de gestion simplifiée utilisateur où l’utilisateur (création de nouveaux comptes d’utilisateurs) de la mise en service est automatique et implicite.</span><span class="sxs-lookup"><span data-stu-id="b68fe-109">Repository API provides a simplified user management model where user provisioning (creating new user accounts) is automatic and implicit.</span></span> <span data-ttu-id="b68fe-110">Lorsqu’un utilisateur effectuer une requête par rapport à l’API de référentiel pour la première fois, le référentiel crée un nouvel enregistrement d’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="b68fe-110">When a user make a request against Repository API for the first time, the repository creates a new User record.</span></span> 
  
<span data-ttu-id="b68fe-111">Appel de que tableau de bord qualité crée automatiquement un utilisateur dédiée des éléments pour le nouvel utilisateur.</span><span class="sxs-lookup"><span data-stu-id="b68fe-111">Call Quality Dashboard also automatically creates a user dedicated items for the new user.</span></span> <span data-ttu-id="b68fe-112">Les nouveaux éléments utilisateur dédiée sont clones complètes d’éléments de l’utilisateur du système.</span><span class="sxs-lookup"><span data-stu-id="b68fe-112">The new user dedicated items are complete clones of system user's items.</span></span> <span data-ttu-id="b68fe-113">Ainsi, les utilisateurs commencent avec leurs propres copies des rapports et des requêtes qu’ils peuvent démarrer immédiatement personnalisation.</span><span class="sxs-lookup"><span data-stu-id="b68fe-113">This way, users start with their own copies of Reports and Queries that they can immediately start customizing.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="b68fe-114">À l’aide du tableau de bord qualité des appels, les utilisateurs peuvent réinitialiser leurs éléments dédiés à tout moment.</span><span class="sxs-lookup"><span data-stu-id="b68fe-114">Using Call Quality Dashboard, users can reset their dedicated items anytime.</span></span> 
  
 <span data-ttu-id="b68fe-115">**ID d’utilisateur spéciaux**</span><span class="sxs-lookup"><span data-stu-id="b68fe-115">**Special User IDs**</span></span>
  
<span data-ttu-id="b68fe-116">API de référentiel inclut URIs REST API qui attend une valeur entière pour spécifier un utilisateur particulier.</span><span class="sxs-lookup"><span data-stu-id="b68fe-116">Repository API includes REST API URIs that expects an integer value to specify a particular user.</span></span> <span data-ttu-id="b68fe-117">Exemple : `https://<portal>/QoERepositoryService/repository/user/{userId}`.</span><span class="sxs-lookup"><span data-stu-id="b68fe-117">Example:  `https://<portal>/QoERepositoryService/repository/user/{userId}`.</span></span> <span data-ttu-id="b68fe-118">Ici, {userId} doit être remplacée par une valeur entière, telles que 0, 1, etc..</span><span class="sxs-lookup"><span data-stu-id="b68fe-118">Here, {userId} should be replaced by an integer value such as 0, 1, etc.</span></span>
  
<span data-ttu-id="b68fe-119">En outre, les API de référentiel accepte deux ID d’utilisateur spéciaux à {userId} dans les URI.</span><span class="sxs-lookup"><span data-stu-id="b68fe-119">Moreover, Repository API will accept two special user IDs at {userId} in URIs.</span></span>
  
-  <span data-ttu-id="b68fe-120">*par défaut* - représente l’utilisateur qui est en train d’interagir avec l’API.</span><span class="sxs-lookup"><span data-stu-id="b68fe-120">*default*  - represents the user who is currently interacting with the API.</span></span> <span data-ttu-id="b68fe-121">Cela permet aux applications d’accéder à contenu de l’utilisateur actuel sans suivi de la valeur d’ID réel de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="b68fe-121">This allows applications to access current user's contents without keeping track of the actual user ID value.</span></span> <span data-ttu-id="b68fe-122">Exemple : ` https://<portal>/QoERepositoryService/repository/user/default`.</span><span class="sxs-lookup"><span data-stu-id="b68fe-122">Example: ` https://<portal>/QoERepositoryService/repository/user/default`.</span></span>
    
-  <span data-ttu-id="b68fe-123">*système* - représente l’utilisateur du système.</span><span class="sxs-lookup"><span data-stu-id="b68fe-123">*system*  - represents the system user.</span></span> <span data-ttu-id="b68fe-124">Cela permet aux applications d’accéder à contenu de l’utilisateur sans connaître la valeur d’ID réel de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="b68fe-124">This allows applications to access the system user's contents without knowing the actual user ID value.</span></span> <span data-ttu-id="b68fe-125">Exemple : `https://<portal>/QoERepositoryService/repository/user/system`.</span><span class="sxs-lookup"><span data-stu-id="b68fe-125">Example: `https://<portal>/QoERepositoryService/repository/user/system`.</span></span>
    
<span data-ttu-id="b68fe-126">Sauf indication contraire, les ID utilisateur spéciaux peuvent être utilisée à {userId} dans les URI.</span><span class="sxs-lookup"><span data-stu-id="b68fe-126">Unless otherwise noted, the special user IDs can be used at {userId} in URIs.</span></span> 
  
<span data-ttu-id="b68fe-127">Les opérations REST sont incluses dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="b68fe-127">The REST operations are included in the following table.</span></span>
  
|<span data-ttu-id="b68fe-128">**Opération**</span><span class="sxs-lookup"><span data-stu-id="b68fe-128">**Operation**</span></span>|<span data-ttu-id="b68fe-129">**Description**</span><span class="sxs-lookup"><span data-stu-id="b68fe-129">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="b68fe-130">Obtenir les utilisateurs</span><span class="sxs-lookup"><span data-stu-id="b68fe-130">Get Users</span></span>](get-users.md) <br/> |<span data-ttu-id="b68fe-131">Renvoie une liste d’utilisateurs dans le référentiel.</span><span class="sxs-lookup"><span data-stu-id="b68fe-131">Returns a list of users in the repository.</span></span>  <br/> |
|[<span data-ttu-id="b68fe-132">Obtenir un utilisateur</span><span class="sxs-lookup"><span data-stu-id="b68fe-132">Get User</span></span>](get-user.md) <br/> |<span data-ttu-id="b68fe-133">Renvoie un enregistrement d’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="b68fe-133">Returns a user record.</span></span>  <br/> |
   

