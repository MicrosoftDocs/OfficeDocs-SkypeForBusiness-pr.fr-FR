---
title: tblComplianceFanout
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f5d9f342-a7cb-4b54-baa6-e656256b75ad
description: tblComplianceFanout contient tous les serveurs qui ont traité un événement de conformité.
ms.openlocfilehash: 1d2dfc99619e0669a08db33dbacc75930053f0dc
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295502"
---
# <a name="tblcompliancefanout"></a><span data-ttu-id="5615f-103">tblComplianceFanout</span><span class="sxs-lookup"><span data-stu-id="5615f-103">tblComplianceFanout</span></span>
 
<span data-ttu-id="5615f-104">tblComplianceFanout contient tous les serveurs qui ont traité un événement de conformité.</span><span class="sxs-lookup"><span data-stu-id="5615f-104">tblComplianceFanout contains all servers that processed a compliance event.</span></span>
  
<span data-ttu-id="5615f-105">**Celles**</span><span class="sxs-lookup"><span data-stu-id="5615f-105">**Columns**</span></span>

|<span data-ttu-id="5615f-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="5615f-106">**Column**</span></span>|<span data-ttu-id="5615f-107">**Type**</span><span class="sxs-lookup"><span data-stu-id="5615f-107">**Type**</span></span>|<span data-ttu-id="5615f-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="5615f-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="5615f-109">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="5615f-109">fanoutEventID</span></span>  <br/> |<span data-ttu-id="5615f-110">int</span><span class="sxs-lookup"><span data-stu-id="5615f-110">int</span></span>  <br/> |<span data-ttu-id="5615f-111">ID de l’événement.</span><span class="sxs-lookup"><span data-stu-id="5615f-111">Event ID.</span></span>  <br/> |
|<span data-ttu-id="5615f-112">fanoutServerID</span><span class="sxs-lookup"><span data-stu-id="5615f-112">fanoutServerID</span></span>  <br/> |<span data-ttu-id="5615f-113">int</span><span class="sxs-lookup"><span data-stu-id="5615f-113">int</span></span>  <br/> |<span data-ttu-id="5615f-114">Identité du serveur (correspondant à la table tblServerIdentity. serverID).</span><span class="sxs-lookup"><span data-stu-id="5615f-114">Server identity (corresponding to tblServerIdentity.serverID table).</span></span>  <br/> |
   
<span data-ttu-id="5615f-115">**Clé**</span><span class="sxs-lookup"><span data-stu-id="5615f-115">**Key**</span></span>

|<span data-ttu-id="5615f-116">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="5615f-116">**Column**</span></span>|<span data-ttu-id="5615f-117">**Description**</span><span class="sxs-lookup"><span data-stu-id="5615f-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="5615f-118">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="5615f-118">fanoutEventID</span></span>  <br/> |<span data-ttu-id="5615f-119">Clé étrangère avec recherche dans la table tblComplianceData. cmplEventID.</span><span class="sxs-lookup"><span data-stu-id="5615f-119">Foreign key with lookup in tblComplianceData.cmplEventID table.</span></span>  <br/> |
   

