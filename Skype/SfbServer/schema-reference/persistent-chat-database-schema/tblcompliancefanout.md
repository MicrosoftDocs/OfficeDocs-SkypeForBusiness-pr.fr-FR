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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: f5d9f342-a7cb-4b54-baa6-e656256b75ad
description: tblComplianceFanout contient tous les serveurs qui ont traité un événement de conformité.
ms.openlocfilehash: cdf455563ccfc971963144b9d4e848d5678cac80
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814652"
---
# <a name="tblcompliancefanout"></a><span data-ttu-id="77276-103">tblComplianceFanout</span><span class="sxs-lookup"><span data-stu-id="77276-103">tblComplianceFanout</span></span>
 
<span data-ttu-id="77276-104">tblComplianceFanout contient tous les serveurs qui ont traité un événement de conformité.</span><span class="sxs-lookup"><span data-stu-id="77276-104">tblComplianceFanout contains all servers that processed a compliance event.</span></span>
  
<span data-ttu-id="77276-105">**Celles**</span><span class="sxs-lookup"><span data-stu-id="77276-105">**Columns**</span></span>

|<span data-ttu-id="77276-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="77276-106">**Column**</span></span>|<span data-ttu-id="77276-107">**Type**</span><span class="sxs-lookup"><span data-stu-id="77276-107">**Type**</span></span>|<span data-ttu-id="77276-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="77276-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="77276-109">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="77276-109">fanoutEventID</span></span>  <br/> |<span data-ttu-id="77276-110">int</span><span class="sxs-lookup"><span data-stu-id="77276-110">int</span></span>  <br/> |<span data-ttu-id="77276-111">ID de l’événement.</span><span class="sxs-lookup"><span data-stu-id="77276-111">Event ID.</span></span>  <br/> |
|<span data-ttu-id="77276-112">fanoutServerID</span><span class="sxs-lookup"><span data-stu-id="77276-112">fanoutServerID</span></span>  <br/> |<span data-ttu-id="77276-113">int</span><span class="sxs-lookup"><span data-stu-id="77276-113">int</span></span>  <br/> |<span data-ttu-id="77276-114">Identité du serveur (correspondant à la table tblServerIdentity. serverID).</span><span class="sxs-lookup"><span data-stu-id="77276-114">Server identity (corresponding to tblServerIdentity.serverID table).</span></span>  <br/> |
   
<span data-ttu-id="77276-115">**Clé**</span><span class="sxs-lookup"><span data-stu-id="77276-115">**Key**</span></span>

|<span data-ttu-id="77276-116">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="77276-116">**Column**</span></span>|<span data-ttu-id="77276-117">**Description**</span><span class="sxs-lookup"><span data-stu-id="77276-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="77276-118">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="77276-118">fanoutEventID</span></span>  <br/> |<span data-ttu-id="77276-119">Clé étrangère avec recherche dans la table tblComplianceData. cmplEventID.</span><span class="sxs-lookup"><span data-stu-id="77276-119">Foreign key with lookup in tblComplianceData.cmplEventID table.</span></span>  <br/> |
   

