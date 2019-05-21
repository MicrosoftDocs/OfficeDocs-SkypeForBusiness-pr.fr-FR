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
localization_priority: Normal
ms.assetid: ea82e56c-3cca-4d89-b4e6-6bcaeb1f2830
description: tblComplianceState contient des informations sur l’état de compatibilité à l’échelle du pool.
ms.openlocfilehash: 1c5571d7150c3859978f8d217f0264f67ee993d5
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295474"
---
# <a name="tblcompliancestate"></a><span data-ttu-id="e6e1b-103">tblComplianceState</span><span class="sxs-lookup"><span data-stu-id="e6e1b-103">tblComplianceState</span></span>
 
<span data-ttu-id="e6e1b-104">tblComplianceState contient des informations sur l’état de compatibilité à l’échelle du pool.</span><span class="sxs-lookup"><span data-stu-id="e6e1b-104">tblComplianceState contains pool-wide compliance state information.</span></span>
  
<span data-ttu-id="e6e1b-105">**Celles**</span><span class="sxs-lookup"><span data-stu-id="e6e1b-105">**Columns**</span></span>

|<span data-ttu-id="e6e1b-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="e6e1b-106">**Column**</span></span>|<span data-ttu-id="e6e1b-107">**Type**</span><span class="sxs-lookup"><span data-stu-id="e6e1b-107">**Type**</span></span>|<span data-ttu-id="e6e1b-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="e6e1b-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e6e1b-109">lastProcessedEntryID</span><span class="sxs-lookup"><span data-stu-id="e6e1b-109">lastProcessedEntryID</span></span>  <br/> |<span data-ttu-id="e6e1b-110">bigint, pas null</span><span class="sxs-lookup"><span data-stu-id="e6e1b-110">bigint, not null</span></span>  <br/> |<span data-ttu-id="e6e1b-111">ID de l’événement de conformité traité le plus récent.</span><span class="sxs-lookup"><span data-stu-id="e6e1b-111">ID of the latest processed compliance event.</span></span>  <br/> |
|<span data-ttu-id="e6e1b-112">activeServerID</span><span class="sxs-lookup"><span data-stu-id="e6e1b-112">activeServerID</span></span>  <br/> |<span data-ttu-id="e6e1b-113">ent, non null</span><span class="sxs-lookup"><span data-stu-id="e6e1b-113">int, not null</span></span>  <br/> |<span data-ttu-id="e6e1b-114">ID du serveur de conformité qui détient le verrou exclusif sur la base de données, ou-1 si aucun.</span><span class="sxs-lookup"><span data-stu-id="e6e1b-114">ID of the Compliance server holding the exclusive lock on the database, or -1 if none.</span></span>  <br/> |
|<span data-ttu-id="e6e1b-115">lockExpirationTime</span><span class="sxs-lookup"><span data-stu-id="e6e1b-115">lockExpirationTime</span></span>  <br/> |<span data-ttu-id="e6e1b-116">datetime2, pas null</span><span class="sxs-lookup"><span data-stu-id="e6e1b-116">datetime2, not null</span></span>  <br/> |<span data-ttu-id="e6e1b-117">Durée d’expiration du verrouillage (si activeServerID n’est pas-1).</span><span class="sxs-lookup"><span data-stu-id="e6e1b-117">Lock expiration time (if activeServerID is not -1).</span></span>  <br/> |
   

