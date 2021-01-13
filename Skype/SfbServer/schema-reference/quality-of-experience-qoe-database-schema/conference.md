---
title: Table Conference
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
ms.assetid: 2a2c327c-4719-42dc-a3bb-6dbc0864d9af
description: La table Conference est une table de prise en charge. Chaque enregistrement représente une conférence ou une session d’égal à égal.
ms.openlocfilehash: 3840ad9bb4f9b0ff0aea5068c73d307d5bd0cf5e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802784"
---
# <a name="conference-table"></a><span data-ttu-id="d4912-104">Table Conference</span><span class="sxs-lookup"><span data-stu-id="d4912-104">Conference table</span></span>
 
<span data-ttu-id="d4912-p102">La table Conference est une table de prise en charge. Chaque enregistrement représente une conférence ou une session d’égal à égal.</span><span class="sxs-lookup"><span data-stu-id="d4912-p102">The Conference table is a supporting table. Each record represents one conference or peer-to-peer session.</span></span>
  
|<span data-ttu-id="d4912-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="d4912-107">**Column**</span></span>|<span data-ttu-id="d4912-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="d4912-108">**Data Type**</span></span>|<span data-ttu-id="d4912-109">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="d4912-109">**Key/Index**</span></span>|<span data-ttu-id="d4912-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="d4912-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d4912-111">**ConferenceKey**</span><span class="sxs-lookup"><span data-stu-id="d4912-111">**ConferenceKey**</span></span> <br/> |<span data-ttu-id="d4912-112">int</span><span class="sxs-lookup"><span data-stu-id="d4912-112">int</span></span>  <br/> |<span data-ttu-id="d4912-113">Primaire</span><span class="sxs-lookup"><span data-stu-id="d4912-113">Primary</span></span>  <br/> |<span data-ttu-id="d4912-114">Numéro unique d’identification de cet enregistrement de conférence.</span><span class="sxs-lookup"><span data-stu-id="d4912-114">Unique number identifying this conference record.</span></span>  <br/> |
|<span data-ttu-id="d4912-115">**ConfURI**</span><span class="sxs-lookup"><span data-stu-id="d4912-115">**ConfURI**</span></span> <br/> |<span data-ttu-id="d4912-116">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="d4912-116">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="d4912-117">unique</span><span class="sxs-lookup"><span data-stu-id="d4912-117">unique</span></span>  <br/> |<span data-ttu-id="d4912-118">URI de conférence s’il s’agit d’une conférence, ou DialogID s’il s’agit d’une session d’égal à égal.</span><span class="sxs-lookup"><span data-stu-id="d4912-118">Conference URI if this is a conference, or DialogID if this is a peer-to-peer session.</span></span>  <br/> |
|<span data-ttu-id="d4912-119">**Somme de contrôle**</span><span class="sxs-lookup"><span data-stu-id="d4912-119">**Checksum**</span></span> <br/> |<span data-ttu-id="d4912-120">int</span><span class="sxs-lookup"><span data-stu-id="d4912-120">int</span></span>  <br/> |<span data-ttu-id="d4912-121">Index</span><span class="sxs-lookup"><span data-stu-id="d4912-121">index</span></span>  <br/> |<span data-ttu-id="d4912-p103">Checksum de l’URI de la conférence. À usage interne.</span><span class="sxs-lookup"><span data-stu-id="d4912-p103">Checksum of the conference URI. This is used internally.</span></span>  <br/> |
|<span data-ttu-id="d4912-124">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="d4912-124">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="d4912-125">DateHeure</span><span class="sxs-lookup"><span data-stu-id="d4912-125">datetime</span></span>  <br/> ||<span data-ttu-id="d4912-126">À usage interne uniquement.</span><span class="sxs-lookup"><span data-stu-id="d4912-126">For internal use only.</span></span>  <br/> |
   

