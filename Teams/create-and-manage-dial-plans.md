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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Calling Plans
- seo-marvel-apr2020
description: Découvrez comment utiliser le Centre Microsoft Teams d’administration Windows PowerShell pour créer et gérer des plans de numérotation (plans de numérotation PSTN).
ms.openlocfilehash: 44ecabfb04d8919ac289067818e736e170e6d181
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58728703"
---
# <a name="create-and-manage-dial-plans"></a>Créer et gérer les plans de numérotation

Après avoir plané les plans de numérotation de votre organisation et compris toutes les règles de normalisation à créer pour le routage vocal, vous êtes prêt à créer les plans de numérotation. Avec un compte d’administrateur dispose d’une licence de numérotation Teams valide, vous pouvez utiliser le Centre d’administration Microsoft Teams ou la Windows PowerShell pour créer et gérer des plans de numérotation.  

## <a name="using-the-microsoft-teams-admin-center"></a>Utiliser le centre d’administration Microsoft Teams

### <a name="create-a-dial-plan"></a>Créer un plan de numérotation

1. Dans le panneau de navigation de gauche du Microsoft Teams d’administration, allez dans **le**  >  **plan de numérotation vocale.**
2. Cliquez **sur** Ajouter, puis entrez un nom et une description pour le plan de numérotation.
    ![Capture d’écran montrant la page Ajouter pour la création d’un plan de numérotation.](media/create-dial-plan.png)
