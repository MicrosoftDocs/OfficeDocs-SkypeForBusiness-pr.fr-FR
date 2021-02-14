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
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
- seo-marvel-apr2020
description: Découvrez comment utiliser le Centre d’administration de Microsoft Teams ou Windows PowerShell pour créer et gérer des plans de numérotation (plans de numérotation PSTN).
ms.openlocfilehash: 0655f81df9c8ce25368a281a7f5b3392f7fe6ec3
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814783"
---
# <a name="create-and-manage-dial-plans"></a><span data-ttu-id="30345-103">Créer et gérer les plans de numérotation</span><span class="sxs-lookup"><span data-stu-id="30345-103">Create and manage dial plans</span></span>

<span data-ttu-id="30345-104">Après avoir plané les plans de numérotation de votre organisation et compris toutes les règles de normalisation à créer pour le routage des appels, vous êtes prêt à créer les plans de numérotation.</span><span class="sxs-lookup"><span data-stu-id="30345-104">After you plan the dial plans for your organization and figured out all the normalization rules that need to be created for call routing, you're ready to create the dial plans.</span></span> <span data-ttu-id="30345-105">Vous pouvez utiliser le Centre d’administration de Microsoft Teams ou Windows PowerShell pour créer et gérer des plans de numérotation.</span><span class="sxs-lookup"><span data-stu-id="30345-105">You can use the Microsoft Teams admin center or Windows PowerShell to create and manage dial plans.</span></span>  

## <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="30345-106">Utiliser le centre d’administration Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="30345-106">Using the Microsoft Teams admin center</span></span>

### <a name="create-a-dial-plan"></a><span data-ttu-id="30345-107">Créer un plan de numérotation</span><span class="sxs-lookup"><span data-stu-id="30345-107">Create a dial plan</span></span>

1. <span data-ttu-id="30345-108">Dans le navigation gauche du Centre d’administration Microsoft Teams, allez au   >  **plan de numérotation vocale.**</span><span class="sxs-lookup"><span data-stu-id="30345-108">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Dial plan**.</span></span>
2. <span data-ttu-id="30345-109">Cliquez **sur** Ajouter, puis entrez un nom et une description pour le plan de numérotation.</span><span class="sxs-lookup"><span data-stu-id="30345-109">Click **Add**, and then enter a name and description for the dial plan.</span></span>
    <span data-ttu-id="30345-110">![Capture d’écran montrant la page Ajouter pour la création d’un plan de numérotation](media/create-dial-plan.png)</span><span class="sxs-lookup"><span data-stu-id="30345-110">![Screenshot showing the Add page for creating a dial plan](media/create-dial-plan.png)</span></span>
