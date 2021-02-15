---
title: tblRoleType
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 1eac3a54-656a-40ac-b771-edfc64d6e34b
description: tblRoleType est une table de choix statique contenant des types de rôles et leurs jeux d’autorisations.
ms.openlocfilehash: c440463d822b908a89c84eb9c85b70e9daf442be
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831524"
---
# <a name="tblroletype"></a><span data-ttu-id="ca0ce-103">tblRoleType</span><span class="sxs-lookup"><span data-stu-id="ca0ce-103">tblRoleType</span></span>
 
<span data-ttu-id="ca0ce-104">tblRoleType est une table de choix statique contenant des types de rôles et leurs jeux d’autorisations.</span><span class="sxs-lookup"><span data-stu-id="ca0ce-104">tblRoleType is a static lookup table with role types and their associated permission sets.</span></span>
  
<span data-ttu-id="ca0ce-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="ca0ce-105">**Columns**</span></span>

|<span data-ttu-id="ca0ce-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="ca0ce-106">**Column**</span></span>|<span data-ttu-id="ca0ce-107">**Type (Type)**</span><span class="sxs-lookup"><span data-stu-id="ca0ce-107">**Type**</span></span>|<span data-ttu-id="ca0ce-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="ca0ce-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ca0ce-109">rtypeID</span><span class="sxs-lookup"><span data-stu-id="ca0ce-109">rtypeID</span></span>  <br/> |<span data-ttu-id="ca0ce-110">int, non null</span><span class="sxs-lookup"><span data-stu-id="ca0ce-110">int, not null</span></span>  <br/> |<span data-ttu-id="ca0ce-111">ID de type de rôle.</span><span class="sxs-lookup"><span data-stu-id="ca0ce-111">Role type ID.</span></span>  <br/> |
|<span data-ttu-id="ca0ce-112">rtypeDesc</span><span class="sxs-lookup"><span data-stu-id="ca0ce-112">rtypeDesc</span></span>  <br/> |<span data-ttu-id="ca0ce-113">nvarchar (256), non null</span><span class="sxs-lookup"><span data-stu-id="ca0ce-113">nvarchar (256), not null</span></span>  <br/> | <span data-ttu-id="ca0ce-p101">Description de type de rôle. Les quatre rôles disponibles sont :</span><span class="sxs-lookup"><span data-stu-id="ca0ce-p101">Role type description. There are four available roles:</span></span> <br/>  <span data-ttu-id="ca0ce-116">Membre : membre de la salle de conversation</span><span class="sxs-lookup"><span data-stu-id="ca0ce-116">Member: Chat room member</span></span> <br/>  <span data-ttu-id="ca0ce-117">Responsable : responsable de la salle de conversation</span><span class="sxs-lookup"><span data-stu-id="ca0ce-117">Manager: Chat room manager</span></span> <br/>  <span data-ttu-id="ca0ce-118">Membre sonore : présentateur de la salle de conversation de type auditorium</span><span class="sxs-lookup"><span data-stu-id="ca0ce-118">Voiced: Presenter for an auditorium chat room</span></span> <br/>  <span data-ttu-id="ca0ce-119">Créateur : peut créer des salles de conversation</span><span class="sxs-lookup"><span data-stu-id="ca0ce-119">Creator: Can create chat rooms</span></span> <br/> |
|<span data-ttu-id="ca0ce-120">rtypeAllowedPermSet</span><span class="sxs-lookup"><span data-stu-id="ca0ce-120">rtypeAllowedPermSet</span></span>  <br/> |<span data-ttu-id="ca0ce-121">bigint, non null</span><span class="sxs-lookup"><span data-stu-id="ca0ce-121">bigint, not null</span></span>  <br/> | <span data-ttu-id="ca0ce-p102">Définition de l’autorisation du rôle. Les bits utilisés sont :</span><span class="sxs-lookup"><span data-stu-id="ca0ce-p102">Permission set for the role. The used bits are:</span></span> <br/>  <span data-ttu-id="ca0ce-124">2 : True si le rôle peut gérer des nœuds.</span><span class="sxs-lookup"><span data-stu-id="ca0ce-124">2: True if the role can manage nodes.</span></span> <br/>  <span data-ttu-id="ca0ce-125">4 : True si le rôle peut créer des nœuds enfants.</span><span class="sxs-lookup"><span data-stu-id="ca0ce-125">4: True if the role can create children nodes.</span></span> <br/>  <span data-ttu-id="ca0ce-126">7 : True si le rôle peut rejoindre une salle de conversation (ou les salles de conversation enfants d’une catégorie).</span><span class="sxs-lookup"><span data-stu-id="ca0ce-126">7: True if the role can join a chat room (or children chat rooms of a category).</span></span> <br/>  <span data-ttu-id="ca0ce-127">8 : True si le rôle peut converser dans une salle de conversation (ou les salles de conversation enfants d’une catégorie).</span><span class="sxs-lookup"><span data-stu-id="ca0ce-127">8: True if the role can chat in a chat room (or in children chat rooms of a category).</span></span> <br/>  <span data-ttu-id="ca0ce-128">10 : True si le rôle peut lire l’historique d’une conversation même s’il n’a pas rejoint une salle de conversation.</span><span class="sxs-lookup"><span data-stu-id="ca0ce-128">10: True if the role can read chat history even when not joined to a chat room.</span></span> <br/>  <span data-ttu-id="ca0ce-p103">11 : True si le rôle peut voir la salle de conversation. (Les facteurs tels que l’étendue et la visibilité permettent d’affiner davantage).</span><span class="sxs-lookup"><span data-stu-id="ca0ce-p103">11: True if the role can see the chat room. (This is further refined by factors such as scope and visibility.)</span></span> <br/>  <span data-ttu-id="ca0ce-131">12 : True si le rôle peut converser dans la salle de conversation de type auditorium.</span><span class="sxs-lookup"><span data-stu-id="ca0ce-131">12: True if the role can chat in an auditorium chat room.</span></span> <br/>  <span data-ttu-id="ca0ce-132">13 : True si le rôle peut contourner les règles de visibilité lors de la visualisation des nœuds.</span><span class="sxs-lookup"><span data-stu-id="ca0ce-132">13: True if the role can bypass visibility rules when viewing nodes.</span></span> <br/> |
   
<span data-ttu-id="ca0ce-133">**Clé**</span><span class="sxs-lookup"><span data-stu-id="ca0ce-133">**Key**</span></span>

|<span data-ttu-id="ca0ce-134">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="ca0ce-134">**Column**</span></span>|<span data-ttu-id="ca0ce-135">**Description**</span><span class="sxs-lookup"><span data-stu-id="ca0ce-135">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ca0ce-136">rtypeID</span><span class="sxs-lookup"><span data-stu-id="ca0ce-136">rtypeID</span></span>  <br/> |<span data-ttu-id="ca0ce-137">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="ca0ce-137">Primary key.</span></span>  <br/> |
   

