---
title: Vue média
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1a7b2e59-082e-4188-98ae-48ae9bd3494a
description: La vue média stocke des informations sur un type de support utilisé dans une session peer-to-peer. Une session est représentée par plusieurs enregistrements de la table, si plus d’un type de média est utilisé. Cette vue a été introduite dans Microsoft Lync Server 2013.
ms.openlocfilehash: 0cbcb353ec768b9d3ee66f1a10d59b5c4523acea
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="media-view"></a><span data-ttu-id="d6a78-105">Vue média</span><span class="sxs-lookup"><span data-stu-id="d6a78-105">Media view</span></span>
 
<span data-ttu-id="d6a78-106">La vue média stocke des informations sur un type de support utilisé dans une session peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="d6a78-106">The Media view stores information about one media type used in a peer-to-peer session.</span></span> <span data-ttu-id="d6a78-107">Une session est représentée par plusieurs enregistrements de la table, si plus d’un type de média est utilisé.</span><span class="sxs-lookup"><span data-stu-id="d6a78-107">One session would be represented by multiple records in the table, if more than one media type is used.</span></span> <span data-ttu-id="d6a78-108">Cette vue a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d6a78-108">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d6a78-109">La vue média ne doit pas servir pour calculer la durée d’une session de média.</span><span class="sxs-lookup"><span data-stu-id="d6a78-109">The Media view should not be used to calculate the media duration for a session.</span></span> <span data-ttu-id="d6a78-110">Cette vue contient les détails de signalisation de l’échange de médias dans une session.</span><span class="sxs-lookup"><span data-stu-id="d6a78-110">This view contains the signaling details of media exchange in a session.</span></span> <span data-ttu-id="d6a78-111">Échange de médias est effectué par la demande d’invitation et StartTime indique l’heure à laquelle l’invitation a été envoyée. L’heure de l’invitation ne signifie pas nécessairement que le support de démarrage, car le média ne démarre qu’après que la session est acceptée.</span><span class="sxs-lookup"><span data-stu-id="d6a78-111">Media exchange is done by the INVITE request, and StartTime indicates the time that the INVITE was sent out. The invite time does not necessarily mean the media start time, because media starts only after the session is accepted.</span></span> 
  
<span data-ttu-id="d6a78-112">La vue média contient toutes les colonnes dans la [vue de le SessionDetails](sessiondetails-0.md) en outre ceux répertoriés ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="d6a78-112">The Media view contains all of the columns in the [SessionDetails view](sessiondetails-0.md) in addition the ones listed below.</span></span>
  
|<span data-ttu-id="d6a78-113">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="d6a78-113">**Column**</span></span>|<span data-ttu-id="d6a78-114">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="d6a78-114">**Data Type**</span></span>|<span data-ttu-id="d6a78-115">**Détails**</span><span class="sxs-lookup"><span data-stu-id="d6a78-115">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d6a78-116">**Media**</span><span class="sxs-lookup"><span data-stu-id="d6a78-116">**Media**</span></span> <br/> |<span data-ttu-id="d6a78-117">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="d6a78-117">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="d6a78-118">Type de média.</span><span class="sxs-lookup"><span data-stu-id="d6a78-118">Media type.</span></span> <span data-ttu-id="d6a78-119">Consultez le [tableau de MediaList](medialist.md) pour plus d’informations.</span><span class="sxs-lookup"><span data-stu-id="d6a78-119">See the [MediaList table](medialist.md) for more information.</span></span> <br/> |
|<span data-ttu-id="d6a78-120">**MediaStartTime**</span><span class="sxs-lookup"><span data-stu-id="d6a78-120">**MediaStartTime**</span></span> <br/> |<span data-ttu-id="d6a78-121">DateHeure</span><span class="sxs-lookup"><span data-stu-id="d6a78-121">datetime</span></span>  <br/> |<span data-ttu-id="d6a78-122">Heure à laquelle une demande de support a été envoyée.</span><span class="sxs-lookup"><span data-stu-id="d6a78-122">Time that a media request was sent out.</span></span>  <br/> |
|<span data-ttu-id="d6a78-123">**MediaEndTime**</span><span class="sxs-lookup"><span data-stu-id="d6a78-123">**MediaEndTime**</span></span> <br/> |<span data-ttu-id="d6a78-124">DateHeure</span><span class="sxs-lookup"><span data-stu-id="d6a78-124">datetime</span></span>  <br/> |<span data-ttu-id="d6a78-125">Heure de fin de la session.</span><span class="sxs-lookup"><span data-stu-id="d6a78-125">End time of the session.</span></span>  <br/> |
   

