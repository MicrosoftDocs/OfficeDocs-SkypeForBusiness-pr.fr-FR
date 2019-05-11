---
title: Table Mcus dans Skype pour Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 271b7963-8fd8-4d92-a701-1a62aaf895ee
description: Le tableau de MCU est une table de prise en charge. Chaque enregistrement stocke des informations sur un service de conférence. Il peut s’agir le service de conférence par messagerie instantanée et le service de téléconférence (ce qui s’exécutent en tant que processus sur les serveurs frontaux) et que le service de conférence Web et A / service de conférence V.
ms.openlocfilehash: 6b5df793008fcf7586d62cab77a1b362848374ac
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930671"
---
# <a name="mcus-table-in-skype-for-business-server-2015"></a><span data-ttu-id="513d2-105">Table Mcus dans Skype pour Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="513d2-105">Mcus table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="513d2-106">Le tableau de MCU est une table de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="513d2-106">The Mcus table is a supporting table.</span></span> <span data-ttu-id="513d2-107">Chaque enregistrement stocke des informations sur un service de conférence.</span><span class="sxs-lookup"><span data-stu-id="513d2-107">Each record stores information about one conferencing service.</span></span> <span data-ttu-id="513d2-108">Il peut s’agir le service de conférence par messagerie instantanée et le service de téléconférence (ce qui s’exécutent en tant que processus sur les serveurs frontaux) et que le service de conférence Web et A / service de conférence V.</span><span class="sxs-lookup"><span data-stu-id="513d2-108">These can include the IM Conferencing service and the Telephony Conferencing service (which run as processes on front-end servers), and the Web Conferencing service and A/V Conferencing service.</span></span> 
  
|<span data-ttu-id="513d2-109">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="513d2-109">**Column**</span></span>|<span data-ttu-id="513d2-110">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="513d2-110">**Data Type**</span></span>|<span data-ttu-id="513d2-111">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="513d2-111">**Key/Index**</span></span>|<span data-ttu-id="513d2-112">**Détails**</span><span class="sxs-lookup"><span data-stu-id="513d2-112">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="513d2-113">**McuId**</span><span class="sxs-lookup"><span data-stu-id="513d2-113">**McuId**</span></span> <br/> |<span data-ttu-id="513d2-114">int</span><span class="sxs-lookup"><span data-stu-id="513d2-114">int</span></span>  <br/> |<span data-ttu-id="513d2-115">Principal</span><span class="sxs-lookup"><span data-stu-id="513d2-115">Primary</span></span>  <br/> |<span data-ttu-id="513d2-116">Numéro unique identifiant ce serveur de conférence.</span><span class="sxs-lookup"><span data-stu-id="513d2-116">Unique number identifying this conferencing server.</span></span>  <br/> |
|<span data-ttu-id="513d2-117">**McuUri**</span><span class="sxs-lookup"><span data-stu-id="513d2-117">**McuUri**</span></span> <br/> |<span data-ttu-id="513d2-118">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="513d2-118">nvarchar(450)</span></span>  <br/> | <br/> | <br/> |
|<span data-ttu-id="513d2-119">**McuTypeId**</span><span class="sxs-lookup"><span data-stu-id="513d2-119">**McuTypeId**</span></span> <br/> |<span data-ttu-id="513d2-120">inyint</span><span class="sxs-lookup"><span data-stu-id="513d2-120">inyint</span></span>  <br/> | <span data-ttu-id="513d2-121">Étrangère</span><span class="sxs-lookup"><span data-stu-id="513d2-121">Foreign</span></span> <br/> |<span data-ttu-id="513d2-122">Type de serveur de conférence, tel que conf:chat (pour les messages instantanés) ou conf:audio-vidéo.</span><span class="sxs-lookup"><span data-stu-id="513d2-122">Conferencing server type, such as conf:chat (for IMs) or conf:audio-video.</span></span> <span data-ttu-id="513d2-123">Consultez la [table UriTypes](uritypes.md) pour plus d’informations.</span><span class="sxs-lookup"><span data-stu-id="513d2-123">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

