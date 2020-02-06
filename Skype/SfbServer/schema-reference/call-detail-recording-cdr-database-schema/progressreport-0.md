---
title: Affichage ProgressReport
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
ms.assetid: b49f3fc7-0e2f-498f-8505-aaaf54e435f9
description: L’affichage ProgressReport stocke les informations sur les sessions terminées. Les rapports de progression seront écrits uniquement pour les appels et les sessions que Lync Server 2013 détermine peut être utile à des fins de diagnostic. Cet affichage a été présenté dans Microsoft Lync Server 2013.
ms.openlocfilehash: c07b9db8ebd9f898ab9d8feb5b07c4723209522c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814982"
---
# <a name="progressreport-view"></a><span data-ttu-id="e712e-105">Affichage ProgressReport</span><span class="sxs-lookup"><span data-stu-id="e712e-105">ProgressReport view</span></span>
 
<span data-ttu-id="e712e-106">L’affichage ProgressReport stocke les informations sur les sessions terminées.</span><span class="sxs-lookup"><span data-stu-id="e712e-106">The ProgressReport view stores information about completed sessions.</span></span> <span data-ttu-id="e712e-107">Les rapports de progression seront écrits uniquement pour les appels et les sessions que Lync Server 2013 détermine peut être utile à des fins de diagnostic.</span><span class="sxs-lookup"><span data-stu-id="e712e-107">Progress reports will be written only for calls and sessions that Lync Server 2013 determines might be useful for diagnostic purposes.</span></span> <span data-ttu-id="e712e-108">Cet affichage a été présenté dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e712e-108">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e712e-109">Les champs ErrorTime, ErrorReportSeq et ProgressReportSeq ne font pas nécessairement référence aux erreurs, mais aux messages indiquant l’état des appels ou des messages.</span><span class="sxs-lookup"><span data-stu-id="e712e-109">The ErrorTime, ErrorReportSeq and ProgressReportSeq fields don't necessarily refer to errors but to messages that indicate the status of calls or messages.</span></span> 
  
