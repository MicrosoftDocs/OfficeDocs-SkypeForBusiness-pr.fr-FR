---
title: Microsoft Teams Vue d’ensemble de PowerShell
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
description: Découvrez comment utiliser les contrôles PowerShell pour gérer les Microsoft Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 448658fb844052815e14b85e0c70a33cb737b72d
ms.sourcegitcommit: 616403037ddb2d44f06cd9b2eaa9da699b119ef8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/15/2021
ms.locfileid: "51768353"
---
# <a name="microsoft-teams-powershell-overview"></a><span data-ttu-id="c18a5-103">Microsoft Teams Vue d’ensemble de PowerShell</span><span class="sxs-lookup"><span data-stu-id="c18a5-103">Microsoft Teams PowerShell Overview</span></span>

<span data-ttu-id="c18a5-104">Microsoft Teams PowerShell est un ensemble d’lets de commande qui vous Teams gérer vos commandes directement à partir de la ligne de commande PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c18a5-104">Microsoft Teams PowerShell is a set of cmdlets for managing Teams directly from the PowerShell command line.</span></span> <span data-ttu-id="c18a5-105">Écrit dans .NET Standard, Teams PowerShell fonctionne sur PowerShell 5.1 sur Windows, PowerShell 6.x et les plateformes supérieures, y compris Azure Cloud Shell.</span><span class="sxs-lookup"><span data-stu-id="c18a5-105">Written in .NET Standard, Teams PowerShell works on PowerShell 5.1 on Windows, PowerShell 6.x and higher on all platforms including Azure Cloud Shell.</span></span>

<span data-ttu-id="c18a5-106">Avant de commencer à utiliser PowerShell, vous devez [l’installer.](teams-powershell-install.md)</span><span class="sxs-lookup"><span data-stu-id="c18a5-106">Before you can start using PowerShell, you'll need to [install it](teams-powershell-install.md).</span></span> 

> [!WARNING]
> <span data-ttu-id="c18a5-107">Certains problèmes connus sur PowerShell 7 et Teams PowerShell sont connus.</span><span class="sxs-lookup"><span data-stu-id="c18a5-107">There are known issues with PowerShell 7 and Teams PowerShell.</span></span> <span data-ttu-id="c18a5-108">Nous vous recommandons d’utiliser PowerShell 5.1 jusqu’à ce que les problèmes soient résolus.</span><span class="sxs-lookup"><span data-stu-id="c18a5-108">We recommend using PowerShell 5.1 until the issues are resolved.</span></span>

## <a name="releases"></a><span data-ttu-id="c18a5-109">Publication</span><span class="sxs-lookup"><span data-stu-id="c18a5-109">Releases</span></span>


