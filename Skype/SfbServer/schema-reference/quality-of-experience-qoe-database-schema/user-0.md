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
localization_priority: Normal
ms.assetid: 6b52047e-286d-47ab-b7bc-a9b266f62d82
description: La table utilisateur est une table qui contient une liste des différents utilisateurs ayant participé à des sessions enregistrées dans la base de données. Chaque enregistrement de la table représente un utilisateur.
ms.openlocfilehash: a9f72793d3b287406b1b3b7e1ad360e7f5abc598
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294613"
---
# <a name="user-table"></a><span data-ttu-id="76f30-104">Table User</span><span class="sxs-lookup"><span data-stu-id="76f30-104">User table</span></span>
 
<span data-ttu-id="76f30-105">La table utilisateur est une table qui contient une liste des différents utilisateurs ayant participé à des sessions enregistrées dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="76f30-105">The User table is a supporting table that stores a list of the various users who have participated in sessions recorded in the database.</span></span> <span data-ttu-id="76f30-106">Chaque enregistrement de la table représente un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="76f30-106">Each record in the table represents one user.</span></span>
  
|<span data-ttu-id="76f30-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="76f30-107">**Column**</span></span>|<span data-ttu-id="76f30-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="76f30-108">**Data Type**</span></span>|<span data-ttu-id="76f30-109">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="76f30-109">**Key/Index**</span></span>|<span data-ttu-id="76f30-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="76f30-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="76f30-111">**UserKey**</span><span class="sxs-lookup"><span data-stu-id="76f30-111">**UserKey**</span></span> <br/> |<span data-ttu-id="76f30-112">int</span><span class="sxs-lookup"><span data-stu-id="76f30-112">int</span></span>  <br/> |<span data-ttu-id="76f30-113">Principal</span><span class="sxs-lookup"><span data-stu-id="76f30-113">Primary</span></span>  <br/> |<span data-ttu-id="76f30-114">Numéro unique identifiant cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="76f30-114">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="76f30-115">**SPAMMEUR**</span><span class="sxs-lookup"><span data-stu-id="76f30-115">**URI**</span></span> <br/> |<span data-ttu-id="76f30-116">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="76f30-116">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="76f30-117">Différent</span><span class="sxs-lookup"><span data-stu-id="76f30-117">Unique</span></span>  <br/> |<span data-ttu-id="76f30-118">Chaîne d’URI.</span><span class="sxs-lookup"><span data-stu-id="76f30-118">URI string.</span></span>  <br/> |
|<span data-ttu-id="76f30-119">**URIType**</span><span class="sxs-lookup"><span data-stu-id="76f30-119">**URIType**</span></span> <br/> |<span data-ttu-id="76f30-120">int</span><span class="sxs-lookup"><span data-stu-id="76f30-120">int</span></span>  <br/> ||<span data-ttu-id="76f30-121">1 est un type d’URI inconnu.</span><span class="sxs-lookup"><span data-stu-id="76f30-121">1 is unknown URI type.</span></span>  <br/> <span data-ttu-id="76f30-122">2 est l’URI de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="76f30-122">2 is user URI.</span></span>  <br/> <span data-ttu-id="76f30-123">4 est un URI de conférence.</span><span class="sxs-lookup"><span data-stu-id="76f30-123">4 is conference URI.</span></span>  <br/> <span data-ttu-id="76f30-124">8 est un URI de téléphone.</span><span class="sxs-lookup"><span data-stu-id="76f30-124">8 is phone URI.</span></span>  <br/> |
|<span data-ttu-id="76f30-125">**TenantKey**</span><span class="sxs-lookup"><span data-stu-id="76f30-125">**TenantKey**</span></span> <br/> |<span data-ttu-id="76f30-126">int</span><span class="sxs-lookup"><span data-stu-id="76f30-126">int</span></span>  <br/> |<span data-ttu-id="76f30-127">Externes</span><span class="sxs-lookup"><span data-stu-id="76f30-127">Foreign</span></span>  <br/> |<span data-ttu-id="76f30-128">Client de l’utilisateur, référencé dans la table locataire.</span><span class="sxs-lookup"><span data-stu-id="76f30-128">Tenant of the user, referenced from tenant table.</span></span>  <br/> |
|<span data-ttu-id="76f30-129">**LastPoorCallTime**</span><span class="sxs-lookup"><span data-stu-id="76f30-129">**LastPoorCallTime**</span></span> <br/> |<span data-ttu-id="76f30-130">DateHeure</span><span class="sxs-lookup"><span data-stu-id="76f30-130">datetime</span></span>  <br/> ||<span data-ttu-id="76f30-131">Horodatage le plus récent lorsque l’utilisateur avait un appel audio médiocre.</span><span class="sxs-lookup"><span data-stu-id="76f30-131">Latest time stamp when the user had a poor audio call.</span></span>  <br/> |
|<span data-ttu-id="76f30-132">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="76f30-132">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="76f30-133">DateHeure</span><span class="sxs-lookup"><span data-stu-id="76f30-133">datetime</span></span>  <br/> ||<span data-ttu-id="76f30-134">Pour un usage interne uniquement.</span><span class="sxs-lookup"><span data-stu-id="76f30-134">For internal use only.</span></span>  <br/> |
   

