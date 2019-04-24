---
title: Vue clientversions
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: caf7678f-83a0-46c8-83cc-fee4c3991f52
description: La vue ClientVersions stocke des informations sur les différents types de clients et les versions qui ont participé à des sessions enregistrées dans la base de données. Chaque enregistrement dans la vue représente une version du client. Cet affichage a été introduit dans Microsoft Lync Server 2013.
ms.openlocfilehash: abf1436a2c3309e95bec8371b586c017e11b816d
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213395"
---
# <a name="clientversions-view"></a><span data-ttu-id="cb0e3-105">Vue clientversions</span><span class="sxs-lookup"><span data-stu-id="cb0e3-105">ClientVersions view</span></span>
 
<span data-ttu-id="cb0e3-106">La vue ClientVersions stocke des informations sur les différents types de clients et les versions qui ont participé à des sessions enregistrées dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="cb0e3-106">The ClientVersions view stores information about the various client types and versions that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="cb0e3-107">Chaque enregistrement dans la vue représente une version du client.</span><span class="sxs-lookup"><span data-stu-id="cb0e3-107">Each record in the view represents one client version.</span></span> <span data-ttu-id="cb0e3-108">Cet affichage a été introduit dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cb0e3-108">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="cb0e3-109">Il peuvent exister plusieurs enregistrements pour certaines colonnes.</span><span class="sxs-lookup"><span data-stu-id="cb0e3-109">There may be multiple records for certain columns.</span></span> 
  
|<span data-ttu-id="cb0e3-110">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="cb0e3-110">**Column**</span></span>|<span data-ttu-id="cb0e3-111">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="cb0e3-111">**Data Type**</span></span>|<span data-ttu-id="cb0e3-112">**Détails**</span><span class="sxs-lookup"><span data-stu-id="cb0e3-112">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="cb0e3-113">**VersionId**</span><span class="sxs-lookup"><span data-stu-id="cb0e3-113">**VersionId**</span></span> <br/> |<span data-ttu-id="cb0e3-114">int</span><span class="sxs-lookup"><span data-stu-id="cb0e3-114">int</span></span>  <br/> |<span data-ttu-id="cb0e3-115">Numéro unique identifiant ce type de client et de la version.</span><span class="sxs-lookup"><span data-stu-id="cb0e3-115">Unique number identifying this client type and version.</span></span>  <br/> |
|<span data-ttu-id="cb0e3-116">**Version**</span><span class="sxs-lookup"><span data-stu-id="cb0e3-116">**Version**</span></span> <br/> |<span data-ttu-id="cb0e3-117">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="cb0e3-117">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="cb0e3-118">Représente l’agent utilisateur.</span><span class="sxs-lookup"><span data-stu-id="cb0e3-118">Represents the user agent.</span></span>  <br/> |
|<span data-ttu-id="cb0e3-119">**TypeClient**</span><span class="sxs-lookup"><span data-stu-id="cb0e3-119">**ClientType**</span></span> <br/> |<span data-ttu-id="cb0e3-120">int</span><span class="sxs-lookup"><span data-stu-id="cb0e3-120">int</span></span>  <br/> |<span data-ttu-id="cb0e3-121">Type de client.</span><span class="sxs-lookup"><span data-stu-id="cb0e3-121">Type of client.</span></span>  <br/> |
|<span data-ttu-id="cb0e3-122">**ClientCategory**</span><span class="sxs-lookup"><span data-stu-id="cb0e3-122">**ClientCategory**</span></span> <br/> |<span data-ttu-id="cb0e3-123">nvarchar(64)</span><span class="sxs-lookup"><span data-stu-id="cb0e3-123">nvarchar(64)</span></span>  <br/> |<span data-ttu-id="cb0e3-124">Catégorie à laquelle appartient le client.</span><span class="sxs-lookup"><span data-stu-id="cb0e3-124">Category that the client belongs to.</span></span> <span data-ttu-id="cb0e3-125">Par exemple, le client Conferencing_Attendant_1.0 appartient à la CAA ClientCategory.</span><span class="sxs-lookup"><span data-stu-id="cb0e3-125">For example, the client Conferencing_Attendant_1.0 belongs to the ClientCategory CAA.</span></span>  <br/> |
   

