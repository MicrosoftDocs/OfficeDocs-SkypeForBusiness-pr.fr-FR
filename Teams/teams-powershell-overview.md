---
title: Vue d’ensemble de Microsoft teams PowerShell
ms.reviewer: ''
author: brandber
ms.author: brandber
manager: kojiko
ms.date: 06/30/2020
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: Découvrez comment utiliser les contrôles PowerShell pour gérer Microsoft Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5385430c7db8aab0adf1efbaec546134e9adf388
ms.sourcegitcommit: 9b1c138b39fd87e239a7b1c5051f30c633e7d813
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/01/2020
ms.locfileid: "44943987"
---
# <a name="microsoft-teams-powershell-overview"></a><span data-ttu-id="e6915-103">Vue d’ensemble de Microsoft teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="e6915-103">Microsoft Teams PowerShell Overview</span></span>

<span data-ttu-id="e6915-104">Microsoft teams PowerShell est un ensemble d’applets de commande qui vous permet de gérer teams directement à partir de la ligne de commande PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e6915-104">Microsoft Teams PowerShell is a set of cmdlets for managing Teams directly from the PowerShell command line.</span></span> <span data-ttu-id="e6915-105">Écrit en .NET standard, teams PowerShell fonctionne sur PowerShell 5,1 sur Windows, PowerShell 6. x et versions ultérieures sur toutes les plateformes, dont Azure Shell.</span><span class="sxs-lookup"><span data-stu-id="e6915-105">Written in .NET Standard, Teams PowerShell works on PowerShell 5.1 on Windows,PowerShell 6.x and higher on all platforms including Azure Shell.</span></span>

<span data-ttu-id="e6915-106">Pour pouvoir commencer à utiliser PowerShell, vous devez l' [installer](teams-powershell-install.md).</span><span class="sxs-lookup"><span data-stu-id="e6915-106">Before you can start using PowerShell, you'll need to [install it](teams-powershell-install.md).</span></span> 

> [!WARNING]
> <span data-ttu-id="e6915-107">Il existe des problèmes connus dans PowerShell 7 et teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e6915-107">There are known issues with PowerShell 7 and Teams PowerShell.</span></span> <span data-ttu-id="e6915-108">Nous vous recommandons d’utiliser PowerShell 5,1 jusqu’à la résolution des problèmes.</span><span class="sxs-lookup"><span data-stu-id="e6915-108">We recommend using PowerShell 5.1 until the issues are resolved.</span></span>

## <a name="releases"></a><span data-ttu-id="e6915-109">Versions</span><span class="sxs-lookup"><span data-stu-id="e6915-109">Releases</span></span>


