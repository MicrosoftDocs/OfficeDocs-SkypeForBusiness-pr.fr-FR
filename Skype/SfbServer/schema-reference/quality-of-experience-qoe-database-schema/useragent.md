---
title: Table UserAgent
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d6bda1c0-b053-457a-9ffa-2ae859788775
description: La table UserAgent est une table de prise en charge qui stocke une liste des agents utilisateurs différents qui ont participé à des sessions enregistrées dans la base de données. Chaque enregistrement de la table représente un agent utilisateur
ms.openlocfilehash: 17cb395569e8a634925be27705b878b104a3b70a
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30893103"
---
# <a name="useragent-table"></a><span data-ttu-id="0611b-104">Table UserAgent</span><span class="sxs-lookup"><span data-stu-id="0611b-104">UserAgent table</span></span>
 
<span data-ttu-id="0611b-105">La table UserAgent est une table de prise en charge qui stocke une liste des agents utilisateurs différents qui ont participé à des sessions enregistrées dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="0611b-105">The UserAgent table is a supporting table that stores a list of the various user agents that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="0611b-106">Chaque enregistrement de la table représente un agent utilisateur</span><span class="sxs-lookup"><span data-stu-id="0611b-106">Each record in the table represents one user agent</span></span>
  
|<span data-ttu-id="0611b-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="0611b-107">**Column**</span></span>|<span data-ttu-id="0611b-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="0611b-108">**Data Type**</span></span>|<span data-ttu-id="0611b-109">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="0611b-109">**Key/Index**</span></span>|<span data-ttu-id="0611b-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="0611b-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="0611b-111">**UserAgentKey**</span><span class="sxs-lookup"><span data-stu-id="0611b-111">**UserAgentKey**</span></span> <br/> |<span data-ttu-id="0611b-112">int</span><span class="sxs-lookup"><span data-stu-id="0611b-112">int</span></span>  <br/> |<span data-ttu-id="0611b-113">Principal</span><span class="sxs-lookup"><span data-stu-id="0611b-113">Primary</span></span>  <br/> |<span data-ttu-id="0611b-114">Numéro unique identifiant cet agent utilisateur.</span><span class="sxs-lookup"><span data-stu-id="0611b-114">Unique number identifying this user agent.</span></span>  <br/> |
|<span data-ttu-id="0611b-115">**UserAgent**</span><span class="sxs-lookup"><span data-stu-id="0611b-115">**UserAgent**</span></span> <br/> |<span data-ttu-id="0611b-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="0611b-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="0611b-117">Unique</span><span class="sxs-lookup"><span data-stu-id="0611b-117">Unique</span></span>  <br/> |<span data-ttu-id="0611b-118">Chaîne d’Agent utilisateur.</span><span class="sxs-lookup"><span data-stu-id="0611b-118">User Agent string.</span></span>  <br/> |
|<span data-ttu-id="0611b-119">**UAType**</span><span class="sxs-lookup"><span data-stu-id="0611b-119">**UAType**</span></span> <br/> |<span data-ttu-id="0611b-120">smallint</span><span class="sxs-lookup"><span data-stu-id="0611b-120">smallint</span></span>  <br/> | <br/> |<span data-ttu-id="0611b-121">1 est le serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="0611b-121">1 is Mediation Server.</span></span>  <br/> <span data-ttu-id="0611b-122">2 a / V Conferencing Server.</span><span class="sxs-lookup"><span data-stu-id="0611b-122">2 is A/V Conferencing Server.</span></span>  <br/> <span data-ttu-id="0611b-123">4 est Skype pour les entreprises.</span><span class="sxs-lookup"><span data-stu-id="0611b-123">4 is Skype for Business.</span></span>  <br/> <span data-ttu-id="0611b-124">8 est un téléphone IP.</span><span class="sxs-lookup"><span data-stu-id="0611b-124">8 is IP Phone.</span></span>  <br/> <span data-ttu-id="0611b-125">16 correspond à la Console Live Meeting.</span><span class="sxs-lookup"><span data-stu-id="0611b-125">16 is Live Meeting Console.</span></span>  <br/> <span data-ttu-id="0611b-126">32 est un outil de Validation de déploiement (configurations).</span><span class="sxs-lookup"><span data-stu-id="0611b-126">32 is Deployment Validation Tool (DVT).</span></span>  <br/> <span data-ttu-id="0611b-127">64 est Skype pour Business Server sur les ordinateurs Macintosh.</span><span class="sxs-lookup"><span data-stu-id="0611b-127">64 is Skype for Business Server on Macintosh computers.</span></span>  <br/> <span data-ttu-id="0611b-128">128 est Skype pour Business Server Attendant.</span><span class="sxs-lookup"><span data-stu-id="0611b-128">128 is Skype for Business Server Attendant.</span></span>  <br/> <span data-ttu-id="0611b-129">256 est un service d’annonce de conférence.</span><span class="sxs-lookup"><span data-stu-id="0611b-129">256 is Conferencing Announcement service.</span></span>  <br/> <span data-ttu-id="0611b-130">512 correspond au standard automatique de conférence.</span><span class="sxs-lookup"><span data-stu-id="0611b-130">512 is Conferencing Auto Attendant.</span></span>  <br/> <span data-ttu-id="0611b-131">1024 correspond à l’application Response Group.</span><span class="sxs-lookup"><span data-stu-id="0611b-131">1024 is Response Group application.</span></span>  <br/> <span data-ttu-id="0611b-132">2048 correspond au contrôle vocal extérieur.</span><span class="sxs-lookup"><span data-stu-id="0611b-132">2048 is Outside Voice Control.</span></span>  <br/> |
   