|<span data-ttu-id="e712e-110">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="e712e-110">**Column**</span></span>|<span data-ttu-id="e712e-111">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="e712e-111">**Data Type**</span></span>|<span data-ttu-id="e712e-112">**Détails**</span><span class="sxs-lookup"><span data-stu-id="e712e-112">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e712e-113">**ErrorTime**</span><span class="sxs-lookup"><span data-stu-id="e712e-113">**ErrorTime**</span></span> <br/> |<span data-ttu-id="e712e-114">DateHeure</span><span class="sxs-lookup"><span data-stu-id="e712e-114">datetime</span></span>  <br/> |<span data-ttu-id="e712e-115">L’heure de l’erreur s’est produite.</span><span class="sxs-lookup"><span data-stu-id="e712e-115">Time of error occurred.</span></span> <span data-ttu-id="e712e-116">Utilisé conjointement avec ErrorReportSeq pour identifier de manière unique une erreur.</span><span class="sxs-lookup"><span data-stu-id="e712e-116">Used in conjunction with ErrorReportSeq to uniquely identify an error.</span></span>  <br/> |
|<span data-ttu-id="e712e-117">**ErrorReportSeq**</span><span class="sxs-lookup"><span data-stu-id="e712e-117">**ErrorReportSeq**</span></span> <br/> |<span data-ttu-id="e712e-118">int</span><span class="sxs-lookup"><span data-stu-id="e712e-118">int</span></span>  <br/> |<span data-ttu-id="e712e-119">Numéro d’identification pour identifier l’erreur.</span><span class="sxs-lookup"><span data-stu-id="e712e-119">ID number to identify the error.</span></span> <span data-ttu-id="e712e-120">Utilisé conjointement avec ErrorTime pour identifier de manière unique une erreur.</span><span class="sxs-lookup"><span data-stu-id="e712e-120">Used in conjunction with ErrorTime to uniquely identify an error.</span></span>  <br/> |
|<span data-ttu-id="e712e-121">**ProgressReportSeq**</span><span class="sxs-lookup"><span data-stu-id="e712e-121">**ProgressReportSeq**</span></span> <br/> |<span data-ttu-id="e712e-122">int</span><span class="sxs-lookup"><span data-stu-id="e712e-122">int</span></span>  <br/> |<span data-ttu-id="e712e-123">ID pour identifier le rapport de progression.</span><span class="sxs-lookup"><span data-stu-id="e712e-123">ID to identify the progress report.</span></span> <span data-ttu-id="e712e-124">Permet de distinguer les rapports de progression d’un même rapport d’erreur.</span><span class="sxs-lookup"><span data-stu-id="e712e-124">Used to distinguish progress reports of the same error report.</span></span>  <br/> |
|<span data-ttu-id="e712e-125">**MsDiagId**</span><span class="sxs-lookup"><span data-stu-id="e712e-125">**MsDiagId**</span></span> <br/> |<span data-ttu-id="e712e-126">int</span><span class="sxs-lookup"><span data-stu-id="e712e-126">int</span></span>  <br/> |<span data-ttu-id="e712e-127">ID de diagnostic du rapport d’erreur.</span><span class="sxs-lookup"><span data-stu-id="e712e-127">Diagnostic ID for the error report.</span></span>  <br/> |
|<span data-ttu-id="e712e-128">**Source**</span><span class="sxs-lookup"><span data-stu-id="e712e-128">**Source**</span></span> <br/> |<span data-ttu-id="e712e-129">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e712e-129">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="e712e-130">Nom du serveur à l’origine de l’erreur (si le rapport a été envoyé à partir d’un composant serveur).</span><span class="sxs-lookup"><span data-stu-id="e712e-130">Name of server that originated the error (if report was sent from a server component).</span></span>  <br/> |
|<span data-ttu-id="e712e-131">**Application**</span><span class="sxs-lookup"><span data-stu-id="e712e-131">**Application**</span></span> <br/> |<span data-ttu-id="e712e-132">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e712e-132">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="e712e-133">Nom de l’application à l’origine de l’erreur (si le rapport a été envoyé à partir d’un composant serveur).</span><span class="sxs-lookup"><span data-stu-id="e712e-133">Name of application that originated the error (if report was sent from a server component).</span></span>  <br/> |
|<span data-ttu-id="e712e-134">**TelemetryId**</span><span class="sxs-lookup"><span data-stu-id="e712e-134">**TelemetryId**</span></span> <br/> |<span data-ttu-id="e712e-135">identificateur</span><span class="sxs-lookup"><span data-stu-id="e712e-135">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="e712e-136">Identifiant unique permettant de corréler les informations de connexion aux différents composants participant à une conférence.</span><span class="sxs-lookup"><span data-stu-id="e712e-136">Unique identifier correlating join time information for the different components involved in a conference.</span></span>  <br/> |
|<span data-ttu-id="e712e-137">**SessionSetupTime**</span><span class="sxs-lookup"><span data-stu-id="e712e-137">**SessionSetupTime**</span></span> <br/> |<span data-ttu-id="e712e-138">int</span><span class="sxs-lookup"><span data-stu-id="e712e-138">int</span></span>  <br/> |<span data-ttu-id="e712e-139">Durée (en millisecondes) requise pour un composant spécifique pour participer à une conférence.</span><span class="sxs-lookup"><span data-stu-id="e712e-139">Time (in milliseconds) required for a specific component to join a conference.</span></span>  <br/> |
|<span data-ttu-id="e712e-140">**MsDiagHeader**</span><span class="sxs-lookup"><span data-stu-id="e712e-140">**MsDiagHeader**</span></span> <br/> |<span data-ttu-id="e712e-141">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="e712e-141">varchar(max)</span></span>  <br/> |<span data-ttu-id="e712e-142">Informations supplémentaires sur l’erreur.</span><span class="sxs-lookup"><span data-stu-id="e712e-142">Additional error information.</span></span>  <br/> |
   

