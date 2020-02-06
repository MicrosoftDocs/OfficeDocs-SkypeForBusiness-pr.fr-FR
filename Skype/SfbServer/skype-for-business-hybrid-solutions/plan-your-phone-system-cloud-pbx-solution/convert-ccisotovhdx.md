---
title: Convert-CcIsoToVhdx
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
ms.assetid: 216abec2-d354-4ee3-9999-0a6b350a4a5f
description: L’applet de commande Convert-CcIsoToVhdx crée un fichier de disque dur virtuel de base (VHDX) en utilisant un fichier ISO fourni au client de Windows Server 2012 R2. Le fichier VHDX sera utilisé pendant le déploiement de la version Cloud Connector de Skype Entreprise.
ms.openlocfilehash: f6b16c27b82919f24b9ee0e3094fb03fffa6443b
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802424"
---
# <a name="convert-ccisotovhdx"></a><span data-ttu-id="49bb1-104">Convert-CcIsoToVhdx</span><span class="sxs-lookup"><span data-stu-id="49bb1-104">Convert-CcIsoToVhdx</span></span>
 
<span data-ttu-id="49bb1-p102">L’applet de commande Convert-CcIsoToVhdx crée un fichier de disque dur virtuel de base (VHDX) en utilisant un fichier ISO fourni au client de Windows Server 2012 R2. Le fichier VHDX sera utilisé pendant le déploiement de la version Cloud Connector de Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="49bb1-p102">The Convert-CcIsoToVhdx cmdlet creates a base virtual hard disk file (VHDX) using a customer supplied Windows Server 2012 R2 ISO file. The VHDX file will be used during the deployment of Skype for Business Cloud Connector Edition.</span></span>
  
```powershell
Convert-CcIsoToVhdx [[-IsoFilePath] <string>] [-GeneralizeOnly] [-PauseBeforeUpdate]
```

## <a name="parameters"></a><span data-ttu-id="49bb1-107">Paramètres</span><span class="sxs-lookup"><span data-stu-id="49bb1-107">Parameters</span></span>

|<span data-ttu-id="49bb1-108">**Paramètre**</span><span class="sxs-lookup"><span data-stu-id="49bb1-108">**Parameter**</span></span>|<span data-ttu-id="49bb1-109">**Obligatoire**</span><span class="sxs-lookup"><span data-stu-id="49bb1-109">**Required**</span></span>|<span data-ttu-id="49bb1-110">**Type**</span><span class="sxs-lookup"><span data-stu-id="49bb1-110">**Type**</span></span>|<span data-ttu-id="49bb1-111">**Description**</span><span class="sxs-lookup"><span data-stu-id="49bb1-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="49bb1-112">IsoFilePath</span><span class="sxs-lookup"><span data-stu-id="49bb1-112">IsoFilePath</span></span>  <br/> | <span data-ttu-id="49bb1-113">Obligatoire</span><span class="sxs-lookup"><span data-stu-id="49bb1-113">Required</span></span> <br/> |<span data-ttu-id="49bb1-114">System.String</span><span class="sxs-lookup"><span data-stu-id="49bb1-114">System.String</span></span>  <br/> | <span data-ttu-id="49bb1-115">Le chemin d’accès vers le fichier ISO de Windows Server 2012 R2. </span><span class="sxs-lookup"><span data-stu-id="49bb1-115">The path to the Windows Server 2012 R2 ISO file.</span></span> <br/> |
|<span data-ttu-id="49bb1-116">GeneralizeOnly</span><span class="sxs-lookup"><span data-stu-id="49bb1-116">GeneralizeOnly</span></span>  <br/> |<span data-ttu-id="49bb1-117">Facultatif</span><span class="sxs-lookup"><span data-stu-id="49bb1-117">Optional</span></span>  <br/> |<span data-ttu-id="49bb1-118">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="49bb1-118">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="49bb1-p103">Si le processus de conversion échoue pendant la mise à jour de Windows, vous pouvez essayer de configurer un réseau/proxy et mettre à jour Manuellement Windows. Après avoir effectué le travail manuel, vous pouvez exécuter cette applet de commande avec le paramètre GeneralizeOnly qui terminera les tâches à accomplir. </span><span class="sxs-lookup"><span data-stu-id="49bb1-p103">If the conversion process fails during Windows update, you can try to configure a network/proxy and update Windows manually. After the manual work is done, you can run this cmdlet with the -GeneralizeOnly parameter and it will complete the remaining jobs.</span></span>  <br/> |
|<span data-ttu-id="49bb1-121">PauseBeforeUpdate</span><span class="sxs-lookup"><span data-stu-id="49bb1-121">PauseBeforeUpdate</span></span>  <br/> |<span data-ttu-id="49bb1-122">Facultatif</span><span class="sxs-lookup"><span data-stu-id="49bb1-122">Optional</span></span>  <br/> |<span data-ttu-id="49bb1-123">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="49bb1-123">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="49bb1-p104">Pour mettre à jour Windows, certaines configurations manuelles réseau/proxy configuration peuvent être nécessaires sur les machines virtuelles de base. Le processus de conversion va être suspendu avant la mise à jour de Windows si ce paramètre est fourni. Après avoir effectué la configuration manuelle, vous pouvez reprendre le processus. </span><span class="sxs-lookup"><span data-stu-id="49bb1-p104">To update Windows, some manual network/proxy configuration on the base VM might be necessary. The conversion process will pause before Windows update if this parameter is provided. After the manual configuration is done, you can resume the process.</span></span>  <br/> |
   
