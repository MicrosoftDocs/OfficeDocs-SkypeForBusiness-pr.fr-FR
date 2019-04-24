---
title: tblComplianceState
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ea82e56c-3cca-4d89-b4e6-6bcaeb1f2830
description: tblComplianceState contient des informations d’état de conformité au niveau du pool.
ms.openlocfilehash: 4e9f103ef019e743b5dfcb4ef554ff6a28c340b8
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212634"
---
# <a name="tblcompliancestate"></a><span data-ttu-id="3f31e-103">tblComplianceState</span><span class="sxs-lookup"><span data-stu-id="3f31e-103">tblComplianceState</span></span>
 
<span data-ttu-id="3f31e-104">tblComplianceState contient des informations d’état de conformité au niveau du pool.</span><span class="sxs-lookup"><span data-stu-id="3f31e-104">tblComplianceState contains pool-wide compliance state information.</span></span>
  
<span data-ttu-id="3f31e-105">**Colonnes**</span><span class="sxs-lookup"><span data-stu-id="3f31e-105">**Columns**</span></span>

|<span data-ttu-id="3f31e-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="3f31e-106">**Column**</span></span>|<span data-ttu-id="3f31e-107">**Type**</span><span class="sxs-lookup"><span data-stu-id="3f31e-107">**Type**</span></span>|<span data-ttu-id="3f31e-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="3f31e-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="3f31e-109">lastProcessedEntryID</span><span class="sxs-lookup"><span data-stu-id="3f31e-109">lastProcessedEntryID</span></span>  <br/> |<span data-ttu-id="3f31e-110">bigint, non null</span><span class="sxs-lookup"><span data-stu-id="3f31e-110">bigint, not null</span></span>  <br/> |<span data-ttu-id="3f31e-111">ID du dernier événement de conformité traité.</span><span class="sxs-lookup"><span data-stu-id="3f31e-111">ID of the latest processed compliance event.</span></span>  <br/> |
|<span data-ttu-id="3f31e-112">activeServerID</span><span class="sxs-lookup"><span data-stu-id="3f31e-112">activeServerID</span></span>  <br/> |<span data-ttu-id="3f31e-113">int, non null</span><span class="sxs-lookup"><span data-stu-id="3f31e-113">int, not null</span></span>  <br/> |<span data-ttu-id="3f31e-114">ID du serveur de conformité qui détient le verrou exclusif sur la base de données, ou -1 si aucun.</span><span class="sxs-lookup"><span data-stu-id="3f31e-114">ID of the Compliance server holding the exclusive lock on the database, or -1 if none.</span></span>  <br/> |
|<span data-ttu-id="3f31e-115">lockExpirationTime</span><span class="sxs-lookup"><span data-stu-id="3f31e-115">lockExpirationTime</span></span>  <br/> |<span data-ttu-id="3f31e-116">dateheure2, non null</span><span class="sxs-lookup"><span data-stu-id="3f31e-116">datetime2, not null</span></span>  <br/> |<span data-ttu-id="3f31e-117">Verrouiller le délai d’expiration (si activeServerID est différent de -1).</span><span class="sxs-lookup"><span data-stu-id="3f31e-117">Lock expiration time (if activeServerID is not -1).</span></span>  <br/> |
   

