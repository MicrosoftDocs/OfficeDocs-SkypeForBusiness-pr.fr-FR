---
title: tblComplianceFanout
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: f5d9f342-a7cb-4b54-baa6-e656256b75ad
description: La table tblComplianceFanout contient tous les serveurs qui ont traité un événement de conformité.
ms.openlocfilehash: 75e232cd464a2199b490e555c0fab79ded119c94
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809794"
---
# <a name="tblcompliancefanout"></a><span data-ttu-id="177ae-103">tblComplianceFanout</span><span class="sxs-lookup"><span data-stu-id="177ae-103">tblComplianceFanout</span></span>
 
<span data-ttu-id="177ae-104">La table tblComplianceFanout contient tous les serveurs qui ont traité un événement de conformité.</span><span class="sxs-lookup"><span data-stu-id="177ae-104">tblComplianceFanout contains all servers that processed a compliance event.</span></span>
  
<span data-ttu-id="177ae-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="177ae-105">**Columns**</span></span>

|<span data-ttu-id="177ae-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="177ae-106">**Column**</span></span>|<span data-ttu-id="177ae-107">**Type (Type)**</span><span class="sxs-lookup"><span data-stu-id="177ae-107">**Type**</span></span>|<span data-ttu-id="177ae-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="177ae-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="177ae-109">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="177ae-109">fanoutEventID</span></span>  <br/> |<span data-ttu-id="177ae-110">int</span><span class="sxs-lookup"><span data-stu-id="177ae-110">int</span></span>  <br/> |<span data-ttu-id="177ae-111">ID d’événement.</span><span class="sxs-lookup"><span data-stu-id="177ae-111">Event ID.</span></span>  <br/> |
|<span data-ttu-id="177ae-112">fanoutServerID</span><span class="sxs-lookup"><span data-stu-id="177ae-112">fanoutServerID</span></span>  <br/> |<span data-ttu-id="177ae-113">int</span><span class="sxs-lookup"><span data-stu-id="177ae-113">int</span></span>  <br/> |<span data-ttu-id="177ae-114">Identité du serveur (correspondant à la table tblServerIdentity.serverID).</span><span class="sxs-lookup"><span data-stu-id="177ae-114">Server identity (corresponding to tblServerIdentity.serverID table).</span></span>  <br/> |
   
<span data-ttu-id="177ae-115">**Clé**</span><span class="sxs-lookup"><span data-stu-id="177ae-115">**Key**</span></span>

|<span data-ttu-id="177ae-116">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="177ae-116">**Column**</span></span>|<span data-ttu-id="177ae-117">**Description**</span><span class="sxs-lookup"><span data-stu-id="177ae-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="177ae-118">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="177ae-118">fanoutEventID</span></span>  <br/> |<span data-ttu-id="177ae-119">Clé étrangère avec recherche dans la table tblComplianceData.cmplEventID.</span><span class="sxs-lookup"><span data-stu-id="177ae-119">Foreign key with lookup in tblComplianceData.cmplEventID table.</span></span>  <br/> |
   

