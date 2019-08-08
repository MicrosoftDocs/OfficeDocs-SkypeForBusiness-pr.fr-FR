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
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 179276a049a30f1d049521cc3b4db326b988667c
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36246178"
---
# <a name="install-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="bbb0e-103">Installer le module PowerShell Microsoft StaffHub</span><span class="sxs-lookup"><span data-stu-id="bbb0e-103">Install the Microsoft StaffHub PowerShell module</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bbb0e-104">À compter du 1er octobre 2019, Microsoft StaffHub sera supprimé.</span><span class="sxs-lookup"><span data-stu-id="bbb0e-104">Effective October 1, 2019, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="bbb0e-105">Nous développons des fonctionnalités StaffHub dans Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="bbb0e-105">We’re building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="bbb0e-106">Aujourd’hui, teams inclut l’application Shifts pour la gestion des plannings et des fonctionnalités supplémentaires seront déployées dans le temps.</span><span class="sxs-lookup"><span data-stu-id="bbb0e-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="bbb0e-107">StaffHub ne fonctionnera pas pour tous les utilisateurs du 1er octobre 2019.</span><span class="sxs-lookup"><span data-stu-id="bbb0e-107">StaffHub will stop working for all users on October 1, 2019.</span></span> <span data-ttu-id="bbb0e-108">Tout utilisateur essayant d’ouvrir StaffHub verra s’afficher un message lui indiquant de télécharger Teams.</span><span class="sxs-lookup"><span data-stu-id="bbb0e-108">Anyone who tries to open StaffHub will be shown a message directing them to download Teams.</span></span> <span data-ttu-id="bbb0e-109">Pour en savoir plus, consultez la rubrique [Microsoft StaffHub](microsoft-staffhub-to-be-retired.md).</span><span class="sxs-lookup"><span data-stu-id="bbb0e-109">To learn more, see [Microsoft StaffHub to be retired](microsoft-staffhub-to-be-retired.md).</span></span>  

<span data-ttu-id="bbb0e-110">Suivez les étapes décrites dans cet article pour installer le module Microsoft StaffHub PowerShell et vous y connecter.</span><span class="sxs-lookup"><span data-stu-id="bbb0e-110">Use the steps in this article to install and connect to the Microsoft StaffHub PowerShell module.</span></span> <span data-ttu-id="bbb0e-111">Vous en aurez besoin pour gérer StaffHub à l’aide de PowerShell et déplacer vos équipes StaffHub vers Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="bbb0e-111">You'll need this to manage StaffHub by using PowerShell and to move your StaffHub teams to Microsoft Teams.</span></span>

## <a name="install-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="bbb0e-112">Installer le module PowerShell Microsoft StaffHub</span><span class="sxs-lookup"><span data-stu-id="bbb0e-112">Install the Microsoft StaffHub PowerShell module</span></span>

