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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: caf7678f-83a0-46c8-83cc-fee4c3991f52
description: Le mode ClientVersions stocke les informations sur les différents types de clients et différentes versions ayant participé à des sessions enregistrées dans la base de données. Chaque enregistrement dans la vue représente une version du client. Cet affichage a été présenté dans Microsoft Lync Server 2013.
ms.openlocfilehash: d37e2a1599eaf8906d11fdb8faf545aa3447f00f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815412"
---
# <a name="clientversions-view"></a><span data-ttu-id="cd22b-105">Affichage ClientVersions</span><span class="sxs-lookup"><span data-stu-id="cd22b-105">ClientVersions view</span></span>
 
<span data-ttu-id="cd22b-106">Le mode ClientVersions stocke les informations sur les différents types de clients et différentes versions ayant participé à des sessions enregistrées dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="cd22b-106">The ClientVersions view stores information about the various client types and versions that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="cd22b-107">Chaque enregistrement dans la vue représente une version du client.</span><span class="sxs-lookup"><span data-stu-id="cd22b-107">Each record in the view represents one client version.</span></span> <span data-ttu-id="cd22b-108">Cet affichage a été présenté dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cd22b-108">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="cd22b-109">Il peut y avoir plusieurs enregistrements pour certaines colonnes.</span><span class="sxs-lookup"><span data-stu-id="cd22b-109">There may be multiple records for certain columns.</span></span> 
  
|<span data-ttu-id="cd22b-110">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="cd22b-110">**Column**</span></span>|<span data-ttu-id="cd22b-111">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="cd22b-111">**Data Type**</span></span>|<span data-ttu-id="cd22b-112">**Détails**</span><span class="sxs-lookup"><span data-stu-id="cd22b-112">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="cd22b-113">**VersionId**</span><span class="sxs-lookup"><span data-stu-id="cd22b-113">**VersionId**</span></span> <br/> |<span data-ttu-id="cd22b-114">int</span><span class="sxs-lookup"><span data-stu-id="cd22b-114">int</span></span>  <br/> |<span data-ttu-id="cd22b-115">Numéro unique identifiant ce type et version de client.</span><span class="sxs-lookup"><span data-stu-id="cd22b-115">Unique number identifying this client type and version.</span></span>  <br/> |
|<span data-ttu-id="cd22b-116">**Version**</span><span class="sxs-lookup"><span data-stu-id="cd22b-116">**Version**</span></span> <br/> |<span data-ttu-id="cd22b-117">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="cd22b-117">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="cd22b-118">Représente l’agent utilisateur.</span><span class="sxs-lookup"><span data-stu-id="cd22b-118">Represents the user agent.</span></span>  <br/> |
|<span data-ttu-id="cd22b-119">**TypeClient**</span><span class="sxs-lookup"><span data-stu-id="cd22b-119">**ClientType**</span></span> <br/> |<span data-ttu-id="cd22b-120">int</span><span class="sxs-lookup"><span data-stu-id="cd22b-120">int</span></span>  <br/> |<span data-ttu-id="cd22b-121">Type de client.</span><span class="sxs-lookup"><span data-stu-id="cd22b-121">Type of client.</span></span>  <br/> |
|<span data-ttu-id="cd22b-122">**ClientCategory**</span><span class="sxs-lookup"><span data-stu-id="cd22b-122">**ClientCategory**</span></span> <br/> |<span data-ttu-id="cd22b-123">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="cd22b-123">nvarchar(64)</span></span>  <br/> |<span data-ttu-id="cd22b-124">Catégorie à laquelle le client appartient.</span><span class="sxs-lookup"><span data-stu-id="cd22b-124">Category that the client belongs to.</span></span> <span data-ttu-id="cd22b-125">Par exemple, le client Conferencing_Attendant_1.0 appartient au CAA ClientCategory.</span><span class="sxs-lookup"><span data-stu-id="cd22b-125">For example, the client Conferencing_Attendant_1.0 belongs to the ClientCategory CAA.</span></span>  <br/> |
   