<span data-ttu-id="e6915-110">PowerShell teams est disponible dans la [Galerie PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) en deux types de publication.</span><span class="sxs-lookup"><span data-stu-id="e6915-110">Teams PowerShell is available on [PowerShell Gallery](https://www.powershellgallery.com/packages/MicrosoftTeams) in two release types.</span></span>

- <span data-ttu-id="e6915-111">**Disponibilité générale (GA)**: cmdlets prêts à l’emploi, mises à jour mensuelles.</span><span class="sxs-lookup"><span data-stu-id="e6915-111">**General Availability (GA)**: Production-ready cmdlets, updated monthly.</span></span>

- <span data-ttu-id="e6915-112">Préversion **publique**: accès en avant-première aux fonctions.</span><span class="sxs-lookup"><span data-stu-id="e6915-112">**Public Preview**: Early access to features.</span></span> <span data-ttu-id="e6915-113">Est-il possible de mettre à jour plus fréquemment que la disponibilité.</span><span class="sxs-lookup"><span data-stu-id="e6915-113">May be updated more frequently than GA.</span></span>

<span data-ttu-id="e6915-114">Pour plus d’informations sur les ajouts et améliorations de fonctionnalités pour les deux versions, consultez les [notes de publication de teams PowerShell](teams-powershell-release-notes.md).</span><span class="sxs-lookup"><span data-stu-id="e6915-114">For detailed information on feature additions and improvements for both releases, read the [Teams PowerShell release notes](teams-powershell-release-notes.md).</span></span>


## <a name="manage-teams-with-powershell"></a><span data-ttu-id="e6915-115">Gestion des équipes avec PowerShell</span><span class="sxs-lookup"><span data-stu-id="e6915-115">Manage Teams with PowerShell</span></span>

<span data-ttu-id="e6915-116">Vous utiliserez les deux modules PowerShell suivants pour gérer pleinement teams :</span><span class="sxs-lookup"><span data-stu-id="e6915-116">You'll use both of these PowerShell modules to fully manage Teams:</span></span>

- <span data-ttu-id="e6915-117">[Module Microsoft teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/): le module PowerShell teams contient des cmdlets de gestion des équipes, des discussions et des canaux.</span><span class="sxs-lookup"><span data-stu-id="e6915-117">[Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams/): The Teams PowerShell module contains cmdlets for managing teams, chat, and channels.</span></span>

- <span data-ttu-id="e6915-118">[Module PowerShell Skype entreprise](https://www.microsoft.com/download/details.aspx?id=39366): le module PowerShell Skype entreprise contient les applets de applet permettant de gérer les fonctionnalités de réunion, de système téléphonique et de stratégie.</span><span class="sxs-lookup"><span data-stu-id="e6915-118">[Skype for Business PowerShell module](https://www.microsoft.com/download/details.aspx?id=39366): The Skype for Business PowerShell module contains the cmdlets to manage meetings, phone system, and policies features.</span></span>

<span data-ttu-id="e6915-119">Pour consulter un guide complet de la gestion d’équipes à l’aide de ces modules, voir [gérer les équipes grâce aux équipes PowerShell](teams-powershell-managing-teams.md).</span><span class="sxs-lookup"><span data-stu-id="e6915-119">For a complete guide to managing Teams using these modules, please see [Manage Teams with Teams PowerShell](teams-powershell-managing-teams.md).</span></span>

> [!NOTE]
> <span data-ttu-id="e6915-120">La [version d’évaluation publique PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/) la plus récente est intégrée au connecteur Skype entreprise Online pour proposer un module unique pour la gestion d’teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e6915-120">The latest [Teams PowerShell public preview release](https://www.powershellgallery.com/packages/MicrosoftTeams/) is integrated with Skype for Business Online Connector, providing a single module for Teams PowerShell management.</span></span>

## <a name="related-topics"></a><span data-ttu-id="e6915-121">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="e6915-121">Related topics</span></span>

[<span data-ttu-id="e6915-122">Installation de PowerShell teams</span><span class="sxs-lookup"><span data-stu-id="e6915-122">Installing Teams PowerShell</span></span>](teams-powershell-install.md)

[<span data-ttu-id="e6915-123">Gestion des équipes avec PowerShell teams</span><span class="sxs-lookup"><span data-stu-id="e6915-123">Managing Teams with Teams PowerShell</span></span>](teams-powershell-managing-teams.md)

[<span data-ttu-id="e6915-124">Notes de publication teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="e6915-124">Teams PowerShell Release Notes</span></span>](teams-powershell-release-notes.md)

[<span data-ttu-id="e6915-125">Référence sur les applets de passe Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="e6915-125">Microsoft Teams cmdlet reference</span></span>](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[<span data-ttu-id="e6915-126">Référence sur les applets de fonction Skype entreprise</span><span class="sxs-lookup"><span data-stu-id="e6915-126">Skype for Business cmdlet reference</span></span>](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)

[<span data-ttu-id="e6915-127">Utiliser des rôles d’administrateur de Microsoft Teams pour gérer Teams</span><span class="sxs-lookup"><span data-stu-id="e6915-127">Use Microsoft Teams admin roles to manage Teams</span></span>](using-admin-roles.md)
