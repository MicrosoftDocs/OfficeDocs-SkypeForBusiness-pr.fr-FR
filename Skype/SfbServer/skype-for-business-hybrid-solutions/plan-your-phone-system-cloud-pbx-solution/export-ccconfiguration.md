---
title: Export-CcConfiguration
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e3775bd6-682c-4f62-aafc-974fe3a65c61
description: Exporte le Skype pour la configuration du connecteur du nuage Professionnel vers un fichier local sur le Skype pour le serveur hôte de nuage connecteur édition.
ms.openlocfilehash: 8afca55e6727c84c579957de9e2010e84a72fb15
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32234055"
---
# <a name="export-ccconfiguration"></a><span data-ttu-id="e5420-103">Export-CcConfiguration</span><span class="sxs-lookup"><span data-stu-id="e5420-103">Export-CcConfiguration</span></span>
 
<span data-ttu-id="e5420-104">Exporte le Skype pour la configuration du connecteur du nuage Professionnel vers un fichier local sur le Skype pour le serveur hôte de nuage connecteur édition.</span><span class="sxs-lookup"><span data-stu-id="e5420-104">Exports the Skype for Business Cloud Connector Edition configuration to a local file on the Skype for Business Cloud Connector Edition host server.</span></span>
  
```
Export-CcConfiguration [-Path] <String> [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="e5420-105">Exemples</span><span class="sxs-lookup"><span data-stu-id="e5420-105">Examples</span></span>
<span data-ttu-id="e5420-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="e5420-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="e5420-107">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="e5420-107">Example 1</span></span>

<span data-ttu-id="e5420-108">L’exemple suivant définit le paramètre de chemin d’accès sous la forme d’un chemin d’accès complet et exporte les configurations dans ce fichier.</span><span class="sxs-lookup"><span data-stu-id="e5420-108">The following example sets the Path parameter as a full file path and exports configurations to that file.</span></span>
  
```
Export-CcConfiguration -Path "C:\test\CloudConnector.ini" 
```

## <a name="detailed-description"></a><span data-ttu-id="e5420-109">Description détaillée</span><span class="sxs-lookup"><span data-stu-id="e5420-109">Detailed Description</span></span>
<span data-ttu-id="e5420-110"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="e5420-110"></span></span>

<span data-ttu-id="e5420-111">L’applet de commande Export-CcConfiguration vous permet d’enregistrer la configuration du connecteur du nuage vers un fichier dans un chemin d’accès sélectionné.</span><span class="sxs-lookup"><span data-stu-id="e5420-111">The Export-CcConfiguration cmdlet allows you to save the Cloud Connector configuration to a file in a selected path.</span></span> <span data-ttu-id="e5420-112">Cette commande a été introduite dans le nuage connecteur Edition version 2.0.</span><span class="sxs-lookup"><span data-stu-id="e5420-112">This command was introduced in Cloud Connector Edition version 2.0.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="e5420-113">Paramètres</span><span class="sxs-lookup"><span data-stu-id="e5420-113">Parameters</span></span>
<span data-ttu-id="e5420-114"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="e5420-114"></span></span>

|<span data-ttu-id="e5420-115">**Paramètre**</span><span class="sxs-lookup"><span data-stu-id="e5420-115">**Parameter**</span></span>|<span data-ttu-id="e5420-116">**Obligatoire**</span><span class="sxs-lookup"><span data-stu-id="e5420-116">**Required**</span></span>|<span data-ttu-id="e5420-117">**Type**</span><span class="sxs-lookup"><span data-stu-id="e5420-117">**Type**</span></span>|<span data-ttu-id="e5420-118">**Description**</span><span class="sxs-lookup"><span data-stu-id="e5420-118">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e5420-119"> Path</span><span class="sxs-lookup"><span data-stu-id="e5420-119">Path</span></span>  <br/> |<span data-ttu-id="e5420-120">Obligatoire</span><span class="sxs-lookup"><span data-stu-id="e5420-120">Required</span></span>  <br/> |<span data-ttu-id="e5420-121">System.String</span><span class="sxs-lookup"><span data-stu-id="e5420-121">System.String</span></span>  <br/> |<span data-ttu-id="e5420-122">Chemin d’accès complet du fichier où seront stockées les configurations de connecteur dans le nuage.</span><span class="sxs-lookup"><span data-stu-id="e5420-122">Full file path where the Cloud Connector configurations will be stored.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="e5420-123">Types d’entrées</span><span class="sxs-lookup"><span data-stu-id="e5420-123">Input Types</span></span>
<span data-ttu-id="e5420-124"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="e5420-124"></span></span>

<span data-ttu-id="e5420-125">Aucun.</span><span class="sxs-lookup"><span data-stu-id="e5420-125">None.</span></span> <span data-ttu-id="e5420-126">L’applet de commande Export-CcConfiguration n’accepte pas la saisie de données redirigées.</span><span class="sxs-lookup"><span data-stu-id="e5420-126">The Export-CcConfiguration cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="e5420-127">Types de retours</span><span class="sxs-lookup"><span data-stu-id="e5420-127">Return Types</span></span>
<span data-ttu-id="e5420-128"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="e5420-128"></span></span>

<span data-ttu-id="e5420-129">Aucun.</span><span class="sxs-lookup"><span data-stu-id="e5420-129">None.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="e5420-130">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e5420-130">See also</span></span>
<span data-ttu-id="e5420-131"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="e5420-131"></span></span>

<span data-ttu-id="e5420-132">Import-CcConfiguration</span><span class="sxs-lookup"><span data-stu-id="e5420-132">Import-CcConfiguration</span></span>
  

