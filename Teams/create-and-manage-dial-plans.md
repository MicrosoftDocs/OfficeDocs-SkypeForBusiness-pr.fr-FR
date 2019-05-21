---
title: Créer et gérer les plans de numérotation
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 7af17c94-5f8f-4452-ae1d-01f495b4dc94
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
description: 'Découvrez comment créer des plans de numérotation téléphonique (appels RTC) dans Office 365 et comment les gérer. '
ms.openlocfilehash: 10a05c9d4c16f7c5681f0c7c6fcc931e041426f3
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34281831"
---
# <a name="create-and-manage-dial-plans"></a><span data-ttu-id="96d62-103">Créer et gérer les plans de numérotation</span><span class="sxs-lookup"><span data-stu-id="96d62-103">Create and manage dial plans</span></span>

<span data-ttu-id="96d62-104">Une fois que vous avez planifié le plan de numérotation pour votre organisation et que vous avez effectué toutes les règles de normalisation qui doivent être créées pour le routage des appels, vous devez utiliser Windows PowerShell pour créer les plans de numérotation et apporter des modifications de paramètres.</span><span class="sxs-lookup"><span data-stu-id="96d62-104">After you have planned the dial plans for your organization and figured out all of the normalization rules that need to be created for call routing, you will need to use Windows PowerShell to create the dial plans and make any setting changes.</span></span>
  
> [!NOTE]
> <span data-ttu-id="96d62-105">Le centre d’administration Skype entreprise ne peut pas être utilisé pour créer et gérer les plans de numérotation.</span><span class="sxs-lookup"><span data-stu-id="96d62-105">The Skype for Business admin center can't be used for creating and managing dial plans.</span></span> 
  
## <a name="verifying-and-starting-remote-powershell"></a><span data-ttu-id="96d62-106">Vérification et démarrage de la session PowerShell distante</span><span class="sxs-lookup"><span data-stu-id="96d62-106">Verifying and starting Remote PowerShell</span></span>

 <span data-ttu-id="96d62-107">**Vérifiez que vous exécutez la version 3.0 ou une version ultérieure de Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="96d62-107">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
  
