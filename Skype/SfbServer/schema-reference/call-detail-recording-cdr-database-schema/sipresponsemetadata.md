---
title: Table SIPResponseMetaData
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: cf723737-4a75-4352-829b-f4954aa59716
description: La table SIPResponseMetaDataTable contient la liste des codes de réponse SIP et les classification et définition de chacun de ces codes. Ceux-ci sont générés en réponse aux événements affectant les périphériques SIP et les sessions de communication SIP. Par exemple, le code de réponse 403 est généré quand un périphérique SIP effectue une requête, mais que le serveur refuse d’honorer cette requête.
ms.openlocfilehash: 3d6714e9c5b5c154d19381fad33821b02ec8a73e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809924"
---
# <a name="sipresponsemetadata-table"></a><span data-ttu-id="65345-104">Table SIPResponseMetaData</span><span class="sxs-lookup"><span data-stu-id="65345-104">SIPResponseMetaData table</span></span>
 
<span data-ttu-id="65345-p102">La table SIPResponseMetaDataTable contient la liste des codes de réponse SIP et les classification et définition de chacun de ces codes. Ceux-ci sont générés en réponse aux événements affectant les périphériques SIP et les sessions de communication SIP. Par exemple, le code de réponse 403 est généré quand un périphérique SIP effectue une requête, mais que le serveur refuse d’honorer cette requête.</span><span class="sxs-lookup"><span data-stu-id="65345-p102">The SIPResponseMetaDataTable contains a list of SIP response codes and the classification and definition of each of those codes. These codes are generated in response to events affecting SIP devices and SIP communication sessions; for example, the response code 403 is generated when a SIP device makes a request, but the server declines to honor that request.</span></span>
  
<span data-ttu-id="65345-107">Ce tableau a été introduit dans Skype Entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="65345-107">This table was introduced in Skype for Business Server 2015.</span></span>
  
|<span data-ttu-id="65345-108">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="65345-108">**Column**</span></span>|<span data-ttu-id="65345-109">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="65345-109">**Data Type**</span></span>|<span data-ttu-id="65345-110">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="65345-110">**Key/Index**</span></span>|<span data-ttu-id="65345-111">**Détails**</span><span class="sxs-lookup"><span data-stu-id="65345-111">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="65345-112">**ResponseCode**</span><span class="sxs-lookup"><span data-stu-id="65345-112">**ResponseCode**</span></span> <br/> |<span data-ttu-id="65345-113">int</span><span class="sxs-lookup"><span data-stu-id="65345-113">int</span></span>  <br/> |<span data-ttu-id="65345-114">Primaire</span><span class="sxs-lookup"><span data-stu-id="65345-114">Primary</span></span>  <br/> |<span data-ttu-id="65345-115">Valeur numérique qui représente le code de réponse SIP.</span><span class="sxs-lookup"><span data-stu-id="65345-115">Numeric value that represents the SIP response code.</span></span>  <br/> |
|<span data-ttu-id="65345-116">**Classe**</span><span class="sxs-lookup"><span data-stu-id="65345-116">**Class**</span></span> <br/> |<span data-ttu-id="65345-117">int</span><span class="sxs-lookup"><span data-stu-id="65345-117">int</span></span>  <br/> || <span data-ttu-id="65345-p103">Classification générale pour le code de réponse. Les classifications comprennent :</span><span class="sxs-lookup"><span data-stu-id="65345-p103">General classification for the response code. Classifications include:</span></span> <br/>  <span data-ttu-id="65345-120">1 - Réponses d’information</span><span class="sxs-lookup"><span data-stu-id="65345-120">1 - Informational Responses</span></span> <br/>  <span data-ttu-id="65345-121">2 - Réponses réussies</span><span class="sxs-lookup"><span data-stu-id="65345-121">2 - Successful Responses</span></span> <br/>  <span data-ttu-id="65345-122">3 - Réponses de redirection</span><span class="sxs-lookup"><span data-stu-id="65345-122">3 - Redirection Responses</span></span> <br/>  <span data-ttu-id="65345-123">4 - Réponses d’échec du client</span><span class="sxs-lookup"><span data-stu-id="65345-123">4 - Client Failure Responses</span></span> <br/>  <span data-ttu-id="65345-124">5 -- Réponses de défaillance du serveur</span><span class="sxs-lookup"><span data-stu-id="65345-124">5 -- Server Failure Responses</span></span> <br/>  <span data-ttu-id="65345-125">6 - Réponse d’échec global</span><span class="sxs-lookup"><span data-stu-id="65345-125">6 - Global Failure Response</span></span> <br/> |
|<span data-ttu-id="65345-126">**Description**</span><span class="sxs-lookup"><span data-stu-id="65345-126">**Description**</span></span> <br/> |<span data-ttu-id="65345-127">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="65345-127">nvarchar(256)</span></span>  <br/> ||<span data-ttu-id="65345-p104">Description du code de réponse SIP. Par exemple, le code de réponse 181 a la description suivante :</span><span class="sxs-lookup"><span data-stu-id="65345-p104">Description of the SIP response code. For example, response code 181 has the following description:</span></span>  <br/> <span data-ttu-id="65345-130">L’appel est en cours de transfert</span><span class="sxs-lookup"><span data-stu-id="65345-130">Call Is Being Forwarded</span></span>  <br/> |
   

