---
title: Configurer le module add-on de réunion Microsoft Teams pour Google Workspace
author: cichur
ms.author: v-cichur
ms.reviewer: aravin
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
searchScope:
- Microsoft Teams
search.appverid: MET150
description: Découvrez comment configurer le module add-on de réunion Microsoft Teams pour Google Workspace.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6e1b7024190ac51b89e09fafced86ffea13f5961
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120695"
---
# <a name="set-up-microsoft-teams-meeting-add-on-for-google-workspace"></a>Configurer le module add-on de réunion Microsoft Teams pour Google Workspace

L’utilisation du module logiciel Microsoft Teams permet aux utilisateurs de calendrier Google de planifier et de rejoindre une réunion Microsoft Teams directement à partir de Google Workspace. Les utilisateurs auront accès aux fonctionnalités de réunions Teams, notamment à la vidéoconférence et à l’audioconférence, au partage d’écran, aux discussions de réunion, aux tableaux blancs numériques, etc. Restez connecté et organisé pour être encore plus efficace au sein de votre vie professionnelle, scolaire et personnelle.

Pour que les utilisateurs clients peuvent accéder à l’application, le module ajout de réunion Microsoft Teams pour Google Workspace doit être activé par un administrateur Teams.

## <a name="enable-or-disable-microsoft-teams-meeting-add-on-for-google-workspace-in-the-azure-portal"></a>Activer ou désactiver le module add-on de réunion Microsoft Teams pour Google Workspace dans le portail Azure

En tant qu’administrateur client, vous pouvez activer ou désactiver un module add-on de réunion Microsoft Teams pour Google Workspace à partir du compte d’administrateur de votre organisation à l’aide du portail Azure.

L’option d’ajout est activée par défaut.

1. Connectez-vous au portail Azure.

2. Sélectionnez **Applications d’entreprise**  >  **Toutes les applications.**

3. Recherchez **le module ajouté à une réunion Microsoft Teams pour Google Workspace.**

   ![Portail Azure affichant toutes les applications](media/aad-add-google-workspace.png)

4. Sélectionnez **Oui.**

   ![Portail Azure affichant les propriétés de l’espace de travail Google](media/google-workspace-properties.png)

5. (Facultatif) Pour désactiver l’module ajouté, sélectionnez **Non** au lieu de **Oui** à l’étape 4.

## <a name="disable-microsoft-teams-meeting-add-on-for-google-workspace-using-powershell"></a>Désactiver le module add-on de réunion Microsoft Teams pour Google Workspace à l’aide de PowerShell

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
    $servicePrincipal = New-AzureADServicePrincipal -AppId $appId -DisplayName $displayName -AccountEnabled $false
    Write-Host "Created and disabled the Service Principal \n"
}
```

Pour plus d’informations, [voir Créer un principal de service Azure avec Azure PowerShell.](/powershell/azure/create-azure-service-principal-azureps?view=azps-5.0.0)

## <a name="delete-the-microsoft-teams-meeting-add-on-for-google-workspace"></a>Supprimer le module ajouté à la réunion Microsoft Teams pour Google Workspace

Voir la documentation Google [Supprimer une application Google Workspace Marketplace pour](https://support.google.com/a/answer/6216211?hl=en) obtenir des instructions.