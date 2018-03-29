---
title: tblComplianceState
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ea82e56c-3cca-4d89-b4e6-6bcaeb1f2830
description: tblComplianceState contient les informations d’état de conformité de l’ensemble du pool.
ms.openlocfilehash: e46db9c73f4489ade9bbed90f0061567fd14af1d
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="tblcompliancestate"></a><span data-ttu-id="a23ef-103">tblComplianceState</span><span class="sxs-lookup"><span data-stu-id="a23ef-103">tblComplianceState</span></span>
 
<span data-ttu-id="a23ef-104">tblComplianceState contient les informations d’état de conformité de l’ensemble du pool.</span><span class="sxs-lookup"><span data-stu-id="a23ef-104">tblComplianceState contains pool-wide compliance state information.</span></span>
  
<span data-ttu-id="a23ef-105">**Colonnes**</span><span class="sxs-lookup"><span data-stu-id="a23ef-105">**Columns**</span></span>

|<span data-ttu-id="a23ef-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="a23ef-106">**Column**</span></span>|<span data-ttu-id="a23ef-107">**Type de**</span><span class="sxs-lookup"><span data-stu-id="a23ef-107">**Type**</span></span>|<span data-ttu-id="a23ef-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="a23ef-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a23ef-109">lastProcessedEntryID</span><span class="sxs-lookup"><span data-stu-id="a23ef-109">lastProcessedEntryID</span></span>  <br/> |<span data-ttu-id="a23ef-110">bigint, non null</span><span class="sxs-lookup"><span data-stu-id="a23ef-110">bigint, not null</span></span>  <br/> |<span data-ttu-id="a23ef-111">ID de l’événement de conformité traités plus récent.</span><span class="sxs-lookup"><span data-stu-id="a23ef-111">ID of the latest processed compliance event.</span></span>  <br/> |
|<span data-ttu-id="a23ef-112">activeServerID</span><span class="sxs-lookup"><span data-stu-id="a23ef-112">activeServerID</span></span>  <br/> |<span data-ttu-id="a23ef-113">int, non null</span><span class="sxs-lookup"><span data-stu-id="a23ef-113">int, not null</span></span>  <br/> |<span data-ttu-id="a23ef-114">ID du serveur de mise en conformité maintenant le verrou exclusif sur la base de données, ou -1 si aucun.</span><span class="sxs-lookup"><span data-stu-id="a23ef-114">ID of the Compliance server holding the exclusive lock on the database, or -1 if none.</span></span>  <br/> |
|<span data-ttu-id="a23ef-115">lockExpirationTime</span><span class="sxs-lookup"><span data-stu-id="a23ef-115">lockExpirationTime</span></span>  <br/> |<span data-ttu-id="a23ef-116">datetime2, non null</span><span class="sxs-lookup"><span data-stu-id="a23ef-116">datetime2, not null</span></span>  <br/> |<span data-ttu-id="a23ef-117">Verrouiller le délai d’expiration (si activeServerID n’est pas -1).</span><span class="sxs-lookup"><span data-stu-id="a23ef-117">Lock expiration time (if activeServerID is not -1).</span></span>  <br/> |
   