<span data-ttu-id="c18a5-110">Teams PowerShell est disponible dans la [galerie PowerShell en](https://www.powershellgallery.com/packages/MicrosoftTeams) deux types.</span><span class="sxs-lookup"><span data-stu-id="c18a5-110">Teams PowerShell is available on [PowerShell Gallery](https://www.powershellgallery.com/packages/MicrosoftTeams) in two release types.</span></span>

- <span data-ttu-id="c18a5-111">**Disponibilité générale (GA)**: cmdlets prêtes pour la production, mises à jour tous les mois.</span><span class="sxs-lookup"><span data-stu-id="c18a5-111">**General Availability (GA)**: Production-ready cmdlets, updated monthly.</span></span>

- <span data-ttu-id="c18a5-112">**Aperçu public :** Accès en avant-première aux fonctionnalités.</span><span class="sxs-lookup"><span data-stu-id="c18a5-112">**Public Preview**: Early access to features.</span></span> <span data-ttu-id="c18a5-113">Peut être mis à jour plus fréquemment que GA.</span><span class="sxs-lookup"><span data-stu-id="c18a5-113">May be updated more frequently than GA.</span></span>

<span data-ttu-id="c18a5-114">Pour plus d’informations sur les ajouts de fonctionnalités et les améliorations apportées aux deux version, lisez les Teams de [publication de PowerShell.](teams-powershell-release-notes.md)</span><span class="sxs-lookup"><span data-stu-id="c18a5-114">For detailed information on feature additions and improvements for both releases, read the [Teams PowerShell release notes](teams-powershell-release-notes.md).</span></span>


## <a name="manage-teams-with-powershell"></a><span data-ttu-id="c18a5-115">Gérer Teams avec PowerShell</span><span class="sxs-lookup"><span data-stu-id="c18a5-115">Manage Teams with PowerShell</span></span>

<span data-ttu-id="c18a5-116">Vous utiliserez les modules PowerShell Teams pour gérer entièrement les Teams :</span><span class="sxs-lookup"><span data-stu-id="c18a5-116">You'll use Teams PowerShell modules to fully manage Teams:</span></span>

- <span data-ttu-id="c18a5-117">[Microsoft Teams module PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/): le module PowerShell Teams des cmdlets pour la gestion des équipes, des discussions et des canaux.</span><span class="sxs-lookup"><span data-stu-id="c18a5-117">[Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams/): The Teams PowerShell module contains cmdlets for managing teams, chat, and channels.</span></span>

> [!NOTE]
> <span data-ttu-id="c18a5-118">La Teams version publique [de PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/) 2.0 ou version supérieure inclut toutes les cmdlets Skype Entreprise Online Connector, fournissant un seul module pour la gestion Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c18a5-118">The [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/) version 2.0 or higher includes all  Skype for Business Online Connector cmdlets, providing a single module for Teams PowerShell management.</span></span>

- <span data-ttu-id="c18a5-119">[Skype Entreprise Connecteur PowerShell :](/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell)le connecteur PowerShell Skype Entreprise fait désormais partie d’Teams module PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c18a5-119">[Skype for Business PowerShell Connector](/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell): The Skype for Business PowerShell connector is now a part of Teams PowerShell module.</span></span>

<span data-ttu-id="c18a5-120">Pour consulter un guide complet de gestion Teams l’aide de ces modules, voir Gérer les Teams [avec Teams PowerShell.](teams-powershell-managing-teams.md)</span><span class="sxs-lookup"><span data-stu-id="c18a5-120">For a complete guide to managing Teams using these modules, please see [Manage Teams with Teams PowerShell](teams-powershell-managing-teams.md).</span></span>


## <a name="related-topics"></a><span data-ttu-id="c18a5-121">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="c18a5-121">Related topics</span></span>

[<span data-ttu-id="c18a5-122">Installation Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="c18a5-122">Installing Teams PowerShell</span></span>](teams-powershell-install.md)

[<span data-ttu-id="c18a5-123">Gestion des Teams à l’Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="c18a5-123">Managing Teams with Teams PowerShell</span></span>](teams-powershell-managing-teams.md)

[<span data-ttu-id="c18a5-124">Teams Notes de publication de PowerShell</span><span class="sxs-lookup"><span data-stu-id="c18a5-124">Teams PowerShell Release Notes</span></span>](teams-powershell-release-notes.md)

[<span data-ttu-id="c18a5-125">Microsoft Teams des cmdlet</span><span class="sxs-lookup"><span data-stu-id="c18a5-125">Microsoft Teams cmdlet reference</span></span>](/powershell/teams/?view=teams-ps)

[<span data-ttu-id="c18a5-126">Skype Entreprise des cmdlet</span><span class="sxs-lookup"><span data-stu-id="c18a5-126">Skype for Business cmdlet reference</span></span>](/powershell/skype/intro?view=skype-ps)

[<span data-ttu-id="c18a5-127">Utiliser des rôles d’administrateur de Microsoft Teams pour gérer Teams</span><span class="sxs-lookup"><span data-stu-id="c18a5-127">Use Microsoft Teams admin roles to manage Teams</span></span>](using-admin-roles.md)
