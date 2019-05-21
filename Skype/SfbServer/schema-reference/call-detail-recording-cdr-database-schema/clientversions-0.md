---
title: Affichage ClientVersions
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: caf7678f-83a0-46c8-83cc-fee4c3991f52
description: Le mode ClientVersions stocke les informations sur les différents types de clients et différentes versions ayant participé à des sessions enregistrées dans la base de données. Chaque enregistrement dans la vue représente une version du client. Cet affichage a été présenté dans Microsoft Lync Server 2013.
ms.openlocfilehash: 845a6fdb88ba62273413d8e7ea50fb165f0f321c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296538"
---
# <a name="clientversions-view"></a><span data-ttu-id="e6698-105">Affichage ClientVersions</span><span class="sxs-lookup"><span data-stu-id="e6698-105">ClientVersions view</span></span>
 
<span data-ttu-id="e6698-106">Le mode ClientVersions stocke les informations sur les différents types de clients et différentes versions ayant participé à des sessions enregistrées dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="e6698-106">The ClientVersions view stores information about the various client types and versions that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="e6698-107">Chaque enregistrement dans la vue représente une version du client.</span><span class="sxs-lookup"><span data-stu-id="e6698-107">Each record in the view represents one client version.</span></span> <span data-ttu-id="e6698-108">Cet affichage a été présenté dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e6698-108">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e6698-109">Il peut y avoir plusieurs enregistrements pour certaines colonnes.</span><span class="sxs-lookup"><span data-stu-id="e6698-109">There may be multiple records for certain columns.</span></span> 
  
|<span data-ttu-id="e6698-110">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="e6698-110">**Column**</span></span>|<span data-ttu-id="e6698-111">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="e6698-111">**Data Type**</span></span>|<span data-ttu-id="e6698-112">**Détails**</span><span class="sxs-lookup"><span data-stu-id="e6698-112">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e6698-113">**VersionId**</span><span class="sxs-lookup"><span data-stu-id="e6698-113">**VersionId**</span></span> <br/> |<span data-ttu-id="e6698-114">int</span><span class="sxs-lookup"><span data-stu-id="e6698-114">int</span></span>  <br/> |<span data-ttu-id="e6698-115">Numéro unique identifiant ce type et version de client.</span><span class="sxs-lookup"><span data-stu-id="e6698-115">Unique number identifying this client type and version.</span></span>  <br/> |
|<span data-ttu-id="e6698-116">**Version**</span><span class="sxs-lookup"><span data-stu-id="e6698-116">**Version**</span></span> <br/> |<span data-ttu-id="e6698-117">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e6698-117">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="e6698-118">Représente l’agent utilisateur.</span><span class="sxs-lookup"><span data-stu-id="e6698-118">Represents the user agent.</span></span>  <br/> |
|<span data-ttu-id="e6698-119">**TypeClient**</span><span class="sxs-lookup"><span data-stu-id="e6698-119">**ClientType**</span></span> <br/> |<span data-ttu-id="e6698-120">int</span><span class="sxs-lookup"><span data-stu-id="e6698-120">int</span></span>  <br/> |<span data-ttu-id="e6698-121">Type de client.</span><span class="sxs-lookup"><span data-stu-id="e6698-121">Type of client.</span></span>  <br/> |
|<span data-ttu-id="e6698-122">**ClientCategory**</span><span class="sxs-lookup"><span data-stu-id="e6698-122">**ClientCategory**</span></span> <br/> |<span data-ttu-id="e6698-123">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="e6698-123">nvarchar(64)</span></span>  <br/> |<span data-ttu-id="e6698-124">Catégorie à laquelle le client appartient.</span><span class="sxs-lookup"><span data-stu-id="e6698-124">Category that the client belongs to.</span></span> <span data-ttu-id="e6698-125">Par exemple, le client Conferencing_Attendant_ 1.0 appartient au CAA ClientCategory.</span><span class="sxs-lookup"><span data-stu-id="e6698-125">For example, the client Conferencing_Attendant_1.0 belongs to the ClientCategory CAA.</span></span>  <br/> |
   