1. <span data-ttu-id="bbb0e-113">Téléchargez le [module StaffHub PowerShell](https://www.powershellgallery.com/packages/MicrosoftStaffHub/1.0.0-alpha).</span><span class="sxs-lookup"><span data-stu-id="bbb0e-113">Download the [StaffHub PowerShell module](https://www.powershellgallery.com/packages/MicrosoftStaffHub/1.0.0-alpha).</span></span> 
2. <span data-ttu-id="bbb0e-114">Ouvrez Windows PowerShell 3,0 ou version ultérieure en tant qu’administrateur. Pour cela, cliquez sur **Démarrer**, tapez **Windows PowerShell**, cliquez avec le bouton droit sur **Windows PowerShell**, puis sélectionnez **exécuter en tant qu’administrateur**.</span><span class="sxs-lookup"><span data-stu-id="bbb0e-114">Open Windows PowerShell 3.0 or later as an admin. To do this, click **Start**, type **Windows PowerShell**, right-click **Windows PowerShell**, and then select **Run as administrator**.</span></span>
    > [!NOTE]
    > <span data-ttu-id="bbb0e-115">Pour obtenir la dernière version de Windows PowerShell, voir [installation de Windows PowerShell](https://docs.microsoft.com/powershell/scripting/install/installing-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="bbb0e-115">To get the latest version of Windows PowerShell, see [Installing Windows PowerShell](https://docs.microsoft.com/powershell/scripting/install/installing-windows-powershell).</span></span> 
3. <span data-ttu-id="bbb0e-116">Exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="bbb0e-116">Run the following:</span></span>

    ```
    $ENV:PSModulePath
    ```
    

4. <span data-ttu-id="bbb0e-117">Consultez le chemin d’accès du dossier dans la sortie et assurez-vous que tous les dossiers du chemin d’accès existent sur votre ordinateur avant de passer à l’étape suivante.</span><span class="sxs-lookup"><span data-stu-id="bbb0e-117">Check the folder path in the output and make sure that all folders in the path exist on your computer before you go to the next step.</span></span> <span data-ttu-id="bbb0e-118">Si les dossiers sont manquants, créez-les.</span><span class="sxs-lookup"><span data-stu-id="bbb0e-118">If folders are missing, create them.</span></span>
5. <span data-ttu-id="bbb0e-119">Pour pouvoir installer le module StaffHub PowerShell, procédez comme suit:</span><span class="sxs-lookup"><span data-stu-id="bbb0e-119">Run the following to allow for installation of the StaffHub PowerShell module:</span></span>

    ```
    Set-ExecutionPolicy RemoteSigned
    ```

6. <span data-ttu-id="bbb0e-120">Exécutez la commande suivante, &lt;où&gt; Path correspond au chemin d’accès dans la sortie de l’étape 2.</span><span class="sxs-lookup"><span data-stu-id="bbb0e-120">Run the following, where &lt;path&gt; is the path in the output from step 2.</span></span> <span data-ttu-id="bbb0e-121">Par exemple, le chemin d’accès peut ressembler à C:\Users\User1\Documents\WindowsPowerShell\Modules.</span><span class="sxs-lookup"><span data-stu-id="bbb0e-121">For example, the path might look like C:\Users\User1\Documents\WindowsPowerShell\Modules.</span></span>

    <span data-ttu-id="bbb0e-122">Assurez-vous d’exécuter chaque commande séparément.</span><span class="sxs-lookup"><span data-stu-id="bbb0e-122">Be sure to run each command separately.</span></span>

    ```
    Save-Module -Name PowerShellGet -Path <path> -RequiredVersion 1.6.6
    Install-Module -Name PackageManagement -Force  -AllowClobber
    Install-Module -Name PowerShellGet -Force  -AllowClobber
    Save-Module -Name MicrosoftStaffHub -Path <path> -RequiredVersion 1.0.5-alpha -AllowPrerelease
    ```
7. <span data-ttu-id="bbb0e-123">Quittez Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bbb0e-123">Exit Windows PowerShell.</span></span>
8. <span data-ttu-id="bbb0e-124">Ouvrez Windows PowerShell 3,0 ou version ultérieure en tant qu’administrateur global, puis exécutez la commande suivante:</span><span class="sxs-lookup"><span data-stu-id="bbb0e-124">Open Windows PowerShell 3.0 or later as a global admin, and then run the following:</span></span>

    ```
    Install-Module -Name MicrosoftStaffHub -RequiredVersion 1.0.5-alpha -AllowPrerelease
    ```

## <a name="connect-to-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="bbb0e-125">Se connecter au module Microsoft StaffHub PowerShell</span><span class="sxs-lookup"><span data-stu-id="bbb0e-125">Connect to the Microsoft StaffHub PowerShell module</span></span>

1. <span data-ttu-id="bbb0e-126">Exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="bbb0e-126">Run the following:</span></span>

    ```
    Connect-StaffHub
    ```

2. <span data-ttu-id="bbb0e-127">Lorsque vous y êtes invité, connectez-vous en tant qu’administrateur général.</span><span class="sxs-lookup"><span data-stu-id="bbb0e-127">When you're prompted, log in as a global admin.</span></span>

## <a name="related-topics"></a><span data-ttu-id="bbb0e-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="bbb0e-128">Related topics</span></span>

- [<span data-ttu-id="bbb0e-129">Référence PowerShell Microsoft StaffHub</span><span class="sxs-lookup"><span data-stu-id="bbb0e-129">Microsoft StaffHub PowerShell reference</span></span>](https://docs.microsoft.com/en-us/powershell/module/staffhub/?view=staffhub-ps)
- [<span data-ttu-id="bbb0e-130">Faire passer vos équipes de Microsoft StaffHub vers Shifts dans Teams</span><span class="sxs-lookup"><span data-stu-id="bbb0e-130">Move your Microsoft StaffHub teams to Shifts in Teams</span></span>](move-staffhub-teams-to-shifts-in-teams.md)
