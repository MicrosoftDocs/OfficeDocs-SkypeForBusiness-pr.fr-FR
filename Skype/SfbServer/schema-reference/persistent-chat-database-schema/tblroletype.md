---
title: tblRoleType
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1eac3a54-656a-40ac-b771-edfc64d6e34b
description: tblRoleType est une table de recherche statiques avec les types de rôles et de leurs jeux d’autorisations associés.
ms.openlocfilehash: 2a380539c547f4ba6eb911f7e5247056c59a73ca
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="tblroletype"></a><span data-ttu-id="f6391-103">tblRoleType</span><span class="sxs-lookup"><span data-stu-id="f6391-103">tblRoleType</span></span>
 
<span data-ttu-id="f6391-104">tblRoleType est une table de recherche statiques avec les types de rôles et de leurs jeux d’autorisations associés.</span><span class="sxs-lookup"><span data-stu-id="f6391-104">tblRoleType is a static lookup table with role types and their associated permission sets.</span></span>
  
<span data-ttu-id="f6391-105">**Colonnes**</span><span class="sxs-lookup"><span data-stu-id="f6391-105">**Columns**</span></span>

|<span data-ttu-id="f6391-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="f6391-106">**Column**</span></span>|<span data-ttu-id="f6391-107">**Type de**</span><span class="sxs-lookup"><span data-stu-id="f6391-107">**Type**</span></span>|<span data-ttu-id="f6391-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="f6391-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f6391-109">rtypeID</span><span class="sxs-lookup"><span data-stu-id="f6391-109">rtypeID</span></span>  <br/> |<span data-ttu-id="f6391-110">int, non null</span><span class="sxs-lookup"><span data-stu-id="f6391-110">int, not null</span></span>  <br/> |<span data-ttu-id="f6391-111">ID de type de rôle.</span><span class="sxs-lookup"><span data-stu-id="f6391-111">Role type ID.</span></span>  <br/> |
|<span data-ttu-id="f6391-112">rtypeDesc</span><span class="sxs-lookup"><span data-stu-id="f6391-112">rtypeDesc</span></span>  <br/> |<span data-ttu-id="f6391-113">nvarchar (256), non null</span><span class="sxs-lookup"><span data-stu-id="f6391-113">nvarchar (256), not null</span></span>  <br/> | <span data-ttu-id="f6391-114">Description du type de rôle.</span><span class="sxs-lookup"><span data-stu-id="f6391-114">Role type description.</span></span> <span data-ttu-id="f6391-115">Il existe quatre rôles disponibles :</span><span class="sxs-lookup"><span data-stu-id="f6391-115">There are four available roles:</span></span> <br/>  <span data-ttu-id="f6391-116">: Membres salle de conversation</span><span class="sxs-lookup"><span data-stu-id="f6391-116">Member: Chat room member</span></span> <br/>  <span data-ttu-id="f6391-117">: Gestionnaire salle de conversation</span><span class="sxs-lookup"><span data-stu-id="f6391-117">Manager: Chat room manager</span></span> <br/>  <span data-ttu-id="f6391-118">Voisé : Le présentateur pour une salle de conversation auditorium</span><span class="sxs-lookup"><span data-stu-id="f6391-118">Voiced: Presenter for an auditorium chat room</span></span> <br/>  <span data-ttu-id="f6391-119">Créateur : Peut créer des salles de conversation</span><span class="sxs-lookup"><span data-stu-id="f6391-119">Creator: Can create chat rooms</span></span> <br/> |
|<span data-ttu-id="f6391-120">rtypeAllowedPermSet</span><span class="sxs-lookup"><span data-stu-id="f6391-120">rtypeAllowedPermSet</span></span>  <br/> |<span data-ttu-id="f6391-121">bigint, non null</span><span class="sxs-lookup"><span data-stu-id="f6391-121">bigint, not null</span></span>  <br/> | <span data-ttu-id="f6391-122">Jeu d’autorisations pour le rôle.</span><span class="sxs-lookup"><span data-stu-id="f6391-122">Permission set for the role.</span></span> <span data-ttu-id="f6391-123">Les bits utilisés sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="f6391-123">The used bits are:</span></span> <br/>  <span data-ttu-id="f6391-124">2 : true si le rôle peut gérer des nœuds.</span><span class="sxs-lookup"><span data-stu-id="f6391-124">2: True if the role can manage nodes.</span></span> <br/>  <span data-ttu-id="f6391-125">4 : true si le rôle peut créer des nœuds enfants.</span><span class="sxs-lookup"><span data-stu-id="f6391-125">4: True if the role can create children nodes.</span></span> <br/>  <span data-ttu-id="f6391-126">7 : true si le rôle peut rejoindre une salle de conversation (ou salles de conversation enfants d’une catégorie).</span><span class="sxs-lookup"><span data-stu-id="f6391-126">7: True if the role can join a chat room (or children chat rooms of a category).</span></span> <br/>  <span data-ttu-id="f6391-127">8 : true si le rôle peut discuter dans une salle de conversation (ou dans les salles de conversation enfants d’une catégorie).</span><span class="sxs-lookup"><span data-stu-id="f6391-127">8: True if the role can chat in a chat room (or in children chat rooms of a category).</span></span> <br/>  <span data-ttu-id="f6391-128">10 : true si le rôle peut lire l’historique de conversation même si ne pas connecté à une salle de conversation.</span><span class="sxs-lookup"><span data-stu-id="f6391-128">10: True if the role can read chat history even when not joined to a chat room.</span></span> <br/>  <span data-ttu-id="f6391-129">11 : true si le rôle peut voir la salle de conversation.</span><span class="sxs-lookup"><span data-stu-id="f6391-129">11: True if the role can see the chat room.</span></span> <span data-ttu-id="f6391-130">(Il est affiné par des facteurs tels que la portée et visibilité.)</span><span class="sxs-lookup"><span data-stu-id="f6391-130">(This is further refined by factors such as scope and visibility.)</span></span> <br/>  <span data-ttu-id="f6391-131">12 : true si le rôle peut discuter dans une salle de conversation auditorium.</span><span class="sxs-lookup"><span data-stu-id="f6391-131">12: True if the role can chat in an auditorium chat room.</span></span> <br/>  <span data-ttu-id="f6391-132">13 : true si le rôle peut ignorer les règles de visibilité lors de l’affichage de nœuds.</span><span class="sxs-lookup"><span data-stu-id="f6391-132">13: True if the role can bypass visibility rules when viewing nodes.</span></span> <br/> |
   
<span data-ttu-id="f6391-133">**Clé**</span><span class="sxs-lookup"><span data-stu-id="f6391-133">**Key**</span></span>

|<span data-ttu-id="f6391-134">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="f6391-134">**Column**</span></span>|<span data-ttu-id="f6391-135">**Description**</span><span class="sxs-lookup"><span data-stu-id="f6391-135">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="f6391-136">rtypeID</span><span class="sxs-lookup"><span data-stu-id="f6391-136">rtypeID</span></span>  <br/> |<span data-ttu-id="f6391-137">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="f6391-137">Primary key.</span></span>  <br/> |
   