## <a name="examples"></a><span data-ttu-id="49bb1-127">Exemples</span><span class="sxs-lookup"><span data-stu-id="49bb1-127">Examples</span></span>
<span data-ttu-id="49bb1-128"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="49bb1-128"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="49bb1-129">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="49bb1-129">Example 1</span></span>

<span data-ttu-id="49bb1-130">L’exemple suivant prépare le fichier VHDX de base en utilisant un fichier ISO de Windows Server 2012 R2 situé dans "C:\Windows_Server_2012_R2-EN-US-x64.ISO": </span><span class="sxs-lookup"><span data-stu-id="49bb1-130">The following example prepares the base VHDX file using a Windows Server 2012 R2 ISO file located at "C:\Windows_Server_2012_R2-EN-US-x64.ISO":</span></span> 
  
```powershell
Convert-CcIsoToVhdx -IsoFilePath "C:\Windows_Server_2012_R2-EN-US-x64.ISO" 
```

### <a name="example-2"></a><span data-ttu-id="49bb1-131">Exemple 2</span><span class="sxs-lookup"><span data-stu-id="49bb1-131">Example 2</span></span>

<span data-ttu-id="49bb1-132">Si l’applet de connexion Convert-CcIsoToVhdx échoue lors de la mise à jour de Windows, il est probable qu’il n’y a pas de configuration réseau/proxy incorrecte.</span><span class="sxs-lookup"><span data-stu-id="49bb1-132">If the Convert-CcIsoToVhdx cmdlet fails during Windows update, it's probably because of incorrect network/proxy configuration.</span></span> <span data-ttu-id="49bb1-133">Vous pouvez suivre les instructions dans le message d'erreur et vous connecter à la machine virtuelle de base pour corriger le problème et mettre à jour manuellement Windows.</span><span class="sxs-lookup"><span data-stu-id="49bb1-133">You can follow the instructions in the error message and log on to the base virtual machine to fix the issue and update Windows manually.</span></span> <span data-ttu-id="49bb1-134">Après avoir effectué les tâches manuelles, exécutez à nouveau l’applet de commande à l’aide du paramètre GeneralizeOnly afin de terminer les tâches à accomplir :</span><span class="sxs-lookup"><span data-stu-id="49bb1-134">After the manual work is done, run the cmdlet again with the -GeneralizeOnly parameter to complete the remaining jobs:</span></span> 
  
