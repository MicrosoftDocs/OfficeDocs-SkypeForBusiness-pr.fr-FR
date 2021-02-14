---
title: Affichage ClientVersions
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
ms.assetid: caf7678f-83a0-46c8-83cc-fee4c3991f52
description: L’affichage ClientVersions stocke des informations sur les différents types et versions de clients qui ont participé à des sessions enregistrées dans la base de données. Chaque enregistrement de l’affichage représente une version du client. Cette vue a été introduite dans Microsoft Lync Server 2013.
ms.openlocfilehash: b38e00c0a860b94b72c7d0dc396ff44357c2741f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813354"
---
# <a name="clientversions-view"></a><span data-ttu-id="801d4-105">Affichage ClientVersions</span><span class="sxs-lookup"><span data-stu-id="801d4-105">ClientVersions view</span></span>
 
<span data-ttu-id="801d4-106">L’affichage ClientVersions stocke des informations sur les différents types et versions de clients qui ont participé à des sessions enregistrées dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="801d4-106">The ClientVersions view stores information about the various client types and versions that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="801d4-107">Chaque enregistrement de l’affichage représente une version du client.</span><span class="sxs-lookup"><span data-stu-id="801d4-107">Each record in the view represents one client version.</span></span> <span data-ttu-id="801d4-108">Cette vue a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="801d4-108">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="801d4-109">Il peut y avoir plusieurs enregistrements pour certaines colonnes.</span><span class="sxs-lookup"><span data-stu-id="801d4-109">There may be multiple records for certain columns.</span></span> 
  
|<span data-ttu-id="801d4-110">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="801d4-110">**Column**</span></span>|<span data-ttu-id="801d4-111">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="801d4-111">**Data Type**</span></span>|<span data-ttu-id="801d4-112">**Détails**</span><span class="sxs-lookup"><span data-stu-id="801d4-112">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="801d4-113">**VersionId**</span><span class="sxs-lookup"><span data-stu-id="801d4-113">**VersionId**</span></span> <br/> |<span data-ttu-id="801d4-114">int</span><span class="sxs-lookup"><span data-stu-id="801d4-114">int</span></span>  <br/> |<span data-ttu-id="801d4-115">Numéro unique identifiant le type et la version de ce client.</span><span class="sxs-lookup"><span data-stu-id="801d4-115">Unique number identifying this client type and version.</span></span>  <br/> |
|<span data-ttu-id="801d4-116">**Version**</span><span class="sxs-lookup"><span data-stu-id="801d4-116">**Version**</span></span> <br/> |<span data-ttu-id="801d4-117">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="801d4-117">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="801d4-118">Représente l’agent utilisateur.</span><span class="sxs-lookup"><span data-stu-id="801d4-118">Represents the user agent.</span></span>  <br/> |
|<span data-ttu-id="801d4-119">**ClientType**</span><span class="sxs-lookup"><span data-stu-id="801d4-119">**ClientType**</span></span> <br/> |<span data-ttu-id="801d4-120">int</span><span class="sxs-lookup"><span data-stu-id="801d4-120">int</span></span>  <br/> |<span data-ttu-id="801d4-121">Type de client.</span><span class="sxs-lookup"><span data-stu-id="801d4-121">Type of client.</span></span>  <br/> |
|<span data-ttu-id="801d4-122">**ClientCategory**</span><span class="sxs-lookup"><span data-stu-id="801d4-122">**ClientCategory**</span></span> <br/> |<span data-ttu-id="801d4-123">nvarchar(64)</span><span class="sxs-lookup"><span data-stu-id="801d4-123">nvarchar(64)</span></span>  <br/> |<span data-ttu-id="801d4-124">Catégorie à qui appartient le client.</span><span class="sxs-lookup"><span data-stu-id="801d4-124">Category that the client belongs to.</span></span> <span data-ttu-id="801d4-125">Par exemple, le client Conferencing_Attendant_1.0 appartient à l’ACA ClientCategory.</span><span class="sxs-lookup"><span data-stu-id="801d4-125">For example, the client Conferencing_Attendant_1.0 belongs to the ClientCategory CAA.</span></span>  <br/> |
   

