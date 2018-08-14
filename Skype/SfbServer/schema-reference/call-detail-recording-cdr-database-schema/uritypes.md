---
title: Table UriTypes
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
ms.openlocfilehash: d1a796367ae068dcd814b13b1b0ec6ce9ae453f1
ms.sourcegitcommit: 6340d0050a51790e40b7ab8e4e89348251ba184f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/06/2018
ms.locfileid: "19649604"
---
# <a name="uritypes-table"></a><span data-ttu-id="c8a0c-103">Table UriTypes</span><span class="sxs-lookup"><span data-stu-id="c8a0c-103">UriTypes table</span></span>
 
<span data-ttu-id="c8a0c-104">La UriTypes Table contient les différents types d’URI (Uniform resource identifier) surveillés dans Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="c8a0c-104">The UriTypes Table contains the different URI (Uniform resource identifier) types monitored in Skype for Business Server 2015.</span></span>

<span data-ttu-id="c8a0c-105">Lorsque la CDR DB est créée, deux enregistrements pour représenter PhoneUri et UserUri sont créés et enregistrements créés après que qui sont attribuées dynamiquement UriTypeId.</span><span class="sxs-lookup"><span data-stu-id="c8a0c-105">When the CDR DB is created, two records to represent PhoneUri and UserUri are created, and records created after that are dynamically assigned UriTypeId.</span></span> 
  
|<span data-ttu-id="c8a0c-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="c8a0c-106">**Column**</span></span>|<span data-ttu-id="c8a0c-107">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="c8a0c-107">**Data Type**</span></span>|<span data-ttu-id="c8a0c-108">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="c8a0c-108">**Key/Index**</span></span>|<span data-ttu-id="c8a0c-109">**Détails**</span><span class="sxs-lookup"><span data-stu-id="c8a0c-109">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c8a0c-110">**UriTypeId**</span><span class="sxs-lookup"><span data-stu-id="c8a0c-110">**UriTypeId**</span></span> <br/> |<span data-ttu-id="c8a0c-111">tinyint</span><span class="sxs-lookup"><span data-stu-id="c8a0c-111">tinyint</span></span>  <br/> |<span data-ttu-id="c8a0c-112">Principal</span><span class="sxs-lookup"><span data-stu-id="c8a0c-112">Primary</span></span>  <br/> |<span data-ttu-id="c8a0c-113">Identificateur unique attribué à un type d’URI.</span><span class="sxs-lookup"><span data-stu-id="c8a0c-113">Unique identifier assigned to a URI type.</span></span>  <br/> <span data-ttu-id="c8a0c-114">Valeurs possibles - 0 et 255.</span><span class="sxs-lookup"><span data-stu-id="c8a0c-114">Possible values - 0 to 255</span></span> |
|<span data-ttu-id="c8a0c-115">**UriType**</span><span class="sxs-lookup"><span data-stu-id="c8a0c-115">**UriType**</span></span> <br/> |<span data-ttu-id="c8a0c-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="c8a0c-116">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="c8a0c-117">Descriptions des différents types d’URI.</span><span class="sxs-lookup"><span data-stu-id="c8a0c-117">Descriptions of the different URI types.</span></span> <span data-ttu-id="c8a0c-118">Les valeurs suivantes sont affectées par défaut :</span><span class="sxs-lookup"><span data-stu-id="c8a0c-118">The following values are pre-assigned:</span></span> <br/>  <span data-ttu-id="c8a0c-119">1 - Uri du téléphone</span><span class="sxs-lookup"><span data-stu-id="c8a0c-119">1 - Phone Uri</span></span> <br/>  <span data-ttu-id="c8a0c-120">0 - Uri utilisateur</span><span class="sxs-lookup"><span data-stu-id="c8a0c-120">0 - User Uri</span></span> <br/> <br/>  <span data-ttu-id="c8a0c-121">Autres types possibles sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="c8a0c-121">Other possible types include:</span></span> <br/><span data-ttu-id="c8a0c-122">conf:applicationsharing</span><span class="sxs-lookup"><span data-stu-id="c8a0c-122">conf:applicationsharing</span></span> <br/> <span data-ttu-id="c8a0c-123">conf:audio-video</span><span class="sxs-lookup"><span data-stu-id="c8a0c-123">conf:audio-video</span></span><br/> <span data-ttu-id="c8a0c-124">conf:Chat</span><span class="sxs-lookup"><span data-stu-id="c8a0c-124">conf:chat</span></span><br/>    <span data-ttu-id="c8a0c-125">conf:focus</span><span class="sxs-lookup"><span data-stu-id="c8a0c-125">conf:focus</span></span><br/>   <span data-ttu-id="c8a0c-126">MRAS</span><span class="sxs-lookup"><span data-stu-id="c8a0c-126">mras</span></span><br/>
