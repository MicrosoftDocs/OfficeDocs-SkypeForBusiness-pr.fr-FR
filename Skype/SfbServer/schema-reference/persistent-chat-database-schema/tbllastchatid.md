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
description: tblLastChatId contient le dernier ID de conversation généré (et utilisé dans la table tblChat) pour chaque utilisateur.
ms.openlocfilehash: dc25eb68ee1b4069ba54133548f743ca45b73e16
ms.sourcegitcommit: b14cfca231b618ec28cf9f4efe11cb3e8aceb34b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/19/2018
ms.locfileid: "19505088"
---
# <a name="tbllastchatid"></a><span data-ttu-id="d52f0-103">tblLastChatId</span><span class="sxs-lookup"><span data-stu-id="d52f0-103">tblLastChatId</span></span>
 
<span data-ttu-id="d52f0-104">tblLastChatId contient le dernier ID de conversation généré (et utilisé dans la table tblChat) pour chaque utilisateur.</span><span class="sxs-lookup"><span data-stu-id="d52f0-104">tblLastChatId contains the last chat ID that was generated (and used in the tblChat table) for each user.</span></span>
  
<span data-ttu-id="d52f0-105">**Colonnes**</span><span class="sxs-lookup"><span data-stu-id="d52f0-105">**Columns**</span></span>

|<span data-ttu-id="d52f0-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="d52f0-106">**Column**</span></span>|<span data-ttu-id="d52f0-107">**Type**</span><span class="sxs-lookup"><span data-stu-id="d52f0-107">**Type**</span></span>|<span data-ttu-id="d52f0-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="d52f0-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d52f0-109">nodeID</span><span class="sxs-lookup"><span data-stu-id="d52f0-109">nodeID</span></span>  <br/> |<span data-ttu-id="d52f0-110">int, non null</span><span class="sxs-lookup"><span data-stu-id="d52f0-110">int, not null</span></span>  <br/> |<span data-ttu-id="d52f0-111">ID de nœud (salle de conversation de type uniquement).</span><span class="sxs-lookup"><span data-stu-id="d52f0-111">Node ID (chat room-type only).</span></span>  <br/> |
|<span data-ttu-id="d52f0-112">lastChatID</span><span class="sxs-lookup"><span data-stu-id="d52f0-112">lastChatID</span></span>  <br/> |<span data-ttu-id="d52f0-113">bigint, non null</span><span class="sxs-lookup"><span data-stu-id="d52f0-113">bigint, not null</span></span>  <br/> |<span data-ttu-id="d52f0-114">Dernier ID de conversation utilisé.</span><span class="sxs-lookup"><span data-stu-id="d52f0-114">Last used chat ID.</span></span>  <br/> |
   
<span data-ttu-id="d52f0-115">**Clés**</span><span class="sxs-lookup"><span data-stu-id="d52f0-115">**Keys**</span></span>

|<span data-ttu-id="d52f0-116">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="d52f0-116">**Column**</span></span>|<span data-ttu-id="d52f0-117">**Description**</span><span class="sxs-lookup"><span data-stu-id="d52f0-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d52f0-118">\<nodeID, lastChatID\></span><span class="sxs-lookup"><span data-stu-id="d52f0-118">\<nodeID, lastChatID\></span></span>  <br/> |<span data-ttu-id="d52f0-119">Clé primaire (nodeID est suffisant pour le traitement).</span><span class="sxs-lookup"><span data-stu-id="d52f0-119">Primary key (just nodeID is sufficient for processing).</span></span>  <br/> |
|<span data-ttu-id="d52f0-120">nodeID</span><span class="sxs-lookup"><span data-stu-id="d52f0-120">nodeID</span></span>  <br/> |<span data-ttu-id="d52f0-121">Clé étrangère avec recherche dans la table tblNode.nodeID.</span><span class="sxs-lookup"><span data-stu-id="d52f0-121">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="d52f0-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d52f0-122">See also</span></span>

[<span data-ttu-id="d52f0-123">tblChat</span><span class="sxs-lookup"><span data-stu-id="d52f0-123">tblChat</span></span>](tblchat.md)