---
title: Table ConferenceUris dans Skype entreprise Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b1721d52-3c65-45ea-8997-06af8fef93fc
description: La table ConfereneUris est une table qui contient une liste des différents URI de conférence ayant participé à des sessions de conférence enregistrées dans la base de données. Chaque enregistrement de la table représente un URI de conférence.
ms.openlocfilehash: f1e95cce4fedf26477973a4fba6a9d3a32288f92
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815312"
---
# <a name="conferenceuris-table-in-skype-for-business-server-2015"></a><span data-ttu-id="c1221-104">Table ConferenceUris dans Skype entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="c1221-104">ConferenceUris table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="c1221-105">La table ConfereneUris est une table qui contient une liste des différents URI de conférence ayant participé à des sessions de conférence enregistrées dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="c1221-105">The ConfereneUris table is a supporting table that stores a list of the various conference URIs that have participated in conference sessions recorded in the database.</span></span> <span data-ttu-id="c1221-106">Chaque enregistrement de la table représente un URI de conférence.</span><span class="sxs-lookup"><span data-stu-id="c1221-106">Each record in the table represents one conference URI.</span></span>
  
|<span data-ttu-id="c1221-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="c1221-107">**Column**</span></span>|<span data-ttu-id="c1221-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="c1221-108">**Data Type**</span></span>|<span data-ttu-id="c1221-109">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="c1221-109">**Key/Index**</span></span>|<span data-ttu-id="c1221-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="c1221-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c1221-111">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="c1221-111">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="c1221-112">DateHeure</span><span class="sxs-lookup"><span data-stu-id="c1221-112">datetime</span></span>  <br/> |<span data-ttu-id="c1221-113">Principal</span><span class="sxs-lookup"><span data-stu-id="c1221-113">Primary</span></span>  <br/> |<span data-ttu-id="c1221-114">Date et heure d’utilisation internes.</span><span class="sxs-lookup"><span data-stu-id="c1221-114">Time stamp, Internal used.</span></span>  <br/> |
|<span data-ttu-id="c1221-115">**ConferenceUriId**</span><span class="sxs-lookup"><span data-stu-id="c1221-115">**ConferenceUriId**</span></span> <br/> |<span data-ttu-id="c1221-116">int</span><span class="sxs-lookup"><span data-stu-id="c1221-116">int</span></span>  <br/> |<span data-ttu-id="c1221-117">Principal</span><span class="sxs-lookup"><span data-stu-id="c1221-117">Primary</span></span>  <br/> |<span data-ttu-id="c1221-118">Numéro unique identifiant cet URI de conférence.</span><span class="sxs-lookup"><span data-stu-id="c1221-118">Unique number identifying this conference URI.</span></span>  <br/> |
|<span data-ttu-id="c1221-119">**ConferenceUri**</span><span class="sxs-lookup"><span data-stu-id="c1221-119">**ConferenceUri**</span></span> <br/> |<span data-ttu-id="c1221-120">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="c1221-120">nvarchar(450)</span></span>  <br/> ||<span data-ttu-id="c1221-121">URI de conférence.</span><span class="sxs-lookup"><span data-stu-id="c1221-121">Conference URI.</span></span>  <br/> |
|<span data-ttu-id="c1221-122">**1018**</span><span class="sxs-lookup"><span data-stu-id="c1221-122">**Checksum**</span></span> <br/> |<span data-ttu-id="c1221-123">int</span><span class="sxs-lookup"><span data-stu-id="c1221-123">int</span></span>  <br/> ||<span data-ttu-id="c1221-124">Checksum de ConferenceUri.</span><span class="sxs-lookup"><span data-stu-id="c1221-124">Checksum of ConferenceUri.</span></span> <span data-ttu-id="c1221-125">Permet d’augmenter la vitesse de recherche de la base de données.</span><span class="sxs-lookup"><span data-stu-id="c1221-125">Used to increases the speed of database searches.</span></span>  <br/> |
|<span data-ttu-id="c1221-126">**UriTypeId**</span><span class="sxs-lookup"><span data-stu-id="c1221-126">**UriTypeId**</span></span> <br/> |<span data-ttu-id="c1221-127">int</span><span class="sxs-lookup"><span data-stu-id="c1221-127">int</span></span>  <br/> |<span data-ttu-id="c1221-128">Externes</span><span class="sxs-lookup"><span data-stu-id="c1221-128">Foreign</span></span>  <br/> |<span data-ttu-id="c1221-129">Type d’URI (par exemple, conf : chat pour une conférence par messagerie instantanée, ou conf : audio-vidéo pour les conférences audio/vidéo).</span><span class="sxs-lookup"><span data-stu-id="c1221-129">URI type, such as conf:chat for IM conference, or conf:audio-video for audio/video conference.</span></span> <span data-ttu-id="c1221-130">Pour plus d’informations, voir la table [UriTypes table](uritypes.md) .</span><span class="sxs-lookup"><span data-stu-id="c1221-130">See the [UriTypes table](uritypes.md) table for more information.</span></span> <br/> |
   

