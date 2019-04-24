---
title: Table ClientVersions dans Skype pour Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 542316cf-a6db-4d52-ab28-8bf6d27a3b48
description: La table ClientVersions est une table de prise en charge qui stocke une liste des différents types de clients et les versions qui ont participé à des sessions enregistrées dans la base de données. Chaque enregistrement de la table représente une version du client.
ms.openlocfilehash: df80e907359297c9cdb518562fdeea54d31a2a47
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213381"
---
# <a name="clientversions-table-in-skype-for-business-server-2015"></a><span data-ttu-id="c725b-104">Table ClientVersions dans Skype pour Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="c725b-104">ClientVersions table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="c725b-105">La table ClientVersions est une table de prise en charge qui stocke une liste des différents types de clients et les versions qui ont participé à des sessions enregistrées dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="c725b-105">The ClientVersions table is a supporting table that stores a list of the various client types and versions that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="c725b-106">Chaque enregistrement de la table représente une version du client.</span><span class="sxs-lookup"><span data-stu-id="c725b-106">Each record in the table represents one client version.</span></span>
  
|<span data-ttu-id="c725b-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="c725b-107">**Column**</span></span>|<span data-ttu-id="c725b-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="c725b-108">**Data Type**</span></span>|<span data-ttu-id="c725b-109">**Clé/Index**</span><span class="sxs-lookup"><span data-stu-id="c725b-109">**Key/Index**</span></span>|<span data-ttu-id="c725b-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="c725b-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c725b-111">**VersionId**</span><span class="sxs-lookup"><span data-stu-id="c725b-111">**VersionId**</span></span> <br/> |<span data-ttu-id="c725b-112">**int**</span><span class="sxs-lookup"><span data-stu-id="c725b-112">**int**</span></span> <br/> |<span data-ttu-id="c725b-113">Principal</span><span class="sxs-lookup"><span data-stu-id="c725b-113">Primary</span></span>  <br/> |<span data-ttu-id="c725b-114">Numéro unique identifiant ce type de client et de la version.</span><span class="sxs-lookup"><span data-stu-id="c725b-114">Unique number identifying this client type and version.</span></span>  <br/> |
|<span data-ttu-id="c725b-115">**Version**</span><span class="sxs-lookup"><span data-stu-id="c725b-115">**Version**</span></span> <br/> |<span data-ttu-id="c725b-116">**nvarchar(256)**</span><span class="sxs-lookup"><span data-stu-id="c725b-116">**nvarchar(256)**</span></span> <br/> ||<span data-ttu-id="c725b-117">Nom de la version.</span><span class="sxs-lookup"><span data-stu-id="c725b-117">Version name.</span></span>  <br/> |
|<span data-ttu-id="c725b-118">**TypeClient**</span><span class="sxs-lookup"><span data-stu-id="c725b-118">**ClientType**</span></span> <br/> |<span data-ttu-id="c725b-119">int</span><span class="sxs-lookup"><span data-stu-id="c725b-119">int</span></span>  <br/> ||<span data-ttu-id="c725b-120">Spécifie le type du client utilisé dans la session.</span><span class="sxs-lookup"><span data-stu-id="c725b-120">Specifies the type of client used in the session.</span></span> <span data-ttu-id="c725b-121">Consultez la [table UserAgentDef](useragentdef.md) pour plus d’informations.</span><span class="sxs-lookup"><span data-stu-id="c725b-121">See the [UserAgentDef table](useragentdef.md) for more information.</span></span> <br/> <span data-ttu-id="c725b-122">Ce champ est une nouveauté dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c725b-122">This field was introduced in Microsoft Lync Server 2013.</span></span>  <br/> |
   

