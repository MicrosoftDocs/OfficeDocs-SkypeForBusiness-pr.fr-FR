---
title: Vue de ClientVersions
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: caf7678f-83a0-46c8-83cc-fee4c3991f52
description: La vue ClientVersions stocke des informations sur les différents types de clients et les versions qui ont participé aux sessions enregistrées dans la base de données. Chaque enregistrement dans la vue représente une version du client. Cette vue a été introduite dans Microsoft Lync Server 2013.
ms.openlocfilehash: 0906e35d0912684c9aeb169017b5df0a53202c50
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="clientversions-view"></a><span data-ttu-id="32139-105">Vue de ClientVersions</span><span class="sxs-lookup"><span data-stu-id="32139-105">ClientVersions view</span></span>
 
<span data-ttu-id="32139-106">La vue ClientVersions stocke des informations sur les différents types de clients et les versions qui ont participé aux sessions enregistrées dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="32139-106">The ClientVersions view stores information about the various client types and versions that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="32139-107">Chaque enregistrement dans la vue représente une version du client.</span><span class="sxs-lookup"><span data-stu-id="32139-107">Each record in the view represents one client version.</span></span> <span data-ttu-id="32139-108">Cette vue a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="32139-108">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="32139-109">Il peuvent exister plusieurs enregistrements pour certaines colonnes.</span><span class="sxs-lookup"><span data-stu-id="32139-109">There may be multiple records for certain columns.</span></span> 
  
|<span data-ttu-id="32139-110">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="32139-110">**Column**</span></span>|<span data-ttu-id="32139-111">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="32139-111">**Data Type**</span></span>|<span data-ttu-id="32139-112">**Détails**</span><span class="sxs-lookup"><span data-stu-id="32139-112">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="32139-113">**Valeur de VersionId**</span><span class="sxs-lookup"><span data-stu-id="32139-113">**VersionId**</span></span> <br/> |<span data-ttu-id="32139-114">int</span><span class="sxs-lookup"><span data-stu-id="32139-114">int</span></span>  <br/> |<span data-ttu-id="32139-115">Numéro unique identifiant le type de client et de la version.</span><span class="sxs-lookup"><span data-stu-id="32139-115">Unique number identifying this client type and version.</span></span>  <br/> |
|<span data-ttu-id="32139-116">**Version**</span><span class="sxs-lookup"><span data-stu-id="32139-116">**Version**</span></span> <br/> |<span data-ttu-id="32139-117">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="32139-117">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="32139-118">Représente l’agent utilisateur.</span><span class="sxs-lookup"><span data-stu-id="32139-118">Represents the user agent.</span></span>  <br/> |
|<span data-ttu-id="32139-119">**TypeClient**</span><span class="sxs-lookup"><span data-stu-id="32139-119">**ClientType**</span></span> <br/> |<span data-ttu-id="32139-120">int</span><span class="sxs-lookup"><span data-stu-id="32139-120">int</span></span>  <br/> |<span data-ttu-id="32139-121">Type de client.</span><span class="sxs-lookup"><span data-stu-id="32139-121">Type of client.</span></span>  <br/> |
|<span data-ttu-id="32139-122">**ClientCategory**</span><span class="sxs-lookup"><span data-stu-id="32139-122">**ClientCategory**</span></span> <br/> |<span data-ttu-id="32139-123">nvarchar(64)</span><span class="sxs-lookup"><span data-stu-id="32139-123">nvarchar(64)</span></span>  <br/> |<span data-ttu-id="32139-124">Catégorie à laquelle appartient le client.</span><span class="sxs-lookup"><span data-stu-id="32139-124">Category that the client belongs to.</span></span> <span data-ttu-id="32139-125">Par exemple, le client Conferencing_Attendant_1.0 appartient à la TCHA ClientCategory.</span><span class="sxs-lookup"><span data-stu-id="32139-125">For example, the client Conferencing_Attendant_1.0 belongs to the ClientCategory CAA.</span></span>  <br/> |
   

