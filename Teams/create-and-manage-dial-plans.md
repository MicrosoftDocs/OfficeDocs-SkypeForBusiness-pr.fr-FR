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
description: Découvrez comment utiliser le centre d’administration Microsoft teams ou Windows PowerShell pour créer et gérer les plans de numérotation (appels RTC).
ms.openlocfilehash: 0e5f45ecdb92843a77bd7a957b1b7c31b3403b92
ms.sourcegitcommit: 60b859dcb8ac727a38bf28cdb63ff762e7338af8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/30/2020
ms.locfileid: "44938233"
---
# <a name="create-and-manage-dial-plans"></a><span data-ttu-id="258ec-103">Créer et gérer les plans de numérotation</span><span class="sxs-lookup"><span data-stu-id="258ec-103">Create and manage dial plans</span></span>

<span data-ttu-id="258ec-104">Une fois que vous avez planifié les plans de numérotation pour votre organisation et que vous avez défini toutes les règles de normalisation qui doivent être créées pour le routage des appels, vous pouvez créer les plans de numérotation.</span><span class="sxs-lookup"><span data-stu-id="258ec-104">After you plan the dial plans for your organization and figured out all the normalization rules that need to be created for call routing, you're ready to create the dial plans.</span></span> <span data-ttu-id="258ec-105">Vous pouvez utiliser le centre d’administration Microsoft teams ou Windows PowerShell pour créer et gérer les plans de numérotation.</span><span class="sxs-lookup"><span data-stu-id="258ec-105">You can use the Microsoft Teams admin center or Windows PowerShell to create and manage dial plans.</span></span>  

## <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="258ec-106">Utilisation du centre d’administration Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="258ec-106">Using the Microsoft Teams admin center</span></span>

### <a name="create-a-dial-plan"></a><span data-ttu-id="258ec-107">Créer un plan de numérotation</span><span class="sxs-lookup"><span data-stu-id="258ec-107">Create a dial plan</span></span>

1. <span data-ttu-id="258ec-108">Dans le volet de navigation de gauche du centre d’administration de Microsoft **Voice**Teams, accédez au  >  **plan de numérotation**vocale.</span><span class="sxs-lookup"><span data-stu-id="258ec-108">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Dial plan**.</span></span>
2. <span data-ttu-id="258ec-109">Cliquez sur **Ajouter**, puis entrez un nom et une description pour le plan de numérotation.</span><span class="sxs-lookup"><span data-stu-id="258ec-109">Click **Add**, and then enter a name and description for the dial plan.</span></span>
    <span data-ttu-id="258ec-110">![Capture d’écran montrant la page Ajouter pour la création d’un plan de numérotation](media/create-dial-plan.png)</span><span class="sxs-lookup"><span data-stu-id="258ec-110">![Screenshot showing the Add page for creating a dial plan](media/create-dial-plan.png)</span></span>
