---
title: tblRoleType
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1eac3a54-656a-40ac-b771-edfc64d6e34b
description: tblRoleType est une table de choix statique avec les types de rôles et leurs jeux d’autorisations.
ms.openlocfilehash: 6b5e545306c402fbfb89094a19799fe3ff6d2e34
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30883144"
---
# <a name="tblroletype"></a><span data-ttu-id="9cd31-103">tblRoleType</span><span class="sxs-lookup"><span data-stu-id="9cd31-103">tblRoleType</span></span>
 
<span data-ttu-id="9cd31-104">tblRoleType est une table de choix statique avec les types de rôles et leurs jeux d’autorisations.</span><span class="sxs-lookup"><span data-stu-id="9cd31-104">tblRoleType is a static lookup table with role types and their associated permission sets.</span></span>
  
<span data-ttu-id="9cd31-105">**Colonnes**</span><span class="sxs-lookup"><span data-stu-id="9cd31-105">**Columns**</span></span>

|<span data-ttu-id="9cd31-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="9cd31-106">**Column**</span></span>|<span data-ttu-id="9cd31-107">**Type**</span><span class="sxs-lookup"><span data-stu-id="9cd31-107">**Type**</span></span>|<span data-ttu-id="9cd31-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="9cd31-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="9cd31-109">rtypeID</span><span class="sxs-lookup"><span data-stu-id="9cd31-109">rtypeID</span></span>  <br/> |<span data-ttu-id="9cd31-110">int, non null</span><span class="sxs-lookup"><span data-stu-id="9cd31-110">int, not null</span></span>  <br/> |<span data-ttu-id="9cd31-111">ID de type de rôle.</span><span class="sxs-lookup"><span data-stu-id="9cd31-111">Role type ID.</span></span>  <br/> |
|<span data-ttu-id="9cd31-112">rtypeDesc</span><span class="sxs-lookup"><span data-stu-id="9cd31-112">rtypeDesc</span></span>  <br/> |<span data-ttu-id="9cd31-113">nvarchar (256), non null</span><span class="sxs-lookup"><span data-stu-id="9cd31-113">nvarchar (256), not null</span></span>  <br/> | <span data-ttu-id="9cd31-114">Description du type de rôle.</span><span class="sxs-lookup"><span data-stu-id="9cd31-114">Role type description.</span></span> <span data-ttu-id="9cd31-115">Il existe quatre rôles disponibles :</span><span class="sxs-lookup"><span data-stu-id="9cd31-115">There are four available roles:</span></span> <br/>  <span data-ttu-id="9cd31-116">: Membres salle de conversation</span><span class="sxs-lookup"><span data-stu-id="9cd31-116">Member: Chat room member</span></span> <br/>  <span data-ttu-id="9cd31-117">: Gestionnaire salle de conversation</span><span class="sxs-lookup"><span data-stu-id="9cd31-117">Manager: Chat room manager</span></span> <br/>  <span data-ttu-id="9cd31-118">Membre sonore : Le présentateur pour une salle de conversation de type auditorium</span><span class="sxs-lookup"><span data-stu-id="9cd31-118">Voiced: Presenter for an auditorium chat room</span></span> <br/>  <span data-ttu-id="9cd31-119">Créateur : Peut créer des salles de conversation</span><span class="sxs-lookup"><span data-stu-id="9cd31-119">Creator: Can create chat rooms</span></span> <br/> |
|<span data-ttu-id="9cd31-120">rtypeAllowedPermSet</span><span class="sxs-lookup"><span data-stu-id="9cd31-120">rtypeAllowedPermSet</span></span>  <br/> |<span data-ttu-id="9cd31-121">bigint, non null</span><span class="sxs-lookup"><span data-stu-id="9cd31-121">bigint, not null</span></span>  <br/> | <span data-ttu-id="9cd31-122">Jeu d’autorisations pour le rôle.</span><span class="sxs-lookup"><span data-stu-id="9cd31-122">Permission set for the role.</span></span> <span data-ttu-id="9cd31-123">Les fichiers binaires utilisés sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="9cd31-123">The used bits are:</span></span> <br/>  <span data-ttu-id="9cd31-124">2 : true si le rôle peut gérer des nœuds.</span><span class="sxs-lookup"><span data-stu-id="9cd31-124">2: True if the role can manage nodes.</span></span> <br/>  <span data-ttu-id="9cd31-125">4 : true si le rôle peut créer des nœuds enfants.</span><span class="sxs-lookup"><span data-stu-id="9cd31-125">4: True if the role can create children nodes.</span></span> <br/>  <span data-ttu-id="9cd31-126">7 : true si le rôle peut rejoindre une salle de conversation (ou les salles de conversation enfants d’une catégorie).</span><span class="sxs-lookup"><span data-stu-id="9cd31-126">7: True if the role can join a chat room (or children chat rooms of a category).</span></span> <br/>  <span data-ttu-id="9cd31-127">8 : true si le rôle peut converser dans une salle de conversation (ou dans les salles de conversation enfants d’une catégorie).</span><span class="sxs-lookup"><span data-stu-id="9cd31-127">8: True if the role can chat in a chat room (or in children chat rooms of a category).</span></span> <br/>  <span data-ttu-id="9cd31-128">10 : true si le rôle peut lire l’historique des conversations même lorsque ne pas lié à une salle de conversation.</span><span class="sxs-lookup"><span data-stu-id="9cd31-128">10: True if the role can read chat history even when not joined to a chat room.</span></span> <br/>  <span data-ttu-id="9cd31-129">11 : true si le rôle peut voir la salle de conversation.</span><span class="sxs-lookup"><span data-stu-id="9cd31-129">11: True if the role can see the chat room.</span></span> <span data-ttu-id="9cd31-130">(Il est affiné par facteurs, tels que l’étendue et la visibilité.)</span><span class="sxs-lookup"><span data-stu-id="9cd31-130">(This is further refined by factors such as scope and visibility.)</span></span> <br/>  <span data-ttu-id="9cd31-131">12 : true si le rôle peut converser dans une salle de conversation de type auditorium.</span><span class="sxs-lookup"><span data-stu-id="9cd31-131">12: True if the role can chat in an auditorium chat room.</span></span> <br/>  <span data-ttu-id="9cd31-132">13 : true si le rôle peut contourner les règles de visibilité lors de l’affichage des nœuds.</span><span class="sxs-lookup"><span data-stu-id="9cd31-132">13: True if the role can bypass visibility rules when viewing nodes.</span></span> <br/> |
   
<span data-ttu-id="9cd31-133">**Clé**</span><span class="sxs-lookup"><span data-stu-id="9cd31-133">**Key**</span></span>

|<span data-ttu-id="9cd31-134">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="9cd31-134">**Column**</span></span>|<span data-ttu-id="9cd31-135">**Description**</span><span class="sxs-lookup"><span data-stu-id="9cd31-135">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="9cd31-136">rtypeID</span><span class="sxs-lookup"><span data-stu-id="9cd31-136">rtypeID</span></span>  <br/> |<span data-ttu-id="9cd31-137">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="9cd31-137">Primary key.</span></span>  <br/> |
   

