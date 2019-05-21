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
localization_priority: Normal
ms.assetid: 8ee3ee95-fb78-4d4e-bcdd-6ce5a0a23b44
description: Le mode ConferenceMessageCount stocke les informations sur le nombre de messages envoyés par un utilisateur à une conférence. Cet affichage a été présenté dans Microsoft Lync Server 2013.
ms.openlocfilehash: 890a5912c6f828f614fbff89627c94c4e12ba7e1
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296489"
---
# <a name="conferencemessagecount-view"></a><span data-ttu-id="a4fc3-104">Affichage ConferenceMessageCount</span><span class="sxs-lookup"><span data-stu-id="a4fc3-104">ConferenceMessageCount view</span></span>
 
<span data-ttu-id="a4fc3-105">Le mode ConferenceMessageCount stocke les informations sur le nombre de messages envoyés par un utilisateur à une conférence.</span><span class="sxs-lookup"><span data-stu-id="a4fc3-105">The ConferenceMessageCount view stores information about how many messages were sent by a user to a conference.</span></span> <span data-ttu-id="a4fc3-106">Cet affichage a été présenté dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a4fc3-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a4fc3-107">Le mode ConferenceMessageCount contient toutes les colonnes de la [vue ConferenceSessionDetails](conferencesessiondetails.md) , en plus des colonnes répertoriées ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="a4fc3-107">The ConferenceMessageCount view contains all of the columns in the [ConferenceSessionDetails view](conferencesessiondetails.md) in addition the columns listed below.</span></span>
  
|<span data-ttu-id="a4fc3-108">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="a4fc3-108">**Column**</span></span>|<span data-ttu-id="a4fc3-109">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="a4fc3-109">**Data Type**</span></span>|<span data-ttu-id="a4fc3-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="a4fc3-110">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a4fc3-111">**UserUri**</span><span class="sxs-lookup"><span data-stu-id="a4fc3-111">**UserUri**</span></span> <br/> |<span data-ttu-id="a4fc3-112">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="a4fc3-112">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="a4fc3-113">URI de l’utilisateur qui a envoyé le message.</span><span class="sxs-lookup"><span data-stu-id="a4fc3-113">URI of the user who sent the message.</span></span>  <br/> |
|<span data-ttu-id="a4fc3-114">**UserUriType**</span><span class="sxs-lookup"><span data-stu-id="a4fc3-114">**UserUriType**</span></span> <br/> |<span data-ttu-id="a4fc3-115">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="a4fc3-115">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="a4fc3-116">Type d’URI de l’utilisateur qui a envoyé les messages.</span><span class="sxs-lookup"><span data-stu-id="a4fc3-116">Type of URI of the user who sent the messages.</span></span> <span data-ttu-id="a4fc3-117">Pour plus d’informations, voir la [table UriTypes](uritypes.md) .</span><span class="sxs-lookup"><span data-stu-id="a4fc3-117">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
|<span data-ttu-id="a4fc3-118">**UserTenant**</span><span class="sxs-lookup"><span data-stu-id="a4fc3-118">**UserTenant**</span></span> <br/> |<span data-ttu-id="a4fc3-119">identificateur</span><span class="sxs-lookup"><span data-stu-id="a4fc3-119">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="a4fc3-120">Client de l’utilisateur qui a envoyé les messages.</span><span class="sxs-lookup"><span data-stu-id="a4fc3-120">Tenant of user who sent the messages.</span></span> <span data-ttu-id="a4fc3-121">Pour plus d’informations, voir la [table locataires](tenants.md) .</span><span class="sxs-lookup"><span data-stu-id="a4fc3-121">See the [Tenants table](tenants.md) for more information.</span></span> <br/> |
|<span data-ttu-id="a4fc3-122">**UserMessageCount**</span><span class="sxs-lookup"><span data-stu-id="a4fc3-122">**UserMessageCount**</span></span> <br/> |<span data-ttu-id="a4fc3-123">type</span><span class="sxs-lookup"><span data-stu-id="a4fc3-123">smallint</span></span>  <br/> |<span data-ttu-id="a4fc3-124">Nombre de messages envoyés par l’utilisateur au cours de la session de conférence.</span><span class="sxs-lookup"><span data-stu-id="a4fc3-124">Number of messages sent by the user during the conference session.</span></span>  <br/> |
   

