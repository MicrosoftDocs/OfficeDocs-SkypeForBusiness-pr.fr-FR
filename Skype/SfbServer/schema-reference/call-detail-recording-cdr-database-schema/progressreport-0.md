---
title: Affichage ProgressReport
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
ms.assetid: b49f3fc7-0e2f-498f-8505-aaaf54e435f9
description: L’affichage ProgressReport stocke les informations relatives aux sessions terminées. Les rapports d’avancement sont créés uniquement pour les appels et les sessions que Lync Server 2013 considère comme utiles à des fins de diagnostic. Cette vue a été introduite dans Microsoft Lync Server 2013.
ms.openlocfilehash: 6cc8295e73463fff9d4913efbf9d4844f9316149
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823184"
---
# <a name="progressreport-view"></a><span data-ttu-id="1d961-105">Affichage ProgressReport</span><span class="sxs-lookup"><span data-stu-id="1d961-105">ProgressReport view</span></span>
 
<span data-ttu-id="1d961-106">L’affichage ProgressReport stocke les informations relatives aux sessions terminées.</span><span class="sxs-lookup"><span data-stu-id="1d961-106">The ProgressReport view stores information about completed sessions.</span></span> <span data-ttu-id="1d961-107">Les rapports d’avancement sont créés uniquement pour les appels et les sessions que Lync Server 2013 considère comme utiles à des fins de diagnostic.</span><span class="sxs-lookup"><span data-stu-id="1d961-107">Progress reports will be written only for calls and sessions that Lync Server 2013 determines might be useful for diagnostic purposes.</span></span> <span data-ttu-id="1d961-108">Cette vue a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1d961-108">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1d961-109">Les champs ErrorTime, ErrorReportSeq et ProgressReportSeq ne font pas nécessairement référence à des erreurs, mais à des messages qui indiquent l’état des appels ou des messages.</span><span class="sxs-lookup"><span data-stu-id="1d961-109">The ErrorTime, ErrorReportSeq and ProgressReportSeq fields don't necessarily refer to errors but to messages that indicate the status of calls or messages.</span></span> 
  
