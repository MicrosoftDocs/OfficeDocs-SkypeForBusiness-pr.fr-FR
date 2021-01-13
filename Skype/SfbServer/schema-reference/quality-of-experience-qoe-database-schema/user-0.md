---
title: Table User
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6b52047e-286d-47ab-b7bc-a9b266f62d82
description: La table User est une table de prise en charge qui stocke la liste des divers utilisateurs ayant participé à des sessions enregistrées dans la base de données. Chaque enregistrement de la table représente un utilisateur.
ms.openlocfilehash: 5c84f0b947199fa497964cb1689dccc571a98d14
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49800074"
---
# <a name="user-table"></a><span data-ttu-id="d8dd1-104">Table User</span><span class="sxs-lookup"><span data-stu-id="d8dd1-104">User table</span></span>
 
<span data-ttu-id="d8dd1-p102">La table User est une table de prise en charge qui stocke la liste des divers utilisateurs ayant participé à des sessions enregistrées dans la base de données. Chaque enregistrement de la table représente un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="d8dd1-p102">The User table is a supporting table that stores a list of the various users who have participated in sessions recorded in the database. Each record in the table represents one user.</span></span>
  
|<span data-ttu-id="d8dd1-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="d8dd1-107">**Column**</span></span>|<span data-ttu-id="d8dd1-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="d8dd1-108">**Data Type**</span></span>|<span data-ttu-id="d8dd1-109">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="d8dd1-109">**Key/Index**</span></span>|<span data-ttu-id="d8dd1-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="d8dd1-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d8dd1-111">**UserKey**</span><span class="sxs-lookup"><span data-stu-id="d8dd1-111">**UserKey**</span></span> <br/> |<span data-ttu-id="d8dd1-112">int</span><span class="sxs-lookup"><span data-stu-id="d8dd1-112">int</span></span>  <br/> |<span data-ttu-id="d8dd1-113">Primaire</span><span class="sxs-lookup"><span data-stu-id="d8dd1-113">Primary</span></span>  <br/> |<span data-ttu-id="d8dd1-114">Nombre unique identifiant cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="d8dd1-114">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="d8dd1-115">**URI**</span><span class="sxs-lookup"><span data-stu-id="d8dd1-115">**URI**</span></span> <br/> |<span data-ttu-id="d8dd1-116">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="d8dd1-116">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="d8dd1-117">Uniques</span><span class="sxs-lookup"><span data-stu-id="d8dd1-117">Unique</span></span>  <br/> |<span data-ttu-id="d8dd1-118">Chaîne URI.</span><span class="sxs-lookup"><span data-stu-id="d8dd1-118">URI string.</span></span>  <br/> |
|<span data-ttu-id="d8dd1-119">**URIType**</span><span class="sxs-lookup"><span data-stu-id="d8dd1-119">**URIType**</span></span> <br/> |<span data-ttu-id="d8dd1-120">int</span><span class="sxs-lookup"><span data-stu-id="d8dd1-120">int</span></span>  <br/> ||<span data-ttu-id="d8dd1-121">1 est type URI inconnu.</span><span class="sxs-lookup"><span data-stu-id="d8dd1-121">1 is unknown URI type.</span></span>  <br/> <span data-ttu-id="d8dd1-122">2 est URI d’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="d8dd1-122">2 is user URI.</span></span>  <br/> <span data-ttu-id="d8dd1-123">4 est URI de conférence.</span><span class="sxs-lookup"><span data-stu-id="d8dd1-123">4 is conference URI.</span></span>  <br/> <span data-ttu-id="d8dd1-124">8 est URI de téléphone.</span><span class="sxs-lookup"><span data-stu-id="d8dd1-124">8 is phone URI.</span></span>  <br/> |
|<span data-ttu-id="d8dd1-125">**TenantKey**</span><span class="sxs-lookup"><span data-stu-id="d8dd1-125">**TenantKey**</span></span> <br/> |<span data-ttu-id="d8dd1-126">int</span><span class="sxs-lookup"><span data-stu-id="d8dd1-126">int</span></span>  <br/> |<span data-ttu-id="d8dd1-127">Étranger</span><span class="sxs-lookup"><span data-stu-id="d8dd1-127">Foreign</span></span>  <br/> |<span data-ttu-id="d8dd1-128">Locataire de l’utilisateur, référencé depuis la table de locataires.</span><span class="sxs-lookup"><span data-stu-id="d8dd1-128">Tenant of the user, referenced from tenant table.</span></span>  <br/> |
|<span data-ttu-id="d8dd1-129">**LastPoorCallTime**</span><span class="sxs-lookup"><span data-stu-id="d8dd1-129">**LastPoorCallTime**</span></span> <br/> |<span data-ttu-id="d8dd1-130">DateHeure</span><span class="sxs-lookup"><span data-stu-id="d8dd1-130">datetime</span></span>  <br/> ||<span data-ttu-id="d8dd1-131">Horodatage le plus récent du moment où l’utilisateur avait un appel de mauvaise qualité audio.</span><span class="sxs-lookup"><span data-stu-id="d8dd1-131">Latest time stamp when the user had a poor audio call.</span></span>  <br/> |
|<span data-ttu-id="d8dd1-132">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="d8dd1-132">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="d8dd1-133">DateHeure</span><span class="sxs-lookup"><span data-stu-id="d8dd1-133">datetime</span></span>  <br/> ||<span data-ttu-id="d8dd1-134">À usage interne uniquement.</span><span class="sxs-lookup"><span data-stu-id="d8dd1-134">For internal use only.</span></span>  <br/> |
   

