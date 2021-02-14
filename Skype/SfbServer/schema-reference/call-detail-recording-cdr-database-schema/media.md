---
title: Table Media
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
ms.assetid: 1e1b427f-59b5-4564-bde5-1002a80439ee
description: Chaque enregistrement représente un type de média utilisé au cours d’une session d’égal à égal. Une session est représentée par plusieurs enregistrements dans la table, si plusieurs types de médias sont utilisés.
ms.openlocfilehash: ce5b5a2b312307e608367279e4e871ed03063860
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49800104"
---
# <a name="media-table"></a><span data-ttu-id="2f65e-104">Table Media</span><span class="sxs-lookup"><span data-stu-id="2f65e-104">Media table</span></span>
 
<span data-ttu-id="2f65e-p102">Chaque enregistrement représente un type de média utilisé au cours d’une session d’égal à égal. Une session est représentée par plusieurs enregistrements dans la table, si plusieurs types de médias sont utilisés.</span><span class="sxs-lookup"><span data-stu-id="2f65e-p102">Each record represents one media type used in a peer-to-peer session. One session would be represented by multiple records in the table, if more than one media type is used.</span></span>
  
> [!NOTE]
> <span data-ttu-id="2f65e-p103">La table Media ne doit pas être utilisée pour calculer la durée du média lors d’une session. Cette table contient les détails de signalisation de l’échange multimédia lors d’une session. L’échange multimédia est effectué par la requête INVITE et StartTime indique l’heure à laquelle la requête INVITE a été envoyée. L’heure d’invitation ne signifie pas nécessairement l’heure de début du média, car le média démarre seulement lorsque le destinataire de la session accepte la session. EndTime signifie généralement l’heure de fin de cette session.</span><span class="sxs-lookup"><span data-stu-id="2f65e-p103">The Media table should not be used to calculate the media duration for a session. This table contains the signaling details of media exchange in a session. Media exchange is done by the INVITE request, and StartTime indicates the time that the INVITE was sent out. The invite time does not necessarily mean the media start time, because media starts only after the sessionee accepts the session. The EndTime usually means the end time of this session.</span></span> 
  
|<span data-ttu-id="2f65e-111">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="2f65e-111">**Column**</span></span>|<span data-ttu-id="2f65e-112">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="2f65e-112">**Data Type**</span></span>|<span data-ttu-id="2f65e-113">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="2f65e-113">**Key/Index**</span></span>|<span data-ttu-id="2f65e-114">**Détails**</span><span class="sxs-lookup"><span data-stu-id="2f65e-114">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2f65e-115">**SessionIdTime**</span><span class="sxs-lookup"><span data-stu-id="2f65e-115">**SessionIdTime**</span></span> <br/> |<span data-ttu-id="2f65e-116">DateHeure</span><span class="sxs-lookup"><span data-stu-id="2f65e-116">datetime</span></span>  <br/> |<span data-ttu-id="2f65e-117">Primaire, étrangère</span><span class="sxs-lookup"><span data-stu-id="2f65e-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="2f65e-118">Heure de la demande de session.</span><span class="sxs-lookup"><span data-stu-id="2f65e-118">Time of session request.</span></span> <span data-ttu-id="2f65e-119">Utilisée conjointement avec **SessionIdSeq** pour identifier de manière unique une session.</span><span class="sxs-lookup"><span data-stu-id="2f65e-119">Used in conjunction with **SessionIdSeq** to uniquely identify a session.</span></span> <span data-ttu-id="2f65e-120">Pour plus d’informations, voir le tableau Dialogs dans Skype Entreprise [Server 2015.](dialogs.md)</span><span class="sxs-lookup"><span data-stu-id="2f65e-120">See the [Dialogs table in Skype for Business Server 2015](dialogs.md) for more information.</span></span> <br/> |
|<span data-ttu-id="2f65e-121">**SessionIdSeq**</span><span class="sxs-lookup"><span data-stu-id="2f65e-121">**SessionIdSeq**</span></span> <br/> |<span data-ttu-id="2f65e-122">int</span><span class="sxs-lookup"><span data-stu-id="2f65e-122">int</span></span>  <br/> |<span data-ttu-id="2f65e-123">Primaire, étrangère</span><span class="sxs-lookup"><span data-stu-id="2f65e-123">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="2f65e-124">Numéro d’ID pour identifier la session.</span><span class="sxs-lookup"><span data-stu-id="2f65e-124">ID number to identify the session.</span></span> <span data-ttu-id="2f65e-125">Utilisé conjointement avec **SessionIdTime** pour identifier de manière unique une session.</span><span class="sxs-lookup"><span data-stu-id="2f65e-125">Used in conjunction with **SessionIdTime** to uniquely identify a session.</span></span> <span data-ttu-id="2f65e-126">Pour plus d’informations, voir le tableau Dialogs dans Skype Entreprise [Server 2015.](dialogs.md)</span><span class="sxs-lookup"><span data-stu-id="2f65e-126">See the [Dialogs table in Skype for Business Server 2015](dialogs.md) for more information.</span></span> <br/> |
|<span data-ttu-id="2f65e-127">**MediaId**</span><span class="sxs-lookup"><span data-stu-id="2f65e-127">**MediaId**</span></span> <br/> |<span data-ttu-id="2f65e-128">tinyint</span><span class="sxs-lookup"><span data-stu-id="2f65e-128">tinyint</span></span>  <br/> |<span data-ttu-id="2f65e-129">Primaire, étrangère</span><span class="sxs-lookup"><span data-stu-id="2f65e-129">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="2f65e-130">Numéro unique d’identification de ce type de média.</span><span class="sxs-lookup"><span data-stu-id="2f65e-130">Unique number identifying this media type.</span></span> <span data-ttu-id="2f65e-131">Pour plus [d’informations, voir le tableau MediaList.](medialist.md)</span><span class="sxs-lookup"><span data-stu-id="2f65e-131">See the [MediaList table](medialist.md) for more information.</span></span> <br/> |
|<span data-ttu-id="2f65e-132">**StartTime**</span><span class="sxs-lookup"><span data-stu-id="2f65e-132">**StartTime**</span></span> <br/> |<span data-ttu-id="2f65e-133">DateHeure</span><span class="sxs-lookup"><span data-stu-id="2f65e-133">datetime</span></span>  <br/> |<span data-ttu-id="2f65e-134">Primaire</span><span class="sxs-lookup"><span data-stu-id="2f65e-134">Primary</span></span>  <br/> |<span data-ttu-id="2f65e-p107">Heure d’envoi de la demande multimédia, et non pas heure réelle du début du média. **StartTime** inclut l’heure de configuration de la session.</span><span class="sxs-lookup"><span data-stu-id="2f65e-p107">This is the time that a media request was sent out, not the real media start time. **StartTime** includes the session setup time. </span></span><br/> |
|<span data-ttu-id="2f65e-137">**EndTime**</span><span class="sxs-lookup"><span data-stu-id="2f65e-137">**EndTime**</span></span> <br/> |<span data-ttu-id="2f65e-138">DateHeure</span><span class="sxs-lookup"><span data-stu-id="2f65e-138">datetime</span></span>  <br/> ||<span data-ttu-id="2f65e-139">Heure de fin de la session.</span><span class="sxs-lookup"><span data-stu-id="2f65e-139">This is the end time of the session.</span></span>  <br/> |
   

