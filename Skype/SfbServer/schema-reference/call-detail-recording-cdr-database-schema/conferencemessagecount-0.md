---
title: Affichage ConferenceMessageCount
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
ms.assetid: 8ee3ee95-fb78-4d4e-bcdd-6ce5a0a23b44
description: L’affichage ConferenceMessageCount stocke les informations relatives au nombre de messages envoyés par un utilisateur à une conférence. Cette vue a été introduite dans Microsoft Lync Server 2013.
ms.openlocfilehash: 8394ed37d4b85e8ec5fcda4234b4c28f4276fb17
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813294"
---
# <a name="conferencemessagecount-view"></a><span data-ttu-id="acca5-104">Affichage ConferenceMessageCount</span><span class="sxs-lookup"><span data-stu-id="acca5-104">ConferenceMessageCount view</span></span>
 
<span data-ttu-id="acca5-105">L’affichage ConferenceMessageCount stocke les informations relatives au nombre de messages envoyés par un utilisateur à une conférence.</span><span class="sxs-lookup"><span data-stu-id="acca5-105">The ConferenceMessageCount view stores information about how many messages were sent by a user to a conference.</span></span> <span data-ttu-id="acca5-106">Cette vue a été introduite dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="acca5-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="acca5-107">L’affichage ConferenceMessageCount contient toutes les colonnes de la vue [ConferenceSessionDetails](conferencesessiondetails.md) en plus des colonnes répertoriées ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="acca5-107">The ConferenceMessageCount view contains all of the columns in the [ConferenceSessionDetails view](conferencesessiondetails.md) in addition the columns listed below.</span></span>
  
|<span data-ttu-id="acca5-108">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="acca5-108">**Column**</span></span>|<span data-ttu-id="acca5-109">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="acca5-109">**Data Type**</span></span>|<span data-ttu-id="acca5-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="acca5-110">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="acca5-111">**UserUri**</span><span class="sxs-lookup"><span data-stu-id="acca5-111">**UserUri**</span></span> <br/> |<span data-ttu-id="acca5-112">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="acca5-112">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="acca5-113">URI de l’utilisateur qui a envoyé le message.</span><span class="sxs-lookup"><span data-stu-id="acca5-113">URI of the user who sent the message.</span></span>  <br/> |
|<span data-ttu-id="acca5-114">**UserUriType**</span><span class="sxs-lookup"><span data-stu-id="acca5-114">**UserUriType**</span></span> <br/> |<span data-ttu-id="acca5-115">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="acca5-115">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="acca5-116">Type d’URI de l’utilisateur qui a envoyé les messages.</span><span class="sxs-lookup"><span data-stu-id="acca5-116">Type of URI of the user who sent the messages.</span></span> <span data-ttu-id="acca5-117">Pour plus [d’informations, voir la table UriTypes.](uritypes.md)</span><span class="sxs-lookup"><span data-stu-id="acca5-117">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
|<span data-ttu-id="acca5-118">**UserTenant**</span><span class="sxs-lookup"><span data-stu-id="acca5-118">**UserTenant**</span></span> <br/> |<span data-ttu-id="acca5-119">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="acca5-119">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="acca5-120">Locataire de l’utilisateur qui a envoyé les messages.</span><span class="sxs-lookup"><span data-stu-id="acca5-120">Tenant of user who sent the messages.</span></span> <span data-ttu-id="acca5-121">Pour plus [d’informations, voir la table Tenants.](tenants.md)</span><span class="sxs-lookup"><span data-stu-id="acca5-121">See the [Tenants table](tenants.md) for more information.</span></span> <br/> |
|<span data-ttu-id="acca5-122">**UserMessageCount**</span><span class="sxs-lookup"><span data-stu-id="acca5-122">**UserMessageCount**</span></span> <br/> |<span data-ttu-id="acca5-123">smallint</span><span class="sxs-lookup"><span data-stu-id="acca5-123">smallint</span></span>  <br/> |<span data-ttu-id="acca5-124">Nombre de messages envoyés par l’utilisateur pendant la session de conférence.</span><span class="sxs-lookup"><span data-stu-id="acca5-124">Number of messages sent by the user during the conference session.</span></span>  <br/> |
   

