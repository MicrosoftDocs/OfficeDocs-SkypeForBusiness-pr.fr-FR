---
title: Export-CcConfiguration
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e3775bd6-682c-4f62-aafc-974fe3a65c61
description: Exporte la configuration de Skype entreprise version Cloud Connector vers un fichier local sur le serveur hôte Cloud Connector Skype entreprise.
ms.openlocfilehash: 7548b2fba602364d98c7540607660ccc57710654
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287418"
---
# <a name="export-ccconfiguration"></a><span data-ttu-id="07be4-103">Export-CcConfiguration</span><span class="sxs-lookup"><span data-stu-id="07be4-103">Export-CcConfiguration</span></span>
 
<span data-ttu-id="07be4-104">Exporte la configuration de Skype entreprise version Cloud Connector vers un fichier local sur le serveur hôte Cloud Connector Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="07be4-104">Exports the Skype for Business Cloud Connector Edition configuration to a local file on the Skype for Business Cloud Connector Edition host server.</span></span>
  
```
Export-CcConfiguration [-Path] <String> [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="07be4-105">Exemples</span><span class="sxs-lookup"><span data-stu-id="07be4-105">Examples</span></span>
<span data-ttu-id="07be4-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="07be4-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="07be4-107">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="07be4-107">Example 1</span></span>

<span data-ttu-id="07be4-108">L’exemple suivant définit le paramètre path pour le chemin d’accès complet au fichier et exporte les configurations vers ce fichier.</span><span class="sxs-lookup"><span data-stu-id="07be4-108">The following example sets the Path parameter as a full file path and exports configurations to that file.</span></span>
  
```
Export-CcConfiguration -Path "C:\test\CloudConnector.ini" 
```

## <a name="detailed-description"></a><span data-ttu-id="07be4-109">Description détaillée</span><span class="sxs-lookup"><span data-stu-id="07be4-109">Detailed Description</span></span>
<span data-ttu-id="07be4-110"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="07be4-110"></span></span>

<span data-ttu-id="07be4-111">L’applet de connexion Export-CcConfiguration vous permet d’enregistrer la configuration du connecteur Cloud dans un fichier dans un chemin sélectionné.</span><span class="sxs-lookup"><span data-stu-id="07be4-111">The Export-CcConfiguration cmdlet allows you to save the Cloud Connector configuration to a file in a selected path.</span></span> <span data-ttu-id="07be4-112">Cette commande a été introduite dans la version 2,0 d’édition Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="07be4-112">This command was introduced in Cloud Connector Edition version 2.0.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="07be4-113">Paramètres</span><span class="sxs-lookup"><span data-stu-id="07be4-113">Parameters</span></span>
<span data-ttu-id="07be4-114"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="07be4-114"></span></span>

|<span data-ttu-id="07be4-115">**Paramètre**</span><span class="sxs-lookup"><span data-stu-id="07be4-115">**Parameter**</span></span>|<span data-ttu-id="07be4-116">**Obligatoire**</span><span class="sxs-lookup"><span data-stu-id="07be4-116">**Required**</span></span>|<span data-ttu-id="07be4-117">**Type**</span><span class="sxs-lookup"><span data-stu-id="07be4-117">**Type**</span></span>|<span data-ttu-id="07be4-118">**Description**</span><span class="sxs-lookup"><span data-stu-id="07be4-118">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="07be4-119"> Path</span><span class="sxs-lookup"><span data-stu-id="07be4-119">Path</span></span>  <br/> |<span data-ttu-id="07be4-120">Obligatoire</span><span class="sxs-lookup"><span data-stu-id="07be4-120">Required</span></span>  <br/> |<span data-ttu-id="07be4-121">System.String</span><span class="sxs-lookup"><span data-stu-id="07be4-121">System.String</span></span>  <br/> |<span data-ttu-id="07be4-122">Chemin d’accès complet du fichier dans lequel les configurations du connecteur Cloud seront stockées.</span><span class="sxs-lookup"><span data-stu-id="07be4-122">Full file path where the Cloud Connector configurations will be stored.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="07be4-123">Types d’entrées</span><span class="sxs-lookup"><span data-stu-id="07be4-123">Input Types</span></span>
<span data-ttu-id="07be4-124"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="07be4-124"></span></span>

<span data-ttu-id="07be4-125">Aucun.</span><span class="sxs-lookup"><span data-stu-id="07be4-125">None.</span></span> <span data-ttu-id="07be4-126">L’applet de commande Export-CcConfiguration n’accepte pas les entrées pipelines.</span><span class="sxs-lookup"><span data-stu-id="07be4-126">The Export-CcConfiguration cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="07be4-127">Types de retours</span><span class="sxs-lookup"><span data-stu-id="07be4-127">Return Types</span></span>
<span data-ttu-id="07be4-128"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="07be4-128"></span></span>

<span data-ttu-id="07be4-129">Aucun.</span><span class="sxs-lookup"><span data-stu-id="07be4-129">None.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="07be4-130">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="07be4-130">See also</span></span>
<span data-ttu-id="07be4-131"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="07be4-131"></span></span>

<span data-ttu-id="07be4-132">Import-CcConfiguration</span><span class="sxs-lookup"><span data-stu-id="07be4-132">Import-CcConfiguration</span></span>
  

