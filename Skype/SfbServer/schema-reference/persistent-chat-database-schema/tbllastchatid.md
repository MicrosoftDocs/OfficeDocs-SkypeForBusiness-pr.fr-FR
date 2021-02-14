---
title: tblLastChatId
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
ms.assetid: 17a4ffbe-cca9-4ec5-ae46-38a15274889a
description: tblLastChatId contient le dernier ID de conversation généré (et utilisé dans la table tblChat) pour chaque utilisateur.
ms.openlocfilehash: 80664d6b296fce9b4909674f9d21b1aa13285826
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816004"
---
# <a name="tbllastchatid"></a><span data-ttu-id="22461-103">tblLastChatId</span><span class="sxs-lookup"><span data-stu-id="22461-103">tblLastChatId</span></span>
 
<span data-ttu-id="22461-104">tblLastChatId contient le dernier ID de conversation généré (et utilisé dans la table tblChat) pour chaque utilisateur.</span><span class="sxs-lookup"><span data-stu-id="22461-104">tblLastChatId contains the last chat ID that was generated (and used in the tblChat table) for each user.</span></span>
  
<span data-ttu-id="22461-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="22461-105">**Columns**</span></span>

|<span data-ttu-id="22461-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="22461-106">**Column**</span></span>|<span data-ttu-id="22461-107">**Type (Type)**</span><span class="sxs-lookup"><span data-stu-id="22461-107">**Type**</span></span>|<span data-ttu-id="22461-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="22461-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="22461-109">nodeID</span><span class="sxs-lookup"><span data-stu-id="22461-109">nodeID</span></span>  <br/> |<span data-ttu-id="22461-110">int, non null</span><span class="sxs-lookup"><span data-stu-id="22461-110">int, not null</span></span>  <br/> |<span data-ttu-id="22461-111">ID de nœud (type de salle de conversation seulement).</span><span class="sxs-lookup"><span data-stu-id="22461-111">Node ID (chat room-type only).</span></span>  <br/> |
|<span data-ttu-id="22461-112">lastChatID</span><span class="sxs-lookup"><span data-stu-id="22461-112">lastChatID</span></span>  <br/> |<span data-ttu-id="22461-113">bigint, non null</span><span class="sxs-lookup"><span data-stu-id="22461-113">bigint, not null</span></span>  <br/> |<span data-ttu-id="22461-114">ID de conversation le plus récemment utilisé.</span><span class="sxs-lookup"><span data-stu-id="22461-114">Last used chat ID.</span></span>  <br/> |
   
<span data-ttu-id="22461-115">**Keys**</span><span class="sxs-lookup"><span data-stu-id="22461-115">**Keys**</span></span>

|<span data-ttu-id="22461-116">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="22461-116">**Column**</span></span>|<span data-ttu-id="22461-117">**Description**</span><span class="sxs-lookup"><span data-stu-id="22461-117">**Description**</span></span>|
|:-----|:-----|
|\<nodeID, lastChatID\>  <br/> |<span data-ttu-id="22461-118">Clé principale (nodeID est suffisant pour le traitement).</span><span class="sxs-lookup"><span data-stu-id="22461-118">Primary key (just nodeID is sufficient for processing).</span></span>  <br/> |
|<span data-ttu-id="22461-119">nodeID</span><span class="sxs-lookup"><span data-stu-id="22461-119">nodeID</span></span>  <br/> |<span data-ttu-id="22461-120">Clé étrangère avec recherche dans la table tblNode.nodeID.</span><span class="sxs-lookup"><span data-stu-id="22461-120">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="22461-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="22461-121">See also</span></span>

[<span data-ttu-id="22461-122">tblChat</span><span class="sxs-lookup"><span data-stu-id="22461-122">tblChat</span></span>](tblchat.md)
