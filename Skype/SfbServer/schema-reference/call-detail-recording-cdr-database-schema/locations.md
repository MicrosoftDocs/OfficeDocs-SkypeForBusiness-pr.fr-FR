---
title: Tableau des emplacements dans Skype pour Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 78dc1b14-5394-4f8e-89d3-4ba593272a04
description: Chaque enregistrement représente une référence d’emplacement dans un appel d’urgence, comme un appel E9-1-1.
ms.openlocfilehash: b15e7f0b7930871b97dc3341a47153965529810e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="locations-table-in-skype-for-business-server-2015"></a><span data-ttu-id="dda5d-103">Tableau des emplacements dans Skype pour Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="dda5d-103">Locations table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="dda5d-104">Chaque enregistrement représente une référence d’emplacement dans un appel d’urgence, comme un appel E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="dda5d-104">Each record represents one location reference in an emergency call, like an E9-1-1 call.</span></span>
  
|<span data-ttu-id="dda5d-105">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="dda5d-105">**Column**</span></span>|<span data-ttu-id="dda5d-106">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="dda5d-106">**Data Type**</span></span>|<span data-ttu-id="dda5d-107">**Index de la clé**</span><span class="sxs-lookup"><span data-stu-id="dda5d-107">**Key/Index**</span></span>|<span data-ttu-id="dda5d-108">**Détails**</span><span class="sxs-lookup"><span data-stu-id="dda5d-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="dda5d-109">**SessionIdTime**</span><span class="sxs-lookup"><span data-stu-id="dda5d-109">**SessionIdTime**</span></span> <br/> |<span data-ttu-id="dda5d-110">DateHeure</span><span class="sxs-lookup"><span data-stu-id="dda5d-110">datetime</span></span>  <br/> |<span data-ttu-id="dda5d-111">Primaires et étrangères</span><span class="sxs-lookup"><span data-stu-id="dda5d-111">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="dda5d-112">Heure de la demande de la session.</span><span class="sxs-lookup"><span data-stu-id="dda5d-112">Time of session request.</span></span> <span data-ttu-id="dda5d-113">Utilisé en association avec **SessionIdSeq** pour identifier de manière unique une session.</span><span class="sxs-lookup"><span data-stu-id="dda5d-113">Used in conjunction with **SessionIdSeq** to uniquely identify a session.</span></span> <span data-ttu-id="dda5d-114">Consultez le [tableau dans Skype pour Business Server 2015 des boîtes de dialogue](dialogs.md) pour plus d’informations.</span><span class="sxs-lookup"><span data-stu-id="dda5d-114">See the [Dialogs table in Skype for Business Server 2015](dialogs.md) for more information.</span></span> <br/> |
|<span data-ttu-id="dda5d-115">**SessionIdSeq**</span><span class="sxs-lookup"><span data-stu-id="dda5d-115">**SessionIdSeq**</span></span> <br/> |<span data-ttu-id="dda5d-116">int</span><span class="sxs-lookup"><span data-stu-id="dda5d-116">int</span></span>  <br/> |<span data-ttu-id="dda5d-117">Primaires et étrangères</span><span class="sxs-lookup"><span data-stu-id="dda5d-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="dda5d-118">Numéro d’ID pour identifier la session.</span><span class="sxs-lookup"><span data-stu-id="dda5d-118">ID number to identify the session.</span></span> <span data-ttu-id="dda5d-119">Utilisé en association avec **SessionIdTime** pour identifier de manière unique une session.</span><span class="sxs-lookup"><span data-stu-id="dda5d-119">Used in conjunction with **SessionIdTime** to uniquely identify a session.</span></span> <span data-ttu-id="dda5d-120">Consultez le [tableau dans Skype pour Business Server 2015 des boîtes de dialogue](dialogs.md) pour plus d’informations.</span><span class="sxs-lookup"><span data-stu-id="dda5d-120">See the [Dialogs table in Skype for Business Server 2015](dialogs.md) for more information.</span></span> <br/> |
|<span data-ttu-id="dda5d-121">**Emplacement**</span><span class="sxs-lookup"><span data-stu-id="dda5d-121">**Location**</span></span> <br/> |<span data-ttu-id="dda5d-122">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="dda5d-122">nvarchar(max)</span></span>  <br/> ||<span data-ttu-id="dda5d-123">Emplacement d’appel d’urgence.</span><span class="sxs-lookup"><span data-stu-id="dda5d-123">Location of emergency call.</span></span>  <br/> |
   

