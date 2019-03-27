---
title: tblServerIdentity
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5411c9bc-b0b3-41fc-8b7e-fa71cccd770b
description: tblServerIdentity contient les serveurs de conversation actifs dans le pool de serveurs de conversation permanente.
ms.openlocfilehash: 1f9455e4c35a3bc6061c1d44ad10cbd4778c6c1f
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30899525"
---
# <a name="tblserveridentity"></a><span data-ttu-id="0c63d-103">tblServerIdentity</span><span class="sxs-lookup"><span data-stu-id="0c63d-103">tblServerIdentity</span></span>
 
<span data-ttu-id="0c63d-104">tblServerIdentity contient les serveurs de conversation actifs dans le pool de serveurs de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="0c63d-104">tblServerIdentity contains the active chat servers in the Persistent Chat Server pool.</span></span>
  
<span data-ttu-id="0c63d-105">**Colonnes**</span><span class="sxs-lookup"><span data-stu-id="0c63d-105">**Columns**</span></span>

|<span data-ttu-id="0c63d-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="0c63d-106">**Column**</span></span>|<span data-ttu-id="0c63d-107">**Type**</span><span class="sxs-lookup"><span data-stu-id="0c63d-107">**Type**</span></span>|<span data-ttu-id="0c63d-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="0c63d-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="0c63d-109">serverID</span><span class="sxs-lookup"><span data-stu-id="0c63d-109">serverID</span></span>  <br/> |<span data-ttu-id="0c63d-110">int, non null</span><span class="sxs-lookup"><span data-stu-id="0c63d-110">int, not null</span></span>  <br/> |<span data-ttu-id="0c63d-111">ID du serveur.</span><span class="sxs-lookup"><span data-stu-id="0c63d-111">Server ID.</span></span> <span data-ttu-id="0c63d-112">Correspond à l’ID de l’instance du magasin Central de gestion.</span><span class="sxs-lookup"><span data-stu-id="0c63d-112">Corresponds to the instance ID from Central Management store.</span></span>  <br/> |
|<span data-ttu-id="0c63d-113">serverAddress</span><span class="sxs-lookup"><span data-stu-id="0c63d-113">serverAddress</span></span>  <br/> |<span data-ttu-id="0c63d-114">nvarchar (256), non null</span><span class="sxs-lookup"><span data-stu-id="0c63d-114">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="0c63d-115">Adresse du serveur à l’aide de l’adresse Windows Communication Foundation.</span><span class="sxs-lookup"><span data-stu-id="0c63d-115">Server address using the Windows Communication Foundation address.</span></span>  <br/> |
|<span data-ttu-id="0c63d-116">serverLastPingTime</span><span class="sxs-lookup"><span data-stu-id="0c63d-116">serverLastPingTime</span></span>  <br/> |<span data-ttu-id="0c63d-117">DateHeure</span><span class="sxs-lookup"><span data-stu-id="0c63d-117">datetime</span></span>  <br/> |<span data-ttu-id="0c63d-118">La dernière heure à laquelle le serveur de canal mis à jour cette ligne pour faire la preuve de son exécution.</span><span class="sxs-lookup"><span data-stu-id="0c63d-118">The latest time that the Channel Server updated this row to give evidence that it is running.</span></span>  <br/> |
   
<span data-ttu-id="0c63d-119">**Clé**</span><span class="sxs-lookup"><span data-stu-id="0c63d-119">**Key**</span></span>

|<span data-ttu-id="0c63d-120">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="0c63d-120">**Column**</span></span>|<span data-ttu-id="0c63d-121">**Description**</span><span class="sxs-lookup"><span data-stu-id="0c63d-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="0c63d-122">serverID</span><span class="sxs-lookup"><span data-stu-id="0c63d-122">serverID</span></span>  <br/> |<span data-ttu-id="0c63d-123">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="0c63d-123">Primary key.</span></span>  <br/> |
   

