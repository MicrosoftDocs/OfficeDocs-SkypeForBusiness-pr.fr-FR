---
title: Export-CcConfigurationSampleFile
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 0aaacc05-3430-4579-acbf-d7c7670c3864
description: La cmdlet Export-CcConfigurationSampleFile exporte un exemple de fichier de configuration (.ini) de la version Cloud Connector de Skype Entreprise vers l’annuaire d’équipements d’une appliance Cloud Connector. Vous pouvez modifier et renommer le fichier à utiliser pour votre déploiement.
ms.openlocfilehash: a29a3db8e77ee239263d015bd7a3efcf4f3f7c5c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41801004"
---
# <a name="export-ccconfigurationsamplefile"></a><span data-ttu-id="fe9c3-104">Export-CcConfigurationSampleFile</span><span class="sxs-lookup"><span data-stu-id="fe9c3-104">Export-CcConfigurationSampleFile</span></span>
 
<span data-ttu-id="fe9c3-105">La cmdlet Export-CcConfigurationSampleFile exporte un exemple de fichier de configuration (.ini) de la version Cloud Connector de Skype Entreprise vers l’annuaire d’équipements d’une appliance Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="fe9c3-105">The Export-CcConfigurationSampleFile cmdlet exports a Skype for Business Cloud Connector Edition sample configuration file (.ini) to the appliance directory of a Cloud Connector appliance.</span></span> <span data-ttu-id="fe9c3-106">Vous pouvez modifier et renommer le fichier à utiliser pour votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="fe9c3-106">You can modify and rename the file to use for your deployment.</span></span>
  
<span data-ttu-id="fe9c3-107">Cette cmdlet s’applique à Skype Entreprise, version Cloud Connector 1.4.1, 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="fe9c3-107">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```powershell
Export-CcConfigurationSampleFile
```

## <a name="parameters"></a><span data-ttu-id="fe9c3-108">Paramètres</span><span class="sxs-lookup"><span data-stu-id="fe9c3-108">Parameters</span></span>

<span data-ttu-id="fe9c3-109">Aucun</span><span class="sxs-lookup"><span data-stu-id="fe9c3-109">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="fe9c3-110">Exemples</span><span class="sxs-lookup"><span data-stu-id="fe9c3-110">Examples</span></span>
<span data-ttu-id="fe9c3-111"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="fe9c3-111"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="fe9c3-112">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="fe9c3-112">Example 1</span></span>

<span data-ttu-id="fe9c3-113">L’exemple suivant télécharge un exemple de fichier de configuration à partir du site Microsoft et l’écrit dans l’annuaire d’appliances de l’appliance Cloud Connector :</span><span class="sxs-lookup"><span data-stu-id="fe9c3-113">The following example downloads a sample configuration file from the Microsoft site and writes it to the appliance directory of the Cloud Connector appliance:</span></span>
  
```powershell
Export-CcConfigurationSampleFile
```

## <a name="detailed-description"></a><span data-ttu-id="fe9c3-114">Description détaillée</span><span class="sxs-lookup"><span data-stu-id="fe9c3-114">Detailed Description</span></span>
<span data-ttu-id="fe9c3-115"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="fe9c3-115"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="fe9c3-116">La version actuelle de Cloud Connector nécessite que vous fournissiez plusieurs paramètres dans le fichier .ini . par exemple, les paramètres tels que les adresses IP des machines virtuelles pour les composants Cloud Connector, les noms des composants, les paramètres de passerelle, etc.</span><span class="sxs-lookup"><span data-stu-id="fe9c3-116">The current version of Cloud Connector requires you to provide several parameters in the .ini file; for example, parameters such as the IP addresses of virtual machines for the Cloud Connector components, component names, gateway parameters, and so on.</span></span>
  
<span data-ttu-id="fe9c3-117">Cette cmdlet, lorsqu’elle est exécuté sur l’ordinateur hôte de Cloud Connector, télécharge un exemple de fichier .ini avec des exemples de configuration à partir du site Microsoft.</span><span class="sxs-lookup"><span data-stu-id="fe9c3-117">This cmdlet, when run on the host machine of Cloud Connector, downloads a sample .ini file with configuration examples from the Microsoft site.</span></span> <span data-ttu-id="fe9c3-118">L’cmdlet écrit le fichier dans l’annuaire d’appliances de l’appliance Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="fe9c3-118">The cmdlet writes the file to the appliance directory of the Cloud Connector appliance.</span></span> <span data-ttu-id="fe9c3-119">Le répertoire de l’appliance est spécifié à l’aide Set-CcApplianceDirectory cmdlet.</span><span class="sxs-lookup"><span data-stu-id="fe9c3-119">The appliance directory is specified by using the Set-CcApplianceDirectory cmdlet.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="fe9c3-120">Types d’entrée</span><span class="sxs-lookup"><span data-stu-id="fe9c3-120">Input Types</span></span>
<span data-ttu-id="fe9c3-121"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="fe9c3-121"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="fe9c3-122">Aucun.</span><span class="sxs-lookup"><span data-stu-id="fe9c3-122">None.</span></span> <span data-ttu-id="fe9c3-123">La cmdlet Export-CcConfigurationSampleFile n’accepte pas la saisie de données pipeline.</span><span class="sxs-lookup"><span data-stu-id="fe9c3-123">The Export-CcConfigurationSampleFile cmdlet does not accept pipelined input.</span></span> 
  
## <a name="return-types"></a><span data-ttu-id="fe9c3-124">Types de retour</span><span class="sxs-lookup"><span data-stu-id="fe9c3-124">Return Types</span></span>
<span data-ttu-id="fe9c3-125"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="fe9c3-125"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="fe9c3-126">Aucun</span><span class="sxs-lookup"><span data-stu-id="fe9c3-126">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="fe9c3-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="fe9c3-127">See also</span></span>
<span data-ttu-id="fe9c3-128"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="fe9c3-128"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="fe9c3-129">Set-CcApplianceDirectory</span><span class="sxs-lookup"><span data-stu-id="fe9c3-129">Set-CcApplianceDirectory</span></span>](set-ccappliancedirectory.md)
  

