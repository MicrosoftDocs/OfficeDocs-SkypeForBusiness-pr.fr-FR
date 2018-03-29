---
title: tblServerIdentity
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5411c9bc-b0b3-41fc-8b7e-fa71cccd770b
description: tblServerIdentity contient les serveurs de discussion active dans le pool de serveur de conversation persistant.
ms.openlocfilehash: 445021bb486d418011ea21dd32c0339e11b4d17a
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="tblserveridentity"></a><span data-ttu-id="e8c89-103">tblServerIdentity</span><span class="sxs-lookup"><span data-stu-id="e8c89-103">tblServerIdentity</span></span>
 
<span data-ttu-id="e8c89-104">tblServerIdentity contient les serveurs de discussion active dans le pool de serveur de conversation persistant.</span><span class="sxs-lookup"><span data-stu-id="e8c89-104">tblServerIdentity contains the active chat servers in the Persistent Chat Server pool.</span></span>
  
<span data-ttu-id="e8c89-105">**Colonnes**</span><span class="sxs-lookup"><span data-stu-id="e8c89-105">**Columns**</span></span>

|<span data-ttu-id="e8c89-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="e8c89-106">**Column**</span></span>|<span data-ttu-id="e8c89-107">**Type de**</span><span class="sxs-lookup"><span data-stu-id="e8c89-107">**Type**</span></span>|<span data-ttu-id="e8c89-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="e8c89-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e8c89-109">serverID</span><span class="sxs-lookup"><span data-stu-id="e8c89-109">serverID</span></span>  <br/> |<span data-ttu-id="e8c89-110">int, non null</span><span class="sxs-lookup"><span data-stu-id="e8c89-110">int, not null</span></span>  <br/> |<span data-ttu-id="e8c89-111">ID du serveur.</span><span class="sxs-lookup"><span data-stu-id="e8c89-111">Server ID.</span></span> <span data-ttu-id="e8c89-112">Correspond à l’ID d’instance du magasin Central de gestion.</span><span class="sxs-lookup"><span data-stu-id="e8c89-112">Corresponds to the instance ID from Central Management store.</span></span>  <br/> |
|<span data-ttu-id="e8c89-113">serverAddress</span><span class="sxs-lookup"><span data-stu-id="e8c89-113">serverAddress</span></span>  <br/> |<span data-ttu-id="e8c89-114">nvarchar (256), non null</span><span class="sxs-lookup"><span data-stu-id="e8c89-114">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="e8c89-115">Adresse du serveur à l’aide de l’adresse de Windows Communication Foundation.</span><span class="sxs-lookup"><span data-stu-id="e8c89-115">Server address using the Windows Communication Foundation address.</span></span>  <br/> |
|<span data-ttu-id="e8c89-116">serverLastPingTime</span><span class="sxs-lookup"><span data-stu-id="e8c89-116">serverLastPingTime</span></span>  <br/> |<span data-ttu-id="e8c89-117">DateHeure</span><span class="sxs-lookup"><span data-stu-id="e8c89-117">datetime</span></span>  <br/> |<span data-ttu-id="e8c89-118">Dernière heure à laquelle le serveur du canal de mise à jour de cette ligne pour apporter la preuve qu’il est en cours d’exécution.</span><span class="sxs-lookup"><span data-stu-id="e8c89-118">The latest time that the Channel Server updated this row to give evidence that it is running.</span></span>  <br/> |
   
<span data-ttu-id="e8c89-119">**Clé**</span><span class="sxs-lookup"><span data-stu-id="e8c89-119">**Key**</span></span>

|<span data-ttu-id="e8c89-120">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="e8c89-120">**Column**</span></span>|<span data-ttu-id="e8c89-121">**Description**</span><span class="sxs-lookup"><span data-stu-id="e8c89-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e8c89-122">serverID</span><span class="sxs-lookup"><span data-stu-id="e8c89-122">serverID</span></span>  <br/> |<span data-ttu-id="e8c89-123">Clé primaire.</span><span class="sxs-lookup"><span data-stu-id="e8c89-123">Primary key.</span></span>  <br/> |
   

