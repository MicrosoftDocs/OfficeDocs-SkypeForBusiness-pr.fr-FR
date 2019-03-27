---
title: Table UriTypes
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 77c4dfae-1b29-4e81-ba05-609e61643998
description: La UriTypes Table contient les différents types d’URI (Uniform resource identifier) surveillés dans Skype pour Business Server 2015.
ms.openlocfilehash: cb9c131901a322f9d22c8d29aa52a73dc27c9ea1
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30899644"
---
# <a name="uritypes-table"></a><span data-ttu-id="70be7-103">Table UriTypes</span><span class="sxs-lookup"><span data-stu-id="70be7-103">UriTypes table</span></span>
 
<span data-ttu-id="70be7-104">La UriTypes Table contient les différents types d’URI (Uniform resource identifier) surveillés dans Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="70be7-104">The UriTypes Table contains the different URI (Uniform resource identifier) types monitored in Skype for Business Server 2015.</span></span>

<span data-ttu-id="70be7-105">Lorsque la CDR DB est créée, deux enregistrements pour représenter PhoneUri et UserUri sont créés et enregistrements créés après que qui sont attribuées dynamiquement UriTypeId.</span><span class="sxs-lookup"><span data-stu-id="70be7-105">When the CDR DB is created, two records to represent PhoneUri and UserUri are created, and records created after that are dynamically assigned UriTypeId.</span></span> 
  
|<span data-ttu-id="70be7-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="70be7-106">**Column**</span></span>|<span data-ttu-id="70be7-107">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="70be7-107">**Data Type**</span></span>|<span data-ttu-id="70be7-108">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="70be7-108">**Key/Index**</span></span>|<span data-ttu-id="70be7-109">**Détails**</span><span class="sxs-lookup"><span data-stu-id="70be7-109">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="70be7-110">**UriTypeId**</span><span class="sxs-lookup"><span data-stu-id="70be7-110">**UriTypeId**</span></span> <br/> |<span data-ttu-id="70be7-111">tinyint</span><span class="sxs-lookup"><span data-stu-id="70be7-111">tinyint</span></span>  <br/> |<span data-ttu-id="70be7-112">Principal</span><span class="sxs-lookup"><span data-stu-id="70be7-112">Primary</span></span>  <br/> |<span data-ttu-id="70be7-113">Identificateur unique attribué à un type d’URI.</span><span class="sxs-lookup"><span data-stu-id="70be7-113">Unique identifier assigned to a URI type.</span></span>  <br/> <span data-ttu-id="70be7-114">Valeurs possibles - 0 et 255.</span><span class="sxs-lookup"><span data-stu-id="70be7-114">Possible values - 0 to 255</span></span> |
|<span data-ttu-id="70be7-115">**UriType**</span><span class="sxs-lookup"><span data-stu-id="70be7-115">**UriType**</span></span> <br/> |<span data-ttu-id="70be7-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="70be7-116">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="70be7-117">Descriptions des différents types d’URI.</span><span class="sxs-lookup"><span data-stu-id="70be7-117">Descriptions of the different URI types.</span></span> <span data-ttu-id="70be7-118">Les valeurs suivantes sont affectées par défaut :</span><span class="sxs-lookup"><span data-stu-id="70be7-118">The following values are pre-assigned:</span></span> <br/>  <span data-ttu-id="70be7-119">1 - Uri du téléphone</span><span class="sxs-lookup"><span data-stu-id="70be7-119">1 - Phone Uri</span></span> <br/>  <span data-ttu-id="70be7-120">0 - Uri utilisateur</span><span class="sxs-lookup"><span data-stu-id="70be7-120">0 - User Uri</span></span> <br/> <br/>  <span data-ttu-id="70be7-121">Autres types possibles sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="70be7-121">Other possible types include:</span></span> <br/><span data-ttu-id="70be7-122">conf:applicationsharing</span><span class="sxs-lookup"><span data-stu-id="70be7-122">conf:applicationsharing</span></span> <br/> <span data-ttu-id="70be7-123">conf:audio-video</span><span class="sxs-lookup"><span data-stu-id="70be7-123">conf:audio-video</span></span><br/> <span data-ttu-id="70be7-124">conf:Chat</span><span class="sxs-lookup"><span data-stu-id="70be7-124">conf:chat</span></span><br/>    <span data-ttu-id="70be7-125">conf:focus</span><span class="sxs-lookup"><span data-stu-id="70be7-125">conf:focus</span></span><br/>   <span data-ttu-id="70be7-126">MRAS</span><span class="sxs-lookup"><span data-stu-id="70be7-126">mras</span></span><br/>
