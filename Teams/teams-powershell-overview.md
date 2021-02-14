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
ms.openlocfilehash: 12360110df90fb5de2e3e4547534c8569cc5537a
ms.sourcegitcommit: 3f465eb6eb46db008f2b69fc4c6bb425d432dfcc
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48852155"
---
# <a name="microsoft-teams-powershell-overview"></a><span data-ttu-id="ba556-103">Vue d’ensemble de Microsoft Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="ba556-103">Microsoft Teams PowerShell Overview</span></span>

<span data-ttu-id="ba556-104">Microsoft Teams PowerShell est un ensemble d’lets de commande qui vous aide à gérer Teams directement à partir de la ligne de commande PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ba556-104">Microsoft Teams PowerShell is a set of cmdlets for managing Teams directly from the PowerShell command line.</span></span> <span data-ttu-id="ba556-105">Écrit dans .NET Standard, Teams PowerShell fonctionne sur PowerShell 5.1 sur Windows, PowerShell 6.x et les systèmes plus élevés sur toutes les plateformes, y compris Azure Cloud Shell.</span><span class="sxs-lookup"><span data-stu-id="ba556-105">Written in .NET Standard, Teams PowerShell works on PowerShell 5.1 on Windows, PowerShell 6.x and higher on all platforms including Azure Cloud Shell.</span></span>

<span data-ttu-id="ba556-106">Avant de commencer à utiliser PowerShell, vous devez [l’installer.](teams-powershell-install.md)</span><span class="sxs-lookup"><span data-stu-id="ba556-106">Before you can start using PowerShell, you'll need to [install it](teams-powershell-install.md).</span></span> 

> [!WARNING]
> <span data-ttu-id="ba556-107">Il existe des problèmes connus avec PowerShell 7 et Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ba556-107">There are known issues with PowerShell 7 and Teams PowerShell.</span></span> <span data-ttu-id="ba556-108">Nous vous recommandons d’utiliser PowerShell 5.1 jusqu’à ce que les problèmes soient résolus.</span><span class="sxs-lookup"><span data-stu-id="ba556-108">We recommend using PowerShell 5.1 until the issues are resolved.</span></span>

## <a name="releases"></a><span data-ttu-id="ba556-109">Publication</span><span class="sxs-lookup"><span data-stu-id="ba556-109">Releases</span></span>


<span data-ttu-id="ba556-110">Teams PowerShell est disponible dans la [galerie PowerShell en](https://www.powershellgallery.com/packages/MicrosoftTeams) deux types.</span><span class="sxs-lookup"><span data-stu-id="ba556-110">Teams PowerShell is available on [PowerShell Gallery](https://www.powershellgallery.com/packages/MicrosoftTeams) in two release types.</span></span>

- <span data-ttu-id="ba556-111">**Disponibilité générale (GA)**: cmdlets prêtes pour la production, mises à jour tous les mois.</span><span class="sxs-lookup"><span data-stu-id="ba556-111">**General Availability (GA)**: Production-ready cmdlets, updated monthly.</span></span>

- <span data-ttu-id="ba556-112">**Prévisualisation** publique : Accès précoce aux fonctionnalités.</span><span class="sxs-lookup"><span data-stu-id="ba556-112">**Public Preview**: Early access to features.</span></span> <span data-ttu-id="ba556-113">Peut être mis à jour plus fréquemment que GA.</span><span class="sxs-lookup"><span data-stu-id="ba556-113">May be updated more frequently than GA.</span></span>

<span data-ttu-id="ba556-114">Pour plus d’informations sur les ajouts de fonctionnalités et les améliorations apportées aux deux version, lisez les notes de publication [Teams PowerShell.](teams-powershell-release-notes.md)</span><span class="sxs-lookup"><span data-stu-id="ba556-114">For detailed information on feature additions and improvements for both releases, read the [Teams PowerShell release notes](teams-powershell-release-notes.md).</span></span>


## <a name="manage-teams-with-powershell"></a><span data-ttu-id="ba556-115">Gérer Teams avec PowerShell</span><span class="sxs-lookup"><span data-stu-id="ba556-115">Manage Teams with PowerShell</span></span>

<span data-ttu-id="ba556-116">Vous utiliserez les modules Teams PowerShell pour gérer entièrement Teams :</span><span class="sxs-lookup"><span data-stu-id="ba556-116">You'll use Teams PowerShell modules to fully manage Teams:</span></span>

- <span data-ttu-id="ba556-117">[Module Microsoft Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/): le module Teams PowerShell contient des cmdlets pour la gestion des équipes, des discussions et des canaux.</span><span class="sxs-lookup"><span data-stu-id="ba556-117">[Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams/): The Teams PowerShell module contains cmdlets for managing teams, chat, and channels.</span></span>

> [!NOTE]
> <span data-ttu-id="ba556-118">La dernière version [publique de Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/) est intégrée à Skype Entreprise Online Connector et fournit un seul module pour la gestion de Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ba556-118">The latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/) is integrated with Skype for Business Online Connector, providing a single module for Teams PowerShell management.</span></span>

- <span data-ttu-id="ba556-119">[Connecteur PowerShell Skype Entreprise](https://www.microsoft.com/download/details.aspx?id=39366): Le connecteur Skype Entreprise PowerShell fait désormais partie du module Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ba556-119">[Skype for Business PowerShell Connector](https://www.microsoft.com/download/details.aspx?id=39366): The Skype for Business PowerShell connector is now a part of Teams PowerShell module.</span></span>

<span data-ttu-id="ba556-120">Pour consulter un guide complet de la gestion de Teams à l’aide de ces modules, voir [Gérer Teams avec Teams PowerShell.](teams-powershell-managing-teams.md)</span><span class="sxs-lookup"><span data-stu-id="ba556-120">For a complete guide to managing Teams using these modules, please see [Manage Teams with Teams PowerShell](teams-powershell-managing-teams.md).</span></span>


## <a name="related-topics"></a><span data-ttu-id="ba556-121">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="ba556-121">Related topics</span></span>

[<span data-ttu-id="ba556-122">Installation de Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="ba556-122">Installing Teams PowerShell</span></span>](teams-powershell-install.md)

[<span data-ttu-id="ba556-123">Gestion des équipes avec Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="ba556-123">Managing Teams with Teams PowerShell</span></span>](teams-powershell-managing-teams.md)

[<span data-ttu-id="ba556-124">Notes de publication de Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="ba556-124">Teams PowerShell Release Notes</span></span>](teams-powershell-release-notes.md)

[<span data-ttu-id="ba556-125">Référence de l’cmdlet Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ba556-125">Microsoft Teams cmdlet reference</span></span>](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[<span data-ttu-id="ba556-126">Référence de l’cmdlet Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="ba556-126">Skype for Business cmdlet reference</span></span>](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)

[<span data-ttu-id="ba556-127">Utiliser des rôles d’administrateur de Microsoft Teams pour gérer Teams</span><span class="sxs-lookup"><span data-stu-id="ba556-127">Use Microsoft Teams admin roles to manage Teams</span></span>](using-admin-roles.md)
