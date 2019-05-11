---
title: tblRoleType
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1eac3a54-656a-40ac-b771-edfc64d6e34b
description: tblRoleType est une table de choix statique avec les types de rôles et leurs jeux d’autorisations.
ms.openlocfilehash: 074b65d3f701d122bbb311da3096e6727dd17264
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33924962"
---
# <a name="tblroletype"></a><span data-ttu-id="0e12c-103">tblRoleType</span><span class="sxs-lookup"><span data-stu-id="0e12c-103">tblRoleType</span></span>
 
<span data-ttu-id="0e12c-104">tblRoleType est une table de choix statique avec les types de rôles et leurs jeux d’autorisations.</span><span class="sxs-lookup"><span data-stu-id="0e12c-104">tblRoleType is a static lookup table with role types and their associated permission sets.</span></span>
  
<span data-ttu-id="0e12c-105">**Colonnes**</span><span class="sxs-lookup"><span data-stu-id="0e12c-105">**Columns**</span></span>

|<span data-ttu-id="0e12c-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="0e12c-106">**Column**</span></span>|<span data-ttu-id="0e12c-107">**Type**</span><span class="sxs-lookup"><span data-stu-id="0e12c-107">**Type**</span></span>|<span data-ttu-id="0e12c-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="0e12c-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="0e12c-109">rtypeID</span><span class="sxs-lookup"><span data-stu-id="0e12c-109">rtypeID</span></span>  <br/> |<span data-ttu-id="0e12c-110">int, non null</span><span class="sxs-lookup"><span data-stu-id="0e12c-110">int, not null</span></span>  <br/> |<span data-ttu-id="0e12c-111">ID de type de rôle.</span><span class="sxs-lookup"><span data-stu-id="0e12c-111">Role type ID.</span></span>  <br/> |
|<span data-ttu-id="0e12c-112">rtypeDesc</span><span class="sxs-lookup"><span data-stu-id="0e12c-112">rtypeDesc</span></span>  <br/> |<span data-ttu-id="0e12c-113">nvarchar (256), non null</span><span class="sxs-lookup"><span data-stu-id="0e12c-113">nvarchar (256), not null</span></span>  <br/> | <span data-ttu-id="0e12c-114">Description du type de rôle.</span><span class="sxs-lookup"><span data-stu-id="0e12c-114">Role type description.</span></span> <span data-ttu-id="0e12c-115">Il existe quatre rôles disponibles :</span><span class="sxs-lookup"><span data-stu-id="0e12c-115">There are four available roles:</span></span> <br/>  <span data-ttu-id="0e12c-116">: Membres salle de conversation</span><span class="sxs-lookup"><span data-stu-id="0e12c-116">Member: Chat room member</span></span> <br/>  <span data-ttu-id="0e12c-117">: Gestionnaire salle de conversation</span><span class="sxs-lookup"><span data-stu-id="0e12c-117">Manager: Chat room manager</span></span> <br/>  <span data-ttu-id="0e12c-118">Membre sonore : Le présentateur pour une salle de conversation de type auditorium</span><span class="sxs-lookup"><span data-stu-id="0e12c-118">Voiced: Presenter for an auditorium chat room</span></span> <br/>  <span data-ttu-id="0e12c-119">Créateur : Peut créer des salles de conversation</span><span class="sxs-lookup"><span data-stu-id="0e12c-119">Creator: Can create chat rooms</span></span> <br/> |
|<span data-ttu-id="0e12c-120">rtypeAllowedPermSet</span><span class="sxs-lookup"><span data-stu-id="0e12c-120">rtypeAllowedPermSet</span></span>  <br/> |<span data-ttu-id="0e12c-121">bigint, non null</span><span class="sxs-lookup"><span data-stu-id="0e12c-121">bigint, not null</span></span>  <br/> | <span data-ttu-id="0e12c-122">Jeu d’autorisations pour le rôle.</span><span class="sxs-lookup"><span data-stu-id="0e12c-122">Permission set for the role.</span></span> <span data-ttu-id="0e12c-123">Les fichiers binaires utilisés sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="0e12c-123">The used bits are:</span></span> <br/>  <span data-ttu-id="0e12c-124">2 : true si le rôle peut gérer des nœuds.</span><span class="sxs-lookup"><span data-stu-id="0e12c-124">2: True if the role can manage nodes.</span></span> <br/>  <span data-ttu-id="0e12c-125">4 : true si le rôle peut créer des nœuds enfants.</span><span class="sxs-lookup"><span data-stu-id="0e12c-125">4: True if the role can create children nodes.</span></span> <br/>  <span data-ttu-id="0e12c-126">7 : true si le rôle peut rejoindre une salle de conversation (ou les salles de conversation enfants d’une catégorie).</span><span class="sxs-lookup"><span data-stu-id="0e12c-126">7: True if the role can join a chat room (or children chat rooms of a category).</span></span> <br/>  <span data-ttu-id="0e12c-127">8 : true si le rôle peut converser dans une salle de conversation (ou dans les salles de conversation enfants d’une catégorie).</span><span class="sxs-lookup"><span data-stu-id="0e12c-127">8: True if the role can chat in a chat room (or in children chat rooms of a category).</span></span> <br/>  <span data-ttu-id="0e12c-128">10 : true si le rôle peut lire l’historique des conversations même lorsque ne pas lié à une salle de conversation.</span><span class="sxs-lookup"><span data-stu-id="0e12c-128">10: True if the role can read chat history even when not joined to a chat room.</span></span> <br/>  <span data-ttu-id="0e12c-129">11 : true si le rôle peut voir la salle de conversation.</span><span class="sxs-lookup"><span data-stu-id="0e12c-129">11: True if the role can see the chat room.</span></span> <span data-ttu-id="0e12c-130">(Il est affiné par facteurs, tels que l’étendue et la visibilité.)</span><span class="sxs-lookup"><span data-stu-id="0e12c-130">(This is further refined by factors such as scope and visibility.)</span></span> <br/>  <span data-ttu-id="0e12c-131">12 : true si le rôle peut converser dans une salle de conversation de type auditorium.</span><span class="sxs-lookup"><span data-stu-id="0e12c-131">12: True if the role can chat in an auditorium chat room.</span></span> <br/>  <span data-ttu-id="0e12c-132">13 : true si le rôle peut contourner les règles de visibilité lors de l’affichage des nœuds.</span><span class="sxs-lookup"><span data-stu-id="0e12c-132">13: True if the role can bypass visibility rules when viewing nodes.</span></span> <br/> |
   
<span data-ttu-id="0e12c-133">**Clé**</span><span class="sxs-lookup"><span data-stu-id="0e12c-133">**Key**</span></span>

|<span data-ttu-id="0e12c-134">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="0e12c-134">**Column**</span></span>|<span data-ttu-id="0e12c-135">**Description**</span><span class="sxs-lookup"><span data-stu-id="0e12c-135">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="0e12c-136">rtypeID</span><span class="sxs-lookup"><span data-stu-id="0e12c-136">rtypeID</span></span>  <br/> |<span data-ttu-id="0e12c-137">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="0e12c-137">Primary key.</span></span>  <br/> |
   

