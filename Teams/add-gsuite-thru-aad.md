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
# <a name="set-up-microsoft-teams-meeting-add-on-for-google-workspace"></a><span data-ttu-id="c1fe7-103">Configurer le composant additionnel de réunion Microsoft teams pour Google Workspace</span><span class="sxs-lookup"><span data-stu-id="c1fe7-103">Set up Microsoft Teams meeting add-on for Google Workspace</span></span>

<span data-ttu-id="c1fe7-104">L’utilisation du composant additionnel réunion Microsoft teams permet aux utilisateurs du calendrier Google de programmer et de rejoindre une réunion Microsoft teams directement dans Google Workspace.</span><span class="sxs-lookup"><span data-stu-id="c1fe7-104">Using the Microsoft Teams meeting add-on lets Google calendar users schedule and join a Microsoft Teams meeting directly from Google Workspace.</span></span> <span data-ttu-id="c1fe7-105">Les utilisateurs pourront accéder aux fonctionnalités de réunion en équipe, notamment les conférences vidéo et audio, le partage d’écran, les discussions de la réunion, les tableaux blancs numériques, etc.</span><span class="sxs-lookup"><span data-stu-id="c1fe7-105">Users will get access to Teams meetings features including video and audio conferencing, screen sharing, meeting chat, digital whiteboards, and more.</span></span> <span data-ttu-id="c1fe7-106">Restez connecté et organisé pour une collaboration plus approfondie au sein de votre entreprise, de votre école et de votre vie.</span><span class="sxs-lookup"><span data-stu-id="c1fe7-106">Stay connected and organized to get more done together across work, school, and life.</span></span>

<span data-ttu-id="c1fe7-107">Pour pouvoir accéder à l’application, le composant additionnel de réunion Microsoft teams pour Google Workspace doit être activé par un administrateur d’équipes.</span><span class="sxs-lookup"><span data-stu-id="c1fe7-107">The Microsoft Teams meeting add-on for Google Workspace must be enabled by a Teams admin before tenant users can access the app.</span></span>

## <a name="enable-or-disable-microsoft-teams-meeting-add-on-for-google-workspace-in-the-azure-portal"></a><span data-ttu-id="c1fe7-108">Activer ou désactiver le composant additionnel de réunion Microsoft teams pour Google Workspace dans le portail Azure</span><span class="sxs-lookup"><span data-stu-id="c1fe7-108">Enable or disable Microsoft Teams meeting add-on for Google Workspace in the Azure portal</span></span>

<span data-ttu-id="c1fe7-109">En tant qu’administrateur client, vous pouvez activer ou désactiver un composant additionnel de réunion Microsoft teams pour Google Workspace à partir du compte d’administrateur de votre organisation à l’aide du portail Azure.</span><span class="sxs-lookup"><span data-stu-id="c1fe7-109">As a tenant administrator, you can enable or disable a Microsoft Teams meeting add-on for Google Workspace from your organization's admin account using the Azure portal.</span></span>

<span data-ttu-id="c1fe7-110">L’extension est activée par défaut.</span><span class="sxs-lookup"><span data-stu-id="c1fe7-110">The add-on is enabled by default.</span></span>

1. <span data-ttu-id="c1fe7-111">Connectez-vous au portail Azure.</span><span class="sxs-lookup"><span data-stu-id="c1fe7-111">Sign in to the Azure portal.</span></span>

2. <span data-ttu-id="c1fe7-112">Sélectionnez **applications d’entreprise**  >  **toutes les applications**.</span><span class="sxs-lookup"><span data-stu-id="c1fe7-112">Select **Enterprise applications** > **All applications**.</span></span>

3. <span data-ttu-id="c1fe7-113">Recherchez **le composant additionnel pour les réunions Microsoft teams pour Google Workspace**.</span><span class="sxs-lookup"><span data-stu-id="c1fe7-113">Search for **Microsoft Teams meeting add-on for Google Workspace**.</span></span>

   ![Portail Azure affichant toutes les applications](media/aad-add-google-workspace.png)

4. <span data-ttu-id="c1fe7-115">Sélectionnez **Oui**.</span><span class="sxs-lookup"><span data-stu-id="c1fe7-115">Select **Yes**.</span></span>

   ![Portail Azure affichant les propriétés Google Workspace](media/google-workspace-properties.png)

5. <span data-ttu-id="c1fe7-117">Facultatif Pour désactiver le module complémentaire, sélectionnez **non** à la place de **Oui** à l’étape 4.</span><span class="sxs-lookup"><span data-stu-id="c1fe7-117">(Optional) To disable the add-on, select **No** instead of **Yes** in Step 4.</span></span>

## <a name="disable-microsoft-teams-meeting-add-on-for-google-workspace-using-powershell"></a><span data-ttu-id="c1fe7-118">Désactiver le composant additionnel de réunion Microsoft teams pour Google Workspace à l’aide de PowerShell</span><span class="sxs-lookup"><span data-stu-id="c1fe7-118">Disable Microsoft Teams meeting add-on for Google Workspace using PowerShell</span></span>

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

<span data-ttu-id="c1fe7-119">Pour plus d’informations, consultez [créer un principal de service Azure avec Azure PowerShell](https://docs.microsoft.com/powershell/azure/create-azure-service-principal-azureps?view=azps-5.0.0).</span><span class="sxs-lookup"><span data-stu-id="c1fe7-119">For more information, see [Create an Azure service principal with Azure PowerShell](https://docs.microsoft.com/powershell/azure/create-azure-service-principal-azureps?view=azps-5.0.0).</span></span>

## <a name="delete-the-microsoft-teams-meeting-add-on-for-google-workspace"></a><span data-ttu-id="c1fe7-120">Supprimer le composant additionnel pour la réunion Microsoft teams pour Google Workspace</span><span class="sxs-lookup"><span data-stu-id="c1fe7-120">Delete the Microsoft Teams meeting add-on for Google Workspace</span></span>

<span data-ttu-id="c1fe7-121">Pour obtenir des instructions, reportez-vous à la documentation Google [supprimer une application Google Workspace Marketplace](https://support.google.com/a/answer/6216211?hl=en) .</span><span class="sxs-lookup"><span data-stu-id="c1fe7-121">See the Google documentation [Delete a Google Workspace Marketplace app](https://support.google.com/a/answer/6216211?hl=en) for instructions.</span></span>