1. <span data-ttu-id="96d62-108">Pour vérifier que vous exécutez la version 3.0 ou une version ultérieure : **Menu Démarrer** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="96d62-108">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="96d62-109">Consultez la version en entrant  _Get-Host_ dans la fenêtre **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="96d62-109">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="96d62-p101">Si vous n'utilisez pas la version 3.0 ou une version ultérieure, vous devez télécharger et installer les mises à jour de Windows PowerShell. Pour télécharger et mettre à jour Windows PowerShell vers la version 4.0, consultez [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845). Redémarrez votre ordinateur lorsque vous y êtes invité.</span><span class="sxs-lookup"><span data-stu-id="96d62-p101">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell. See [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0. Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="96d62-p102">Vous devrez également installer le module Windows PowerShell pour Skype Entreprise Online qui vous permet de créer une session Windows PowerShell distante qui se connecte à Skype Entreprise Online. Ce module, pris en charge uniquement sur les ordinateurs 64 bits, peut être téléchargé sur le centre de téléchargement de Microsoft à la page [Module Windows PowerShell pour Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=294688). Redémarrez votre ordinateur si vous y êtes invité.</span><span class="sxs-lookup"><span data-stu-id="96d62-p102">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
<span data-ttu-id="96d62-116">Pour en savoir plus, voir [Se connecter à tous les services Office 365 dans une fenêtre Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span><span class="sxs-lookup"><span data-stu-id="96d62-116">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span></span>
  
 <span data-ttu-id="96d62-117">**Démarrez une session Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="96d62-117">**Start a Windows PowerShell session**</span></span>
  
1. <span data-ttu-id="96d62-118">From the **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="96d62-118">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="96d62-119">Dans la fenêtre **Windows PowerShell**, connectez-vous à votre organisation Office 365 en exécutant :</span><span class="sxs-lookup"><span data-stu-id="96d62-119">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="96d62-120">Vous devez seulement exécuter la commande **Import-Module** la première fois que vous utilisez le module Windows PowerShell pour Skype Entreprise Online.</span><span class="sxs-lookup"><span data-stu-id="96d62-120">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>
  
> 
>   ```
>     Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
>     $credential = Get-Credential
>     $session = New-CsOnlineSession -Credential $credential
>     Import-PSSession $session
>   ```

<span data-ttu-id="96d62-121">Pour plus d’informations sur le démarrage de Windows PowerShell, voir [se connecter à tous les services Office 365 dans une seule fenêtre Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx) ou [à vous connecter à Skype entreprise Online à l’aide de Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="96d62-121">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx) or [Connecting to Skype for Business Online by using Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span></span>
  
## <a name="creating-and-managing-your-dial-plans"></a><span data-ttu-id="96d62-122">Création et gestion de vos plans de numérotation</span><span class="sxs-lookup"><span data-stu-id="96d62-122">Creating and managing your dial plans</span></span>

<span data-ttu-id="96d62-123">Vous pouvez utiliser une cmdlet unique ou un script PowerShell pour créer et gérer les plans de numérotation client.</span><span class="sxs-lookup"><span data-stu-id="96d62-123">You can either use a single cmdlet or a PowerShell script to create and manage tenant dial plans.</span></span>
  
### <a name="using-single-cmdlets"></a><span data-ttu-id="96d62-124">Utilisation d’applets de applet uniques</span><span class="sxs-lookup"><span data-stu-id="96d62-124">Using single cmdlets</span></span>

- <span data-ttu-id="96d62-125">Pour créer un plan de numérotation, exécutez:</span><span class="sxs-lookup"><span data-stu-id="96d62-125">To create a new dial plan, run:</span></span>
    
  ```
  New-CsTenantDialPlan -Identity RedmondDialPlan -Description "Dial Plan for Redmond" -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9 -SimpleName "Dial-Plan-for-Redmond"
  ```

    <span data-ttu-id="96d62-126">Pour obtenir d’autres exemples et des paramètres, consultez la rubrique [New-rubrique Remove](https://technet.microsoft.com/library/mt775026.aspx).</span><span class="sxs-lookup"><span data-stu-id="96d62-126">For other examples and parameters, see [New-CsTenantDialPlan](https://technet.microsoft.com/library/mt775026.aspx).</span></span>
    
- <span data-ttu-id="96d62-127">Pour modifier les paramètres d’un plan de numérotation existant, exécutez:</span><span class="sxs-lookup"><span data-stu-id="96d62-127">To make setting changes to an existing dial plan, run:</span></span>
    
  ```
  Set-CsTenantDialPlan -Identity RedmondDialPlan  -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9
    -SimpleName "Dial-Plan-for-Redmond"
  ```

    <span data-ttu-id="96d62-128">Pour obtenir d’autres exemples et des paramètres, consultez la rubrique [Set-rubrique Remove](https://technet.microsoft.com/library/mt775023.aspx).</span><span class="sxs-lookup"><span data-stu-id="96d62-128">For other examples and parameters, see [Set-CsTenantDialPlan](https://technet.microsoft.com/library/mt775023.aspx).</span></span>
    
- <span data-ttu-id="96d62-129">Pour ajouter des utilisateurs à un plan de numérotation, exécutez:</span><span class="sxs-lookup"><span data-stu-id="96d62-129">To add users to a dial plan, run:</span></span>
    
  ```
  Grant-CsTenantDialPlan -Identity amos.marble@contoso.com -PolicyName RedmondDialPlan
  ```

    <span data-ttu-id="96d62-130">Pour obtenir d’autres exemples et des paramètres, consultez la rubrique [Grant-rubrique Remove](https://technet.microsoft.com/library/mt775021.aspx).</span><span class="sxs-lookup"><span data-stu-id="96d62-130">For other examples and parameters, see [Grant-CsTenantDialPlan](https://technet.microsoft.com/library/mt775021.aspx).</span></span>
    
- <span data-ttu-id="96d62-131">Pour afficher les paramètres d’un plan de numérotation, exécutez:</span><span class="sxs-lookup"><span data-stu-id="96d62-131">To view the settings on a dial plan, run:</span></span>
    
  ```
  Get-CsTenantDialPlan -Identity RedmondDialPlan
  ```

    <span data-ttu-id="96d62-132">Pour obtenir d’autres exemples et des paramètres, consultez la rubrique [Get-rubrique Remove](https://technet.microsoft.com/library/mt775024.aspx).</span><span class="sxs-lookup"><span data-stu-id="96d62-132">For other examples and parameters, see [Get-CsTenantDialPlan](https://technet.microsoft.com/library/mt775024.aspx).</span></span>
    
- <span data-ttu-id="96d62-133">Pour supprimer un plan de numérotation, exécutez:</span><span class="sxs-lookup"><span data-stu-id="96d62-133">To delete a dial plan, run:</span></span>
    
  ```
  Remove-CsTenantDialPlan -Identity RedmondDialPlan -force
  ```

    <span data-ttu-id="96d62-134">Pour obtenir d’autres exemples et des paramètres, consultez la rubrique [Remove-rubrique Remove](https://technet.microsoft.com/library/mt775020.aspx).</span><span class="sxs-lookup"><span data-stu-id="96d62-134">For other examples and parameters, see [Remove-CsTenantDialPlan](https://technet.microsoft.com/library/mt775020.aspx).</span></span>
    
- <span data-ttu-id="96d62-135">Pour afficher les paramètres du plan de numérotation efficace, exécutez:</span><span class="sxs-lookup"><span data-stu-id="96d62-135">To see the settings of the effective dial plan, run:</span></span>
    
  ```
  Get-CsEffectiveTenantDialPlan -Identity amos.marble@contoso.com
  ```

    <span data-ttu-id="96d62-136">Pour obtenir d’autres exemples et des paramètres, consultez la rubrique [Get-CsEffectiveTenantDialPlan](https://technet.microsoft.com/library/mt775022.aspx).</span><span class="sxs-lookup"><span data-stu-id="96d62-136">For other examples and parameters, see [Get-CsEffectiveTenantDialPlan](https://technet.microsoft.com/library/mt775022.aspx).</span></span>
    
- <span data-ttu-id="96d62-137">Pour tester les paramètres efficaces d’un plan de numérotation, exécutez:</span><span class="sxs-lookup"><span data-stu-id="96d62-137">To test the effective settings of a dial plan, run:</span></span>
    
  ```
  Test-CsEffectiveTenantDialPlan -DialedNumber 14255551234 -Identity 1849827b-a810-40a8-8f77-e94250d4680b_US_TenantDialPlanRedmond
  ```

    <span data-ttu-id="96d62-138">Pour obtenir d’autres exemples et des paramètres, consultez la rubrique [test-CsEffectiveTenantDialPlan](https://technet.microsoft.com/library/mt775025.aspx).</span><span class="sxs-lookup"><span data-stu-id="96d62-138">For other examples and parameters, see [Test-CsEffectiveTenantDialPlan](https://technet.microsoft.com/library/mt775025.aspx).</span></span>
    
### <a name="using-a-powershell-script"></a><span data-ttu-id="96d62-139">Utilisation d’un script PowerShell</span><span class="sxs-lookup"><span data-stu-id="96d62-139">Using a PowerShell script</span></span>

<span data-ttu-id="96d62-140">Exécutez l’opération suivante pour supprimer une règle de normalisation associée à un plan de numérotation client sans avoir à supprimer d’abord le plan de numérotation client:</span><span class="sxs-lookup"><span data-stu-id="96d62-140">Run this to delete a normalization rule that is associated with a tenant dial plan without needing to deleting the tenant dial plan first:</span></span>
```
$b1=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$b1}
(Get-CsTenantDialPlan -Identity RedmondDialPlan).NormalizationRules
$b2=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$b2}
```
<span data-ttu-id="96d62-141">Exécutez l’outil pour ajouter la règle de normalisation suivante au plan de numérotation client existant nommé RedmondDialPlan.</span><span class="sxs-lookup"><span data-stu-id="96d62-141">Run this to add the following normalization rule to the existing tenant dial plan named RedmondDialPlan.</span></span>
```
$nr1=New-CsVoiceNormalizationRule -Parent Global -Description 'Organization extension dialing' -Pattern '^(\\d{3})$' -Translation '+14255551$1' -Name NR1 -IsInternalExtension $false -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$nr1}
```
<span data-ttu-id="96d62-142">Exécutez cette commande pour supprimer la règle de normalisation suivante du plan de numérotation client existant nommé RedmondDialPlan.</span><span class="sxs-lookup"><span data-stu-id="96d62-142">Run this to remove the following normalization rule from the existing tenant dial plan named RedmondDialPlan.</span></span>
```
$nr1=New-CsVoiceNormalizationRule -Parent Global/NR1 -InMemory
Set-CsTenantDialPlan -Identity DP1 -NormalizationRules @{remove=$nr1}
```

<span data-ttu-id="96d62-143">Exécutez la commande suivante lorsque vous voulez également examiner les règles de normalisation existantes, déterminer celle que vous voulez supprimer, puis utiliser son index pour la supprimer.</span><span class="sxs-lookup"><span data-stu-id="96d62-143">Run the following when you want to also examine the existing normalization rules, determine which one you want to delete, and then use its index to remove it.</span></span> <span data-ttu-id="96d62-144">Le tableau de règles de normalisation commence par l’index 0.</span><span class="sxs-lookup"><span data-stu-id="96d62-144">The array of normalization rules starts with index 0.</span></span> <span data-ttu-id="96d62-145">Nous voulons supprimer la règle de normalisation à 3 chiffres, afin qu’il s’agit de l’index 1.</span><span class="sxs-lookup"><span data-stu-id="96d62-145">We would like to remove the 3-digit normalization rule, so that is index 1.</span></span>
  
```
Get-CsTenantDialPlan RedmondDialPlan).NormalizationRules
Description         : 4-digit
Pattern             : ^(\\d{4})$
Translation         : +1426666$1
Name                : NR2
IsInternalExtension : False

Description         : 3-digit
Pattern             : ^(\\d{3})$
Translation         : +14255551$1
Name                : NR12
IsInternalExtension : False

$nr1=(Get-CsTenantDialPlan RedmondDialPlan).NormalizationRules[Number 1]
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$nr1}
```

<span data-ttu-id="96d62-146">Exécutez l’outil pour rechercher tous les utilisateurs disposant d’un plan de numérotation client RedmondDialPlan.</span><span class="sxs-lookup"><span data-stu-id="96d62-146">Run this to find all users who have been granted the RedmondDialPlan tenant dial plan.</span></span>
  
```
Get-CsOnlineuser | where-Object {$_.TenantDialPlan -eq "RedmondDialPlan"}
```

<span data-ttu-id="96d62-147">Exécutez cette opération pour supprimer PolicyName pour tous les utilisateurs qui disposent de HostingProvider sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="96d62-147">Run this to delete policyname for all users who have HostingProvider sipfed.online.lync.com.</span></span>
```
Get-CsOnlineUser -Filter {HostingProvider -eq “sipfed.online.lync.com”} | Grant-CsTenantDialPlan -policyname $null
```

<span data-ttu-id="96d62-148">Exécutez ces derniers pour ajouter le plan de numérotation local existant intitulé OPDP1 comme plan de numérotation client pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="96d62-148">Run these to add the existing on-premises dial plan named OPDP1 as a tenant dial plan for your organization.</span></span> <span data-ttu-id="96d62-149">Vous devez d’abord enregistrer le plan de numérotation local dans un fichier. xml, puis l’utiliser pour créer le plan de numérotation client.</span><span class="sxs-lookup"><span data-stu-id="96d62-149">You need to first save the on-premises dial plan to an .xml file, and then use it to create the new tenant dial plan.</span></span>
  
<span data-ttu-id="96d62-150">Exécutez cet enregistrement pour enregistrer le plan de numérotation local au fichier. Xml.</span><span class="sxs-lookup"><span data-stu-id="96d62-150">Run this to save the on-premises dial plan to the .xml file.</span></span>
  
```
$DPName = "OPDP1"
$DPFileName = "dialplan.xml"
Get-CsDialplan $DPName | Export-Clixml $DPFileName
```

<span data-ttu-id="96d62-151">Exécutez cette opération pour créer le plan de numérotation client.</span><span class="sxs-lookup"><span data-stu-id="96d62-151">Run this to create the new tenant dial plan.</span></span>
  
```
$DPFileName = "dialplan.xml"
$DP = Import-Clixml $DPFileName
$NormRules = @()
ForEach($nr in $dp.NormalizationRules)
{
 $id1 = "Global/" +$nr.Name
$nr2 = New-CsVoiceNormalizationRule -Identity $id1 -Description $nr.Description -Pattern $nr.Pattern -Translation $nr.Translation  -IsInternalExtension $nr.IsInternalExtension -InMemory
$NormRules += $nr2
}
New-CsTenantDialPlan -Identity $dp.SimpleName -ExternalAccessPrefix $dp.ExternalAccessPrefix -Description $dp.Description -OptimizeDeviceDialing $dp.OptimizeDeviceDialing -SimpleName $dp.SimpleName -NormalizationRules $NormRules
```
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="96d62-152">Vous voulez en savoir plus sur Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="96d62-152">Want to know more about Windows Powershell?</span></span>

- <span data-ttu-id="96d62-153">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer.</span><span class="sxs-lookup"><span data-stu-id="96d62-153">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="96d62-154">Avec Windows PowerShell, vous pouvez gérer Office 365 et Skype Entreprise Online à l'aide d'un point d'administration central qui peut simplifier votre travail quotidien, lorsque vous devez effectuer plusieurs tâches.</span><span class="sxs-lookup"><span data-stu-id="96d62-154">With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="96d62-155">Pour prendre en main Windows PowerShell, consultez ces rubriques :</span><span class="sxs-lookup"><span data-stu-id="96d62-155">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="96d62-156">Présentation de Windows PowerShell et Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="96d62-156">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="96d62-157">Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="96d62-157">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="96d62-158">Windows PowerShell dispose de nombreux avantages de la vitesse, de la simplicité et de la productivité par le biais du centre d’administration Microsoft 365, par exemple, lorsque vous apportez des modifications à un grand nombre d’utilisateurs à la fois.</span><span class="sxs-lookup"><span data-stu-id="96d62-158">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="96d62-159">Découvrez ces avantages dans les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="96d62-159">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="96d62-160">Meilleures méthodes de gestion d'Office 365 avec Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="96d62-160">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="96d62-161">Utilisation de Windows PowerShell pour gérer Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="96d62-161">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="96d62-162">Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="96d62-162">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="96d62-163">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="96d62-163">Related topics</span></span>
[<span data-ttu-id="96d62-164">Questions fréquentes à propos du transfert de numéros de téléphone</span><span class="sxs-lookup"><span data-stu-id="96d62-164">Transferring phone numbers common questions</span></span>](transferring-phone-numbers-common-questions.md)

[<span data-ttu-id="96d62-165">Différents types de numéros de téléphone utilisés pour les offres d'appel</span><span class="sxs-lookup"><span data-stu-id="96d62-165">Different kinds of phone numbers used for Calling Plans</span></span>](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[<span data-ttu-id="96d62-166">Gérer des numéros de téléphone pour votre entreprise</span><span class="sxs-lookup"><span data-stu-id="96d62-166">Manage phone numbers for your organization</span></span>](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[<span data-ttu-id="96d62-167">Conditions générales relatives aux appels d'urgence</span><span class="sxs-lookup"><span data-stu-id="96d62-167">Emergency calling terms and conditions</span></span>](emergency-calling-terms-and-conditions.md)

<span data-ttu-id="96d62-168">[Skype Entreprise Online : étiquette d'exclusion de responsabilité pour les appels d'urgence](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="96d62-168">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
 
