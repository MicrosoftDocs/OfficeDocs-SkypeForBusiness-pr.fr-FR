---
title: Table ClientVersions dans Skype Entreprise Server 2015
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
ms.assetid: 542316cf-a6db-4d52-ab28-8bf6d27a3b48
description: La table ClientVersions est une table de prise en charge qui stocke la liste des divers types et versions de clients ayant participé à des sessions enregistrées dans la base de données. Chaque enregistrement de la table représente une version de client.
ms.openlocfilehash: 9f72a640fa294a51e483f496cad9913177dfcd2c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813314"
---
# <a name="clientversions-table-in-skype-for-business-server-2015"></a><span data-ttu-id="faba7-104">Table ClientVersions dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="faba7-104">ClientVersions table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="faba7-p102">La table ClientVersions est une table de prise en charge qui stocke la liste des divers types et versions de clients ayant participé à des sessions enregistrées dans la base de données. Chaque enregistrement de la table représente une version de client.</span><span class="sxs-lookup"><span data-stu-id="faba7-p102">The ClientVersions table is a supporting table that stores a list of the various client types and versions that have participated in sessions recorded in the database. Each record in the table represents one client version.</span></span>
  
|<span data-ttu-id="faba7-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="faba7-107">**Column**</span></span>|<span data-ttu-id="faba7-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="faba7-108">**Data Type**</span></span>|<span data-ttu-id="faba7-109">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="faba7-109">**Key/Index**</span></span>|<span data-ttu-id="faba7-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="faba7-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="faba7-111">**VersionId**</span><span class="sxs-lookup"><span data-stu-id="faba7-111">**VersionId**</span></span> <br/> |<span data-ttu-id="faba7-112">**int**</span><span class="sxs-lookup"><span data-stu-id="faba7-112">**int**</span></span> <br/> |<span data-ttu-id="faba7-113">Primaire</span><span class="sxs-lookup"><span data-stu-id="faba7-113">Primary</span></span>  <br/> |<span data-ttu-id="faba7-114">Numéro unique identifiant le type et la version de ce client.</span><span class="sxs-lookup"><span data-stu-id="faba7-114">Unique number identifying this client type and version.</span></span>  <br/> |
|<span data-ttu-id="faba7-115">**Version**</span><span class="sxs-lookup"><span data-stu-id="faba7-115">**Version**</span></span> <br/> |<span data-ttu-id="faba7-116">**nvarchar(256)**</span><span class="sxs-lookup"><span data-stu-id="faba7-116">**nvarchar(256)**</span></span> <br/> ||<span data-ttu-id="faba7-117">Nom de la version.</span><span class="sxs-lookup"><span data-stu-id="faba7-117">Version name.</span></span>  <br/> |
|<span data-ttu-id="faba7-118">**ClientType**</span><span class="sxs-lookup"><span data-stu-id="faba7-118">**ClientType**</span></span> <br/> |<span data-ttu-id="faba7-119">int</span><span class="sxs-lookup"><span data-stu-id="faba7-119">int</span></span>  <br/> ||<span data-ttu-id="faba7-120">Spécifie le type de client utilisé dans la session.</span><span class="sxs-lookup"><span data-stu-id="faba7-120">Specifies the type of client used in the session.</span></span> <span data-ttu-id="faba7-121">Pour plus d’informations, voir la [table UserAgentDef.](useragentdef.md)</span><span class="sxs-lookup"><span data-stu-id="faba7-121">See the [UserAgentDef table](useragentdef.md) for more information.</span></span> <br/> <span data-ttu-id="faba7-122">Ce champ a été introduit dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="faba7-122">This field was introduced in Microsoft Lync Server 2013.</span></span>  <br/> |
   

