---
title: Import-CcConfiguration
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 10/11/2017
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 461361a0-9aa9-469d-ace0-dc70b95cd4a3
description: Importe la configuration de la version Cloud Connector de Skype Entreprise à partir d’un fichier local vers le serveur hôte Cloud Connector.
ms.openlocfilehash: 626ba52d4d67f99dd67d3d1f91d26d6e6d03f95e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799854"
---
# <a name="import-ccconfiguration"></a><span data-ttu-id="1bbe7-103">Import-CcConfiguration</span><span class="sxs-lookup"><span data-stu-id="1bbe7-103">Import-CcConfiguration</span></span>
 
<span data-ttu-id="1bbe7-104">Importe la configuration de la version Cloud Connector de Skype Entreprise à partir d’un fichier local vers le serveur hôte Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="1bbe7-104">Imports the Skype for Business Cloud Connector Edition configuration from a local file to the Cloud Connector host server.</span></span>
  
```powershell
Import-CcConfiguration [-Force] [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="1bbe7-105">Exemples</span><span class="sxs-lookup"><span data-stu-id="1bbe7-105">Examples</span></span>
<span data-ttu-id="1bbe7-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="1bbe7-106"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="1bbe7-107">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="1bbe7-107">Example 1</span></span>

<span data-ttu-id="1bbe7-108">L’exemple suivant copie le CloudConnector.ini du répertoire d’appliances de l’instance Cloud Connector dans le répertoire %SystemDrive%\ProgramData\CloudConnector :</span><span class="sxs-lookup"><span data-stu-id="1bbe7-108">The following example copies the CloudConnector.ini from the appliance directory of the Cloud Connector instance to %SystemDrive%\ProgramData\CloudConnector directory:</span></span>
  
```powershell
Import-CcConfiguration
```

## <a name="detailed-description"></a><span data-ttu-id="1bbe7-109">Description détaillée</span><span class="sxs-lookup"><span data-stu-id="1bbe7-109">Detailed Description</span></span>
<span data-ttu-id="1bbe7-110"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="1bbe7-110"><a name="Examples"> </a></span></span>

<span data-ttu-id="1bbe7-111">Cette cmdlet copie le CloudConnector.ini du répertoire d’appliances de l’appliance Cloud Connector vers le répertoire %SystemDrive%\ProgramData\CloudConnector.</span><span class="sxs-lookup"><span data-stu-id="1bbe7-111">This cmdlet copies the CloudConnector.ini from the appliance directory of the Cloud Connector appliance to the %SystemDrive%\ProgramData\CloudConnector directory.</span></span> <span data-ttu-id="1bbe7-112">Le répertoire de l’appliance est spécifié à l’aide Set-CcApplianceDirectory cmdlet.</span><span class="sxs-lookup"><span data-stu-id="1bbe7-112">The appliance directory is specified by using the Set-CcApplianceDirectory cmdlet.</span></span> <span data-ttu-id="1bbe7-113">L’cmdlet va supprimer tout fichier existant dans %SystemDrive%\ProgramData\CloudConnector.</span><span class="sxs-lookup"><span data-stu-id="1bbe7-113">The cmdlet will overwrite any existing file in %SystemDrive%\ProgramData\CloudConnector.</span></span> <span data-ttu-id="1bbe7-114">Cette commande s’applique aux versions 2.0.1 et ultérieures de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="1bbe7-114">This command applies to Cloud Connector Edition version 2.0.1 and later.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="1bbe7-115">Paramètres</span><span class="sxs-lookup"><span data-stu-id="1bbe7-115">Parameters</span></span>
<span data-ttu-id="1bbe7-116"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="1bbe7-116"><a name="Examples"> </a></span></span>

|<span data-ttu-id="1bbe7-117">**Paramètre**</span><span class="sxs-lookup"><span data-stu-id="1bbe7-117">**Parameter**</span></span>|<span data-ttu-id="1bbe7-118">**Obligatoire**</span><span class="sxs-lookup"><span data-stu-id="1bbe7-118">**Required**</span></span>|<span data-ttu-id="1bbe7-119">**Type**</span><span class="sxs-lookup"><span data-stu-id="1bbe7-119">**Type**</span></span>|<span data-ttu-id="1bbe7-120">**Description**</span><span class="sxs-lookup"><span data-stu-id="1bbe7-120">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="1bbe7-121">Force</span><span class="sxs-lookup"><span data-stu-id="1bbe7-121">Force</span></span>  <br/> |<span data-ttu-id="1bbe7-122">Facultatif</span><span class="sxs-lookup"><span data-stu-id="1bbe7-122">Optional</span></span>  <br/> |<span data-ttu-id="1bbe7-123">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="1bbe7-123">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="1bbe7-124">Overwrite existing file in %SystemDrive%\ProgramData\CloudConnector without notification.</span><span class="sxs-lookup"><span data-stu-id="1bbe7-124">Overwrite existing file in %SystemDrive%\ProgramData\CloudConnector without notification.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="1bbe7-125">Types d’entrée</span><span class="sxs-lookup"><span data-stu-id="1bbe7-125">Input Types</span></span>
<span data-ttu-id="1bbe7-126"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="1bbe7-126"><a name="Examples"> </a></span></span>

<span data-ttu-id="1bbe7-127">Aucun.</span><span class="sxs-lookup"><span data-stu-id="1bbe7-127">None.</span></span> <span data-ttu-id="1bbe7-128">La cmdlet Import-CcConfiguration n’accepte pas la saisie de données pipeline.</span><span class="sxs-lookup"><span data-stu-id="1bbe7-128">The Import-CcConfiguration cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="1bbe7-129">Types de retour</span><span class="sxs-lookup"><span data-stu-id="1bbe7-129">Return Types</span></span>
<span data-ttu-id="1bbe7-130"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="1bbe7-130"><a name="Examples"> </a></span></span>

<span data-ttu-id="1bbe7-131">Aucun.</span><span class="sxs-lookup"><span data-stu-id="1bbe7-131">None.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="1bbe7-132">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1bbe7-132">See also</span></span>
<span data-ttu-id="1bbe7-133"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="1bbe7-133"><a name="Examples"> </a></span></span>

<span data-ttu-id="1bbe7-134">Export-CcConfiguration</span><span class="sxs-lookup"><span data-stu-id="1bbe7-134">Export-CcConfiguration</span></span>
  

