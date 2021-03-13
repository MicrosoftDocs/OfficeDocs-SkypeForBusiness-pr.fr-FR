---
title: Vue d’ensemble de Microsoft Teams PowerShell
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
ms.openlocfilehash: 3ec9c9062a26442ae03a332f7cdd6f1e9b56cee5
ms.sourcegitcommit: da2a70a9b5e05d0fd7ecc150b451f5805667514c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/12/2021
ms.locfileid: "50756153"
---
# <a name="microsoft-teams-powershell-overview"></a><span data-ttu-id="668c5-103">Vue d’ensemble de Microsoft Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="668c5-103">Microsoft Teams PowerShell Overview</span></span>

<span data-ttu-id="668c5-104">Microsoft Teams PowerShell est un ensemble d’lets de commande qui vous aide à gérer Teams directement à partir de la ligne de commande PowerShell.</span><span class="sxs-lookup"><span data-stu-id="668c5-104">Microsoft Teams PowerShell is a set of cmdlets for managing Teams directly from the PowerShell command line.</span></span> <span data-ttu-id="668c5-105">Écrit dans .NET Standard, Teams PowerShell fonctionne sur PowerShell 5.1 sur Windows, PowerShell 6.x et les systèmes plus élevés sur toutes les plateformes, y compris Azure Cloud Shell.</span><span class="sxs-lookup"><span data-stu-id="668c5-105">Written in .NET Standard, Teams PowerShell works on PowerShell 5.1 on Windows, PowerShell 6.x and higher on all platforms including Azure Cloud Shell.</span></span>

<span data-ttu-id="668c5-106">Avant de commencer à utiliser PowerShell, vous devez [l’installer.](teams-powershell-install.md)</span><span class="sxs-lookup"><span data-stu-id="668c5-106">Before you can start using PowerShell, you'll need to [install it](teams-powershell-install.md).</span></span> 

> [!WARNING]
> <span data-ttu-id="668c5-107">Il existe des problèmes connus avec PowerShell 7 et Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="668c5-107">There are known issues with PowerShell 7 and Teams PowerShell.</span></span> <span data-ttu-id="668c5-108">Nous vous recommandons d’utiliser PowerShell 5.1 jusqu’à ce que les problèmes soient résolus.</span><span class="sxs-lookup"><span data-stu-id="668c5-108">We recommend using PowerShell 5.1 until the issues are resolved.</span></span>

## <a name="releases"></a><span data-ttu-id="668c5-109">Publication</span><span class="sxs-lookup"><span data-stu-id="668c5-109">Releases</span></span>


<span data-ttu-id="668c5-110">Teams PowerShell est disponible dans la [galerie PowerShell en](https://www.powershellgallery.com/packages/MicrosoftTeams) deux types.</span><span class="sxs-lookup"><span data-stu-id="668c5-110">Teams PowerShell is available on [PowerShell Gallery](https://www.powershellgallery.com/packages/MicrosoftTeams) in two release types.</span></span>

- <span data-ttu-id="668c5-111">**Disponibilité générale (GA)**: cmdlets prêtes pour la production, mises à jour tous les mois.</span><span class="sxs-lookup"><span data-stu-id="668c5-111">**General Availability (GA)**: Production-ready cmdlets, updated monthly.</span></span>

- <span data-ttu-id="668c5-112">**Aperçu public :** Accès en avant-première aux fonctionnalités.</span><span class="sxs-lookup"><span data-stu-id="668c5-112">**Public Preview**: Early access to features.</span></span> <span data-ttu-id="668c5-113">Peut être mis à jour plus fréquemment que GA.</span><span class="sxs-lookup"><span data-stu-id="668c5-113">May be updated more frequently than GA.</span></span>

<span data-ttu-id="668c5-114">Pour plus d’informations sur les ajouts de fonctionnalités et les améliorations apportées aux deux version, lisez les notes de publication [Teams PowerShell.](teams-powershell-release-notes.md)</span><span class="sxs-lookup"><span data-stu-id="668c5-114">For detailed information on feature additions and improvements for both releases, read the [Teams PowerShell release notes](teams-powershell-release-notes.md).</span></span>


## <a name="manage-teams-with-powershell"></a><span data-ttu-id="668c5-115">Gérer Teams avec PowerShell</span><span class="sxs-lookup"><span data-stu-id="668c5-115">Manage Teams with PowerShell</span></span>

<span data-ttu-id="668c5-116">Vous utiliserez les modules Teams PowerShell pour gérer entièrement Teams :</span><span class="sxs-lookup"><span data-stu-id="668c5-116">You'll use Teams PowerShell modules to fully manage Teams:</span></span>

- <span data-ttu-id="668c5-117">[Module Microsoft Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/): le module Teams PowerShell contient des cmdlets pour la gestion des équipes, des discussions et des canaux.</span><span class="sxs-lookup"><span data-stu-id="668c5-117">[Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams/): The Teams PowerShell module contains cmdlets for managing teams, chat, and channels.</span></span>

> [!NOTE]
> <span data-ttu-id="668c5-118">La version 1.1.6 ou ultérieure de [Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/) est intégrée à Skype Entreprise Online Connector et fournit un module unique pour la gestion de Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="668c5-118">The [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/) version 1.1.6 or later is integrated with Skype for Business Online Connector, providing a single module for Teams PowerShell management.</span></span>

- <span data-ttu-id="668c5-119">[Connecteur PowerShell Skype](https://docs.microsoft.com/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell)Entreprise : Le connecteur PowerShell Skype Entreprise fait désormais partie du module Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="668c5-119">[Skype for Business PowerShell Connector](https://docs.microsoft.com/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell): The Skype for Business PowerShell connector is now a part of Teams PowerShell module.</span></span>

<span data-ttu-id="668c5-120">Pour consulter un guide complet de la gestion de Teams à l’aide de ces modules, voir [Gérer Teams avec Teams PowerShell.](teams-powershell-managing-teams.md)</span><span class="sxs-lookup"><span data-stu-id="668c5-120">For a complete guide to managing Teams using these modules, please see [Manage Teams with Teams PowerShell](teams-powershell-managing-teams.md).</span></span>


## <a name="related-topics"></a><span data-ttu-id="668c5-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="668c5-121">Related topics</span></span>

[<span data-ttu-id="668c5-122">Installation de Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="668c5-122">Installing Teams PowerShell</span></span>](teams-powershell-install.md)

[<span data-ttu-id="668c5-123">Gestion des équipes avec Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="668c5-123">Managing Teams with Teams PowerShell</span></span>](teams-powershell-managing-teams.md)

[<span data-ttu-id="668c5-124">Notes de publication de Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="668c5-124">Teams PowerShell Release Notes</span></span>](teams-powershell-release-notes.md)

[<span data-ttu-id="668c5-125">Référence de l’cmdlet Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="668c5-125">Microsoft Teams cmdlet reference</span></span>](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[<span data-ttu-id="668c5-126">Référence de l’cmdlet Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="668c5-126">Skype for Business cmdlet reference</span></span>](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)

[<span data-ttu-id="668c5-127">Utiliser des rôles d’administrateur de Microsoft Teams pour gérer Teams</span><span class="sxs-lookup"><span data-stu-id="668c5-127">Use Microsoft Teams admin roles to manage Teams</span></span>](using-admin-roles.md)
