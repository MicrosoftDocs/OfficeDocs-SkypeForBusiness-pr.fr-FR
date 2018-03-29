---
title: Table ClientVersions dans Skype pour Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 542316cf-a6db-4d52-ab28-8bf6d27a3b48
description: La table ClientVersions est un tableau de prise en charge qui stocke une liste des différents types de client et de versions qui ont participé aux sessions enregistrées dans la base de données. Chaque enregistrement de la table représente une version du client.
ms.openlocfilehash: 488c7f4211eacb6fc496d6198258c119641ebd14
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="clientversions-table-in-skype-for-business-server-2015"></a><span data-ttu-id="7b0bd-104">Table ClientVersions dans Skype pour Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="7b0bd-104">ClientVersions table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="7b0bd-105">La table ClientVersions est un tableau de prise en charge qui stocke une liste des différents types de client et de versions qui ont participé aux sessions enregistrées dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="7b0bd-105">The ClientVersions table is a supporting table that stores a list of the various client types and versions that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="7b0bd-106">Chaque enregistrement de la table représente une version du client.</span><span class="sxs-lookup"><span data-stu-id="7b0bd-106">Each record in the table represents one client version.</span></span>
  
|<span data-ttu-id="7b0bd-107">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="7b0bd-107">**Column**</span></span>|<span data-ttu-id="7b0bd-108">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="7b0bd-108">**Data Type**</span></span>|<span data-ttu-id="7b0bd-109">**Index de la clé**</span><span class="sxs-lookup"><span data-stu-id="7b0bd-109">**Key/Index**</span></span>|<span data-ttu-id="7b0bd-110">**Détails**</span><span class="sxs-lookup"><span data-stu-id="7b0bd-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="7b0bd-111">**Valeur de VersionId**</span><span class="sxs-lookup"><span data-stu-id="7b0bd-111">**VersionId**</span></span> <br/> |<span data-ttu-id="7b0bd-112">**int**</span><span class="sxs-lookup"><span data-stu-id="7b0bd-112">**int**</span></span> <br/> |<span data-ttu-id="7b0bd-113">Principal</span><span class="sxs-lookup"><span data-stu-id="7b0bd-113">Primary</span></span>  <br/> |<span data-ttu-id="7b0bd-114">Numéro unique identifiant le type de client et de la version.</span><span class="sxs-lookup"><span data-stu-id="7b0bd-114">Unique number identifying this client type and version.</span></span>  <br/> |
|<span data-ttu-id="7b0bd-115">**Version**</span><span class="sxs-lookup"><span data-stu-id="7b0bd-115">**Version**</span></span> <br/> |<span data-ttu-id="7b0bd-116">**nvarchar (256)**</span><span class="sxs-lookup"><span data-stu-id="7b0bd-116">**nvarchar(256)**</span></span> <br/> ||<span data-ttu-id="7b0bd-117">Nom de la version.</span><span class="sxs-lookup"><span data-stu-id="7b0bd-117">Version name.</span></span>  <br/> |
|<span data-ttu-id="7b0bd-118">**TypeClient**</span><span class="sxs-lookup"><span data-stu-id="7b0bd-118">**ClientType**</span></span> <br/> |<span data-ttu-id="7b0bd-119">int</span><span class="sxs-lookup"><span data-stu-id="7b0bd-119">int</span></span>  <br/> ||<span data-ttu-id="7b0bd-120">Spécifie le type de client utilisé dans la session.</span><span class="sxs-lookup"><span data-stu-id="7b0bd-120">Specifies the type of client used in the session.</span></span> <span data-ttu-id="7b0bd-121">Consultez le [tableau de UserAgentDef](useragentdef.md) pour plus d’informations.</span><span class="sxs-lookup"><span data-stu-id="7b0bd-121">See the [UserAgentDef table](useragentdef.md) for more information.</span></span> <br/> <span data-ttu-id="7b0bd-122">Ce champ a été introduit dans Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7b0bd-122">This field was introduced in Microsoft Lync Server 2013.</span></span>  <br/> |
   

