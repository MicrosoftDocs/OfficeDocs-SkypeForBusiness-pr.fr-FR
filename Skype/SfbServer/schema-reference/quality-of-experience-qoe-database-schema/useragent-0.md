---
title: Vue UserAgent
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b986f76f-f16e-4e5e-96cb-6e8f7f9b42ee
description: La vue UserAgent stocke des informations sur les agents utilisateurs qui ont participé à des sessions disposant d’enregistrements dans la base de données. Cet affichage a été introduit dans Microsoft Lync Server 2013.
ms.openlocfilehash: c63873f219f5d741925339f52f949be55fc64411
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212066"
---
# <a name="useragent-view"></a><span data-ttu-id="77fbc-104">Vue UserAgent</span><span class="sxs-lookup"><span data-stu-id="77fbc-104">UserAgent view</span></span>
 
<span data-ttu-id="77fbc-105">La vue UserAgent stocke des informations sur les agents utilisateurs qui ont participé à des sessions disposant d’enregistrements dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="77fbc-105">The UserAgent View stores information about the user agents that have been involved in sessions that have records in the database.</span></span> <span data-ttu-id="77fbc-106">Cet affichage a été introduit dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="77fbc-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="77fbc-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="77fbc-107">**Column**</span></span>|<span data-ttu-id="77fbc-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="77fbc-108">**Data Type**</span></span>|<span data-ttu-id="77fbc-109">**Détails**</span><span class="sxs-lookup"><span data-stu-id="77fbc-109">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="77fbc-110">UserAgentKey</span><span class="sxs-lookup"><span data-stu-id="77fbc-110">UserAgentKey</span></span>  <br/> |<span data-ttu-id="77fbc-111">int</span><span class="sxs-lookup"><span data-stu-id="77fbc-111">int</span></span>  <br/> |<span data-ttu-id="77fbc-112">Numéro unique identifiant cet agent utilisateur.</span><span class="sxs-lookup"><span data-stu-id="77fbc-112">Unique number identifying this user agent.</span></span>  <br/> |
|<span data-ttu-id="77fbc-113">UserAgent</span><span class="sxs-lookup"><span data-stu-id="77fbc-113">UserAgent</span></span>  <br/> |<span data-ttu-id="77fbc-114">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="77fbc-114">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="77fbc-115">Chaîne d’agent utilisateur.</span><span class="sxs-lookup"><span data-stu-id="77fbc-115">User agent string.</span></span>  <br/> |
|<span data-ttu-id="77fbc-116">UAType</span><span class="sxs-lookup"><span data-stu-id="77fbc-116">UAType</span></span>  <br/> |<span data-ttu-id="77fbc-117">smallint</span><span class="sxs-lookup"><span data-stu-id="77fbc-117">smallint</span></span>  <br/> |<span data-ttu-id="77fbc-118">Type d’agent utilisateur.</span><span class="sxs-lookup"><span data-stu-id="77fbc-118">Type of user agent.</span></span> <span data-ttu-id="77fbc-119">Voir la [table UserAgent](useragent.md) pour plus d’informations.</span><span class="sxs-lookup"><span data-stu-id="77fbc-119">See the [UserAgent table](useragent.md) for more details.</span></span> <br/> |
|<span data-ttu-id="77fbc-120">UACategory</span><span class="sxs-lookup"><span data-stu-id="77fbc-120">UACategory</span></span>  <br/> |<span data-ttu-id="77fbc-121">nvarchar(64)</span><span class="sxs-lookup"><span data-stu-id="77fbc-121">nvarchar(64)</span></span>  <br/> |<span data-ttu-id="77fbc-122">Catégorie à laquelle appartient l’agent utilisateur.</span><span class="sxs-lookup"><span data-stu-id="77fbc-122">Category that the user agent belongs to.</span></span> <span data-ttu-id="77fbc-123">Par exemple, l’agent utilisateur Conferencing_Attendant_1.0 appartient à la CAA UACategory.</span><span class="sxs-lookup"><span data-stu-id="77fbc-123">For example, the user agent Conferencing_Attendant_1.0 belongs to the UACategory CAA.</span></span>  <br/> |
   

