---
title: Table ConferenceUris dans Skype pour Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b1721d52-3c65-45ea-8997-06af8fef93fc
description: Le tableau ConfereneUris est une table de prise en charge qui stocke une liste de la conférence différents URI qui ont participé à des sessions de conférence enregistrées dans la base de données. Chaque enregistrement de la table représente une URI de conférence.
ms.openlocfilehash: 6f373774b652e9858af84dd4c16b51fcb3c5d493
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30887770"
---
# <a name="conferenceuris-table-in-skype-for-business-server-2015"></a><span data-ttu-id="b32ac-104">Table ConferenceUris dans Skype pour Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="b32ac-104">ConferenceUris table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="b32ac-105">Le tableau ConfereneUris est une table de prise en charge qui stocke une liste de la conférence différents URI qui ont participé à des sessions de conférence enregistrées dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="b32ac-105">The ConfereneUris table is a supporting table that stores a list of the various conference URIs that have participated in conference sessions recorded in the database.</span></span> <span data-ttu-id="b32ac-106">Chaque enregistrement de la table représente une URI de conférence.</span><span class="sxs-lookup"><span data-stu-id="b32ac-106">Each record in the table represents one conference URI.</span></span>
  
|<span data-ttu-id="b32ac-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="b32ac-107">**Column**</span></span>|<span data-ttu-id="b32ac-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="b32ac-108">**Data Type**</span></span>|<span data-ttu-id="b32ac-109">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="b32ac-109">**Key/Index**</span></span>|<span data-ttu-id="b32ac-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="b32ac-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b32ac-111">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="b32ac-111">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="b32ac-112">DateHeure</span><span class="sxs-lookup"><span data-stu-id="b32ac-112">datetime</span></span>  <br/> |<span data-ttu-id="b32ac-113">Principal</span><span class="sxs-lookup"><span data-stu-id="b32ac-113">Primary</span></span>  <br/> |<span data-ttu-id="b32ac-114">Horodatage pour utilisation interne.</span><span class="sxs-lookup"><span data-stu-id="b32ac-114">Time stamp, Internal used.</span></span>  <br/> |
|<span data-ttu-id="b32ac-115">**ConferenceUriId**</span><span class="sxs-lookup"><span data-stu-id="b32ac-115">**ConferenceUriId**</span></span> <br/> |<span data-ttu-id="b32ac-116">int</span><span class="sxs-lookup"><span data-stu-id="b32ac-116">int</span></span>  <br/> |<span data-ttu-id="b32ac-117">Principal</span><span class="sxs-lookup"><span data-stu-id="b32ac-117">Primary</span></span>  <br/> |<span data-ttu-id="b32ac-118">Numéro unique identifiant cette URI de conférence.</span><span class="sxs-lookup"><span data-stu-id="b32ac-118">Unique number identifying this conference URI.</span></span>  <br/> |
|<span data-ttu-id="b32ac-119">**ConferenceUri**</span><span class="sxs-lookup"><span data-stu-id="b32ac-119">**ConferenceUri**</span></span> <br/> |<span data-ttu-id="b32ac-120">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="b32ac-120">nvarchar(450)</span></span>  <br/> ||<span data-ttu-id="b32ac-121">URI de conférence.</span><span class="sxs-lookup"><span data-stu-id="b32ac-121">Conference URI.</span></span>  <br/> |
|<span data-ttu-id="b32ac-122">**Somme de contrôle**</span><span class="sxs-lookup"><span data-stu-id="b32ac-122">**Checksum**</span></span> <br/> |<span data-ttu-id="b32ac-123">int</span><span class="sxs-lookup"><span data-stu-id="b32ac-123">int</span></span>  <br/> ||<span data-ttu-id="b32ac-124">Somme de contrôle de ConferenceUri.</span><span class="sxs-lookup"><span data-stu-id="b32ac-124">Checksum of ConferenceUri.</span></span> <span data-ttu-id="b32ac-125">Utilisé pour augmenter la vitesse des recherches de base de données.</span><span class="sxs-lookup"><span data-stu-id="b32ac-125">Used to increases the speed of database searches.</span></span>  <br/> |
|<span data-ttu-id="b32ac-126">**UriTypeId**</span><span class="sxs-lookup"><span data-stu-id="b32ac-126">**UriTypeId**</span></span> <br/> |<span data-ttu-id="b32ac-127">int</span><span class="sxs-lookup"><span data-stu-id="b32ac-127">int</span></span>  <br/> |<span data-ttu-id="b32ac-128">Étrangère</span><span class="sxs-lookup"><span data-stu-id="b32ac-128">Foreign</span></span>  <br/> |<span data-ttu-id="b32ac-129">Type d’URI, tel que conf:chat pour la conférence par messagerie instantanée ou conf:audio-vidéo pour la conférence audio/vidéo.</span><span class="sxs-lookup"><span data-stu-id="b32ac-129">URI type, such as conf:chat for IM conference, or conf:audio-video for audio/video conference.</span></span> <span data-ttu-id="b32ac-130">Voir la table [UriTypes](uritypes.md) pour plus d’informations.</span><span class="sxs-lookup"><span data-stu-id="b32ac-130">See the [UriTypes table](uritypes.md) table for more information.</span></span> <br/> |
   

