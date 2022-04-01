---
title: Utiliser PowerShell pour gérer votre connexion Shifts à Blue Yonder Workforce Management
author: LanaChin
ms.author: v-lanachin
ms.reviewer: ''
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Découvrez comment utiliser PowerShell pour gérer votre connexion Shifts à Blue Yonder Workforce Management.
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: e666117b31064697f9ef41299574935109015aba
ms.sourcegitcommit: 2388838163812eeabcbd5331aaf680b79da3ccba
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2022
ms.locfileid: "64593642"
---
# <a name="use-powershell-to-manage-your-shifts-connection-to-blue-yonder-workforce-management"></a>Utiliser PowerShell pour gérer votre connexion Shifts à Blue Yonder Workforce Management

## <a name="overview"></a>Vue d’ensemble

Le [Microsoft Teams Shifts pour Blue Yonder](shifts-connectors.md#microsoft-teams-shifts-connector-for-blue-yonder) vous permet d’intégrer l’application Shifts dans Microsoft Teams avec Blue Yonder Workforce Management (Blue Yonder WFM). Une fois que vous avez établi une connexion, vos employés en contact direct peuvent consulter et gérer leurs plannings en toute transparence dans Blue Yonder WFM à partir de Shifts.

Vous pouvez utiliser [l’Assistant Connecteur Shifts](shifts-connector-wizard.md) du Centre d'administration Microsoft 365 [powershell](shifts-connector-blue-yonder-powershell-setup.md) pour configurer une connexion. Une fois la connexion définie, vous pouvez la gérer à l’aide des [cmdlets PowerShell du connecteur Shifts](#shifts-connector-cmdlets).

Cet article décrit comment utiliser PowerShell pour :

- [Vérifier l’état de la configuration de la connexion](#check-connection-setup-status)
- [Afficher un rapport d’erreurs pour une connexion](#view-an-error-report-for-a-connection)
- [Résoudre les erreurs de connexion](#resolve-connection-errors)
- [Modifier les paramètres de connexion](#change-connection-settings)
- [Démaser une équipe d’une connexion et la maapper à une autre connexion](#unmap-a-team-from-one-connection-and-map-it-to-another-connection)
- [Désactiver la synchronisation d’une connexion](#disable-sync-for-a-connection)

> [!NOTE]
> Cet article part du principe que vous avez déjà installé une connexion à Blue Yonder WFM, à l’aide de l’Assistant ou de PowerShell.

## <a name="before-you-begin"></a>Avant de commencer

[!INCLUDE [shifts-connector-admin-role](../../includes/shifts-connector-admin-role.md)]

## <a name="set-up-your-environment"></a>Configuration de votre environnement

> [!NOTE]
> Veillez à suivre ces étapes pour configurer votre environnement avant d’exécutez les commandes ou scripts décrits dans cet article.

[!INCLUDE [shifts-connector-set-up-environment](../../includes/shifts-connector-set-up-environment.md)]

## <a name="check-connection-setup-status"></a>Vérifier l’état de la configuration de la connexion
<a name="setup_status"> </a>

Pour vérifier l’état de la connexion que vous avez définie à l’aide de l’ID d’opération reçu par courrier électronique :

1. [Configurer votre environnement](#set-up-your-environment) (si ce n’est déjà fait).
1. Exécutez la commande suivante. Cette commande vous donne l’état global des mappages d’équipe pour la connexion.

    ``` powershell
    Get-CsTeamsShiftsConnectionOperation -OperationId <YourOperationId>
    ```

Pour en savoir plus, [consultez Get-CsTeamsShiftsConnectionOperation](/powershell/module/teams/get-csteamsshiftsconnectionoperation?view=teams-ps).

## <a name="view-an-error-report-for-a-connection"></a>Afficher un rapport d’erreurs pour une connexion
<a name="error_report"> </a>

Vous pouvez exécuter un état qui affiche les détails d’erreur d’une connexion. Le rapport répertorie les mappages d’équipes et d’utilisateurs qui ont réussi et échoué. Il fournit également des informations sur les problèmes liés aux comptes associés à la connexion.

1. [Configurer votre environnement](#set-up-your-environment) (si ce n’est déjà fait).
1. Obtenez une liste des rapports d’erreur pour une connexion.

    ``` powershell
    Get-CsTeamsShiftsConnectionErrorReport -ConnectorInstanceId <ConnectorInstanceId>
    ```

1. Pour afficher un rapport d’erreurs spécifique, exécutez la commande suivante :

    ``` powershell
    Get-CsTeamsShiftsConnectionErrorReport -ErrorReportId <ErrorReportId>
    ```

Pour en savoir plus, [consultez Get-CsTeamsShiftsConnectionErrorReport](/powershell/module/teams/get-csteamsshiftsconnectionerrorreport?view=teams-ps).

## <a name="resolve-connection-errors"></a>Résoudre les erreurs de connexion

### <a name="user-mapping-errors"></a>Erreurs de mappage des utilisateurs

Des erreurs de mappage d’utilisateurs peuvent se produire si un ou plusieurs utilisateurs d’un site Blue Yonder WFM n’est pas membre de l’équipe mappée dans Teams. Pour résoudre ce problème, assurez-vous que les utilisateurs de l’équipe mappée correspondent aux utilisateurs du site Blue Yonder WFM.

Pour afficher les détails des utilisateurs non mis en [place,](#set-up-your-environment) définissez votre environnement (si vous ne l’avez pas déjà fait), puis exécutez le script suivant.

```powershell
#View sync errors script 
Write-Host "View sync errors"
Start-Sleep 1

#Ensure Teams module is of version x 
Write-Host "Checking Teams module version"
try {
    Get-InstalledModule -Name "MicrosoftTeams" -MinimumVersion 4.1.0
} catch {
    throw
}

#Authenticate with powershell as to the authorization capabilities of the caller. 
#Connect to Teams
Write-Host "Connecting to Teams"
Connect-MicrosoftTeams
Write-Host "Connected"

#List connection instances available 
Write-Host "Listing connection instances"
$InstanceList = Get-CsTeamsShiftsConnectionInstance
write $InstanceList

#Get an instance
if ($InstanceList.Count -gt 0){
    $InstanceId = Read-Host -Prompt 'Input the instance ID that you want to retrieve user sync results from'
}
else {
    throw "Instance list is empty"
}

#Get a list of the mappings
Write-Host "Listing team mappings"
$mappings = Get-CsTeamsShiftsConnectionTeamMap -ConnectorInstanceId $InstanceId
write $mappings

#For each mapping, retrieve the failed mappings
ForEach ($mapping in $mappings){
    $teamsTeamId = $mapping.TeamId
    $wfmTeamId = $mapping.WfmTeamId
    Write-Host "Failed mapped users in the mapping of ${teamsTeamId} and ${wfmTeamId}:"
    $userSyncResult = Get-CsTeamsShiftsConnectionSyncResult -ConnectorInstanceId $InstanceId -TeamId $teamsTeamId
    Write-Host "Failed AAD users:"
    write $userSyncResult.FailedAadUser
    Write-Host "Failed WFM users:"
    write $userSyncResult.FailedWfmUser
}
```

### <a name="account-authorization-errors"></a>Erreurs d’autorisation de compte

Des erreurs d’autorisation de compte peuvent se produire si les informations d’identification du service Blue Yonder WFM ou Microsoft 365 système sont incorrectes ou ne sont pas autorisées.

Pour modifier vos informations d’identification système ou de Microsoft 365 compte système Blue Yonder WFM pour la connexion, vous pouvez exécuter l’cmdlet [Set-CsTeamsShiftsConnectionInstance](/powershell/module/teams/set-csteamsshiftsconnectioninstance?view=teams-ps) ou utiliser le script PowerShell dans la section Modifier les [paramètres](#change-connection-settings) de connexion de cet article.

## <a name="change-connection-settings"></a>Modifier les paramètres de connexion
<a name="change_settings"> </a>

Utilisez ce script pour modifier les paramètres de connexion. Paramètres que vous pouvez modifier incluent votre compte de service Blue Yonder WFM et votre mot de passe, votre Microsoft 365 système, vos mappages d’équipe et vos paramètres de synchronisation.

Les paramètres de synchronisation incluent la fréquence de synchronisation (en minutes) et les données de planification synchronisées entre Blue Yonder WFM et Shifts. Les données de planification sont définies dans les paramètres suivants, que vous pouvez afficher en exécutant [Get-CsTeamsShiftsConnectionConnector](/powershell/module/teams/get-csteamsshiftsconnectionconnector?view=teams-ps).

- Le **paramètre enabledConnectorScenarios** définit les données synchronisées entre Blue Yonder WFM et Shifts. Les options sont `SwapRequest`, , `UserShiftPreferences`, `OpenShift`, `OpenShiftRequest`, `TimeOffRequest``TimeOff`.`Shift`
- Le **paramètre enabledWfiScenarios** définit les données synchronisées entre Shifts et Blue Yonder WFM. Les options sont `SwapRequest`, `OpenShiftRequest`, `TimeOffRequest`. `UserShiftPreferences`

    > [!NOTE]
    > Si vous choisissez de ne pas synchroniser les shifts ouverts, les demandes de shift ouvertes, les demandes d’échange ou les demandes de congé entre Shifts et Blue Yonder WFM, vous devez faire une autre étape pour masquer la fonctionnalité dans Shifts. Après avoir exécuté ce script, veillez à suivre les étapes de la section Désactiver les [shifts ouverts,](#disable-open-shifts-open-shifts-requests-swap-requests-and-time-off-requests) ouvrir les demandes de shift, les demandes d’échange et les demandes de congé plus loin dans cet article.

> [!IMPORTANT]
> Pour les paramètres que vous ne voulez pas modifier, vous devez entrer de nouveau les paramètres d’origine lorsque vous y êtes invité par le script.

[Définissez votre environnement](#set-up-your-environment) (si ce n’est déjà fait), puis exécutez le script suivant.

```powershell
#Update connector instance and mapping script
Write-Host "Update connector instance and mapping"
Start-Sleep 1

#Ensure Teams module is at least version x
Write-Host "Checking Teams module version"
try {
    Get-InstalledModule -Name "MicrosoftTeams" -MinimumVersion 4.1.0
} catch {
    throw
}

#Authenticate with powershell as to the authorization capabilities of the caller. 
#Connect to Teams
Write-Host "Connecting to Teams"
Connect-MicrosoftTeams
Write-Host "Connected"

#Connect to MS Graph
Connect-MgGraph -Scopes "User.Read.All","Group.ReadWrite.All"

#List connector types available (comment out if not implemented for preview) 
Write-Host "Listing connector types available"
$BlueYonderId = "6A51B888-FF44-4FEA-82E1-839401E9CD74"
$connectors = Get-CsTeamsShiftsConnectionConnector
write $connectors
$blueYonder = $connectors | where {$_.Id -match $BlueYonderId}

#List connection instances available
Write-Host "Listing connection instances available"
$InstanceList = Get-CsTeamsShiftsConnectionInstance
write $InstanceList

#Prompt for the WFM username and password 
$WfmUserName = Read-Host -Prompt 'Input your WFM user name'
$WfmPwd = Read-Host -Prompt 'Input your WFM password' -AsSecureString
$plainPwd =[Runtime.InteropServices.Marshal]::PtrToStringAuto([Runtime.InteropServices.Marshal]::SecureStringToBSTR($WfmPwd))

#Get the instance ID
$BlueYonderId = "6A51B888-FF44-4FEA-82E1-839401E9CD74"
$InstanceId = Read-Host -Prompt 'Input the instance ID that you want to update'
$Instance = Get-CsTeamsShiftsConnectionInstance -ConnectorInstanceId $InstanceId
$Etag = $Instance.etag

#Change sync setting
$designatorName = Read-Host -Prompt "Input designated actor's user name"
$designator = Get-MgUser -UserId $designatorName
$teamsUserId = $designator.Id
$UpdatedInstanceName = Read-Host -Prompt 'Input new connection instance name'
$updatedConnectorScenarioString = Read-Host -Prompt 'Input new enabled connector scenarios'
$updatedWfiScenarioString = Read-Host -Prompt 'Input new enabled WFI scenarios'
$Delimiters = ",", ".", ":", ";", " ", "`t"
$updatedConnectorScenario = $updatedConnectorScenarioString -Split {$Delimiters -contains $_}
$updatedConnectorScenario = $updatedConnectorScenario.Trim()
$updatedConnectorScenario = $updatedConnectorScenario.Split('',[System.StringSplitOptions]::RemoveEmptyEntries)
$updatedWfiScenario = $updatedWfiScenarioString -Split {$Delimiters -contains $_}
$updatedWfiScenario = $updatedWfiScenario.Trim()
$updatedWfiScenario = $updatedWfiScenario.Split('', [System.StringSplitOptions]::RemoveEmptyEntries)
$adminApiUrl = $Instance.ConnectorSpecificSettingAdminApiUrl
$cookieAuthUrl = $Instance.ConnectorSpecificSettingCookieAuthUrl
$essApiUrl = $Instance.ConnectorSpecificSettingEssApiUrl
$federatedAuthUrl = $Instance.ConnectorSpecificSettingFederatedAuthUrl
$retailWebApiUrl = $Instance.ConnectorSpecificSettingRetailWebApiUrl
$siteManagerUrl = $Instance.ConnectorSpecificSettingSiteManagerUrl
$syncFreq = Read-Host -Prompt 'Input new sync frequency'

#Read admin email list
[psobject[]]$AdminEmailList = @()
while ($true){
$AdminEmail = Read-Host -Prompt "Enter admin's email to receive error report"
$AdminEmailList += $AdminEmail
$title    = 'Adding another email'
$question = 'Would you like to add another admin email?'
$choices  = '&Yes', '&No'
$decision = $Host.UI.PromptForChoice($title, $question, $choices, 1)
if ($decision -eq 1) {
    break
}
}
$UpdatedInstance = Set-CsTeamsShiftsConnectionInstance -ConnectorId $BlueYonderId -ConnectorInstanceId $InstanceId -ConnectorSpecificSettingAdminApiUrl $adminApiUrl -ConnectorSpecificSettingCookieAuthUrl $cookieAuthUrl -ConnectorSpecificSettingEssApiUrl $essApiUrl -ConnectorSpecificSettingFederatedAuthUrl $federatedAuthUrl -ConnectorSpecificSettingLoginPwd $plainPwd -ConnectorSpecificSettingLoginUserName $WfmUserName -ConnectorSpecificSettingRetailWebApiUrl $retailWebApiUrl -ConnectorSpecificSettingSiteManagerUrl $siteManagerUrl -DesignatedActorId $teamsUserId -EnabledConnectorScenario $updatedConnectorScenario -EnabledWfiScenario $updatedWfiScenario -Name $UpdatedInstanceName -SyncFrequencyInMin $syncFreq -IfMatch $Etag -ConnectorAdminEmail $AdminEmailList

#Get a list of the mappings
Write-Host "Listing mappings"
$TeamMaps = Get-CsTeamsShiftsConnectionTeamMap -ConnectorInstanceId $InstanceId
write $TeamMaps

#Modify a mapping
#Remove a mapping 
Write-Host "Removing a mapping"
$TeamsTeamId = Read-Host -Prompt 'Input the Teams team ID that you want to unlink'
$WfmTeamId = Read-Host -Prompt 'Input the WFM team ID that you want to unlink'
Remove-CsTeamsShiftsConnectionTeamMap -ConnectorInstanceId $InstanceId -TeamId $TeamsTeamId
Write-Host "Success"

#Add a mapping 
Write-Host "Adding a mapping"
$TeamsTeamId = Read-Host -Prompt 'Input the Teams team ID that you want to link'
$WfmTeamId = Read-Host -Prompt 'Input the WFM team ID that you want to link'
New-CsTeamsShiftsConnectionTeamMap -ConnectorInstanceId $InstanceId -TeamId $TeamsTeamId -TimeZone "America/Los_Angeles" -WfmTeamId $WfmTeamId
Write-Host "Success"
```

## <a name="disable-open-shifts-open-shifts-requests-swap-requests-and-time-off-requests"></a>Désactiver les shifts ouverts, les demandes de shift ouvertes, les demandes d’échange et les demandes de congé

> [!IMPORTANT]
> Suivez ces étapes uniquement si vous choisissez de désactiver les shifts ouverts, les demandes de shift ouvertes, les demandes d’échange ou les demandes de congé à l’aide du script de la section Modifier les [paramètres](#change-connection-settings) de connexion plus haut dans cet article ou à l’aide de la cmdlet [Set-CsTeamsShiftsConnectionInstance](/powershell/module/teams/set-csteamsshiftsconnectioninstance?view=teams-ps) . L’exécution de cette étape masque la fonctionnalité dans Shifts. Sans cette deuxième étape, les utilisateurs continueront de voir la fonctionnalité dans Shifts et un message d’erreur « Opération non pris en place » s’ils essaient de l’utiliser.

Pour masquer les shifts, demandes d’échange et de congé ouverts dans Shifts, utilisez le type de ressource API Graph [Schedule](/graph/api/resources/schedule?view=graph-rest-1.0) pour définir les paramètres suivants ```false``` pour chaque équipe mappée vers un site Blue Yonder WFM :

- Shifts ouverts : ```openShiftsEnabled```
- Demandes d’échange :  ```swapShiftsRequestsEnabled```
- Demandes de congé : ```timeOffRequestsEnabled```

Pour masquer les demandes de shifts ouverts dans Shifts,  Paramètres dans Shifts, puis désactiver le paramètre **Ouvrir les shifts**.

## <a name="unmap-a-team-from-one-connection-and-map-it-to-another-connection"></a>Démaser une équipe d’une connexion et la maapper à une autre connexion

> [!NOTE]
> Le Microsoft 365 système de données doit être identique pour les deux connexions. Si ce n’est pas le cas, un message d’erreur « Ce profil désigné d’actor ne a pas de privilèges de propriété d’équipe » s’agit.

Si vous souhaitez démaser une équipe d’une connexion et la maapper à une autre connexion :

1. [Configurer votre environnement](#set-up-your-environment) (si ce n’est déjà fait).
1. Afficher la liste de tous les mappages d’équipe pour une connexion.

    ```powershell
    Get-CsTeamsShiftsConnectionTeamMap -ConnectorInstanceId <ConnectorInstanceId>
    ```

1. Supprimez un mappage d’équipe de la connexion.

    ```powershell
    Remove-CsTeamsShiftsConnectionTeamMap -ConnectorInstanceId <ConnectorInstanceId> -TeamId <TeamId>
    ```

1. Masiquez l’équipe sur une autre connexion.

    ```powershell
    New-CsTeamsShiftsConnectionTeamMap -ConnectorInstanceId <ConnectorInstanceId> -TeamId <TeamId> -WfmTeamId <SiteId> -TimeZone <TimeZone>
    ```

Pour en savoir plus, voir [Get-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/get-csteamsshiftsconnectionteammap?view=teams-ps), [Remove-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/remove-csteamsshiftsconnectionteammap?view=teams-ps) et [New-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/new-csteamsshiftsconnectionteammap?view=teams-ps).

## <a name="disable-sync-for-a-connection"></a>Désactiver la synchronisation d’une connexion

Utilisez ce script pour désactiver la synchronisation pour une connexion. N’oubliez pas que ce script ne supprime ni ne supprime de connexion. Elle a pour effet de couper la synchronisation de sorte qu’aucune donnée ne soit synchronisée entre Shifts et Blue Yonder WFM pour la connexion que vous spécifiez.

[Définissez votre environnement](#set-up-your-environment) (si ce n’est déjà fait), puis exécutez le script suivant.

```powershell
#Disable sync script
Write-Host "Disable sync"
#Ensure Teams module is at least version x
Write-Host "Checking Teams module version"
try {
    Get-InstalledModule -Name "MicrosoftTeams" -MinimumVersion 4.1.0
} catch {
    throw
}

#Authenticate with powershell as to the authorization capabilities of the caller. 
#Connect to Teams
Write-Host "Connecting to Teams"
Connect-MicrosoftTeams
Write-Host "Connected"

#List connection instances available 
Write-Host "Listing connection instances"
$InstanceList = Get-CsTeamsShiftsConnectionInstance
write $InstanceList

#Get an instance
if ($InstanceList.Count -gt 0){
    $InstanceId = Read-Host -Prompt 'Input the instance ID that you want to disable sync'
    $Instance = Get-CsTeamsShiftsConnectionInstance -ConnectorInstanceId $InstanceId
    $Etag = $Instance.etag
    $InstanceName = $Instance.Name
    $DesignatedActorId = $Instance.designatedActorId
    $adminApiUrl = $Instance.ConnectorSpecificSettingAdminApiUrl
    $cookieAuthUrl = $Instance.ConnectorSpecificSettingCookieAuthUrl
    $essApiUrl = $Instance.ConnectorSpecificSettingEssApiUrl
    $federatedAuthUrl = $Instance.ConnectorSpecificSettingFederatedAuthUrl
    $retailWebApiUrl = $Instance.ConnectorSpecificSettingRetailWebApiUrl
    $siteManagerUrl = $Instance.ConnectorSpecificSettingSiteManagerUrl
    $ConnectorAdminEmail = $Instance.ConnectorAdminEmail
}
else {
    throw "Instance list is empty"
}

#Remove scenarios in the mapping
Write-Host "Disabling scenarios in the team mapping"
$UpdatedInstanceName = $InstanceName + " - Disabled"
$BlueYonderId = "6A51B888-FF44-4FEA-82E1-839401E9CD74"
$WfmUserName = Read-Host -Prompt 'Input your WFM user name'
$WfmPwd = Read-Host -Prompt 'Input your WFM password' -AsSecureString
$plainPwd =[Runtime.InteropServices.Marshal]::PtrToStringAuto([Runtime.InteropServices.Marshal]::SecureStringToBSTR($WfmPwd))

$UpdatedInstance = Set-CsTeamsShiftsConnectionInstance -ConnectorId $BlueYonderId -ConnectorInstanceId $InstanceId -ConnectorSpecificSettingAdminApiUrl $adminApiUrl -ConnectorSpecificSettingCookieAuthUrl $cookieAuthUrl -ConnectorSpecificSettingEssApiUrl $essApiUrl -ConnectorSpecificSettingFederatedAuthUrl $federatedAuthUrl -ConnectorSpecificSettingLoginPwd $plainPwd -ConnectorSpecificSettingLoginUserName $WfmUserName -ConnectorSpecificSettingRetailWebApiUrl $retailWebApiUrl -ConnectorSpecificSettingSiteManagerUrl $siteManagerUrl -DesignatedActorId $DesignatedActorId -EnabledConnectorScenario @() -EnabledWfiScenario @() -Name $UpdatedInstanceName -SyncFrequencyInMin 60 -IfMatch $Etag -ConnectorAdminEmail $ConnectorAdminEmail

if ($UpdatedInstance.Id -ne $null) {
    Write-Host "Success"
}
else {
    throw "Update instance failed"
}
```

## <a name="shifts-connector-cmdlets"></a>Cmdlets de connecteur Shifts

Pour obtenir de l’aide sur les cmdlets de connecteur Shifts, recherchez **CsTeamsShiftsConnection** dans la [Teams de l’cmdlet PowerShell](/powershell/teams/intro?view=teams-ps). Voici des liens vers des cmdlets fréquemment utilisées.

- [Get-CsTeamsShiftsConnectionOperation](/powershell/module/teams/get-csteamsshiftsconnectionoperation?view=teams-ps)
- [New-CsTeamsShiftsConnectionInstance](/powershell/module/teams/new-csteamsshiftsconnectioninstance?view=teams-ps)
- [Get-CsTeamsShiftsConnectionInstance](/powershell/module/teams/get-csteamsshiftsconnectioninstance?view=teams-ps)
- [Set-CsTeamsShiftsConnectionInstance](/powershell/module/teams/set-csteamsshiftsconnectioninstance?view=teams-ps)
- [Remove-CsTeamsShiftsConnectionInstance](/powershell/module/teams/remove-csteamsshiftsconnectioninstance?view=teams-ps)
- [Test-CsTeamsShiftsConnectionValidate](/powershell/module/teams/test-csteamsshiftsconnectionvalidate?view=teams-ps)
- [New-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/new-csteamsshiftsconnectionteammap?view=teams-ps)
- [Get-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/get-csteamsshiftsconnectionteammap?view=teams-ps)
- [Remove-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/remove-csteamsshiftsconnectionteammap?view=teams-ps)
- [Get-CsTeamsShiftsConnectionConnector](/powershell/module/teams/get-csteamsshiftsconnectionconnector?view=teams-ps)
- [Get-CsTeamsShiftsConnectionSyncResult](/powershell/module/teams/get-csteamsshiftsconnectionsyncresult?view=teams-ps)
- [Get-CsTeamsShiftsConnectionWfmUser](/powershell/module/teams/get-csteamsshiftsconnectionwfmuser?view=teams-ps)
- [Get-CsTeamsShiftsConnectionWfmTeam](/powershell/module/teams/get-csteamsshiftsconnectionwfmteam?view=teams-ps)
- [Get-CsTeamsShiftsConnectionErrorReport](/powershell/module/teams/get-csteamsshiftsconnectionerrorreport?view=teams-ps)
- [Remove-CsTeamsShiftsScheduleRecord](/powershell/module/teams/remove-csteamsshiftsschedulerecord?view=teams-ps)

## <a name="related-articles"></a>Articles connexes

- [Connecteurs Shifts](shifts-connectors.md)
- [Utiliser l’Assistant Connecteur Shifts pour connecter Shifts à Blue Yonder Workforce Management](shifts-connector-wizard.md)
- [Utiliser PowerShell pour connecter Shifts à Blue Yonder Workforce Management](shifts-connector-blue-yonder-powershell-setup.md)
- [Gérer l’application Shifts](manage-the-shifts-app-for-your-organization-in-teams.md)
- [Présentation de Teams PowerShell](../../teams-powershell-overview.md)