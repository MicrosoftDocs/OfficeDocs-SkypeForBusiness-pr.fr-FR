---
title: tblActivePeers
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b50c3f4a-bab6-4cb9-b40e-016cf1a9c607
description: tblActivePeers contient les connexions d’égal à égal actuelles entre les services de discussion.
ms.openlocfilehash: f45a04019cafc2304baf825b5000e96ca7a6cead
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295544"
---
# <a name="tblactivepeers"></a><span data-ttu-id="76ea2-103">tblActivePeers</span><span class="sxs-lookup"><span data-stu-id="76ea2-103">tblActivePeers</span></span>
 
<span data-ttu-id="76ea2-104">tblActivePeers contient les connexions d’égal à égal actuelles entre les services de discussion.</span><span class="sxs-lookup"><span data-stu-id="76ea2-104">tblActivePeers contains the current peer-to-peer connections between chat services.</span></span>
  
<span data-ttu-id="76ea2-105">**Celles**</span><span class="sxs-lookup"><span data-stu-id="76ea2-105">**Columns**</span></span>

|<span data-ttu-id="76ea2-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="76ea2-106">**Column**</span></span>|<span data-ttu-id="76ea2-107">**Type**</span><span class="sxs-lookup"><span data-stu-id="76ea2-107">**Type**</span></span>|<span data-ttu-id="76ea2-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="76ea2-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="76ea2-109">aplServerID</span><span class="sxs-lookup"><span data-stu-id="76ea2-109">aplServerID</span></span>  <br/> |<span data-ttu-id="76ea2-110">ent, non null</span><span class="sxs-lookup"><span data-stu-id="76ea2-110">int, not null</span></span>  <br/> |<span data-ttu-id="76ea2-111">ID du serveur qui a publié l’entrée.</span><span class="sxs-lookup"><span data-stu-id="76ea2-111">ID of the server that posted the entry.</span></span>  <br/> |
|<span data-ttu-id="76ea2-112">aplPeerID</span><span class="sxs-lookup"><span data-stu-id="76ea2-112">aplPeerID</span></span>  <br/> |<span data-ttu-id="76ea2-113">ent, non null</span><span class="sxs-lookup"><span data-stu-id="76ea2-113">int, not null</span></span>  <br/> |<span data-ttu-id="76ea2-114">ID de l’homologue auquel est connecté le serveur de publication.</span><span class="sxs-lookup"><span data-stu-id="76ea2-114">ID of the peer that the posting server is connected to.</span></span>  <br/> |
   
<span data-ttu-id="76ea2-115">**Permettent**</span><span class="sxs-lookup"><span data-stu-id="76ea2-115">**Keys**</span></span>

|<span data-ttu-id="76ea2-116">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="76ea2-116">**Column**</span></span>|<span data-ttu-id="76ea2-117">**Description**</span><span class="sxs-lookup"><span data-stu-id="76ea2-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="76ea2-118">\<aplServerID, aplPeerID\></span><span class="sxs-lookup"><span data-stu-id="76ea2-118">\<aplServerID, aplPeerID\></span></span>  <br/> |<span data-ttu-id="76ea2-119">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="76ea2-119">Primary key.</span></span>  <br/> |
|<span data-ttu-id="76ea2-120">aplServerID</span><span class="sxs-lookup"><span data-stu-id="76ea2-120">aplServerID</span></span>  <br/> |<span data-ttu-id="76ea2-121">Clé étrangère avec recherche dans la table tblServerIdentity. serverID.</span><span class="sxs-lookup"><span data-stu-id="76ea2-121">Foreign key with lookup in tblServerIdentity.serverID table.</span></span>  <br/> |
|<span data-ttu-id="76ea2-122">aplPeerID</span><span class="sxs-lookup"><span data-stu-id="76ea2-122">aplPeerID</span></span>  <br/> |<span data-ttu-id="76ea2-123">Clé étrangère avec recherche dans la table tblServerIdentity. serverID.</span><span class="sxs-lookup"><span data-stu-id="76ea2-123">Foreign key with lookup in tblServerIdentity.serverID table.</span></span>  <br/> |
   

