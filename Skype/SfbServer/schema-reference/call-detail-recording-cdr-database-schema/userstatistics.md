---
title: Table UserStatistics
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cfaf803b-1679-4169-92d3-533fad3e56ed
description: La table UserStatistics est une table de prise en charge. Chaque enregistrement de la table stocke des informations sur l’utilisation d’un utilisateur individuel du système. Ce tableau a été introduit dans Microsoft Lync Server 2013.
ms.openlocfilehash: 45f34a1e8905d19b5ce48d94824591f25ec1ef28
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213038"
---
# <a name="userstatistics-table"></a><span data-ttu-id="de5cf-105">Table UserStatistics</span><span class="sxs-lookup"><span data-stu-id="de5cf-105">UserStatistics table</span></span>
 
<span data-ttu-id="de5cf-106">La table UserStatistics est une table de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="de5cf-106">The UserStatistics table is a supporting table.</span></span> <span data-ttu-id="de5cf-107">Chaque enregistrement de la table stocke des informations sur l’utilisation d’un utilisateur individuel du système.</span><span class="sxs-lookup"><span data-stu-id="de5cf-107">Each record in the table stores information about an individual user's usage of the system.</span></span> <span data-ttu-id="de5cf-108">Ce tableau a été introduit dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="de5cf-108">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="de5cf-109">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="de5cf-109">**Column**</span></span>|<span data-ttu-id="de5cf-110">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="de5cf-110">**Data Type**</span></span>|<span data-ttu-id="de5cf-111">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="de5cf-111">**Key/Index**</span></span>|<span data-ttu-id="de5cf-112">**Détails**</span><span class="sxs-lookup"><span data-stu-id="de5cf-112">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="de5cf-113">**Nom d’utilisateur**</span><span class="sxs-lookup"><span data-stu-id="de5cf-113">**UserId**</span></span> <br/> |<span data-ttu-id="de5cf-114">int</span><span class="sxs-lookup"><span data-stu-id="de5cf-114">int</span></span>  <br/> |<span data-ttu-id="de5cf-115">Principal</span><span class="sxs-lookup"><span data-stu-id="de5cf-115">Primary</span></span>  <br/> |<span data-ttu-id="de5cf-116">Numéro unique identifiant cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="de5cf-116">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="de5cf-117">**LastLogInTime**</span><span class="sxs-lookup"><span data-stu-id="de5cf-117">**LastLogInTime**</span></span> <br/> |<span data-ttu-id="de5cf-118">DateHeure</span><span class="sxs-lookup"><span data-stu-id="de5cf-118">datetime</span></span>  <br/> ||<span data-ttu-id="de5cf-119">Heure de la dernière connecté de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="de5cf-119">Last time the user logged in.</span></span>  <br/> |
|<span data-ttu-id="de5cf-120">**LastConfOrganizedTime**</span><span class="sxs-lookup"><span data-stu-id="de5cf-120">**LastConfOrganizedTime**</span></span> <br/> |<span data-ttu-id="de5cf-121">DateHeure</span><span class="sxs-lookup"><span data-stu-id="de5cf-121">datetime</span></span>  <br/> ||<span data-ttu-id="de5cf-122">Heure de la dernière l’utilisateur organisé une conférence.</span><span class="sxs-lookup"><span data-stu-id="de5cf-122">Last time the user organized a conference.</span></span>  <br/> |
|<span data-ttu-id="de5cf-123">**LastCallOrganizerCallFailureTime**</span><span class="sxs-lookup"><span data-stu-id="de5cf-123">**LastCallOrganizerCallFailureTime**</span></span> <br/> |<span data-ttu-id="de5cf-124">DateHeure</span><span class="sxs-lookup"><span data-stu-id="de5cf-124">datetime</span></span>  <br/> ||<span data-ttu-id="de5cf-125">Heure de la dernière l’utilisateur a rencontré un échec d’appel.</span><span class="sxs-lookup"><span data-stu-id="de5cf-125">Last time the user experienced a call failure.</span></span>  <br/> |
|<span data-ttu-id="de5cf-126">**LastConfOrganizerCallFailureTime**</span><span class="sxs-lookup"><span data-stu-id="de5cf-126">**LastConfOrganizerCallFailureTime**</span></span> <br/> |<span data-ttu-id="de5cf-127">DateHeure</span><span class="sxs-lookup"><span data-stu-id="de5cf-127">datetime</span></span>  <br/> ||<span data-ttu-id="de5cf-128">Heure de la dernière l’utilisateur a rencontré un échec d’appel en tant qu’organisateur de la conférence.</span><span class="sxs-lookup"><span data-stu-id="de5cf-128">Last time the user experienced a call failure as a conference organizer.</span></span>  <br/> |
   

