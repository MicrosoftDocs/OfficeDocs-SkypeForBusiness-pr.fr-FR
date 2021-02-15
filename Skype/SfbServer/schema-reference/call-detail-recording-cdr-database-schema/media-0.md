---
title: Affichage multimédia
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
ms.assetid: 1a7b2e59-082e-4188-98ae-48ae9bd3494a
description: La vue Media stocke des informations sur un type de média utilisé au cours d’une session d’égal à égal. Une session est représentée par plusieurs enregistrements dans la table, si plusieurs types de médias sont utilisés. Cette vue a été introduite dans Microsoft Lync Server 2013.
ms.openlocfilehash: 77c22246056a28cdb41a007ac0d7e2617fa00ad9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831785"
---
# <a name="media-view"></a><span data-ttu-id="b311e-105">Affichage multimédia</span><span class="sxs-lookup"><span data-stu-id="b311e-105">Media view</span></span>
 
<span data-ttu-id="b311e-106">La vue Media stocke des informations sur un type de média utilisé au cours d’une session d’égal à égal.</span><span class="sxs-lookup"><span data-stu-id="b311e-106">The Media view stores information about one media type used in a peer-to-peer session.</span></span> <span data-ttu-id="b311e-107">Une session est représentée par plusieurs enregistrements dans la table, si plusieurs types de médias sont utilisés.</span><span class="sxs-lookup"><span data-stu-id="b311e-107">One session would be represented by multiple records in the table, if more than one media type is used.</span></span> <span data-ttu-id="b311e-108">Cette vue a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b311e-108">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b311e-p103">La vue Media ne doit pas être utilisée pour calculer la durée du média lors d’une session. Cette vue contient les détails de signalisation de l’échange multimédia lors d’une session. L’échange multimédia est effectué par la requête INVITE et StartTime indique l’heure à laquelle la requête INVITE a été envoyée. L’heure d’invitation ne signifie pas nécessairement l’heure de début du média, car le média démarre seulement une fois la session acceptée.</span><span class="sxs-lookup"><span data-stu-id="b311e-p103">The Media view should not be used to calculate the media duration for a session. This view contains the signaling details of media exchange in a session. Media exchange is done by the INVITE request, and StartTime indicates the time that the INVITE was sent out. The invite time does not necessarily mean the media start time, because media starts only after the session is accepted.</span></span> 
  
<span data-ttu-id="b311e-112">L’affichage Multimédia contient toutes les colonnes de l’affichage [SessionDetails](sessiondetails-0.md) en plus de ceux répertoriés ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="b311e-112">The Media view contains all of the columns in the [SessionDetails view](sessiondetails-0.md) in addition the ones listed below.</span></span>
  
|<span data-ttu-id="b311e-113">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="b311e-113">**Column**</span></span>|<span data-ttu-id="b311e-114">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="b311e-114">**Data Type**</span></span>|<span data-ttu-id="b311e-115">**Détails**</span><span class="sxs-lookup"><span data-stu-id="b311e-115">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b311e-116">**Media**</span><span class="sxs-lookup"><span data-stu-id="b311e-116">**Media**</span></span> <br/> |<span data-ttu-id="b311e-117">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="b311e-117">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="b311e-118">Type de média.</span><span class="sxs-lookup"><span data-stu-id="b311e-118">Media type.</span></span> <span data-ttu-id="b311e-119">Pour plus [d’informations, voir le tableau MediaList.](medialist.md)</span><span class="sxs-lookup"><span data-stu-id="b311e-119">See the [MediaList table](medialist.md) for more information.</span></span> <br/> |
|<span data-ttu-id="b311e-120">**MediaStartTime**</span><span class="sxs-lookup"><span data-stu-id="b311e-120">**MediaStartTime**</span></span> <br/> |<span data-ttu-id="b311e-121">DateHeure</span><span class="sxs-lookup"><span data-stu-id="b311e-121">datetime</span></span>  <br/> |<span data-ttu-id="b311e-122">Heure d’envoi d’une demande multimédia.</span><span class="sxs-lookup"><span data-stu-id="b311e-122">Time that a media request was sent out.</span></span>  <br/> |
|<span data-ttu-id="b311e-123">**MediaEndTime**</span><span class="sxs-lookup"><span data-stu-id="b311e-123">**MediaEndTime**</span></span> <br/> |<span data-ttu-id="b311e-124">DateHeure</span><span class="sxs-lookup"><span data-stu-id="b311e-124">datetime</span></span>  <br/> |<span data-ttu-id="b311e-125">Heure de fin de la session.</span><span class="sxs-lookup"><span data-stu-id="b311e-125">End time of the session.</span></span>  <br/> |
   

