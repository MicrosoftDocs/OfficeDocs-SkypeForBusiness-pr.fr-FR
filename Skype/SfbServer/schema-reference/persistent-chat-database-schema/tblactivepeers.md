---
title: tblActivePeers
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b50c3f4a-bab6-4cb9-b40e-016cf1a9c607
description: Activepeers contient les connexions d’égal à égal actuelles entre les services de conversation.
ms.openlocfilehash: 7d7f995b878d6e47878636bee6f9c16ac142352e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929874"
---
# <a name="tblactivepeers"></a><span data-ttu-id="ac631-103">tblActivePeers</span><span class="sxs-lookup"><span data-stu-id="ac631-103">tblActivePeers</span></span>
 
<span data-ttu-id="ac631-104">Activepeers contient les connexions d’égal à égal actuelles entre les services de conversation.</span><span class="sxs-lookup"><span data-stu-id="ac631-104">tblActivePeers contains the current peer-to-peer connections between chat services.</span></span>
  
<span data-ttu-id="ac631-105">**Colonnes**</span><span class="sxs-lookup"><span data-stu-id="ac631-105">**Columns**</span></span>

|<span data-ttu-id="ac631-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="ac631-106">**Column**</span></span>|<span data-ttu-id="ac631-107">**Type**</span><span class="sxs-lookup"><span data-stu-id="ac631-107">**Type**</span></span>|<span data-ttu-id="ac631-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="ac631-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ac631-109">aplServerID</span><span class="sxs-lookup"><span data-stu-id="ac631-109">aplServerID</span></span>  <br/> |<span data-ttu-id="ac631-110">int, non null</span><span class="sxs-lookup"><span data-stu-id="ac631-110">int, not null</span></span>  <br/> |<span data-ttu-id="ac631-111">ID du serveur ayant publié l’entrée.</span><span class="sxs-lookup"><span data-stu-id="ac631-111">ID of the server that posted the entry.</span></span>  <br/> |
|<span data-ttu-id="ac631-112">aplPeerID</span><span class="sxs-lookup"><span data-stu-id="ac631-112">aplPeerID</span></span>  <br/> |<span data-ttu-id="ac631-113">int, non null</span><span class="sxs-lookup"><span data-stu-id="ac631-113">int, not null</span></span>  <br/> |<span data-ttu-id="ac631-114">ID de l’homologue auquel est connecté le serveur de publication.</span><span class="sxs-lookup"><span data-stu-id="ac631-114">ID of the peer that the posting server is connected to.</span></span>  <br/> |
   
<span data-ttu-id="ac631-115">**Clés**</span><span class="sxs-lookup"><span data-stu-id="ac631-115">**Keys**</span></span>

|<span data-ttu-id="ac631-116">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="ac631-116">**Column**</span></span>|<span data-ttu-id="ac631-117">**Description**</span><span class="sxs-lookup"><span data-stu-id="ac631-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ac631-118">\<aplServerID, aplPeerID\></span><span class="sxs-lookup"><span data-stu-id="ac631-118">\<aplServerID, aplPeerID\></span></span>  <br/> |<span data-ttu-id="ac631-119">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="ac631-119">Primary key.</span></span>  <br/> |
|<span data-ttu-id="ac631-120">aplServerID</span><span class="sxs-lookup"><span data-stu-id="ac631-120">aplServerID</span></span>  <br/> |<span data-ttu-id="ac631-121">Clé étrangère avec recherche dans la table tblServerIdentity.serverID.</span><span class="sxs-lookup"><span data-stu-id="ac631-121">Foreign key with lookup in tblServerIdentity.serverID table.</span></span>  <br/> |
|<span data-ttu-id="ac631-122">aplPeerID</span><span class="sxs-lookup"><span data-stu-id="ac631-122">aplPeerID</span></span>  <br/> |<span data-ttu-id="ac631-123">Clé étrangère avec recherche dans la table tblServerIdentity.serverID.</span><span class="sxs-lookup"><span data-stu-id="ac631-123">Foreign key with lookup in tblServerIdentity.serverID table.</span></span>  <br/> |
   

