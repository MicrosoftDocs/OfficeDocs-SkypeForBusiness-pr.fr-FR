---
title: Table UserAgent
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d6bda1c0-b053-457a-9ffa-2ae859788775
description: La table UserAgent est une table de prise en charge qui stocke une liste des agents utilisateurs différents qui ont participé à des sessions enregistrées dans la base de données. Chaque enregistrement de la table représente un agent utilisateur
ms.openlocfilehash: 432f5ccc26d790aff07f221a7ef9912d16c49499
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33907002"
---
# <a name="useragent-table"></a><span data-ttu-id="38984-104">Table UserAgent</span><span class="sxs-lookup"><span data-stu-id="38984-104">UserAgent table</span></span>
 
<span data-ttu-id="38984-105">La table UserAgent est une table de prise en charge qui stocke une liste des agents utilisateurs différents qui ont participé à des sessions enregistrées dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="38984-105">The UserAgent table is a supporting table that stores a list of the various user agents that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="38984-106">Chaque enregistrement de la table représente un agent utilisateur</span><span class="sxs-lookup"><span data-stu-id="38984-106">Each record in the table represents one user agent</span></span>
  
|<span data-ttu-id="38984-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="38984-107">**Column**</span></span>|<span data-ttu-id="38984-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="38984-108">**Data Type**</span></span>|<span data-ttu-id="38984-109">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="38984-109">**Key/Index**</span></span>|<span data-ttu-id="38984-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="38984-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="38984-111">**UserAgentKey**</span><span class="sxs-lookup"><span data-stu-id="38984-111">**UserAgentKey**</span></span> <br/> |<span data-ttu-id="38984-112">int</span><span class="sxs-lookup"><span data-stu-id="38984-112">int</span></span>  <br/> |<span data-ttu-id="38984-113">Principal</span><span class="sxs-lookup"><span data-stu-id="38984-113">Primary</span></span>  <br/> |<span data-ttu-id="38984-114">Numéro unique identifiant cet agent utilisateur.</span><span class="sxs-lookup"><span data-stu-id="38984-114">Unique number identifying this user agent.</span></span>  <br/> |
|<span data-ttu-id="38984-115">**UserAgent**</span><span class="sxs-lookup"><span data-stu-id="38984-115">**UserAgent**</span></span> <br/> |<span data-ttu-id="38984-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="38984-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="38984-117">Unique</span><span class="sxs-lookup"><span data-stu-id="38984-117">Unique</span></span>  <br/> |<span data-ttu-id="38984-118">Chaîne d’Agent utilisateur.</span><span class="sxs-lookup"><span data-stu-id="38984-118">User Agent string.</span></span>  <br/> |
|<span data-ttu-id="38984-119">**UAType**</span><span class="sxs-lookup"><span data-stu-id="38984-119">**UAType**</span></span> <br/> |<span data-ttu-id="38984-120">smallint</span><span class="sxs-lookup"><span data-stu-id="38984-120">smallint</span></span>  <br/> | <br/> |<span data-ttu-id="38984-121">1 est le serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="38984-121">1 is Mediation Server.</span></span>  <br/> <span data-ttu-id="38984-122">2 a / V Conferencing Server.</span><span class="sxs-lookup"><span data-stu-id="38984-122">2 is A/V Conferencing Server.</span></span>  <br/> <span data-ttu-id="38984-123">4 est Skype pour les entreprises.</span><span class="sxs-lookup"><span data-stu-id="38984-123">4 is Skype for Business.</span></span>  <br/> <span data-ttu-id="38984-124">8 est un téléphone IP.</span><span class="sxs-lookup"><span data-stu-id="38984-124">8 is IP Phone.</span></span>  <br/> <span data-ttu-id="38984-125">16 correspond à la Console Live Meeting.</span><span class="sxs-lookup"><span data-stu-id="38984-125">16 is Live Meeting Console.</span></span>  <br/> <span data-ttu-id="38984-126">32 est un outil de Validation de déploiement (configurations).</span><span class="sxs-lookup"><span data-stu-id="38984-126">32 is Deployment Validation Tool (DVT).</span></span>  <br/> <span data-ttu-id="38984-127">64 est Skype pour Business Server sur les ordinateurs Macintosh.</span><span class="sxs-lookup"><span data-stu-id="38984-127">64 is Skype for Business Server on Macintosh computers.</span></span>  <br/> <span data-ttu-id="38984-128">128 est Skype pour Business Server Attendant.</span><span class="sxs-lookup"><span data-stu-id="38984-128">128 is Skype for Business Server Attendant.</span></span>  <br/> <span data-ttu-id="38984-129">256 est un service d’annonce de conférence.</span><span class="sxs-lookup"><span data-stu-id="38984-129">256 is Conferencing Announcement service.</span></span>  <br/> <span data-ttu-id="38984-130">512 correspond au standard automatique de conférence.</span><span class="sxs-lookup"><span data-stu-id="38984-130">512 is Conferencing Auto Attendant.</span></span>  <br/> <span data-ttu-id="38984-131">1024 correspond à l’application Response Group.</span><span class="sxs-lookup"><span data-stu-id="38984-131">1024 is Response Group application.</span></span>  <br/> <span data-ttu-id="38984-132">2048 correspond au contrôle vocal extérieur.</span><span class="sxs-lookup"><span data-stu-id="38984-132">2048 is Outside Voice Control.</span></span>  <br/> |
   

