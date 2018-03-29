---
title: Convert-CcIsoToVhdx
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 216abec2-d354-4ee3-9999-0a6b350a4a5f
description: L’applet de commande Convert-CcIsoToVhdx crée un fichier de disque dur virtuel de base (VHDX) en utilisant un fichier ISO fourni au client de Windows Server 2012 R2. Le fichier VHDX sera utilisé pendant le déploiement de la version Cloud Connector de Skype Entreprise.
ms.openlocfilehash: 9bf27e7161a3d5c74cc972df12246c36226be8cc
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="convert-ccisotovhdx"></a><span data-ttu-id="496b6-104">Convert-CcIsoToVhdx</span><span class="sxs-lookup"><span data-stu-id="496b6-104">Convert-CcIsoToVhdx</span></span>
 
<span data-ttu-id="496b6-p102">L’applet de commande Convert-CcIsoToVhdx crée un fichier de disque dur virtuel de base (VHDX) en utilisant un fichier ISO fourni au client de Windows Server 2012 R2. Le fichier VHDX sera utilisé pendant le déploiement de la version Cloud Connector de Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="496b6-p102">The Convert-CcIsoToVhdx cmdlet creates a base virtual hard disk file (VHDX) using a customer supplied Windows Server 2012 R2 ISO file. The VHDX file will be used during the deployment of Skype for Business Cloud Connector Edition.</span></span>
  
```
Convert-CcIsoToVhdx [[-IsoFilePath] <string>] [-GeneralizeOnly] [-PauseBeforeUpdate]
```

## <a name="parameters"></a><span data-ttu-id="496b6-107">Paramètres</span><span class="sxs-lookup"><span data-stu-id="496b6-107">Parameters</span></span>

|<span data-ttu-id="496b6-108">**Paramètre**</span><span class="sxs-lookup"><span data-stu-id="496b6-108">**Parameter**</span></span>|<span data-ttu-id="496b6-109">**Obligatoire**</span><span class="sxs-lookup"><span data-stu-id="496b6-109">**Required**</span></span>|<span data-ttu-id="496b6-110">**Type de**</span><span class="sxs-lookup"><span data-stu-id="496b6-110">**Type**</span></span>|<span data-ttu-id="496b6-111">**Description**</span><span class="sxs-lookup"><span data-stu-id="496b6-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="496b6-112">IsoFilePath</span><span class="sxs-lookup"><span data-stu-id="496b6-112">IsoFilePath</span></span>  <br/> | <span data-ttu-id="496b6-113">Obligatoire</span><span class="sxs-lookup"><span data-stu-id="496b6-113">Required</span></span> <br/> |<span data-ttu-id="496b6-114">System.String</span><span class="sxs-lookup"><span data-stu-id="496b6-114">System.String</span></span>  <br/> | <span data-ttu-id="496b6-115">Le chemin d’accès vers le fichier ISO de Windows Server 2012 R2. </span><span class="sxs-lookup"><span data-stu-id="496b6-115">The path to the Windows Server 2012 R2 ISO file.</span></span> <br/> |
|<span data-ttu-id="496b6-116">GeneralizeOnly</span><span class="sxs-lookup"><span data-stu-id="496b6-116">GeneralizeOnly</span></span>  <br/> |<span data-ttu-id="496b6-117">Facultatif</span><span class="sxs-lookup"><span data-stu-id="496b6-117">Optional</span></span>  <br/> |<span data-ttu-id="496b6-118">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="496b6-118">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="496b6-p103">Si le processus de conversion échoue pendant la mise à jour de Windows, vous pouvez essayer de configurer un réseau/proxy et mettre à jour Manuellement Windows. Après avoir effectué le travail manuel, vous pouvez exécuter cette applet de commande avec le paramètre GeneralizeOnly qui terminera les tâches à accomplir. </span><span class="sxs-lookup"><span data-stu-id="496b6-p103">If the conversion process fails during Windows update, you can try to configure a network/proxy and update Windows manually. After the manual work is done, you can run this cmdlet with the -GeneralizeOnly parameter and it will complete the remaining jobs.</span></span>  <br/> |
|<span data-ttu-id="496b6-121">PauseBeforeUpdate</span><span class="sxs-lookup"><span data-stu-id="496b6-121">PauseBeforeUpdate</span></span>  <br/> |<span data-ttu-id="496b6-122">Facultatif</span><span class="sxs-lookup"><span data-stu-id="496b6-122">Optional</span></span>  <br/> |<span data-ttu-id="496b6-123">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="496b6-123">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="496b6-p104">Pour mettre à jour Windows, certaines configurations manuelles réseau/proxy configuration peuvent être nécessaires sur les machines virtuelles de base. Le processus de conversion va être suspendu avant la mise à jour de Windows si ce paramètre est fourni. Après avoir effectué la configuration manuelle, vous pouvez reprendre le processus. </span><span class="sxs-lookup"><span data-stu-id="496b6-p104">To update Windows, some manual network/proxy configuration on the base VM might be necessary. The conversion process will pause before Windows update if this parameter is provided. After the manual configuration is done, you can resume the process.</span></span>  <br/> |
   
## <a name="examples"></a><span data-ttu-id="496b6-127">Exemples</span><span class="sxs-lookup"><span data-stu-id="496b6-127">Examples</span></span>
<span data-ttu-id="496b6-128"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="496b6-128"></span></span>

### <a name="example-1"></a><span data-ttu-id="496b6-129">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="496b6-129">Example 1</span></span>

