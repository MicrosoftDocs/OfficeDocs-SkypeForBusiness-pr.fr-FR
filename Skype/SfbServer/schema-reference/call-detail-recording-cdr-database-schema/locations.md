---
title: Tableau emplacements dans Skype entreprise Server 2015
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
ms.assetid: 78dc1b14-5394-4f8e-89d3-4ba593272a04
description: Chaque enregistrement représente une référence d’emplacement dans un appel d’urgence, par exemple un appel E9-1-1.
ms.openlocfilehash: a1dd7dfdf84ef196b24fa97b1b24950c326b0241
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815112"
---
# <a name="locations-table-in-skype-for-business-server-2015"></a><span data-ttu-id="f9b58-103">Tableau emplacements dans Skype entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="f9b58-103">Locations table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="f9b58-104">Chaque enregistrement représente une référence d’emplacement dans un appel d’urgence, par exemple un appel E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="f9b58-104">Each record represents one location reference in an emergency call, like an E9-1-1 call.</span></span>
  
|<span data-ttu-id="f9b58-105">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="f9b58-105">**Column**</span></span>|<span data-ttu-id="f9b58-106">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="f9b58-106">**Data Type**</span></span>|<span data-ttu-id="f9b58-107">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="f9b58-107">**Key/Index**</span></span>|<span data-ttu-id="f9b58-108">**Détails**</span><span class="sxs-lookup"><span data-stu-id="f9b58-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="f9b58-109">**SessionIdTime**</span><span class="sxs-lookup"><span data-stu-id="f9b58-109">**SessionIdTime**</span></span> <br/> |<span data-ttu-id="f9b58-110">DateHeure</span><span class="sxs-lookup"><span data-stu-id="f9b58-110">datetime</span></span>  <br/> |<span data-ttu-id="f9b58-111">Etranger principal</span><span class="sxs-lookup"><span data-stu-id="f9b58-111">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="f9b58-112">Durée de la demande de session.</span><span class="sxs-lookup"><span data-stu-id="f9b58-112">Time of session request.</span></span> <span data-ttu-id="f9b58-113">Utilisé conjointement avec **SessionIdSeq** pour identifier une session de manière unique.</span><span class="sxs-lookup"><span data-stu-id="f9b58-113">Used in conjunction with **SessionIdSeq** to uniquely identify a session.</span></span> <span data-ttu-id="f9b58-114">Pour plus d’informations, voir le [tableau des boîtes de dialogue dans Skype entreprise Server 2015](dialogs.md) .</span><span class="sxs-lookup"><span data-stu-id="f9b58-114">See the [Dialogs table in Skype for Business Server 2015](dialogs.md) for more information.</span></span> <br/> |
|<span data-ttu-id="f9b58-115">**SessionIdSeq**</span><span class="sxs-lookup"><span data-stu-id="f9b58-115">**SessionIdSeq**</span></span> <br/> |<span data-ttu-id="f9b58-116">int</span><span class="sxs-lookup"><span data-stu-id="f9b58-116">int</span></span>  <br/> |<span data-ttu-id="f9b58-117">Etranger principal</span><span class="sxs-lookup"><span data-stu-id="f9b58-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="f9b58-118">IDENTIFIant de la session.</span><span class="sxs-lookup"><span data-stu-id="f9b58-118">ID number to identify the session.</span></span> <span data-ttu-id="f9b58-119">Utilisé conjointement avec **SessionIdTime** pour identifier une session de manière unique.</span><span class="sxs-lookup"><span data-stu-id="f9b58-119">Used in conjunction with **SessionIdTime** to uniquely identify a session.</span></span> <span data-ttu-id="f9b58-120">Pour plus d’informations, voir le [tableau des boîtes de dialogue dans Skype entreprise Server 2015](dialogs.md) .</span><span class="sxs-lookup"><span data-stu-id="f9b58-120">See the [Dialogs table in Skype for Business Server 2015](dialogs.md) for more information.</span></span> <br/> |
|<span data-ttu-id="f9b58-121">**Emplacement**</span><span class="sxs-lookup"><span data-stu-id="f9b58-121">**Location**</span></span> <br/> |<span data-ttu-id="f9b58-122">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="f9b58-122">nvarchar(max)</span></span>  <br/> ||<span data-ttu-id="f9b58-123">Emplacement de l’appel d’urgence.</span><span class="sxs-lookup"><span data-stu-id="f9b58-123">Location of emergency call.</span></span>  <br/> |
   

