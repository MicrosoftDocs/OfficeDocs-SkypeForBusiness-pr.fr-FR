---
title: tblComplianceFanout
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f5d9f342-a7cb-4b54-baa6-e656256b75ad
description: la table tblComplianceFanout contient tous les serveurs qui ont traité un événement de conformité.
ms.openlocfilehash: 7f24b1a78dab16b43036734e21d5a8a9b876ca7a
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30874050"
---
# <a name="tblcompliancefanout"></a><span data-ttu-id="b953d-103">tblComplianceFanout</span><span class="sxs-lookup"><span data-stu-id="b953d-103">tblComplianceFanout</span></span>
 
<span data-ttu-id="b953d-104">la table tblComplianceFanout contient tous les serveurs qui ont traité un événement de conformité.</span><span class="sxs-lookup"><span data-stu-id="b953d-104">tblComplianceFanout contains all servers that processed a compliance event.</span></span>
  
<span data-ttu-id="b953d-105">**Colonnes**</span><span class="sxs-lookup"><span data-stu-id="b953d-105">**Columns**</span></span>

|<span data-ttu-id="b953d-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="b953d-106">**Column**</span></span>|<span data-ttu-id="b953d-107">**Type**</span><span class="sxs-lookup"><span data-stu-id="b953d-107">**Type**</span></span>|<span data-ttu-id="b953d-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="b953d-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b953d-109">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="b953d-109">fanoutEventID</span></span>  <br/> |<span data-ttu-id="b953d-110">int</span><span class="sxs-lookup"><span data-stu-id="b953d-110">int</span></span>  <br/> |<span data-ttu-id="b953d-111">ID d’événement.</span><span class="sxs-lookup"><span data-stu-id="b953d-111">Event ID.</span></span>  <br/> |
|<span data-ttu-id="b953d-112">fanoutServerID</span><span class="sxs-lookup"><span data-stu-id="b953d-112">fanoutServerID</span></span>  <br/> |<span data-ttu-id="b953d-113">int</span><span class="sxs-lookup"><span data-stu-id="b953d-113">int</span></span>  <br/> |<span data-ttu-id="b953d-114">Identité du serveur (correspondant à la table tblServerIdentity.serverID).</span><span class="sxs-lookup"><span data-stu-id="b953d-114">Server identity (corresponding to tblServerIdentity.serverID table).</span></span>  <br/> |
   
<span data-ttu-id="b953d-115">**Clé**</span><span class="sxs-lookup"><span data-stu-id="b953d-115">**Key**</span></span>

|<span data-ttu-id="b953d-116">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="b953d-116">**Column**</span></span>|<span data-ttu-id="b953d-117">**Description**</span><span class="sxs-lookup"><span data-stu-id="b953d-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b953d-118">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="b953d-118">fanoutEventID</span></span>  <br/> |<span data-ttu-id="b953d-119">Clé étrangère avec recherche dans la table tblComplianceData.cmplEventID.</span><span class="sxs-lookup"><span data-stu-id="b953d-119">Foreign key with lookup in tblComplianceData.cmplEventID table.</span></span>  <br/> |
   

