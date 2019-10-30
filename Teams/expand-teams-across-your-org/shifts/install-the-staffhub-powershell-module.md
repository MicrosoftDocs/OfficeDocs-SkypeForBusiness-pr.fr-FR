---
title: Installer le module PowerShell Microsoft StaffHub
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Découvrez comment installer le module Microsoft StaffHub PowerShell et vous y connecter.
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: ef80290e6b8a1ce4de834a000148d60b2c5ef89d
ms.sourcegitcommit: 7d5dd650480ca2e55c24ce30408a5058067f6932
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/29/2019
ms.locfileid: "37775073"
---
# <a name="install-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="9c1ce-103">Installer le module PowerShell Microsoft StaffHub</span><span class="sxs-lookup"><span data-stu-id="9c1ce-103">Install the Microsoft StaffHub PowerShell module</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9c1ce-104">À compter du 31 décembre 2019, Microsoft StaffHub sera supprimé.</span><span class="sxs-lookup"><span data-stu-id="9c1ce-104">Effective December 31, 2019, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="9c1ce-105">Nous développons des fonctionnalités StaffHub dans Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="9c1ce-105">We’re building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="9c1ce-106">Aujourd’hui, teams inclut l’application Shifts pour la gestion des plannings et des fonctionnalités supplémentaires seront déployées dans le temps.</span><span class="sxs-lookup"><span data-stu-id="9c1ce-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="9c1ce-107">StaffHub s’arrêtera de fonctionner pour tous les utilisateurs du 31 décembre 2019.</span><span class="sxs-lookup"><span data-stu-id="9c1ce-107">StaffHub will stop working for all users on December 31, 2019.</span></span> <span data-ttu-id="9c1ce-108">Tout utilisateur essayant d’ouvrir StaffHub verra s’afficher un message lui indiquant de télécharger Teams.</span><span class="sxs-lookup"><span data-stu-id="9c1ce-108">Anyone who tries to open StaffHub will be shown a message directing them to download Teams.</span></span> <span data-ttu-id="9c1ce-109">Pour en savoir plus, consultez la rubrique [Microsoft StaffHub](microsoft-staffhub-to-be-retired.md).</span><span class="sxs-lookup"><span data-stu-id="9c1ce-109">To learn more, see [Microsoft StaffHub to be retired](microsoft-staffhub-to-be-retired.md).</span></span>  

