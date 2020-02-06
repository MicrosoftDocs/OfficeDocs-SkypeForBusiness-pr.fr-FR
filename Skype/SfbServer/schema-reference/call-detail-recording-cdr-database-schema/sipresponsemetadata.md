---
title: Table SIPResponseMetaData
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: cf723737-4a75-4352-829b-f4954aa59716
description: Le SIPResponseMetaDataTable contient une liste des codes de réponse SIP et la classification et la définition de chacun de ces codes. Ces codes sont générés en réponse à des événements affectant des périphériques SIP et des sessions de communication SIP ; par exemple, le code de réponse 403 est généré lorsqu’un périphérique SIP envoie une demande, mais que le serveur décline la demande.
ms.openlocfilehash: 2c302793dc9f9c53d445d231a261bf43a0c385df
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814892"
---
# <a name="sipresponsemetadata-table"></a><span data-ttu-id="372b7-104">Table SIPResponseMetaData</span><span class="sxs-lookup"><span data-stu-id="372b7-104">SIPResponseMetaData table</span></span>
 
<span data-ttu-id="372b7-105">Le SIPResponseMetaDataTable contient une liste des codes de réponse SIP et la classification et la définition de chacun de ces codes.</span><span class="sxs-lookup"><span data-stu-id="372b7-105">The SIPResponseMetaDataTable contains a list of SIP response codes and the classification and definition of each of those codes.</span></span> <span data-ttu-id="372b7-106">Ces codes sont générés en réponse à des événements affectant des périphériques SIP et des sessions de communication SIP ; par exemple, le code de réponse 403 est généré lorsqu’un périphérique SIP envoie une demande, mais que le serveur décline la demande.</span><span class="sxs-lookup"><span data-stu-id="372b7-106">These codes are generated in response to events affecting SIP devices and SIP communication sessions; for example, the response code 403 is generated when a SIP device makes a request, but the server declines to honor that request.</span></span>
  
<span data-ttu-id="372b7-107">Ce tableau a été présenté dans Skype entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="372b7-107">This table was introduced in Skype for Business Server 2015.</span></span>
  
|<span data-ttu-id="372b7-108">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="372b7-108">**Column**</span></span>|<span data-ttu-id="372b7-109">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="372b7-109">**Data Type**</span></span>|<span data-ttu-id="372b7-110">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="372b7-110">**Key/Index**</span></span>|<span data-ttu-id="372b7-111">**Détails**</span><span class="sxs-lookup"><span data-stu-id="372b7-111">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="372b7-112">**ResponseCode**</span><span class="sxs-lookup"><span data-stu-id="372b7-112">**ResponseCode**</span></span> <br/> |<span data-ttu-id="372b7-113">int</span><span class="sxs-lookup"><span data-stu-id="372b7-113">int</span></span>  <br/> |<span data-ttu-id="372b7-114">Principal</span><span class="sxs-lookup"><span data-stu-id="372b7-114">Primary</span></span>  <br/> |<span data-ttu-id="372b7-115">Valeur numérique qui représente le code de réponse SIP.</span><span class="sxs-lookup"><span data-stu-id="372b7-115">Numeric value that represents the SIP response code.</span></span>  <br/> |
|<span data-ttu-id="372b7-116">**Cours**</span><span class="sxs-lookup"><span data-stu-id="372b7-116">**Class**</span></span> <br/> |<span data-ttu-id="372b7-117">int</span><span class="sxs-lookup"><span data-stu-id="372b7-117">int</span></span>  <br/> || <span data-ttu-id="372b7-118">Classification générale du code de réponse.</span><span class="sxs-lookup"><span data-stu-id="372b7-118">General classification for the response code.</span></span> <span data-ttu-id="372b7-119">Les classifications sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="372b7-119">Classifications include:</span></span> <br/>  <span data-ttu-id="372b7-120">1-réponses d’information</span><span class="sxs-lookup"><span data-stu-id="372b7-120">1 - Informational Responses</span></span> <br/>  <span data-ttu-id="372b7-121">2-réponses réussies</span><span class="sxs-lookup"><span data-stu-id="372b7-121">2 - Successful Responses</span></span> <br/>  <span data-ttu-id="372b7-122">3-réponses de redirection</span><span class="sxs-lookup"><span data-stu-id="372b7-122">3 - Redirection Responses</span></span> <br/>  <span data-ttu-id="372b7-123">4-réponses de défaillance client</span><span class="sxs-lookup"><span data-stu-id="372b7-123">4 - Client Failure Responses</span></span> <br/>  <span data-ttu-id="372b7-124">5 réponses aux échecs sur le serveur</span><span class="sxs-lookup"><span data-stu-id="372b7-124">5 -- Server Failure Responses</span></span> <br/>  <span data-ttu-id="372b7-125">6-réponse d’échec globale</span><span class="sxs-lookup"><span data-stu-id="372b7-125">6 - Global Failure Response</span></span> <br/> |
|<span data-ttu-id="372b7-126">**Description**</span><span class="sxs-lookup"><span data-stu-id="372b7-126">**Description**</span></span> <br/> |<span data-ttu-id="372b7-127">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="372b7-127">nvarchar(256)</span></span>  <br/> ||<span data-ttu-id="372b7-128">Description du code de réponse SIP.</span><span class="sxs-lookup"><span data-stu-id="372b7-128">Description of the SIP response code.</span></span> <span data-ttu-id="372b7-129">Par exemple, le code de réponse 181 contient la description suivante :</span><span class="sxs-lookup"><span data-stu-id="372b7-129">For example, response code 181 has the following description:</span></span>  <br/> <span data-ttu-id="372b7-130">Appel en cours de transfert</span><span class="sxs-lookup"><span data-stu-id="372b7-130">Call Is Being Forwarded</span></span>  <br/> |
   

