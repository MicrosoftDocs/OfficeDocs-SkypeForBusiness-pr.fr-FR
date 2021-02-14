---
title: Table Mcus dans Skype Entreprise Server 2015
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
ms.assetid: 271b7963-8fd8-4d92-a701-1a62aaf895ee
description: La table Mcus est une table de prise en charge. Chaque enregistrement stocke des informations sur un service de conférence. Il peut s’agir du service de conférence par messagerie instantanée et du service de conférence téléphonique (qui s’exécutent en tant que processus sur les serveurs frontaux), du service de conférence Web et du service de conférence A/V.
ms.openlocfilehash: fe43bfc747cd08febe00a68925ad520b6add5846
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821424"
---
# <a name="mcus-table-in-skype-for-business-server-2015"></a><span data-ttu-id="d83d8-105">Table Mcus dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="d83d8-105">Mcus table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="d83d8-106">La table Mcus est une table de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="d83d8-106">The Mcus table is a supporting table.</span></span> <span data-ttu-id="d83d8-107">Chaque enregistrement stocke des informations sur un service de conférence.</span><span class="sxs-lookup"><span data-stu-id="d83d8-107">Each record stores information about one conferencing service.</span></span> <span data-ttu-id="d83d8-108">Il peut s’agir du service de conférence par messagerie instantanée et du service de conférence téléphonique (qui s’exécutent en tant que processus sur les serveurs frontaux), du service de conférence Web et du service de conférence A/V.</span><span class="sxs-lookup"><span data-stu-id="d83d8-108">These can include the IM Conferencing service and the Telephony Conferencing service (which run as processes on front-end servers), and the Web Conferencing service and A/V Conferencing service.</span></span> 
  
|<span data-ttu-id="d83d8-109">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="d83d8-109">**Column**</span></span>|<span data-ttu-id="d83d8-110">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="d83d8-110">**Data Type**</span></span>|<span data-ttu-id="d83d8-111">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="d83d8-111">**Key/Index**</span></span>|<span data-ttu-id="d83d8-112">**Détails**</span><span class="sxs-lookup"><span data-stu-id="d83d8-112">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d83d8-113">**McuId**</span><span class="sxs-lookup"><span data-stu-id="d83d8-113">**McuId**</span></span> <br/> |<span data-ttu-id="d83d8-114">int</span><span class="sxs-lookup"><span data-stu-id="d83d8-114">int</span></span>  <br/> |<span data-ttu-id="d83d8-115">Primaire</span><span class="sxs-lookup"><span data-stu-id="d83d8-115">Primary</span></span>  <br/> |<span data-ttu-id="d83d8-116">Numéro unique identifiant ce serveur de conférence.</span><span class="sxs-lookup"><span data-stu-id="d83d8-116">Unique number identifying this conferencing server.</span></span>  <br/> |
|<span data-ttu-id="d83d8-117">**McuUri**</span><span class="sxs-lookup"><span data-stu-id="d83d8-117">**McuUri**</span></span> <br/> |<span data-ttu-id="d83d8-118">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="d83d8-118">nvarchar(450)</span></span>  <br/> | <br/> | <br/> |
|<span data-ttu-id="d83d8-119">**McuTypeId**</span><span class="sxs-lookup"><span data-stu-id="d83d8-119">**McuTypeId**</span></span> <br/> |<span data-ttu-id="d83d8-120">inynt</span><span class="sxs-lookup"><span data-stu-id="d83d8-120">inyint</span></span>  <br/> | <span data-ttu-id="d83d8-121">Étranger</span><span class="sxs-lookup"><span data-stu-id="d83d8-121">Foreign</span></span> <br/> |<span data-ttu-id="d83d8-122">Type de serveur de conférence, tel que conf:chat (pour les IM) ou conf:audio-video.</span><span class="sxs-lookup"><span data-stu-id="d83d8-122">Conferencing server type, such as conf:chat (for IMs) or conf:audio-video.</span></span> <span data-ttu-id="d83d8-123">Pour plus [d’informations, voir la table UriTypes.](uritypes.md)</span><span class="sxs-lookup"><span data-stu-id="d83d8-123">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

