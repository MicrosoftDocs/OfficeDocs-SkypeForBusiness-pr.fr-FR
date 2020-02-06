---
title: Affichage ConferenceMessageCount
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
ms.assetid: 8ee3ee95-fb78-4d4e-bcdd-6ce5a0a23b44
description: Le mode ConferenceMessageCount stocke les informations sur le nombre de messages envoyés par un utilisateur à une conférence. Cet affichage a été présenté dans Microsoft Lync Server 2013.
ms.openlocfilehash: a766e63fbca5c30cec3c3891c9ccfc2355f16d2d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815382"
---
# <a name="conferencemessagecount-view"></a><span data-ttu-id="c5a18-104">Affichage ConferenceMessageCount</span><span class="sxs-lookup"><span data-stu-id="c5a18-104">ConferenceMessageCount view</span></span>
 
<span data-ttu-id="c5a18-105">Le mode ConferenceMessageCount stocke les informations sur le nombre de messages envoyés par un utilisateur à une conférence.</span><span class="sxs-lookup"><span data-stu-id="c5a18-105">The ConferenceMessageCount view stores information about how many messages were sent by a user to a conference.</span></span> <span data-ttu-id="c5a18-106">Cet affichage a été présenté dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c5a18-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c5a18-107">Le mode ConferenceMessageCount contient toutes les colonnes de la [vue ConferenceSessionDetails](conferencesessiondetails.md) , en plus des colonnes répertoriées ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="c5a18-107">The ConferenceMessageCount view contains all of the columns in the [ConferenceSessionDetails view](conferencesessiondetails.md) in addition the columns listed below.</span></span>
  
|<span data-ttu-id="c5a18-108">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="c5a18-108">**Column**</span></span>|<span data-ttu-id="c5a18-109">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="c5a18-109">**Data Type**</span></span>|<span data-ttu-id="c5a18-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="c5a18-110">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c5a18-111">**UserUri**</span><span class="sxs-lookup"><span data-stu-id="c5a18-111">**UserUri**</span></span> <br/> |<span data-ttu-id="c5a18-112">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="c5a18-112">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="c5a18-113">URI de l’utilisateur qui a envoyé le message.</span><span class="sxs-lookup"><span data-stu-id="c5a18-113">URI of the user who sent the message.</span></span>  <br/> |
|<span data-ttu-id="c5a18-114">**UserUriType**</span><span class="sxs-lookup"><span data-stu-id="c5a18-114">**UserUriType**</span></span> <br/> |<span data-ttu-id="c5a18-115">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="c5a18-115">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="c5a18-116">Type d’URI de l’utilisateur qui a envoyé les messages.</span><span class="sxs-lookup"><span data-stu-id="c5a18-116">Type of URI of the user who sent the messages.</span></span> <span data-ttu-id="c5a18-117">Pour plus d’informations, voir la [table UriTypes](uritypes.md) .</span><span class="sxs-lookup"><span data-stu-id="c5a18-117">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
|<span data-ttu-id="c5a18-118">**UserTenant**</span><span class="sxs-lookup"><span data-stu-id="c5a18-118">**UserTenant**</span></span> <br/> |<span data-ttu-id="c5a18-119">identificateur</span><span class="sxs-lookup"><span data-stu-id="c5a18-119">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="c5a18-120">Client de l’utilisateur qui a envoyé les messages.</span><span class="sxs-lookup"><span data-stu-id="c5a18-120">Tenant of user who sent the messages.</span></span> <span data-ttu-id="c5a18-121">Pour plus d’informations, voir la [table locataires](tenants.md) .</span><span class="sxs-lookup"><span data-stu-id="c5a18-121">See the [Tenants table](tenants.md) for more information.</span></span> <br/> |
|<span data-ttu-id="c5a18-122">**UserMessageCount**</span><span class="sxs-lookup"><span data-stu-id="c5a18-122">**UserMessageCount**</span></span> <br/> |<span data-ttu-id="c5a18-123">type</span><span class="sxs-lookup"><span data-stu-id="c5a18-123">smallint</span></span>  <br/> |<span data-ttu-id="c5a18-124">Nombre de messages envoyés par l’utilisateur au cours de la session de conférence.</span><span class="sxs-lookup"><span data-stu-id="c5a18-124">Number of messages sent by the user during the conference session.</span></span>  <br/> |
   

