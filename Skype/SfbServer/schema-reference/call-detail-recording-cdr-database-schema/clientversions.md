---
title: Table ClientVersions dans Skype entreprise Server 2015
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
ms.assetid: 542316cf-a6db-4d52-ab28-8bf6d27a3b48
description: La table ClientVersions est une table qui contient une liste des différents types de clients et différentes versions ayant participé à des sessions enregistrées dans la base de données. Chaque enregistrement de la table représente une version du client.
ms.openlocfilehash: c616f7d44d138732e96f2d71c7fdf0197c75ca5c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815402"
---
# <a name="clientversions-table-in-skype-for-business-server-2015"></a><span data-ttu-id="13df7-104">Table ClientVersions dans Skype entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="13df7-104">ClientVersions table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="13df7-105">La table ClientVersions est une table qui contient une liste des différents types de clients et différentes versions ayant participé à des sessions enregistrées dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="13df7-105">The ClientVersions table is a supporting table that stores a list of the various client types and versions that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="13df7-106">Chaque enregistrement de la table représente une version du client.</span><span class="sxs-lookup"><span data-stu-id="13df7-106">Each record in the table represents one client version.</span></span>
  
|<span data-ttu-id="13df7-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="13df7-107">**Column**</span></span>|<span data-ttu-id="13df7-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="13df7-108">**Data Type**</span></span>|<span data-ttu-id="13df7-109">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="13df7-109">**Key/Index**</span></span>|<span data-ttu-id="13df7-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="13df7-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="13df7-111">**VersionId**</span><span class="sxs-lookup"><span data-stu-id="13df7-111">**VersionId**</span></span> <br/> |<span data-ttu-id="13df7-112">**int**</span><span class="sxs-lookup"><span data-stu-id="13df7-112">**int**</span></span> <br/> |<span data-ttu-id="13df7-113">Principal</span><span class="sxs-lookup"><span data-stu-id="13df7-113">Primary</span></span>  <br/> |<span data-ttu-id="13df7-114">Numéro unique identifiant ce type et version de client.</span><span class="sxs-lookup"><span data-stu-id="13df7-114">Unique number identifying this client type and version.</span></span>  <br/> |
|<span data-ttu-id="13df7-115">**Version**</span><span class="sxs-lookup"><span data-stu-id="13df7-115">**Version**</span></span> <br/> |<span data-ttu-id="13df7-116">**nvarchar(256)**</span><span class="sxs-lookup"><span data-stu-id="13df7-116">**nvarchar(256)**</span></span> <br/> ||<span data-ttu-id="13df7-117">Nom de la version.</span><span class="sxs-lookup"><span data-stu-id="13df7-117">Version name.</span></span>  <br/> |
|<span data-ttu-id="13df7-118">**TypeClient**</span><span class="sxs-lookup"><span data-stu-id="13df7-118">**ClientType**</span></span> <br/> |<span data-ttu-id="13df7-119">int</span><span class="sxs-lookup"><span data-stu-id="13df7-119">int</span></span>  <br/> ||<span data-ttu-id="13df7-120">Spécifie le type de client utilisé dans la session.</span><span class="sxs-lookup"><span data-stu-id="13df7-120">Specifies the type of client used in the session.</span></span> <span data-ttu-id="13df7-121">Pour plus d’informations, voir la [table UserAgentDef](useragentdef.md) .</span><span class="sxs-lookup"><span data-stu-id="13df7-121">See the [UserAgentDef table](useragentdef.md) for more information.</span></span> <br/> <span data-ttu-id="13df7-122">Ce champ a été présenté dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="13df7-122">This field was introduced in Microsoft Lync Server 2013.</span></span>  <br/> |
   