<span data-ttu-id="496b6-130">L’exemple suivant prépare le fichier VHDX de base en utilisant un fichier ISO de Windows Server 2012 R2 situé dans "C:\Windows_Server_2012_R2-EN-US-x64.ISO": </span><span class="sxs-lookup"><span data-stu-id="496b6-130">The following example prepares the base VHDX file using a Windows Server 2012 R2 ISO file located at "C:\Windows_Server_2012_R2-EN-US-x64.ISO":</span></span> 
  
```
Convert-CcIsoToVhdx -IsoFilePath "C:\Windows_Server_2012_R2-EN-US-x64.ISO" 
```

### <a name="example-2"></a><span data-ttu-id="496b6-131">Exemple 2</span><span class="sxs-lookup"><span data-stu-id="496b6-131">Example 2</span></span>

<span data-ttu-id="496b6-132">En cas de défaillance de l’applet de commande Convert-CcIsoToVhdx au cours de la mise à jour de Windows, il est probablement dû à la configuration du réseau/proxy incorrect.</span><span class="sxs-lookup"><span data-stu-id="496b6-132">If the Convert-CcIsoToVhdx cmdlet fails during Windows update, it's probably because of incorrect network/proxy configuration.</span></span> <span data-ttu-id="496b6-133">Vous pouvez suivre les instructions dans le message d'erreur et vous connecter à la machine virtuelle de base pour corriger le problème et mettre à jour manuellement Windows.</span><span class="sxs-lookup"><span data-stu-id="496b6-133">You can follow the instructions in the error message and log on to the base virtual machine to fix the issue and update Windows manually.</span></span> <span data-ttu-id="496b6-134">Après avoir effectué les tâches manuelles, exécutez à nouveau l’applet de commande à l’aide du paramètre GeneralizeOnly afin de terminer les tâches à accomplir :</span><span class="sxs-lookup"><span data-stu-id="496b6-134">After the manual work is done, run the cmdlet again with the -GeneralizeOnly parameter to complete the remaining jobs:</span></span> 
  
```
Convert-CcIsoToVhdx -IsoFilePath "C:\Windows_Server_2012_R2-EN-US-x64.ISO" -GeneralizeOnly
```

### <a name="example-3"></a><span data-ttu-id="496b6-135">Exemple 3</span><span class="sxs-lookup"><span data-stu-id="496b6-135">Example 3</span></span>

<span data-ttu-id="496b6-136">Si la configuration manuelle est nécessaire pour mettre à jour Windows, vous pouvez utiliser le paramètre -PauseBeforeUpdate.</span><span class="sxs-lookup"><span data-stu-id="496b6-136">If manual configuration is necessary to update Windows, you can use the -PauseBeforeUpdate parameter.</span></span> <span data-ttu-id="496b6-137">Avec ce paramètre, le connecteur de nuage s’interrompt avant le processus de mise à jour de Windows.</span><span class="sxs-lookup"><span data-stu-id="496b6-137">With this parameter, Cloud Connector will pause before the Windows update process.</span></span> <span data-ttu-id="496b6-138">Vous pouvez ensuite terminer la configuration manuelle et achever le processus de conversion de la manière suivante :</span><span class="sxs-lookup"><span data-stu-id="496b6-138">You can then complete the manual configuration and resume the conversion process as follows:</span></span>
  
```
Convert-CcIsoToVhdx -IsoFilePath "C:\Windows_Server_2012_R2-EN-US-x64.ISO" -PauseBeforeUpdate 
```

## <a name="detailed-description"></a><span data-ttu-id="496b6-139">Description détaillée</span><span class="sxs-lookup"><span data-stu-id="496b6-139">Detailed Description</span></span>
<span data-ttu-id="496b6-140"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="496b6-140"></span></span>

<span data-ttu-id="496b6-141">L’applet de commande Convert-CcIsoToVhdx crée une base de que machine virtuelle installe tout d’abord, certains composants de base que connecteur de nuage dépend et puis installe les mises à jour Windows.</span><span class="sxs-lookup"><span data-stu-id="496b6-141">The Convert-CcIsoToVhdx cmdlet creates a base VM first, installs some basic components that Cloud Connector depends on, and then installs Windows updates.</span></span> <span data-ttu-id="496b6-142">Enfin, il généralise l’ordinateur virtuel (sysprep) pour obtenir un fichier VHDX de base qui sera utilisé par les ordinateurs virtuels d’un appareil de connecteur de nuage.</span><span class="sxs-lookup"><span data-stu-id="496b6-142">Finally, it generalizes the virtual machine (sysprep) to get a base VHDX file that will be used by the virtual machines of a Cloud Connector appliance.</span></span> 
  
## <a name="input-types"></a><span data-ttu-id="496b6-143">Types d’entrées</span><span class="sxs-lookup"><span data-stu-id="496b6-143">Input Types</span></span>
<span data-ttu-id="496b6-144"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="496b6-144"></span></span>

<span data-ttu-id="496b6-p108">Aucun. L’applet de commande Convert-CcIsoToVhdx n’accepte pas l’entrée redirigée.</span><span class="sxs-lookup"><span data-stu-id="496b6-p108">None. The Convert-CcIsoToVhdx cmdlet does not accept pipelined input.</span></span> 
  
## <a name="return-types"></a><span data-ttu-id="496b6-147">Types de retours</span><span class="sxs-lookup"><span data-stu-id="496b6-147">Return Types</span></span>
<span data-ttu-id="496b6-148"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="496b6-148"></span></span>

<span data-ttu-id="496b6-149">Aucun</span><span class="sxs-lookup"><span data-stu-id="496b6-149">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="496b6-150">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="496b6-150">See also</span></span>
<span data-ttu-id="496b6-151"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="496b6-151"></span></span>

<span data-ttu-id="496b6-152">Aucun</span><span class="sxs-lookup"><span data-stu-id="496b6-152">None</span></span>
  

