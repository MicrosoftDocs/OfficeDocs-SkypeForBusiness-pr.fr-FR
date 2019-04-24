---
title: tblActivePeers
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b50c3f4a-bab6-4cb9-b40e-016cf1a9c607
description: Activepeers contient les connexions d’égal à égal actuelles entre les services de conversation.
ms.openlocfilehash: e921d6faa4f7bcf3e3c6f6dc9859f4bd0db16bc5
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212676"
---
# <a name="tblactivepeers"></a><span data-ttu-id="2b012-103">tblActivePeers</span><span class="sxs-lookup"><span data-stu-id="2b012-103">tblActivePeers</span></span>
 
<span data-ttu-id="2b012-104">Activepeers contient les connexions d’égal à égal actuelles entre les services de conversation.</span><span class="sxs-lookup"><span data-stu-id="2b012-104">tblActivePeers contains the current peer-to-peer connections between chat services.</span></span>
  
<span data-ttu-id="2b012-105">**Colonnes**</span><span class="sxs-lookup"><span data-stu-id="2b012-105">**Columns**</span></span>

|<span data-ttu-id="2b012-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="2b012-106">**Column**</span></span>|<span data-ttu-id="2b012-107">**Type**</span><span class="sxs-lookup"><span data-stu-id="2b012-107">**Type**</span></span>|<span data-ttu-id="2b012-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="2b012-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="2b012-109">aplServerID</span><span class="sxs-lookup"><span data-stu-id="2b012-109">aplServerID</span></span>  <br/> |<span data-ttu-id="2b012-110">int, non null</span><span class="sxs-lookup"><span data-stu-id="2b012-110">int, not null</span></span>  <br/> |<span data-ttu-id="2b012-111">ID du serveur ayant publié l’entrée.</span><span class="sxs-lookup"><span data-stu-id="2b012-111">ID of the server that posted the entry.</span></span>  <br/> |
|<span data-ttu-id="2b012-112">aplPeerID</span><span class="sxs-lookup"><span data-stu-id="2b012-112">aplPeerID</span></span>  <br/> |<span data-ttu-id="2b012-113">int, non null</span><span class="sxs-lookup"><span data-stu-id="2b012-113">int, not null</span></span>  <br/> |<span data-ttu-id="2b012-114">ID de l’homologue auquel est connecté le serveur de publication.</span><span class="sxs-lookup"><span data-stu-id="2b012-114">ID of the peer that the posting server is connected to.</span></span>  <br/> |
   
<span data-ttu-id="2b012-115">**Clés**</span><span class="sxs-lookup"><span data-stu-id="2b012-115">**Keys**</span></span>

|<span data-ttu-id="2b012-116">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="2b012-116">**Column**</span></span>|<span data-ttu-id="2b012-117">**Description**</span><span class="sxs-lookup"><span data-stu-id="2b012-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="2b012-118">\<aplServerID, aplPeerID\></span><span class="sxs-lookup"><span data-stu-id="2b012-118">\<aplServerID, aplPeerID\></span></span>  <br/> |<span data-ttu-id="2b012-119">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="2b012-119">Primary key.</span></span>  <br/> |
|<span data-ttu-id="2b012-120">aplServerID</span><span class="sxs-lookup"><span data-stu-id="2b012-120">aplServerID</span></span>  <br/> |<span data-ttu-id="2b012-121">Clé étrangère avec recherche dans la table tblServerIdentity.serverID.</span><span class="sxs-lookup"><span data-stu-id="2b012-121">Foreign key with lookup in tblServerIdentity.serverID table.</span></span>  <br/> |
|<span data-ttu-id="2b012-122">aplPeerID</span><span class="sxs-lookup"><span data-stu-id="2b012-122">aplPeerID</span></span>  <br/> |<span data-ttu-id="2b012-123">Clé étrangère avec recherche dans la table tblServerIdentity.serverID.</span><span class="sxs-lookup"><span data-stu-id="2b012-123">Foreign key with lookup in tblServerIdentity.serverID table.</span></span>  <br/> |
   

