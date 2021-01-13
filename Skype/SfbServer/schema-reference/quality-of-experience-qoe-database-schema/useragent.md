---
title: Table UserAgent
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
ms.assetid: d6bda1c0-b053-457a-9ffa-2ae859788775
description: La table UserAgent est une table de prise en charge qui stocke la liste des différents agents utilisateurs qui ont participé à des sessions enregistrées dans la base de données. Chaque enregistrement de la table représente un agent utilisateur
ms.openlocfilehash: a1d0e647ff78d409555988a27592228fac2643be
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49799934"
---
# <a name="useragent-table"></a><span data-ttu-id="01674-104">Table UserAgent</span><span class="sxs-lookup"><span data-stu-id="01674-104">UserAgent table</span></span>
 
<span data-ttu-id="01674-105">La table UserAgent est une table de prise en charge qui stocke la liste des différents agents utilisateurs qui ont participé à des sessions enregistrées dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="01674-105">The UserAgent table is a supporting table that stores a list of the various user agents that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="01674-106">Chaque enregistrement de la table représente un agent utilisateur</span><span class="sxs-lookup"><span data-stu-id="01674-106">Each record in the table represents one user agent</span></span>
  
|<span data-ttu-id="01674-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="01674-107">**Column**</span></span>|<span data-ttu-id="01674-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="01674-108">**Data Type**</span></span>|<span data-ttu-id="01674-109">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="01674-109">**Key/Index**</span></span>|<span data-ttu-id="01674-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="01674-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="01674-111">**UserAgentKey**</span><span class="sxs-lookup"><span data-stu-id="01674-111">**UserAgentKey**</span></span> <br/> |<span data-ttu-id="01674-112">int</span><span class="sxs-lookup"><span data-stu-id="01674-112">int</span></span>  <br/> |<span data-ttu-id="01674-113">Primaire</span><span class="sxs-lookup"><span data-stu-id="01674-113">Primary</span></span>  <br/> |<span data-ttu-id="01674-114">Numéro unique qui identifie cet agent utilisateur.</span><span class="sxs-lookup"><span data-stu-id="01674-114">Unique number identifying this user agent.</span></span>  <br/> |
|<span data-ttu-id="01674-115">**UserAgent**</span><span class="sxs-lookup"><span data-stu-id="01674-115">**UserAgent**</span></span> <br/> |<span data-ttu-id="01674-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="01674-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="01674-117">Uniques</span><span class="sxs-lookup"><span data-stu-id="01674-117">Unique</span></span>  <br/> |<span data-ttu-id="01674-118">Chaîne de l’agent utilisateur.</span><span class="sxs-lookup"><span data-stu-id="01674-118">User Agent string.</span></span>  <br/> |
|<span data-ttu-id="01674-119">**UAType**</span><span class="sxs-lookup"><span data-stu-id="01674-119">**UAType**</span></span> <br/> |<span data-ttu-id="01674-120">smallint</span><span class="sxs-lookup"><span data-stu-id="01674-120">smallint</span></span>  <br/> | <br/> |<span data-ttu-id="01674-121">1 est serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="01674-121">1 is Mediation Server.</span></span>  <br/> <span data-ttu-id="01674-122">2 est un serveur de conférence A/V.</span><span class="sxs-lookup"><span data-stu-id="01674-122">2 is A/V Conferencing Server.</span></span>  <br/> <span data-ttu-id="01674-123">4 est Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="01674-123">4 is Skype for Business.</span></span>  <br/> <span data-ttu-id="01674-124">8 est un téléphone IP.</span><span class="sxs-lookup"><span data-stu-id="01674-124">8 is IP Phone.</span></span>  <br/> <span data-ttu-id="01674-125">16 est Live Meeting Console.</span><span class="sxs-lookup"><span data-stu-id="01674-125">16 is Live Meeting Console.</span></span>  <br/> <span data-ttu-id="01674-126">32 est l’outil de validation de déploiement (DVT).</span><span class="sxs-lookup"><span data-stu-id="01674-126">32 is Deployment Validation Tool (DVT).</span></span>  <br/> <span data-ttu-id="01674-127">64 est Skype Entreprise Server sur les ordinateurs Macintosh.</span><span class="sxs-lookup"><span data-stu-id="01674-127">64 is Skype for Business Server on Macintosh computers.</span></span>  <br/> <span data-ttu-id="01674-128">128 est Skype Entreprise Server Attendant.</span><span class="sxs-lookup"><span data-stu-id="01674-128">128 is Skype for Business Server Attendant.</span></span>  <br/> <span data-ttu-id="01674-129">256 est le service d’annonce de conférence.</span><span class="sxs-lookup"><span data-stu-id="01674-129">256 is Conferencing Announcement service.</span></span>  <br/> <span data-ttu-id="01674-130">512 est l’Standard automatique.</span><span class="sxs-lookup"><span data-stu-id="01674-130">512 is Conferencing Auto Attendant.</span></span>  <br/> <span data-ttu-id="01674-131">1024 est l’application Response Group.</span><span class="sxs-lookup"><span data-stu-id="01674-131">1024 is Response Group application.</span></span>  <br/> <span data-ttu-id="01674-132">2048 est hors contrôle vocal.</span><span class="sxs-lookup"><span data-stu-id="01674-132">2048 is Outside Voice Control.</span></span>  <br/> |
   