3. Sous les **détails** du plan de numérotation, spécifiez un préfixe de numérotation externe si les utilisateurs doivent composer un ou plusieurs chiffres de tête supplémentaires (par exemple, 9) pour obtenir une ligne externe. Pour ce faire :
    1. Dans la **zone du préfixe de numérotation** externe, entrez un préfixe de numérotation externe. Le préfixe peut prendre jusqu’à quatre caractères (#,*, et 0-9).
    2. Activer la **numérotation optimisée des appareils.** Si vous spécifiez un préfixe de numérotation externe, vous devez également activer ce paramètre pour appliquer le préfixe afin que les appels soient effectués à l’extérieur de votre organisation.
4. Dans le **cadre des règles de normalisation,** configurez et associez une ou plusieurs règles de [normalisation](what-are-dial-plans.md#normalization-rules) pour le plan de numérotation. Chaque plan de numérotation doit être associé à au moins une règle de normalisation.  Pour ce faire, vous pouvez :
    - Pour créer une règle de normalisation et l’associer au plan de numérotation, cliquez sur **Ajouter,** puis définissez la règle.
    - Pour modifier une règle de normalisation déjà associée au plan de numérotation, sélectionnez-la en cliquant à gauche du nom de la règle, puis cliquez sur **Modifier.** A apporter les modifications de votre souhaitez, puis cliquez sur **Enregistrer.**
    - Pour supprimer une règle de normalisation du plan de numérotation, sélectionnez-la en cliquant à gauche du nom de la règle, puis cliquez sur **Supprimer.**
5. Organisez les règles de normalisation dans l’ordre voulu. Cliquez **sur Monter** ou **Descendre** pour modifier la position des règles dans la liste.

    > [!NOTE]
    > Teams traverse la liste des règles de normalisation du haut vers le bas et utilise la première règle qui correspond au numéro composé. Si vous avez installé un plan de numérotation de sorte qu’un numéro composé corresponde à plusieurs règles de normalisation, veillez à ce que les règles plus restrictives soient triées au-dessus des règles moins restrictives. Si vous définissez un plan de numérotation qui normalise un numéro composé sans le « + », le service d’appel essaiera de revenir à la normale à l’aide des règles du client et du plan de numérotation régional. Pour éviter une normalisation en double, il est recommandé que toutes les règles de normalisation entraînent des nombres commençant par un « + ». Les clients de routage direct peuvent utiliser des règles de [traduction](direct-routing-translate-numbers.md) de ligne pour supprimer le « + » si nécessaire. 

6. Cliquez sur **Enregistrer**.
7. Si vous voulez tester le plan de numérotation, sous Tester le **plan** de numérotation, entrez un numéro de téléphone, puis cliquez sur **Test.**

### <a name="edit-a-dial-plan"></a>Modifier un plan de numérotation

1. Dans le panneau de navigation de gauche du Microsoft Teams d’administration, allez dans **le**  >  **plan de numérotation vocale.**
2. Sélectionnez le plan de numérotation en cliquant à gauche du nom du plan de numérotation, puis cliquez sur **Modifier.**
3. A apporter les modifications de votre souhaitez, puis cliquez sur **Enregistrer.**

### <a name="assign-a-dial-plan-to-users"></a>Affecter un plan de numérotation aux utilisateurs

Vous attribuez un plan de numérotation de la même façon que vous attribuez des stratégies. [!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="using-powershell"></a>Utiliser PowerShell
  
### <a name="start-powershell"></a>Démarrer PowerShell
- Ouvrez une invite Windows PowerShell commande et exécutez les commandes suivantes :

```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```
  
### <a name="create-and-manage-your-dial-plans"></a>Créer et gérer vos plans de numérotation

Vous pouvez utiliser une seule cmdlet ou un script PowerShell pour créer et gérer des plans de numérotation client.
  
#### <a name="using-single-cmdlets"></a>Utilisation d’une seule cmdlets

- Pour créer un plan de numérotation, exécutez :
    
  ```PowerShell
  New-CsTenantDialPlan -Identity RedmondDialPlan -Description "Dial Plan for Redmond" -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9 -SimpleName "Dial-Plan-for-Redmond"
  ```

    Pour obtenir d’autres exemples et des paramètres, [consultez New-CsTenantDialPlan.](/powershell/module/skype/new-cstenantdialplan)
    
- Pour modifier les paramètres d’un plan de numérotation existant, exécutez :
    
  ```PowerShell
  Set-CsTenantDialPlan -Identity RedmondDialPlan  -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9
    -SimpleName "Dial-Plan-for-Redmond"
  ```

    Pour obtenir d’autres exemples et des paramètres, [voir Set-CsTenantDialPlan.](/powershell/module/skype/set-cstenantdialplan)
    
- Pour ajouter des utilisateurs à un plan de numérotation, exécutez :
    
  ```PowerShell
  Grant-CsTenantDialPlan -Identity amos.marble@contoso.com -PolicyName RedmondDialPlan
  ```

    Pour obtenir d’autres exemples et des paramètres, voir [Grant-CsTenantDialPlan.](/powershell/module/skype/grant-cstenantdialplan)
    
- Pour afficher les paramètres d’un plan de numérotation, exécutez :
    
  ```PowerShell
  Get-CsTenantDialPlan -Identity RedmondDialPlan
  ```

    Pour obtenir d’autres exemples et des paramètres, [consultez Get-CsTenantDialPlan.](/powershell/module/skype/get-cstenantdialplan?view=skype-ps)
    
- Pour supprimer un plan de numérotation, exécutez :
    
  ```PowerShell
  Remove-CsTenantDialPlan -Identity RedmondDialPlan -force
  ```

    Pour obtenir d’autres exemples et des paramètres, [voir Remove-CsTenantDialPlan.](/powershell/module/skype/remove-cstenantdialplan?view=skype-ps)
    
- Pour voir les paramètres du plan de numérotation efficace, exécutez :
    
  ```PowerShell
  Get-CsEffectiveTenantDialPlan -Identity amos.marble@contoso.com
  ```

    Pour obtenir d’autres exemples et des paramètres, [consultez Get-CsEffectiveTenantDialPlan.](/powershell/module/skype/get-cseffectivetenantdialplan)
    
- Pour tester les paramètres efficaces d’un plan de numérotation, exécutez :
    
  ```PowerShell
  Test-CsEffectiveTenantDialPlan -DialedNumber 14255550199 -Identity amos.marble@contoso.com
  ```

    Pour obtenir d’autres exemples et des paramètres, voir [Test-CsEffectiveTenantDialPlan.](/powershell/module/skype/test-cseffectivetenantdialplan?view=skype-ps)
    
#### <a name="using-a-powershell-script"></a>Utilisation d’un script PowerShell

Exécutez l’action ci-après pour supprimer une règle de normalisation associée à un plan de numérotation client sans avoir à supprimer d’abord le plan de numérotation client :
```PowerShell
$b1=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$b1}
(Get-CsTenantDialPlan -Identity RedmondDialPlan).NormalizationRules
$b2=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$b2}
```
Exécutez l’action suivante pour ajouter la règle de normalisation suivante au plan de numérotation client existant nommé RedmondDialPlan.
```PowerShell
$nr1=New-CsVoiceNormalizationRule -Parent Global -Description 'Organization extension dialing' -Pattern '^(\\d{3})$' -Translation '+14255551$1' -Name NR1 -IsInternalExtension $false -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$nr1}
```
Exécutez cette action pour supprimer la règle de normalisation suivante du plan de numérotation client existant nommé RedmondDialPlan.
```PowerShell
$nr1=New-CsVoiceNormalizationRule -Parent Global/NR1 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$nr1}
```

Exécutez l’objet suivant lorsque vous voulez également examiner les règles de normalisation existantes, déterminer celle que vous voulez supprimer, puis utiliser son index pour la supprimer. L’ensemble des règles de normalisation commence par l’index 0. Nous voulons supprimer la règle de normalisation de 3 chiffres, à savoir l’index 1.
  
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

Exécutez l’événement pour rechercher tous les utilisateurs qui ont reçu le plan de numérotation client RedmondDialPlan.
  
```PowerShell
Get-CsOnlineUser | Where-Object {$_.TenantDialPlan -eq "RedmondDialPlan"}
```

Exécutez cette tâche pour supprimer tout TenantDialPlan affecté à tous les utilisateurs qui ont un HostingProvider of sipfed.online.lync.com.
```PowerShell
Get-CsOnlineUser -Filter {HostingProvider -eq "sipfed.online.lync.com"} | Grant-CsTenantDialPlan -policyname $null
```

Exécutez-les pour ajouter le plan de numérotation local nommé OPDP1 comme plan de numérotation client pour votre organisation. Vous devez d’abord enregistrer le plan de numérotation local dans un fichier .xml puis l’utiliser pour créer le plan de numérotation client.
  
Exécutez l’action ci-après pour enregistrer le plan de numérotation local dans .xml fichier.
  
```PowerShell
$DPName = "OPDP1"
$DPFileName = "dialplan.xml"
Get-CsDialplan $DPName | Export-Clixml $DPFileName
```

Exécutez l’action ci-après pour créer le plan de numérotation client.
  
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
    
## <a name="related-topics"></a>Sujets associés

- [Qu’est-ce que les plans de numérotation ?](what-are-dial-plans.md)
- [Questions fréquentes à propos du transfert de numéros de téléphone](./phone-number-calling-plans/port-order-overview.md)
- [Différents types de numéros de téléphone utilisés pour les offres d'appel](different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [Gérer des numéros de téléphone pour votre entreprise](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
- [Conditions générales relatives aux appels d'urgence](emergency-calling-terms-and-conditions.md)
- [Étiquette d’exclusion de responsabilité pour les appels d’urgence](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
- [Présentation de Teams PowerShell](teams-powershell-overview.md)
