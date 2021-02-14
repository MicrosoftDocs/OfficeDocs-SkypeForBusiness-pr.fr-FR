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
description: LConvert-CcIsoToVhdx cmdlet crée un fichier de disque dur virtuel de base (VHDX) à l’aide d’un fichier ISO de Windows Server 2012 R2 fourni par le client. Le fichier VHDX sera utilisé lors du déploiement de Skype Entreprise, version Cloud Connector.
ms.openlocfilehash: f6b16c27b82919f24b9ee0e3094fb03fffa6443b
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802424"
---
# <a name="convert-ccisotovhdx"></a><span data-ttu-id="20588-104">Convert-CcIsoToVhdx</span><span class="sxs-lookup"><span data-stu-id="20588-104">Convert-CcIsoToVhdx</span></span>
 
<span data-ttu-id="20588-105">LConvert-CcIsoToVhdx cmdlet crée un fichier de disque dur virtuel de base (VHDX) à l’aide d’un fichier ISO de Windows Server 2012 R2 fourni par le client.</span><span class="sxs-lookup"><span data-stu-id="20588-105">The Convert-CcIsoToVhdx cmdlet creates a base virtual hard disk file (VHDX) using a customer supplied Windows Server 2012 R2 ISO file.</span></span> <span data-ttu-id="20588-106">Le fichier VHDX sera utilisé lors du déploiement de Skype Entreprise, version Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="20588-106">The VHDX file will be used during the deployment of Skype for Business Cloud Connector Edition.</span></span>
  
```powershell
Convert-CcIsoToVhdx [[-IsoFilePath] <string>] [-GeneralizeOnly] [-PauseBeforeUpdate]
```

## <a name="parameters"></a><span data-ttu-id="20588-107">Paramètres</span><span class="sxs-lookup"><span data-stu-id="20588-107">Parameters</span></span>

|<span data-ttu-id="20588-108">**Paramètre**</span><span class="sxs-lookup"><span data-stu-id="20588-108">**Parameter**</span></span>|<span data-ttu-id="20588-109">**Obligatoire**</span><span class="sxs-lookup"><span data-stu-id="20588-109">**Required**</span></span>|<span data-ttu-id="20588-110">**Type**</span><span class="sxs-lookup"><span data-stu-id="20588-110">**Type**</span></span>|<span data-ttu-id="20588-111">**Description**</span><span class="sxs-lookup"><span data-stu-id="20588-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="20588-112">IsoFilePath</span><span class="sxs-lookup"><span data-stu-id="20588-112">IsoFilePath</span></span>  <br/> | <span data-ttu-id="20588-113">Requis</span><span class="sxs-lookup"><span data-stu-id="20588-113">Required</span></span> <br/> |<span data-ttu-id="20588-114">System.String</span><span class="sxs-lookup"><span data-stu-id="20588-114">System.String</span></span>  <br/> | <span data-ttu-id="20588-115">Chemin d’accès au fichier ISO Windows Server 2012 R2.</span><span class="sxs-lookup"><span data-stu-id="20588-115">The path to the Windows Server 2012 R2 ISO file.</span></span> <br/> |
|<span data-ttu-id="20588-116">GeneralizeOnly</span><span class="sxs-lookup"><span data-stu-id="20588-116">GeneralizeOnly</span></span>  <br/> |<span data-ttu-id="20588-117">Facultatif</span><span class="sxs-lookup"><span data-stu-id="20588-117">Optional</span></span>  <br/> |<span data-ttu-id="20588-118">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="20588-118">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="20588-119">Si le processus de conversion échoue pendant la mise à jour de Windows, vous pouvez essayer de configurer un réseau/proxy et de mettre à jour Windows manuellement.</span><span class="sxs-lookup"><span data-stu-id="20588-119">If the conversion process fails during Windows update, you can try to configure a network/proxy and update Windows manually.</span></span> <span data-ttu-id="20588-120">Une fois le travail manuel terminé, vous pouvez exécuter cette cmdlet avec le paramètre -GeneralizeOnly et terminera les travaux restants.</span><span class="sxs-lookup"><span data-stu-id="20588-120">After the manual work is done, you can run this cmdlet with the -GeneralizeOnly parameter and it will complete the remaining jobs.</span></span>  <br/> |
|<span data-ttu-id="20588-121">PauseBeforeUpdate</span><span class="sxs-lookup"><span data-stu-id="20588-121">PauseBeforeUpdate</span></span>  <br/> |<span data-ttu-id="20588-122">Facultatif</span><span class="sxs-lookup"><span data-stu-id="20588-122">Optional</span></span>  <br/> |<span data-ttu-id="20588-123">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="20588-123">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="20588-124">Pour mettre à jour Windows, une configuration manuelle réseau/proxy sur l’ordinateur VM de base peut être nécessaire.</span><span class="sxs-lookup"><span data-stu-id="20588-124">To update Windows, some manual network/proxy configuration on the base VM might be necessary.</span></span> <span data-ttu-id="20588-125">Le processus de conversion sera suspendu avant la mise à jour de Windows si ce paramètre est fourni.</span><span class="sxs-lookup"><span data-stu-id="20588-125">The conversion process will pause before Windows update if this parameter is provided.</span></span> <span data-ttu-id="20588-126">Une fois la configuration manuelle effectuée, vous pouvez reprendre le processus.</span><span class="sxs-lookup"><span data-stu-id="20588-126">After the manual configuration is done, you can resume the process.</span></span>  <br/> |
   
## <a name="examples"></a><span data-ttu-id="20588-127">Exemples</span><span class="sxs-lookup"><span data-stu-id="20588-127">Examples</span></span>
<span data-ttu-id="20588-128"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="20588-128"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="20588-129">Exemple 1</span><span class="sxs-lookup"><span data-stu-id="20588-129">Example 1</span></span>