<span data-ttu-id="9c1ce-110">Suivez les étapes décrites dans cet article pour installer le module Microsoft StaffHub PowerShell et vous y connecter.</span><span class="sxs-lookup"><span data-stu-id="9c1ce-110">Use the steps in this article to install and connect to the Microsoft StaffHub PowerShell module.</span></span> <span data-ttu-id="9c1ce-111">Vous en aurez besoin pour [migrer vos équipes StaffHub vers teams](move-staffhub-teams-to-shifts-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="9c1ce-111">You'll need this to [move your StaffHub teams to Teams](move-staffhub-teams-to-shifts-in-teams.md).</span></span>

## <a name="install-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="9c1ce-112">Installer le module PowerShell Microsoft StaffHub</span><span class="sxs-lookup"><span data-stu-id="9c1ce-112">Install the Microsoft StaffHub PowerShell module</span></span>

1. <span data-ttu-id="9c1ce-113">Téléchargez le [module StaffHub PowerShell](https://www.powershellgallery.com/packages/MicrosoftStaffHub).</span><span class="sxs-lookup"><span data-stu-id="9c1ce-113">Download the [StaffHub PowerShell module](https://www.powershellgallery.com/packages/MicrosoftStaffHub).</span></span>
2. <span data-ttu-id="9c1ce-114">Ouvrez Windows PowerShell 3,0 ou version ultérieure en tant qu’administrateur. Pour cela, cliquez sur **Démarrer**, tapez **Windows PowerShell**, cliquez avec le bouton droit sur **Windows PowerShell**, puis sélectionnez **exécuter en tant qu’administrateur**.</span><span class="sxs-lookup"><span data-stu-id="9c1ce-114">Open Windows PowerShell 3.0 or later as an admin. To do this, click **Start**, type **Windows PowerShell**, right-click **Windows PowerShell**, and then select **Run as administrator**.</span></span>
    > [!NOTE]
    > <span data-ttu-id="9c1ce-115">Pour obtenir la dernière version de Windows PowerShell, voir [installation de Windows PowerShell](https://docs.microsoft.com/powershell/scripting/install/installing-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="9c1ce-115">To get the latest version of Windows PowerShell, see [Installing Windows PowerShell](https://docs.microsoft.com/powershell/scripting/install/installing-windows-powershell).</span></span>
3. <span data-ttu-id="9c1ce-116">Exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="9c1ce-116">Run the following:</span></span>

    ```
    $ENV:PSModulePath
    ```
4. <span data-ttu-id="9c1ce-117">Consultez le chemin d’accès du dossier dans la sortie et assurez-vous que tous les dossiers du chemin d’accès existent sur votre ordinateur avant de passer à l’étape suivante.</span><span class="sxs-lookup"><span data-stu-id="9c1ce-117">Check the folder path in the output and make sure that all folders in the path exist on your computer before you go to the next step.</span></span> <span data-ttu-id="9c1ce-118">Si les dossiers sont manquants, créez-les.</span><span class="sxs-lookup"><span data-stu-id="9c1ce-118">If folders are missing, create them.</span></span>
5. <span data-ttu-id="9c1ce-119">Pour pouvoir installer le module StaffHub PowerShell, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="9c1ce-119">Run the following to allow for installation of the StaffHub PowerShell module:</span></span>

    ```
    Set-ExecutionPolicy RemoteSigned
    ```
6. <span data-ttu-id="9c1ce-120">Exécutez la commande suivante, &lt;où&gt; Path correspond au chemin d’accès dans la sortie de l’étape 3.</span><span class="sxs-lookup"><span data-stu-id="9c1ce-120">Run the following, where &lt;path&gt; is the path in the output from step 3.</span></span> <span data-ttu-id="9c1ce-121">Par exemple, le chemin d’accès peut ressembler à C:\Users\User1\Documents\WindowsPowerShell\Modules.</span><span class="sxs-lookup"><span data-stu-id="9c1ce-121">For example, the path might look like C:\Users\User1\Documents\WindowsPowerShell\Modules.</span></span>

    <span data-ttu-id="9c1ce-122">Assurez-vous d’exécuter chaque commande séparément.</span><span class="sxs-lookup"><span data-stu-id="9c1ce-122">Be sure to run each command separately.</span></span>

    ```
    Install-Module -Name PackageManagement -Force  -AllowClobber
    Install-Module -Name PowerShellGet -Force  -AllowClobber
    ```
7. <span data-ttu-id="9c1ce-123">Quittez Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9c1ce-123">Exit Windows PowerShell.</span></span>
8. <span data-ttu-id="9c1ce-124">Ouvrez Windows PowerShell 3,0 ou version ultérieure en tant qu’administrateur global, puis exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="9c1ce-124">Open Windows PowerShell 3.0 or later as a global admin, and then run the following:</span></span>

    ```
    Install-Module -Name MicrosoftStaffHub

## Connect to the Microsoft StaffHub PowerShell module

1. Run the following:

    ```
    <span data-ttu-id="9c1ce-125">Connexion-StaffHub</span><span class="sxs-lookup"><span data-stu-id="9c1ce-125">Connect-StaffHub</span></span>
    ```

2. When you're prompted, log in as a global admin.

## Related topics

- [Microsoft StaffHub PowerShell reference](https://docs.microsoft.com/powershell/module/staffhub/?view=staffhub-ps)
- [Move your Microsoft StaffHub teams to Shifts in Teams](move-staffhub-teams-to-shifts-in-teams.md)
