---
title: Table Dialog
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d93424f-9072-43f5-83c2-3d539e3e9ca6
description: La boîte de dialogue est une table de prise en charge ; chaque enregistrement représente une boîte de dialogue protocole SIP (Session Initiation).
ms.openlocfilehash: 36ab76d147673ca85371ca4cdfb151fa953e29b2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33920088"
---
# <a name="dialog-table"></a><span data-ttu-id="e5ac6-103">Table Dialog</span><span class="sxs-lookup"><span data-stu-id="e5ac6-103">Dialog table</span></span>
 
<span data-ttu-id="e5ac6-104">La boîte de dialogue est une table de prise en charge ; chaque enregistrement représente une boîte de dialogue protocole SIP (Session Initiation).</span><span class="sxs-lookup"><span data-stu-id="e5ac6-104">The Dialog table is a supporting table; each record represents one Session Initiation Protocol (SIP) dialog.</span></span>
  
|<span data-ttu-id="e5ac6-105">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="e5ac6-105">**Column**</span></span>|<span data-ttu-id="e5ac6-106">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="e5ac6-106">**Data Type**</span></span>|<span data-ttu-id="e5ac6-107">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="e5ac6-107">**Key/Index**</span></span>|<span data-ttu-id="e5ac6-108">**Détails**</span><span class="sxs-lookup"><span data-stu-id="e5ac6-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e5ac6-109">**Paramètre ConferenceDateTime**</span><span class="sxs-lookup"><span data-stu-id="e5ac6-109">**ConferenceDateTime**</span></span> <br/> |<span data-ttu-id="e5ac6-110">DateHeure</span><span class="sxs-lookup"><span data-stu-id="e5ac6-110">datetime</span></span>  <br/> |<span data-ttu-id="e5ac6-111">Principal</span><span class="sxs-lookup"><span data-stu-id="e5ac6-111">Primary</span></span>  <br/> |<span data-ttu-id="e5ac6-112">Temps lorsque l’agent de la qualité d’Excellence (QoE) reçoit le premier rapport de l’appelant ou appelé.</span><span class="sxs-lookup"><span data-stu-id="e5ac6-112">Time when the Quality of Excellence (QoE) agent receives the first report from either caller or callee.</span></span> <span data-ttu-id="e5ac6-113">Utilisé conjointement avec SessionSeq pour identifier de manière unique une session.</span><span class="sxs-lookup"><span data-stu-id="e5ac6-113">Used in conjunction with SessionSeq to uniquely identify a session.</span></span>  <br/> |
|<span data-ttu-id="e5ac6-114">**SessionSeq**</span><span class="sxs-lookup"><span data-stu-id="e5ac6-114">**SessionSeq**</span></span> <br/> |<span data-ttu-id="e5ac6-115">int</span><span class="sxs-lookup"><span data-stu-id="e5ac6-115">int</span></span>  <br/> |<span data-ttu-id="e5ac6-116">Principal</span><span class="sxs-lookup"><span data-stu-id="e5ac6-116">Primary</span></span>  <br/> |<span data-ttu-id="e5ac6-117">Numéro de séquence pour différencier les sessions lorsqu’elles ont le même paramètre ConferenceDateTime.</span><span class="sxs-lookup"><span data-stu-id="e5ac6-117">Sequence number to differentiate sessions when they have the same ConferenceDateTime.</span></span>  <br/> |
|<span data-ttu-id="e5ac6-118">**DialogID**</span><span class="sxs-lookup"><span data-stu-id="e5ac6-118">**DialogID**</span></span> <br/> |<span data-ttu-id="e5ac6-119">varchar(256)</span><span class="sxs-lookup"><span data-stu-id="e5ac6-119">varchar(256)</span></span>  <br/> ||<span data-ttu-id="e5ac6-120">ID du dialogue qui est globalement unique.</span><span class="sxs-lookup"><span data-stu-id="e5ac6-120">Dialog ID which is globally unique.</span></span>  <br/> |
|<span data-ttu-id="e5ac6-121">**DialogIDChecksum**</span><span class="sxs-lookup"><span data-stu-id="e5ac6-121">**DialogIDChecksum**</span></span> <br/> |<span data-ttu-id="e5ac6-122">int</span><span class="sxs-lookup"><span data-stu-id="e5ac6-122">int</span></span>  <br/> |<span data-ttu-id="e5ac6-123">index</span><span class="sxs-lookup"><span data-stu-id="e5ac6-123">index</span></span>  <br/> |<span data-ttu-id="e5ac6-124">Somme de contrôle de l’ID de la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="e5ac6-124">Checksum of the Dialog ID.</span></span>  <br/> |
   

