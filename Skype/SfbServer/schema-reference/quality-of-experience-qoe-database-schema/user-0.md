---
title: Table User
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6b52047e-286d-47ab-b7bc-a9b266f62d82
description: La table est une table de prise en charge qui stocke une liste de différents utilisateurs qui ont participé à des sessions enregistrées dans la base de données. Chaque enregistrement de la table représente un utilisateur.
ms.openlocfilehash: fcdc8682b86432613af79d5e4d2abbdb248fef0f
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212080"
---
# <a name="user-table"></a><span data-ttu-id="d705d-104">Table User</span><span class="sxs-lookup"><span data-stu-id="d705d-104">User table</span></span>
 
<span data-ttu-id="d705d-105">La table est une table de prise en charge qui stocke une liste de différents utilisateurs qui ont participé à des sessions enregistrées dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="d705d-105">The User table is a supporting table that stores a list of the various users who have participated in sessions recorded in the database.</span></span> <span data-ttu-id="d705d-106">Chaque enregistrement de la table représente un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="d705d-106">Each record in the table represents one user.</span></span>
  
|<span data-ttu-id="d705d-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="d705d-107">**Column**</span></span>|<span data-ttu-id="d705d-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="d705d-108">**Data Type**</span></span>|<span data-ttu-id="d705d-109">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="d705d-109">**Key/Index**</span></span>|<span data-ttu-id="d705d-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="d705d-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d705d-111">**UserKey**</span><span class="sxs-lookup"><span data-stu-id="d705d-111">**UserKey**</span></span> <br/> |<span data-ttu-id="d705d-112">int</span><span class="sxs-lookup"><span data-stu-id="d705d-112">int</span></span>  <br/> |<span data-ttu-id="d705d-113">Principal</span><span class="sxs-lookup"><span data-stu-id="d705d-113">Primary</span></span>  <br/> |<span data-ttu-id="d705d-114">Numéro unique identifiant cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="d705d-114">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="d705d-115">**URI**</span><span class="sxs-lookup"><span data-stu-id="d705d-115">**URI**</span></span> <br/> |<span data-ttu-id="d705d-116">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="d705d-116">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="d705d-117">Unique</span><span class="sxs-lookup"><span data-stu-id="d705d-117">Unique</span></span>  <br/> |<span data-ttu-id="d705d-118">Chaîne d’URI.</span><span class="sxs-lookup"><span data-stu-id="d705d-118">URI string.</span></span>  <br/> |
|<span data-ttu-id="d705d-119">**URIType**</span><span class="sxs-lookup"><span data-stu-id="d705d-119">**URIType**</span></span> <br/> |<span data-ttu-id="d705d-120">int</span><span class="sxs-lookup"><span data-stu-id="d705d-120">int</span></span>  <br/> ||<span data-ttu-id="d705d-121">1 est type URI inconnu.</span><span class="sxs-lookup"><span data-stu-id="d705d-121">1 is unknown URI type.</span></span>  <br/> <span data-ttu-id="d705d-122">2 est URI de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="d705d-122">2 is user URI.</span></span>  <br/> <span data-ttu-id="d705d-123">4 est URI de conférence.</span><span class="sxs-lookup"><span data-stu-id="d705d-123">4 is conference URI.</span></span>  <br/> <span data-ttu-id="d705d-124">8 est URI de téléphone.</span><span class="sxs-lookup"><span data-stu-id="d705d-124">8 is phone URI.</span></span>  <br/> |
|<span data-ttu-id="d705d-125">**TenantKey**</span><span class="sxs-lookup"><span data-stu-id="d705d-125">**TenantKey**</span></span> <br/> |<span data-ttu-id="d705d-126">int</span><span class="sxs-lookup"><span data-stu-id="d705d-126">int</span></span>  <br/> |<span data-ttu-id="d705d-127">Étrangère</span><span class="sxs-lookup"><span data-stu-id="d705d-127">Foreign</span></span>  <br/> |<span data-ttu-id="d705d-128">Client de l’utilisateur, référencé à partir de la table clients.</span><span class="sxs-lookup"><span data-stu-id="d705d-128">Tenant of the user, referenced from tenant table.</span></span>  <br/> |
|<span data-ttu-id="d705d-129">**LastPoorCallTime**</span><span class="sxs-lookup"><span data-stu-id="d705d-129">**LastPoorCallTime**</span></span> <br/> |<span data-ttu-id="d705d-130">DateHeure</span><span class="sxs-lookup"><span data-stu-id="d705d-130">datetime</span></span>  <br/> ||<span data-ttu-id="d705d-131">Dernières date et l’heure où l’utilisateur avait un appel audio médiocre.</span><span class="sxs-lookup"><span data-stu-id="d705d-131">Latest time stamp when the user had a poor audio call.</span></span>  <br/> |
|<span data-ttu-id="d705d-132">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="d705d-132">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="d705d-133">DateHeure</span><span class="sxs-lookup"><span data-stu-id="d705d-133">datetime</span></span>  <br/> ||<span data-ttu-id="d705d-134">À usage interne uniquement.</span><span class="sxs-lookup"><span data-stu-id="d705d-134">For internal use only.</span></span>  <br/> |
   

