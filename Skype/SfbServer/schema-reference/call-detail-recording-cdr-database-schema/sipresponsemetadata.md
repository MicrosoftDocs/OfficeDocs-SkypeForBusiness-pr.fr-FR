---
title: Table de SIPResponseMetaData
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cf723737-4a75-4352-829b-f4954aa59716
description: La SIPResponseMetaDataTable contient une liste des codes de réponse SIP et la classification et la définition de chacun de ces codes. Ces codes sont générés en réponse aux événements affectant les équipements SIP et SIP des sessions de communication ; par exemple, le code de réponse 403 est généré lorsqu’un périphérique SIP fait une demande, mais le serveur refuse d’honorer la demande.
ms.openlocfilehash: a90a248837dd705746fe3b342874aad10480e8a6
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="sipresponsemetadata-table"></a><span data-ttu-id="6b878-104">Table de SIPResponseMetaData</span><span class="sxs-lookup"><span data-stu-id="6b878-104">SIPResponseMetaData table</span></span>
 
<span data-ttu-id="6b878-105">La SIPResponseMetaDataTable contient une liste des codes de réponse SIP et la classification et la définition de chacun de ces codes.</span><span class="sxs-lookup"><span data-stu-id="6b878-105">The SIPResponseMetaDataTable contains a list of SIP response codes and the classification and definition of each of those codes.</span></span> <span data-ttu-id="6b878-106">Ces codes sont générés en réponse aux événements affectant les équipements SIP et SIP des sessions de communication ; par exemple, le code de réponse 403 est généré lorsqu’un périphérique SIP fait une demande, mais le serveur refuse d’honorer la demande.</span><span class="sxs-lookup"><span data-stu-id="6b878-106">These codes are generated in response to events affecting SIP devices and SIP communication sessions; for example, the response code 403 is generated when a SIP device makes a request, but the server declines to honor that request.</span></span>
  
<span data-ttu-id="6b878-107">Cette table a été introduite dans Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="6b878-107">This table was introduced in Skype for Business Server 2015.</span></span>
  
|<span data-ttu-id="6b878-108">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="6b878-108">**Column**</span></span>|<span data-ttu-id="6b878-109">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="6b878-109">**Data Type**</span></span>|<span data-ttu-id="6b878-110">**Index de la clé**</span><span class="sxs-lookup"><span data-stu-id="6b878-110">**Key/Index**</span></span>|<span data-ttu-id="6b878-111">**Détails**</span><span class="sxs-lookup"><span data-stu-id="6b878-111">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="6b878-112">**ResponseCode**</span><span class="sxs-lookup"><span data-stu-id="6b878-112">**ResponseCode**</span></span> <br/> |<span data-ttu-id="6b878-113">int</span><span class="sxs-lookup"><span data-stu-id="6b878-113">int</span></span>  <br/> |<span data-ttu-id="6b878-114">Principal</span><span class="sxs-lookup"><span data-stu-id="6b878-114">Primary</span></span>  <br/> |<span data-ttu-id="6b878-115">Valeur numérique qui représente le code de réponse SIP.</span><span class="sxs-lookup"><span data-stu-id="6b878-115">Numeric value that represents the SIP response code.</span></span>  <br/> |
|<span data-ttu-id="6b878-116">**Classe**</span><span class="sxs-lookup"><span data-stu-id="6b878-116">**Class**</span></span> <br/> |<span data-ttu-id="6b878-117">int</span><span class="sxs-lookup"><span data-stu-id="6b878-117">int</span></span>  <br/> || <span data-ttu-id="6b878-118">Classification générale pour le code de réponse.</span><span class="sxs-lookup"><span data-stu-id="6b878-118">General classification for the response code.</span></span> <span data-ttu-id="6b878-119">Les classifications sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="6b878-119">Classifications include:</span></span> <br/>  <span data-ttu-id="6b878-120">1 - réponses d’information</span><span class="sxs-lookup"><span data-stu-id="6b878-120">1 - Informational Responses</span></span> <br/>  <span data-ttu-id="6b878-121">2 - réponses réussis</span><span class="sxs-lookup"><span data-stu-id="6b878-121">2 - Successful Responses</span></span> <br/>  <span data-ttu-id="6b878-122">3 - réponses de redirection</span><span class="sxs-lookup"><span data-stu-id="6b878-122">3 - Redirection Responses</span></span> <br/>  <span data-ttu-id="6b878-123">4 - réponses Échec de la client</span><span class="sxs-lookup"><span data-stu-id="6b878-123">4 - Client Failure Responses</span></span> <br/>  <span data-ttu-id="6b878-124">5--Réponses d’échec serveur</span><span class="sxs-lookup"><span data-stu-id="6b878-124">5 -- Server Failure Responses</span></span> <br/>  <span data-ttu-id="6b878-125">6 - réponse d’échec global</span><span class="sxs-lookup"><span data-stu-id="6b878-125">6 - Global Failure Response</span></span> <br/> |
|<span data-ttu-id="6b878-126">**Description**</span><span class="sxs-lookup"><span data-stu-id="6b878-126">**Description**</span></span> <br/> |<span data-ttu-id="6b878-127">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="6b878-127">nvarchar(256)</span></span>  <br/> ||<span data-ttu-id="6b878-128">Description du code de réponse SIP.</span><span class="sxs-lookup"><span data-stu-id="6b878-128">Description of the SIP response code.</span></span> <span data-ttu-id="6b878-129">Par exemple, le code de réponse 181 a la description suivante :</span><span class="sxs-lookup"><span data-stu-id="6b878-129">For example, response code 181 has the following description:</span></span>  <br/> <span data-ttu-id="6b878-130">Appel est transmis</span><span class="sxs-lookup"><span data-stu-id="6b878-130">Call Is Being Forwarded</span></span>  <br/> |
   

