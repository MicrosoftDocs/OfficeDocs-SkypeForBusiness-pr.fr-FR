---
title: Table UriTypes
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 77c4dfae-1b29-4e81-ba05-609e61643998
description: La UriTypes Table contient les différents types d’URI (Uniform resource identifier) surveillés dans Skype pour Business Server 2015.
ms.openlocfilehash: 72704715ff5e5fd3a354b75b0aa6baff45ecea54
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930268"
---
# <a name="uritypes-table"></a><span data-ttu-id="2846e-103">Table UriTypes</span><span class="sxs-lookup"><span data-stu-id="2846e-103">UriTypes table</span></span>
 
<span data-ttu-id="2846e-104">La UriTypes Table contient les différents types d’URI (Uniform resource identifier) surveillés dans Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="2846e-104">The UriTypes Table contains the different URI (Uniform resource identifier) types monitored in Skype for Business Server 2015.</span></span>

<span data-ttu-id="2846e-105">Lorsque la CDR DB est créée, deux enregistrements pour représenter PhoneUri et UserUri sont créés et enregistrements créés après que qui sont attribuées dynamiquement UriTypeId.</span><span class="sxs-lookup"><span data-stu-id="2846e-105">When the CDR DB is created, two records to represent PhoneUri and UserUri are created, and records created after that are dynamically assigned UriTypeId.</span></span> 
  
|<span data-ttu-id="2846e-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="2846e-106">**Column**</span></span>|<span data-ttu-id="2846e-107">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="2846e-107">**Data Type**</span></span>|<span data-ttu-id="2846e-108">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="2846e-108">**Key/Index**</span></span>|<span data-ttu-id="2846e-109">**Détails**</span><span class="sxs-lookup"><span data-stu-id="2846e-109">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2846e-110">**UriTypeId**</span><span class="sxs-lookup"><span data-stu-id="2846e-110">**UriTypeId**</span></span> <br/> |<span data-ttu-id="2846e-111">tinyint</span><span class="sxs-lookup"><span data-stu-id="2846e-111">tinyint</span></span>  <br/> |<span data-ttu-id="2846e-112">Principal</span><span class="sxs-lookup"><span data-stu-id="2846e-112">Primary</span></span>  <br/> |<span data-ttu-id="2846e-113">Identificateur unique attribué à un type d’URI.</span><span class="sxs-lookup"><span data-stu-id="2846e-113">Unique identifier assigned to a URI type.</span></span>  <br/> <span data-ttu-id="2846e-114">Valeurs possibles - 0 et 255.</span><span class="sxs-lookup"><span data-stu-id="2846e-114">Possible values - 0 to 255</span></span> |
|<span data-ttu-id="2846e-115">**UriType**</span><span class="sxs-lookup"><span data-stu-id="2846e-115">**UriType**</span></span> <br/> |<span data-ttu-id="2846e-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="2846e-116">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="2846e-117">Descriptions des différents types d’URI.</span><span class="sxs-lookup"><span data-stu-id="2846e-117">Descriptions of the different URI types.</span></span> <span data-ttu-id="2846e-118">Les valeurs suivantes sont affectées par défaut :</span><span class="sxs-lookup"><span data-stu-id="2846e-118">The following values are pre-assigned:</span></span> <br/>  <span data-ttu-id="2846e-119">1 - Uri du téléphone</span><span class="sxs-lookup"><span data-stu-id="2846e-119">1 - Phone Uri</span></span> <br/>  <span data-ttu-id="2846e-120">0 - Uri utilisateur</span><span class="sxs-lookup"><span data-stu-id="2846e-120">0 - User Uri</span></span> <br/> <br/>  <span data-ttu-id="2846e-121">Autres types possibles sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="2846e-121">Other possible types include:</span></span> <br/><span data-ttu-id="2846e-122">conf:applicationsharing</span><span class="sxs-lookup"><span data-stu-id="2846e-122">conf:applicationsharing</span></span> <br/> <span data-ttu-id="2846e-123">conf:audio-video</span><span class="sxs-lookup"><span data-stu-id="2846e-123">conf:audio-video</span></span><br/> <span data-ttu-id="2846e-124">conf:Chat</span><span class="sxs-lookup"><span data-stu-id="2846e-124">conf:chat</span></span><br/>    <span data-ttu-id="2846e-125">conf:focus</span><span class="sxs-lookup"><span data-stu-id="2846e-125">conf:focus</span></span><br/>   <span data-ttu-id="2846e-126">MRAS</span><span class="sxs-lookup"><span data-stu-id="2846e-126">mras</span></span><br/>
