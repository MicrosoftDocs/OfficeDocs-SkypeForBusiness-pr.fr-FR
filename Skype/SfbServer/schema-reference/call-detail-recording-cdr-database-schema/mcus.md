---
title: Table MCU dans Skype entreprise Server 2015
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
ms.assetid: 271b7963-8fd8-4d92-a701-1a62aaf895ee
description: La table MCU est une table de support. Chaque enregistrement stocke les informations relatives à un service de conférence. Il peut s’agir du service de conférence par messagerie instantanée et du service de conférence téléphonique (qui s’exécutent sous forme de processus sur les serveurs frontaux), du service de conférence Web et du service de conférence A/V.
ms.openlocfilehash: 1e5141ee2a103e540d3ac50e99de0036f31262d7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815062"
---
# <a name="mcus-table-in-skype-for-business-server-2015"></a><span data-ttu-id="b454f-105">Table MCU dans Skype entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="b454f-105">Mcus table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="b454f-106">La table MCU est une table de support.</span><span class="sxs-lookup"><span data-stu-id="b454f-106">The Mcus table is a supporting table.</span></span> <span data-ttu-id="b454f-107">Chaque enregistrement stocke les informations relatives à un service de conférence.</span><span class="sxs-lookup"><span data-stu-id="b454f-107">Each record stores information about one conferencing service.</span></span> <span data-ttu-id="b454f-108">Il peut s’agir du service de conférence par messagerie instantanée et du service de conférence téléphonique (qui s’exécutent sous forme de processus sur les serveurs frontaux), du service de conférence Web et du service de conférence A/V.</span><span class="sxs-lookup"><span data-stu-id="b454f-108">These can include the IM Conferencing service and the Telephony Conferencing service (which run as processes on front-end servers), and the Web Conferencing service and A/V Conferencing service.</span></span> 
  
|<span data-ttu-id="b454f-109">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="b454f-109">**Column**</span></span>|<span data-ttu-id="b454f-110">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="b454f-110">**Data Type**</span></span>|<span data-ttu-id="b454f-111">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="b454f-111">**Key/Index**</span></span>|<span data-ttu-id="b454f-112">**Détails**</span><span class="sxs-lookup"><span data-stu-id="b454f-112">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b454f-113">**McuId**</span><span class="sxs-lookup"><span data-stu-id="b454f-113">**McuId**</span></span> <br/> |<span data-ttu-id="b454f-114">int</span><span class="sxs-lookup"><span data-stu-id="b454f-114">int</span></span>  <br/> |<span data-ttu-id="b454f-115">Principal</span><span class="sxs-lookup"><span data-stu-id="b454f-115">Primary</span></span>  <br/> |<span data-ttu-id="b454f-116">Numéro unique identifiant ce serveur de conférence.</span><span class="sxs-lookup"><span data-stu-id="b454f-116">Unique number identifying this conferencing server.</span></span>  <br/> |
|<span data-ttu-id="b454f-117">**McuUri**</span><span class="sxs-lookup"><span data-stu-id="b454f-117">**McuUri**</span></span> <br/> |<span data-ttu-id="b454f-118">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="b454f-118">nvarchar(450)</span></span>  <br/> | <br/> | <br/> |
|<span data-ttu-id="b454f-119">**McuTypeId**</span><span class="sxs-lookup"><span data-stu-id="b454f-119">**McuTypeId**</span></span> <br/> |<span data-ttu-id="b454f-120">inyint</span><span class="sxs-lookup"><span data-stu-id="b454f-120">inyint</span></span>  <br/> | <span data-ttu-id="b454f-121">Externes</span><span class="sxs-lookup"><span data-stu-id="b454f-121">Foreign</span></span> <br/> |<span data-ttu-id="b454f-122">Le type de serveur de conférence, tel que conf : chat (pour les messages instantanés) ou conf : audio-vidéo.</span><span class="sxs-lookup"><span data-stu-id="b454f-122">Conferencing server type, such as conf:chat (for IMs) or conf:audio-video.</span></span> <span data-ttu-id="b454f-123">Pour plus d’informations, voir la [table UriTypes](uritypes.md) .</span><span class="sxs-lookup"><span data-stu-id="b454f-123">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