3. <span data-ttu-id="258ec-111">Sous **Détails du plan de numérotation**, spécifiez un préfixe de numérotation externe si les utilisateurs doivent composer au moins un chiffre de début supplémentaire (par exemple, 9) pour obtenir une ligne externe.</span><span class="sxs-lookup"><span data-stu-id="258ec-111">Under **Dial plan details**, specify an external dialing prefix if users need to dial one or more additional leading digits (for example, 9) to get an external line.</span></span> <span data-ttu-id="258ec-112">Pour ce faire :</span><span class="sxs-lookup"><span data-stu-id="258ec-112">To do this:</span></span>
    1. <span data-ttu-id="258ec-113">Dans la zone **préfixe de numérotation externe** , entrez un préfixe de numérotation externe.</span><span class="sxs-lookup"><span data-stu-id="258ec-113">In the **External dialing prefix** box, enter an external dialing prefix.</span></span> <span data-ttu-id="258ec-114">Le préfixe peut comporter jusqu’à 4 caractères (#, \* et 0-9).</span><span class="sxs-lookup"><span data-stu-id="258ec-114">The prefix can be up to four characters (#,\*, and 0-9).</span></span>
    2. <span data-ttu-id="258ec-115">Activez la **numérotation de l’appareil optimisé**.</span><span class="sxs-lookup"><span data-stu-id="258ec-115">Turn on **Optimized device dialing**.</span></span> <span data-ttu-id="258ec-116">Si vous spécifiez un préfixe de numérotation externe, vous devez également activer ce paramètre pour appliquer le préfixe de sorte que les appels puissent être effectués en dehors de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="258ec-116">If you specify an external dialing prefix, you must also turn on this setting to apply the prefix so calls can be made outside your organization.</span></span>
4. <span data-ttu-id="258ec-117">Sous **règles de normalisation**, configurez et associez une ou plusieurs [règles de normalisation](what-are-dial-plans.md#normalization-rules) pour le plan de numérotation.</span><span class="sxs-lookup"><span data-stu-id="258ec-117">Under **Normalization rules**, configure and associate one or more [normalization rules](what-are-dial-plans.md#normalization-rules) for the dial plan.</span></span> <span data-ttu-id="258ec-118">Au moins une règle de normalisation doit être associée à chaque plan de numérotation.</span><span class="sxs-lookup"><span data-stu-id="258ec-118">Each dial plan must have at least one normalization rule associated with it.</span></span>  <span data-ttu-id="258ec-119">Pour cela, effectuez une ou plusieurs des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="258ec-119">To do this, do one or more of the following:</span></span>
    - <span data-ttu-id="258ec-120">Pour créer une règle de normalisation et l’associer au plan de numérotation, cliquez sur **Ajouter**, puis définissez la règle.</span><span class="sxs-lookup"><span data-stu-id="258ec-120">To create a new normalization rule and associate it with the dial plan, click **Add**, and then define the rule.</span></span>
    - <span data-ttu-id="258ec-121">Pour modifier une règle de normalisation déjà associée au plan de numérotation, sélectionnez la règle en cliquant à gauche du nom de la règle, puis cliquez sur **modifier**.</span><span class="sxs-lookup"><span data-stu-id="258ec-121">To edit a normalization rule that's already associated with the dial plan, select the rule by clicking to the left of the rule name, and then click **Edit**.</span></span> <span data-ttu-id="258ec-122">Apportez les modifications souhaitées, puis cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="258ec-122">Make the changes you want, and then click **Save**.</span></span>
    - <span data-ttu-id="258ec-123">Pour supprimer une règle de normalisation du plan de numérotation, sélectionnez la règle en cliquant à gauche du nom de la règle, puis cliquez sur **supprimer**.</span><span class="sxs-lookup"><span data-stu-id="258ec-123">To remove a normalization rule from the dial plan, select the rule by clicking to the left of the rule name, and then click **Remove**.</span></span>
5. <span data-ttu-id="258ec-124">Organisez les règles de normalisation dans l’ordre de votre choix.</span><span class="sxs-lookup"><span data-stu-id="258ec-124">Arrange the normalization rules in the order that you want.</span></span> <span data-ttu-id="258ec-125">Cliquez sur **monter** ou **descendre** pour modifier la position des règles dans la liste.</span><span class="sxs-lookup"><span data-stu-id="258ec-125">Click **Move up** or **Move down** to change the position of rules in the list.</span></span>

    > [!NOTE]
    > <span data-ttu-id="258ec-126">Teams parcourt la liste des règles de normalisation du haut vers le bas et utilise la première règle qui correspond au numéro numéroté.</span><span class="sxs-lookup"><span data-stu-id="258ec-126">Teams traverses the list of normalization rules from the top down and uses the first rule that matches the dialed number.</span></span> <span data-ttu-id="258ec-127">Si vous avez configuré un plan de numérotation de manière à ce qu’un numéro composé puisse correspondre à plusieurs règles de normalisation, assurez-vous que les règles les plus restrictives sont triées au-dessus des règles les moins strictes.</span><span class="sxs-lookup"><span data-stu-id="258ec-127">If you set up a dial plan so that a dialed number can match more than one normalization rule, make sure the more restrictive rules are sorted above the less restrictive ones.</span></span>

6. <span data-ttu-id="258ec-128">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="258ec-128">Click **Save**.</span></span>
7. <span data-ttu-id="258ec-129">Si vous voulez tester le plan de numérotation, sous **tester le plan de numérotation**, entrez un numéro de téléphone, puis cliquez sur **tester**.</span><span class="sxs-lookup"><span data-stu-id="258ec-129">If you want to test the dial plan, under **Test dial plan**, enter a phone number, and then click **Test**.</span></span>

### <a name="edit-a-dial-plan"></a><span data-ttu-id="258ec-130">Modifier un plan de numérotation</span><span class="sxs-lookup"><span data-stu-id="258ec-130">Edit a dial plan</span></span>

1. <span data-ttu-id="258ec-131">Dans le volet de navigation de gauche du centre d’administration de Microsoft **Voice**Teams, accédez au  >  **plan de numérotation**vocale.</span><span class="sxs-lookup"><span data-stu-id="258ec-131">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Dial plan**.</span></span>
2. <span data-ttu-id="258ec-132">Sélectionnez le plan de numérotation en cliquant à gauche du nom du plan de numérotation, puis cliquez sur **modifier**.</span><span class="sxs-lookup"><span data-stu-id="258ec-132">Select the dial plan by clicking to the left of the dial plan name, and then click **Edit**.</span></span>
3. <span data-ttu-id="258ec-133">Apportez les modifications souhaitées, puis cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="258ec-133">Make the changes that you want, and then click **Save**.</span></span>

### <a name="assign-a-dial-plan-to-users"></a><span data-ttu-id="258ec-134">Affectation d’un plan de numérotation aux utilisateurs</span><span class="sxs-lookup"><span data-stu-id="258ec-134">Assign a dial plan to users</span></span>

<span data-ttu-id="258ec-135">Vous affectez un plan de numérotation de la même manière que vous attribuez des stratégies.</span><span class="sxs-lookup"><span data-stu-id="258ec-135">You assign a dial plan in the same way you assign policies.</span></span> [!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="using-powershell"></a><span data-ttu-id="258ec-136">Utiliser PowerShell</span><span class="sxs-lookup"><span data-stu-id="258ec-136">Using PowerShell</span></span>
  
### <a name="verify-and-start-remote-powershell"></a><span data-ttu-id="258ec-137">Vérifier et Démarrer PowerShell distant</span><span class="sxs-lookup"><span data-stu-id="258ec-137">Verify and start Remote PowerShell</span></span>

 <span data-ttu-id="258ec-138">**Vérifiez que vous exécutez la version 3,0 ou une version ultérieure de Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="258ec-138">**Check that you are running Windows PowerShell version 3.0 or later**</span></span>
  
1. <span data-ttu-id="258ec-139">Pour vérifier que vous exécutez la version 3,0 ou une version ultérieure : **menu Démarrer**  >  **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="258ec-139">To verify that you're running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="258ec-140">Consultez la version en entrant  _Get-Host_ dans la fenêtre **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="258ec-140">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="258ec-141">Si vous n’avez pas la version 3,0 ou une version ultérieure, téléchargez et installez les mises à jour de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="258ec-141">If you don't have version 3.0 or later, download and install updates to Windows PowerShell.</span></span> <span data-ttu-id="258ec-142">Pour télécharger et mettre à jour Windows PowerShell vers la version 4,0, voir [Windows Management Framework 4,0](https://go.microsoft.com/fwlink/?LinkId=716845) .</span><span class="sxs-lookup"><span data-stu-id="258ec-142">See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0.</span></span> <span data-ttu-id="258ec-143">Redémarrez votre ordinateur lorsque vous y êtes invité.</span><span class="sxs-lookup"><span data-stu-id="258ec-143">Restart your computer when you're prompted.</span></span>
    
4. <span data-ttu-id="258ec-144">Vous devez également installer le module Windows PowerShell pour Skype entreprise Online qui vous permet de créer une session Windows PowerShell distante qui se connecte à Skype entreprise online.</span><span class="sxs-lookup"><span data-stu-id="258ec-144">You'll also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> <span data-ttu-id="258ec-145">Vous pouvez télécharger ce module, qui est uniquement pris en charge sur les ordinateurs 64 bits, dans le [module Windows PowerShell pour Skype entreprise Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span><span class="sxs-lookup"><span data-stu-id="258ec-145">You can download this module, which is supported only on 64-bit computers, at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span></span> <span data-ttu-id="258ec-146">Redémarrez l’ordinateur si vous y êtes invité.</span><span class="sxs-lookup"><span data-stu-id="258ec-146">Restart your computer if you're prompted.</span></span>
    
<span data-ttu-id="258ec-147">Pour en savoir plus, voir [se connecter à tous les services microsoft 365 ou Office 365 dans une seule fenêtre Windows PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span><span class="sxs-lookup"><span data-stu-id="258ec-147">To learn more, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span>
  
 <span data-ttu-id="258ec-148">**Démarrez une session Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="258ec-148">**Start a Windows PowerShell session**</span></span>
  
1. <span data-ttu-id="258ec-149">Cliquez sur **Démarrer**  >  **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="258ec-149">Click **Start** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="258ec-150">Dans la fenêtre **Windows PowerShell** , connectez-vous à Microsoft 365 ou Office 365 en exécutant :</span><span class="sxs-lookup"><span data-stu-id="258ec-150">In the **Windows PowerShell** window, connect to Microsoft 365 or Office 365 by running:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="258ec-151">Vous devez seulement exécuter la commande **Import-Module** la première fois que vous utilisez le module Windows PowerShell pour Skype Entreprise Online.</span><span class="sxs-lookup"><span data-stu-id="258ec-151">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>
  

    ```PowerShell
    Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
    ```
  
### <a name="create-and-manage-your-dial-plans"></a><span data-ttu-id="258ec-152">Création et gestion de vos plans de numérotation</span><span class="sxs-lookup"><span data-stu-id="258ec-152">Create and manage your dial plans</span></span>

<span data-ttu-id="258ec-153">Vous pouvez utiliser une cmdlet unique ou un script PowerShell pour créer et gérer les plans de numérotation client.</span><span class="sxs-lookup"><span data-stu-id="258ec-153">You can either use a single cmdlet or a PowerShell script to create and manage tenant dial plans.</span></span>
  
#### <a name="using-single-cmdlets"></a><span data-ttu-id="258ec-154">Utilisation d’applets de applet uniques</span><span class="sxs-lookup"><span data-stu-id="258ec-154">Using single cmdlets</span></span>

- <span data-ttu-id="258ec-155">Pour créer un plan de numérotation, exécutez :</span><span class="sxs-lookup"><span data-stu-id="258ec-155">To create a new dial plan, run:</span></span>
    
  ```PowerShell
  New-CsTenantDialPlan -Identity RedmondDialPlan -Description "Dial Plan for Redmond" -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9 -SimpleName "Dial-Plan-for-Redmond"
  ```

    <span data-ttu-id="258ec-156">Pour obtenir d’autres exemples et des paramètres, consultez la rubrique [New-rubrique Remove](https://docs.microsoft.com/powershell/module/skype/new-cstenantdialplan).</span><span class="sxs-lookup"><span data-stu-id="258ec-156">For other examples and parameters, see [New-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/new-cstenantdialplan).</span></span>
    
- <span data-ttu-id="258ec-157">Pour modifier les paramètres d’un plan de numérotation existant, exécutez :</span><span class="sxs-lookup"><span data-stu-id="258ec-157">To edit the settings of an existing dial plan, run:</span></span>
    
  ```PowerShell
  Set-CsTenantDialPlan -Identity RedmondDialPlan  -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9
    -SimpleName "Dial-Plan-for-Redmond"
  ```

    <span data-ttu-id="258ec-158">Pour obtenir d’autres exemples et des paramètres, consultez la rubrique [Set-rubrique Remove](https://docs.microsoft.com/powershell/module/skype/set-cstenantdialplan).</span><span class="sxs-lookup"><span data-stu-id="258ec-158">For other examples and parameters, see [Set-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/set-cstenantdialplan).</span></span>
    
- <span data-ttu-id="258ec-159">Pour ajouter des utilisateurs à un plan de numérotation, exécutez :</span><span class="sxs-lookup"><span data-stu-id="258ec-159">To add users to a dial plan, run:</span></span>
    
  ```PowerShell
  Grant-CsTenantDialPlan -Identity amos.marble@contoso.com -PolicyName RedmondDialPlan
  ```

    <span data-ttu-id="258ec-160">Pour obtenir d’autres exemples et des paramètres, consultez la rubrique [Grant-rubrique Remove](https://docs.microsoft.com/powershell/module/skype/grant-cstenantdialplan).</span><span class="sxs-lookup"><span data-stu-id="258ec-160">For other examples and parameters, see [Grant-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-cstenantdialplan).</span></span>
    
- <span data-ttu-id="258ec-161">Pour afficher les paramètres d’un plan de numérotation, exécutez :</span><span class="sxs-lookup"><span data-stu-id="258ec-161">To view the settings on a dial plan, run:</span></span>
    
  ```PowerShell
  Get-CsTenantDialPlan -Identity RedmondDialPlan
  ```

    <span data-ttu-id="258ec-162">Pour obtenir d’autres exemples et des paramètres, consultez la rubrique [Get-rubrique Remove](https://docs.microsoft.com/powershell/module/skype/get-cstenantdialplan?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="258ec-162">For other examples and parameters, see [Get-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/get-cstenantdialplan?view=skype-ps).</span></span>
    
- <span data-ttu-id="258ec-163">Pour supprimer un plan de numérotation, exécutez :</span><span class="sxs-lookup"><span data-stu-id="258ec-163">To delete a dial plan, run:</span></span>
    
  ```PowerShell
  Remove-CsTenantDialPlan -Identity RedmondDialPlan -force
  ```

    <span data-ttu-id="258ec-164">Pour obtenir d’autres exemples et des paramètres, consultez la rubrique [Remove-rubrique Remove](https://docs.microsoft.com/powershell/module/skype/remove-cstenantdialplan?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="258ec-164">For other examples and parameters, see [Remove-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/remove-cstenantdialplan?view=skype-ps).</span></span>
    
- <span data-ttu-id="258ec-165">Pour afficher les paramètres du plan de numérotation efficace, exécutez :</span><span class="sxs-lookup"><span data-stu-id="258ec-165">To see the settings of the effective dial plan, run:</span></span>
    
  ```PowerShell
  Get-CsEffectiveTenantDialPlan -Identity amos.marble@contoso.com
  ```

    <span data-ttu-id="258ec-166">Pour obtenir d’autres exemples et des paramètres, consultez la rubrique [Get-CsEffectiveTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/get-cseffectivetenantdialplan).</span><span class="sxs-lookup"><span data-stu-id="258ec-166">For other examples and parameters, see [Get-CsEffectiveTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/get-cseffectivetenantdialplan).</span></span>
    
- <span data-ttu-id="258ec-167">Pour tester les paramètres efficaces d’un plan de numérotation, exécutez :</span><span class="sxs-lookup"><span data-stu-id="258ec-167">To test the effective settings of a dial plan, run:</span></span>
    
  ```PowerShell
  Test-CsEffectiveTenantDialPlan -DialedNumber 14255550199 -Identity amos.marble@contoso.com
  ```

    <span data-ttu-id="258ec-168">Pour obtenir d’autres exemples et des paramètres, consultez la rubrique [test-CsEffectiveTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/test-cseffectivetenantdialplan?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="258ec-168">For other examples and parameters, see [Test-CsEffectiveTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/test-cseffectivetenantdialplan?view=skype-ps).</span></span>
    
#### <a name="using-a-powershell-script"></a><span data-ttu-id="258ec-169">Utilisation d’un script PowerShell</span><span class="sxs-lookup"><span data-stu-id="258ec-169">Using a PowerShell script</span></span>

<span data-ttu-id="258ec-170">Exécutez l’opération suivante pour supprimer une règle de normalisation associée à un plan de numérotation client sans avoir à supprimer d’abord le plan de numérotation client :</span><span class="sxs-lookup"><span data-stu-id="258ec-170">Run this to delete a normalization rule that is associated with a tenant dial plan without needing to delete the tenant dial plan first:</span></span>
```PowerShell
$b1=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$b1}
(Get-CsTenantDialPlan -Identity RedmondDialPlan).NormalizationRules
$b2=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$b2}
```
<span data-ttu-id="258ec-171">Exécutez l’outil pour ajouter la règle de normalisation suivante au plan de numérotation client existant nommé RedmondDialPlan.</span><span class="sxs-lookup"><span data-stu-id="258ec-171">Run this to add the following normalization rule to the existing tenant dial plan named RedmondDialPlan.</span></span>
```PowerShell
$nr1=New-CsVoiceNormalizationRule -Parent Global -Description 'Organization extension dialing' -Pattern '^(\\d{3})$' -Translation '+14255551$1' -Name NR1 -IsInternalExtension $false -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$nr1}
```
<span data-ttu-id="258ec-172">Exécutez cette commande pour supprimer la règle de normalisation suivante du plan de numérotation client existant nommé RedmondDialPlan.</span><span class="sxs-lookup"><span data-stu-id="258ec-172">Run this to remove the following normalization rule from the existing tenant dial plan named RedmondDialPlan.</span></span>
```PowerShell
$nr1=New-CsVoiceNormalizationRule -Parent Global/NR1 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$nr1}
```

<span data-ttu-id="258ec-173">Exécutez la commande suivante lorsque vous voulez également examiner les règles de normalisation existantes, déterminer celle que vous voulez supprimer, puis utiliser son index pour la supprimer.</span><span class="sxs-lookup"><span data-stu-id="258ec-173">Run the following when you want to also examine the existing normalization rules, determine which one you want to delete, and then use its index to remove it.</span></span> <span data-ttu-id="258ec-174">Le tableau de règles de normalisation commence par l’index 0.</span><span class="sxs-lookup"><span data-stu-id="258ec-174">The array of normalization rules starts with index 0.</span></span> <span data-ttu-id="258ec-175">Nous voulons supprimer la règle de normalisation à 3 chiffres, afin qu’il s’agit de l’index 1.</span><span class="sxs-lookup"><span data-stu-id="258ec-175">We would like to remove the 3-digit normalization rule, so that is index 1.</span></span>
  
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

<span data-ttu-id="258ec-176">Exécutez l’outil pour rechercher tous les utilisateurs disposant d’un plan de numérotation client RedmondDialPlan.</span><span class="sxs-lookup"><span data-stu-id="258ec-176">Run this to find all users who have been granted the RedmondDialPlan tenant dial plan.</span></span>
  
```PowerShell
Get-CsOnlineUser | Where-Object {$_.TenantDialPlan -eq "RedmondDialPlan"}
```

<span data-ttu-id="258ec-177">Exécutez cette opération pour supprimer les TenantDialPlan attribués de tous les utilisateurs disposant d’un HostingProvider de sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="258ec-177">Run this to remove any assigned TenantDialPlan from all users who have a HostingProvider of sipfed.online.lync.com.</span></span>
```PowerShell
Get-CsOnlineUser -Filter {HostingProvider -eq "sipfed.online.lync.com"} | Grant-CsTenantDialPlan -policyname $null
```

<span data-ttu-id="258ec-178">Exécutez ces derniers pour ajouter le plan de numérotation local existant intitulé OPDP1 comme plan de numérotation client pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="258ec-178">Run these to add the existing on-premises dial plan named OPDP1 as a tenant dial plan for your organization.</span></span> <span data-ttu-id="258ec-179">Vous devez d’abord enregistrer le plan de numérotation local dans un fichier. xml, puis l’utiliser pour créer le plan de numérotation client.</span><span class="sxs-lookup"><span data-stu-id="258ec-179">You need to first save the on-premises dial plan to an .xml file, and then use it to create the new tenant dial plan.</span></span>
  
<span data-ttu-id="258ec-180">Exécutez cet enregistrement pour enregistrer le plan de numérotation local au fichier. Xml.</span><span class="sxs-lookup"><span data-stu-id="258ec-180">Run this to save the on-premises dial plan to the .xml file.</span></span>
  
```PowerShell
$DPName = "OPDP1"
$DPFileName = "dialplan.xml"
Get-CsDialplan $DPName | Export-Clixml $DPFileName
```

<span data-ttu-id="258ec-181">Exécutez cette opération pour créer le plan de numérotation client.</span><span class="sxs-lookup"><span data-stu-id="258ec-181">Run this to create the new tenant dial plan.</span></span>
  
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
    
## <a name="related-topics"></a><span data-ttu-id="258ec-182">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="258ec-182">Related topics</span></span>

- [<span data-ttu-id="258ec-183">Qu’est-ce que les plans de numérotation ?</span><span class="sxs-lookup"><span data-stu-id="258ec-183">What are dial plans?</span></span>](what-are-dial-plans.md)
- [<span data-ttu-id="258ec-184">Questions fréquentes à propos du transfert de numéros de téléphone</span><span class="sxs-lookup"><span data-stu-id="258ec-184">Transferring phone numbers common questions</span></span>](transferring-phone-numbers-common-questions.md)
- [<span data-ttu-id="258ec-185">Différents types de numéros de téléphone utilisés pour les offres d'appel</span><span class="sxs-lookup"><span data-stu-id="258ec-185">Different kinds of phone numbers used for Calling Plans</span></span>](different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [<span data-ttu-id="258ec-186">Gérer des numéros de téléphone pour votre entreprise</span><span class="sxs-lookup"><span data-stu-id="258ec-186">Manage phone numbers for your organization</span></span>](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
- [<span data-ttu-id="258ec-187">Conditions générales relatives aux appels d'urgence</span><span class="sxs-lookup"><span data-stu-id="258ec-187">Emergency calling terms and conditions</span></span>](emergency-calling-terms-and-conditions.md)
- <span data-ttu-id="258ec-188">[Libellé d’exclusion d’appel d’urgence](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="258ec-188">[Emergency calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>
- [<span data-ttu-id="258ec-189">Présentation de Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="258ec-189">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
