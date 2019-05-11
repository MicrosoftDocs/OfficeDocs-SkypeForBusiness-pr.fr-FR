---
title: Table SIPResponseMetaData
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cf723737-4a75-4352-829b-f4954aa59716
description: La SIPResponseMetaDataTable contient une liste de codes de réponse SIP et la classification et la définition de chacun de ces codes. Ces codes sont générées en réponse aux événements affectant des périphériques SIP et SIP des sessions de communication ; par exemple, le code de réponse 403 est généré lorsqu’un périphérique SIP envoie une demande, mais le serveur refuse de respecter cette demande.
ms.openlocfilehash: edd1f4e60376b367f701864ff15d334c4d971e47
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930284"
---
# <a name="sipresponsemetadata-table"></a><span data-ttu-id="c1dfa-104">Table SIPResponseMetaData</span><span class="sxs-lookup"><span data-stu-id="c1dfa-104">SIPResponseMetaData table</span></span>
 
<span data-ttu-id="c1dfa-105">La SIPResponseMetaDataTable contient une liste de codes de réponse SIP et la classification et la définition de chacun de ces codes.</span><span class="sxs-lookup"><span data-stu-id="c1dfa-105">The SIPResponseMetaDataTable contains a list of SIP response codes and the classification and definition of each of those codes.</span></span> <span data-ttu-id="c1dfa-106">Ces codes sont générées en réponse aux événements affectant des périphériques SIP et SIP des sessions de communication ; par exemple, le code de réponse 403 est généré lorsqu’un périphérique SIP envoie une demande, mais le serveur refuse de respecter cette demande.</span><span class="sxs-lookup"><span data-stu-id="c1dfa-106">These codes are generated in response to events affecting SIP devices and SIP communication sessions; for example, the response code 403 is generated when a SIP device makes a request, but the server declines to honor that request.</span></span>
  
<span data-ttu-id="c1dfa-107">Ce tableau a été introduit dans Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="c1dfa-107">This table was introduced in Skype for Business Server 2015.</span></span>
  
|<span data-ttu-id="c1dfa-108">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="c1dfa-108">**Column**</span></span>|<span data-ttu-id="c1dfa-109">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="c1dfa-109">**Data Type**</span></span>|<span data-ttu-id="c1dfa-110">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="c1dfa-110">**Key/Index**</span></span>|<span data-ttu-id="c1dfa-111">**Détails**</span><span class="sxs-lookup"><span data-stu-id="c1dfa-111">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c1dfa-112">**ResponseCode**</span><span class="sxs-lookup"><span data-stu-id="c1dfa-112">**ResponseCode**</span></span> <br/> |<span data-ttu-id="c1dfa-113">int</span><span class="sxs-lookup"><span data-stu-id="c1dfa-113">int</span></span>  <br/> |<span data-ttu-id="c1dfa-114">Principal</span><span class="sxs-lookup"><span data-stu-id="c1dfa-114">Primary</span></span>  <br/> |<span data-ttu-id="c1dfa-115">Valeur numérique qui représente le code de réponse SIP.</span><span class="sxs-lookup"><span data-stu-id="c1dfa-115">Numeric value that represents the SIP response code.</span></span>  <br/> |
|<span data-ttu-id="c1dfa-116">**Classe**</span><span class="sxs-lookup"><span data-stu-id="c1dfa-116">**Class**</span></span> <br/> |<span data-ttu-id="c1dfa-117">int</span><span class="sxs-lookup"><span data-stu-id="c1dfa-117">int</span></span>  <br/> || <span data-ttu-id="c1dfa-118">Classification générale pour le code de réponse.</span><span class="sxs-lookup"><span data-stu-id="c1dfa-118">General classification for the response code.</span></span> <span data-ttu-id="c1dfa-119">Classifications sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="c1dfa-119">Classifications include:</span></span> <br/>  <span data-ttu-id="c1dfa-120">1 - réponses informatives</span><span class="sxs-lookup"><span data-stu-id="c1dfa-120">1 - Informational Responses</span></span> <br/>  <span data-ttu-id="c1dfa-121">2 - réponses réussite</span><span class="sxs-lookup"><span data-stu-id="c1dfa-121">2 - Successful Responses</span></span> <br/>  <span data-ttu-id="c1dfa-122">3 - réponses de redirection</span><span class="sxs-lookup"><span data-stu-id="c1dfa-122">3 - Redirection Responses</span></span> <br/>  <span data-ttu-id="c1dfa-123">4 - réponses d’échec de client</span><span class="sxs-lookup"><span data-stu-id="c1dfa-123">4 - Client Failure Responses</span></span> <br/>  <span data-ttu-id="c1dfa-124">5--Réponses d’échec de serveur</span><span class="sxs-lookup"><span data-stu-id="c1dfa-124">5 -- Server Failure Responses</span></span> <br/>  <span data-ttu-id="c1dfa-125">6 - réponse d’échec global</span><span class="sxs-lookup"><span data-stu-id="c1dfa-125">6 - Global Failure Response</span></span> <br/> |
|<span data-ttu-id="c1dfa-126">**Description**</span><span class="sxs-lookup"><span data-stu-id="c1dfa-126">**Description**</span></span> <br/> |<span data-ttu-id="c1dfa-127">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="c1dfa-127">nvarchar(256)</span></span>  <br/> ||<span data-ttu-id="c1dfa-128">Description du code de réponse SIP.</span><span class="sxs-lookup"><span data-stu-id="c1dfa-128">Description of the SIP response code.</span></span> <span data-ttu-id="c1dfa-129">Par exemple, le code de réponse 181 a la description suivante :</span><span class="sxs-lookup"><span data-stu-id="c1dfa-129">For example, response code 181 has the following description:</span></span>  <br/> <span data-ttu-id="c1dfa-130">Appel est transféré.</span><span class="sxs-lookup"><span data-stu-id="c1dfa-130">Call Is Being Forwarded</span></span>  <br/> |
   

