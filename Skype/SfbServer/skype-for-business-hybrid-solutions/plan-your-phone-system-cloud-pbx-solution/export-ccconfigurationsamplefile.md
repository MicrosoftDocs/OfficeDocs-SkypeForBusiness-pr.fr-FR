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
localization_priority: Normal
ms.assetid: 0aaacc05-3430-4579-acbf-d7c7670c3864
description: L’applet de commande Export-CcConfigurationSampleFile exporte un fichier modèle de configuration (.ini) de la version Cloud Connector de Skype Entreprise vers l’annuaire d’appliances d’une appliance de Cloud Connector. Vous pouvez modifier et renommer le fichier à utiliser pour votre déploiement.
ms.openlocfilehash: b62d5d7ffa9e8f10aeae509201c5aa0a1e7fa0a4
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003424"
---
# <a name="export-ccconfigurationsamplefile"></a><span data-ttu-id="10196-104">Export-CcConfigurationSampleFile</span><span class="sxs-lookup"><span data-stu-id="10196-104">Export-CcConfigurationSampleFile</span></span>
 
<span data-ttu-id="10196-p102">L’applet de commande Export-CcConfigurationSampleFile exporte un fichier modèle de configuration (.ini) de la version Cloud Connector de Skype Entreprise vers l’annuaire d’appliances d’une appliance de Cloud Connector. Vous pouvez modifier et renommer le fichier à utiliser pour votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="10196-p102">The Export-CcConfigurationSampleFile cmdlet exports a Skype for Business Cloud Connector Edition sample configuration file (.ini) to the appliance directory of a Cloud Connector appliance. You can modify and rename the file to use for your deployment.</span></span>
  
<span data-ttu-id="10196-107">Cette applet de commande s’applique à Skype Entreprise, version Cloud Connector 1.4.1, 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="10196-107">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```powershell
Export-CcConfigurationSampleFile
```

## <a name="parameters"></a><span data-ttu-id="10196-108">Paramètres</span><span class="sxs-lookup"><span data-stu-id="10196-108">Parameters</span></span>

<span data-ttu-id="10196-109">Aucun</span><span class="sxs-lookup"><span data-stu-id="10196-109">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="10196-110">Exemples</span><span class="sxs-lookup"><span data-stu-id="10196-110">Examples</span></span>
<span data-ttu-id="10196-111"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="10196-111"></span></span>

### <a name="example-1"></a><span data-ttu-id="10196-112">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="10196-112">Example 1</span></span>

<span data-ttu-id="10196-113">L’exemple suivant permet de télécharger un exemple de fichier de configuration à partir du site Microsoft et de l’écrire dans le répertoire de l’application du dispositif Cloud Connector :</span><span class="sxs-lookup"><span data-stu-id="10196-113">The following example downloads a sample configuration file from the Microsoft site and writes it to the appliance directory of the Cloud Connector appliance:</span></span>
  
```powershell
Export-CcConfigurationSampleFile
```

## <a name="detailed-description"></a><span data-ttu-id="10196-114">Description détaillée</span><span class="sxs-lookup"><span data-stu-id="10196-114">Detailed Description</span></span>
<span data-ttu-id="10196-115"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="10196-115"></span></span>

<span data-ttu-id="10196-116">La version actuelle de Cloud Connector nécessite que vous fournissiez plusieurs paramètres dans le fichier. ini ; par exemple, des paramètres tels que les adresses IP d’ordinateurs virtuels pour les composants Cloud Connector, les noms de composants, les paramètres de passerelle, etc.</span><span class="sxs-lookup"><span data-stu-id="10196-116">The current version of Cloud Connector requires you to provide several parameters in the .ini file; for example, parameters such as the IP addresses of virtual machines for the Cloud Connector components, component names, gateway parameters, and so on.</span></span>
  
<span data-ttu-id="10196-117">Lors de l’exécution de cette applet de connexion sur l’ordinateur hôte du Cloud Connector, télécharge un exemple de fichier. ini contenant des exemples de configuration du site Microsoft.</span><span class="sxs-lookup"><span data-stu-id="10196-117">This cmdlet, when run on the host machine of Cloud Connector, downloads a sample .ini file with configuration examples from the Microsoft site.</span></span> <span data-ttu-id="10196-118">L’applet de connexion écrit le fichier dans le répertoire de l’application Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="10196-118">The cmdlet writes the file to the appliance directory of the Cloud Connector appliance.</span></span> <span data-ttu-id="10196-119">L’annuaire d’appliances est précisé en utilisant l’applet de commande Set-CcApplianceDirectory cmdlet.</span><span class="sxs-lookup"><span data-stu-id="10196-119">The appliance directory is specified by using the Set-CcApplianceDirectory cmdlet.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="10196-120">Types d’entrées</span><span class="sxs-lookup"><span data-stu-id="10196-120">Input Types</span></span>
<span data-ttu-id="10196-121"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="10196-121"></span></span>

<span data-ttu-id="10196-p104">Aucun. L’applet de commande Export-CcConfigurationSampleFile n’accepte pas l’entrée redirigée.</span><span class="sxs-lookup"><span data-stu-id="10196-p104">None. The Export-CcConfigurationSampleFile cmdlet does not accept pipelined input.</span></span> 
  
## <a name="return-types"></a><span data-ttu-id="10196-124">Types de retours</span><span class="sxs-lookup"><span data-stu-id="10196-124">Return Types</span></span>
<span data-ttu-id="10196-125"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="10196-125"></span></span>

<span data-ttu-id="10196-126">Aucun</span><span class="sxs-lookup"><span data-stu-id="10196-126">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="10196-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="10196-127">See also</span></span>
<span data-ttu-id="10196-128"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="10196-128"></span></span>

[<span data-ttu-id="10196-129">Set-CcApplianceDirectory</span><span class="sxs-lookup"><span data-stu-id="10196-129">Set-CcApplianceDirectory</span></span>](set-ccappliancedirectory.md)
  

