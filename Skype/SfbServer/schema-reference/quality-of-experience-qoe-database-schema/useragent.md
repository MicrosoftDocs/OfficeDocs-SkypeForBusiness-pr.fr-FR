---
title: Table UserAgent
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d6bda1c0-b053-457a-9ffa-2ae859788775
description: La table UserAgent est une table qui contient une liste des différents agents utilisateurs ayant participé à des sessions enregistrées dans la base de données. Chaque enregistrement de la table représente un agent utilisateur
ms.openlocfilehash: f0c8a2f182611887db1324d17b6b7c28d6a9393d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294585"
---
# <a name="useragent-table"></a><span data-ttu-id="c981a-104">Table UserAgent</span><span class="sxs-lookup"><span data-stu-id="c981a-104">UserAgent table</span></span>
 
<span data-ttu-id="c981a-105">La table UserAgent est une table qui contient une liste des différents agents utilisateurs ayant participé à des sessions enregistrées dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="c981a-105">The UserAgent table is a supporting table that stores a list of the various user agents that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="c981a-106">Chaque enregistrement de la table représente un agent utilisateur</span><span class="sxs-lookup"><span data-stu-id="c981a-106">Each record in the table represents one user agent</span></span>
  
|<span data-ttu-id="c981a-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="c981a-107">**Column**</span></span>|<span data-ttu-id="c981a-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="c981a-108">**Data Type**</span></span>|<span data-ttu-id="c981a-109">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="c981a-109">**Key/Index**</span></span>|<span data-ttu-id="c981a-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="c981a-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c981a-111">**UserAgentKey**</span><span class="sxs-lookup"><span data-stu-id="c981a-111">**UserAgentKey**</span></span> <br/> |<span data-ttu-id="c981a-112">int</span><span class="sxs-lookup"><span data-stu-id="c981a-112">int</span></span>  <br/> |<span data-ttu-id="c981a-113">Principal</span><span class="sxs-lookup"><span data-stu-id="c981a-113">Primary</span></span>  <br/> |<span data-ttu-id="c981a-114">Numéro unique identifiant cet agent utilisateur.</span><span class="sxs-lookup"><span data-stu-id="c981a-114">Unique number identifying this user agent.</span></span>  <br/> |
|<span data-ttu-id="c981a-115">**UserAgent**</span><span class="sxs-lookup"><span data-stu-id="c981a-115">**UserAgent**</span></span> <br/> |<span data-ttu-id="c981a-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="c981a-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="c981a-117">Différent</span><span class="sxs-lookup"><span data-stu-id="c981a-117">Unique</span></span>  <br/> |<span data-ttu-id="c981a-118">Chaîne de l’agent utilisateur.</span><span class="sxs-lookup"><span data-stu-id="c981a-118">User Agent string.</span></span>  <br/> |
|<span data-ttu-id="c981a-119">**UAType**</span><span class="sxs-lookup"><span data-stu-id="c981a-119">**UAType**</span></span> <br/> |<span data-ttu-id="c981a-120">type</span><span class="sxs-lookup"><span data-stu-id="c981a-120">smallint</span></span>  <br/> | <br/> |<span data-ttu-id="c981a-121">1 est un serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="c981a-121">1 is Mediation Server.</span></span>  <br/> <span data-ttu-id="c981a-122">2 est un serveur de conférence A/V.</span><span class="sxs-lookup"><span data-stu-id="c981a-122">2 is A/V Conferencing Server.</span></span>  <br/> <span data-ttu-id="c981a-123">4 est Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="c981a-123">4 is Skype for Business.</span></span>  <br/> <span data-ttu-id="c981a-124">8 est le téléphone IP.</span><span class="sxs-lookup"><span data-stu-id="c981a-124">8 is IP Phone.</span></span>  <br/> <span data-ttu-id="c981a-125">16 est la console Live Meeting.</span><span class="sxs-lookup"><span data-stu-id="c981a-125">16 is Live Meeting Console.</span></span>  <br/> <span data-ttu-id="c981a-126">32 est l’outil de validation du déploiement (DVT).</span><span class="sxs-lookup"><span data-stu-id="c981a-126">32 is Deployment Validation Tool (DVT).</span></span>  <br/> <span data-ttu-id="c981a-127">64 est Skype entreprise Server sur les ordinateurs Macintosh.</span><span class="sxs-lookup"><span data-stu-id="c981a-127">64 is Skype for Business Server on Macintosh computers.</span></span>  <br/> <span data-ttu-id="c981a-128">128 est Skype entreprise Server attendant.</span><span class="sxs-lookup"><span data-stu-id="c981a-128">128 is Skype for Business Server Attendant.</span></span>  <br/> <span data-ttu-id="c981a-129">256 est le service d’annonce de conférence.</span><span class="sxs-lookup"><span data-stu-id="c981a-129">256 is Conferencing Announcement service.</span></span>  <br/> <span data-ttu-id="c981a-130">512 est le standard automatique de conférence.</span><span class="sxs-lookup"><span data-stu-id="c981a-130">512 is Conferencing Auto Attendant.</span></span>  <br/> <span data-ttu-id="c981a-131">1024 est une application de Response Group.</span><span class="sxs-lookup"><span data-stu-id="c981a-131">1024 is Response Group application.</span></span>  <br/> <span data-ttu-id="c981a-132">2048 est hors du contrôle vocal.</span><span class="sxs-lookup"><span data-stu-id="c981a-132">2048 is Outside Voice Control.</span></span>  <br/> |
   

