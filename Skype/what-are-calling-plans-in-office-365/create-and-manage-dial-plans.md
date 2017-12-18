---
title: "Créer et gérer des plans de numérotation"
ms.author: tonysmit
author: tonysmit
ms.date: 11/10/2017
ms.audience: Admin
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.custom: Strat_SB_PSTN
ms.assetid: 7af17c94-5f8f-4452-ae1d-01f495b4dc94
description: "Learn how to create calling dial plans (PSTN Calling dial plans) in Office 365 and how to manage them. "
---

# Créer et gérer des plans de numérotation

> [!IMPORTANT]
> Cet article a été traduit automatiquement, voir l'avertissement.  
  
Après avoir planifiée plans de numérotation pour votre organisation et maîtrisez toutes les règles de normalisation qui doivent être créés pour le routage d'appel, vous devrez utiliser Windows PowerShell pour créer des plans de numérotation et apportez les modifications de paramètre.
  
> [!NOTE]
> Vous ne pouvez pas utiliser le Centre d'administration de Skype Entreprise pour créer et gérer des plans de numérotation. 
  
## Vérification et démarrage de la session PowerShell distante

 **Vérifiez que vous exécutez la version 3.0 ou une version ultérieure de Windows PowerShell**
  
1. Pour vérifier que vous exécutez la version 3.0 ou une version ultérieure : **Menu Démarrer** > **Windows PowerShell**.
    
2. Consultez la version en entrant  _Get-Host_ dans la fenêtre **Windows PowerShell**.
    
3. Si vous n'utilisez pas la version 3.0 ou une version ultérieure, vous devez télécharger et installer les mises à jour de Windows PowerShell. Pour télécharger et mettre à jour Windows PowerShell vers la version 4.0, consultez [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845). Redémarrez votre ordinateur lorsque vous y êtes invité.
    
4. Vous devrez également installer le module Windows PowerShell pour Skype Entreprise Online qui vous permet de créer une session Windows PowerShell distante qui se connecte à Skype Entreprise Online. Ce module, pris en charge uniquement sur les ordinateurs 64 bits, peut être téléchargé sur le centre de téléchargement de Microsoft à la page [Module Windows PowerShell pour Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=294688). Redémarrez votre ordinateur si vous y êtes invité.
    
Pour en savoir plus, voir [Se connecter à tous les services Office 365 dans une fenêtre Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx).
  
 **Démarrez une session Windows PowerShell**
  
1. Dans le **menu Démarrer**, recherchez **Windows PowerShell**.
    
2. Dans la fenêtre **Windows PowerShell**, connectez-vous à votre organisation Office 365 en exécutant :
    
    > [!NOTE]
    > Vous devez seulement exécuter la commande **Import-Module** la première fois que vous utilisez le module Windows PowerShell pour Skype Entreprise Online.
  
> 
  ```
  Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
  ```

> 
  ```
  $credential = Get-Credential
  ```

> 
  ```
  $session = New-CsOnlineSession -Credential $credential
  ```

> 
  ```
  Import-PSSession $session
  ```

