---
title: Table User
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6b52047e-286d-47ab-b7bc-a9b266f62d82
description: La table est une table de prise en charge qui stocke une liste de différents utilisateurs qui ont participé à des sessions enregistrées dans la base de données. Chaque enregistrement de la table représente un utilisateur.
ms.openlocfilehash: 426d272a5c8bee2fd37511edc62bcb3e1a0c533e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33907037"
---
# <a name="user-table"></a><span data-ttu-id="8c272-104">Table User</span><span class="sxs-lookup"><span data-stu-id="8c272-104">User table</span></span>
 
<span data-ttu-id="8c272-105">La table est une table de prise en charge qui stocke une liste de différents utilisateurs qui ont participé à des sessions enregistrées dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="8c272-105">The User table is a supporting table that stores a list of the various users who have participated in sessions recorded in the database.</span></span> <span data-ttu-id="8c272-106">Chaque enregistrement de la table représente un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="8c272-106">Each record in the table represents one user.</span></span>
  
|<span data-ttu-id="8c272-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="8c272-107">**Column**</span></span>|<span data-ttu-id="8c272-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="8c272-108">**Data Type**</span></span>|<span data-ttu-id="8c272-109">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="8c272-109">**Key/Index**</span></span>|<span data-ttu-id="8c272-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="8c272-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="8c272-111">**UserKey**</span><span class="sxs-lookup"><span data-stu-id="8c272-111">**UserKey**</span></span> <br/> |<span data-ttu-id="8c272-112">int</span><span class="sxs-lookup"><span data-stu-id="8c272-112">int</span></span>  <br/> |<span data-ttu-id="8c272-113">Principal</span><span class="sxs-lookup"><span data-stu-id="8c272-113">Primary</span></span>  <br/> |<span data-ttu-id="8c272-114">Numéro unique identifiant cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="8c272-114">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="8c272-115">**URI**</span><span class="sxs-lookup"><span data-stu-id="8c272-115">**URI**</span></span> <br/> |<span data-ttu-id="8c272-116">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="8c272-116">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="8c272-117">Unique</span><span class="sxs-lookup"><span data-stu-id="8c272-117">Unique</span></span>  <br/> |<span data-ttu-id="8c272-118">Chaîne d’URI.</span><span class="sxs-lookup"><span data-stu-id="8c272-118">URI string.</span></span>  <br/> |
|<span data-ttu-id="8c272-119">**URIType**</span><span class="sxs-lookup"><span data-stu-id="8c272-119">**URIType**</span></span> <br/> |<span data-ttu-id="8c272-120">int</span><span class="sxs-lookup"><span data-stu-id="8c272-120">int</span></span>  <br/> ||<span data-ttu-id="8c272-121">1 est type URI inconnu.</span><span class="sxs-lookup"><span data-stu-id="8c272-121">1 is unknown URI type.</span></span>  <br/> <span data-ttu-id="8c272-122">2 est URI de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="8c272-122">2 is user URI.</span></span>  <br/> <span data-ttu-id="8c272-123">4 est URI de conférence.</span><span class="sxs-lookup"><span data-stu-id="8c272-123">4 is conference URI.</span></span>  <br/> <span data-ttu-id="8c272-124">8 est URI de téléphone.</span><span class="sxs-lookup"><span data-stu-id="8c272-124">8 is phone URI.</span></span>  <br/> |
|<span data-ttu-id="8c272-125">**TenantKey**</span><span class="sxs-lookup"><span data-stu-id="8c272-125">**TenantKey**</span></span> <br/> |<span data-ttu-id="8c272-126">int</span><span class="sxs-lookup"><span data-stu-id="8c272-126">int</span></span>  <br/> |<span data-ttu-id="8c272-127">Étrangère</span><span class="sxs-lookup"><span data-stu-id="8c272-127">Foreign</span></span>  <br/> |<span data-ttu-id="8c272-128">Client de l’utilisateur, référencé à partir de la table clients.</span><span class="sxs-lookup"><span data-stu-id="8c272-128">Tenant of the user, referenced from tenant table.</span></span>  <br/> |
|<span data-ttu-id="8c272-129">**LastPoorCallTime**</span><span class="sxs-lookup"><span data-stu-id="8c272-129">**LastPoorCallTime**</span></span> <br/> |<span data-ttu-id="8c272-130">DateHeure</span><span class="sxs-lookup"><span data-stu-id="8c272-130">datetime</span></span>  <br/> ||<span data-ttu-id="8c272-131">Dernières date et l’heure où l’utilisateur avait un appel audio médiocre.</span><span class="sxs-lookup"><span data-stu-id="8c272-131">Latest time stamp when the user had a poor audio call.</span></span>  <br/> |
|<span data-ttu-id="8c272-132">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="8c272-132">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="8c272-133">DateHeure</span><span class="sxs-lookup"><span data-stu-id="8c272-133">datetime</span></span>  <br/> ||<span data-ttu-id="8c272-134">À usage interne uniquement.</span><span class="sxs-lookup"><span data-stu-id="8c272-134">For internal use only.</span></span>  <br/> |
   

