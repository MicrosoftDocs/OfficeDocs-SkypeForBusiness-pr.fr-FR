---
title: Table UserStatistics
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
ms.assetid: cfaf803b-1679-4169-92d3-533fad3e56ed
description: La table UserStatistics est une table de prise en charge. Chaque enregistrement de la table stocke des informations sur l’utilisation individuelle du système par un utilisateur. Ce tableau a été présenté dans Microsoft Lync Server 2013.
ms.openlocfilehash: 048c26279deb6f89e69784d754567dfde84d9983
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814792"
---
# <a name="userstatistics-table"></a><span data-ttu-id="35995-105">Table UserStatistics</span><span class="sxs-lookup"><span data-stu-id="35995-105">UserStatistics table</span></span>
 
<span data-ttu-id="35995-106">La table UserStatistics est une table de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="35995-106">The UserStatistics table is a supporting table.</span></span> <span data-ttu-id="35995-107">Chaque enregistrement de la table stocke des informations sur l’utilisation individuelle du système par un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="35995-107">Each record in the table stores information about an individual user's usage of the system.</span></span> <span data-ttu-id="35995-108">Ce tableau a été présenté dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="35995-108">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="35995-109">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="35995-109">**Column**</span></span>|<span data-ttu-id="35995-110">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="35995-110">**Data Type**</span></span>|<span data-ttu-id="35995-111">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="35995-111">**Key/Index**</span></span>|<span data-ttu-id="35995-112">**Détails**</span><span class="sxs-lookup"><span data-stu-id="35995-112">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="35995-113">**UserId**</span><span class="sxs-lookup"><span data-stu-id="35995-113">**UserId**</span></span> <br/> |<span data-ttu-id="35995-114">int</span><span class="sxs-lookup"><span data-stu-id="35995-114">int</span></span>  <br/> |<span data-ttu-id="35995-115">Principal</span><span class="sxs-lookup"><span data-stu-id="35995-115">Primary</span></span>  <br/> |<span data-ttu-id="35995-116">Numéro unique identifiant cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="35995-116">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="35995-117">**LastLogInTime**</span><span class="sxs-lookup"><span data-stu-id="35995-117">**LastLogInTime**</span></span> <br/> |<span data-ttu-id="35995-118">DateHeure</span><span class="sxs-lookup"><span data-stu-id="35995-118">datetime</span></span>  <br/> ||<span data-ttu-id="35995-119">Dernière connexion de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="35995-119">Last time the user logged in.</span></span>  <br/> |
|<span data-ttu-id="35995-120">**LastConfOrganizedTime**</span><span class="sxs-lookup"><span data-stu-id="35995-120">**LastConfOrganizedTime**</span></span> <br/> |<span data-ttu-id="35995-121">DateHeure</span><span class="sxs-lookup"><span data-stu-id="35995-121">datetime</span></span>  <br/> ||<span data-ttu-id="35995-122">Dernière organisation d’une conférence.</span><span class="sxs-lookup"><span data-stu-id="35995-122">Last time the user organized a conference.</span></span>  <br/> |
|<span data-ttu-id="35995-123">**LastCallOrganizerCallFailureTime**</span><span class="sxs-lookup"><span data-stu-id="35995-123">**LastCallOrganizerCallFailureTime**</span></span> <br/> |<span data-ttu-id="35995-124">DateHeure</span><span class="sxs-lookup"><span data-stu-id="35995-124">datetime</span></span>  <br/> ||<span data-ttu-id="35995-125">Dernière fois que l’utilisateur a rencontré un échec de l’appel.</span><span class="sxs-lookup"><span data-stu-id="35995-125">Last time the user experienced a call failure.</span></span>  <br/> |
|<span data-ttu-id="35995-126">**LastConfOrganizerCallFailureTime**</span><span class="sxs-lookup"><span data-stu-id="35995-126">**LastConfOrganizerCallFailureTime**</span></span> <br/> |<span data-ttu-id="35995-127">DateHeure</span><span class="sxs-lookup"><span data-stu-id="35995-127">datetime</span></span>  <br/> ||<span data-ttu-id="35995-128">Dernière fois que l’utilisateur a rencontré un appel d’organisateur en tant qu’organisateur de la Conférence.</span><span class="sxs-lookup"><span data-stu-id="35995-128">Last time the user experienced a call failure as a conference organizer.</span></span>  <br/> |
   

