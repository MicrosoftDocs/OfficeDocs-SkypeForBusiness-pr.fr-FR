---
title: Table UserStatistics
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
ms.assetid: cfaf803b-1679-4169-92d3-533fad3e56ed
description: La table UserStatistics est une table de prise en charge. Chaque enregistrement de la table stocke des informations sur l’utilisation du système par un utilisateur individuel. Ce tableau a été introduit dans Microsoft Lync Server 2013.
ms.openlocfilehash: 65017c9f807b272097b39bac88c80cc81e617ff4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813104"
---
# <a name="userstatistics-table"></a><span data-ttu-id="560e5-105">Table UserStatistics</span><span class="sxs-lookup"><span data-stu-id="560e5-105">UserStatistics table</span></span>
 
<span data-ttu-id="560e5-106">La table UserStatistics est une table de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="560e5-106">The UserStatistics table is a supporting table.</span></span> <span data-ttu-id="560e5-107">Chaque enregistrement de la table stocke des informations sur l’utilisation du système par un utilisateur individuel.</span><span class="sxs-lookup"><span data-stu-id="560e5-107">Each record in the table stores information about an individual user's usage of the system.</span></span> <span data-ttu-id="560e5-108">Ce tableau a été introduit dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="560e5-108">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="560e5-109">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="560e5-109">**Column**</span></span>|<span data-ttu-id="560e5-110">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="560e5-110">**Data Type**</span></span>|<span data-ttu-id="560e5-111">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="560e5-111">**Key/Index**</span></span>|<span data-ttu-id="560e5-112">**Details**</span><span class="sxs-lookup"><span data-stu-id="560e5-112">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="560e5-113">**UserId**</span><span class="sxs-lookup"><span data-stu-id="560e5-113">**UserId**</span></span> <br/> |<span data-ttu-id="560e5-114">int</span><span class="sxs-lookup"><span data-stu-id="560e5-114">int</span></span>  <br/> |<span data-ttu-id="560e5-115">Primaire</span><span class="sxs-lookup"><span data-stu-id="560e5-115">Primary</span></span>  <br/> |<span data-ttu-id="560e5-116">Numéro unique identifiant cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="560e5-116">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="560e5-117">**LastLogInTime**</span><span class="sxs-lookup"><span data-stu-id="560e5-117">**LastLogInTime**</span></span> <br/> |<span data-ttu-id="560e5-118">DateHeure</span><span class="sxs-lookup"><span data-stu-id="560e5-118">datetime</span></span>  <br/> ||<span data-ttu-id="560e5-119">Heure de la dernière connexion de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="560e5-119">Last time the user logged in.</span></span>  <br/> |
|<span data-ttu-id="560e5-120">**LastConfOrganizedTime**</span><span class="sxs-lookup"><span data-stu-id="560e5-120">**LastConfOrganizedTime**</span></span> <br/> |<span data-ttu-id="560e5-121">DateHeure</span><span class="sxs-lookup"><span data-stu-id="560e5-121">datetime</span></span>  <br/> ||<span data-ttu-id="560e5-122">Heure de la dernière organisation d’une conférence par l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="560e5-122">Last time the user organized a conference.</span></span>  <br/> |
|<span data-ttu-id="560e5-123">**LastCallOrganizerCallFailureTime**</span><span class="sxs-lookup"><span data-stu-id="560e5-123">**LastCallOrganizerCallFailureTime**</span></span> <br/> |<span data-ttu-id="560e5-124">DateHeure</span><span class="sxs-lookup"><span data-stu-id="560e5-124">datetime</span></span>  <br/> ||<span data-ttu-id="560e5-125">Heure du dernier échec d’appel de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="560e5-125">Last time the user experienced a call failure.</span></span>  <br/> |
|<span data-ttu-id="560e5-126">**LastConfOrganizerCallFailureTime**</span><span class="sxs-lookup"><span data-stu-id="560e5-126">**LastConfOrganizerCallFailureTime**</span></span> <br/> |<span data-ttu-id="560e5-127">DateHeure</span><span class="sxs-lookup"><span data-stu-id="560e5-127">datetime</span></span>  <br/> ||<span data-ttu-id="560e5-128">Heure du dernier échec d’appel de l’utilisateur en tant qu’organisateur de conférence.</span><span class="sxs-lookup"><span data-stu-id="560e5-128">Last time the user experienced a call failure as a conference organizer.</span></span>  <br/> |
   

