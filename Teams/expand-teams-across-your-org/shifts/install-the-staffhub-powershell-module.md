---
title: Installez le module StaffHub PowerShell
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.date: 04/08/2019
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: Découvrez comment installer et se connecter au module Microsoft StaffHub PowerShell.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: fe419348d966d9ddfc5c16eee29d9a5005cd6db8
ms.sourcegitcommit: a505869a3cc2fe6fe4ee18bcbe99bf980aa91a86
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/08/2019
ms.locfileid: "31555131"
---
# <a name="install-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="57045-103">Installer le module Microsoft StaffHub PowerShell</span><span class="sxs-lookup"><span data-stu-id="57045-103">Install the Microsoft StaffHub PowerShell module</span></span>

> [!IMPORTANT]
> <span data-ttu-id="57045-104">Effet 2019, octobre 1, Microsoft StaffHub sera être retirée.</span><span class="sxs-lookup"><span data-stu-id="57045-104">Effective October 1, 2019, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="57045-105">Nous créons StaffHub fonctionnalités dans Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="57045-105">We’re building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="57045-106">Aujourd'hui, les équipes inclut l’application des équipes de gestion de la planification et des fonctionnalités supplémentaires seront intégrées au fil du temps.</span><span class="sxs-lookup"><span data-stu-id="57045-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="57045-107">StaffHub cessera de fonctionner pour tous les utilisateurs sur le 1 octobre 2019.</span><span class="sxs-lookup"><span data-stu-id="57045-107">StaffHub will stop working for all users on October 1, 2019.</span></span> <span data-ttu-id="57045-108">Toute personne qui essaie d’ouvrir StaffHub s’affichera un message pronom pour télécharger les équipes.</span><span class="sxs-lookup"><span data-stu-id="57045-108">Anyone who tries to open StaffHub will be shown a message directing them to download Teams.</span></span> <span data-ttu-id="57045-109">Pour plus d’informations, voir [Microsoft StaffHub à retirer](microsoft-staffhub-to-be-retired.md).</span><span class="sxs-lookup"><span data-stu-id="57045-109">To learn more, see [Microsoft StaffHub to be retired](microsoft-staffhub-to-be-retired.md).</span></span>  

<span data-ttu-id="57045-110">Utilisez les étapes décrites dans cet article pour installer et se connecter au module Microsoft StaffHub PowerShell.</span><span class="sxs-lookup"><span data-stu-id="57045-110">Use the steps in this article to install and connect to the Microsoft StaffHub PowerShell module.</span></span> <span data-ttu-id="57045-111">Vous aurez besoin pour gérer les StaffHub à l’aide de PowerShell et atteindre vos équipes StaffHub Teams Microsoft.</span><span class="sxs-lookup"><span data-stu-id="57045-111">You'll need this to manage StaffHub by using PowerShell and to move your StaffHub teams to Microsoft Teams.</span></span>

## <a name="install-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="57045-112">Installer le module Microsoft StaffHub PowerShell</span><span class="sxs-lookup"><span data-stu-id="57045-112">Install the Microsoft StaffHub PowerShell module</span></span>

1. <span data-ttu-id="57045-113">Télécharger le [module StaffHub PowerShell](https://www.powershellgallery.com/packages/MicrosoftStaffHub/1.0.0-alpha).</span><span class="sxs-lookup"><span data-stu-id="57045-113">Download the [StaffHub PowerShell module](https://www.powershellgallery.com/packages/MicrosoftStaffHub/1.0.0-alpha).</span></span> 
2. <span data-ttu-id="57045-114">Ouvrez Windows PowerShell 3.0 ou version ultérieure en tant qu’administrateur.</span><span class="sxs-lookup"><span data-stu-id="57045-114">Open Windows PowerShell 3.0 or later as an administrator.</span></span> <span data-ttu-id="57045-115">Pour ce faire, cliquez sur **Démarrer**, tapez **Windows PowerShell**, avec le bouton droit de **Windows PowerShell**, puis sélectionnez **Exécuter en tant qu’administrateur**.</span><span class="sxs-lookup"><span data-stu-id="57045-115">To do this, click **Start**, type **Windows PowerShell**, right-click **Windows PowerShell**, and then select **Run as administrator**.</span></span>
3. <span data-ttu-id="57045-116">Exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="57045-116">Run the following:</span></span>

    ```
    $ENV:PSModulePath
    ```

4. <span data-ttu-id="57045-117">Vérifiez le chemin d’accès du dossier dans la sortie et vous assurer que tous les dossiers dans le chemin d’accès existent sur votre ordinateur avant de passer à l’étape suivante.</span><span class="sxs-lookup"><span data-stu-id="57045-117">Check the folder path in the output and make sure that all folders in the path exist on your computer before you go to the next step.</span></span> <span data-ttu-id="57045-118">Si des dossiers sont manquants, les créer.</span><span class="sxs-lookup"><span data-stu-id="57045-118">If folders are missing, create them.</span></span>
5. <span data-ttu-id="57045-119">Exécutez la commande suivante, où &lt;chemin d’accès&gt; est le chemin d’accès dans la sortie de l’étape 2.</span><span class="sxs-lookup"><span data-stu-id="57045-119">Run the following, where &lt;path&gt; is the path in the output from step 2.</span></span> <span data-ttu-id="57045-120">Par exemple, le chemin d’accès peut ressembler à C:\Users\User1\Documents\WindowsPowerShell\Modules.</span><span class="sxs-lookup"><span data-stu-id="57045-120">For example, the path might look like C:\Users\User1\Documents\WindowsPowerShell\Modules.</span></span>

    ```
    Save-Module -Name PowerShellGet -Path <path> -RequiredVersion 1.6.6
    Install-Module -Name PowerShellGet -Force  -AllowClobber
    Save-Module -Name MicrosoftStaffHub -Path <path> -RequiredVersion 1.0.2
    Install-Module -Name MicrosoftStaffHub -RequiredVersion 1.0.2
    ```

## <a name="connect-to-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="57045-121">Se connecter au module Microsoft StaffHub PowerShell</span><span class="sxs-lookup"><span data-stu-id="57045-121">Connect to the Microsoft StaffHub PowerShell module</span></span>

1. <span data-ttu-id="57045-122">Exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="57045-122">Run the following:</span></span>

    ```
    Connect-StaffHub
    ```

2. <span data-ttu-id="57045-123">Lorsque vous y êtes invité, ouvrez une session tant qu’un administrateur global.</span><span class="sxs-lookup"><span data-stu-id="57045-123">When you're prompted, log in as a global admin.</span></span>

## <a name="related-topics"></a><span data-ttu-id="57045-124">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="57045-124">Related topics</span></span>

- [<span data-ttu-id="57045-125">Référence Microsoft StaffHub PowerShell</span><span class="sxs-lookup"><span data-stu-id="57045-125">Microsoft StaffHub PowerShell reference</span></span>](https://docs.microsoft.com/en-us/powershell/module/staffhub/?view=staffhub-ps)
- [<span data-ttu-id="57045-126">Faire passer vos équipes de Microsoft StaffHub vers Shifts dans Teams</span><span class="sxs-lookup"><span data-stu-id="57045-126">Move your Microsoft StaffHub teams to Shifts in Teams</span></span>](move-staffhub-teams-to-shifts-in-teams.md)
