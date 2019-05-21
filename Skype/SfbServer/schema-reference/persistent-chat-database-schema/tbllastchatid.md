---
title: tblLastChatId
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 17a4ffbe-cca9-4ec5-ae46-38a15274889a
description: tblLastChatId contient le dernier ID de chat qui a été généré (et utilisé dans la table tblChat) pour chaque utilisateur.
ms.openlocfilehash: f14d8090fd3252d88ef747de93a987f51870a63b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295397"
---
# <a name="tbllastchatid"></a><span data-ttu-id="025c0-103">tblLastChatId</span><span class="sxs-lookup"><span data-stu-id="025c0-103">tblLastChatId</span></span>
 
<span data-ttu-id="025c0-104">tblLastChatId contient le dernier ID de chat qui a été généré (et utilisé dans la table tblChat) pour chaque utilisateur.</span><span class="sxs-lookup"><span data-stu-id="025c0-104">tblLastChatId contains the last chat ID that was generated (and used in the tblChat table) for each user.</span></span>
  
<span data-ttu-id="025c0-105">**Celles**</span><span class="sxs-lookup"><span data-stu-id="025c0-105">**Columns**</span></span>

|<span data-ttu-id="025c0-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="025c0-106">**Column**</span></span>|<span data-ttu-id="025c0-107">**Type**</span><span class="sxs-lookup"><span data-stu-id="025c0-107">**Type**</span></span>|<span data-ttu-id="025c0-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="025c0-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="025c0-109">ID</span><span class="sxs-lookup"><span data-stu-id="025c0-109">nodeID</span></span>  <br/> |<span data-ttu-id="025c0-110">ent, non null</span><span class="sxs-lookup"><span data-stu-id="025c0-110">int, not null</span></span>  <br/> |<span data-ttu-id="025c0-111">ID de nœud (salle de conversation-type uniquement).</span><span class="sxs-lookup"><span data-stu-id="025c0-111">Node ID (chat room-type only).</span></span>  <br/> |
|<span data-ttu-id="025c0-112">lastChatID</span><span class="sxs-lookup"><span data-stu-id="025c0-112">lastChatID</span></span>  <br/> |<span data-ttu-id="025c0-113">bigint, pas null</span><span class="sxs-lookup"><span data-stu-id="025c0-113">bigint, not null</span></span>  <br/> |<span data-ttu-id="025c0-114">Dernier ID de conversation utilisé.</span><span class="sxs-lookup"><span data-stu-id="025c0-114">Last used chat ID.</span></span>  <br/> |
   
<span data-ttu-id="025c0-115">**Permettent**</span><span class="sxs-lookup"><span data-stu-id="025c0-115">**Keys**</span></span>

|<span data-ttu-id="025c0-116">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="025c0-116">**Column**</span></span>|<span data-ttu-id="025c0-117">**Description**</span><span class="sxs-lookup"><span data-stu-id="025c0-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="025c0-118">\<nodeID, lastChatID\></span><span class="sxs-lookup"><span data-stu-id="025c0-118">\<nodeID, lastChatID\></span></span>  <br/> |<span data-ttu-id="025c0-119">Clé primaire (uniquement nodeID est suffisante pour le traitement).</span><span class="sxs-lookup"><span data-stu-id="025c0-119">Primary key (just nodeID is sufficient for processing).</span></span>  <br/> |
|<span data-ttu-id="025c0-120">ID</span><span class="sxs-lookup"><span data-stu-id="025c0-120">nodeID</span></span>  <br/> |<span data-ttu-id="025c0-121">Clé étrangère avec recherche dans la table tblNode. nodeID.</span><span class="sxs-lookup"><span data-stu-id="025c0-121">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="025c0-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="025c0-122">See also</span></span>

[<span data-ttu-id="025c0-123">tblChat</span><span class="sxs-lookup"><span data-stu-id="025c0-123">tblChat</span></span>](tblchat.md)
