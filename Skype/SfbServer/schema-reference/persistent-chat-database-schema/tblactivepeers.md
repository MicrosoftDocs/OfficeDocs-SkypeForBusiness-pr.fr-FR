---
title: tblActivePeers
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b50c3f4a-bab6-4cb9-b40e-016cf1a9c607
description: tblActivePeers contient les connexions de pair à pair en cours entre les services de conversation.
ms.openlocfilehash: 5dc585a8db67c1bbdcc1c3933018b1296fd75484
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="tblactivepeers"></a><span data-ttu-id="88eae-103">tblActivePeers</span><span class="sxs-lookup"><span data-stu-id="88eae-103">tblActivePeers</span></span>
 
<span data-ttu-id="88eae-104">tblActivePeers contient les connexions de pair à pair en cours entre les services de conversation.</span><span class="sxs-lookup"><span data-stu-id="88eae-104">tblActivePeers contains the current peer-to-peer connections between chat services.</span></span>
  
<span data-ttu-id="88eae-105">**Colonnes**</span><span class="sxs-lookup"><span data-stu-id="88eae-105">**Columns**</span></span>

|<span data-ttu-id="88eae-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="88eae-106">**Column**</span></span>|<span data-ttu-id="88eae-107">**Type de**</span><span class="sxs-lookup"><span data-stu-id="88eae-107">**Type**</span></span>|<span data-ttu-id="88eae-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="88eae-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="88eae-109">aplServerID</span><span class="sxs-lookup"><span data-stu-id="88eae-109">aplServerID</span></span>  <br/> |<span data-ttu-id="88eae-110">int, non null</span><span class="sxs-lookup"><span data-stu-id="88eae-110">int, not null</span></span>  <br/> |<span data-ttu-id="88eae-111">ID du serveur qui a validé l’écriture.</span><span class="sxs-lookup"><span data-stu-id="88eae-111">ID of the server that posted the entry.</span></span>  <br/> |
|<span data-ttu-id="88eae-112">aplPeerID</span><span class="sxs-lookup"><span data-stu-id="88eae-112">aplPeerID</span></span>  <br/> |<span data-ttu-id="88eae-113">int, non null</span><span class="sxs-lookup"><span data-stu-id="88eae-113">int, not null</span></span>  <br/> |<span data-ttu-id="88eae-114">ID de l’hôte auquel est connecté le serveur de validation.</span><span class="sxs-lookup"><span data-stu-id="88eae-114">ID of the peer that the posting server is connected to.</span></span>  <br/> |
   
<span data-ttu-id="88eae-115">**Clés**</span><span class="sxs-lookup"><span data-stu-id="88eae-115">**Keys**</span></span>

|<span data-ttu-id="88eae-116">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="88eae-116">**Column**</span></span>|<span data-ttu-id="88eae-117">**Description**</span><span class="sxs-lookup"><span data-stu-id="88eae-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="88eae-118">\<aplServerID, aplPeerID\></span><span class="sxs-lookup"><span data-stu-id="88eae-118">\<aplServerID, aplPeerID\></span></span>  <br/> |<span data-ttu-id="88eae-119">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="88eae-119">Primary key.</span></span>  <br/> |
|<span data-ttu-id="88eae-120">aplServerID</span><span class="sxs-lookup"><span data-stu-id="88eae-120">aplServerID</span></span>  <br/> |<span data-ttu-id="88eae-121">Clé étrangère avec la recherche dans la table de tblServerIdentity.serverID.</span><span class="sxs-lookup"><span data-stu-id="88eae-121">Foreign key with lookup in tblServerIdentity.serverID table.</span></span>  <br/> |
|<span data-ttu-id="88eae-122">aplPeerID</span><span class="sxs-lookup"><span data-stu-id="88eae-122">aplPeerID</span></span>  <br/> |<span data-ttu-id="88eae-123">Clé étrangère avec la recherche dans la table de tblServerIdentity.serverID.</span><span class="sxs-lookup"><span data-stu-id="88eae-123">Foreign key with lookup in tblServerIdentity.serverID table.</span></span>  <br/> |
   

