---
title: Table Dialog
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d93424f-9072-43f5-83c2-3d539e3e9ca6
description: La boîte de dialogue est une table de prise en charge ; chaque enregistrement représente une boîte de dialogue Session Initiation Protocol (SIP).
ms.openlocfilehash: 0380f9c7c48ff7d3b26b9ea5442fb5ac2155f785
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="dialog-table"></a><span data-ttu-id="28cd3-103">Table Dialog</span><span class="sxs-lookup"><span data-stu-id="28cd3-103">Dialog table</span></span>
 
<span data-ttu-id="28cd3-104">La boîte de dialogue est une table de prise en charge ; chaque enregistrement représente une boîte de dialogue Session Initiation Protocol (SIP).</span><span class="sxs-lookup"><span data-stu-id="28cd3-104">The Dialog table is a supporting table; each record represents one Session Initiation Protocol (SIP) dialog.</span></span>
  
|<span data-ttu-id="28cd3-105">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="28cd3-105">**Column**</span></span>|<span data-ttu-id="28cd3-106">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="28cd3-106">**Data Type**</span></span>|<span data-ttu-id="28cd3-107">**Index de la clé**</span><span class="sxs-lookup"><span data-stu-id="28cd3-107">**Key/Index**</span></span>|<span data-ttu-id="28cd3-108">**Détails**</span><span class="sxs-lookup"><span data-stu-id="28cd3-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="28cd3-109">**ConferenceDateTime**</span><span class="sxs-lookup"><span data-stu-id="28cd3-109">**ConferenceDateTime**</span></span> <br/> |<span data-ttu-id="28cd3-110">DateHeure</span><span class="sxs-lookup"><span data-stu-id="28cd3-110">datetime</span></span>  <br/> |<span data-ttu-id="28cd3-111">Principal</span><span class="sxs-lookup"><span data-stu-id="28cd3-111">Primary</span></span>  <br/> |<span data-ttu-id="28cd3-112">Heure lorsque l’agent de la qualité d’Excellence (QoE) reçoit le premier rapport de l’appelant ou appelé.</span><span class="sxs-lookup"><span data-stu-id="28cd3-112">Time when the Quality of Excellence (QoE) agent receives the first report from either caller or callee.</span></span> <span data-ttu-id="28cd3-113">Utilisé en association avec SessionSeq pour identifier de manière unique une session.</span><span class="sxs-lookup"><span data-stu-id="28cd3-113">Used in conjunction with SessionSeq to uniquely identify a session.</span></span>  <br/> |
|<span data-ttu-id="28cd3-114">**SessionSeq**</span><span class="sxs-lookup"><span data-stu-id="28cd3-114">**SessionSeq**</span></span> <br/> |<span data-ttu-id="28cd3-115">int</span><span class="sxs-lookup"><span data-stu-id="28cd3-115">int</span></span>  <br/> |<span data-ttu-id="28cd3-116">Principal</span><span class="sxs-lookup"><span data-stu-id="28cd3-116">Primary</span></span>  <br/> |<span data-ttu-id="28cd3-117">Numéro de séquence pour différencier les sessions lorsqu’ils ont le même ConferenceDateTime.</span><span class="sxs-lookup"><span data-stu-id="28cd3-117">Sequence number to differentiate sessions when they have the same ConferenceDateTime.</span></span>  <br/> |
|<span data-ttu-id="28cd3-118">**DialogID**</span><span class="sxs-lookup"><span data-stu-id="28cd3-118">**DialogID**</span></span> <br/> |<span data-ttu-id="28cd3-119">varchar(256)</span><span class="sxs-lookup"><span data-stu-id="28cd3-119">varchar(256)</span></span>  <br/> ||<span data-ttu-id="28cd3-120">ID de boîte de dialogue qui est globalement unique.</span><span class="sxs-lookup"><span data-stu-id="28cd3-120">Dialog ID which is globally unique.</span></span>  <br/> |
|<span data-ttu-id="28cd3-121">**DialogIDChecksum**</span><span class="sxs-lookup"><span data-stu-id="28cd3-121">**DialogIDChecksum**</span></span> <br/> |<span data-ttu-id="28cd3-122">int</span><span class="sxs-lookup"><span data-stu-id="28cd3-122">int</span></span>  <br/> |<span data-ttu-id="28cd3-123">index</span><span class="sxs-lookup"><span data-stu-id="28cd3-123">index</span></span>  <br/> |<span data-ttu-id="28cd3-124">Total de contrôle de l’ID de boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="28cd3-124">Checksum of the Dialog ID.</span></span>  <br/> |
   

