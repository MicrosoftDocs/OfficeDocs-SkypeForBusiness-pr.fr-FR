---
title: Vue conferencemessagecount
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ee3ee95-fb78-4d4e-bcdd-6ce5a0a23b44
description: L’affichage ConferenceMessageCount stocke des informations sur le nombre de messages envoyé par un utilisateur à une conférence. Cet affichage a été introduit dans Microsoft Lync Server 2013.
ms.openlocfilehash: f2290eef7d2738831ed3ce72c794a36659858b8b
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30874073"
---
# <a name="conferencemessagecount-view"></a><span data-ttu-id="d5f81-104">Vue conferencemessagecount</span><span class="sxs-lookup"><span data-stu-id="d5f81-104">ConferenceMessageCount view</span></span>
 
<span data-ttu-id="d5f81-105">L’affichage ConferenceMessageCount stocke des informations sur le nombre de messages envoyé par un utilisateur à une conférence.</span><span class="sxs-lookup"><span data-stu-id="d5f81-105">The ConferenceMessageCount view stores information about how many messages were sent by a user to a conference.</span></span> <span data-ttu-id="d5f81-106">Cet affichage a été introduit dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d5f81-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d5f81-107">L’affichage ConferenceMessageCount contient toutes les colonnes dans la [vue conferencesessiondetails](conferencesessiondetails.md) en plus des colonnes répertoriées ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="d5f81-107">The ConferenceMessageCount view contains all of the columns in the [ConferenceSessionDetails view](conferencesessiondetails.md) in addition the columns listed below.</span></span>
  
|<span data-ttu-id="d5f81-108">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="d5f81-108">**Column**</span></span>|<span data-ttu-id="d5f81-109">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="d5f81-109">**Data Type**</span></span>|<span data-ttu-id="d5f81-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="d5f81-110">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d5f81-111">**UserUri**</span><span class="sxs-lookup"><span data-stu-id="d5f81-111">**UserUri**</span></span> <br/> |<span data-ttu-id="d5f81-112">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="d5f81-112">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="d5f81-113">URI de l’utilisateur qui a envoyé le message.</span><span class="sxs-lookup"><span data-stu-id="d5f81-113">URI of the user who sent the message.</span></span>  <br/> |
|<span data-ttu-id="d5f81-114">**UserUriType**</span><span class="sxs-lookup"><span data-stu-id="d5f81-114">**UserUriType**</span></span> <br/> |<span data-ttu-id="d5f81-115">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="d5f81-115">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="d5f81-116">Type d’URI de l’utilisateur qui a envoyé les messages.</span><span class="sxs-lookup"><span data-stu-id="d5f81-116">Type of URI of the user who sent the messages.</span></span> <span data-ttu-id="d5f81-117">Consultez la [table UriTypes](uritypes.md) pour plus d’informations.</span><span class="sxs-lookup"><span data-stu-id="d5f81-117">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
|<span data-ttu-id="d5f81-118">**UserTenant**</span><span class="sxs-lookup"><span data-stu-id="d5f81-118">**UserTenant**</span></span> <br/> |<span data-ttu-id="d5f81-119">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="d5f81-119">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="d5f81-120">Client de l’utilisateur qui a envoyé les messages.</span><span class="sxs-lookup"><span data-stu-id="d5f81-120">Tenant of user who sent the messages.</span></span> <span data-ttu-id="d5f81-121">Consultez le [tableau des clients](tenants.md) pour plus d’informations.</span><span class="sxs-lookup"><span data-stu-id="d5f81-121">See the [Tenants table](tenants.md) for more information.</span></span> <br/> |
|<span data-ttu-id="d5f81-122">**UserMessageCount**</span><span class="sxs-lookup"><span data-stu-id="d5f81-122">**UserMessageCount**</span></span> <br/> |<span data-ttu-id="d5f81-123">smallint</span><span class="sxs-lookup"><span data-stu-id="d5f81-123">smallint</span></span>  <br/> |<span data-ttu-id="d5f81-124">Nombre de messages envoyés par l’utilisateur pendant la session de conférence.</span><span class="sxs-lookup"><span data-stu-id="d5f81-124">Number of messages sent by the user during the conference session.</span></span>  <br/> |
   