<span data-ttu-id="20588-130">L’exemple suivant prépare le fichier VHDX de base à l’aide d’un fichier ISO Windows Server 2012 R2 situé à l’emplacement « C:\Windows_Server_2012_R2-EN-US-x64.ISO » :</span><span class="sxs-lookup"><span data-stu-id="20588-130">The following example prepares the base VHDX file using a Windows Server 2012 R2 ISO file located at "C:\Windows_Server_2012_R2-EN-US-x64.ISO":</span></span> 
  
```powershell
Convert-CcIsoToVhdx -IsoFilePath "C:\Windows_Server_2012_R2-EN-US-x64.ISO" 
```

### <a name="example-2"></a><span data-ttu-id="20588-131">Exemple 2</span><span class="sxs-lookup"><span data-stu-id="20588-131">Example 2</span></span>

<span data-ttu-id="20588-132">Si l'Convert-CcIsoToVhdx cmdlet échoue pendant la mise à jour de Windows, c’est probablement en raison d’une configuration réseau/proxy incorrecte.</span><span class="sxs-lookup"><span data-stu-id="20588-132">If the Convert-CcIsoToVhdx cmdlet fails during Windows update, it's probably because of incorrect network/proxy configuration.</span></span> <span data-ttu-id="20588-133">Vous pouvez suivre les instructions du message d’erreur et vous connecter à la machine virtuelle de base pour résoudre le problème et mettre à jour Windows manuellement.</span><span class="sxs-lookup"><span data-stu-id="20588-133">You can follow the instructions in the error message and log on to the base virtual machine to fix the issue and update Windows manually.</span></span> <span data-ttu-id="20588-134">Une fois le travail manuel terminé, ré-exécutez l’cmdlet avec le paramètre -GeneralizeOnly pour terminer les travaux restants :</span><span class="sxs-lookup"><span data-stu-id="20588-134">After the manual work is done, run the cmdlet again with the -GeneralizeOnly parameter to complete the remaining jobs:</span></span> 
  
```powershell
Convert-CcIsoToVhdx -IsoFilePath "C:\Windows_Server_2012_R2-EN-US-x64.ISO" -GeneralizeOnly
```

### <a name="example-3"></a><span data-ttu-id="20588-135">Exemple 3</span><span class="sxs-lookup"><span data-stu-id="20588-135">Example 3</span></span>

<span data-ttu-id="20588-136">Si la configuration manuelle est nécessaire pour mettre à jour Windows, vous pouvez utiliser le paramètre -PauseBeforeUpdate.</span><span class="sxs-lookup"><span data-stu-id="20588-136">If manual configuration is necessary to update Windows, you can use the -PauseBeforeUpdate parameter.</span></span> <span data-ttu-id="20588-137">Avec ce paramètre, Cloud Connector sera suspendu avant le processus de mise à jour de Windows.</span><span class="sxs-lookup"><span data-stu-id="20588-137">With this parameter, Cloud Connector will pause before the Windows update process.</span></span> <span data-ttu-id="20588-138">Vous pouvez ensuite terminer la configuration manuelle et reprendre le processus de conversion comme suit :</span><span class="sxs-lookup"><span data-stu-id="20588-138">You can then complete the manual configuration and resume the conversion process as follows:</span></span>
  
```powershell
Convert-CcIsoToVhdx -IsoFilePath "C:\Windows_Server_2012_R2-EN-US-x64.ISO" -PauseBeforeUpdate 
```

## <a name="detailed-description"></a><span data-ttu-id="20588-139">Description détaillée</span><span class="sxs-lookup"><span data-stu-id="20588-139">Detailed Description</span></span>
<span data-ttu-id="20588-140"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="20588-140"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="20588-141">LConvert-CcIsoToVhdx cmdlet crée d’abord une VM de base, installe certains composants de base dont dépend Cloud Connector, puis installe les mises à jour Windows.</span><span class="sxs-lookup"><span data-stu-id="20588-141">The Convert-CcIsoToVhdx cmdlet creates a base VM first, installs some basic components that Cloud Connector depends on, and then installs Windows updates.</span></span> <span data-ttu-id="20588-142">Enfin, il généralise la machine virtuelle (sysprep) pour obtenir un fichier VHDX de base qui sera utilisé par les machines virtuelles d’une appliance Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="20588-142">Finally, it generalizes the virtual machine (sysprep) to get a base VHDX file that will be used by the virtual machines of a Cloud Connector appliance.</span></span> 
  
## <a name="input-types"></a><span data-ttu-id="20588-143">Types d’entrée</span><span class="sxs-lookup"><span data-stu-id="20588-143">Input Types</span></span>
<span data-ttu-id="20588-144"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="20588-144"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="20588-145">Aucun.</span><span class="sxs-lookup"><span data-stu-id="20588-145">None.</span></span> <span data-ttu-id="20588-146">La cmdlet Convert-CcIsoToVhdx n’accepte pas la saisie de données pipeline.</span><span class="sxs-lookup"><span data-stu-id="20588-146">The Convert-CcIsoToVhdx cmdlet does not accept pipelined input.</span></span> 
  
## <a name="return-types"></a><span data-ttu-id="20588-147">Types de retour</span><span class="sxs-lookup"><span data-stu-id="20588-147">Return Types</span></span>
<span data-ttu-id="20588-148"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="20588-148"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="20588-149">Aucun</span><span class="sxs-lookup"><span data-stu-id="20588-149">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="20588-150">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="20588-150">See also</span></span>
<span data-ttu-id="20588-151"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="20588-151"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="20588-152">Aucun</span><span class="sxs-lookup"><span data-stu-id="20588-152">None</span></span>
  

