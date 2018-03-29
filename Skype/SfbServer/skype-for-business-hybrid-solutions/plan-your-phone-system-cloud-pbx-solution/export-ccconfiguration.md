---
title: Exportation-CcConfiguration
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e3775bd6-682c-4f62-aafc-974fe3a65c61
description: Exporte le Skype pour la configuration du connecteur de Cloud Business Edition à un fichier local sur le Skype pour serveur hôte de connecteur de Cloud Business Edition.
ms.openlocfilehash: dfabf5f486190b13acd18f0ffcf67f9b7e37052c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="export-ccconfiguration"></a><span data-ttu-id="3215b-103">Exportation-CcConfiguration</span><span class="sxs-lookup"><span data-stu-id="3215b-103">Export-CcConfiguration</span></span>
 
<span data-ttu-id="3215b-104">Exporte le Skype pour la configuration du connecteur de Cloud Business Edition à un fichier local sur le Skype pour serveur hôte de connecteur de Cloud Business Edition.</span><span class="sxs-lookup"><span data-stu-id="3215b-104">Exports the Skype for Business Cloud Connector Edition configuration to a local file on the Skype for Business Cloud Connector Edition host server.</span></span>
  
```
Export-CcConfiguration [-Path] <String> [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="3215b-105">Exemples</span><span class="sxs-lookup"><span data-stu-id="3215b-105">Examples</span></span>
<span data-ttu-id="3215b-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="3215b-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="3215b-107">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="3215b-107">Example 1</span></span>

<span data-ttu-id="3215b-108">L’exemple suivant définit le paramètre de chemin d’accès sous la forme d’un chemin d’accès complet du fichier et exporte les configurations à ce fichier.</span><span class="sxs-lookup"><span data-stu-id="3215b-108">The following example sets the Path parameter as a full file path and exports configurations to that file.</span></span>
  
```
Export-CcConfiguration -Path "C:\test\CloudConnector.ini" 
```

## <a name="detailed-description"></a><span data-ttu-id="3215b-109">Description détaillée</span><span class="sxs-lookup"><span data-stu-id="3215b-109">Detailed Description</span></span>
<span data-ttu-id="3215b-110"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="3215b-110"></span></span>

<span data-ttu-id="3215b-111">L’applet de commande exportation-CcConfiguration vous permet d’enregistrer la configuration du connecteur du Cloud dans un fichier dans un chemin d’accès sélectionné.</span><span class="sxs-lookup"><span data-stu-id="3215b-111">The Export-CcConfiguration cmdlet allows you to save the Cloud Connector configuration to a file in a selected path.</span></span> <span data-ttu-id="3215b-112">Cette commande a été introduite dans le nuage lien Edition version 2.0.</span><span class="sxs-lookup"><span data-stu-id="3215b-112">This command was introduced in Cloud Connector Edition version 2.0.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="3215b-113">Paramètres</span><span class="sxs-lookup"><span data-stu-id="3215b-113">Parameters</span></span>
<span data-ttu-id="3215b-114"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="3215b-114"></span></span>

|<span data-ttu-id="3215b-115">**Paramètre**</span><span class="sxs-lookup"><span data-stu-id="3215b-115">**Parameter**</span></span>|<span data-ttu-id="3215b-116">**Obligatoire**</span><span class="sxs-lookup"><span data-stu-id="3215b-116">**Required**</span></span>|<span data-ttu-id="3215b-117">**Type de**</span><span class="sxs-lookup"><span data-stu-id="3215b-117">**Type**</span></span>|<span data-ttu-id="3215b-118">**Description**</span><span class="sxs-lookup"><span data-stu-id="3215b-118">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="3215b-119"> Path</span><span class="sxs-lookup"><span data-stu-id="3215b-119">Path</span></span>  <br/> |<span data-ttu-id="3215b-120">Obligatoire</span><span class="sxs-lookup"><span data-stu-id="3215b-120">Required</span></span>  <br/> |<span data-ttu-id="3215b-121">System.String</span><span class="sxs-lookup"><span data-stu-id="3215b-121">System.String</span></span>  <br/> |<span data-ttu-id="3215b-122">Chemin complet du fichier où seront stockées les configurations de connecteur de nuage.</span><span class="sxs-lookup"><span data-stu-id="3215b-122">Full file path where the Cloud Connector configurations will be stored.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="3215b-123">Types d’entrées</span><span class="sxs-lookup"><span data-stu-id="3215b-123">Input Types</span></span>
<span data-ttu-id="3215b-124"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="3215b-124"></span></span>

<span data-ttu-id="3215b-125">Aucun.</span><span class="sxs-lookup"><span data-stu-id="3215b-125">None.</span></span> <span data-ttu-id="3215b-126">L’applet de commande exportation-CcConfiguration n’accepte pas les entrées de pipeline.</span><span class="sxs-lookup"><span data-stu-id="3215b-126">The Export-CcConfiguration cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="3215b-127">Types de retours</span><span class="sxs-lookup"><span data-stu-id="3215b-127">Return Types</span></span>
<span data-ttu-id="3215b-128"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="3215b-128"></span></span>

<span data-ttu-id="3215b-129">Aucun.</span><span class="sxs-lookup"><span data-stu-id="3215b-129">None.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="3215b-130">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3215b-130">See also</span></span>
<span data-ttu-id="3215b-131"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="3215b-131"></span></span>

<span data-ttu-id="3215b-132">Importation-CcConfiguration</span><span class="sxs-lookup"><span data-stu-id="3215b-132">Import-CcConfiguration</span></span>
  

