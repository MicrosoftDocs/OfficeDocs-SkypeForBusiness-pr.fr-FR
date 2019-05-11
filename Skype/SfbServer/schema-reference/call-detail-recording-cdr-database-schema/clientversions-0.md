---
title: Vue clientversions
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: caf7678f-83a0-46c8-83cc-fee4c3991f52
description: La vue ClientVersions stocke des informations sur les différents types de clients et les versions qui ont participé à des sessions enregistrées dans la base de données. Chaque enregistrement dans la vue représente une version du client. Cet affichage a été introduit dans Microsoft Lync Server 2013.
ms.openlocfilehash: cc4024a7e2644a177eb6962c8fdc7078fd6b397d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901521"
---
# <a name="clientversions-view"></a><span data-ttu-id="ca1d7-105">Vue clientversions</span><span class="sxs-lookup"><span data-stu-id="ca1d7-105">ClientVersions view</span></span>
 
<span data-ttu-id="ca1d7-106">La vue ClientVersions stocke des informations sur les différents types de clients et les versions qui ont participé à des sessions enregistrées dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="ca1d7-106">The ClientVersions view stores information about the various client types and versions that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="ca1d7-107">Chaque enregistrement dans la vue représente une version du client.</span><span class="sxs-lookup"><span data-stu-id="ca1d7-107">Each record in the view represents one client version.</span></span> <span data-ttu-id="ca1d7-108">Cet affichage a été introduit dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ca1d7-108">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ca1d7-109">Il peuvent exister plusieurs enregistrements pour certaines colonnes.</span><span class="sxs-lookup"><span data-stu-id="ca1d7-109">There may be multiple records for certain columns.</span></span> 
  
|<span data-ttu-id="ca1d7-110">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="ca1d7-110">**Column**</span></span>|<span data-ttu-id="ca1d7-111">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="ca1d7-111">**Data Type**</span></span>|<span data-ttu-id="ca1d7-112">**Détails**</span><span class="sxs-lookup"><span data-stu-id="ca1d7-112">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ca1d7-113">**VersionId**</span><span class="sxs-lookup"><span data-stu-id="ca1d7-113">**VersionId**</span></span> <br/> |<span data-ttu-id="ca1d7-114">int</span><span class="sxs-lookup"><span data-stu-id="ca1d7-114">int</span></span>  <br/> |<span data-ttu-id="ca1d7-115">Numéro unique identifiant ce type de client et de la version.</span><span class="sxs-lookup"><span data-stu-id="ca1d7-115">Unique number identifying this client type and version.</span></span>  <br/> |
|<span data-ttu-id="ca1d7-116">**Version**</span><span class="sxs-lookup"><span data-stu-id="ca1d7-116">**Version**</span></span> <br/> |<span data-ttu-id="ca1d7-117">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="ca1d7-117">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="ca1d7-118">Représente l’agent utilisateur.</span><span class="sxs-lookup"><span data-stu-id="ca1d7-118">Represents the user agent.</span></span>  <br/> |
|<span data-ttu-id="ca1d7-119">**TypeClient**</span><span class="sxs-lookup"><span data-stu-id="ca1d7-119">**ClientType**</span></span> <br/> |<span data-ttu-id="ca1d7-120">int</span><span class="sxs-lookup"><span data-stu-id="ca1d7-120">int</span></span>  <br/> |<span data-ttu-id="ca1d7-121">Type de client.</span><span class="sxs-lookup"><span data-stu-id="ca1d7-121">Type of client.</span></span>  <br/> |
|<span data-ttu-id="ca1d7-122">**ClientCategory**</span><span class="sxs-lookup"><span data-stu-id="ca1d7-122">**ClientCategory**</span></span> <br/> |<span data-ttu-id="ca1d7-123">nvarchar(64)</span><span class="sxs-lookup"><span data-stu-id="ca1d7-123">nvarchar(64)</span></span>  <br/> |<span data-ttu-id="ca1d7-124">Catégorie à laquelle appartient le client.</span><span class="sxs-lookup"><span data-stu-id="ca1d7-124">Category that the client belongs to.</span></span> <span data-ttu-id="ca1d7-125">Par exemple, le client Conferencing_Attendant_1.0 appartient à la CAA ClientCategory.</span><span class="sxs-lookup"><span data-stu-id="ca1d7-125">For example, the client Conferencing_Attendant_1.0 belongs to the ClientCategory CAA.</span></span>  <br/> |
   

