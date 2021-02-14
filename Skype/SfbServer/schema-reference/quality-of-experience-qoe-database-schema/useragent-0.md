---
title: Affichage UserAgent
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
ms.assetid: b986f76f-f16e-4e5e-96cb-6e8f7f9b42ee
description: L’affichage UserAgent stocke les informations relatives aux agents utilisateur qui ont été impliqués dans des sessions ayant des enregistrements dans la base de données. Cette vue a été introduite dans Microsoft Lync Server 2013.
ms.openlocfilehash: 90db61df5bd947b101823172602103e47d4182a9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49800014"
---
# <a name="useragent-view"></a><span data-ttu-id="44783-104">Affichage UserAgent</span><span class="sxs-lookup"><span data-stu-id="44783-104">UserAgent view</span></span>
 
<span data-ttu-id="44783-105">L’affichage UserAgent stocke les informations relatives aux agents utilisateur qui ont été impliqués dans des sessions ayant des enregistrements dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="44783-105">The UserAgent View stores information about the user agents that have been involved in sessions that have records in the database.</span></span> <span data-ttu-id="44783-106">Cette vue a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="44783-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="44783-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="44783-107">**Column**</span></span>|<span data-ttu-id="44783-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="44783-108">**Data Type**</span></span>|<span data-ttu-id="44783-109">**Détails**</span><span class="sxs-lookup"><span data-stu-id="44783-109">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="44783-110">UserAgentKey</span><span class="sxs-lookup"><span data-stu-id="44783-110">UserAgentKey</span></span>  <br/> |<span data-ttu-id="44783-111">int</span><span class="sxs-lookup"><span data-stu-id="44783-111">int</span></span>  <br/> |<span data-ttu-id="44783-112">Numéro unique qui identifie cet agent utilisateur.</span><span class="sxs-lookup"><span data-stu-id="44783-112">Unique number identifying this user agent.</span></span>  <br/> |
|<span data-ttu-id="44783-113">UserAgent</span><span class="sxs-lookup"><span data-stu-id="44783-113">UserAgent</span></span>  <br/> |<span data-ttu-id="44783-114">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="44783-114">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="44783-115">Chaîne d’agent utilisateur.</span><span class="sxs-lookup"><span data-stu-id="44783-115">User agent string.</span></span>  <br/> |
|<span data-ttu-id="44783-116">UAType</span><span class="sxs-lookup"><span data-stu-id="44783-116">UAType</span></span>  <br/> |<span data-ttu-id="44783-117">smallint</span><span class="sxs-lookup"><span data-stu-id="44783-117">smallint</span></span>  <br/> |<span data-ttu-id="44783-118">Type d’agent utilisateur.</span><span class="sxs-lookup"><span data-stu-id="44783-118">Type of user agent.</span></span> <span data-ttu-id="44783-119">Pour plus [d’informations, voir le tableau UserAgent.](useragent.md)</span><span class="sxs-lookup"><span data-stu-id="44783-119">See the [UserAgent table](useragent.md) for more details.</span></span> <br/> |
|<span data-ttu-id="44783-120">UACategory</span><span class="sxs-lookup"><span data-stu-id="44783-120">UACategory</span></span>  <br/> |<span data-ttu-id="44783-121">nvarchar(64)</span><span class="sxs-lookup"><span data-stu-id="44783-121">nvarchar(64)</span></span>  <br/> |<span data-ttu-id="44783-p104">Catégorie à laquelle appartient l’agent utilisateur. Par exemple, l’agent utilisateur Conferencing_Attendant_1.0 appartient au standard automatique de conférence (CAA) UACategory.</span><span class="sxs-lookup"><span data-stu-id="44783-p104">Category that the user agent belongs to. For example, the user agent Conferencing_Attendant_1.0 belongs to the UACategory CAA.</span></span>  <br/> |
   

