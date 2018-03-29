---
title: tblLastChatId
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 17a4ffbe-cca9-4ec5-ae46-38a15274889a
description: tblLastChatId contient le dernier ID de conversation qui a été généré (et utilisé dans la table tblChat) pour chaque utilisateur.
ms.openlocfilehash: 4a22dc9ba1c2dbe15ae0a24de6e4f347a62deaee
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="tbllastchatid"></a><span data-ttu-id="a4673-103">tblLastChatId</span><span class="sxs-lookup"><span data-stu-id="a4673-103">tblLastChatId</span></span>
 
<span data-ttu-id="a4673-104">tblLastChatId contient le dernier ID de conversation qui a été généré (et utilisé dans la table tblChat) pour chaque utilisateur.</span><span class="sxs-lookup"><span data-stu-id="a4673-104">tblLastChatId contains the last chat ID that was generated (and used in the tblChat table) for each user.</span></span>
  
<span data-ttu-id="a4673-105">**Colonnes**</span><span class="sxs-lookup"><span data-stu-id="a4673-105">**Columns**</span></span>

|<span data-ttu-id="a4673-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="a4673-106">**Column**</span></span>|<span data-ttu-id="a4673-107">**Type de**</span><span class="sxs-lookup"><span data-stu-id="a4673-107">**Type**</span></span>|<span data-ttu-id="a4673-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="a4673-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a4673-109">nodeID</span><span class="sxs-lookup"><span data-stu-id="a4673-109">nodeID</span></span>  <br/> |<span data-ttu-id="a4673-110">int, non null</span><span class="sxs-lookup"><span data-stu-id="a4673-110">int, not null</span></span>  <br/> |<span data-ttu-id="a4673-111">ID de nœud (salle de conversation de type uniquement).</span><span class="sxs-lookup"><span data-stu-id="a4673-111">Node ID (chat room-type only).</span></span>  <br/> |
|<span data-ttu-id="a4673-112">lastChatID</span><span class="sxs-lookup"><span data-stu-id="a4673-112">lastChatID</span></span>  <br/> |<span data-ttu-id="a4673-113">bigint, non null</span><span class="sxs-lookup"><span data-stu-id="a4673-113">bigint, not null</span></span>  <br/> |<span data-ttu-id="a4673-114">Dernier ID de conversation d’utilisés.</span><span class="sxs-lookup"><span data-stu-id="a4673-114">Last used chat ID.</span></span>  <br/> |
   
<span data-ttu-id="a4673-115">**Clés**</span><span class="sxs-lookup"><span data-stu-id="a4673-115">**Keys**</span></span>

|<span data-ttu-id="a4673-116">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="a4673-116">**Column**</span></span>|<span data-ttu-id="a4673-117">**Description**</span><span class="sxs-lookup"><span data-stu-id="a4673-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a4673-118">\<nodeID, lastChatID\></span><span class="sxs-lookup"><span data-stu-id="a4673-118">\<nodeID, lastChatID\></span></span>  <br/> |<span data-ttu-id="a4673-119">Clé primaire (nodeID uniquement est suffisant pour le traitement).</span><span class="sxs-lookup"><span data-stu-id="a4673-119">Primary key (just nodeID is sufficient for processing).</span></span>  <br/> |
|<span data-ttu-id="a4673-120">nodeID</span><span class="sxs-lookup"><span data-stu-id="a4673-120">nodeID</span></span>  <br/> |<span data-ttu-id="a4673-121">Clé étrangère avec la recherche dans la table de tblNode.nodeID.</span><span class="sxs-lookup"><span data-stu-id="a4673-121">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="a4673-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a4673-122">See also</span></span>

#### 

[<span data-ttu-id="a4673-123">tblChat</span><span class="sxs-lookup"><span data-stu-id="a4673-123">tblChat</span></span>](tblchat.md)