3. <span data-ttu-id="30345-111">Sous les **détails** du plan de numérotation, spécifiez un préfixe de numérotation externe si les utilisateurs doivent composer un ou plusieurs chiffres de tête supplémentaires (par exemple, 9) pour obtenir une ligne externe.</span><span class="sxs-lookup"><span data-stu-id="30345-111">Under **Dial plan details**, specify an external dialing prefix if users need to dial one or more additional leading digits (for example, 9) to get an external line.</span></span> <span data-ttu-id="30345-112">Pour ce faire :</span><span class="sxs-lookup"><span data-stu-id="30345-112">To do this:</span></span>
    1. <span data-ttu-id="30345-113">Dans la **zone du préfixe de numérotation** externe, entrez un préfixe de numérotation externe.</span><span class="sxs-lookup"><span data-stu-id="30345-113">In the **External dialing prefix** box, enter an external dialing prefix.</span></span> <span data-ttu-id="30345-114">Le préfixe peut prendre jusqu’à quatre caractères (#,\*, et 0-9).</span><span class="sxs-lookup"><span data-stu-id="30345-114">The prefix can be up to four characters (#,\*, and 0-9).</span></span>
    2. <span data-ttu-id="30345-115">Activer la **numérotation optimisée des appareils.**</span><span class="sxs-lookup"><span data-stu-id="30345-115">Turn on **Optimized device dialing**.</span></span> <span data-ttu-id="30345-116">Si vous spécifiez un préfixe de numérotation externe, vous devez également activer ce paramètre pour appliquer le préfixe afin que les appels soient effectués à l’extérieur de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="30345-116">If you specify an external dialing prefix, you must also turn on this setting to apply the prefix so calls can be made outside your organization.</span></span>
4. <span data-ttu-id="30345-117">Dans le **cadre des règles de normalisation,** configurez et associez une ou plusieurs règles de [normalisation](what-are-dial-plans.md#normalization-rules) pour le plan de numérotation.</span><span class="sxs-lookup"><span data-stu-id="30345-117">Under **Normalization rules**, configure and associate one or more [normalization rules](what-are-dial-plans.md#normalization-rules) for the dial plan.</span></span> <span data-ttu-id="30345-118">Chaque plan de numérotation doit être associé à au moins une règle de normalisation.</span><span class="sxs-lookup"><span data-stu-id="30345-118">Each dial plan must have at least one normalization rule associated with it.</span></span>  <span data-ttu-id="30345-119">Pour ce faire, vous pouvez :</span><span class="sxs-lookup"><span data-stu-id="30345-119">To do this, do one or more of the following:</span></span>
    - <span data-ttu-id="30345-120">Pour créer une règle de normalisation et l’associer au plan de numérotation, cliquez sur **Ajouter,** puis définissez la règle.</span><span class="sxs-lookup"><span data-stu-id="30345-120">To create a new normalization rule and associate it with the dial plan, click **Add**, and then define the rule.</span></span>
    - <span data-ttu-id="30345-121">Pour modifier une règle de normalisation déjà associée au plan de numérotation, sélectionnez-la en cliquant à gauche du nom de la règle, puis cliquez sur **Modifier.**</span><span class="sxs-lookup"><span data-stu-id="30345-121">To edit a normalization rule that's already associated with the dial plan, select the rule by clicking to the left of the rule name, and then click **Edit**.</span></span> <span data-ttu-id="30345-122">A apporter les modifications de votre souhaitez, puis cliquez sur **Enregistrer.**</span><span class="sxs-lookup"><span data-stu-id="30345-122">Make the changes you want, and then click **Save**.</span></span>
    - <span data-ttu-id="30345-123">Pour supprimer une règle de normalisation du plan de numérotation, sélectionnez-la en cliquant à gauche du nom de la règle, puis cliquez sur **Supprimer.**</span><span class="sxs-lookup"><span data-stu-id="30345-123">To remove a normalization rule from the dial plan, select the rule by clicking to the left of the rule name, and then click **Remove**.</span></span>
5. <span data-ttu-id="30345-124">Organisez les règles de normalisation dans l’ordre voulu.</span><span class="sxs-lookup"><span data-stu-id="30345-124">Arrange the normalization rules in the order that you want.</span></span> <span data-ttu-id="30345-125">Cliquez **sur Monter** ou **Descendre** pour modifier la position des règles dans la liste.</span><span class="sxs-lookup"><span data-stu-id="30345-125">Click **Move up** or **Move down** to change the position of rules in the list.</span></span>

    > [!NOTE]
    > <span data-ttu-id="30345-126">Teams traverse la liste des règles de normalisation du haut vers le bas et utilise la première règle qui correspond au numéro composé.</span><span class="sxs-lookup"><span data-stu-id="30345-126">Teams traverses the list of normalization rules from the top down and uses the first rule that matches the dialed number.</span></span> <span data-ttu-id="30345-127">Si vous avez installé un plan de numérotation de sorte qu’un numéro composé corresponde à plusieurs règles de normalisation, veillez à ce que les règles plus restrictives soient triées au-dessus des règles moins restrictives.</span><span class="sxs-lookup"><span data-stu-id="30345-127">If you set up a dial plan so that a dialed number can match more than one normalization rule, make sure the more restrictive rules are sorted above the less restrictive ones.</span></span>

6. <span data-ttu-id="30345-128">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="30345-128">Click **Save**.</span></span>
7. <span data-ttu-id="30345-129">Si vous voulez tester le plan de numérotation, sous Tester le **plan** de numérotation, entrez un numéro de téléphone, puis cliquez sur **Test.**</span><span class="sxs-lookup"><span data-stu-id="30345-129">If you want to test the dial plan, under **Test dial plan**, enter a phone number, and then click **Test**.</span></span>

### <a name="edit-a-dial-plan"></a><span data-ttu-id="30345-130">Modifier un plan de numérotation</span><span class="sxs-lookup"><span data-stu-id="30345-130">Edit a dial plan</span></span>

1. <span data-ttu-id="30345-131">Dans le navigation gauche du Centre d’administration Microsoft Teams, allez au   >  **plan de numérotation vocale.**</span><span class="sxs-lookup"><span data-stu-id="30345-131">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Dial plan**.</span></span>
2. <span data-ttu-id="30345-132">Sélectionnez le plan de numérotation en cliquant à gauche du nom du plan de numérotation, puis cliquez sur **Modifier.**</span><span class="sxs-lookup"><span data-stu-id="30345-132">Select the dial plan by clicking to the left of the dial plan name, and then click **Edit**.</span></span>
3. <span data-ttu-id="30345-133">A apporter les modifications de votre souhaitez, puis cliquez sur **Enregistrer.**</span><span class="sxs-lookup"><span data-stu-id="30345-133">Make the changes that you want, and then click **Save**.</span></span>

### <a name="assign-a-dial-plan-to-users"></a><span data-ttu-id="30345-134">Affecter un plan de numérotation aux utilisateurs</span><span class="sxs-lookup"><span data-stu-id="30345-134">Assign a dial plan to users</span></span>

<span data-ttu-id="30345-135">Vous attribuez un plan de numérotation de la même façon que vous attribuez des stratégies.</span><span class="sxs-lookup"><span data-stu-id="30345-135">You assign a dial plan in the same way you assign policies.</span></span> [!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="using-powershell"></a><span data-ttu-id="30345-136">Utiliser PowerShell</span><span class="sxs-lookup"><span data-stu-id="30345-136">Using PowerShell</span></span>
  
### <a name="verify-and-start-remote-powershell"></a><span data-ttu-id="30345-137">Vérifier et démarrer Remote PowerShell</span><span class="sxs-lookup"><span data-stu-id="30345-137">Verify and start Remote PowerShell</span></span>

 <span data-ttu-id="30345-138">**Vérifier que vous exécutez Windows PowerShell version 3.0 ou ultérieure**</span><span class="sxs-lookup"><span data-stu-id="30345-138">**Check that you are running Windows PowerShell version 3.0 or later**</span></span>
  
1. <span data-ttu-id="30345-139">Pour vérifier que vous exécutez la version 3.0 ou une version supérieure : démarrer **le menu**  >  **Windows PowerShell.**</span><span class="sxs-lookup"><span data-stu-id="30345-139">To verify that you're running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="30345-140">Consultez la version en entrant  _Get-Host_ dans la fenêtre **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="30345-140">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="30345-141">Si vous n’avez pas la version 3.0 ou une version ultérieure, téléchargez et installez les mises à jour Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="30345-141">If you don't have version 3.0 or later, download and install updates to Windows PowerShell.</span></span> <span data-ttu-id="30345-142">Voir [Windows Management Framework 4.0 pour](https://go.microsoft.com/fwlink/?LinkId=716845) télécharger et mettre à Windows PowerShell jour vers la version 4.0.</span><span class="sxs-lookup"><span data-stu-id="30345-142">See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0.</span></span> <span data-ttu-id="30345-143">Redémarrez votre ordinateur lorsque vous y êtes invité.</span><span class="sxs-lookup"><span data-stu-id="30345-143">Restart your computer when you're prompted.</span></span>
    
4. <span data-ttu-id="30345-144">Vous devrez également installer le module Windows PowerShell pour Skype Entreprise Online qui vous permet de créer une session de Windows PowerShell distante qui se connecte à Skype Entreprise Online.</span><span class="sxs-lookup"><span data-stu-id="30345-144">You'll also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> <span data-ttu-id="30345-145">Vous pouvez télécharger ce module, qui est pris en charge uniquement sur les ordinateurs 64 bits, dans [le module Windows PowerShell pour Skype Entreprise Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span><span class="sxs-lookup"><span data-stu-id="30345-145">You can download this module, which is supported only on 64-bit computers, at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span></span> <span data-ttu-id="30345-146">Redémarrez votre ordinateur si vous y êtes invité.</span><span class="sxs-lookup"><span data-stu-id="30345-146">Restart your computer if you're prompted.</span></span>
    
<span data-ttu-id="30345-147">Pour en savoir plus, voir Se connecter à tous les [services Microsoft 365 ou Office 365](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window)dans une seule Windows PowerShell service.</span><span class="sxs-lookup"><span data-stu-id="30345-147">To learn more, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span>
  
 <span data-ttu-id="30345-148">**Démarrez une session Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="30345-148">**Start a Windows PowerShell session**</span></span>
  
1. <span data-ttu-id="30345-149">Cliquez **sur Démarrer**  >  **Windows PowerShell.**</span><span class="sxs-lookup"><span data-stu-id="30345-149">Click **Start** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="30345-150">Dans la **Windows PowerShell,** connectez-vous à Microsoft 365 ou Office 365 en exécutant :</span><span class="sxs-lookup"><span data-stu-id="30345-150">In the **Windows PowerShell** window, connect to Microsoft 365 or Office 365 by running:</span></span>
    
 
    > [!NOTE]
    > <span data-ttu-id="30345-151">Skype Entreprise Online Connector fait actuellement partie du module Teams PowerShell le plus récent.</span><span class="sxs-lookup"><span data-stu-id="30345-151">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
    >
    > <span data-ttu-id="30345-152">Si vous utilisez la dernière version publique [de Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)vous n’avez pas besoin d’installer Skype Entreprise Online Connector.</span><span class="sxs-lookup"><span data-stu-id="30345-152">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

    ```PowerShell
   Import-Module -Name MicrosoftTeams
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
    ```
  
### <a name="create-and-manage-your-dial-plans"></a><span data-ttu-id="30345-153">Créer et gérer vos plans de numérotation</span><span class="sxs-lookup"><span data-stu-id="30345-153">Create and manage your dial plans</span></span>

<span data-ttu-id="30345-154">Vous pouvez utiliser une seule cmdlet ou un script PowerShell pour créer et gérer des plans de numérotation client.</span><span class="sxs-lookup"><span data-stu-id="30345-154">You can either use a single cmdlet or a PowerShell script to create and manage tenant dial plans.</span></span>
  
#### <a name="using-single-cmdlets"></a><span data-ttu-id="30345-155">Utilisation d’une seule cmdlets</span><span class="sxs-lookup"><span data-stu-id="30345-155">Using single cmdlets</span></span>

- <span data-ttu-id="30345-156">Pour créer un plan de numérotation, exécutez :</span><span class="sxs-lookup"><span data-stu-id="30345-156">To create a new dial plan, run:</span></span>
    
  ```PowerShell
  New-CsTenantDialPlan -Identity RedmondDialPlan -Description "Dial Plan for Redmond" -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9 -SimpleName "Dial-Plan-for-Redmond"
  ```

    <span data-ttu-id="30345-157">Pour obtenir d’autres exemples et des paramètres, [consultez New-CsTenantDialPlan.](https://docs.microsoft.com/powershell/module/skype/new-cstenantdialplan)</span><span class="sxs-lookup"><span data-stu-id="30345-157">For other examples and parameters, see [New-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/new-cstenantdialplan).</span></span>
    
- <span data-ttu-id="30345-158">Pour modifier les paramètres d’un plan de numérotation existant, exécutez :</span><span class="sxs-lookup"><span data-stu-id="30345-158">To edit the settings of an existing dial plan, run:</span></span>
    
  ```PowerShell
  Set-CsTenantDialPlan -Identity RedmondDialPlan  -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9
    -SimpleName "Dial-Plan-for-Redmond"
  ```

    <span data-ttu-id="30345-159">Pour obtenir d’autres exemples et des paramètres, [voir Set-CsTenantDialPlan.](https://docs.microsoft.com/powershell/module/skype/set-cstenantdialplan)</span><span class="sxs-lookup"><span data-stu-id="30345-159">For other examples and parameters, see [Set-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/set-cstenantdialplan).</span></span>
    
- <span data-ttu-id="30345-160">Pour ajouter des utilisateurs à un plan de numérotation, exécutez :</span><span class="sxs-lookup"><span data-stu-id="30345-160">To add users to a dial plan, run:</span></span>
    
  ```PowerShell
  Grant-CsTenantDialPlan -Identity amos.marble@contoso.com -PolicyName RedmondDialPlan
  ```

    <span data-ttu-id="30345-161">Pour obtenir d’autres exemples et des paramètres, voir [Grant-CsTenantDialPlan.](https://docs.microsoft.com/powershell/module/skype/grant-cstenantdialplan)</span><span class="sxs-lookup"><span data-stu-id="30345-161">For other examples and parameters, see [Grant-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-cstenantdialplan).</span></span>
    
- <span data-ttu-id="30345-162">Pour afficher les paramètres d’un plan de numérotation, exécutez :</span><span class="sxs-lookup"><span data-stu-id="30345-162">To view the settings on a dial plan, run:</span></span>
    
  ```PowerShell
  Get-CsTenantDialPlan -Identity RedmondDialPlan
  ```

    <span data-ttu-id="30345-163">Pour obtenir d’autres exemples et des paramètres, [consultez Get-CsTenantDialPlan.](https://docs.microsoft.com/powershell/module/skype/get-cstenantdialplan?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="30345-163">For other examples and parameters, see [Get-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/get-cstenantdialplan?view=skype-ps).</span></span>
    
- <span data-ttu-id="30345-164">Pour supprimer un plan de numérotation, exécutez :</span><span class="sxs-lookup"><span data-stu-id="30345-164">To delete a dial plan, run:</span></span>
    
  ```PowerShell
  Remove-CsTenantDialPlan -Identity RedmondDialPlan -force
  ```

    <span data-ttu-id="30345-165">Pour obtenir d’autres exemples et des paramètres, [voir Remove-CsTenantDialPlan.](https://docs.microsoft.com/powershell/module/skype/remove-cstenantdialplan?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="30345-165">For other examples and parameters, see [Remove-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/remove-cstenantdialplan?view=skype-ps).</span></span>
    
- <span data-ttu-id="30345-166">Pour voir les paramètres du plan de numérotation efficace, exécutez :</span><span class="sxs-lookup"><span data-stu-id="30345-166">To see the settings of the effective dial plan, run:</span></span>
    
  ```PowerShell
  Get-CsEffectiveTenantDialPlan -Identity amos.marble@contoso.com
  ```

    <span data-ttu-id="30345-167">Pour obtenir d’autres exemples et des paramètres, [consultez Get-CsEffectiveTenantDialPlan.](https://docs.microsoft.com/powershell/module/skype/get-cseffectivetenantdialplan)</span><span class="sxs-lookup"><span data-stu-id="30345-167">For other examples and parameters, see [Get-CsEffectiveTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/get-cseffectivetenantdialplan).</span></span>
    
- <span data-ttu-id="30345-168">Pour tester les paramètres efficaces d’un plan de numérotation, exécutez :</span><span class="sxs-lookup"><span data-stu-id="30345-168">To test the effective settings of a dial plan, run:</span></span>
    
  ```PowerShell
  Test-CsEffectiveTenantDialPlan -DialedNumber 14255550199 -Identity amos.marble@contoso.com
  ```

    <span data-ttu-id="30345-169">Pour obtenir d’autres exemples et des paramètres, voir [Test-CsEffectiveTenantDialPlan.](https://docs.microsoft.com/powershell/module/skype/test-cseffectivetenantdialplan?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="30345-169">For other examples and parameters, see [Test-CsEffectiveTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/test-cseffectivetenantdialplan?view=skype-ps).</span></span>
    
#### <a name="using-a-powershell-script"></a><span data-ttu-id="30345-170">Utilisation d’un script PowerShell</span><span class="sxs-lookup"><span data-stu-id="30345-170">Using a PowerShell script</span></span>

<span data-ttu-id="30345-171">Exécutez l’action ci-après pour supprimer une règle de normalisation associée à un plan de numérotation client sans avoir à supprimer d’abord le plan de numérotation client :</span><span class="sxs-lookup"><span data-stu-id="30345-171">Run this to delete a normalization rule that is associated with a tenant dial plan without needing to delete the tenant dial plan first:</span></span>
```PowerShell
$b1=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$b1}
(Get-CsTenantDialPlan -Identity RedmondDialPlan).NormalizationRules
$b2=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$b2}
```
<span data-ttu-id="30345-172">Exécutez l’action suivante pour ajouter la règle de normalisation suivante au plan de numérotation client existant nommé RedmondDialPlan.</span><span class="sxs-lookup"><span data-stu-id="30345-172">Run this to add the following normalization rule to the existing tenant dial plan named RedmondDialPlan.</span></span>
```PowerShell
$nr1=New-CsVoiceNormalizationRule -Parent Global -Description 'Organization extension dialing' -Pattern '^(\\d{3})$' -Translation '+14255551$1' -Name NR1 -IsInternalExtension $false -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$nr1}
```
<span data-ttu-id="30345-173">Exécutez cette action pour supprimer la règle de normalisation suivante du plan de numérotation client existant nommé RedmondDialPlan.</span><span class="sxs-lookup"><span data-stu-id="30345-173">Run this to remove the following normalization rule from the existing tenant dial plan named RedmondDialPlan.</span></span>
```PowerShell
$nr1=New-CsVoiceNormalizationRule -Parent Global/NR1 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$nr1}
```

<span data-ttu-id="30345-174">Exécutez l’objet suivant lorsque vous voulez également examiner les règles de normalisation existantes, déterminer celle que vous voulez supprimer, puis utiliser son index pour la supprimer.</span><span class="sxs-lookup"><span data-stu-id="30345-174">Run the following when you want to also examine the existing normalization rules, determine which one you want to delete, and then use its index to remove it.</span></span> <span data-ttu-id="30345-175">L’ensemble des règles de normalisation commence par l’index 0.</span><span class="sxs-lookup"><span data-stu-id="30345-175">The array of normalization rules starts with index 0.</span></span> <span data-ttu-id="30345-176">Nous voulons supprimer la règle de normalisation de 3 chiffres, à savoir l’index 1.</span><span class="sxs-lookup"><span data-stu-id="30345-176">We would like to remove the 3-digit normalization rule, so that is index 1.</span></span>
  
```PowerShell
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

$nr1=(Get-CsTenantDialPlan RedmondDialPlan).NormalizationRules[1]
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$nr1}
```

<span data-ttu-id="30345-177">Exécutez l’événement pour rechercher tous les utilisateurs qui ont reçu le plan de numérotation client RedmondDialPlan.</span><span class="sxs-lookup"><span data-stu-id="30345-177">Run this to find all users who have been granted the RedmondDialPlan tenant dial plan.</span></span>
  
```PowerShell
Get-CsOnlineUser | Where-Object {$_.TenantDialPlan -eq "RedmondDialPlan"}
```

<span data-ttu-id="30345-178">Exécutez cette tâche pour supprimer tout TenantDialPlan affecté à tous les utilisateurs qui ont un HostingProvider of sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="30345-178">Run this to remove any assigned TenantDialPlan from all users who have a HostingProvider of sipfed.online.lync.com.</span></span>
```PowerShell
Get-CsOnlineUser -Filter {HostingProvider -eq "sipfed.online.lync.com"} | Grant-CsTenantDialPlan -policyname $null
```

<span data-ttu-id="30345-179">Exécutez-les pour ajouter le plan de numérotation local nommé OPDP1 comme plan de numérotation client pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="30345-179">Run these to add the existing on-premises dial plan named OPDP1 as a tenant dial plan for your organization.</span></span> <span data-ttu-id="30345-180">Vous devez d’abord enregistrer le plan de numérotation local dans un fichier .xml, puis l’utiliser pour créer le plan de numérotation client.</span><span class="sxs-lookup"><span data-stu-id="30345-180">You need to first save the on-premises dial plan to an .xml file, and then use it to create the new tenant dial plan.</span></span>
  
<span data-ttu-id="30345-181">Exécutez l’action ci-après pour enregistrer le plan de numérotation local au fichier .xml.</span><span class="sxs-lookup"><span data-stu-id="30345-181">Run this to save the on-premises dial plan to the .xml file.</span></span>
  
```PowerShell
$DPName = "OPDP1"
$DPFileName = "dialplan.xml"
Get-CsDialplan $DPName | Export-Clixml $DPFileName
```

<span data-ttu-id="30345-182">Exécutez l’action ci-après pour créer le plan de numérotation client.</span><span class="sxs-lookup"><span data-stu-id="30345-182">Run this to create the new tenant dial plan.</span></span>
  
```PowerShell
$DPFileName = "dialplan.xml"
$dp = Import-Clixml $DPFileName
$NormRules = @()
ForEach($nr in $dp.NormalizationRules)
{
 $id1 = "Global/" + $nr.Name
 $nr2 = New-CsVoiceNormalizationRule -Identity $id1 -Description $nr.Description -Pattern $nr.Pattern -Translation $nr.Translation -IsInternalExtension $nr.IsInternalExtension -InMemory
 $NormRules += $nr2
}
New-CsTenantDialPlan -Identity $dp.SimpleName -ExternalAccessPrefix $dp.ExternalAccessPrefix -Description $dp.Description -OptimizeDeviceDialing $dp.OptimizeDeviceDialing -SimpleName $dp.SimpleName -NormalizationRules $NormRules
```
    
## <a name="related-topics"></a><span data-ttu-id="30345-183">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="30345-183">Related topics</span></span>

- [<span data-ttu-id="30345-184">Qu’est-ce que les plans de numérotation ?</span><span class="sxs-lookup"><span data-stu-id="30345-184">What are dial plans?</span></span>](what-are-dial-plans.md)
- [<span data-ttu-id="30345-185">Questions fréquentes à propos du transfert de numéros de téléphone</span><span class="sxs-lookup"><span data-stu-id="30345-185">Transferring phone numbers common questions</span></span>](transferring-phone-numbers-common-questions.md)
- [<span data-ttu-id="30345-186">Différents types de numéros de téléphone utilisés pour les offres d'appel</span><span class="sxs-lookup"><span data-stu-id="30345-186">Different kinds of phone numbers used for Calling Plans</span></span>](different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [<span data-ttu-id="30345-187">Gérer des numéros de téléphone pour votre entreprise</span><span class="sxs-lookup"><span data-stu-id="30345-187">Manage phone numbers for your organization</span></span>](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
- [<span data-ttu-id="30345-188">Conditions générales relatives aux appels d'urgence</span><span class="sxs-lookup"><span data-stu-id="30345-188">Emergency calling terms and conditions</span></span>](emergency-calling-terms-and-conditions.md)
- <span data-ttu-id="30345-189">[Étiquette d’exclusion de responsabilité pour les appels d’urgence](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="30345-189">[Emergency calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>
- [<span data-ttu-id="30345-190">Présentation de Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="30345-190">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
