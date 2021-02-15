---
title: tblServerIdentity
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
ms.assetid: 5411c9bc-b0b3-41fc-8b7e-fa71cccd770b
description: tblServerIdentity contient les serveurs de conversation actifs dans le pool de serveurs de conversation permanente.
ms.openlocfilehash: 7fa8c1b804432b3a9368785682f45e9ce8d7898e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831494"
---
# <a name="tblserveridentity"></a><span data-ttu-id="9262f-103">tblServerIdentity</span><span class="sxs-lookup"><span data-stu-id="9262f-103">tblServerIdentity</span></span>
 
<span data-ttu-id="9262f-104">tblServerIdentity contient les serveurs de conversation actifs dans le pool de serveurs de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="9262f-104">tblServerIdentity contains the active chat servers in the Persistent Chat Server pool.</span></span>
  
<span data-ttu-id="9262f-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="9262f-105">**Columns**</span></span>

|<span data-ttu-id="9262f-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="9262f-106">**Column**</span></span>|<span data-ttu-id="9262f-107">**Type (Type)**</span><span class="sxs-lookup"><span data-stu-id="9262f-107">**Type**</span></span>|<span data-ttu-id="9262f-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="9262f-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="9262f-109">serverID</span><span class="sxs-lookup"><span data-stu-id="9262f-109">serverID</span></span>  <br/> |<span data-ttu-id="9262f-110">int, non null</span><span class="sxs-lookup"><span data-stu-id="9262f-110">int, not null</span></span>  <br/> |<span data-ttu-id="9262f-111">ID de serveur.</span><span class="sxs-lookup"><span data-stu-id="9262f-111">Server ID.</span></span> <span data-ttu-id="9262f-112">Correspond à l’ID d’instance du magasin central de gestion.</span><span class="sxs-lookup"><span data-stu-id="9262f-112">Corresponds to the instance ID from Central Management store.</span></span>  <br/> |
|<span data-ttu-id="9262f-113">serverAddress</span><span class="sxs-lookup"><span data-stu-id="9262f-113">serverAddress</span></span>  <br/> |<span data-ttu-id="9262f-114">nvarchar (256), non null</span><span class="sxs-lookup"><span data-stu-id="9262f-114">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="9262f-115">Adresse de serveur utilisant l’adresse WCF (Windows Communication Foundation).</span><span class="sxs-lookup"><span data-stu-id="9262f-115">Server address using the Windows Communication Foundation address.</span></span>  <br/> |
|<span data-ttu-id="9262f-116">serverLastPingTime</span><span class="sxs-lookup"><span data-stu-id="9262f-116">serverLastPingTime</span></span>  <br/> |<span data-ttu-id="9262f-117">DateHeure</span><span class="sxs-lookup"><span data-stu-id="9262f-117">datetime</span></span>  <br/> |<span data-ttu-id="9262f-118">Dernière fois où le serveur de canal a mis à jour cette ligne pour faire la preuve de son exécution.</span><span class="sxs-lookup"><span data-stu-id="9262f-118">The latest time that the Channel Server updated this row to give evidence that it is running.</span></span>  <br/> |
   
<span data-ttu-id="9262f-119">**Clé**</span><span class="sxs-lookup"><span data-stu-id="9262f-119">**Key**</span></span>

|<span data-ttu-id="9262f-120">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="9262f-120">**Column**</span></span>|<span data-ttu-id="9262f-121">**Description**</span><span class="sxs-lookup"><span data-stu-id="9262f-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="9262f-122">serverID</span><span class="sxs-lookup"><span data-stu-id="9262f-122">serverID</span></span>  <br/> |<span data-ttu-id="9262f-123">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="9262f-123">Primary key.</span></span>  <br/> |
   

