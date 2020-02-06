---
title: tblRoleType
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 1eac3a54-656a-40ac-b771-edfc64d6e34b
description: tblRoleType est une table de recherche statique avec les types de rôles et leurs jeux d’autorisations associés.
ms.openlocfilehash: 888628c1aca01e90694ed946569a81b1b7394b95
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812902"
---
# <a name="tblroletype"></a><span data-ttu-id="e9df2-103">tblRoleType</span><span class="sxs-lookup"><span data-stu-id="e9df2-103">tblRoleType</span></span>
 
<span data-ttu-id="e9df2-104">tblRoleType est une table de recherche statique avec les types de rôles et leurs jeux d’autorisations associés.</span><span class="sxs-lookup"><span data-stu-id="e9df2-104">tblRoleType is a static lookup table with role types and their associated permission sets.</span></span>
  
<span data-ttu-id="e9df2-105">**Celles**</span><span class="sxs-lookup"><span data-stu-id="e9df2-105">**Columns**</span></span>

|<span data-ttu-id="e9df2-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="e9df2-106">**Column**</span></span>|<span data-ttu-id="e9df2-107">**Type**</span><span class="sxs-lookup"><span data-stu-id="e9df2-107">**Type**</span></span>|<span data-ttu-id="e9df2-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="e9df2-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e9df2-109">rtypeID</span><span class="sxs-lookup"><span data-stu-id="e9df2-109">rtypeID</span></span>  <br/> |<span data-ttu-id="e9df2-110">ent, non null</span><span class="sxs-lookup"><span data-stu-id="e9df2-110">int, not null</span></span>  <br/> |<span data-ttu-id="e9df2-111">ID du type de rôle.</span><span class="sxs-lookup"><span data-stu-id="e9df2-111">Role type ID.</span></span>  <br/> |
|<span data-ttu-id="e9df2-112">rtypeDesc</span><span class="sxs-lookup"><span data-stu-id="e9df2-112">rtypeDesc</span></span>  <br/> |<span data-ttu-id="e9df2-113">nvarchar (256), pas null</span><span class="sxs-lookup"><span data-stu-id="e9df2-113">nvarchar (256), not null</span></span>  <br/> | <span data-ttu-id="e9df2-114">Description du type de rôle.</span><span class="sxs-lookup"><span data-stu-id="e9df2-114">Role type description.</span></span> <span data-ttu-id="e9df2-115">Il existe quatre rôles disponibles :</span><span class="sxs-lookup"><span data-stu-id="e9df2-115">There are four available roles:</span></span> <br/>  <span data-ttu-id="e9df2-116">Membre : membres de salle de conversation</span><span class="sxs-lookup"><span data-stu-id="e9df2-116">Member: Chat room member</span></span> <br/>  <span data-ttu-id="e9df2-117">Manager : gestionnaire de salle de conversation</span><span class="sxs-lookup"><span data-stu-id="e9df2-117">Manager: Chat room manager</span></span> <br/>  <span data-ttu-id="e9df2-118">Voix : présentateur pour une salle de conversation Auditorium</span><span class="sxs-lookup"><span data-stu-id="e9df2-118">Voiced: Presenter for an auditorium chat room</span></span> <br/>  <span data-ttu-id="e9df2-119">Créateur : peut créer des salles de conversation</span><span class="sxs-lookup"><span data-stu-id="e9df2-119">Creator: Can create chat rooms</span></span> <br/> |
|<span data-ttu-id="e9df2-120">rtypeAllowedPermSet</span><span class="sxs-lookup"><span data-stu-id="e9df2-120">rtypeAllowedPermSet</span></span>  <br/> |<span data-ttu-id="e9df2-121">bigint, pas null</span><span class="sxs-lookup"><span data-stu-id="e9df2-121">bigint, not null</span></span>  <br/> | <span data-ttu-id="e9df2-122">Autorisation définie pour le rôle.</span><span class="sxs-lookup"><span data-stu-id="e9df2-122">Permission set for the role.</span></span> <span data-ttu-id="e9df2-123">Les bits utilisés sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="e9df2-123">The used bits are:</span></span> <br/>  <span data-ttu-id="e9df2-124">2 : true si le rôle peut gérer des nœuds.</span><span class="sxs-lookup"><span data-stu-id="e9df2-124">2: True if the role can manage nodes.</span></span> <br/>  <span data-ttu-id="e9df2-125">4 : true si le rôle peut créer des nœuds enfants.</span><span class="sxs-lookup"><span data-stu-id="e9df2-125">4: True if the role can create children nodes.</span></span> <br/>  <span data-ttu-id="e9df2-126">7 : true si le rôle peut rejoindre une salle de conversation (ou des salles de conversation enfant d’une catégorie).</span><span class="sxs-lookup"><span data-stu-id="e9df2-126">7: True if the role can join a chat room (or children chat rooms of a category).</span></span> <br/>  <span data-ttu-id="e9df2-127">8 : true si le rôle peut discuter dans une salle de conversation (ou dans des salles de conversation enfant d’une catégorie).</span><span class="sxs-lookup"><span data-stu-id="e9df2-127">8: True if the role can chat in a chat room (or in children chat rooms of a category).</span></span> <br/>  <span data-ttu-id="e9df2-128">10 : true si le rôle peut lire l’historique des conversations même en l’absence de participation à une salle de conversation.</span><span class="sxs-lookup"><span data-stu-id="e9df2-128">10: True if the role can read chat history even when not joined to a chat room.</span></span> <br/>  <span data-ttu-id="e9df2-129">11 : true si le rôle peut voir la salle de conversation.</span><span class="sxs-lookup"><span data-stu-id="e9df2-129">11: True if the role can see the chat room.</span></span> <span data-ttu-id="e9df2-130">(Cette valeur est améliorée par des facteurs tels que Scope et Visibility.)</span><span class="sxs-lookup"><span data-stu-id="e9df2-130">(This is further refined by factors such as scope and visibility.)</span></span> <br/>  <span data-ttu-id="e9df2-131">12 : true si le rôle peut discuter dans une salle de conversation Auditorium.</span><span class="sxs-lookup"><span data-stu-id="e9df2-131">12: True if the role can chat in an auditorium chat room.</span></span> <br/>  <span data-ttu-id="e9df2-132">13 : true si le rôle peut ignorer les règles de visibilité lors de la consultation des nœuds.</span><span class="sxs-lookup"><span data-stu-id="e9df2-132">13: True if the role can bypass visibility rules when viewing nodes.</span></span> <br/> |
   
<span data-ttu-id="e9df2-133">**Clé**</span><span class="sxs-lookup"><span data-stu-id="e9df2-133">**Key**</span></span>

|<span data-ttu-id="e9df2-134">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="e9df2-134">**Column**</span></span>|<span data-ttu-id="e9df2-135">**Description**</span><span class="sxs-lookup"><span data-stu-id="e9df2-135">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e9df2-136">rtypeID</span><span class="sxs-lookup"><span data-stu-id="e9df2-136">rtypeID</span></span>  <br/> |<span data-ttu-id="e9df2-137">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="e9df2-137">Primary key.</span></span>  <br/> |
   

