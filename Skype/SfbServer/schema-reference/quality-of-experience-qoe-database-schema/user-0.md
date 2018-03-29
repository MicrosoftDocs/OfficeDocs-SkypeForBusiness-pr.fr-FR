---
title: Table User
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6b52047e-286d-47ab-b7bc-a9b266f62d82
description: La table est une table de prise en charge qui stocke une liste des différents utilisateurs qui ont participé aux sessions enregistrées dans la base de données. Chaque enregistrement de la table représente un utilisateur.
ms.openlocfilehash: 3261133b8c36fe96fd847c075dce0be2a903c417
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="user-table"></a><span data-ttu-id="49339-104">Table User</span><span class="sxs-lookup"><span data-stu-id="49339-104">User table</span></span>
 
<span data-ttu-id="49339-105">La table est une table de prise en charge qui stocke une liste des différents utilisateurs qui ont participé aux sessions enregistrées dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="49339-105">The User table is a supporting table that stores a list of the various users who have participated in sessions recorded in the database.</span></span> <span data-ttu-id="49339-106">Chaque enregistrement de la table représente un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="49339-106">Each record in the table represents one user.</span></span>
  
|<span data-ttu-id="49339-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="49339-107">**Column**</span></span>|<span data-ttu-id="49339-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="49339-108">**Data Type**</span></span>|<span data-ttu-id="49339-109">**Index de la clé**</span><span class="sxs-lookup"><span data-stu-id="49339-109">**Key/Index**</span></span>|<span data-ttu-id="49339-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="49339-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="49339-111">**UserKey**</span><span class="sxs-lookup"><span data-stu-id="49339-111">**UserKey**</span></span> <br/> |<span data-ttu-id="49339-112">int</span><span class="sxs-lookup"><span data-stu-id="49339-112">int</span></span>  <br/> |<span data-ttu-id="49339-113">Principal</span><span class="sxs-lookup"><span data-stu-id="49339-113">Primary</span></span>  <br/> |<span data-ttu-id="49339-114">Numéro unique identifiant l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="49339-114">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="49339-115">**URI**</span><span class="sxs-lookup"><span data-stu-id="49339-115">**URI**</span></span> <br/> |<span data-ttu-id="49339-116">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="49339-116">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="49339-117">Unique</span><span class="sxs-lookup"><span data-stu-id="49339-117">Unique</span></span>  <br/> |<span data-ttu-id="49339-118">Chaîne d’URI.</span><span class="sxs-lookup"><span data-stu-id="49339-118">URI string.</span></span>  <br/> |
|<span data-ttu-id="49339-119">**URIType**</span><span class="sxs-lookup"><span data-stu-id="49339-119">**URIType**</span></span> <br/> |<span data-ttu-id="49339-120">int</span><span class="sxs-lookup"><span data-stu-id="49339-120">int</span></span>  <br/> ||<span data-ttu-id="49339-121">1 est inconnu type d’URI.</span><span class="sxs-lookup"><span data-stu-id="49339-121">1 is unknown URI type.</span></span>  <br/> <span data-ttu-id="49339-122">2 est utilisateur URI.</span><span class="sxs-lookup"><span data-stu-id="49339-122">2 is user URI.</span></span>  <br/> <span data-ttu-id="49339-123">4 est la conférence URI.</span><span class="sxs-lookup"><span data-stu-id="49339-123">4 is conference URI.</span></span>  <br/> <span data-ttu-id="49339-124">8 est un URI de téléphone.</span><span class="sxs-lookup"><span data-stu-id="49339-124">8 is phone URI.</span></span>  <br/> |
|<span data-ttu-id="49339-125">**TenantKey**</span><span class="sxs-lookup"><span data-stu-id="49339-125">**TenantKey**</span></span> <br/> |<span data-ttu-id="49339-126">int</span><span class="sxs-lookup"><span data-stu-id="49339-126">int</span></span>  <br/> |<span data-ttu-id="49339-127">Étrangère</span><span class="sxs-lookup"><span data-stu-id="49339-127">Foreign</span></span>  <br/> |<span data-ttu-id="49339-128">Clients de l’utilisateur, référencé à partir de la table des clients.</span><span class="sxs-lookup"><span data-stu-id="49339-128">Tenant of the user, referenced from tenant table.</span></span>  <br/> |
|<span data-ttu-id="49339-129">**LastPoorCallTime**</span><span class="sxs-lookup"><span data-stu-id="49339-129">**LastPoorCallTime**</span></span> <br/> |<span data-ttu-id="49339-130">DateHeure</span><span class="sxs-lookup"><span data-stu-id="49339-130">datetime</span></span>  <br/> ||<span data-ttu-id="49339-131">Dernier horodatage lorsque l’utilisateur a un appel audio médiocre.</span><span class="sxs-lookup"><span data-stu-id="49339-131">Latest time stamp when the user had a poor audio call.</span></span>  <br/> |
|<span data-ttu-id="49339-132">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="49339-132">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="49339-133">DateHeure</span><span class="sxs-lookup"><span data-stu-id="49339-133">datetime</span></span>  <br/> ||<span data-ttu-id="49339-134">À usage interne uniquement.</span><span class="sxs-lookup"><span data-stu-id="49339-134">For internal use only.</span></span>  <br/> |
   

