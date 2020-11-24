---
title: Configurer le composant additionnel de réunion Microsoft teams pour Google Workspace
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
description: Apprenez à configurer le composant additionnel pour les réunions Microsoft teams pour Google Workspace.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9c86d707a4298d88d3ae0cff389bda73490390e4
ms.sourcegitcommit: 882ed439f8bba27b1cf0c14056c146267cacd359
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/24/2020
ms.locfileid: "49387287"
---
# <a name="set-up-microsoft-teams-meeting-add-on-for-google-workspace"></a>Configurer le composant additionnel de réunion Microsoft teams pour Google Workspace

L’utilisation du composant additionnel réunion Microsoft teams permet aux utilisateurs du calendrier Google de programmer et de rejoindre une réunion Microsoft teams directement dans Google Workspace. Les utilisateurs pourront accéder aux fonctionnalités de réunion en équipe, notamment les conférences vidéo et audio, le partage d’écran, les discussions de la réunion, les tableaux blancs numériques, etc. Restez connecté et organisé pour une collaboration plus approfondie au sein de votre entreprise, de votre école et de votre vie.

Pour pouvoir accéder à l’application, le composant additionnel de réunion Microsoft teams pour Google Workspace doit être activé par un administrateur d’équipes.

## <a name="enable-or-disable-microsoft-teams-meeting-add-on-for-google-workspace-in-the-azure-portal"></a>Activer ou désactiver le composant additionnel de réunion Microsoft teams pour Google Workspace dans le portail Azure

En tant qu’administrateur client, vous pouvez activer ou désactiver un composant additionnel de réunion Microsoft teams pour Google Workspace à partir du compte d’administrateur de votre organisation à l’aide du portail Azure.

L’extension est activée par défaut.

1. Connectez-vous au portail Azure.

2. Sélectionnez **applications d’entreprise**  >  **toutes les applications**.

3. Recherchez **le composant additionnel pour les réunions Microsoft teams pour Google Workspace**.

   ![Portail Azure affichant toutes les applications](media/aad-add-google-workspace.png)

4. Sélectionnez **Oui**.

   ![Portail Azure affichant les propriétés Google Workspace](media/google-workspace-properties.png)

5. Facultatif Pour désactiver le module complémentaire, sélectionnez **non** à la place de **Oui** à l’étape 4.

## <a name="disable-microsoft-teams-meeting-add-on-for-google-workspace-using-powershell"></a>Désactiver le composant additionnel de réunion Microsoft teams pour Google Workspace à l’aide de PowerShell

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

Pour plus d’informations, consultez [créer un principal de service Azure avec Azure PowerShell](https://docs.microsoft.com/powershell/azure/create-azure-service-principal-azureps?view=azps-5.0.0).

## <a name="delete-the-microsoft-teams-meeting-add-on-for-google-workspace"></a>Supprimer le composant additionnel pour la réunion Microsoft teams pour Google Workspace

Pour obtenir des instructions, reportez-vous à la documentation Google [supprimer une application Google Workspace Marketplace](https://support.google.com/a/answer/6216211?hl=en) .
