---
title: tblComplianceState
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ea82e56c-3cca-4d89-b4e6-6bcaeb1f2830
description: tblComplianceState contient des informations d’état de conformité au niveau du pool.
ms.openlocfilehash: 6f6b3891638fc3d769c0b0f4f4a42ca5f94a5a54
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929846"
---
# <a name="tblcompliancestate"></a><span data-ttu-id="96a8a-103">tblComplianceState</span><span class="sxs-lookup"><span data-stu-id="96a8a-103">tblComplianceState</span></span>
 
<span data-ttu-id="96a8a-104">tblComplianceState contient des informations d’état de conformité au niveau du pool.</span><span class="sxs-lookup"><span data-stu-id="96a8a-104">tblComplianceState contains pool-wide compliance state information.</span></span>
  
<span data-ttu-id="96a8a-105">**Colonnes**</span><span class="sxs-lookup"><span data-stu-id="96a8a-105">**Columns**</span></span>

|<span data-ttu-id="96a8a-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="96a8a-106">**Column**</span></span>|<span data-ttu-id="96a8a-107">**Type**</span><span class="sxs-lookup"><span data-stu-id="96a8a-107">**Type**</span></span>|<span data-ttu-id="96a8a-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="96a8a-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="96a8a-109">lastProcessedEntryID</span><span class="sxs-lookup"><span data-stu-id="96a8a-109">lastProcessedEntryID</span></span>  <br/> |<span data-ttu-id="96a8a-110">bigint, non null</span><span class="sxs-lookup"><span data-stu-id="96a8a-110">bigint, not null</span></span>  <br/> |<span data-ttu-id="96a8a-111">ID du dernier événement de conformité traité.</span><span class="sxs-lookup"><span data-stu-id="96a8a-111">ID of the latest processed compliance event.</span></span>  <br/> |
|<span data-ttu-id="96a8a-112">activeServerID</span><span class="sxs-lookup"><span data-stu-id="96a8a-112">activeServerID</span></span>  <br/> |<span data-ttu-id="96a8a-113">int, non null</span><span class="sxs-lookup"><span data-stu-id="96a8a-113">int, not null</span></span>  <br/> |<span data-ttu-id="96a8a-114">ID du serveur de conformité qui détient le verrou exclusif sur la base de données, ou -1 si aucun.</span><span class="sxs-lookup"><span data-stu-id="96a8a-114">ID of the Compliance server holding the exclusive lock on the database, or -1 if none.</span></span>  <br/> |
|<span data-ttu-id="96a8a-115">lockExpirationTime</span><span class="sxs-lookup"><span data-stu-id="96a8a-115">lockExpirationTime</span></span>  <br/> |<span data-ttu-id="96a8a-116">dateheure2, non null</span><span class="sxs-lookup"><span data-stu-id="96a8a-116">datetime2, not null</span></span>  <br/> |<span data-ttu-id="96a8a-117">Verrouiller le délai d’expiration (si activeServerID est différent de -1).</span><span class="sxs-lookup"><span data-stu-id="96a8a-117">Lock expiration time (if activeServerID is not -1).</span></span>  <br/> |
   

