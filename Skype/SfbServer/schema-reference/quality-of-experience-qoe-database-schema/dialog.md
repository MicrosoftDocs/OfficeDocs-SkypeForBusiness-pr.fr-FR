---
title: Table Dialog
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d93424f-9072-43f5-83c2-3d539e3e9ca6
description: La boîte de dialogue est une table de prise en charge ; chaque enregistrement représente une boîte de dialogue protocole SIP (Session Initiation).
ms.openlocfilehash: 017da65154d12c89aeed63ea59269639d23b2129
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30876626"
---
# <a name="dialog-table"></a><span data-ttu-id="84f73-103">Table Dialog</span><span class="sxs-lookup"><span data-stu-id="84f73-103">Dialog table</span></span>
 
<span data-ttu-id="84f73-104">La boîte de dialogue est une table de prise en charge ; chaque enregistrement représente une boîte de dialogue protocole SIP (Session Initiation).</span><span class="sxs-lookup"><span data-stu-id="84f73-104">The Dialog table is a supporting table; each record represents one Session Initiation Protocol (SIP) dialog.</span></span>
  
|<span data-ttu-id="84f73-105">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="84f73-105">**Column**</span></span>|<span data-ttu-id="84f73-106">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="84f73-106">**Data Type**</span></span>|<span data-ttu-id="84f73-107">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="84f73-107">**Key/Index**</span></span>|<span data-ttu-id="84f73-108">**Détails**</span><span class="sxs-lookup"><span data-stu-id="84f73-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="84f73-109">**Paramètre ConferenceDateTime**</span><span class="sxs-lookup"><span data-stu-id="84f73-109">**ConferenceDateTime**</span></span> <br/> |<span data-ttu-id="84f73-110">DateHeure</span><span class="sxs-lookup"><span data-stu-id="84f73-110">datetime</span></span>  <br/> |<span data-ttu-id="84f73-111">Principal</span><span class="sxs-lookup"><span data-stu-id="84f73-111">Primary</span></span>  <br/> |<span data-ttu-id="84f73-112">Temps lorsque l’agent de la qualité d’Excellence (QoE) reçoit le premier rapport de l’appelant ou appelé.</span><span class="sxs-lookup"><span data-stu-id="84f73-112">Time when the Quality of Excellence (QoE) agent receives the first report from either caller or callee.</span></span> <span data-ttu-id="84f73-113">Utilisé conjointement avec SessionSeq pour identifier de manière unique une session.</span><span class="sxs-lookup"><span data-stu-id="84f73-113">Used in conjunction with SessionSeq to uniquely identify a session.</span></span>  <br/> |
|<span data-ttu-id="84f73-114">**SessionSeq**</span><span class="sxs-lookup"><span data-stu-id="84f73-114">**SessionSeq**</span></span> <br/> |<span data-ttu-id="84f73-115">int</span><span class="sxs-lookup"><span data-stu-id="84f73-115">int</span></span>  <br/> |<span data-ttu-id="84f73-116">Principal</span><span class="sxs-lookup"><span data-stu-id="84f73-116">Primary</span></span>  <br/> |<span data-ttu-id="84f73-117">Numéro de séquence pour différencier les sessions lorsqu’elles ont le même paramètre ConferenceDateTime.</span><span class="sxs-lookup"><span data-stu-id="84f73-117">Sequence number to differentiate sessions when they have the same ConferenceDateTime.</span></span>  <br/> |
|<span data-ttu-id="84f73-118">**DialogID**</span><span class="sxs-lookup"><span data-stu-id="84f73-118">**DialogID**</span></span> <br/> |<span data-ttu-id="84f73-119">varchar(256)</span><span class="sxs-lookup"><span data-stu-id="84f73-119">varchar(256)</span></span>  <br/> ||<span data-ttu-id="84f73-120">ID du dialogue qui est globalement unique.</span><span class="sxs-lookup"><span data-stu-id="84f73-120">Dialog ID which is globally unique.</span></span>  <br/> |
|<span data-ttu-id="84f73-121">**DialogIDChecksum**</span><span class="sxs-lookup"><span data-stu-id="84f73-121">**DialogIDChecksum**</span></span> <br/> |<span data-ttu-id="84f73-122">int</span><span class="sxs-lookup"><span data-stu-id="84f73-122">int</span></span>  <br/> |<span data-ttu-id="84f73-123">index</span><span class="sxs-lookup"><span data-stu-id="84f73-123">index</span></span>  <br/> |<span data-ttu-id="84f73-124">Somme de contrôle de l’ID de la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="84f73-124">Checksum of the Dialog ID.</span></span>  <br/> |
   

