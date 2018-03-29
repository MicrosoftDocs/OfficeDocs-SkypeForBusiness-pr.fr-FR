---
title: Table de MCU dans Skype pour Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 271b7963-8fd8-4d92-a701-1a62aaf895ee
description: La table MCU est une table de prise en charge. Chaque enregistrement contient des informations sur un service de conférence. Il peut s’agir du service de conférence de la messagerie instantanée et le service de conférences téléphoniques (qui s’exécutent en tant que processus sur les serveurs frontaux), le service de conférence Web et A / V Conferencing service.
ms.openlocfilehash: 2a85d46e733d230dc7c8096c8804146b19766bcf
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="mcus-table-in-skype-for-business-server-2015"></a><span data-ttu-id="2cac5-105">Table de MCU dans Skype pour Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="2cac5-105">Mcus table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="2cac5-106">La table MCU est une table de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="2cac5-106">The Mcus table is a supporting table.</span></span> <span data-ttu-id="2cac5-107">Chaque enregistrement contient des informations sur un service de conférence.</span><span class="sxs-lookup"><span data-stu-id="2cac5-107">Each record stores information about one conferencing service.</span></span> <span data-ttu-id="2cac5-108">Il peut s’agir du service de conférence de la messagerie instantanée et le service de conférences téléphoniques (qui s’exécutent en tant que processus sur les serveurs frontaux), le service de conférence Web et A / V Conferencing service.</span><span class="sxs-lookup"><span data-stu-id="2cac5-108">These can include the IM Conferencing service and the Telephony Conferencing service (which run as processes on front-end servers), and the Web Conferencing service and A/V Conferencing service.</span></span> 
  
|<span data-ttu-id="2cac5-109">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="2cac5-109">**Column**</span></span>|<span data-ttu-id="2cac5-110">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="2cac5-110">**Data Type**</span></span>|<span data-ttu-id="2cac5-111">**Index de la clé**</span><span class="sxs-lookup"><span data-stu-id="2cac5-111">**Key/Index**</span></span>|<span data-ttu-id="2cac5-112">**Détails**</span><span class="sxs-lookup"><span data-stu-id="2cac5-112">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2cac5-113">**McuId**</span><span class="sxs-lookup"><span data-stu-id="2cac5-113">**McuId**</span></span> <br/> |<span data-ttu-id="2cac5-114">int</span><span class="sxs-lookup"><span data-stu-id="2cac5-114">int</span></span>  <br/> |<span data-ttu-id="2cac5-115">Principal</span><span class="sxs-lookup"><span data-stu-id="2cac5-115">Primary</span></span>  <br/> |<span data-ttu-id="2cac5-116">Numéro unique qui identifie ce serveur de conférence.</span><span class="sxs-lookup"><span data-stu-id="2cac5-116">Unique number identifying this conferencing server.</span></span>  <br/> |
|<span data-ttu-id="2cac5-117">**McuUri**</span><span class="sxs-lookup"><span data-stu-id="2cac5-117">**McuUri**</span></span> <br/> |<span data-ttu-id="2cac5-118">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="2cac5-118">nvarchar(450)</span></span>  <br/> | <br/> | <br/> |
|<span data-ttu-id="2cac5-119">**McuTypeId**</span><span class="sxs-lookup"><span data-stu-id="2cac5-119">**McuTypeId**</span></span> <br/> |<span data-ttu-id="2cac5-120">inyint</span><span class="sxs-lookup"><span data-stu-id="2cac5-120">inyint</span></span>  <br/> | <span data-ttu-id="2cac5-121">Étrangère</span><span class="sxs-lookup"><span data-stu-id="2cac5-121">Foreign</span></span> <br/> |<span data-ttu-id="2cac5-122">Type de serveur de conférence, par exemple conf:chat (pour IMs) ou conf:audio-vidéo.</span><span class="sxs-lookup"><span data-stu-id="2cac5-122">Conferencing server type, such as conf:chat (for IMs) or conf:audio-video.</span></span> <span data-ttu-id="2cac5-123">Consultez le [tableau de UriTypes](uritypes.md) pour plus d’informations.</span><span class="sxs-lookup"><span data-stu-id="2cac5-123">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

