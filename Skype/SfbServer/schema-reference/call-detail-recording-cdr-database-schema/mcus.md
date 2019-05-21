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
localization_priority: Normal
ms.assetid: 271b7963-8fd8-4d92-a701-1a62aaf895ee
description: La table MCU est une table de support. Chaque enregistrement stocke les informations relatives à un service de conférence. Il peut s’agir du service de conférence par messagerie instantanée et du service de conférence téléphonique (qui s’exécutent sous forme de processus sur les serveurs frontaux), du service de conférence Web et du service de conférence A/V.
ms.openlocfilehash: fcd12bcc8da7aa6513d78e1a9c4a6f11930065aa
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296041"
---
# <a name="mcus-table-in-skype-for-business-server-2015"></a><span data-ttu-id="0c86b-105">Table MCU dans Skype entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="0c86b-105">Mcus table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="0c86b-106">La table MCU est une table de support.</span><span class="sxs-lookup"><span data-stu-id="0c86b-106">The Mcus table is a supporting table.</span></span> <span data-ttu-id="0c86b-107">Chaque enregistrement stocke les informations relatives à un service de conférence.</span><span class="sxs-lookup"><span data-stu-id="0c86b-107">Each record stores information about one conferencing service.</span></span> <span data-ttu-id="0c86b-108">Il peut s’agir du service de conférence par messagerie instantanée et du service de conférence téléphonique (qui s’exécutent sous forme de processus sur les serveurs frontaux), du service de conférence Web et du service de conférence A/V.</span><span class="sxs-lookup"><span data-stu-id="0c86b-108">These can include the IM Conferencing service and the Telephony Conferencing service (which run as processes on front-end servers), and the Web Conferencing service and A/V Conferencing service.</span></span> 
  
|<span data-ttu-id="0c86b-109">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="0c86b-109">**Column**</span></span>|<span data-ttu-id="0c86b-110">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="0c86b-110">**Data Type**</span></span>|<span data-ttu-id="0c86b-111">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="0c86b-111">**Key/Index**</span></span>|<span data-ttu-id="0c86b-112">**Détails**</span><span class="sxs-lookup"><span data-stu-id="0c86b-112">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="0c86b-113">**McuId**</span><span class="sxs-lookup"><span data-stu-id="0c86b-113">**McuId**</span></span> <br/> |<span data-ttu-id="0c86b-114">int</span><span class="sxs-lookup"><span data-stu-id="0c86b-114">int</span></span>  <br/> |<span data-ttu-id="0c86b-115">Principal</span><span class="sxs-lookup"><span data-stu-id="0c86b-115">Primary</span></span>  <br/> |<span data-ttu-id="0c86b-116">Numéro unique identifiant ce serveur de conférence.</span><span class="sxs-lookup"><span data-stu-id="0c86b-116">Unique number identifying this conferencing server.</span></span>  <br/> |
|<span data-ttu-id="0c86b-117">**McuUri**</span><span class="sxs-lookup"><span data-stu-id="0c86b-117">**McuUri**</span></span> <br/> |<span data-ttu-id="0c86b-118">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="0c86b-118">nvarchar(450)</span></span>  <br/> | <br/> | <br/> |
|<span data-ttu-id="0c86b-119">**McuTypeId**</span><span class="sxs-lookup"><span data-stu-id="0c86b-119">**McuTypeId**</span></span> <br/> |<span data-ttu-id="0c86b-120">inyint</span><span class="sxs-lookup"><span data-stu-id="0c86b-120">inyint</span></span>  <br/> | <span data-ttu-id="0c86b-121">Externes</span><span class="sxs-lookup"><span data-stu-id="0c86b-121">Foreign</span></span> <br/> |<span data-ttu-id="0c86b-122">Le type de serveur de conférence, tel que conf: chat (pour les messages instantanés) ou conf: audio-vidéo.</span><span class="sxs-lookup"><span data-stu-id="0c86b-122">Conferencing server type, such as conf:chat (for IMs) or conf:audio-video.</span></span> <span data-ttu-id="0c86b-123">Pour plus d’informations, voir la [table UriTypes](uritypes.md) .</span><span class="sxs-lookup"><span data-stu-id="0c86b-123">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

