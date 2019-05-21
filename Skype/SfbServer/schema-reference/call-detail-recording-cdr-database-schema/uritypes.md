---
title: Table UriTypes
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 77c4dfae-1b29-4e81-ba05-609e61643998
description: La table UriTypes contient les différents types d’URI (Uniform Resource Identifier) surveillés dans Skype entreprise Server 2015.
ms.openlocfilehash: 5ad8e1d0432aff3278f897fbe82d3759ad3c95e1
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295747"
---
# <a name="uritypes-table"></a><span data-ttu-id="1e09e-103">Table UriTypes</span><span class="sxs-lookup"><span data-stu-id="1e09e-103">UriTypes table</span></span>
 
<span data-ttu-id="1e09e-104">La table UriTypes contient les différents types d’URI (Uniform Resource Identifier) surveillés dans Skype entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="1e09e-104">The UriTypes Table contains the different URI (Uniform resource identifier) types monitored in Skype for Business Server 2015.</span></span>

<span data-ttu-id="1e09e-105">Lors de la création de la base de données de CDR, deux enregistrements permettant de représenter PhoneUri et UserUri sont créés, et les enregistrements créés après leur attribution dynamique UriTypeId.</span><span class="sxs-lookup"><span data-stu-id="1e09e-105">When the CDR DB is created, two records to represent PhoneUri and UserUri are created, and records created after that are dynamically assigned UriTypeId.</span></span> 
  
|<span data-ttu-id="1e09e-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="1e09e-106">**Column**</span></span>|<span data-ttu-id="1e09e-107">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="1e09e-107">**Data Type**</span></span>|<span data-ttu-id="1e09e-108">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="1e09e-108">**Key/Index**</span></span>|<span data-ttu-id="1e09e-109">**Détails**</span><span class="sxs-lookup"><span data-stu-id="1e09e-109">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="1e09e-110">**UriTypeId**</span><span class="sxs-lookup"><span data-stu-id="1e09e-110">**UriTypeId**</span></span> <br/> |<span data-ttu-id="1e09e-111">tinyint</span><span class="sxs-lookup"><span data-stu-id="1e09e-111">tinyint</span></span>  <br/> |<span data-ttu-id="1e09e-112">Principal</span><span class="sxs-lookup"><span data-stu-id="1e09e-112">Primary</span></span>  <br/> |<span data-ttu-id="1e09e-113">Identificateur unique attribué à un type d’URI.</span><span class="sxs-lookup"><span data-stu-id="1e09e-113">Unique identifier assigned to a URI type.</span></span>  <br/> <span data-ttu-id="1e09e-114">Valeurs possibles: 0 à 255</span><span class="sxs-lookup"><span data-stu-id="1e09e-114">Possible values - 0 to 255</span></span> |
|<span data-ttu-id="1e09e-115">**UriType**</span><span class="sxs-lookup"><span data-stu-id="1e09e-115">**UriType**</span></span> <br/> |<span data-ttu-id="1e09e-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="1e09e-116">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="1e09e-117">Descriptions des différents types d’URI.</span><span class="sxs-lookup"><span data-stu-id="1e09e-117">Descriptions of the different URI types.</span></span> <span data-ttu-id="1e09e-118">Les valeurs suivantes sont préaffectées:</span><span class="sxs-lookup"><span data-stu-id="1e09e-118">The following values are pre-assigned:</span></span> <br/>  <span data-ttu-id="1e09e-119">1-URI de téléphone</span><span class="sxs-lookup"><span data-stu-id="1e09e-119">1 - Phone Uri</span></span> <br/>  <span data-ttu-id="1e09e-120">0-URI de l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="1e09e-120">0 - User Uri</span></span> <br/> <br/>  <span data-ttu-id="1e09e-121">Voici d’autres types possibles:</span><span class="sxs-lookup"><span data-stu-id="1e09e-121">Other possible types include:</span></span> <br/><span data-ttu-id="1e09e-122">conf:applicationsharing</span><span class="sxs-lookup"><span data-stu-id="1e09e-122">conf:applicationsharing</span></span> <br/> <span data-ttu-id="1e09e-123">conf:audio-video</span><span class="sxs-lookup"><span data-stu-id="1e09e-123">conf:audio-video</span></span><br/> <span data-ttu-id="1e09e-124">conf: chat</span><span class="sxs-lookup"><span data-stu-id="1e09e-124">conf:chat</span></span><br/>    <span data-ttu-id="1e09e-125">conf:focus</span><span class="sxs-lookup"><span data-stu-id="1e09e-125">conf:focus</span></span><br/>   <span data-ttu-id="1e09e-126">mras</span><span class="sxs-lookup"><span data-stu-id="1e09e-126">mras</span></span><br/>
