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
ms.openlocfilehash: 9ce0d1acec923d09591e8f81b3f500ee9a910f5c
ms.sourcegitcommit: b914c044c43ff8147f35eea684fec1de01a7bcd2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/19/2019
ms.locfileid: "36464664"
---
# <a name="install-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="b2119-103">Installer le module PowerShell Microsoft StaffHub</span><span class="sxs-lookup"><span data-stu-id="b2119-103">Install the Microsoft StaffHub PowerShell module</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b2119-104">À compter du 1er octobre 2019, Microsoft StaffHub sera supprimé.</span><span class="sxs-lookup"><span data-stu-id="b2119-104">Effective October 1, 2019, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="b2119-105">Nous développons des fonctionnalités StaffHub dans Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="b2119-105">We’re building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="b2119-106">Aujourd’hui, teams inclut l’application Shifts pour la gestion des plannings et des fonctionnalités supplémentaires seront déployées dans le temps.</span><span class="sxs-lookup"><span data-stu-id="b2119-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="b2119-107">StaffHub ne fonctionnera pas pour tous les utilisateurs du 1er octobre 2019.</span><span class="sxs-lookup"><span data-stu-id="b2119-107">StaffHub will stop working for all users on October 1, 2019.</span></span> <span data-ttu-id="b2119-108">Tout utilisateur essayant d’ouvrir StaffHub verra s’afficher un message lui indiquant de télécharger Teams.</span><span class="sxs-lookup"><span data-stu-id="b2119-108">Anyone who tries to open StaffHub will be shown a message directing them to download Teams.</span></span> <span data-ttu-id="b2119-109">Pour en savoir plus, consultez la rubrique [Microsoft StaffHub](microsoft-staffhub-to-be-retired.md).</span><span class="sxs-lookup"><span data-stu-id="b2119-109">To learn more, see [Microsoft StaffHub to be retired](microsoft-staffhub-to-be-retired.md).</span></span>  

<span data-ttu-id="b2119-110">Suivez les étapes décrites dans cet article pour installer le module Microsoft StaffHub PowerShell et vous y connecter.</span><span class="sxs-lookup"><span data-stu-id="b2119-110">Use the steps in this article to install and connect to the Microsoft StaffHub PowerShell module.</span></span> <span data-ttu-id="b2119-111">Vous en aurez besoin pour gérer StaffHub à l’aide de PowerShell et déplacer vos équipes StaffHub vers Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="b2119-111">You'll need this to manage StaffHub by using PowerShell and to move your StaffHub teams to Microsoft Teams.</span></span>

## <a name="install-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="b2119-112">Installer le module PowerShell Microsoft StaffHub</span><span class="sxs-lookup"><span data-stu-id="b2119-112">Install the Microsoft StaffHub PowerShell module</span></span>

1. <span data-ttu-id="b2119-113">Ouvrez Windows PowerShell 3,0 ou version ultérieure en tant qu’administrateur. Pour cela, cliquez sur **Démarrer**, tapez **Windows PowerShell**, cliquez avec le bouton droit sur **Windows PowerShell**, puis sélectionnez **exécuter en tant qu’administrateur**.</span><span class="sxs-lookup"><span data-stu-id="b2119-113">Open Windows PowerShell 3.0 or later as an admin. To do this, click **Start**, type **Windows PowerShell**, right-click **Windows PowerShell**, and then select **Run as administrator**.</span></span>
    > [!NOTE]
    > <span data-ttu-id="b2119-114">Pour obtenir la dernière version de Windows PowerShell, voir [installation de Windows PowerShell](https://docs.microsoft.com/powershell/scripting/install/installing-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="b2119-114">To get the latest version of Windows PowerShell, see [Installing Windows PowerShell](https://docs.microsoft.com/powershell/scripting/install/installing-windows-powershell).</span></span> 
2. <span data-ttu-id="b2119-115">Pour installer la version stable actuelle du module StaffHub PowerShell, exécutez la commande suivante:</span><span class="sxs-lookup"><span data-stu-id="b2119-115">Run the following to install the current stable version of the StaffHub PowerShell module:</span></span>

    ```
    Install-Module -Name MicrosoftStaffHub
    ```
    
    <span data-ttu-id="b2119-116">Vous pouvez exécuter cette commande uniquement si vous avez besoin d’installer la version la plus récente, qui peut avoir une plus grande instabilité par rapport à la version stable actuelle:`Install-Module -Name MicrosoftStaffHub -AllowPrerelease`</span><span class="sxs-lookup"><span data-stu-id="b2119-116">You can run this command only if you need to install the latest version, which may have more instabilities than the current stable version: `Install-Module -Name MicrosoftStaffHub -AllowPrerelease`</span></span>

     > [!NOTE]
     > <span data-ttu-id="b2119-117">Si vous recevez un message d’erreur lors de l’installation de la version la plus récente en ayant une plus grande instabilité, vous pouvez exécuter:`Install-Module PowershellGet -Force`</span><span class="sxs-lookup"><span data-stu-id="b2119-117">If you receive an error during the installation of the latest version with more instabilities, you can run: `Install-Module PowershellGet -Force`</span></span>

3. <span data-ttu-id="b2119-118">Le message d’avertissement suivant risque de s’afficher:</span><span class="sxs-lookup"><span data-stu-id="b2119-118">You may see the warning message:</span></span>

    ```
    Untrusted repository - You are installing the modules from an untrusted repository. If you trust this repository, change its InstallationPolicy value by running the Set-PSRepository cmdlet. Are you sure you want to install the modules from 'PSGallery'?
    ```

<span data-ttu-id="b2119-119">Tapez `Y` , puis `Enter`cliquez sur.</span><span class="sxs-lookup"><span data-stu-id="b2119-119">Type `Y` and click `Enter`.</span></span>
 
4. <span data-ttu-id="b2119-120">Quittez Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b2119-120">Exit Windows PowerShell.</span></span>

## <a name="connect-to-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="b2119-121">Se connecter au module Microsoft StaffHub PowerShell</span><span class="sxs-lookup"><span data-stu-id="b2119-121">Connect to the Microsoft StaffHub PowerShell module</span></span>

1. <span data-ttu-id="b2119-122">Exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="b2119-122">Run the following:</span></span>

    ```
    Connect-StaffHub
    ```

2. <span data-ttu-id="b2119-123">Lorsque vous y êtes invité, connectez-vous en tant qu’administrateur général.</span><span class="sxs-lookup"><span data-stu-id="b2119-123">When you're prompted, log in as a global admin.</span></span>

## <a name="related-topics"></a><span data-ttu-id="b2119-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b2119-124">Related topics</span></span>

- [<span data-ttu-id="b2119-125">Référence PowerShell Microsoft StaffHub</span><span class="sxs-lookup"><span data-stu-id="b2119-125">Microsoft StaffHub PowerShell reference</span></span>](https://docs.microsoft.com/en-us/powershell/module/staffhub/?view=staffhub-ps)
- [<span data-ttu-id="b2119-126">Faire passer vos équipes de Microsoft StaffHub vers Shifts dans Teams</span><span class="sxs-lookup"><span data-stu-id="b2119-126">Move your Microsoft StaffHub teams to Shifts in Teams</span></span>](move-staffhub-teams-to-shifts-in-teams.md)
