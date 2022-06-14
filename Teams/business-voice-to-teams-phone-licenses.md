---
title: Passer de Business Voice à Teams Téléphone licences
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.localizationpriority: medium
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
description: Découvrez comment modifier vos licences Business Voice pour Teams Téléphone licences.
appliesto:
- Microsoft Teams
ms.openlocfilehash: e9e973d00761e62e62a3c749163f9e6dcaa8a636
ms.sourcegitcommit: e38776625a3623216b0d5f092fffaff67519b1a6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/13/2022
ms.locfileid: "66057094"
---
# <a name="move-from-business-voice-to-teams-phone-licenses"></a>Passer de Business Voice à Teams Téléphone licences

À la fin de juin 2022, Business Voice sera mis hors service. Nous recommandons donc [aux entreprises de passer à Téléphonie Microsoft Teams avec forfait d'appels licences groupées](https://techcommunity.microsoft.com/t5/small-and-medium-business-blog/teams-phone-with-calling-plan-available-in-33-markets-on-january/ba-p/2967643).

Business Voice a regroupé les trois licences de module complémentaire Teams suivantes :

- **Téléphonie Microsoft Teams** pour un Système téléphonique cloud dans Microsoft Teams.
- **Audioconférence** pour les conférences rendez-vous et rendez-vous pour les réunions.
- **Forfaits d’appels Microsoft** pour les appels nationaux à la connectivité RTC (Public Switched Telephone Network).

Les clients Business Voice existants ne sont pas automatiquement transférés vers le nouveau modèle de licence.

Cet article s’adresse aux administrateurs informatiques qui doivent modifier leurs licences Business Voice pour Téléphonie Microsoft Teams et Audioconférence licences tout en conservant les mêmes fonctionnalités.

> [!WARNING]
> Suivez attentivement les instructions de cet article. Si les instructions vous indiquent de NE PAS sélectionner le bouton **Enregistrer** , ne sélectionnez pas le bouton **Enregistrer** .
>
> L’enregistrement prématuré peut entraîner la perte d’affectations de numéros de téléphone, de plans de numérotation, de standards automatiques et de files d’attente d’appels.

## <a name="acquire-new-licenses"></a>Acquérir de nouvelles licences

Avant de remplacer les licences Business Voice, vous devez d’abord acheter des licences de remplacement pour vos utilisateurs.

Vous aurez besoin de licences pour fournir les fonctionnalités suivantes :

- Audioconférence
- Système téléphonique cloud
- Connectivité PSTN

Utilisez le tableau suivant pour déterminer les licences à acheter en fonction de vos besoins :

| Ancien plan de licence | Plan de licence recommandé | Description |
| ---------------- | ------------------------ | ----------- |
| Business Voice avec forfait d’appels | Teams Téléphone avec forfait d’appels et Audioconférence Microsoft Teams avec rendez-vous aux États-Unis/CAN | Fournit des fonctionnalités de Système téléphonique basées sur le cloud, un forfait d’appels nationaux avec Microsoft comme fournisseur RTC, ainsi que des fonctionnalités de connexion et de numérotation pour les participants à la réunion organisées par un utilisateur sous licence. |
| Business Voice sans forfait d’appels | Teams Phone Standard et Audioconférence Microsoft Teams avec rendez-vous aux États-Unis/CAN | Fournit des fonctionnalités de Système téléphonique basées sur le cloud qui peuvent être combinées avec [un plan d’appel tiers avec un fournisseur RTC à l’aide de fonctionnalités de routage Operator Connect ou direct](pstn-connectivity.md), de connexion et de numérotation pour rencontrer des participants organisés par un utilisateur sous licence. |

## <a name="how-to-update-licenses"></a>Comment mettre à jour les licences

Vous avez quatre façons de mettre à jour vos licences :

- Mise à jour des licences mono-utilisateur via Centre d'administration Microsoft 365
- Mise à jour de licence utilisateur en bloc via Centre d'administration Microsoft 365
- Mise à jour de licence utilisateur en bloc à l’aide d’un script PowerShell
- Mise à jour de licence utilisateur en bloc à l’aide de licences basées sur un groupe Azure

# <a name="option-1-single-user-in-admin-center"></a>[Option 1 : Utilisateur unique dans le Centre d’administration](#tab/single-user)

### <a name="option-1-single-user-license-update-via-microsoft-365-admin-center"></a>Option 1 : Mise à jour de la licence utilisateur unique via Centre d'administration Microsoft 365

Pour mettre à jour un seul utilisateur, vous pouvez utiliser le Centre d'administration Microsoft 365.

1. Accédez à [admin.microsoft.com](https://admin.microsoft.com/) et connectez-vous avec les informations d’identification de l’administrateur client.
1. Accédez à **Utilisateurs** > **actifs** et sélectionnez l’utilisateur souhaité.
1. Sélectionnez **Gérer les licences de produit** dans la barre d’outils de liste.
1. Dans l’écran **Licences et applications** , désélectionnez la licence Business Voice.
    > [!IMPORTANT]
    > N’enregistrez pas encore les modifications. Si vous enregistrez les modifications sans ajouter les nouvelles licences, le compte d’utilisateur est déprovisionné et le numéro de téléphone n’est pas attribué.
1. Après avoir désélectionner Business Voice, vérifiez les nouvelles licences Teams Téléphone et Audioconférence.
1. Vous pouvez maintenant enregistrer vos modifications en toute sécurité en sélectionnant **Enregistrer la modification**.

Les licences de l’utilisateur seront mises à jour et ne doivent pas avoir d’impact sur la disponibilité du service.

# <a name="option-2-bulk-users-in-admin-center"></a>[Option 2 : Utilisateurs en bloc dans le Centre d’administration](#tab/bulk-users-admin-center)

### <a name="option-2-bulk-user-license-update-via-microsoft-365-admin-center"></a>Option 2 : Mise à jour en bloc des licences utilisateur via Centre d'administration Microsoft 365

Pour mettre à jour les licences de plusieurs utilisateurs en bloc, vous pouvez utiliser le Centre d'administration Microsoft 365. Les utilisateurs sélectionnés auront la même attribution de plan de licence.

1. Accédez à [admin.microsoft.com](https://admin.microsoft.com/) et connectez-vous avec les informations d’identification de l’administrateur client.
1. Accédez à **Utilisateurs** > **actifs** et sélectionnez tous les utilisateurs souhaités.  
1. Sélectionnez **Gérer les licences de produit** dans la barre d’outils de liste.
1. À l’invite **Que voulez-vous faire avec les licences pour ces utilisateurs ?** Sélectionnez l’option **Remplacer : Annuler l’affectation de licences existantes et attribuer de nouvelles licences** .
    > [!IMPORTANT]
    > L’option **Remplacer** supprime toutes les licences existantes pour les utilisateurs sélectionnés.  Par conséquent, vous devrez sélectionner l’état de licence souhaité pour les utilisateurs, y compris toutes les autres licences utilisées, comme Microsoft 365 Business Premium.
    >
    > En outre, si les utilisateurs sélectionnés ont des configurations de licence de base différentes, ils seront remplacés par vos licences sélectionnées, ce qui peut affecter d’autres zones de Microsoft 365.
    >
    > Pour les locataires disposant d’une configuration de licence mixte, nous vous recommandons d’utiliser [l’option de mise à jour en bloc avec un script PowerShell](#option-3-bulk-user-license-update-using-a-powershell-script).
1. Dans l’écran **Licences et applications** , désélectionnez la licence Business Voice.
    > [!IMPORTANT]
    > N’enregistrez pas encore les modifications. Si vous enregistrez les modifications sans ajouter les nouvelles licences, les comptes des utilisateurs sélectionnés seront déprovisionnés et le numéro de téléphone non attribué.
1. Après avoir désélectionner Business Voice, vérifiez les nouvelles licences Teams Téléphone et Audioconférence.
1. Vous pouvez maintenant enregistrer vos modifications en toute sécurité en sélectionnant **Enregistrer la modification**.
  Les licences des utilisateurs seront mises à jour et ne doivent pas avoir d’impact sur la disponibilité du service.

# <a name="option-3-bulk-users-via-powershell"></a>[Option 3 : Utilisateurs en bloc via PowerShell](#tab/powershell)

### <a name="option-3-bulk-user-license-update-using-a-powershell-script"></a>Option 3 : Mise à jour de licence utilisateur en bloc à l’aide d’un script PowerShell

Le remplacement du plan de licence Business Voice à l’aide d’un script PowerShell est une solution efficace pour la plupart des scénarios.  

Pour utiliser cette méthode, vous allez suivre les étapes générales suivantes :

1. Obtenez les identificateurs de plan de licence spécifiques au locataire de vos licences Business Voice actuelles.
1. Obtenez les identificateurs spécifiques au locataire de vos nouveaux plans de licence Teams Téléphone et Audioconférence.
1. Vérifiez si les nouveaux plans de licence ont les mêmes plans de service que la licence Business Voice actuelle.
1. Recherchez les utilisateurs clients sous licence pour Business Voice (ou modifiez le script pour inclure un filtre pour sélectionner un sous-ensemble d’utilisateurs, si vous le souhaitez).
1. Mettez à jour la configuration des licences des utilisateurs avec des plans Teams Téléphone et Audioconférence.

> [!IMPORTANT]
> Le script fourni est un exemple de code. Le script ne doit pas être copié en l’état et exécuté dans un locataire de production sans test, validation et personnalisation pour votre environnement spécifique.

### <a name="how-to-bulk-update-licenses-using-powershell"></a>Comment mettre à jour des licences en bloc à l’aide de PowerShell

1. Installez et importez le module AzureAD PowerShell.

    ```powershell
    Install-Module AzureAD
    Import-Module AzureAD
    ```

1. Connecter à votre locataire Microsoft 365 et fournissez les informations d’identification d’administrateur du locataire.

    ```powershell
    Connect-AzureAD
    ```

1. Utilisez l’applet de commande suivante pour répertorier tous les packages de licence dans le locataire.

    ```powershell
    Get-AzureADSubscribedSku
    ```

1. Utilisez le tableau suivant pour identifier le plan de licence de module complémentaire Business Voice qui sera remplacé.

    | SKU Code | Type de licence |
    | -------- | ------------ |
    | BUSINESS_VOICE_MED | Voix d’entreprise avec forfait d’appels - Canada |
    | BUSINESS_VOICE | Business Voice avec forfait d’appels - Royaume-Uni |
    | BUSINESS_VOICE_MED2_TELCO | Business Voice avec forfait d’appels - États-Unis |
    | BUSINESS_VOICE_DIRECTROUTING | Business Voice sans forfait d’appels |
    | BUSINESS_VOICE_DIRECTROUTING_MED | Business Voice sans forfait d’appels - États-Unis |

    > [!NOTE]
    > Le script fourni dans ce document part du principe que vous disposez d’une seule référence SKU Code for Business Voice dans votre locataire.  
    >
    > Si vous avez plusieurs références SKU Business Voice, vous devez ajuster le script ou l’exécuter plusieurs fois, une fois pour chaque code de référence SKU.

1. Créez une variable PowerShell nommée `$skuSourceBV`.
    1. Veillez à remplacer l’étiquette par le `SkuPartNumber` code de référence SKU Business Voice de votre locataire.
    1. Dans cet exemple, nous utilisons le code de référence `BUSINESS_VOICE_MED2_TELCO` SKU.

    ```powershell
    $skuSourceBV = Get-AzureADSubscribedSku  | where {$_.SkuPartNumber -eq "BUSINESS_VOICE_MED2_TELCO"}
    ```

1. Utilisez le tableau suivant pour identifier vos nouveaux codes de référence SKU de licence Teams Téléphone et Audioconférence.

    | SKU Code | Type de licence |
    | -------- | ------------ |
    | MCOTEAMS_ESSENTIALS | Téléphone Teams avec forfait d'appel |
    | MCOEV | Teams Phone Standard (aucun forfait d’appels) |
    | MCOMEETADV | Audioconférence |
    | Microsoft_Teams_Audio_Conferencing_select_dial_out | Audioconférence Microsoft Teams sélectionnez Numérotation sortante |

1. Créez des variables PowerShell pour stocker les Teams Téléphone uniques et les codes de référence SKU Audioconférence.
    1. Veillez à remplacer l’étiquette `SkuPartNumber` par les codes de référence SKU que vous avez disponibles dans votre locataire.
    1. Dans cet exemple, nous utilisons les codes et `MCOMEETADV` les `MCOTEAM_ESSENTIALS` codes de référence SKU.

        ```powershell
        $skuTargetTPCP = Get-AzureADSubscribedSku | where {$_.SkuPartNumber -eq "MCOTEAMS_ESSENTIALS"}
        $skuTargetAC = Get-AzureADSubscribedSku | where {$_.SkuPartNumber -eq "MCOMEETADV"} 
        ```

1. Exécutez ce script pour collecter les données de plan de service requises à partir de la référence SKU source dans des objets uniques.

     ```powershell
     $servicePlan_Phone = $skuSourceBV.ServicePlans | where {$_.ServicePlanName.ToString() -like "*EV*"}
    $servicePlan_AC = $skuSourceBV.ServicePlans | where {$_.ServicePlanName.ToString() -like "*MEET*"}
    $servicePlan_CP = $skuSourceBV.ServicePlans | where {$_.ServicePlanName.ToString() -like "*PSTN*"}
    ```

1. Avant de passer à autre chose, vérifiez si la référence SKU source (Business Voice) et les références SKU cibles (Teams Téléphone et Audioconférence) ont les mêmes plans de service inclus.
    1. Une incompatibilité peut déclencher une modification de licence susceptible de perturber les services de voix et d’audioconférence des utilisateurs.
    2. Créez des variables pour vérifier si tous les plans de service de la référence SKU source seront remplacés par le même plan de service cible.

        ```powershell
        $validated_TP = $false
        $validated_AC = $false
        $validated_CP = $false
        ```

    3. Si la licence Business Voice source n’inclut aucun forfait d’appels, ne le recherchez pas.

        ```powershell
        if($skuSourceBV.ServicePlans.Count -eq 2) { $validated_CP = $true }
        ```

    4. Vérifiez si tous les plans de service dans la référence SKU source ont un plan de service correspondant dans la référence SKU cible.

        ```powershell
        For ($i=0; $i -le $skuSourceBV.ServicePlans.Count ; $i++) {
        if($validated_TP -eq $false) { if($skuTargetTP.ServicePlans.Contains($servicePlan_Phone)) { $validated_TP = $true } }
        if($validated_AC -eq $false) { if($skuTargetAC.ServicePlans.Contains($servicePlan_AC)) { $validated_AC = $true } }
        if($validated_CP -eq $false) { if($skuTargetTP.ServicePlans.Contains($servicePlan_CP)) { $validated_CP = $true } }
        }
        ```

    5. S’il manque un plan de service dans la référence SKU cible, vous pouvez interrompre la disponibilité du service pour les utilisateurs et votre script doit arrêter le traitement.

        ```powershell
        if($validated_TP -eq $false ) { Write-Host "Stop updating users because target SKU does not have the same Service Plan for Teams Phone." ; exit }
        if($validated_AC -eq $false ) { Write-Host "Stop updating users because target SKU does not have the same Service Plan for Audio Conferencing." ; exit }
        if($validated_CP -eq $false ) { Write-Host "Stop updating users because target SKU does not have the same Service Plan for Calling Plan." ; exit }
        ```

1. Si tout semble correct, préparez les objets PowerShell pour effectuer les opérations de mise à jour sur les objets utilisateur. Utilisez l’objet `AssignedLicenses` pour cela.

    ```powershell
    $LicenseAddTPCP = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
    $LicenseAddTPCP.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $skuTargetTPCP.SkuPartNumber -EQ).SkuID
    $LicenseAddAC = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
    $LicenseAddAC.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $skuTargetAC.SkuPartNumber -EQ).SkuID
    
    $LicensesToUpdate = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
    $LicensesToUpdate.AddLicenses += ($LicenseAddTPCP)
    $LicensesToUpdate.AddLicenses += ($LicenseAddAC)
    $LicensesToUpdate.RemoveLicenses = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $skuSourceBV.SkuPartNumber -EQ).SkuID
    ```

1. Ensuite, obtenez la liste des utilisateurs auxquels les licences Business Voice sont attribuées et stockez-la dans une liste nommée `$usersLicensedOldSKU`.

    ```powershell
    $usersLicensedOldSKU = New-Object System.Collections.Generic.List[Microsoft.Open.AzureAD.Model.User]
    
    Get-AzureAdUser | ForEach { $BVlicensed=$False ; For ($i=0; $i -le ($_.AssignedLicenses | Measure).Count ; $i++) { If($_.AssignedLicenses[$i].SkuId -eq $skuSourceBV.SkuId) { $BVlicensed=$true } } ; If( $BVlicensed -eq $true) { $usersLicensedOldSKU.Add($_)} }
    ```

1. À présent, à l’aide de la nouvelle liste d’utilisateurs, effectuez une activité de mise à jour pour supprimer les licences Business Voice et ajouter les licences Teams Téléphone et Audioconférence, à l’aide de l’objet ``$LicensesToUpdate`` que vous avez créé précédemment.

    ```powershell
    $usersLicensedOldSKU | ForEach { Set-AzureADUserLicense -ObjectId $_.ObjectId -AssignedLicenses $LicensesToUpdate; Write-Host "Completed Update of user " $_.UserPrincipalName;  }
    ```

> [!NOTE]
> Si vous n’avez pas suffisamment de licences Teams Téléphone et/ou Audioconférence disponibles pour remplacer Business Voice, vous obtenez l’abonnement d’erreur **avec guid de référence SKU qui n’a pas de licence disponible** lors de l’attribution de l’utilisateur dès que le pool de licences est épuisé.

### <a name="full-script"></a>Script complet

```powershell
#Install the AzureAD module when required
Install-Module AzureAD
#Import the AzureAD module so you can use the commandlets
Import-Module AzureAD

#Connect to your tenant
Connect-AzureAD

#When necessary, uncomment and use this commandlet to list all the licenses in the tenant and identify which license packages are required
#Get-AzureADSubscribedSku

##Replace the SKU codes below to match your desired scenario
$skuSourceBV = Get-AzureADSubscribedSku | where {$_.SkuPartNumber -eq "BUSINESS_VOICE_MED2_TELCO"}
$skuTargetTP = Get-AzureADSubscribedSku | where {$_.SkuPartNumber -eq "MCOTEAMS_ESSENTIALS"}
$skuTargetAC = Get-AzureADSubscribedSku | where {$_.SkuPartNumber -eq "MCOMEETADV"}

##Replace the SKU codes below to match your desired scenario
$servicePlan_Phone = $skuSourceBV.ServicePlans | where {$_.ServicePlanName.ToString() -like "*EV*"}
$servicePlan_AC = $skuSourceBV.ServicePlans | where {$_.ServicePlanName.ToString() -like "*MEET*"}
$servicePlan_CP = $skuSourceBV.ServicePlans | where {$_.ServicePlanName.ToString() -like "*PSTN*"}

##Create variables to validate if all Service Plans in the source SKU will be replaced with the same target service plan
$validated_TP = $false
$validated_AC = $false
$validated_CP = $false

##If source Business Voice has no Calling Plan included, do not check
if($skuSourceBV.ServicePlans.Count -eq 2) { $validated_CP = $true }

##Verify if all service plans in source SKU have a matching service plan in target SKU
For ($i=0; $i -le $skuSourceBV.ServicePlans.Count ; $i++) { 
    if($validated_TP -eq $false) { if($skuTargetTP.ServicePlans.Contains($servicePlan_Phone)) { $validated_TP = $true } }
    if($validated_AC -eq $false) { if($skuTargetAC.ServicePlans.Contains($servicePlan_AC)) { $validated_AC = $true } }
    if($validated_CP -eq $false) { if($skuTargetTP.ServicePlans.Contains($servicePlan_CP)) { $validated_CP = $true } }
}

##If there's a missing service plan in the target sku, we might impact service availability for a user and therefore stop processing
if($validated_TP -eq $false ) { Write-Host "Stop updating users because target SKU does not have the same Service Plan for Teams Phone." ; exit } 
if($validated_AC -eq $false ) { Write-Host "Stop updating users because target SKU does not have the same Service Plan for Audio Conferencing." ; exit } 
if($validated_CP -eq $false ) { Write-Host "Stop updating users because target SKU does not have the same Service Plan for Calling Plan." ; exit } 


##Prepare variables and update
$LicenseAddTP = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$LicenseAddTP.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $skuTargetTP.SkuPartNumber -EQ).SkuID
$LicenseAddAC = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$LicenseAddAC.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $skuTargetAC.SkuPartNumber -EQ).SkuID
$LicensesToUpdate = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$LicensesToUpdate.AddLicenses += ($LicenseAddTP)
$LicensesToUpdate.AddLicenses += ($LicenseAddAC)
$LicensesToUpdate.RemoveLicenses = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $skuSourceBV.SkuPartNumber -EQ).SkuID

$usersLicensedOldSKU = New-Object System.Collections.Generic.List[Microsoft.Open.AzureAD.Model.User]
Get-AzureAdUser | ForEach { $BVlicensed=$False ; For ($i=0; $i -le ($_.AssignedLicenses | Measure).Count ; $i++) { If($_.AssignedLicenses[$i].SkuId -eq $skuSourceBV.SkuId) { $BVlicensed=$true } } ; If( $BVlicensed -eq $true) { $usersLicensedOldSKU.Add($_)} }

$usersLicensedOldSKU | ForEach { Set-AzureADUserLicense -ObjectId $_.ObjectId -AssignedLicenses $LicensesToUpdate; Write-Host "Completed Update of user " $_.UserPrincipalName;  }
```

# <a name="option-4-bulk-users-with-azure-group-based-licensing"></a>[Option 4 : Utilisateurs en bloc avec licences basées sur un groupe Azure](#tab/azure-licensing)

### <a name="option-4-bulk-user-license-update-using-azure-group-based-licensing"></a>Option 4 : Mise à jour en bloc des licences utilisateur à l’aide de licences basées sur un groupe Azure

La gestion des licences basées sur un groupe Azure vous permet d’attribuer des abonnements et des plans de service à un groupe.

Cette méthode garantit que :

- Les licences sont attribuées à tous les membres du groupe.
- Les nouveaux membres qui rejoignent le groupe bénéficient des licences appropriées.
- Lorsque des membres sont supprimés du groupe, ces licences sont également supprimées.

Vous devrez valider les exigences de [licence pour les licences basées sur un groupe](/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal).

> [!NOTE]
> Pour cette méthode, les mises à jour de licence doivent être traitées en une seule étape.
>
> Nous vous recommandons de compiler une liste des groupes existants auxquels des licences Business Voice sont attribuées, de sélectionner d’abord un petit groupe d’utilisateurs de test et de remplacer l’attribution de plan de licence par les nouveaux plans de licence préférés.

### <a name="how-to-bulk-update-licenses-using-group-based-licensing"></a>Comment mettre à jour des licences en bloc à l’aide de licences basées sur un groupe

1. Accédez à [portal.azure.com](https://portal.azure.com) et connectez-vous avec les informations d’identification de l’administrateur.
1. Accédez à **Azure Active Directory** et dans le menu de gauche, sélectionnez **Licences**.
1. Pour vérifier quels groupes ont des licences Business Voice affectées, choisissez **Tous les produits** et sélectionnez le plan Business Voice.
1. Sélectionnez **Groupes sous licence** ou **utilisateurs sous licence**. Vous trouverez la liste des groupes sous licence dans le volet droit.
1. Sélectionnez le nom du groupe pour ouvrir les détails de l’attribution de groupe.
1. Sélectionnez **Affectations** pour modifier les licences attribuées à ce groupe.
1. Cochez les cases devant les plans de licence que vous avez acquis pour remplacer Business Voice.
1. Décochez la case devant le plan de licence Microsoft 365 Business Voice.
1. Sélectionnez **Enregistrer**.
1. Revenez au groupe en sélectionnant le nom du groupe. Vous verrez une bannière indiquant que **des modifications de licence sont en attente**.
1. Sélectionnez **Retraiter** pour forcer la mise à jour de l’attribution de licence.

---

## <a name="validate-user-license-updates"></a>Valider les mises à jour des licences utilisateur

Une fois que vous avez terminé la méthode choisie, vérifiez si les licences utilisateur ont été correctement mises à jour.

1. Accédez à la [Centre d'administration Microsoft 365](https://admin.microsoft.com) et connectez-vous avec les informations d’identification de l’administrateur.
1. Accédez à **Utilisateurs** > **actifs** et sélectionnez un utilisateur de test.
1. Sélectionnez **Gérer les licences de produit** dans la barre d’outils.
1. Dans l’écran **Licences et applications** , examinez les licences qui leur ont été attribuées.

Si les licences appropriées sont attribuées à tous les utilisateurs ciblés, vous avez terminé la mise à jour de vos licences Business Voice pour Teams Téléphone et Audioconférence licences.
