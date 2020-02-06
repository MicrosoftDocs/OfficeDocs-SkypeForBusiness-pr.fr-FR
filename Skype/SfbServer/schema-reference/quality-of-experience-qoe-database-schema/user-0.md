---
title: Table User
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6b52047e-286d-47ab-b7bc-a9b266f62d82
description: La table utilisateur est une table qui contient une liste des différents utilisateurs ayant participé à des sessions enregistrées dans la base de données. Chaque enregistrement de la table représente un utilisateur.
ms.openlocfilehash: fcb6c4d45f1392c31ba87637d6e3a1a697f7be9e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41805092"
---
# <a name="user-table"></a><span data-ttu-id="787f3-104">Table User</span><span class="sxs-lookup"><span data-stu-id="787f3-104">User table</span></span>
 
<span data-ttu-id="787f3-105">La table utilisateur est une table qui contient une liste des différents utilisateurs ayant participé à des sessions enregistrées dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="787f3-105">The User table is a supporting table that stores a list of the various users who have participated in sessions recorded in the database.</span></span> <span data-ttu-id="787f3-106">Chaque enregistrement de la table représente un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="787f3-106">Each record in the table represents one user.</span></span>
  
|<span data-ttu-id="787f3-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="787f3-107">**Column**</span></span>|<span data-ttu-id="787f3-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="787f3-108">**Data Type**</span></span>|<span data-ttu-id="787f3-109">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="787f3-109">**Key/Index**</span></span>|<span data-ttu-id="787f3-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="787f3-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="787f3-111">**UserKey**</span><span class="sxs-lookup"><span data-stu-id="787f3-111">**UserKey**</span></span> <br/> |<span data-ttu-id="787f3-112">int</span><span class="sxs-lookup"><span data-stu-id="787f3-112">int</span></span>  <br/> |<span data-ttu-id="787f3-113">Principal</span><span class="sxs-lookup"><span data-stu-id="787f3-113">Primary</span></span>  <br/> |<span data-ttu-id="787f3-114">Numéro unique identifiant cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="787f3-114">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="787f3-115">**SPAMMEUR**</span><span class="sxs-lookup"><span data-stu-id="787f3-115">**URI**</span></span> <br/> |<span data-ttu-id="787f3-116">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="787f3-116">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="787f3-117">Différent</span><span class="sxs-lookup"><span data-stu-id="787f3-117">Unique</span></span>  <br/> |<span data-ttu-id="787f3-118">Chaîne d’URI.</span><span class="sxs-lookup"><span data-stu-id="787f3-118">URI string.</span></span>  <br/> |
|<span data-ttu-id="787f3-119">**URIType**</span><span class="sxs-lookup"><span data-stu-id="787f3-119">**URIType**</span></span> <br/> |<span data-ttu-id="787f3-120">int</span><span class="sxs-lookup"><span data-stu-id="787f3-120">int</span></span>  <br/> ||<span data-ttu-id="787f3-121">1 est un type d’URI inconnu.</span><span class="sxs-lookup"><span data-stu-id="787f3-121">1 is unknown URI type.</span></span>  <br/> <span data-ttu-id="787f3-122">2 est l’URI de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="787f3-122">2 is user URI.</span></span>  <br/> <span data-ttu-id="787f3-123">4 est un URI de conférence.</span><span class="sxs-lookup"><span data-stu-id="787f3-123">4 is conference URI.</span></span>  <br/> <span data-ttu-id="787f3-124">8 est un URI de téléphone.</span><span class="sxs-lookup"><span data-stu-id="787f3-124">8 is phone URI.</span></span>  <br/> |
|<span data-ttu-id="787f3-125">**TenantKey**</span><span class="sxs-lookup"><span data-stu-id="787f3-125">**TenantKey**</span></span> <br/> |<span data-ttu-id="787f3-126">int</span><span class="sxs-lookup"><span data-stu-id="787f3-126">int</span></span>  <br/> |<span data-ttu-id="787f3-127">Externes</span><span class="sxs-lookup"><span data-stu-id="787f3-127">Foreign</span></span>  <br/> |<span data-ttu-id="787f3-128">Client de l’utilisateur, référencé dans la table locataire.</span><span class="sxs-lookup"><span data-stu-id="787f3-128">Tenant of the user, referenced from tenant table.</span></span>  <br/> |
|<span data-ttu-id="787f3-129">**LastPoorCallTime**</span><span class="sxs-lookup"><span data-stu-id="787f3-129">**LastPoorCallTime**</span></span> <br/> |<span data-ttu-id="787f3-130">DateHeure</span><span class="sxs-lookup"><span data-stu-id="787f3-130">datetime</span></span>  <br/> ||<span data-ttu-id="787f3-131">Horodatage le plus récent lorsque l’utilisateur avait un appel audio médiocre.</span><span class="sxs-lookup"><span data-stu-id="787f3-131">Latest time stamp when the user had a poor audio call.</span></span>  <br/> |
|<span data-ttu-id="787f3-132">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="787f3-132">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="787f3-133">DateHeure</span><span class="sxs-lookup"><span data-stu-id="787f3-133">datetime</span></span>  <br/> ||<span data-ttu-id="787f3-134">Pour un usage interne uniquement.</span><span class="sxs-lookup"><span data-stu-id="787f3-134">For internal use only.</span></span>  <br/> |
   

