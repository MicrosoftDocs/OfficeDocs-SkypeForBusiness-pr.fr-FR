---
title: Importation-CcConfiguration
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 10/11/2017
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 461361a0-9aa9-469d-ace0-dc70b95cd4a3
description: Importe le Skype pour la configuration du connecteur de Cloud Business Edition à partir d’un fichier local sur le serveur hôte de connecteur de nuage.
ms.openlocfilehash: 46f4099258ce4090fa23ec980801e55f7300895f
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="import-ccconfiguration"></a><span data-ttu-id="6e4b9-103">Importation-CcConfiguration</span><span class="sxs-lookup"><span data-stu-id="6e4b9-103">Import-CcConfiguration</span></span>
 
<span data-ttu-id="6e4b9-104">Importe le Skype pour la configuration du connecteur de Cloud Business Edition à partir d’un fichier local sur le serveur hôte de connecteur de nuage.</span><span class="sxs-lookup"><span data-stu-id="6e4b9-104">Imports the Skype for Business Cloud Connector Edition configuration from a local file to the Cloud Connector host server.</span></span>
  
```

Import-CcConfiguration [-Force] [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="6e4b9-105">Exemples</span><span class="sxs-lookup"><span data-stu-id="6e4b9-105">Examples</span></span>
<span data-ttu-id="6e4b9-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="6e4b9-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="6e4b9-107">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="6e4b9-107">Example 1</span></span>

<span data-ttu-id="6e4b9-108">L’exemple suivant copie le CloudConnector.ini à partir du répertoire de la solution matérielle-logicielle de l’instance du connecteur de Cloud dans le répertoire de %SystemDrive%\ProgramData\CloudConnector :</span><span class="sxs-lookup"><span data-stu-id="6e4b9-108">The following example copies the CloudConnector.ini from the appliance directory of the Cloud Connector instance to %SystemDrive%\ProgramData\CloudConnector directory:</span></span>
  
```
Import-CcConfiguration
```

## <a name="detailed-description"></a><span data-ttu-id="6e4b9-109">Description détaillée</span><span class="sxs-lookup"><span data-stu-id="6e4b9-109">Detailed Description</span></span>
<span data-ttu-id="6e4b9-110"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="6e4b9-110"></span></span>

<span data-ttu-id="6e4b9-111">Cette applet de commande copie les CloudConnector.ini à partir du répertoire de la solution matérielle-logicielle de la solution matérielle-logicielle connecteur du Cloud dans le répertoire %SystemDrive%\ProgramData\CloudConnector.</span><span class="sxs-lookup"><span data-stu-id="6e4b9-111">This cmdlet copies the CloudConnector.ini from the appliance directory of the Cloud Connector appliance to the %SystemDrive%\ProgramData\CloudConnector directory.</span></span> <span data-ttu-id="6e4b9-112">L’annuaire d’appliances est précisé en utilisant l’applet de commande Set-CcApplianceDirectory cmdlet.</span><span class="sxs-lookup"><span data-stu-id="6e4b9-112">The appliance directory is specified by using the Set-CcApplianceDirectory cmdlet.</span></span> <span data-ttu-id="6e4b9-113">L’applet de commande remplace tout fichier existant dans % SystemDrive%\ProgramData\CloudConnector.</span><span class="sxs-lookup"><span data-stu-id="6e4b9-113">The cmdlet will overwrite any existing file in %SystemDrive%\ProgramData\CloudConnector.</span></span> <span data-ttu-id="6e4b9-114">Cette commande s’applique au nuage connecteur Edition version 2.0.1 et versions ultérieures.</span><span class="sxs-lookup"><span data-stu-id="6e4b9-114">This command applies to Cloud Connector Edition version 2.0.1 and later.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="6e4b9-115">Paramètres</span><span class="sxs-lookup"><span data-stu-id="6e4b9-115">Parameters</span></span>
<span data-ttu-id="6e4b9-116"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="6e4b9-116"></span></span>

|<span data-ttu-id="6e4b9-117">**Paramètre**</span><span class="sxs-lookup"><span data-stu-id="6e4b9-117">**Parameter**</span></span>|<span data-ttu-id="6e4b9-118">**Obligatoire**</span><span class="sxs-lookup"><span data-stu-id="6e4b9-118">**Required**</span></span>|<span data-ttu-id="6e4b9-119">**Type de**</span><span class="sxs-lookup"><span data-stu-id="6e4b9-119">**Type**</span></span>|<span data-ttu-id="6e4b9-120">**Description**</span><span class="sxs-lookup"><span data-stu-id="6e4b9-120">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="6e4b9-121">Force</span><span class="sxs-lookup"><span data-stu-id="6e4b9-121">Force</span></span>  <br/> |<span data-ttu-id="6e4b9-122">Facultatif</span><span class="sxs-lookup"><span data-stu-id="6e4b9-122">Optional</span></span>  <br/> |<span data-ttu-id="6e4b9-123">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="6e4b9-123">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="6e4b9-124">Remplacer le fichier existant dans la %SystemDrive%\ProgramData\CloudConnector sans notification.</span><span class="sxs-lookup"><span data-stu-id="6e4b9-124">Overwrite existing file in %SystemDrive%\ProgramData\CloudConnector without notification.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="6e4b9-125">Types d’entrées</span><span class="sxs-lookup"><span data-stu-id="6e4b9-125">Input Types</span></span>
<span data-ttu-id="6e4b9-126"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="6e4b9-126"></span></span>

<span data-ttu-id="6e4b9-127">Aucun.</span><span class="sxs-lookup"><span data-stu-id="6e4b9-127">None.</span></span> <span data-ttu-id="6e4b9-128">La cmdlet Import-CcConfiguration n’accepte pas les entrées de pipeline.</span><span class="sxs-lookup"><span data-stu-id="6e4b9-128">The Import-CcConfiguration cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="6e4b9-129">Types de retours</span><span class="sxs-lookup"><span data-stu-id="6e4b9-129">Return Types</span></span>
<span data-ttu-id="6e4b9-130"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="6e4b9-130"></span></span>

<span data-ttu-id="6e4b9-131">Aucun.</span><span class="sxs-lookup"><span data-stu-id="6e4b9-131">None.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="6e4b9-132">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6e4b9-132">See also</span></span>
<span data-ttu-id="6e4b9-133"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="6e4b9-133"></span></span>

<span data-ttu-id="6e4b9-134">Exportation-CcConfiguration</span><span class="sxs-lookup"><span data-stu-id="6e4b9-134">Export-CcConfiguration</span></span>
  

