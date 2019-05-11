---
title: Table Conference
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2a2c327c-4719-42dc-a3bb-6dbc0864d9af
description: La table de conférence est une table de prise en charge. Chaque enregistrement représente une conférence ou une session d’égal à égal.
ms.openlocfilehash: 0914e98aed4aea16e5301ccae454e925663454a5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33920165"
---
# <a name="conference-table"></a><span data-ttu-id="17abf-104">Table Conference</span><span class="sxs-lookup"><span data-stu-id="17abf-104">Conference table</span></span>
 
<span data-ttu-id="17abf-105">La table de conférence est une table de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="17abf-105">The Conference table is a supporting table.</span></span> <span data-ttu-id="17abf-106">Chaque enregistrement représente une conférence ou une session d’égal à égal.</span><span class="sxs-lookup"><span data-stu-id="17abf-106">Each record represents one conference or peer-to-peer session.</span></span>
  
|<span data-ttu-id="17abf-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="17abf-107">**Column**</span></span>|<span data-ttu-id="17abf-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="17abf-108">**Data Type**</span></span>|<span data-ttu-id="17abf-109">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="17abf-109">**Key/Index**</span></span>|<span data-ttu-id="17abf-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="17abf-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="17abf-111">**ConferenceKey**</span><span class="sxs-lookup"><span data-stu-id="17abf-111">**ConferenceKey**</span></span> <br/> |<span data-ttu-id="17abf-112">int</span><span class="sxs-lookup"><span data-stu-id="17abf-112">int</span></span>  <br/> |<span data-ttu-id="17abf-113">Principal</span><span class="sxs-lookup"><span data-stu-id="17abf-113">Primary</span></span>  <br/> |<span data-ttu-id="17abf-114">Numéro unique identifiant cet enregistrement de conférence.</span><span class="sxs-lookup"><span data-stu-id="17abf-114">Unique number identifying this conference record.</span></span>  <br/> |
|<span data-ttu-id="17abf-115">**ConfURI**</span><span class="sxs-lookup"><span data-stu-id="17abf-115">**ConfURI**</span></span> <br/> |<span data-ttu-id="17abf-116">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="17abf-116">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="17abf-117">unique</span><span class="sxs-lookup"><span data-stu-id="17abf-117">unique</span></span>  <br/> |<span data-ttu-id="17abf-118">Conférence URI s’il s’agit une conférence, ou DialogID s’il est une session d’égal à égal.</span><span class="sxs-lookup"><span data-stu-id="17abf-118">Conference URI if this is a conference, or DialogID if this is a peer-to-peer session.</span></span>  <br/> |
|<span data-ttu-id="17abf-119">**Somme de contrôle**</span><span class="sxs-lookup"><span data-stu-id="17abf-119">**Checksum**</span></span> <br/> |<span data-ttu-id="17abf-120">int</span><span class="sxs-lookup"><span data-stu-id="17abf-120">int</span></span>  <br/> |<span data-ttu-id="17abf-121">index</span><span class="sxs-lookup"><span data-stu-id="17abf-121">index</span></span>  <br/> |<span data-ttu-id="17abf-122">Somme de contrôle de l’URI de conférence.</span><span class="sxs-lookup"><span data-stu-id="17abf-122">Checksum of the conference URI.</span></span> <span data-ttu-id="17abf-123">Il est utilisé en interne.</span><span class="sxs-lookup"><span data-stu-id="17abf-123">This is used internally.</span></span>  <br/> |
|<span data-ttu-id="17abf-124">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="17abf-124">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="17abf-125">DateHeure</span><span class="sxs-lookup"><span data-stu-id="17abf-125">datetime</span></span>  <br/> ||<span data-ttu-id="17abf-126">À usage interne uniquement.</span><span class="sxs-lookup"><span data-stu-id="17abf-126">For internal use only.</span></span>  <br/> |
   