|<span data-ttu-id="1d961-110">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="1d961-110">**Column**</span></span>|<span data-ttu-id="1d961-111">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="1d961-111">**Data Type**</span></span>|<span data-ttu-id="1d961-112">**Détails**</span><span class="sxs-lookup"><span data-stu-id="1d961-112">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1d961-113">**ErrorTime**</span><span class="sxs-lookup"><span data-stu-id="1d961-113">**ErrorTime**</span></span> <br/> |<span data-ttu-id="1d961-114">DateHeure</span><span class="sxs-lookup"><span data-stu-id="1d961-114">datetime</span></span>  <br/> |<span data-ttu-id="1d961-p103">Heure à laquelle l’erreur s’est produite. Utilisé conjointement à ErrorReportSeq pour identifier une erreur de manière unique.</span><span class="sxs-lookup"><span data-stu-id="1d961-p103">Time of error occurred. Used in conjunction with ErrorReportSeq to uniquely identify an error.</span></span>  <br/> |
|<span data-ttu-id="1d961-117">**ErrorReportSeq**</span><span class="sxs-lookup"><span data-stu-id="1d961-117">**ErrorReportSeq**</span></span> <br/> |<span data-ttu-id="1d961-118">int</span><span class="sxs-lookup"><span data-stu-id="1d961-118">int</span></span>  <br/> |<span data-ttu-id="1d961-p104">Numéro d’identification de l’erreur. Utilisé conjointement avec ErrorTime pour identifier de manière unique une erreur.</span><span class="sxs-lookup"><span data-stu-id="1d961-p104">ID number to identify the error. Used in conjunction with ErrorTime to uniquely identify an error.</span></span>  <br/> |
|<span data-ttu-id="1d961-121">**ProgressReportSeq**</span><span class="sxs-lookup"><span data-stu-id="1d961-121">**ProgressReportSeq**</span></span> <br/> |<span data-ttu-id="1d961-122">int</span><span class="sxs-lookup"><span data-stu-id="1d961-122">int</span></span>  <br/> |<span data-ttu-id="1d961-123">ID utilisé pour identifier le rapport d’avancement.</span><span class="sxs-lookup"><span data-stu-id="1d961-123">ID to identify the progress report.</span></span> <span data-ttu-id="1d961-124">Utilisé pour distinguer des rapports d’avancement du même rapport d’erreurs.</span><span class="sxs-lookup"><span data-stu-id="1d961-124">Used to distinguish progress reports of the same error report.</span></span>  <br/> |
|<span data-ttu-id="1d961-125">**MsDiagId**</span><span class="sxs-lookup"><span data-stu-id="1d961-125">**MsDiagId**</span></span> <br/> |<span data-ttu-id="1d961-126">int</span><span class="sxs-lookup"><span data-stu-id="1d961-126">int</span></span>  <br/> |<span data-ttu-id="1d961-127">ID de diagnostic pour le rapport d’erreurs.</span><span class="sxs-lookup"><span data-stu-id="1d961-127">Diagnostic ID for the error report.</span></span>  <br/> |
|<span data-ttu-id="1d961-128">**Source**</span><span class="sxs-lookup"><span data-stu-id="1d961-128">**Source**</span></span> <br/> |<span data-ttu-id="1d961-129">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="1d961-129">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="1d961-130">Nom du serveur à l’origine de l’erreur (si le rapport a été envoyé à partir d’un composant serveur).</span><span class="sxs-lookup"><span data-stu-id="1d961-130">Name of server that originated the error (if report was sent from a server component).</span></span>  <br/> |
|<span data-ttu-id="1d961-131">**Application**</span><span class="sxs-lookup"><span data-stu-id="1d961-131">**Application**</span></span> <br/> |<span data-ttu-id="1d961-132">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="1d961-132">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="1d961-133">Nom de l’application à l’origine de l’erreur (si le rapport a été envoyé à partir d’un composant serveur).</span><span class="sxs-lookup"><span data-stu-id="1d961-133">Name of application that originated the error (if report was sent from a server component).</span></span>  <br/> |
|<span data-ttu-id="1d961-134">**TelemetryId**</span><span class="sxs-lookup"><span data-stu-id="1d961-134">**TelemetryId**</span></span> <br/> |<span data-ttu-id="1d961-135">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="1d961-135">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="1d961-136">Identificateur unique corrélant les informations d’heure de participation pour les différents composants impliqués dans une conférence.</span><span class="sxs-lookup"><span data-stu-id="1d961-136">Unique identifier correlating join time information for the different components involved in a conference.</span></span>  <br/> |
|<span data-ttu-id="1d961-137">**SessionSetupTime**</span><span class="sxs-lookup"><span data-stu-id="1d961-137">**SessionSetupTime**</span></span> <br/> |<span data-ttu-id="1d961-138">int</span><span class="sxs-lookup"><span data-stu-id="1d961-138">int</span></span>  <br/> |<span data-ttu-id="1d961-139">Durée (en millisecondes) requise pour qu’un composant spécifique rejoigne une conférence.</span><span class="sxs-lookup"><span data-stu-id="1d961-139">Time (in milliseconds) required for a specific component to join a conference.</span></span>  <br/> |
|<span data-ttu-id="1d961-140">**MsDiagHeader**</span><span class="sxs-lookup"><span data-stu-id="1d961-140">**MsDiagHeader**</span></span> <br/> |<span data-ttu-id="1d961-141">varchar(max)</span><span class="sxs-lookup"><span data-stu-id="1d961-141">varchar(max)</span></span>  <br/> |<span data-ttu-id="1d961-142">Informations supplémentaires sur l’erreur.</span><span class="sxs-lookup"><span data-stu-id="1d961-142">Additional error information.</span></span>  <br/> |
   

