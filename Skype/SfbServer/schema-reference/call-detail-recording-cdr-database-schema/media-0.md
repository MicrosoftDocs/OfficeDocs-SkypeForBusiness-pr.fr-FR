---
title: Vue média
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1a7b2e59-082e-4188-98ae-48ae9bd3494a
description: La vue Media stocke des informations sur un type de support utilisé dans une session d’égal à égal. Une session est représentée par plusieurs enregistrements dans le tableau, si plus d’un type de média est utilisé. Cet affichage a été introduit dans Microsoft Lync Server 2013.
ms.openlocfilehash: 83caf609efae4e97961e7c62c3a1ed6c6004e8e8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930692"
---
# <a name="media-view"></a><span data-ttu-id="145d6-105">Vue média</span><span class="sxs-lookup"><span data-stu-id="145d6-105">Media view</span></span>
 
<span data-ttu-id="145d6-106">La vue Media stocke des informations sur un type de support utilisé dans une session d’égal à égal.</span><span class="sxs-lookup"><span data-stu-id="145d6-106">The Media view stores information about one media type used in a peer-to-peer session.</span></span> <span data-ttu-id="145d6-107">Une session est représentée par plusieurs enregistrements dans le tableau, si plus d’un type de média est utilisé.</span><span class="sxs-lookup"><span data-stu-id="145d6-107">One session would be represented by multiple records in the table, if more than one media type is used.</span></span> <span data-ttu-id="145d6-108">Cet affichage a été introduit dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="145d6-108">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="145d6-109">La vue Media ne doit pas être utilisée pour calculer la durée d’une session multimédia.</span><span class="sxs-lookup"><span data-stu-id="145d6-109">The Media view should not be used to calculate the media duration for a session.</span></span> <span data-ttu-id="145d6-110">Cet affichage contient les détails de signalisation d’échanges multimédias dans une session.</span><span class="sxs-lookup"><span data-stu-id="145d6-110">This view contains the signaling details of media exchange in a session.</span></span> <span data-ttu-id="145d6-111">Échanges multimédias est effectué à la demande d’invitation et StartTime indique l’heure à laquelle l’invitation a été envoyée. Le temps d’inviter ne signifie pas nécessairement que le support de démarrage, car media commence uniquement une fois que la session est acceptée.</span><span class="sxs-lookup"><span data-stu-id="145d6-111">Media exchange is done by the INVITE request, and StartTime indicates the time that the INVITE was sent out. The invite time does not necessarily mean the media start time, because media starts only after the session is accepted.</span></span> 
  
<span data-ttu-id="145d6-112">La vue Media contient toutes les colonnes de [SessionDetails view](sessiondetails-0.md) en plus celles répertoriées ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="145d6-112">The Media view contains all of the columns in the [SessionDetails view](sessiondetails-0.md) in addition the ones listed below.</span></span>
  
|<span data-ttu-id="145d6-113">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="145d6-113">**Column**</span></span>|<span data-ttu-id="145d6-114">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="145d6-114">**Data Type**</span></span>|<span data-ttu-id="145d6-115">**Détails**</span><span class="sxs-lookup"><span data-stu-id="145d6-115">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="145d6-116">**Media**</span><span class="sxs-lookup"><span data-stu-id="145d6-116">**Media**</span></span> <br/> |<span data-ttu-id="145d6-117">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="145d6-117">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="145d6-118">Type de média.</span><span class="sxs-lookup"><span data-stu-id="145d6-118">Media type.</span></span> <span data-ttu-id="145d6-119">Consultez la [table MediaList](medialist.md) pour plus d’informations.</span><span class="sxs-lookup"><span data-stu-id="145d6-119">See the [MediaList table](medialist.md) for more information.</span></span> <br/> |
|<span data-ttu-id="145d6-120">**MediaStartTime**</span><span class="sxs-lookup"><span data-stu-id="145d6-120">**MediaStartTime**</span></span> <br/> |<span data-ttu-id="145d6-121">DateHeure</span><span class="sxs-lookup"><span data-stu-id="145d6-121">datetime</span></span>  <br/> |<span data-ttu-id="145d6-122">Heure à laquelle une demande de support a été envoyée.</span><span class="sxs-lookup"><span data-stu-id="145d6-122">Time that a media request was sent out.</span></span>  <br/> |
|<span data-ttu-id="145d6-123">**MediaEndTime**</span><span class="sxs-lookup"><span data-stu-id="145d6-123">**MediaEndTime**</span></span> <br/> |<span data-ttu-id="145d6-124">DateHeure</span><span class="sxs-lookup"><span data-stu-id="145d6-124">datetime</span></span>  <br/> |<span data-ttu-id="145d6-125">Heure de fin de la session.</span><span class="sxs-lookup"><span data-stu-id="145d6-125">End time of the session.</span></span>  <br/> |
   

