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
# <a name="set-up-microsoft-teams-meeting-add-on-for-google-workspace"></a><span data-ttu-id="2e5f3-103">Configurer le module add-on de réunion Microsoft Teams pour Google Workspace</span><span class="sxs-lookup"><span data-stu-id="2e5f3-103">Set up Microsoft Teams meeting add-on for Google Workspace</span></span>

<span data-ttu-id="2e5f3-104">L’utilisation du module logiciel Microsoft Teams permet aux utilisateurs de calendrier Google de planifier et de rejoindre une réunion Microsoft Teams directement à partir de Google Workspace.</span><span class="sxs-lookup"><span data-stu-id="2e5f3-104">Using the Microsoft Teams meeting add-on lets Google calendar users schedule and join a Microsoft Teams meeting directly from Google Workspace.</span></span> <span data-ttu-id="2e5f3-105">Les utilisateurs auront accès aux fonctionnalités de réunions Teams, notamment à la vidéoconférence et à l’audioconférence, au partage d’écran, aux discussions de réunion, aux tableaux blancs numériques, etc.</span><span class="sxs-lookup"><span data-stu-id="2e5f3-105">Users will get access to Teams meetings features including video and audio conferencing, screen sharing, meeting chat, digital whiteboards, and more.</span></span> <span data-ttu-id="2e5f3-106">Restez connecté et organisé pour être encore plus efficace au sein de votre vie professionnelle, scolaire et personnelle.</span><span class="sxs-lookup"><span data-stu-id="2e5f3-106">Stay connected and organized to get more done together across work, school, and life.</span></span>

<span data-ttu-id="2e5f3-107">Pour que les utilisateurs clients peuvent accéder à l’application, le module ajout de réunion Microsoft Teams pour Google Workspace doit être activé par un administrateur Teams.</span><span class="sxs-lookup"><span data-stu-id="2e5f3-107">The Microsoft Teams meeting add-on for Google Workspace must be enabled by a Teams admin before tenant users can access the app.</span></span>

## <a name="enable-or-disable-microsoft-teams-meeting-add-on-for-google-workspace-in-the-azure-portal"></a><span data-ttu-id="2e5f3-108">Activer ou désactiver le module add-on de réunion Microsoft Teams pour Google Workspace dans le portail Azure</span><span class="sxs-lookup"><span data-stu-id="2e5f3-108">Enable or disable Microsoft Teams meeting add-on for Google Workspace in the Azure portal</span></span>

<span data-ttu-id="2e5f3-109">En tant qu’administrateur client, vous pouvez activer ou désactiver un module add-on de réunion Microsoft Teams pour Google Workspace à partir du compte d’administrateur de votre organisation à l’aide du portail Azure.</span><span class="sxs-lookup"><span data-stu-id="2e5f3-109">As a tenant administrator, you can enable or disable a Microsoft Teams meeting add-on for Google Workspace from your organization's admin account using the Azure portal.</span></span>

<span data-ttu-id="2e5f3-110">L’option d’ajout est activée par défaut.</span><span class="sxs-lookup"><span data-stu-id="2e5f3-110">The add-on is enabled by default.</span></span>

1. <span data-ttu-id="2e5f3-111">Connectez-vous au portail Azure.</span><span class="sxs-lookup"><span data-stu-id="2e5f3-111">Sign in to the Azure portal.</span></span>

2. <span data-ttu-id="2e5f3-112">Sélectionnez **Applications d’entreprise**  >  **Toutes les applications.**</span><span class="sxs-lookup"><span data-stu-id="2e5f3-112">Select **Enterprise applications** > **All applications**.</span></span>

3. <span data-ttu-id="2e5f3-113">Recherchez **le module ajouté à une réunion Microsoft Teams pour Google Workspace.**</span><span class="sxs-lookup"><span data-stu-id="2e5f3-113">Search for **Microsoft Teams meeting add-on for Google Workspace**.</span></span>

   ![Portail Azure affichant toutes les applications](media/aad-add-google-workspace.png)

4. <span data-ttu-id="2e5f3-115">Sélectionnez **Oui.**</span><span class="sxs-lookup"><span data-stu-id="2e5f3-115">Select **Yes**.</span></span>

   ![Portail Azure affichant les propriétés de l’espace de travail Google](media/google-workspace-properties.png)

5. <span data-ttu-id="2e5f3-117">(Facultatif) Pour désactiver l’module ajouté, sélectionnez **Non** au lieu de **Oui** à l’étape 4.</span><span class="sxs-lookup"><span data-stu-id="2e5f3-117">(Optional) To disable the add-on, select **No** instead of **Yes** in Step 4.</span></span>

## <a name="disable-microsoft-teams-meeting-add-on-for-google-workspace-using-powershell"></a><span data-ttu-id="2e5f3-118">Désactiver le module add-on de réunion Microsoft Teams pour Google Workspace à l’aide de PowerShell</span><span class="sxs-lookup"><span data-stu-id="2e5f3-118">Disable Microsoft Teams meeting add-on for Google Workspace using PowerShell</span></span>

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

<span data-ttu-id="2e5f3-119">Pour plus d’informations, [voir Créer un principal de service Azure avec Azure PowerShell.](/powershell/azure/create-azure-service-principal-azureps?view=azps-5.0.0)</span><span class="sxs-lookup"><span data-stu-id="2e5f3-119">For more information, see [Create an Azure service principal with Azure PowerShell](/powershell/azure/create-azure-service-principal-azureps?view=azps-5.0.0).</span></span>

## <a name="delete-the-microsoft-teams-meeting-add-on-for-google-workspace"></a><span data-ttu-id="2e5f3-120">Supprimer le module ajouté à la réunion Microsoft Teams pour Google Workspace</span><span class="sxs-lookup"><span data-stu-id="2e5f3-120">Delete the Microsoft Teams meeting add-on for Google Workspace</span></span>

<span data-ttu-id="2e5f3-121">Voir la documentation Google [Supprimer une application Google Workspace Marketplace pour](https://support.google.com/a/answer/6216211?hl=en) obtenir des instructions.</span><span class="sxs-lookup"><span data-stu-id="2e5f3-121">See the Google documentation [Delete a Google Workspace Marketplace app](https://support.google.com/a/answer/6216211?hl=en) for instructions.</span></span>