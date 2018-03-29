---
title: Affichage de UserAgent
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b986f76f-f16e-4e5e-96cb-6e8f7f9b42ee
description: La vue UserAgent stocke des informations sur les agents utilisateur qui ont été impliquées dans des sessions avec des enregistrements dans la base de données. Cette vue a été introduite dans Microsoft Lync Server 2013.
ms.openlocfilehash: 8df1d45ed1272a886a440aded79a9c4e04c1bae8
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="useragent-view"></a><span data-ttu-id="578d9-104">Affichage de UserAgent</span><span class="sxs-lookup"><span data-stu-id="578d9-104">UserAgent view</span></span>
 
<span data-ttu-id="578d9-105">La vue UserAgent stocke des informations sur les agents utilisateur qui ont été impliquées dans des sessions avec des enregistrements dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="578d9-105">The UserAgent View stores information about the user agents that have been involved in sessions that have records in the database.</span></span> <span data-ttu-id="578d9-106">Cette vue a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="578d9-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="578d9-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="578d9-107">**Column**</span></span>|<span data-ttu-id="578d9-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="578d9-108">**Data Type**</span></span>|<span data-ttu-id="578d9-109">**Détails**</span><span class="sxs-lookup"><span data-stu-id="578d9-109">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="578d9-110">UserAgentKey</span><span class="sxs-lookup"><span data-stu-id="578d9-110">UserAgentKey</span></span>  <br/> |<span data-ttu-id="578d9-111">int</span><span class="sxs-lookup"><span data-stu-id="578d9-111">int</span></span>  <br/> |<span data-ttu-id="578d9-112">Numéro unique identifiant cet agent utilisateur.</span><span class="sxs-lookup"><span data-stu-id="578d9-112">Unique number identifying this user agent.</span></span>  <br/> |
|<span data-ttu-id="578d9-113">UserAgent</span><span class="sxs-lookup"><span data-stu-id="578d9-113">UserAgent</span></span>  <br/> |<span data-ttu-id="578d9-114">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="578d9-114">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="578d9-115">Chaîne d’agent utilisateur.</span><span class="sxs-lookup"><span data-stu-id="578d9-115">User agent string.</span></span>  <br/> |
|<span data-ttu-id="578d9-116">UAType</span><span class="sxs-lookup"><span data-stu-id="578d9-116">UAType</span></span>  <br/> |<span data-ttu-id="578d9-117">smallint</span><span class="sxs-lookup"><span data-stu-id="578d9-117">smallint</span></span>  <br/> |<span data-ttu-id="578d9-118">Type de l’agent utilisateur.</span><span class="sxs-lookup"><span data-stu-id="578d9-118">Type of user agent.</span></span> <span data-ttu-id="578d9-119">Consultez le [tableau de UserAgent](useragent.md) pour plus de détails.</span><span class="sxs-lookup"><span data-stu-id="578d9-119">See the [UserAgent table](useragent.md) for more details.</span></span> <br/> |
|<span data-ttu-id="578d9-120">UACategory</span><span class="sxs-lookup"><span data-stu-id="578d9-120">UACategory</span></span>  <br/> |<span data-ttu-id="578d9-121">nvarchar(64)</span><span class="sxs-lookup"><span data-stu-id="578d9-121">nvarchar(64)</span></span>  <br/> |<span data-ttu-id="578d9-122">Catégorie à laquelle appartient l’agent utilisateur.</span><span class="sxs-lookup"><span data-stu-id="578d9-122">Category that the user agent belongs to.</span></span> <span data-ttu-id="578d9-123">Par exemple, l’agent utilisateur Conferencing_Attendant_1.0 appartient à la TCHA UACategory.</span><span class="sxs-lookup"><span data-stu-id="578d9-123">For example, the user agent Conferencing_Attendant_1.0 belongs to the UACategory CAA.</span></span>  <br/> |
   

