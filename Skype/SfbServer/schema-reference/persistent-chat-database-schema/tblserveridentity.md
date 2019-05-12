---
title: tblServerIdentity
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5411c9bc-b0b3-41fc-8b7e-fa71cccd770b
description: tblServerIdentity contient les serveurs de conversation actifs dans le pool de serveurs de conversation permanente.
ms.openlocfilehash: d780c2153b2e7f9f1ed5aad20217228e44f29504
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33924807"
---
# <a name="tblserveridentity"></a><span data-ttu-id="1dfa8-103">tblServerIdentity</span><span class="sxs-lookup"><span data-stu-id="1dfa8-103">tblServerIdentity</span></span>
 
<span data-ttu-id="1dfa8-104">tblServerIdentity contient les serveurs de conversation actifs dans le pool de serveurs de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="1dfa8-104">tblServerIdentity contains the active chat servers in the Persistent Chat Server pool.</span></span>
  
<span data-ttu-id="1dfa8-105">**Colonnes**</span><span class="sxs-lookup"><span data-stu-id="1dfa8-105">**Columns**</span></span>

|<span data-ttu-id="1dfa8-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="1dfa8-106">**Column**</span></span>|<span data-ttu-id="1dfa8-107">**Type**</span><span class="sxs-lookup"><span data-stu-id="1dfa8-107">**Type**</span></span>|<span data-ttu-id="1dfa8-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="1dfa8-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1dfa8-109">serverID</span><span class="sxs-lookup"><span data-stu-id="1dfa8-109">serverID</span></span>  <br/> |<span data-ttu-id="1dfa8-110">int, non null</span><span class="sxs-lookup"><span data-stu-id="1dfa8-110">int, not null</span></span>  <br/> |<span data-ttu-id="1dfa8-111">ID du serveur.</span><span class="sxs-lookup"><span data-stu-id="1dfa8-111">Server ID.</span></span> <span data-ttu-id="1dfa8-112">Correspond à l’ID de l’instance du magasin Central de gestion.</span><span class="sxs-lookup"><span data-stu-id="1dfa8-112">Corresponds to the instance ID from Central Management store.</span></span>  <br/> |
|<span data-ttu-id="1dfa8-113">serverAddress</span><span class="sxs-lookup"><span data-stu-id="1dfa8-113">serverAddress</span></span>  <br/> |<span data-ttu-id="1dfa8-114">nvarchar (256), non null</span><span class="sxs-lookup"><span data-stu-id="1dfa8-114">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="1dfa8-115">Adresse du serveur à l’aide de l’adresse Windows Communication Foundation.</span><span class="sxs-lookup"><span data-stu-id="1dfa8-115">Server address using the Windows Communication Foundation address.</span></span>  <br/> |
|<span data-ttu-id="1dfa8-116">serverLastPingTime</span><span class="sxs-lookup"><span data-stu-id="1dfa8-116">serverLastPingTime</span></span>  <br/> |<span data-ttu-id="1dfa8-117">DateHeure</span><span class="sxs-lookup"><span data-stu-id="1dfa8-117">datetime</span></span>  <br/> |<span data-ttu-id="1dfa8-118">La dernière heure à laquelle le serveur de canal mis à jour cette ligne pour faire la preuve de son exécution.</span><span class="sxs-lookup"><span data-stu-id="1dfa8-118">The latest time that the Channel Server updated this row to give evidence that it is running.</span></span>  <br/> |
   
<span data-ttu-id="1dfa8-119">**Clé**</span><span class="sxs-lookup"><span data-stu-id="1dfa8-119">**Key**</span></span>

|<span data-ttu-id="1dfa8-120">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="1dfa8-120">**Column**</span></span>|<span data-ttu-id="1dfa8-121">**Description**</span><span class="sxs-lookup"><span data-stu-id="1dfa8-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1dfa8-122">serverID</span><span class="sxs-lookup"><span data-stu-id="1dfa8-122">serverID</span></span>  <br/> |<span data-ttu-id="1dfa8-123">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="1dfa8-123">Primary key.</span></span>  <br/> |
   

