---
title: Table de UserStatistics
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cfaf803b-1679-4169-92d3-533fad3e56ed
description: La table UserStatistics est un tableau de prise en charge. Chaque enregistrement dans la table stocke les informations relatives à l’utilisation d’un utilisateur individuel du système. Cette table a été introduite dans Microsoft Lync Server 2013.
ms.openlocfilehash: c4a7952eada01033836811555d2e448d13133a27
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="userstatistics-table"></a><span data-ttu-id="e9893-105">Table de UserStatistics</span><span class="sxs-lookup"><span data-stu-id="e9893-105">UserStatistics table</span></span>
 
<span data-ttu-id="e9893-106">La table UserStatistics est un tableau de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="e9893-106">The UserStatistics table is a supporting table.</span></span> <span data-ttu-id="e9893-107">Chaque enregistrement dans la table stocke les informations relatives à l’utilisation d’un utilisateur individuel du système.</span><span class="sxs-lookup"><span data-stu-id="e9893-107">Each record in the table stores information about an individual user's usage of the system.</span></span> <span data-ttu-id="e9893-108">Cette table a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e9893-108">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="e9893-109">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="e9893-109">**Column**</span></span>|<span data-ttu-id="e9893-110">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="e9893-110">**Data Type**</span></span>|<span data-ttu-id="e9893-111">**Index de la clé**</span><span class="sxs-lookup"><span data-stu-id="e9893-111">**Key/Index**</span></span>|<span data-ttu-id="e9893-112">**Détails**</span><span class="sxs-lookup"><span data-stu-id="e9893-112">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e9893-113">**ID utilisateur**</span><span class="sxs-lookup"><span data-stu-id="e9893-113">**UserId**</span></span> <br/> |<span data-ttu-id="e9893-114">int</span><span class="sxs-lookup"><span data-stu-id="e9893-114">int</span></span>  <br/> |<span data-ttu-id="e9893-115">Principal</span><span class="sxs-lookup"><span data-stu-id="e9893-115">Primary</span></span>  <br/> |<span data-ttu-id="e9893-116">Numéro unique identifiant l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="e9893-116">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="e9893-117">**LastLogInTime**</span><span class="sxs-lookup"><span data-stu-id="e9893-117">**LastLogInTime**</span></span> <br/> |<span data-ttu-id="e9893-118">DateHeure</span><span class="sxs-lookup"><span data-stu-id="e9893-118">datetime</span></span>  <br/> ||<span data-ttu-id="e9893-119">Dernière fois que l’utilisateur connecté.</span><span class="sxs-lookup"><span data-stu-id="e9893-119">Last time the user logged in.</span></span>  <br/> |
|<span data-ttu-id="e9893-120">**LastConfOrganizedTime**</span><span class="sxs-lookup"><span data-stu-id="e9893-120">**LastConfOrganizedTime**</span></span> <br/> |<span data-ttu-id="e9893-121">DateHeure</span><span class="sxs-lookup"><span data-stu-id="e9893-121">datetime</span></span>  <br/> ||<span data-ttu-id="e9893-122">Dernière fois que l’utilisateur organisé une conférence.</span><span class="sxs-lookup"><span data-stu-id="e9893-122">Last time the user organized a conference.</span></span>  <br/> |
|<span data-ttu-id="e9893-123">**LastCallOrganizerCallFailureTime**</span><span class="sxs-lookup"><span data-stu-id="e9893-123">**LastCallOrganizerCallFailureTime**</span></span> <br/> |<span data-ttu-id="e9893-124">DateHeure</span><span class="sxs-lookup"><span data-stu-id="e9893-124">datetime</span></span>  <br/> ||<span data-ttu-id="e9893-125">Dernière fois que l’utilisateur a rencontré un échec d’appel.</span><span class="sxs-lookup"><span data-stu-id="e9893-125">Last time the user experienced a call failure.</span></span>  <br/> |
|<span data-ttu-id="e9893-126">**LastConfOrganizerCallFailureTime**</span><span class="sxs-lookup"><span data-stu-id="e9893-126">**LastConfOrganizerCallFailureTime**</span></span> <br/> |<span data-ttu-id="e9893-127">DateHeure</span><span class="sxs-lookup"><span data-stu-id="e9893-127">datetime</span></span>  <br/> ||<span data-ttu-id="e9893-128">Dernière fois que l’utilisateur a rencontré une erreur appel en tant qu’organisateur de la conférence.</span><span class="sxs-lookup"><span data-stu-id="e9893-128">Last time the user experienced a call failure as a conference organizer.</span></span>  <br/> |
   

