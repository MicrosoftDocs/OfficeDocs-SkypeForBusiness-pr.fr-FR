---
title: Table ConferenceUris dans Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b1721d52-3c65-45ea-8997-06af8fef93fc
description: La table ConferenceUris est une table de prise en charge qui stocke une liste des différentes URI de conférence qui ont participé aux sessions de conférence enregistrées dans la base de données. Chaque enregistrement dans le tableau représente une URI de conférence.
ms.openlocfilehash: f439c828460f06067105f8f2da493616c223ed85
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816134"
---
# <a name="conferenceuris-table-in-skype-for-business-server-2015"></a><span data-ttu-id="70178-104">Table ConferenceUris dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="70178-104">ConferenceUris table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="70178-p102">La table ConferenceUris est une table de prise en charge qui stocke une liste des différentes URI de conférence qui ont participé aux sessions de conférence enregistrées dans la base de données. Chaque enregistrement dans le tableau représente une URI de conférence.</span><span class="sxs-lookup"><span data-stu-id="70178-p102">The ConfereneUris table is a supporting table that stores a list of the various conference URIs that have participated in conference sessions recorded in the database. Each record in the table represents one conference URI.</span></span>
  
|<span data-ttu-id="70178-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="70178-107">**Column**</span></span>|<span data-ttu-id="70178-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="70178-108">**Data Type**</span></span>|<span data-ttu-id="70178-109">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="70178-109">**Key/Index**</span></span>|<span data-ttu-id="70178-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="70178-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="70178-111">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="70178-111">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="70178-112">DateHeure</span><span class="sxs-lookup"><span data-stu-id="70178-112">datetime</span></span>  <br/> |<span data-ttu-id="70178-113">Primaire</span><span class="sxs-lookup"><span data-stu-id="70178-113">Primary</span></span>  <br/> |<span data-ttu-id="70178-114">Horodatage pour utilisation interne.</span><span class="sxs-lookup"><span data-stu-id="70178-114">Time stamp, Internal used.</span></span>  <br/> |
|<span data-ttu-id="70178-115">**ConferenceUriId**</span><span class="sxs-lookup"><span data-stu-id="70178-115">**ConferenceUriId**</span></span> <br/> |<span data-ttu-id="70178-116">int</span><span class="sxs-lookup"><span data-stu-id="70178-116">int</span></span>  <br/> |<span data-ttu-id="70178-117">Primaire</span><span class="sxs-lookup"><span data-stu-id="70178-117">Primary</span></span>  <br/> |<span data-ttu-id="70178-118">Numéro unique identifiant cette URI de conférence.</span><span class="sxs-lookup"><span data-stu-id="70178-118">Unique number identifying this conference URI.</span></span>  <br/> |
|<span data-ttu-id="70178-119">**ConferenceUri**</span><span class="sxs-lookup"><span data-stu-id="70178-119">**ConferenceUri**</span></span> <br/> |<span data-ttu-id="70178-120">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="70178-120">nvarchar(450)</span></span>  <br/> ||<span data-ttu-id="70178-121">URI de la conférence.</span><span class="sxs-lookup"><span data-stu-id="70178-121">Conference URI.</span></span>  <br/> |
|<span data-ttu-id="70178-122">**Somme de contrôle**</span><span class="sxs-lookup"><span data-stu-id="70178-122">**Checksum**</span></span> <br/> |<span data-ttu-id="70178-123">int</span><span class="sxs-lookup"><span data-stu-id="70178-123">int</span></span>  <br/> ||<span data-ttu-id="70178-p103">Checksum de ConferenceUri. Sert à augmenter la vitesse des recherches dans les bases de données.</span><span class="sxs-lookup"><span data-stu-id="70178-p103">Checksum of ConferenceUri. Used to increases the speed of database searches.</span></span>  <br/> |
|<span data-ttu-id="70178-126">**UriTypeId**</span><span class="sxs-lookup"><span data-stu-id="70178-126">**UriTypeId**</span></span> <br/> |<span data-ttu-id="70178-127">int</span><span class="sxs-lookup"><span data-stu-id="70178-127">int</span></span>  <br/> |<span data-ttu-id="70178-128">Étranger</span><span class="sxs-lookup"><span data-stu-id="70178-128">Foreign</span></span>  <br/> |<span data-ttu-id="70178-129">Type d’URI, tel que conf:chat pour une conférence de messagerie instantanée ou conf:audio-video pour une conférence audio/vidéo.</span><span class="sxs-lookup"><span data-stu-id="70178-129">URI type, such as conf:chat for IM conference, or conf:audio-video for audio/video conference.</span></span> <span data-ttu-id="70178-130">Pour plus [d’informations, voir la table UriTypes.](uritypes.md)</span><span class="sxs-lookup"><span data-stu-id="70178-130">See the [UriTypes table](uritypes.md) table for more information.</span></span> <br/> |
   

