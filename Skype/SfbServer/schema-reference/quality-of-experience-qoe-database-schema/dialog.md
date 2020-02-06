---
title: Table Dialog
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 4d93424f-9072-43f5-83c2-3d539e3e9ca6
description: Le tableau de boîte de dialogue est une table de prise en charge. chaque enregistrement représente une boîte de dialogue SIP (Session Initiation Protocol).
ms.openlocfilehash: 85d4a9f16a88db386565c065161eedeb61fba913
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41809532"
---
# <a name="dialog-table"></a><span data-ttu-id="de9ab-103">Table Dialog</span><span class="sxs-lookup"><span data-stu-id="de9ab-103">Dialog table</span></span>
 
<span data-ttu-id="de9ab-104">Le tableau de boîte de dialogue est une table de prise en charge. chaque enregistrement représente une boîte de dialogue SIP (Session Initiation Protocol).</span><span class="sxs-lookup"><span data-stu-id="de9ab-104">The Dialog table is a supporting table; each record represents one Session Initiation Protocol (SIP) dialog.</span></span>
  
|<span data-ttu-id="de9ab-105">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="de9ab-105">**Column**</span></span>|<span data-ttu-id="de9ab-106">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="de9ab-106">**Data Type**</span></span>|<span data-ttu-id="de9ab-107">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="de9ab-107">**Key/Index**</span></span>|<span data-ttu-id="de9ab-108">**Détails**</span><span class="sxs-lookup"><span data-stu-id="de9ab-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="de9ab-109">**ConferenceDateTime**</span><span class="sxs-lookup"><span data-stu-id="de9ab-109">**ConferenceDateTime**</span></span> <br/> |<span data-ttu-id="de9ab-110">DateHeure</span><span class="sxs-lookup"><span data-stu-id="de9ab-110">datetime</span></span>  <br/> |<span data-ttu-id="de9ab-111">Principal</span><span class="sxs-lookup"><span data-stu-id="de9ab-111">Primary</span></span>  <br/> |<span data-ttu-id="de9ab-112">Temps pendant lequel l’agent de qualité d’excellence reçoit le premier rapport de l’appelant ou du destinataire.</span><span class="sxs-lookup"><span data-stu-id="de9ab-112">Time when the Quality of Excellence (QoE) agent receives the first report from either caller or callee.</span></span> <span data-ttu-id="de9ab-113">Utilisé conjointement avec SessionSeq pour identifier une session de manière unique.</span><span class="sxs-lookup"><span data-stu-id="de9ab-113">Used in conjunction with SessionSeq to uniquely identify a session.</span></span>  <br/> |
|<span data-ttu-id="de9ab-114">**SessionSeq**</span><span class="sxs-lookup"><span data-stu-id="de9ab-114">**SessionSeq**</span></span> <br/> |<span data-ttu-id="de9ab-115">int</span><span class="sxs-lookup"><span data-stu-id="de9ab-115">int</span></span>  <br/> |<span data-ttu-id="de9ab-116">Principal</span><span class="sxs-lookup"><span data-stu-id="de9ab-116">Primary</span></span>  <br/> |<span data-ttu-id="de9ab-117">Numéro séquentiel pour différencier les sessions lorsqu’elles ont la même ConferenceDateTime.</span><span class="sxs-lookup"><span data-stu-id="de9ab-117">Sequence number to differentiate sessions when they have the same ConferenceDateTime.</span></span>  <br/> |
|<span data-ttu-id="de9ab-118">**DialogID**</span><span class="sxs-lookup"><span data-stu-id="de9ab-118">**DialogID**</span></span> <br/> |<span data-ttu-id="de9ab-119">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="de9ab-119">varchar(256)</span></span>  <br/> ||<span data-ttu-id="de9ab-120">ID de boîte de dialogue globalement unique.</span><span class="sxs-lookup"><span data-stu-id="de9ab-120">Dialog ID which is globally unique.</span></span>  <br/> |
|<span data-ttu-id="de9ab-121">**DialogIDChecksum**</span><span class="sxs-lookup"><span data-stu-id="de9ab-121">**DialogIDChecksum**</span></span> <br/> |<span data-ttu-id="de9ab-122">int</span><span class="sxs-lookup"><span data-stu-id="de9ab-122">int</span></span>  <br/> |<span data-ttu-id="de9ab-123">index</span><span class="sxs-lookup"><span data-stu-id="de9ab-123">index</span></span>  <br/> |<span data-ttu-id="de9ab-124">Checksum de l’ID de boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="de9ab-124">Checksum of the Dialog ID.</span></span>  <br/> |
   

