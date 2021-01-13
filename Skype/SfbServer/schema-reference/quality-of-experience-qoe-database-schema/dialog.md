---
title: Table de dialogue
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
ms.assetid: 4d93424f-9072-43f5-83c2-3d539e3e9ca6
description: La table Dialog est une table de prise en charge ; chaque enregistrement représente un dialogue SIP (Session Initiation Protocol).
ms.openlocfilehash: 05d9519c9aef20b8c82d904a9d5718a4de8c092c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815844"
---
# <a name="dialog-table"></a><span data-ttu-id="fe958-103">Table de dialogue</span><span class="sxs-lookup"><span data-stu-id="fe958-103">Dialog table</span></span>
 
<span data-ttu-id="fe958-104">La table Dialog est une table de prise en charge ; chaque enregistrement représente un dialogue SIP (Session Initiation Protocol).</span><span class="sxs-lookup"><span data-stu-id="fe958-104">The Dialog table is a supporting table; each record represents one Session Initiation Protocol (SIP) dialog.</span></span>
  
|<span data-ttu-id="fe958-105">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="fe958-105">**Column**</span></span>|<span data-ttu-id="fe958-106">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="fe958-106">**Data Type**</span></span>|<span data-ttu-id="fe958-107">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="fe958-107">**Key/Index**</span></span>|<span data-ttu-id="fe958-108">**Details**</span><span class="sxs-lookup"><span data-stu-id="fe958-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="fe958-109">**ConferenceDateTime**</span><span class="sxs-lookup"><span data-stu-id="fe958-109">**ConferenceDateTime**</span></span> <br/> |<span data-ttu-id="fe958-110">DateHeure</span><span class="sxs-lookup"><span data-stu-id="fe958-110">datetime</span></span>  <br/> |<span data-ttu-id="fe958-111">Primaire</span><span class="sxs-lookup"><span data-stu-id="fe958-111">Primary</span></span>  <br/> |<span data-ttu-id="fe958-p101">Heure à laquelle l’agent QoE (Quality of Excellence) reçoit le premier rapport de l’appelant ou de l’appelé. Utilisé conjointement avec SessionSeq pour identifier une session de manière unique.</span><span class="sxs-lookup"><span data-stu-id="fe958-p101">Time when the Quality of Excellence (QoE) agent receives the first report from either caller or callee. Used in conjunction with SessionSeq to uniquely identify a session.</span></span>  <br/> |
|<span data-ttu-id="fe958-114">**SessionSeq**</span><span class="sxs-lookup"><span data-stu-id="fe958-114">**SessionSeq**</span></span> <br/> |<span data-ttu-id="fe958-115">int</span><span class="sxs-lookup"><span data-stu-id="fe958-115">int</span></span>  <br/> |<span data-ttu-id="fe958-116">Primaire</span><span class="sxs-lookup"><span data-stu-id="fe958-116">Primary</span></span>  <br/> |<span data-ttu-id="fe958-117">Numéro de séquence pour différencier les sessions lorsqu’elles ont le même paramètre ConferenceDateTime.</span><span class="sxs-lookup"><span data-stu-id="fe958-117">Sequence number to differentiate sessions when they have the same ConferenceDateTime.</span></span>  <br/> |
|<span data-ttu-id="fe958-118">**DialogID**</span><span class="sxs-lookup"><span data-stu-id="fe958-118">**DialogID**</span></span> <br/> |<span data-ttu-id="fe958-119">varchar(256)</span><span class="sxs-lookup"><span data-stu-id="fe958-119">varchar(256)</span></span>  <br/> ||<span data-ttu-id="fe958-120">ID du dialogue qui est unique à l’échelle globale.</span><span class="sxs-lookup"><span data-stu-id="fe958-120">Dialog ID which is globally unique.</span></span>  <br/> |
|<span data-ttu-id="fe958-121">**DialogIDChecksum**</span><span class="sxs-lookup"><span data-stu-id="fe958-121">**DialogIDChecksum**</span></span> <br/> |<span data-ttu-id="fe958-122">int</span><span class="sxs-lookup"><span data-stu-id="fe958-122">int</span></span>  <br/> |<span data-ttu-id="fe958-123">Index</span><span class="sxs-lookup"><span data-stu-id="fe958-123">index</span></span>  <br/> |<span data-ttu-id="fe958-124">Somme de contrôle de l’ID du dialogue.</span><span class="sxs-lookup"><span data-stu-id="fe958-124">Checksum of the Dialog ID.</span></span>  <br/> |
   

