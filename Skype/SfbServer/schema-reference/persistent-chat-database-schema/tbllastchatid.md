---
title: tblLastChatId
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 17a4ffbe-cca9-4ec5-ae46-38a15274889a
description: tblLastChatId contient le dernier ID de conversation généré (et utilisé dans la table tblChat) pour chaque utilisateur.
ms.openlocfilehash: 9d19c6c873660683ff526eb144d74b6e8752bf80
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929965"
---
# <a name="tbllastchatid"></a><span data-ttu-id="0e05a-103">tblLastChatId</span><span class="sxs-lookup"><span data-stu-id="0e05a-103">tblLastChatId</span></span>
 
<span data-ttu-id="0e05a-104">tblLastChatId contient le dernier ID de conversation généré (et utilisé dans la table tblChat) pour chaque utilisateur.</span><span class="sxs-lookup"><span data-stu-id="0e05a-104">tblLastChatId contains the last chat ID that was generated (and used in the tblChat table) for each user.</span></span>
  
<span data-ttu-id="0e05a-105">**Colonnes**</span><span class="sxs-lookup"><span data-stu-id="0e05a-105">**Columns**</span></span>

|<span data-ttu-id="0e05a-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="0e05a-106">**Column**</span></span>|<span data-ttu-id="0e05a-107">**Type**</span><span class="sxs-lookup"><span data-stu-id="0e05a-107">**Type**</span></span>|<span data-ttu-id="0e05a-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="0e05a-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="0e05a-109">nodeID</span><span class="sxs-lookup"><span data-stu-id="0e05a-109">nodeID</span></span>  <br/> |<span data-ttu-id="0e05a-110">int, non null</span><span class="sxs-lookup"><span data-stu-id="0e05a-110">int, not null</span></span>  <br/> |<span data-ttu-id="0e05a-111">ID de nœud (salle de conversation de type uniquement).</span><span class="sxs-lookup"><span data-stu-id="0e05a-111">Node ID (chat room-type only).</span></span>  <br/> |
|<span data-ttu-id="0e05a-112">lastChatID</span><span class="sxs-lookup"><span data-stu-id="0e05a-112">lastChatID</span></span>  <br/> |<span data-ttu-id="0e05a-113">bigint, non null</span><span class="sxs-lookup"><span data-stu-id="0e05a-113">bigint, not null</span></span>  <br/> |<span data-ttu-id="0e05a-114">Dernier ID de conversation utilisé.</span><span class="sxs-lookup"><span data-stu-id="0e05a-114">Last used chat ID.</span></span>  <br/> |
   
<span data-ttu-id="0e05a-115">**Clés**</span><span class="sxs-lookup"><span data-stu-id="0e05a-115">**Keys**</span></span>

|<span data-ttu-id="0e05a-116">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="0e05a-116">**Column**</span></span>|<span data-ttu-id="0e05a-117">**Description**</span><span class="sxs-lookup"><span data-stu-id="0e05a-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="0e05a-118">\<nodeID, lastChatID\></span><span class="sxs-lookup"><span data-stu-id="0e05a-118">\<nodeID, lastChatID\></span></span>  <br/> |<span data-ttu-id="0e05a-119">Clé primaire (nodeID est suffisant pour le traitement).</span><span class="sxs-lookup"><span data-stu-id="0e05a-119">Primary key (just nodeID is sufficient for processing).</span></span>  <br/> |
|<span data-ttu-id="0e05a-120">nodeID</span><span class="sxs-lookup"><span data-stu-id="0e05a-120">nodeID</span></span>  <br/> |<span data-ttu-id="0e05a-121">Clé étrangère avec recherche dans la table tblNode.nodeID.</span><span class="sxs-lookup"><span data-stu-id="0e05a-121">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="0e05a-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0e05a-122">See also</span></span>

[<span data-ttu-id="0e05a-123">tblChat</span><span class="sxs-lookup"><span data-stu-id="0e05a-123">tblChat</span></span>](tblchat.md)
