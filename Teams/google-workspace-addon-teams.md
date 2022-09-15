---
title: Configurer le module complémentaire de réunion Microsoft Teams pour Google Workspace
ms.author: mabond
author: mkbond007
ms.reviewer: aravin
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
searchScope:
- Microsoft Teams
search.appverid: MET150
description: Découvrez comment configurer le module complémentaire de réunion Microsoft Teams pour Google Workspace.
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0bd6897b770215af75862438996a365acd463c96
ms.sourcegitcommit: 424b14534aa269bb408c97c368102a193b481656
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/14/2022
ms.locfileid: "67706641"
---
# <a name="set-up-microsoft-teams-meeting-add-on-for-google-workspace"></a>Configurer le module complémentaire de réunion Microsoft Teams pour Google Workspace

L’utilisation du module complémentaire de réunion Microsoft Teams permet aux utilisateurs du calendrier Google de planifier et de participer à une réunion Microsoft Teams directement à partir de Google Workspace. Les utilisateurs auront accès aux fonctionnalités des réunions Teams, notamment la vidéo et l’audioconférence, le partage d’écran, la conversation de réunion, les tableaux blancs numériques, etc. Restez connecté et organisé pour faire plus ensemble au travail, à l’école et dans la vie.

Le module complémentaire de réunion Microsoft Teams pour Google Workspace doit être activé par un administrateur Teams pour que les utilisateurs locataires puissent accéder à l’application.

## <a name="enable-or-disable-microsoft-teams-meeting-add-on-for-google-workspace-in-the-azure-portal"></a>Activer ou désactiver le module complémentaire de réunion Microsoft Teams pour Google Workspace dans le Portail Azure

En tant qu’administrateur client, vous pouvez activer ou désactiver un module complémentaire de réunion Microsoft Teams pour Google Workspace à partir du compte d’administrateur de votre organisation à l’aide de la Portail Azure.

Le module complémentaire est activé par défaut.

1. Connectez-vous au Portail Azure.

2. Sélectionnez **Applications d’entreprise** > **Toutes les applications**.

3. Recherchez le **module complémentaire de réunion Microsoft Teams pour Google Workspace**.

   ![Portail Azure montrant toutes les applications.](media/aad-add-google-workspace.png)

4. Sélectionnez **Oui**.

   ![Portail Azure montrant les propriétés de l’espace de travail Google.](media/google-workspace-properties.png)

5. (Facultatif) Pour désactiver le module complémentaire, sélectionnez **Non** au lieu de **Oui** à l’étape 4.

## <a name="disable-microsoft-teams-meeting-add-on-for-google-workspace-using-powershell"></a>Désactiver le module complémentaire de réunion Microsoft Teams pour Google Workspace à l’aide de PowerShell

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

Pour plus d’informations, consultez [Créer un principal de service Azure avec Azure PowerShell](/powershell/azure/create-azure-service-principal-azureps?view=azps-5.0.0).

## <a name="delete-the-microsoft-teams-meeting-add-on-for-google-workspace"></a>Supprimer le module complémentaire de réunion Microsoft Teams pour Google Workspace

Pour obtenir des instructions, consultez la documentation Google [Supprimer une application Google Workspace Marketplace](https://support.google.com/a/answer/6216211?hl=en) .

## <a name="create-the-microsoft-teams-meeting-add-on-for-google-workspace-using-powershell"></a>Créer le module complémentaire de réunion Microsoft Teams pour Google Workspace à l’aide de PowerShell

Si le module complémentaire de réunion Microsoft Teams n’est pas présent dans votre locataire, vous pouvez le créer à l’aide de PowerShell : 

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
