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
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212627"
---
# <a name="tblcompliancefanout"></a><span data-ttu-id="36e90-103">tblComplianceFanout</span><span class="sxs-lookup"><span data-stu-id="36e90-103">tblComplianceFanout</span></span>
 
<span data-ttu-id="36e90-104">la table tblComplianceFanout contient tous les serveurs qui ont traité un événement de conformité.</span><span class="sxs-lookup"><span data-stu-id="36e90-104">tblComplianceFanout contains all servers that processed a compliance event.</span></span>
  
<span data-ttu-id="36e90-105">**Colonnes**</span><span class="sxs-lookup"><span data-stu-id="36e90-105">**Columns**</span></span>

|<span data-ttu-id="36e90-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="36e90-106">**Column**</span></span>|<span data-ttu-id="36e90-107">**Type**</span><span class="sxs-lookup"><span data-stu-id="36e90-107">**Type**</span></span>|<span data-ttu-id="36e90-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="36e90-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="36e90-109">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="36e90-109">fanoutEventID</span></span>  <br/> |<span data-ttu-id="36e90-110">int</span><span class="sxs-lookup"><span data-stu-id="36e90-110">int</span></span>  <br/> |<span data-ttu-id="36e90-111">ID d’événement.</span><span class="sxs-lookup"><span data-stu-id="36e90-111">Event ID.</span></span>  <br/> |
|<span data-ttu-id="36e90-112">fanoutServerID</span><span class="sxs-lookup"><span data-stu-id="36e90-112">fanoutServerID</span></span>  <br/> |<span data-ttu-id="36e90-113">int</span><span class="sxs-lookup"><span data-stu-id="36e90-113">int</span></span>  <br/> |<span data-ttu-id="36e90-114">Identité du serveur (correspondant à la table tblServerIdentity.serverID).</span><span class="sxs-lookup"><span data-stu-id="36e90-114">Server identity (corresponding to tblServerIdentity.serverID table).</span></span>  <br/> |
   
<span data-ttu-id="36e90-115">**Clé**</span><span class="sxs-lookup"><span data-stu-id="36e90-115">**Key**</span></span>

|<span data-ttu-id="36e90-116">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="36e90-116">**Column**</span></span>|<span data-ttu-id="36e90-117">**Description**</span><span class="sxs-lookup"><span data-stu-id="36e90-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="36e90-118">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="36e90-118">fanoutEventID</span></span>  <br/> |<span data-ttu-id="36e90-119">Clé étrangère avec recherche dans la table tblComplianceData.cmplEventID.</span><span class="sxs-lookup"><span data-stu-id="36e90-119">Foreign key with lookup in tblComplianceData.cmplEventID table.</span></span>  <br/> |
   

