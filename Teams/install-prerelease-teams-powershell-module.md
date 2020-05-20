---
title: Installer la version précommerciale du module PowerShell teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: brandber
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Pour installer la version préliminaire du module PowerShell teams à partir de la Galerie de tests PowerShell, procédez comme suit.
ms.openlocfilehash: 1d85fac2ee6a1c8565f8482f7208a2f5ae33db60
ms.sourcegitcommit: 1a6b4efad1e6a958cdbaae4b0e2e231145c9658f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/19/2020
ms.locfileid: "44321767"
---
# <a name="install-the-pre-release-version-of-the-teams-powershell-module"></a><span data-ttu-id="af472-103">Installer la version précommerciale du module PowerShell teams</span><span class="sxs-lookup"><span data-stu-id="af472-103">Install the pre-release version of the Teams PowerShell module</span></span>

<span data-ttu-id="af472-104">Cet article décrit comment installer la dernière version précommerciale du module teams PowerShell à partir de la [Galerie de tests PowerShell](https://www.poshtestgallery.com/packages/MicrosoftTeams/).</span><span class="sxs-lookup"><span data-stu-id="af472-104">This article describes how to install the latest pre-release version of the Teams PowerShell module from the [PowerShell Test Gallery](https://www.poshtestgallery.com/packages/MicrosoftTeams/).</span></span> <span data-ttu-id="af472-105">Vous aurez besoin de la version préliminaire du module PowerShell teams dans les scénarios où les cmdlets de gestion d’une fonctionnalité d’équipes ne sont pas prises en charge dans la version en général disponible du module et sont uniquement disponibles dans la version préliminaire.</span><span class="sxs-lookup"><span data-stu-id="af472-105">You'll need the pre-release version of the Teams PowerShell module in scenarios where cmdlets for managing a Teams feature aren't supported in the Generally Available version of the module and are only available in the pre-release version.</span></span>

<span data-ttu-id="af472-106">Pour installer la dernière version préliminaire du module PowerShell teams à partir de la Galerie de tests PowerShell, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="af472-106">Use these steps to install the latest pre-release version of the Teams PowerShell module from the PowerShell Test Gallery.</span></span>

> [!NOTE]
> <span data-ttu-id="af472-107">N’installez pas le module PowerShell teams à partir de la Galerie de tests PowerShell côte à côte avec une version du module dans la [Galerie PowerShell publique](https://www.powershellgallery.com/packages/MicrosoftTeams/).</span><span class="sxs-lookup"><span data-stu-id="af472-107">Don't install the Teams PowerShell module from the PowerShell Test Gallery side-by-side with a version of the module from the [public PowerShell Gallery](https://www.powershellgallery.com/packages/MicrosoftTeams/).</span></span> <span data-ttu-id="af472-108">Procédez comme suit pour désinstaller d’abord le module PowerShell teams dans la Galerie PowerShell public, puis installez la dernière version du module à partir de la Galerie de tests PowerShell.</span><span class="sxs-lookup"><span data-stu-id="af472-108">Follow these steps to first uninstall the Teams PowerShell module from the public PowerShell Gallery, and then install the latest version of the module from the PowerShell Test Gallery.</span></span>

1. <span data-ttu-id="af472-109">Fermez toutes les sessions PowerShell existantes.</span><span class="sxs-lookup"><span data-stu-id="af472-109">Close all existing PowerShell sessions.</span></span>
2. <span data-ttu-id="af472-110">Démarrez une nouvelle instance du module Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="af472-110">Start a new instance of the Windows PowerShell module.</span></span>
3. <span data-ttu-id="af472-111">Pour désinstaller le module teams PowerShell de la Galerie public PowerShell, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="af472-111">Run the following to uninstall the Teams PowerShell module from the public PowerShell Gallery:</span></span>

    ```PowerShell
    Uninstall-Module -Name MicrosoftTeams
    ```

4. <span data-ttu-id="af472-112">Fermez toutes les sessions PowerShell existantes.</span><span class="sxs-lookup"><span data-stu-id="af472-112">Close all existing PowerShell sessions.</span></span>
5. <span data-ttu-id="af472-113">Démarrez de nouveau le module Windows PowerShell, puis exécutez la commande suivante pour inscrire la Galerie de tests PowerShell en tant que source de confiance :</span><span class="sxs-lookup"><span data-stu-id="af472-113">Start the Windows PowerShell module again, and then run the following to register the PowerShell Test Gallery as a trusted source:</span></span>

    ```PowerShell
    Register-PSRepository -Name PSGalleryInt -SourceLocation https://www.poshtestgallery.com/ -InstallationPolicy Trusted
    ```

6. <span data-ttu-id="af472-114">Pour installer le dernier module PowerShell teams à partir de la Galerie de tests PowerShell, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="af472-114">Run the following to install the latest Teams PowerShell module from the PowerShell Test Gallery:</span></span>

    ```PowerShell
    Install-Module -Name MicrosoftTeams -Repository PSGalleryInt -Force
    ```

7. <span data-ttu-id="af472-115">Exécutez la commande suivante pour vérifier que la version la plus récente du module PowerShell teams de la Galerie de tests PowerShell est correctement installée :</span><span class="sxs-lookup"><span data-stu-id="af472-115">Run the following to verify that the latest version of the Teams PowerShell module from the PowerShell Test Gallery is successfully installed:</span></span>

    ```PowerShell
    Get-Module -Name MicrosoftTeams
    ```

#### <a name="update-to-the-latest-version-of-the-teams-powershell-module-from-the-powershell-test-gallery"></a><span data-ttu-id="af472-116">Effectuer une mise à jour vers la dernière version du module PowerShell teams à partir de la Galerie de tests PowerShell</span><span class="sxs-lookup"><span data-stu-id="af472-116">Update to the latest version of the Teams PowerShell module from the PowerShell Test Gallery</span></span>

<span data-ttu-id="af472-117">Si vous avez déjà installé le module teams PowerShell à partir de la Galerie de tests PowerShell, procédez comme suit pour effectuer une mise à jour vers la dernière version.</span><span class="sxs-lookup"><span data-stu-id="af472-117">If you already installed the Teams PowerShell module from the PowerShell Test Gallery, use the following steps to update to the latest version.</span></span>

1. <span data-ttu-id="af472-118">Fermez toutes les sessions PowerShell existantes.</span><span class="sxs-lookup"><span data-stu-id="af472-118">Close all existing PowerShell sessions.</span></span>
2. <span data-ttu-id="af472-119">Démarrez une nouvelle instance du module Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="af472-119">Start a new instance of the Windows PowerShell module.</span></span>
3. <span data-ttu-id="af472-120">Exécutez la commande suivante pour mettre à jour la version actuellement installée du module PowerShell teams à partir de la Galerie de tests PowerShell :</span><span class="sxs-lookup"><span data-stu-id="af472-120">Run the following to update the currently installed version of the Teams PowerShell module from the PowerShell Test Gallery:</span></span>

    ```PowerShell
    Update-Module -Name MicrosoftTeams -Force
    ```

4. <span data-ttu-id="af472-121">Exécutez la commande suivante pour vérifier que la version la plus récente du module PowerShell teams de la Galerie de tests PowerShell est correctement installée :</span><span class="sxs-lookup"><span data-stu-id="af472-121">Run the following to verify that the latest version of the Teams PowerShell module from the PowerShell Test Gallery is successfully installed:</span></span>

    ```PowerShell
    Get-Module -Name MicrosoftTeams
    ```

## <a name="related-topics"></a><span data-ttu-id="af472-122">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="af472-122">Related topics</span></span>

- [<span data-ttu-id="af472-123">Présentation de Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="af472-123">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
