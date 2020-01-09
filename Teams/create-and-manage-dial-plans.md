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
f1keywords: None
ms.custom:
- Calling Plans
description: Découvrez comment créer et gérer les plans de numérotation des appels RTC et comment les gérer.
ms.openlocfilehash: c9623073cd5660a67bc2ba77b9c07a356d636520
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991659"
---
# <a name="create-and-manage-dial-plans"></a>Créer et gérer les plans de numérotation

Une fois que vous avez planifié les plans de numérotation pour votre organisation et que vous avez défini toutes les règles de normalisation qui doivent être créées pour le routage des appels, vous pouvez créer les plans de numérotation. Vous pouvez utiliser le centre d’administration Microsoft teams ou Windows PowerShell pour créer et gérer les plans de numérotation.  

## <a name="using-the-microsoft-teams-admin-center"></a>Utilisation du centre d’administration Microsoft teams

### <a name="create-a-dial-plan"></a>Créer un plan de numérotation

1. Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, accédez au**plan de numérotation** **vocale** > .
2. Cliquez sur **Ajouter**, puis entrez un nom et une description pour le plan de numérotation.
    ![Capture d’écran montrant la page Ajouter pour la création d’un plan de numérotation](media/create-dial-plan.png)
3. Sous **Détails du plan de numérotation**, spécifiez un préfixe de numérotation externe si les utilisateurs doivent composer au moins un chiffre de début supplémentaire (par exemple, 9) pour obtenir une ligne externe. Pour ce faire :
    1. Dans la zone **préfixe de numérotation externe** , entrez un préfixe de numérotation externe. Le préfixe peut comporter jusqu’à 4 caractères (#, * et 0-9).
    2. Activez la **numérotation de l’appareil optimisé**. Si vous spécifiez un préfixe de numérotation externe, vous devez également activer ce paramètre pour appliquer le préfixe de sorte que les appels puissent être effectués en dehors de votre organisation.
4. Sous **règles de normalisation**, configurez et associez une ou plusieurs [règles de normalisation](what-are-dial-plans.md#normalization-rules) pour le plan de numérotation. Au moins une règle de normalisation doit être associée à chaque plan de numérotation.  Pour cela, effectuez une ou plusieurs des opérations suivantes :
    - Pour créer une règle de normalisation et l’associer au plan de numérotation, cliquez sur **Ajouter**, puis définissez la règle.
    - Pour modifier une règle de normalisation déjà associée au plan de numérotation, sélectionnez la règle en cliquant à gauche du nom de la règle, puis cliquez sur **modifier**. Apportez les modifications souhaitées, puis cliquez sur **Enregistrer**.
    - Pour supprimer une règle de normalisation du plan de numérotation, sélectionnez la règle en cliquant à gauche du nom de la règle, puis cliquez sur **supprimer**.
5. Organisez les règles de normalisation dans l’ordre de votre choix. Cliquez sur **monter** ou **descendre** pour modifier la position des règles dans la liste.

    > [!NOTE]
    > Teams parcourt la liste des règles de normalisation du haut vers le bas et utilise la première règle qui correspond au numéro numéroté. Si vous avez configuré un plan de numérotation de manière à ce qu’un numéro composé puisse correspondre à plusieurs règles de normalisation, assurez-vous que les règles les plus restrictives sont triées au-dessus des règles les moins strictes.

6. Cliquez sur **Enregistrer**.
7. Si vous voulez tester le plan de numérotation, sous **tester le plan de numérotation**, entrez un numéro de téléphone, puis cliquez sur **tester**.

### <a name="edit-a-dial-plan"></a>Modifier un plan de numérotation

1. Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, accédez au**plan de numérotation** **vocale** > .
2. Sélectionnez le plan de numérotation en cliquant à gauche du nom du plan de numérotation, puis cliquez sur **modifier**.
3. Apportez les modifications souhaitées, puis cliquez sur **Enregistrer**.

### <a name="add-users-to-a-dial-plan"></a>Ajouter des utilisateurs à un plan de numérotation

1. Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, accédez au**plan de numérotation** **vocale** > .
2. Sélectionnez le plan de numérotation en cliquant à gauche du nom du plan de numérotation.
3. Sélectionnez **gérer les utilisateurs**.
4. Dans le volet **gérer les utilisateurs** , recherchez l’utilisateur par nom complet ou par nom d’utilisateur, sélectionnez le nom, puis sélectionnez **Ajouter**. Répétez cette étape pour chaque utilisateur que vous souhaitez ajouter.
5. Lorsque vous avez terminé d’ajouter des utilisateurs, sélectionnez **appliquer**.

## <a name="using-powershell"></a>Utiliser PowerShell
  
### <a name="verify-and-start-remote-powershell"></a>Vérifier et Démarrer PowerShell distant

 **Vérifiez que vous exécutez la version 3,0 ou une version ultérieure de Windows PowerShell**
  
1. Pour vérifier que vous exécutez la version 3,0 ou une version ultérieure : **menu** > démarrer**Windows PowerShell**.
    
2. Consultez la version en entrant  _Get-Host_ dans la fenêtre **Windows PowerShell**.
    
3. Si vous n’avez pas la version 3,0 ou une version ultérieure, téléchargez et installez les mises à jour de Windows PowerShell. Pour télécharger et mettre à jour Windows PowerShell vers la version 4,0, voir [Windows Management Framework 4,0](https://go.microsoft.com/fwlink/?LinkId=716845) . Redémarrez votre ordinateur lorsque vous y êtes invité.
    
4. Vous devez également installer le module Windows PowerShell pour Skype entreprise Online qui vous permet de créer une session Windows PowerShell distante qui se connecte à Skype entreprise online. Vous pouvez télécharger ce module, qui est uniquement pris en charge sur les ordinateurs 64 bits, dans le [module Windows PowerShell pour Skype entreprise Online](https://go.microsoft.com/fwlink/?LinkId=294688). Redémarrez l’ordinateur si vous y êtes invité.
    
Pour en savoir plus, voir [se connecter à tous les services Office 365 dans une seule fenêtre Windows PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).
  
 **Démarrez une session Windows PowerShell**
  
1. Cliquez sur **Démarrer** > **Windows PowerShell**.
    
2. Dans la fenêtre **Windows PowerShell**, connectez-vous à votre organisation Office 365 en exécutant :
    
    > [!NOTE]
    > Vous devez seulement exécuter la commande **Import-Module** la première fois que vous utilisez le module Windows PowerShell pour Skype Entreprise Online.
  

    ```PowerShell
    Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
    ```
  
### <a name="create-and-manage-your-dial-plans"></a>Création et gestion de vos plans de numérotation

Vous pouvez utiliser une cmdlet unique ou un script PowerShell pour créer et gérer les plans de numérotation client.
  
#### <a name="using-single-cmdlets"></a>Utilisation d’applets de applet uniques

- Pour créer un plan de numérotation, exécutez :
    
  ```PowerShell
  New-CsTenantDialPlan -Identity RedmondDialPlan -Description "Dial Plan for Redmond" -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9 -SimpleName "Dial-Plan-for-Redmond"
  ```

    Pour obtenir d’autres exemples et des paramètres, consultez la rubrique [New-rubrique Remove](https://docs.microsoft.com/powershell/module/skype/new-cstenantdialplan).
    
- Pour modifier les paramètres d’un plan de numérotation existant, exécutez :
    
  ```PowerShell
  Set-CsTenantDialPlan -Identity RedmondDialPlan  -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9
    -SimpleName "Dial-Plan-for-Redmond"
  ```

    Pour obtenir d’autres exemples et des paramètres, consultez la rubrique [Set-rubrique Remove](https://docs.microsoft.com/powershell/module/skype/set-cstenantdialplan).
    
- Pour ajouter des utilisateurs à un plan de numérotation, exécutez :
    
  ```PowerShell
  Grant-CsTenantDialPlan -Identity amos.marble@contoso.com -PolicyName RedmondDialPlan
  ```

    Pour obtenir d’autres exemples et des paramètres, consultez la rubrique [Grant-rubrique Remove](https://docs.microsoft.com/powershell/module/skype/grant-cstenantdialplan).
    
- Pour afficher les paramètres d’un plan de numérotation, exécutez :
    
  ```PowerShell
  Get-CsTenantDialPlan -Identity RedmondDialPlan
  ```

    Pour obtenir d’autres exemples et des paramètres, consultez la rubrique [Get-rubrique Remove](https://docs.microsoft.com/powershell/module/skype/get-cstenantdialplan?view=skype-ps).
    
- Pour supprimer un plan de numérotation, exécutez :
    
  ```PowerShell
  Remove-CsTenantDialPlan -Identity RedmondDialPlan -force
  ```

    Pour obtenir d’autres exemples et des paramètres, consultez la rubrique [Remove-rubrique Remove](https://docs.microsoft.com/powershell/module/skype/remove-cstenantdialplan?view=skype-ps).
    
- Pour afficher les paramètres du plan de numérotation efficace, exécutez :
    
  ```PowerShell
  Get-CsEffectiveTenantDialPlan -Identity amos.marble@contoso.com
  ```

    Pour obtenir d’autres exemples et des paramètres, consultez la rubrique [Get-CsEffectiveTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/get-cseffectivetenantdialplan).
    
- Pour tester les paramètres efficaces d’un plan de numérotation, exécutez :
    
  ```PowerShell
  Test-CsEffectiveTenantDialPlan -DialedNumber 14255550199 -Identity amos.marble@contoso.com
  ```

    Pour obtenir d’autres exemples et des paramètres, consultez la rubrique [test-CsEffectiveTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/test-cseffectivetenantdialplan?view=skype-ps).
    
#### <a name="using-a-powershell-script"></a>Utilisation d’un script PowerShell

Exécutez l’opération suivante pour supprimer une règle de normalisation associée à un plan de numérotation client sans avoir à supprimer d’abord le plan de numérotation client :
```PowerShell
$b1=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$b1}
(Get-CsTenantDialPlan -Identity RedmondDialPlan).NormalizationRules
$b2=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$b2}
```
Exécutez l’outil pour ajouter la règle de normalisation suivante au plan de numérotation client existant nommé RedmondDialPlan.
```PowerShell
$nr1=New-CsVoiceNormalizationRule -Parent Global -Description 'Organization extension dialing' -Pattern '^(\\d{3})$' -Translation '+14255551$1' -Name NR1 -IsInternalExtension $false -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$nr1}
```
Exécutez cette commande pour supprimer la règle de normalisation suivante du plan de numérotation client existant nommé RedmondDialPlan.
```PowerShell
$nr1=New-CsVoiceNormalizationRule -Parent Global/NR1 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$nr1}
```

Exécutez la commande suivante lorsque vous voulez également examiner les règles de normalisation existantes, déterminer celle que vous voulez supprimer, puis utiliser son index pour la supprimer. Le tableau de règles de normalisation commence par l’index 0. Nous voulons supprimer la règle de normalisation à 3 chiffres, afin qu’il s’agit de l’index 1.
  
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

Exécutez l’outil pour rechercher tous les utilisateurs disposant d’un plan de numérotation client RedmondDialPlan.
  
```PowerShell
Get-CsOnlineUser | Where-Object {$_.TenantDialPlan -eq "RedmondDialPlan"}
```

Exécutez cette opération pour supprimer les TenantDialPlan attribués de tous les utilisateurs disposant d’un HostingProvider de sipfed.online.lync.com.
```PowerShell
Get-CsOnlineUser -Filter {HostingProvider -eq “sipfed.online.lync.com”} | Grant-CsTenantDialPlan -policyname $null
```

Exécutez ces derniers pour ajouter le plan de numérotation local existant intitulé OPDP1 comme plan de numérotation client pour votre organisation. Vous devez d’abord enregistrer le plan de numérotation local dans un fichier. xml, puis l’utiliser pour créer le plan de numérotation client.
  
Exécutez cet enregistrement pour enregistrer le plan de numérotation local au fichier. Xml.
  
```PowerShell
$DPName = "OPDP1"
$DPFileName = "dialplan.xml"
Get-CsDialplan $DPName | Export-Clixml $DPFileName
```

Exécutez cette opération pour créer le plan de numérotation client.
  
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
    
## <a name="related-topics"></a>Voir aussi

- [Qu’est-ce que les plans de numérotation ?](what-are-dial-plans.md)
- [Questions fréquentes à propos du transfert de numéros de téléphone](transferring-phone-numbers-common-questions.md)
- [Différents types de numéros de téléphone utilisés pour les offres d'appel](different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [Gérer des numéros de téléphone pour votre entreprise](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
- [Conditions générales relatives aux appels d'urgence](emergency-calling-terms-and-conditions.md)
- [Libellé d’exclusion d’appel d’urgence](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
- [Aperçu de Teams PowerShell](teams-powershell-overview.md)
