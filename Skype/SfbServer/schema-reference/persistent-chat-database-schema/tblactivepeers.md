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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b50c3f4a-bab6-4cb9-b40e-016cf1a9c607
description: tblActivePeers contient les connexions d’égal à égal actuelles entre les services de discussion.
ms.openlocfilehash: 4604c13dbff9565748dd59e5917a5c133bd71947
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814712"
---
# <a name="tblactivepeers"></a><span data-ttu-id="89502-103">tblActivePeers</span><span class="sxs-lookup"><span data-stu-id="89502-103">tblActivePeers</span></span>
 
<span data-ttu-id="89502-104">tblActivePeers contient les connexions d’égal à égal actuelles entre les services de discussion.</span><span class="sxs-lookup"><span data-stu-id="89502-104">tblActivePeers contains the current peer-to-peer connections between chat services.</span></span>
  
<span data-ttu-id="89502-105">**Celles**</span><span class="sxs-lookup"><span data-stu-id="89502-105">**Columns**</span></span>

|<span data-ttu-id="89502-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="89502-106">**Column**</span></span>|<span data-ttu-id="89502-107">**Type**</span><span class="sxs-lookup"><span data-stu-id="89502-107">**Type**</span></span>|<span data-ttu-id="89502-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="89502-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="89502-109">aplServerID</span><span class="sxs-lookup"><span data-stu-id="89502-109">aplServerID</span></span>  <br/> |<span data-ttu-id="89502-110">ent, non null</span><span class="sxs-lookup"><span data-stu-id="89502-110">int, not null</span></span>  <br/> |<span data-ttu-id="89502-111">ID du serveur qui a publié l’entrée.</span><span class="sxs-lookup"><span data-stu-id="89502-111">ID of the server that posted the entry.</span></span>  <br/> |
|<span data-ttu-id="89502-112">aplPeerID</span><span class="sxs-lookup"><span data-stu-id="89502-112">aplPeerID</span></span>  <br/> |<span data-ttu-id="89502-113">ent, non null</span><span class="sxs-lookup"><span data-stu-id="89502-113">int, not null</span></span>  <br/> |<span data-ttu-id="89502-114">ID de l’homologue auquel est connecté le serveur de publication.</span><span class="sxs-lookup"><span data-stu-id="89502-114">ID of the peer that the posting server is connected to.</span></span>  <br/> |
   
<span data-ttu-id="89502-115">**Permettent**</span><span class="sxs-lookup"><span data-stu-id="89502-115">**Keys**</span></span>

|<span data-ttu-id="89502-116">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="89502-116">**Column**</span></span>|<span data-ttu-id="89502-117">**Description**</span><span class="sxs-lookup"><span data-stu-id="89502-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="89502-118">\<aplServerID, aplPeerID\></span><span class="sxs-lookup"><span data-stu-id="89502-118">\<aplServerID, aplPeerID\></span></span>  <br/> |<span data-ttu-id="89502-119">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="89502-119">Primary key.</span></span>  <br/> |
|<span data-ttu-id="89502-120">aplServerID</span><span class="sxs-lookup"><span data-stu-id="89502-120">aplServerID</span></span>  <br/> |<span data-ttu-id="89502-121">Clé étrangère avec recherche dans la table tblServerIdentity. serverID.</span><span class="sxs-lookup"><span data-stu-id="89502-121">Foreign key with lookup in tblServerIdentity.serverID table.</span></span>  <br/> |
|<span data-ttu-id="89502-122">aplPeerID</span><span class="sxs-lookup"><span data-stu-id="89502-122">aplPeerID</span></span>  <br/> |<span data-ttu-id="89502-123">Clé étrangère avec recherche dans la table tblServerIdentity. serverID.</span><span class="sxs-lookup"><span data-stu-id="89502-123">Foreign key with lookup in tblServerIdentity.serverID table.</span></span>  <br/> |
   

