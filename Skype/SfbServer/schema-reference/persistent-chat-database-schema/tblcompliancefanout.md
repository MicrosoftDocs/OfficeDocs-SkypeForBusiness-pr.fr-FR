---
title: tblComplianceFanout
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f5d9f342-a7cb-4b54-baa6-e656256b75ad
description: tblComplianceFanout contient tous les serveurs de traitement d’un événement de conformité.
ms.openlocfilehash: f9141a6f7144c20d8039756387a889cc25cc8f50
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="tblcompliancefanout"></a><span data-ttu-id="3c21c-103">tblComplianceFanout</span><span class="sxs-lookup"><span data-stu-id="3c21c-103">tblComplianceFanout</span></span>
 
<span data-ttu-id="3c21c-104">tblComplianceFanout contient tous les serveurs de traitement d’un événement de conformité.</span><span class="sxs-lookup"><span data-stu-id="3c21c-104">tblComplianceFanout contains all servers that processed a compliance event.</span></span>
  
<span data-ttu-id="3c21c-105">**Colonnes**</span><span class="sxs-lookup"><span data-stu-id="3c21c-105">**Columns**</span></span>

|<span data-ttu-id="3c21c-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="3c21c-106">**Column**</span></span>|<span data-ttu-id="3c21c-107">**Type de**</span><span class="sxs-lookup"><span data-stu-id="3c21c-107">**Type**</span></span>|<span data-ttu-id="3c21c-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="3c21c-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="3c21c-109">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="3c21c-109">fanoutEventID</span></span>  <br/> |<span data-ttu-id="3c21c-110">int</span><span class="sxs-lookup"><span data-stu-id="3c21c-110">int</span></span>  <br/> |<span data-ttu-id="3c21c-111">ID d’événement.</span><span class="sxs-lookup"><span data-stu-id="3c21c-111">Event ID.</span></span>  <br/> |
|<span data-ttu-id="3c21c-112">fanoutServerID</span><span class="sxs-lookup"><span data-stu-id="3c21c-112">fanoutServerID</span></span>  <br/> |<span data-ttu-id="3c21c-113">int</span><span class="sxs-lookup"><span data-stu-id="3c21c-113">int</span></span>  <br/> |<span data-ttu-id="3c21c-114">Identité du serveur (correspondant à la table de tblServerIdentity.serverID).</span><span class="sxs-lookup"><span data-stu-id="3c21c-114">Server identity (corresponding to tblServerIdentity.serverID table).</span></span>  <br/> |
   
<span data-ttu-id="3c21c-115">**Clé**</span><span class="sxs-lookup"><span data-stu-id="3c21c-115">**Key**</span></span>

|<span data-ttu-id="3c21c-116">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="3c21c-116">**Column**</span></span>|<span data-ttu-id="3c21c-117">**Description**</span><span class="sxs-lookup"><span data-stu-id="3c21c-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="3c21c-118">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="3c21c-118">fanoutEventID</span></span>  <br/> |<span data-ttu-id="3c21c-119">Clé étrangère avec la recherche dans la table de tblComplianceData.cmplEventID.</span><span class="sxs-lookup"><span data-stu-id="3c21c-119">Foreign key with lookup in tblComplianceData.cmplEventID table.</span></span>  <br/> |
   

