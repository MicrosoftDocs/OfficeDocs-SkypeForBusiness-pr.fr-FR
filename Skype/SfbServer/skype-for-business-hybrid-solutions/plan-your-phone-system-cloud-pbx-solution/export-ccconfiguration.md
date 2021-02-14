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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: e3775bd6-682c-4f62-aafc-974fe3a65c61
description: Exporte la configuration de la version Cloud Connector de Skype Entreprise vers un fichier local sur le serveur hôte de la version Cloud Connector de Skype Entreprise.
ms.openlocfilehash: cd0745081e3f069aaf58c9ffdbf24494bfb3ece1
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41801464"
---
# <a name="export-ccconfiguration"></a><span data-ttu-id="0e310-103">Export-CcConfiguration</span><span class="sxs-lookup"><span data-stu-id="0e310-103">Export-CcConfiguration</span></span>
 
<span data-ttu-id="0e310-104">Exporte la configuration de la version Cloud Connector de Skype Entreprise vers un fichier local sur le serveur hôte de la version Cloud Connector de Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="0e310-104">Exports the Skype for Business Cloud Connector Edition configuration to a local file on the Skype for Business Cloud Connector Edition host server.</span></span>
  
```powershell
Export-CcConfiguration [-Path] <String> [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="0e310-105">Exemples</span><span class="sxs-lookup"><span data-stu-id="0e310-105">Examples</span></span>
<span data-ttu-id="0e310-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="0e310-106"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="0e310-107">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="0e310-107">Example 1</span></span>

<span data-ttu-id="0e310-108">L’exemple suivant définit le paramètre Path comme chemin d’accès complet et exporte les configurations dans ce fichier.</span><span class="sxs-lookup"><span data-stu-id="0e310-108">The following example sets the Path parameter as a full file path and exports configurations to that file.</span></span>
  
```powershell
Export-CcConfiguration -Path "C:\test\CloudConnector.ini" 
```

## <a name="detailed-description"></a><span data-ttu-id="0e310-109">Description détaillée</span><span class="sxs-lookup"><span data-stu-id="0e310-109">Detailed Description</span></span>
<span data-ttu-id="0e310-110"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="0e310-110"><a name="Examples"> </a></span></span>

<span data-ttu-id="0e310-111">LExport-CcConfiguration cmdlet vous permet d’enregistrer la configuration Cloud Connector dans un fichier dans un chemin d’accès sélectionné.</span><span class="sxs-lookup"><span data-stu-id="0e310-111">The Export-CcConfiguration cmdlet allows you to save the Cloud Connector configuration to a file in a selected path.</span></span> <span data-ttu-id="0e310-112">Cette commande a été introduite dans la version 2.0 de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="0e310-112">This command was introduced in Cloud Connector Edition version 2.0.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="0e310-113">Paramètres</span><span class="sxs-lookup"><span data-stu-id="0e310-113">Parameters</span></span>
<span data-ttu-id="0e310-114"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="0e310-114"><a name="Examples"> </a></span></span>

|<span data-ttu-id="0e310-115">**Paramètre**</span><span class="sxs-lookup"><span data-stu-id="0e310-115">**Parameter**</span></span>|<span data-ttu-id="0e310-116">**Obligatoire**</span><span class="sxs-lookup"><span data-stu-id="0e310-116">**Required**</span></span>|<span data-ttu-id="0e310-117">**Type**</span><span class="sxs-lookup"><span data-stu-id="0e310-117">**Type**</span></span>|<span data-ttu-id="0e310-118">**Description**</span><span class="sxs-lookup"><span data-stu-id="0e310-118">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="0e310-119">Path</span><span class="sxs-lookup"><span data-stu-id="0e310-119">Path</span></span>  <br/> |<span data-ttu-id="0e310-120">Requis</span><span class="sxs-lookup"><span data-stu-id="0e310-120">Required</span></span>  <br/> |<span data-ttu-id="0e310-121">System.String</span><span class="sxs-lookup"><span data-stu-id="0e310-121">System.String</span></span>  <br/> |<span data-ttu-id="0e310-122">Chemin d’accès complet au fichier dans lequel les configurations Cloud Connector seront stockées.</span><span class="sxs-lookup"><span data-stu-id="0e310-122">Full file path where the Cloud Connector configurations will be stored.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="0e310-123">Types d’entrée</span><span class="sxs-lookup"><span data-stu-id="0e310-123">Input Types</span></span>
<span data-ttu-id="0e310-124"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="0e310-124"><a name="Examples"> </a></span></span>

<span data-ttu-id="0e310-125">Aucun.</span><span class="sxs-lookup"><span data-stu-id="0e310-125">None.</span></span> <span data-ttu-id="0e310-126">La cmdlet Export-CcConfiguration n’accepte pas la saisie de données pipeline.</span><span class="sxs-lookup"><span data-stu-id="0e310-126">The Export-CcConfiguration cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="0e310-127">Types de retour</span><span class="sxs-lookup"><span data-stu-id="0e310-127">Return Types</span></span>
<span data-ttu-id="0e310-128"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="0e310-128"><a name="Examples"> </a></span></span>

<span data-ttu-id="0e310-129">Aucun.</span><span class="sxs-lookup"><span data-stu-id="0e310-129">None.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="0e310-130">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0e310-130">See also</span></span>
<span data-ttu-id="0e310-131"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="0e310-131"><a name="Examples"> </a></span></span>

<span data-ttu-id="0e310-132">Import-CcConfiguration</span><span class="sxs-lookup"><span data-stu-id="0e310-132">Import-CcConfiguration</span></span>
  

