---
title: Affichage UserAgent
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b986f76f-f16e-4e5e-96cb-6e8f7f9b42ee
description: L’affichage UserAgent stocke les informations sur les agents utilisateur impliqués dans les sessions qui contiennent des enregistrements dans la base de données. Cet affichage a été présenté dans Microsoft Lync Server 2013.
ms.openlocfilehash: 874a9c986ec77c3e19b557cd65dcf6dbeb045752
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294606"
---
# <a name="useragent-view"></a><span data-ttu-id="905e6-104">Affichage UserAgent</span><span class="sxs-lookup"><span data-stu-id="905e6-104">UserAgent view</span></span>
 
<span data-ttu-id="905e6-105">L’affichage UserAgent stocke les informations sur les agents utilisateur impliqués dans les sessions qui contiennent des enregistrements dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="905e6-105">The UserAgent View stores information about the user agents that have been involved in sessions that have records in the database.</span></span> <span data-ttu-id="905e6-106">Cet affichage a été présenté dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="905e6-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="905e6-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="905e6-107">**Column**</span></span>|<span data-ttu-id="905e6-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="905e6-108">**Data Type**</span></span>|<span data-ttu-id="905e6-109">**Détails**</span><span class="sxs-lookup"><span data-stu-id="905e6-109">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="905e6-110">UserAgentKey</span><span class="sxs-lookup"><span data-stu-id="905e6-110">UserAgentKey</span></span>  <br/> |<span data-ttu-id="905e6-111">int</span><span class="sxs-lookup"><span data-stu-id="905e6-111">int</span></span>  <br/> |<span data-ttu-id="905e6-112">Numéro unique identifiant cet agent utilisateur.</span><span class="sxs-lookup"><span data-stu-id="905e6-112">Unique number identifying this user agent.</span></span>  <br/> |
|<span data-ttu-id="905e6-113">UserAgent</span><span class="sxs-lookup"><span data-stu-id="905e6-113">UserAgent</span></span>  <br/> |<span data-ttu-id="905e6-114">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="905e6-114">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="905e6-115">Chaîne de l’agent utilisateur.</span><span class="sxs-lookup"><span data-stu-id="905e6-115">User agent string.</span></span>  <br/> |
|<span data-ttu-id="905e6-116">UAType</span><span class="sxs-lookup"><span data-stu-id="905e6-116">UAType</span></span>  <br/> |<span data-ttu-id="905e6-117">type</span><span class="sxs-lookup"><span data-stu-id="905e6-117">smallint</span></span>  <br/> |<span data-ttu-id="905e6-118">Type d’agent utilisateur.</span><span class="sxs-lookup"><span data-stu-id="905e6-118">Type of user agent.</span></span> <span data-ttu-id="905e6-119">Pour plus d’informations, voir la [table UserAgent](useragent.md) .</span><span class="sxs-lookup"><span data-stu-id="905e6-119">See the [UserAgent table](useragent.md) for more details.</span></span> <br/> |
|<span data-ttu-id="905e6-120">UACategory</span><span class="sxs-lookup"><span data-stu-id="905e6-120">UACategory</span></span>  <br/> |<span data-ttu-id="905e6-121">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="905e6-121">nvarchar(64)</span></span>  <br/> |<span data-ttu-id="905e6-122">Catégorie à laquelle l’agent utilisateur appartient.</span><span class="sxs-lookup"><span data-stu-id="905e6-122">Category that the user agent belongs to.</span></span> <span data-ttu-id="905e6-123">Par exemple, l’agent utilisateur Conferencing_Attendant_ 1.0 appartient au CAA UACategory.</span><span class="sxs-lookup"><span data-stu-id="905e6-123">For example, the user agent Conferencing_Attendant_1.0 belongs to the UACategory CAA.</span></span>  <br/> |
   

