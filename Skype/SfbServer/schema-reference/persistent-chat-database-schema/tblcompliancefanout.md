---
title: tblComplianceFanout
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f5d9f342-a7cb-4b54-baa6-e656256b75ad
description: la table tblComplianceFanout contient tous les serveurs qui ont traité un événement de conformité.
ms.openlocfilehash: 002ffe3fd825dd90a5223dca06316ff3a60fddd9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929922"
---
# <a name="tblcompliancefanout"></a><span data-ttu-id="c8bf8-103">tblComplianceFanout</span><span class="sxs-lookup"><span data-stu-id="c8bf8-103">tblComplianceFanout</span></span>
 
<span data-ttu-id="c8bf8-104">la table tblComplianceFanout contient tous les serveurs qui ont traité un événement de conformité.</span><span class="sxs-lookup"><span data-stu-id="c8bf8-104">tblComplianceFanout contains all servers that processed a compliance event.</span></span>
  
<span data-ttu-id="c8bf8-105">**Colonnes**</span><span class="sxs-lookup"><span data-stu-id="c8bf8-105">**Columns**</span></span>

|<span data-ttu-id="c8bf8-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="c8bf8-106">**Column**</span></span>|<span data-ttu-id="c8bf8-107">**Type**</span><span class="sxs-lookup"><span data-stu-id="c8bf8-107">**Type**</span></span>|<span data-ttu-id="c8bf8-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="c8bf8-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c8bf8-109">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="c8bf8-109">fanoutEventID</span></span>  <br/> |<span data-ttu-id="c8bf8-110">int</span><span class="sxs-lookup"><span data-stu-id="c8bf8-110">int</span></span>  <br/> |<span data-ttu-id="c8bf8-111">ID d’événement.</span><span class="sxs-lookup"><span data-stu-id="c8bf8-111">Event ID.</span></span>  <br/> |
|<span data-ttu-id="c8bf8-112">fanoutServerID</span><span class="sxs-lookup"><span data-stu-id="c8bf8-112">fanoutServerID</span></span>  <br/> |<span data-ttu-id="c8bf8-113">int</span><span class="sxs-lookup"><span data-stu-id="c8bf8-113">int</span></span>  <br/> |<span data-ttu-id="c8bf8-114">Identité du serveur (correspondant à la table tblServerIdentity.serverID).</span><span class="sxs-lookup"><span data-stu-id="c8bf8-114">Server identity (corresponding to tblServerIdentity.serverID table).</span></span>  <br/> |
   
<span data-ttu-id="c8bf8-115">**Clé**</span><span class="sxs-lookup"><span data-stu-id="c8bf8-115">**Key**</span></span>

|<span data-ttu-id="c8bf8-116">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="c8bf8-116">**Column**</span></span>|<span data-ttu-id="c8bf8-117">**Description**</span><span class="sxs-lookup"><span data-stu-id="c8bf8-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c8bf8-118">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="c8bf8-118">fanoutEventID</span></span>  <br/> |<span data-ttu-id="c8bf8-119">Clé étrangère avec recherche dans la table tblComplianceData.cmplEventID.</span><span class="sxs-lookup"><span data-stu-id="c8bf8-119">Foreign key with lookup in tblComplianceData.cmplEventID table.</span></span>  <br/> |
   

