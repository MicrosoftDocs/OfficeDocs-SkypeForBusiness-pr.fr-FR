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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 17a4ffbe-cca9-4ec5-ae46-38a15274889a
description: tblLastChatId contient le dernier ID de chat qui a été généré (et utilisé dans la table tblChat) pour chaque utilisateur.
ms.openlocfilehash: 95498f077948e1b400d0a370762c121def703e8c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814582"
---
# <a name="tbllastchatid"></a><span data-ttu-id="cb8a1-103">tblLastChatId</span><span class="sxs-lookup"><span data-stu-id="cb8a1-103">tblLastChatId</span></span>
 
<span data-ttu-id="cb8a1-104">tblLastChatId contient le dernier ID de chat qui a été généré (et utilisé dans la table tblChat) pour chaque utilisateur.</span><span class="sxs-lookup"><span data-stu-id="cb8a1-104">tblLastChatId contains the last chat ID that was generated (and used in the tblChat table) for each user.</span></span>
  
<span data-ttu-id="cb8a1-105">**Celles**</span><span class="sxs-lookup"><span data-stu-id="cb8a1-105">**Columns**</span></span>

|<span data-ttu-id="cb8a1-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="cb8a1-106">**Column**</span></span>|<span data-ttu-id="cb8a1-107">**Type**</span><span class="sxs-lookup"><span data-stu-id="cb8a1-107">**Type**</span></span>|<span data-ttu-id="cb8a1-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="cb8a1-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="cb8a1-109">ID</span><span class="sxs-lookup"><span data-stu-id="cb8a1-109">nodeID</span></span>  <br/> |<span data-ttu-id="cb8a1-110">ent, non null</span><span class="sxs-lookup"><span data-stu-id="cb8a1-110">int, not null</span></span>  <br/> |<span data-ttu-id="cb8a1-111">ID de nœud (salle de conversation-type uniquement).</span><span class="sxs-lookup"><span data-stu-id="cb8a1-111">Node ID (chat room-type only).</span></span>  <br/> |
|<span data-ttu-id="cb8a1-112">lastChatID</span><span class="sxs-lookup"><span data-stu-id="cb8a1-112">lastChatID</span></span>  <br/> |<span data-ttu-id="cb8a1-113">bigint, pas null</span><span class="sxs-lookup"><span data-stu-id="cb8a1-113">bigint, not null</span></span>  <br/> |<span data-ttu-id="cb8a1-114">Dernier ID de conversation utilisé.</span><span class="sxs-lookup"><span data-stu-id="cb8a1-114">Last used chat ID.</span></span>  <br/> |
   
<span data-ttu-id="cb8a1-115">**Permettent**</span><span class="sxs-lookup"><span data-stu-id="cb8a1-115">**Keys**</span></span>

|<span data-ttu-id="cb8a1-116">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="cb8a1-116">**Column**</span></span>|<span data-ttu-id="cb8a1-117">**Description**</span><span class="sxs-lookup"><span data-stu-id="cb8a1-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="cb8a1-118">\<nodeID, lastChatID\></span><span class="sxs-lookup"><span data-stu-id="cb8a1-118">\<nodeID, lastChatID\></span></span>  <br/> |<span data-ttu-id="cb8a1-119">Clé primaire (uniquement nodeID est suffisante pour le traitement).</span><span class="sxs-lookup"><span data-stu-id="cb8a1-119">Primary key (just nodeID is sufficient for processing).</span></span>  <br/> |
|<span data-ttu-id="cb8a1-120">ID</span><span class="sxs-lookup"><span data-stu-id="cb8a1-120">nodeID</span></span>  <br/> |<span data-ttu-id="cb8a1-121">Clé étrangère avec recherche dans la table tblNode. nodeID.</span><span class="sxs-lookup"><span data-stu-id="cb8a1-121">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="cb8a1-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="cb8a1-122">See also</span></span>

[<span data-ttu-id="cb8a1-123">tblChat</span><span class="sxs-lookup"><span data-stu-id="cb8a1-123">tblChat</span></span>](tblchat.md)
