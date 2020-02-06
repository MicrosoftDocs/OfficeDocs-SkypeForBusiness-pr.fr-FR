---
title: tblComplianceState
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
ms.assetid: ea82e56c-3cca-4d89-b4e6-6bcaeb1f2830
description: tblComplianceState contient des informations sur l’état de compatibilité à l’échelle du pool.
ms.openlocfilehash: 6f3a7b1b7744260d0630a5328021b1752137a797
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814632"
---
# <a name="tblcompliancestate"></a><span data-ttu-id="fc33b-103">tblComplianceState</span><span class="sxs-lookup"><span data-stu-id="fc33b-103">tblComplianceState</span></span>
 
<span data-ttu-id="fc33b-104">tblComplianceState contient des informations sur l’état de compatibilité à l’échelle du pool.</span><span class="sxs-lookup"><span data-stu-id="fc33b-104">tblComplianceState contains pool-wide compliance state information.</span></span>
  
<span data-ttu-id="fc33b-105">**Celles**</span><span class="sxs-lookup"><span data-stu-id="fc33b-105">**Columns**</span></span>

|<span data-ttu-id="fc33b-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="fc33b-106">**Column**</span></span>|<span data-ttu-id="fc33b-107">**Type**</span><span class="sxs-lookup"><span data-stu-id="fc33b-107">**Type**</span></span>|<span data-ttu-id="fc33b-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="fc33b-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="fc33b-109">lastProcessedEntryID</span><span class="sxs-lookup"><span data-stu-id="fc33b-109">lastProcessedEntryID</span></span>  <br/> |<span data-ttu-id="fc33b-110">bigint, pas null</span><span class="sxs-lookup"><span data-stu-id="fc33b-110">bigint, not null</span></span>  <br/> |<span data-ttu-id="fc33b-111">ID de l’événement de conformité traité le plus récent.</span><span class="sxs-lookup"><span data-stu-id="fc33b-111">ID of the latest processed compliance event.</span></span>  <br/> |
|<span data-ttu-id="fc33b-112">activeServerID</span><span class="sxs-lookup"><span data-stu-id="fc33b-112">activeServerID</span></span>  <br/> |<span data-ttu-id="fc33b-113">ent, non null</span><span class="sxs-lookup"><span data-stu-id="fc33b-113">int, not null</span></span>  <br/> |<span data-ttu-id="fc33b-114">ID du serveur de conformité qui détient le verrou exclusif sur la base de données, ou-1 si aucun.</span><span class="sxs-lookup"><span data-stu-id="fc33b-114">ID of the Compliance server holding the exclusive lock on the database, or -1 if none.</span></span>  <br/> |
|<span data-ttu-id="fc33b-115">lockExpirationTime</span><span class="sxs-lookup"><span data-stu-id="fc33b-115">lockExpirationTime</span></span>  <br/> |<span data-ttu-id="fc33b-116">datetime2, pas null</span><span class="sxs-lookup"><span data-stu-id="fc33b-116">datetime2, not null</span></span>  <br/> |<span data-ttu-id="fc33b-117">Durée d’expiration du verrouillage (si activeServerID n’est pas-1).</span><span class="sxs-lookup"><span data-stu-id="fc33b-117">Lock expiration time (if activeServerID is not -1).</span></span>  <br/> |
   

