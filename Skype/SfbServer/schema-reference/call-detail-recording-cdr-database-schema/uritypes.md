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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 77c4dfae-1b29-4e81-ba05-609e61643998
description: La table UriTypes contient les différents types d’URI (Uniform Resource Identifier) surveillés dans Skype entreprise Server 2015.
ms.openlocfilehash: 81cd00503f88eac03f952b63ef7a3bd9464c1f51
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814842"
---
# <a name="uritypes-table"></a><span data-ttu-id="66ef7-103">Table UriTypes</span><span class="sxs-lookup"><span data-stu-id="66ef7-103">UriTypes table</span></span>
 
<span data-ttu-id="66ef7-104">La table UriTypes contient les différents types d’URI (Uniform Resource Identifier) surveillés dans Skype entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="66ef7-104">The UriTypes Table contains the different URI (Uniform resource identifier) types monitored in Skype for Business Server 2015.</span></span>

<span data-ttu-id="66ef7-105">Lors de la création de la base de données de CDR, deux enregistrements permettant de représenter PhoneUri et UserUri sont créés, et les enregistrements créés après leur attribution dynamique UriTypeId.</span><span class="sxs-lookup"><span data-stu-id="66ef7-105">When the CDR DB is created, two records to represent PhoneUri and UserUri are created, and records created after that are dynamically assigned UriTypeId.</span></span> 
  
|<span data-ttu-id="66ef7-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="66ef7-106">**Column**</span></span>|<span data-ttu-id="66ef7-107">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="66ef7-107">**Data Type**</span></span>|<span data-ttu-id="66ef7-108">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="66ef7-108">**Key/Index**</span></span>|<span data-ttu-id="66ef7-109">**Détails**</span><span class="sxs-lookup"><span data-stu-id="66ef7-109">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="66ef7-110">**UriTypeId**</span><span class="sxs-lookup"><span data-stu-id="66ef7-110">**UriTypeId**</span></span> <br/> |<span data-ttu-id="66ef7-111">tinyint</span><span class="sxs-lookup"><span data-stu-id="66ef7-111">tinyint</span></span>  <br/> |<span data-ttu-id="66ef7-112">Principal</span><span class="sxs-lookup"><span data-stu-id="66ef7-112">Primary</span></span>  <br/> |<span data-ttu-id="66ef7-113">Identificateur unique attribué à un type d’URI.</span><span class="sxs-lookup"><span data-stu-id="66ef7-113">Unique identifier assigned to a URI type.</span></span>  <br/> <span data-ttu-id="66ef7-114">Valeurs possibles : 0 à 255</span><span class="sxs-lookup"><span data-stu-id="66ef7-114">Possible values - 0 to 255</span></span> |
|<span data-ttu-id="66ef7-115">**UriType**</span><span class="sxs-lookup"><span data-stu-id="66ef7-115">**UriType**</span></span> <br/> |<span data-ttu-id="66ef7-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="66ef7-116">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="66ef7-117">Descriptions des différents types d’URI.</span><span class="sxs-lookup"><span data-stu-id="66ef7-117">Descriptions of the different URI types.</span></span> <span data-ttu-id="66ef7-118">Les valeurs suivantes sont préaffectées :</span><span class="sxs-lookup"><span data-stu-id="66ef7-118">The following values are pre-assigned:</span></span> <br/>  <span data-ttu-id="66ef7-119">1-URI de téléphone</span><span class="sxs-lookup"><span data-stu-id="66ef7-119">1 - Phone Uri</span></span> <br/>  <span data-ttu-id="66ef7-120">0-URI de l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="66ef7-120">0 - User Uri</span></span> <br/> <br/>  <span data-ttu-id="66ef7-121">Voici d’autres types possibles :</span><span class="sxs-lookup"><span data-stu-id="66ef7-121">Other possible types include:</span></span> <br/><span data-ttu-id="66ef7-122">conf:applicationsharing</span><span class="sxs-lookup"><span data-stu-id="66ef7-122">conf:applicationsharing</span></span> <br/> <span data-ttu-id="66ef7-123">conf:audio-video</span><span class="sxs-lookup"><span data-stu-id="66ef7-123">conf:audio-video</span></span><br/> <span data-ttu-id="66ef7-124">conf : chat</span><span class="sxs-lookup"><span data-stu-id="66ef7-124">conf:chat</span></span><br/>    <span data-ttu-id="66ef7-125">conf:focus</span><span class="sxs-lookup"><span data-stu-id="66ef7-125">conf:focus</span></span><br/>   <span data-ttu-id="66ef7-126">mras</span><span class="sxs-lookup"><span data-stu-id="66ef7-126">mras</span></span><br/>
