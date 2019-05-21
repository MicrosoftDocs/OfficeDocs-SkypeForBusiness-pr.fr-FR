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
localization_priority: Normal
ms.assetid: 1eac3a54-656a-40ac-b771-edfc64d6e34b
description: tblRoleType est une table de recherche statique avec les types de rôles et leurs jeux d’autorisations associés.
ms.openlocfilehash: 8d49e9f2c61b8672a01a9c77bcc825925a4e7b2b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295215"
---
# <a name="tblroletype"></a><span data-ttu-id="63db8-103">tblRoleType</span><span class="sxs-lookup"><span data-stu-id="63db8-103">tblRoleType</span></span>
 
<span data-ttu-id="63db8-104">tblRoleType est une table de recherche statique avec les types de rôles et leurs jeux d’autorisations associés.</span><span class="sxs-lookup"><span data-stu-id="63db8-104">tblRoleType is a static lookup table with role types and their associated permission sets.</span></span>
  
<span data-ttu-id="63db8-105">**Celles**</span><span class="sxs-lookup"><span data-stu-id="63db8-105">**Columns**</span></span>

|<span data-ttu-id="63db8-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="63db8-106">**Column**</span></span>|<span data-ttu-id="63db8-107">**Type**</span><span class="sxs-lookup"><span data-stu-id="63db8-107">**Type**</span></span>|<span data-ttu-id="63db8-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="63db8-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="63db8-109">rtypeID</span><span class="sxs-lookup"><span data-stu-id="63db8-109">rtypeID</span></span>  <br/> |<span data-ttu-id="63db8-110">ent, non null</span><span class="sxs-lookup"><span data-stu-id="63db8-110">int, not null</span></span>  <br/> |<span data-ttu-id="63db8-111">ID du type de rôle.</span><span class="sxs-lookup"><span data-stu-id="63db8-111">Role type ID.</span></span>  <br/> |
|<span data-ttu-id="63db8-112">rtypeDesc</span><span class="sxs-lookup"><span data-stu-id="63db8-112">rtypeDesc</span></span>  <br/> |<span data-ttu-id="63db8-113">nvarchar (256), pas null</span><span class="sxs-lookup"><span data-stu-id="63db8-113">nvarchar (256), not null</span></span>  <br/> | <span data-ttu-id="63db8-114">Description du type de rôle.</span><span class="sxs-lookup"><span data-stu-id="63db8-114">Role type description.</span></span> <span data-ttu-id="63db8-115">Il existe quatre rôles disponibles:</span><span class="sxs-lookup"><span data-stu-id="63db8-115">There are four available roles:</span></span> <br/>  <span data-ttu-id="63db8-116">Membre: membres de salle de conversation</span><span class="sxs-lookup"><span data-stu-id="63db8-116">Member: Chat room member</span></span> <br/>  <span data-ttu-id="63db8-117">Manager: gestionnaire de salle de conversation</span><span class="sxs-lookup"><span data-stu-id="63db8-117">Manager: Chat room manager</span></span> <br/>  <span data-ttu-id="63db8-118">Voix: présentateur pour une salle de conversation Auditorium</span><span class="sxs-lookup"><span data-stu-id="63db8-118">Voiced: Presenter for an auditorium chat room</span></span> <br/>  <span data-ttu-id="63db8-119">Créateur: peut créer des salles de conversation</span><span class="sxs-lookup"><span data-stu-id="63db8-119">Creator: Can create chat rooms</span></span> <br/> |
|<span data-ttu-id="63db8-120">rtypeAllowedPermSet</span><span class="sxs-lookup"><span data-stu-id="63db8-120">rtypeAllowedPermSet</span></span>  <br/> |<span data-ttu-id="63db8-121">bigint, pas null</span><span class="sxs-lookup"><span data-stu-id="63db8-121">bigint, not null</span></span>  <br/> | <span data-ttu-id="63db8-122">Autorisation définie pour le rôle.</span><span class="sxs-lookup"><span data-stu-id="63db8-122">Permission set for the role.</span></span> <span data-ttu-id="63db8-123">Les bits utilisés sont les suivants:</span><span class="sxs-lookup"><span data-stu-id="63db8-123">The used bits are:</span></span> <br/>  <span data-ttu-id="63db8-124">2: true si le rôle peut gérer des nœuds.</span><span class="sxs-lookup"><span data-stu-id="63db8-124">2: True if the role can manage nodes.</span></span> <br/>  <span data-ttu-id="63db8-125">4: true si le rôle peut créer des nœuds enfants.</span><span class="sxs-lookup"><span data-stu-id="63db8-125">4: True if the role can create children nodes.</span></span> <br/>  <span data-ttu-id="63db8-126">7: true si le rôle peut rejoindre une salle de conversation (ou des salles de conversation enfant d’une catégorie).</span><span class="sxs-lookup"><span data-stu-id="63db8-126">7: True if the role can join a chat room (or children chat rooms of a category).</span></span> <br/>  <span data-ttu-id="63db8-127">8: true si le rôle peut discuter dans une salle de conversation (ou dans des salles de conversation enfant d’une catégorie).</span><span class="sxs-lookup"><span data-stu-id="63db8-127">8: True if the role can chat in a chat room (or in children chat rooms of a category).</span></span> <br/>  <span data-ttu-id="63db8-128">10: true si le rôle peut lire l’historique des conversations même en l’absence de participation à une salle de conversation.</span><span class="sxs-lookup"><span data-stu-id="63db8-128">10: True if the role can read chat history even when not joined to a chat room.</span></span> <br/>  <span data-ttu-id="63db8-129">11: true si le rôle peut voir la salle de conversation.</span><span class="sxs-lookup"><span data-stu-id="63db8-129">11: True if the role can see the chat room.</span></span> <span data-ttu-id="63db8-130">(Cette valeur est améliorée par des facteurs tels que Scope et Visibility.)</span><span class="sxs-lookup"><span data-stu-id="63db8-130">(This is further refined by factors such as scope and visibility.)</span></span> <br/>  <span data-ttu-id="63db8-131">12: true si le rôle peut discuter dans une salle de conversation Auditorium.</span><span class="sxs-lookup"><span data-stu-id="63db8-131">12: True if the role can chat in an auditorium chat room.</span></span> <br/>  <span data-ttu-id="63db8-132">13: true si le rôle peut ignorer les règles de visibilité lors de la consultation des nœuds.</span><span class="sxs-lookup"><span data-stu-id="63db8-132">13: True if the role can bypass visibility rules when viewing nodes.</span></span> <br/> |
   
<span data-ttu-id="63db8-133">**Clé**</span><span class="sxs-lookup"><span data-stu-id="63db8-133">**Key**</span></span>

|<span data-ttu-id="63db8-134">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="63db8-134">**Column**</span></span>|<span data-ttu-id="63db8-135">**Description**</span><span class="sxs-lookup"><span data-stu-id="63db8-135">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="63db8-136">rtypeID</span><span class="sxs-lookup"><span data-stu-id="63db8-136">rtypeID</span></span>  <br/> |<span data-ttu-id="63db8-137">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="63db8-137">Primary key.</span></span>  <br/> |
   