```powershell
Convert-CcIsoToVhdx -IsoFilePath "C:\Windows_Server_2012_R2-EN-US-x64.ISO" -GeneralizeOnly
```

### <a name="example-3"></a><span data-ttu-id="49bb1-135">Exemple 3</span><span class="sxs-lookup"><span data-stu-id="49bb1-135">Example 3</span></span>

<span data-ttu-id="49bb1-136">Si la configuration manuelle est nécessaire pour mettre à jour Windows, vous pouvez utiliser le paramètre -PauseBeforeUpdate.</span><span class="sxs-lookup"><span data-stu-id="49bb1-136">If manual configuration is necessary to update Windows, you can use the -PauseBeforeUpdate parameter.</span></span> <span data-ttu-id="49bb1-137">Ce paramètre permet de suspendre le Cloud Connector avant le processus Windows Update.</span><span class="sxs-lookup"><span data-stu-id="49bb1-137">With this parameter, Cloud Connector will pause before the Windows update process.</span></span> <span data-ttu-id="49bb1-138">Vous pouvez ensuite terminer la configuration manuelle et achever le processus de conversion de la manière suivante :</span><span class="sxs-lookup"><span data-stu-id="49bb1-138">You can then complete the manual configuration and resume the conversion process as follows:</span></span>
  
```powershell
Convert-CcIsoToVhdx -IsoFilePath "C:\Windows_Server_2012_R2-EN-US-x64.ISO" -PauseBeforeUpdate 
```

## <a name="detailed-description"></a><span data-ttu-id="49bb1-139">Description détaillée</span><span class="sxs-lookup"><span data-stu-id="49bb1-139">Detailed Description</span></span>
<span data-ttu-id="49bb1-140"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="49bb1-140"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="49bb1-141">L’applet de connexion Convert-CcIsoToVhdx crée d’abord un VM de base, installe certains composants de base dont dépend le Cloud Connector, puis installe les mises à jour Windows.</span><span class="sxs-lookup"><span data-stu-id="49bb1-141">The Convert-CcIsoToVhdx cmdlet creates a base VM first, installs some basic components that Cloud Connector depends on, and then installs Windows updates.</span></span> <span data-ttu-id="49bb1-142">Enfin, il généralise l’ordinateur virtuel (Sysprep) pour obtenir un fichier VHDX de base qui sera utilisé par les machines virtuelles d’un appareil de connecteur Cloud.</span><span class="sxs-lookup"><span data-stu-id="49bb1-142">Finally, it generalizes the virtual machine (sysprep) to get a base VHDX file that will be used by the virtual machines of a Cloud Connector appliance.</span></span> 
  
## <a name="input-types"></a><span data-ttu-id="49bb1-143">Types d’entrées</span><span class="sxs-lookup"><span data-stu-id="49bb1-143">Input Types</span></span>
<span data-ttu-id="49bb1-144"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="49bb1-144"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="49bb1-p108">Aucun. L’applet de commande Convert-CcIsoToVhdx n’accepte pas l’entrée redirigée.</span><span class="sxs-lookup"><span data-stu-id="49bb1-p108">None. The Convert-CcIsoToVhdx cmdlet does not accept pipelined input.</span></span> 
  
## <a name="return-types"></a><span data-ttu-id="49bb1-147">Types de retours</span><span class="sxs-lookup"><span data-stu-id="49bb1-147">Return Types</span></span>
<span data-ttu-id="49bb1-148"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="49bb1-148"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="49bb1-149">Aucune</span><span class="sxs-lookup"><span data-stu-id="49bb1-149">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="49bb1-150">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="49bb1-150">See also</span></span>
<span data-ttu-id="49bb1-151"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="49bb1-151"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="49bb1-152">Aucun</span><span class="sxs-lookup"><span data-stu-id="49bb1-152">None</span></span>
  

