---
title: Table ConferenceUris dans Skype pour Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b1721d52-3c65-45ea-8997-06af8fef93fc
description: La table ConfereneUris est un tableau de prise en charge qui stocke une liste de la conférence différents URI qui ont participé aux sessions de conférence enregistrées dans la base de données. Chaque enregistrement de la table représente une conférence URI.
ms.openlocfilehash: 921bb448ffe50d62aa7680db0e8097c186eef8e7
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="conferenceuris-table-in-skype-for-business-server-2015"></a><span data-ttu-id="5be27-104">Table ConferenceUris dans Skype pour Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="5be27-104">ConferenceUris table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="5be27-105">La table ConfereneUris est un tableau de prise en charge qui stocke une liste de la conférence différents URI qui ont participé aux sessions de conférence enregistrées dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="5be27-105">The ConfereneUris table is a supporting table that stores a list of the various conference URIs that have participated in conference sessions recorded in the database.</span></span> <span data-ttu-id="5be27-106">Chaque enregistrement de la table représente une conférence URI.</span><span class="sxs-lookup"><span data-stu-id="5be27-106">Each record in the table represents one conference URI.</span></span>
  
|<span data-ttu-id="5be27-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="5be27-107">**Column**</span></span>|<span data-ttu-id="5be27-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="5be27-108">**Data Type**</span></span>|<span data-ttu-id="5be27-109">**Index de la clé**</span><span class="sxs-lookup"><span data-stu-id="5be27-109">**Key/Index**</span></span>|<span data-ttu-id="5be27-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="5be27-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="5be27-111">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="5be27-111">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="5be27-112">DateHeure</span><span class="sxs-lookup"><span data-stu-id="5be27-112">datetime</span></span>  <br/> |<span data-ttu-id="5be27-113">Principal</span><span class="sxs-lookup"><span data-stu-id="5be27-113">Primary</span></span>  <br/> |<span data-ttu-id="5be27-114">Horodatage, interne utilisé.</span><span class="sxs-lookup"><span data-stu-id="5be27-114">Time stamp, Internal used.</span></span>  <br/> |
|<span data-ttu-id="5be27-115">**ConferenceUriId**</span><span class="sxs-lookup"><span data-stu-id="5be27-115">**ConferenceUriId**</span></span> <br/> |<span data-ttu-id="5be27-116">int</span><span class="sxs-lookup"><span data-stu-id="5be27-116">int</span></span>  <br/> |<span data-ttu-id="5be27-117">Principal</span><span class="sxs-lookup"><span data-stu-id="5be27-117">Primary</span></span>  <br/> |<span data-ttu-id="5be27-118">Numéro unique identifiant cette conférence URI.</span><span class="sxs-lookup"><span data-stu-id="5be27-118">Unique number identifying this conference URI.</span></span>  <br/> |
|<span data-ttu-id="5be27-119">**ConferenceUri**</span><span class="sxs-lookup"><span data-stu-id="5be27-119">**ConferenceUri**</span></span> <br/> |<span data-ttu-id="5be27-120">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="5be27-120">nvarchar(450)</span></span>  <br/> ||<span data-ttu-id="5be27-121">Conférence URI.</span><span class="sxs-lookup"><span data-stu-id="5be27-121">Conference URI.</span></span>  <br/> |
|<span data-ttu-id="5be27-122">**Somme de contrôle**</span><span class="sxs-lookup"><span data-stu-id="5be27-122">**Checksum**</span></span> <br/> |<span data-ttu-id="5be27-123">int</span><span class="sxs-lookup"><span data-stu-id="5be27-123">int</span></span>  <br/> ||<span data-ttu-id="5be27-124">Total de contrôle de ConferenceUri.</span><span class="sxs-lookup"><span data-stu-id="5be27-124">Checksum of ConferenceUri.</span></span> <span data-ttu-id="5be27-125">Utilisé pour augmente la vitesse de recherche de la base de données.</span><span class="sxs-lookup"><span data-stu-id="5be27-125">Used to increases the speed of database searches.</span></span>  <br/> |
|<span data-ttu-id="5be27-126">**UriTypeId**</span><span class="sxs-lookup"><span data-stu-id="5be27-126">**UriTypeId**</span></span> <br/> |<span data-ttu-id="5be27-127">int</span><span class="sxs-lookup"><span data-stu-id="5be27-127">int</span></span>  <br/> |<span data-ttu-id="5be27-128">Étrangère</span><span class="sxs-lookup"><span data-stu-id="5be27-128">Foreign</span></span>  <br/> |<span data-ttu-id="5be27-129">Type d’URI, telles que conf:chat pour la conférence par messagerie instantanée ou conf:audio-vidéo pour les conférences audio/vidéo.</span><span class="sxs-lookup"><span data-stu-id="5be27-129">URI type, such as conf:chat for IM conference, or conf:audio-video for audio/video conference.</span></span> <span data-ttu-id="5be27-130">Consultez la table [UriTypes](uritypes.md) pour plus d’informations.</span><span class="sxs-lookup"><span data-stu-id="5be27-130">See the [UriTypes table](uritypes.md) table for more information.</span></span> <br/> |
   

