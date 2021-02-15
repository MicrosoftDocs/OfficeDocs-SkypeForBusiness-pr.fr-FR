---
title: Table UriTypes
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 77c4dfae-1b29-4e81-ba05-609e61643998
description: La table UriTypes contient les différents types d’URI (Uniform resource identifier) surveillés dans Skype Entreprise Server 2015.
ms.openlocfilehash: 622384086dbd1031633b70758cdcea600ad31d43
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831684"
---
# <a name="uritypes-table"></a><span data-ttu-id="c76d5-103">Table UriTypes</span><span class="sxs-lookup"><span data-stu-id="c76d5-103">UriTypes table</span></span>
 
<span data-ttu-id="c76d5-104">La table UriTypes contient les différents types d’URI (Uniform resource identifier) surveillés dans Skype Entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="c76d5-104">The UriTypes Table contains the different URI (Uniform resource identifier) types monitored in Skype for Business Server 2015.</span></span>

<span data-ttu-id="c76d5-105">Lors de la création de la base de données d’enregistrement des appels, deux enregistrements représentant PhoneUri et UserUri sont créés, et les enregistrements créés par la suite sont affectés dynamiquement à UriTypeId.</span><span class="sxs-lookup"><span data-stu-id="c76d5-105">When the CDR DB is created, two records to represent PhoneUri and UserUri are created, and records created after that are dynamically assigned UriTypeId.</span></span> 
  
|<span data-ttu-id="c76d5-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="c76d5-106">**Column**</span></span>|<span data-ttu-id="c76d5-107">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="c76d5-107">**Data Type**</span></span>|<span data-ttu-id="c76d5-108">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="c76d5-108">**Key/Index**</span></span>|<span data-ttu-id="c76d5-109">**Détails**</span><span class="sxs-lookup"><span data-stu-id="c76d5-109">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c76d5-110">**UriTypeId**</span><span class="sxs-lookup"><span data-stu-id="c76d5-110">**UriTypeId**</span></span> <br/> |<span data-ttu-id="c76d5-111">tinyint</span><span class="sxs-lookup"><span data-stu-id="c76d5-111">tinyint</span></span>  <br/> |<span data-ttu-id="c76d5-112">Primaire</span><span class="sxs-lookup"><span data-stu-id="c76d5-112">Primary</span></span>  <br/> |<span data-ttu-id="c76d5-113">Identificateur unique attribué à un type d’URI.</span><span class="sxs-lookup"><span data-stu-id="c76d5-113">Unique identifier assigned to a URI type.</span></span>  <br/> <span data-ttu-id="c76d5-114">Valeurs possibles - 0 à 255</span><span class="sxs-lookup"><span data-stu-id="c76d5-114">Possible values - 0 to 255</span></span> |
|<span data-ttu-id="c76d5-115">**UriType**</span><span class="sxs-lookup"><span data-stu-id="c76d5-115">**UriType**</span></span> <br/> |<span data-ttu-id="c76d5-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="c76d5-116">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="c76d5-117">Descriptions des différents types d’URI.</span><span class="sxs-lookup"><span data-stu-id="c76d5-117">Descriptions of the different URI types.</span></span> <span data-ttu-id="c76d5-118">Les valeurs suivantes sont pré-affectées :</span><span class="sxs-lookup"><span data-stu-id="c76d5-118">The following values are pre-assigned:</span></span> <br/>  <span data-ttu-id="c76d5-119">1 - Uri de téléphone</span><span class="sxs-lookup"><span data-stu-id="c76d5-119">1 - Phone Uri</span></span> <br/>  <span data-ttu-id="c76d5-120">0 - Uri de l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="c76d5-120">0 - User Uri</span></span> <br/> <br/>  <span data-ttu-id="c76d5-121">Les autres types possibles sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="c76d5-121">Other possible types include:</span></span> <br/><span data-ttu-id="c76d5-122">conf:applicationsharing</span><span class="sxs-lookup"><span data-stu-id="c76d5-122">conf:applicationsharing</span></span> <br/> <span data-ttu-id="c76d5-123">conf:audio-video</span><span class="sxs-lookup"><span data-stu-id="c76d5-123">conf:audio-video</span></span><br/> <span data-ttu-id="c76d5-124">conf:chat</span><span class="sxs-lookup"><span data-stu-id="c76d5-124">conf:chat</span></span><br/>    <span data-ttu-id="c76d5-125">conf:focus</span><span class="sxs-lookup"><span data-stu-id="c76d5-125">conf:focus</span></span><br/>   <span data-ttu-id="c76d5-126">mras</span><span class="sxs-lookup"><span data-stu-id="c76d5-126">mras</span></span><br/>