Pour plus d'informations sur le démarrage de Windows PowerShell, voir [Se connecter à tous les services Office 365 dans une fenêtre Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx) ou[Connexion à Skype Entreprise Online à l'aide de Windows PowerShell](https://technet.microsoft.com/library/dn362795%28v=ocs.15%29.aspx).
  
## Création et gestion de vos plans de numérotation

Vous pouvez utiliser une applet de commande unique ou un script PowerShell pour créer et gérer des plans de numérotation.
  
### Utilisation d'applets de commande uniques

- Pour créer un plan de numérotation, exécutez :
    
  ```
  New-CsTenantDialPlan -Identity RedmondDialPlan -Description "Dial Plan for Redmond" -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9 -SimpleName "Dial-Plan-for-Redmond"
  ```

    Pour obtenir d'autres exemples et des paramètres, consultez la rubrique [New-CsTenantDialPlan](https://technet.microsoft.com/library/mt775026.aspx).
    
- Pour apporter des modifications du paramétrage à un plan de numérotation existant, exécutez :
    
  ```
  Set-CsTenantDialPlan -Identity RedmondDialPlan  -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9
    -SimpleName "Dial-Plan-for-Redmond"
  ```

    Pour obtenir d'autres exemples et des paramètres, consultez la rubrique [Set-CsTenantDialPlan](https://technet.microsoft.com/library/mt775023.aspx).
    
- Pour ajouter des utilisateurs à un plan de numérotation, exécutez :
    
  ```
  Grant-CsTenantDialPlan -Identity amos.marble@contoso.com -PolicyName RedmondDialPlan
  ```

    Pour obtenir d'autres exemples et des paramètres, consultez la rubrique [Grant-CsTenantDialPlan](https://technet.microsoft.com/library/mt775021.aspx).
    
- Pour afficher les paramètres sur un plan de numérotation, exécutez :
    
  ```
  Get-CsTenantDialPlan -Identity RedmondDialPlan
  ```

    Pour obtenir d'autres exemples et des paramètres, consultez la rubrique[Get-CsTenantDialPlan](https://technet.microsoft.com/library/mt775024.aspx).
    
- Pour supprimer un plan de numérotation, exécutez :
    
  ```
  Remove-CsTenantDialPlan -Identity RedmondDialPlan -force
  ```

    Pour obtenir d'autres exemples et des paramètres, consultez la rubrique [Remove-CsTenantDialPlan](https://technet.microsoft.com/library/mt775020.aspx).
    
- Pour afficher les paramètres de plan de numérotation efficace, exécutez :
    
  ```
  Get-CsEffectiveTenantDialPlan -Identity amos.marble@contoso.com
  ```

    Pour obtenir d'autres exemples et des paramètres, consultez la rubrique [Get-CsEffectiveTenantDialPlan](https://technet.microsoft.com/library/mt775022.aspx).
    
- Pour tester les paramètres efficaces d'un plan de numérotation, exécutez :
    
  ```
  Test-CsEffectiveTenantDialPlan -DialedNumber 14255551234 -Identity 1849827b-a810-40a8-8f77-e94250d4680b_US_TenantDialPlanRedmond
  ```

    Pour obtenir d'autres exemples et des paramètres, consultez la rubrique [Test-CsEffectiveTenantDialPlan](https://technet.microsoft.com/library/mt775025.aspx).
    
### Utilisation d'un script PowerShell

Exécutez l'élément suivant pour supprimer une règle de normalisation associée à un plan de numérotation client sans devoir supprimer ce plan au préalable :
  
```
$b1=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
```

```
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$b1}
```

```
(Get-CsTenantDialPlan -Identity RedmondDialPlan).NormalizationRules
```

```
$b2=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
```

```
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$b2}
```

Exécuter cette option pour ajouter la règle de normalisation suivante pour le plan de numérotation client existant nommé RedmondDialPlan.
  
```
$nr1=New-CsVoiceNormalizationRule -Parent Global -Description 'Organization extension dialing' -Pattern '^(\\d{3})$' -Translation '+14255551$1' -Name NR1 -IsInternalExtension $false -InMemory
```

```
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$nr1}
```

Exécutez l'élément suivant pour supprimer la règle de normalisation suivante du plan de numérotation client existant nommé RedmondDialPlan.
  
```
$nr1=New-CsVoiceNormalizationRule -Parent Global/NR1 -InMemory
```

```
Set-CsTenantDialPlan -Identity DP1 -NormalizationRules @{remove=$nr1}
```

Exécutez la commande suivante lorsque vous souhaitez également examiner les règles de normalisation existante et déterminer celle que vous souhaitez supprimer puis utiliser son index pour la supprimer. Le tableau des règles de normalisation commence par index 0. Nous aimerions supprimer la règle de normalisation 3 chiffres, pour qu'elle soit index 1.
  
```
Get-CsTenantDialPlan RedmondDialPlan).NormalizationRules
```

```
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
```

```
$nr1=(Get-CsTenantDialPlan RedmondDialPlan).NormalizationRules[1]
```

```
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$nr1}
```

Exécutez l'élément suivant pour rechercher tous les utilisateurs disposant d'un plan de numérotation client RedmondDialPlan.
  
```
Get-CsOnlineuser | where-Object {$_.TenantDialPlan -eq "RedmondDialPlan"}
```

Exécuter ces pour ajouter que nommée OPDP1 sous forme d'un plan de numérotation client pour votre organisation de plan de numérotation de l'existant en local. Vous devez tout d'abord enregistrer la locale plan vers un fichier .xml de numérotation, puis utilisez-le pour créer le plan de numérotation client.
  
Exécutez cette macro pour enregistrer le plan de numérotation en local dans le fichier .xml.
  
```
$DPName = "OPDP1"
```

```
$DPFileName = "dialplan.xml"
```

```
Get-CsDialplan $DPName | Export-Clixml $DPFileName
```

Exécutez l'élément suivant pour créer le plan de numérotation client.
  
```
$DPFileName = "dialplan.xml"
```

```
$DP = Import-Clixml $DPFileName
```

```
$NormRules = @()
```

```
ForEach($nr in $dp.NormalizationRules)
```

```
{
```

```
 $id1 = "Global/" +$nr.Name
```

```
$nr2 = New-CsVoiceNormalizationRule -Identity $id1 -Description $nr.Description -Pattern $nr.Pattern -Translation $nr.Translation  -IsInternalExtension $nr.IsInternalExtension -InMemory
```

```
$NormRules += $nr2
```

```
}
```

```
New-CsTenantDialPlan -Identity $dp.SimpleName -ExternalAccessPrefix $dp.ExternalAccessPrefix -Description $dp.Description -OptimizeDeviceDialing $dp.OptimizeDeviceDialing -SimpleName $dp.SimpleName -NormalizationRules $NormRules
```

## Vous souhaitez en savoir plus sur Windows PowerShell ?

- Windows PowerShell permet de gérer les utilisateurs et ce qu'ils sont autorisés ou non à faire. Avec Windows PowerShell, vous pouvez gérer Office 365 et Skype Entreprise Online à l'aide d'un point d'administration central qui peut simplifier votre travail quotidien, lorsque vous devez effectuer plusieurs tâches. Pour prendre en main Windows PowerShell, consultez ces rubriques :
    
  - [Présentation de Windows PowerShell et Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Six raisons d'utiliser Windows PowerShell pour gérer Office 365 ](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell offre de nombreux avantages en matière de rapidité, de simplicité et de productivité par rapport à l'utilisation du centre d'administration Office 365 uniquement, par exemple lorsque vous modifiez des paramètres pour un grand nombre d'utilisateurs en même temps. Découvrez ces avantages dans les rubriques suivantes :
    
  - [Meilleures méthodes de gestion d'Office 365 avec Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Utilisation de Windows PowerShell pour gérer Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Avertissement traduction automatique**: cet article a été traduit par un ordinateur, sans intervention humaine. Microsoft propose cette traduction automatique pour offrir aux personnes ne maîtrisant pas l'anglais l'accès au contenu relatif aux produits, services et technologies Microsoft. Comme cet article a été traduit automatiquement, il risque de contenir des erreurs de grammaire, de syntaxe ou de terminologie.
  

