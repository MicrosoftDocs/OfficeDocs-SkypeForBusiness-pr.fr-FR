---
title: Vue multimédia
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
ms.assetid: 1a7b2e59-082e-4188-98ae-48ae9bd3494a
description: Le mode multimédia stocke les informations relatives à un type de média utilisé dans une session d’égal à égal. Une session serait représentée par plusieurs enregistrements dans la table, si plusieurs types de média sont utilisés. Cet affichage a été présenté dans Microsoft Lync Server 2013.
ms.openlocfilehash: 26ef344b5fade02168fb8737fe00049e44e24892
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815052"
---
# <a name="media-view"></a><span data-ttu-id="66e28-105">Vue multimédia</span><span class="sxs-lookup"><span data-stu-id="66e28-105">Media view</span></span>
 
<span data-ttu-id="66e28-106">Le mode multimédia stocke les informations relatives à un type de média utilisé dans une session d’égal à égal.</span><span class="sxs-lookup"><span data-stu-id="66e28-106">The Media view stores information about one media type used in a peer-to-peer session.</span></span> <span data-ttu-id="66e28-107">Une session serait représentée par plusieurs enregistrements dans la table, si plusieurs types de média sont utilisés.</span><span class="sxs-lookup"><span data-stu-id="66e28-107">One session would be represented by multiple records in the table, if more than one media type is used.</span></span> <span data-ttu-id="66e28-108">Cet affichage a été présenté dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="66e28-108">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="66e28-109">Le mode multimédia ne doit pas être utilisé pour calculer la durée du média pour une session.</span><span class="sxs-lookup"><span data-stu-id="66e28-109">The Media view should not be used to calculate the media duration for a session.</span></span> <span data-ttu-id="66e28-110">Cet affichage contient les détails de signalisation d’échange de médias dans une session.</span><span class="sxs-lookup"><span data-stu-id="66e28-110">This view contains the signaling details of media exchange in a session.</span></span> <span data-ttu-id="66e28-111">L’échange de média est effectué par la demande d’invitation, et la durée de StartTime indique l’heure d’envoi de l’invitation. La durée d’invitation ne correspond pas nécessairement à l’heure de début du média, car le contenu multimédia ne démarre qu’après acceptation de la session.</span><span class="sxs-lookup"><span data-stu-id="66e28-111">Media exchange is done by the INVITE request, and StartTime indicates the time that the INVITE was sent out. The invite time does not necessarily mean the media start time, because media starts only after the session is accepted.</span></span> 
  
<span data-ttu-id="66e28-112">La vue multimédia contient toutes les colonnes de la [vue SessionDetails](sessiondetails-0.md) , en plus de celles répertoriées ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="66e28-112">The Media view contains all of the columns in the [SessionDetails view](sessiondetails-0.md) in addition the ones listed below.</span></span>
  
|<span data-ttu-id="66e28-113">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="66e28-113">**Column**</span></span>|<span data-ttu-id="66e28-114">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="66e28-114">**Data Type**</span></span>|<span data-ttu-id="66e28-115">**Détails**</span><span class="sxs-lookup"><span data-stu-id="66e28-115">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="66e28-116">**Media**</span><span class="sxs-lookup"><span data-stu-id="66e28-116">**Media**</span></span> <br/> |<span data-ttu-id="66e28-117">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="66e28-117">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="66e28-118">Type de média.</span><span class="sxs-lookup"><span data-stu-id="66e28-118">Media type.</span></span> <span data-ttu-id="66e28-119">Pour plus d’informations, reportez-vous à la [table de médiane](medialist.md) .</span><span class="sxs-lookup"><span data-stu-id="66e28-119">See the [MediaList table](medialist.md) for more information.</span></span> <br/> |
|<span data-ttu-id="66e28-120">**MediaStartTime**</span><span class="sxs-lookup"><span data-stu-id="66e28-120">**MediaStartTime**</span></span> <br/> |<span data-ttu-id="66e28-121">DateHeure</span><span class="sxs-lookup"><span data-stu-id="66e28-121">datetime</span></span>  <br/> |<span data-ttu-id="66e28-122">Temps d’envoi d’une demande de média.</span><span class="sxs-lookup"><span data-stu-id="66e28-122">Time that a media request was sent out.</span></span>  <br/> |
|<span data-ttu-id="66e28-123">**MediaEndTime**</span><span class="sxs-lookup"><span data-stu-id="66e28-123">**MediaEndTime**</span></span> <br/> |<span data-ttu-id="66e28-124">DateHeure</span><span class="sxs-lookup"><span data-stu-id="66e28-124">datetime</span></span>  <br/> |<span data-ttu-id="66e28-125">Heure de fin de la session.</span><span class="sxs-lookup"><span data-stu-id="66e28-125">End time of the session.</span></span>  <br/> |
   

