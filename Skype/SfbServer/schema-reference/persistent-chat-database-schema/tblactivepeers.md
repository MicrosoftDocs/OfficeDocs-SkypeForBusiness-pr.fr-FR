---
title: tblActivePeers
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
ms.assetid: b50c3f4a-bab6-4cb9-b40e-016cf1a9c607
description: tblActivePeers contient les connexions pair à pair actuelles entre les services de conversation.
ms.openlocfilehash: befba4086a78281fbfbec1e270b7c8e3f8174752
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812934"
---
# <a name="tblactivepeers"></a><span data-ttu-id="320cb-103">tblActivePeers</span><span class="sxs-lookup"><span data-stu-id="320cb-103">tblActivePeers</span></span>
 
<span data-ttu-id="320cb-104">tblActivePeers contient les connexions pair à pair actuelles entre les services de conversation.</span><span class="sxs-lookup"><span data-stu-id="320cb-104">tblActivePeers contains the current peer-to-peer connections between chat services.</span></span>
  
<span data-ttu-id="320cb-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="320cb-105">**Columns**</span></span>

|<span data-ttu-id="320cb-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="320cb-106">**Column**</span></span>|<span data-ttu-id="320cb-107">**Type**</span><span class="sxs-lookup"><span data-stu-id="320cb-107">**Type**</span></span>|<span data-ttu-id="320cb-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="320cb-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="320cb-109">aplServerID</span><span class="sxs-lookup"><span data-stu-id="320cb-109">aplServerID</span></span>  <br/> |<span data-ttu-id="320cb-110">int, non null</span><span class="sxs-lookup"><span data-stu-id="320cb-110">int, not null</span></span>  <br/> |<span data-ttu-id="320cb-111">ID du serveur qui a publié l’entrée.</span><span class="sxs-lookup"><span data-stu-id="320cb-111">ID of the server that posted the entry.</span></span>  <br/> |
|<span data-ttu-id="320cb-112">aplPeerID</span><span class="sxs-lookup"><span data-stu-id="320cb-112">aplPeerID</span></span>  <br/> |<span data-ttu-id="320cb-113">int, non null</span><span class="sxs-lookup"><span data-stu-id="320cb-113">int, not null</span></span>  <br/> |<span data-ttu-id="320cb-114">ID de l’homologue à qui le serveur de publication est connecté.</span><span class="sxs-lookup"><span data-stu-id="320cb-114">ID of the peer that the posting server is connected to.</span></span>  <br/> |
   
<span data-ttu-id="320cb-115">**Keys**</span><span class="sxs-lookup"><span data-stu-id="320cb-115">**Keys**</span></span>

|<span data-ttu-id="320cb-116">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="320cb-116">**Column**</span></span>|<span data-ttu-id="320cb-117">**Description**</span><span class="sxs-lookup"><span data-stu-id="320cb-117">**Description**</span></span>|
|:-----|:-----|
|\<aplServerID, aplPeerID\>  <br/> |<span data-ttu-id="320cb-118">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="320cb-118">Primary key.</span></span>  <br/> |
|<span data-ttu-id="320cb-119">aplServerID</span><span class="sxs-lookup"><span data-stu-id="320cb-119">aplServerID</span></span>  <br/> |<span data-ttu-id="320cb-120">Clé étrangère avec recherche dans la table tblServerIdentity.serverID.</span><span class="sxs-lookup"><span data-stu-id="320cb-120">Foreign key with lookup in tblServerIdentity.serverID table.</span></span>  <br/> |
|<span data-ttu-id="320cb-121">aplPeerID</span><span class="sxs-lookup"><span data-stu-id="320cb-121">aplPeerID</span></span>  <br/> |<span data-ttu-id="320cb-122">Clé étrangère avec recherche dans la table tblServerIdentity.serverID.</span><span class="sxs-lookup"><span data-stu-id="320cb-122">Foreign key with lookup in tblServerIdentity.serverID table.</span></span>  <br/> |
   

