---
title: Configurer le Microsoft Teams de réunion pour Google Workspace
author: SerdarSoysal
ms.author: serdars
ms.reviewer: aravin
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
searchScope:
- Microsoft Teams
search.appverid: MET150
description: Découvrez comment configurer le Microsoft Teams de réunion pour Google Workspace.
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b93fecea83a4fb44a19f490af514626a0d17f3ff
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62388986"
---
# <a name="set-up-microsoft-teams-meeting-add-on-for-google-workspace"></a>Configurer le Microsoft Teams de réunion pour Google Workspace

L’Microsoft Teams à une réunion permet aux utilisateurs de Google Agenda de planifier et de Microsoft Teams réunion directement à partir de Google Workspace. Les utilisateurs ont accès aux Teams fonctionnalités de réunion, notamment les vidéoconférences et audioconférences, le partage d’écran, la conversation de réunion, les tableaux blancs numériques, etc. Restez connecté et organisé pour être encore plus efficace au sein de votre travail, de votre école et de votre vie.

Le Microsoft Teams de réunion pour Google Workspace doit être activé par un administrateur de Teams pour que les utilisateurs clients peuvent accéder à l’application.

## <a name="enable-or-disable-microsoft-teams-meeting-add-on-for-google-workspace-in-the-azure-portal"></a>Activer ou désactiver le Microsoft Teams de réunion pour Google Workspace dans le portail Azure

En tant qu’administrateur client, vous pouvez activer ou désactiver un module Microsoft Teams réunion pour Google Workspace à partir du compte d’administrateur de votre organisation à l’aide du portail Azure.

L’option d’ajout est activée par défaut.

1. Connectez-vous au portail Azure.

2. Sélectionnez **Enterprise applicationsAll** >  **applications**.

3. Recherchez **Microsoft Teams le module-module de réunion pour Google Workspace**.

   ![Portail Azure affichant toutes les applications.](media/aad-add-google-workspace.png)

4. **Sélectionnez Oui**.

   ![Portail Azure affichant les propriétés de l’espace de travail Google.](media/google-workspace-properties.png)

5. (Facultatif) Pour désactiver l’module ajouté, sélectionnez **Non** au lieu de **Oui** à l’étape 4.

## <a name="disable-microsoft-teams-meeting-add-on-for-google-workspace-using-powershell"></a>Désactiver le Microsoft Teams de réunion pour Google Workspace à l’aide de PowerShell

```powershell
Connect-AzureAD

$displayName = 'Microsoft Teams meeting add-on for Google Workspace'
$appId = '7969c887-ba98-48bb-8832-6c9239929d7c'

# Check if a service principal already exists for the app
$servicePrincipal = Get-AzureADServicePrincipal -Filter "appId eq '$appId'"
if ($servicePrincipal) {
    # Service principal exists already, disable it
    Set-AzureADServicePrincipal -ObjectId $servicePrincipal.ObjectId -AccountEnabled $false
    Write-Host "Disabled existing Service Principal \n"
} else {
    # Service principal does not yet exist, create it and disable it at the same time
    New-AzureADServicePrincipal -AppId $appId -DisplayName $displayName
    Get-AzureADServicePrincipal -Filter "appId eq '$appId'" | Set-AzureADServicePrincipal -AccountEnabled:$false
    Write-Host "Created and disabled the Service Principal \n"
}
```

Pour plus d’informations, [voir Créer un principal de service Azure avec Azure PowerShell](/powershell/azure/create-azure-service-principal-azureps?view=azps-5.0.0).

## <a name="delete-the-microsoft-teams-meeting-add-on-for-google-workspace"></a>Supprimer le Microsoft Teams de réunion pour Google Workspace

Voir la documentation Google [Supprimer une application Google Workspace Marketplace pour](https://support.google.com/a/answer/6216211?hl=en) obtenir des instructions.

## <a name="create-the-microsoft-teams-meeting-add-on-for-google-workspace-using-powershell"></a>Créer le Microsoft Teams de réunion pour Google Workspace à l’aide de PowerShell

Si le module Microsoft Teams à une réunion n’est pas présent dans votre client, vous pouvez le créer à l’aide de PowerShell : 

```powershell
Connect-AzureAD

$displayName = 'Microsoft Teams meeting add-on for Google Workspace'
$appId = '7969c887-ba98-48bb-8832-6c9239929d7c'

# Check if a service principal already exists for the app
$servicePrincipal = Get-AzureADServicePrincipal -Filter "appId eq '$appId'"
if ($servicePrincipal) {
    # Service principal exists already
    Write-Host "The Service principal already exists"
} else {
    # Service principal does not yet exist, create it
    New-AzureADServicePrincipal -AppId $appId -DisplayName $displayName
    Write-Host "Created the Service Principal"
}
```
