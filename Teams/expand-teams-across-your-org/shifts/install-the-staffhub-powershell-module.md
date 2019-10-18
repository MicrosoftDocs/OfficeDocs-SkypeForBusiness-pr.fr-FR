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
description: Découvrez comment installer la version préliminaire du module Microsoft StaffHub PowerShell et vous y connecter.
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: aa7f84342b2d4ae16cf801be513e1ae9d6440802
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2019
ms.locfileid: "37569209"
---
# <a name="install-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="f451c-103">Installer le module PowerShell Microsoft StaffHub</span><span class="sxs-lookup"><span data-stu-id="f451c-103">Install the Microsoft StaffHub PowerShell module</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f451c-104">À compter du 31 décembre 2019, Microsoft StaffHub sera supprimé.</span><span class="sxs-lookup"><span data-stu-id="f451c-104">Effective December 31, 2019, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="f451c-105">Nous développons des fonctionnalités StaffHub dans Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f451c-105">We’re building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="f451c-106">Aujourd’hui, teams inclut l’application Shifts pour la gestion des plannings et des fonctionnalités supplémentaires seront déployées dans le temps.</span><span class="sxs-lookup"><span data-stu-id="f451c-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="f451c-107">StaffHub s’arrêtera de fonctionner pour tous les utilisateurs du 31 décembre 2019.</span><span class="sxs-lookup"><span data-stu-id="f451c-107">StaffHub will stop working for all users on December 31, 2019.</span></span> <span data-ttu-id="f451c-108">Tout utilisateur essayant d’ouvrir StaffHub verra s’afficher un message lui indiquant de télécharger Teams.</span><span class="sxs-lookup"><span data-stu-id="f451c-108">Anyone who tries to open StaffHub will be shown a message directing them to download Teams.</span></span> <span data-ttu-id="f451c-109">Pour en savoir plus, consultez la rubrique [Microsoft StaffHub](microsoft-staffhub-to-be-retired.md).</span><span class="sxs-lookup"><span data-stu-id="f451c-109">To learn more, see [Microsoft StaffHub to be retired](microsoft-staffhub-to-be-retired.md).</span></span>  

<span data-ttu-id="f451c-110">Suivez les étapes décrites dans cet article pour installer et vous connecter à la version préliminaire du module Microsoft StaffHub PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f451c-110">Use the steps in this article to install and connect to the prerelease version of the Microsoft StaffHub PowerShell module.</span></span> <span data-ttu-id="f451c-111">Vous en aurez besoin pour [migrer vos équipes StaffHub vers teams](move-staffhub-teams-to-shifts-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="f451c-111">You'll need this to [move your StaffHub teams to Teams](move-staffhub-teams-to-shifts-in-teams.md).</span></span>

## <a name="install-the-prerelease-version-of-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="f451c-112">Installez la version préliminaire du module Microsoft StaffHub PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f451c-112">Install the prerelease version of the Microsoft StaffHub PowerShell module</span></span>

1. <span data-ttu-id="f451c-113">Ouvrez Windows PowerShell 3,0 ou version ultérieure en tant qu’administrateur. Pour cela, cliquez sur **Démarrer**, tapez **Windows PowerShell**, cliquez avec le bouton droit sur **Windows PowerShell**, puis sélectionnez **exécuter en tant qu’administrateur**.</span><span class="sxs-lookup"><span data-stu-id="f451c-113">Open Windows PowerShell 3.0 or later as an admin. To do this, click **Start**, type **Windows PowerShell**, right-click **Windows PowerShell**, and then select **Run as administrator**.</span></span>
    > [!NOTE]
    > <span data-ttu-id="f451c-114">Pour obtenir la dernière version de Windows PowerShell, voir [installation de Windows PowerShell](https://docs.microsoft.com/powershell/scripting/install/installing-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="f451c-114">To get the latest version of Windows PowerShell, see [Installing Windows PowerShell](https://docs.microsoft.com/powershell/scripting/install/installing-windows-powershell).</span></span> 
2. <span data-ttu-id="f451c-115">Pour installer la version préliminaire du module StaffHub PowerShell, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="f451c-115">Run the following to install the prerelease version of the StaffHub PowerShell module:</span></span>

    ```
    Install-Module -Name MicrosoftStaffHub -AllowPrerelease
    ```
3. <span data-ttu-id="f451c-116">Le message d’avertissement suivant risque de s’afficher :</span><span class="sxs-lookup"><span data-stu-id="f451c-116">You may see the warning message:</span></span>

    ```
    Untrusted repository - You are installing the modules from an untrusted repository. If you trust this repository, change its InstallationPolicy value by running the Set-PSRepository cmdlet. Are you sure you want to install the modules from 'PSGallery'?
    ```

    <span data-ttu-id="f451c-117">Tapez `Y`, puis cliquez sur `Enter`.</span><span class="sxs-lookup"><span data-stu-id="f451c-117">Type `Y`, and then click `Enter`.</span></span>
 
4. <span data-ttu-id="f451c-118">Quittez Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f451c-118">Exit Windows PowerShell.</span></span>

## <a name="connect-to-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="f451c-119">Se connecter au module Microsoft StaffHub PowerShell</span><span class="sxs-lookup"><span data-stu-id="f451c-119">Connect to the Microsoft StaffHub PowerShell module</span></span>

1. <span data-ttu-id="f451c-120">Exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="f451c-120">Run the following:</span></span>

    ```
    Connect-StaffHub
    ```

2. <span data-ttu-id="f451c-121">Lorsque vous y êtes invité, connectez-vous en tant qu’administrateur général.</span><span class="sxs-lookup"><span data-stu-id="f451c-121">When you're prompted, log in as a global admin.</span></span>

## <a name="related-topics"></a><span data-ttu-id="f451c-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f451c-122">Related topics</span></span>

- [<span data-ttu-id="f451c-123">Référence PowerShell Microsoft StaffHub</span><span class="sxs-lookup"><span data-stu-id="f451c-123">Microsoft StaffHub PowerShell reference</span></span>](https://docs.microsoft.com/en-us/powershell/module/staffhub/?view=staffhub-ps)
- [<span data-ttu-id="f451c-124">Faire passer vos équipes de Microsoft StaffHub vers Shifts dans Teams</span><span class="sxs-lookup"><span data-stu-id="f451c-124">Move your Microsoft StaffHub teams to Shifts in Teams</span></span>](move-staffhub-teams-to-shifts-in-teams.md)
