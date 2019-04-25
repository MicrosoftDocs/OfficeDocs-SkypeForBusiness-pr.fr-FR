---
title: Export-CcConfigurationSampleFile
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0aaacc05-3430-4579-acbf-d7c7670c3864
description: L’applet de commande Export-CcConfigurationSampleFile exporte un fichier modèle de configuration (.ini) de la version Cloud Connector de Skype Entreprise vers l’annuaire d’appliances d’une appliance de Cloud Connector. Vous pouvez modifier et renommer le fichier à utiliser pour votre déploiement.
ms.openlocfilehash: 3154ff3492899de244c3033e4e35345132d04f20
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32233987"
---
# <a name="export-ccconfigurationsamplefile"></a><span data-ttu-id="d8862-104">Export-CcConfigurationSampleFile</span><span class="sxs-lookup"><span data-stu-id="d8862-104">Export-CcConfigurationSampleFile</span></span>
 
<span data-ttu-id="d8862-p102">L’applet de commande Export-CcConfigurationSampleFile exporte un fichier modèle de configuration (.ini) de la version Cloud Connector de Skype Entreprise vers l’annuaire d’appliances d’une appliance de Cloud Connector. Vous pouvez modifier et renommer le fichier à utiliser pour votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="d8862-p102">The Export-CcConfigurationSampleFile cmdlet exports a Skype for Business Cloud Connector Edition sample configuration file (.ini) to the appliance directory of a Cloud Connector appliance. You can modify and rename the file to use for your deployment.</span></span>
  
<span data-ttu-id="d8862-107">Cette applet de commande s’applique à Skype Entreprise, version Cloud Connector 1.4.1, 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="d8862-107">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```
Export-CcConfigurationSampleFile
```

## <a name="parameters"></a><span data-ttu-id="d8862-108">Paramètres</span><span class="sxs-lookup"><span data-stu-id="d8862-108">Parameters</span></span>

<span data-ttu-id="d8862-109">Aucun</span><span class="sxs-lookup"><span data-stu-id="d8862-109">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="d8862-110">Exemples</span><span class="sxs-lookup"><span data-stu-id="d8862-110">Examples</span></span>
<span data-ttu-id="d8862-111"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="d8862-111"></span></span>

### <a name="example-1"></a><span data-ttu-id="d8862-112">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="d8862-112">Example 1</span></span>

<span data-ttu-id="d8862-113">L’exemple suivant télécharge un exemple de fichier de configuration à partir du site de Microsoft et écrit dans le répertoire appliance de la solution de nuage connecteur :</span><span class="sxs-lookup"><span data-stu-id="d8862-113">The following example downloads a sample configuration file from the Microsoft site and writes it to the appliance directory of the Cloud Connector appliance:</span></span>
  
```
Export-CcConfigurationSampleFile
```

## <a name="detailed-description"></a><span data-ttu-id="d8862-114">Description détaillée</span><span class="sxs-lookup"><span data-stu-id="d8862-114">Detailed Description</span></span>
<span data-ttu-id="d8862-115"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="d8862-115"></span></span>

<span data-ttu-id="d8862-116">La version actuelle du nuage connecteur nécessite de disposer de plusieurs paramètres dans le fichier .ini ; par exemple, des paramètres tels que les adresses IP des ordinateurs virtuels pour les composants du nuage connecteur, les noms de composants, les paramètres de passerelle et ainsi de suite.</span><span class="sxs-lookup"><span data-stu-id="d8862-116">The current version of Cloud Connector requires you to provide several parameters in the .ini file; for example, parameters such as the IP addresses of virtual machines for the Cloud Connector components, component names, gateway parameters, and so on.</span></span>
  
<span data-ttu-id="d8862-117">Cette applet de commande, en cas d’exécution sur l’ordinateur hôte du nuage connecteur, télécharge un exemple de fichier .ini avec des exemples de configuration à partir du site de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d8862-117">This cmdlet, when run on the host machine of Cloud Connector, downloads a sample .ini file with configuration examples from the Microsoft site.</span></span> <span data-ttu-id="d8862-118">L’applet de commande écrit le fichier dans le répertoire appliance de la solution de nuage connecteur.</span><span class="sxs-lookup"><span data-stu-id="d8862-118">The cmdlet writes the file to the appliance directory of the Cloud Connector appliance.</span></span> <span data-ttu-id="d8862-119">L’annuaire d’appliances est précisé en utilisant l’applet de commande Set-CcApplianceDirectory cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d8862-119">The appliance directory is specified by using the Set-CcApplianceDirectory cmdlet.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="d8862-120">Types d’entrées</span><span class="sxs-lookup"><span data-stu-id="d8862-120">Input Types</span></span>
<span data-ttu-id="d8862-121"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="d8862-121"></span></span>

<span data-ttu-id="d8862-p104">Aucun. L’applet de commande Export-CcConfigurationSampleFile n’accepte pas l’entrée redirigée.</span><span class="sxs-lookup"><span data-stu-id="d8862-p104">None. The Export-CcConfigurationSampleFile cmdlet does not accept pipelined input.</span></span> 
  
## <a name="return-types"></a><span data-ttu-id="d8862-124">Types de retours</span><span class="sxs-lookup"><span data-stu-id="d8862-124">Return Types</span></span>
<span data-ttu-id="d8862-125"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="d8862-125"></span></span>

<span data-ttu-id="d8862-126">Aucun</span><span class="sxs-lookup"><span data-stu-id="d8862-126">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d8862-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d8862-127">See also</span></span>
<span data-ttu-id="d8862-128"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="d8862-128"></span></span>

[<span data-ttu-id="d8862-129">Set-CcApplianceDirectory</span><span class="sxs-lookup"><span data-stu-id="d8862-129">Set-CcApplianceDirectory</span></span>](set-ccappliancedirectory.md)
  

