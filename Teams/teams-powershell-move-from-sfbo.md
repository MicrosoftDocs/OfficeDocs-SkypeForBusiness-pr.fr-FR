---
title: Basculer entre le connecteur Skype entreprise Online et le module PowerShell teams
author: pupara
ms.author: pupara
ms.reviewer: pupara
manager: bulenteg
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: Découvrez comment passer du connecteur Skype entreprise Online au module PowerShell teams pour gérer Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4e1838540e57cd91578e898818e2ed12e7b63a78
ms.sourcegitcommit: 51d94d621e3411f35622e852b699275f526600dd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/15/2020
ms.locfileid: "48469665"
---
# <a name="move-from-skype-for-business-online-connector-to-the-teams-powershell-module"></a><span data-ttu-id="a5ebf-103">Basculer entre le connecteur Skype entreprise Online et le module PowerShell teams</span><span class="sxs-lookup"><span data-stu-id="a5ebf-103">Move from Skype for Business Online Connector to the Teams PowerShell module</span></span>

<span data-ttu-id="a5ebf-104">Pour passer de l’utilisation du connecteur Skype entreprise Online au module PowerShell teams pour gérer Teams, vous devez mettre à jour vos scripts PowerShell existants.</span><span class="sxs-lookup"><span data-stu-id="a5ebf-104">To move from using Skype for Business Online Connector to the Teams PowerShell module to manage Teams, you'll need to update your existing PowerShell scripts.</span></span> <span data-ttu-id="a5ebf-105">Cet article explique comment procéder.</span><span class="sxs-lookup"><span data-stu-id="a5ebf-105">This article explains how to do this.</span></span>

1. <span data-ttu-id="a5ebf-106">Installez le dernier module PowerShell Teams.</span><span class="sxs-lookup"><span data-stu-id="a5ebf-106">Install the latest Teams PowerShell module.</span></span> <span data-ttu-id="a5ebf-107">Pour connaître les étapes à suivre, voir [installer Microsoft teams PowerShell](teams-powershell-install.md).</span><span class="sxs-lookup"><span data-stu-id="a5ebf-107">For steps, see [Install Microsoft Teams Powershell](teams-powershell-install.md).</span></span>
2. <span data-ttu-id="a5ebf-108">Désinstaller un connecteur Skype entreprise online.</span><span class="sxs-lookup"><span data-stu-id="a5ebf-108">Uninstall Skype For Business Online Connector.</span></span> <span data-ttu-id="a5ebf-109">Pour ce faire, dans le panneau de configuration, accédez à **programmes et fonctionnalités**, sélectionnez **Skype entreprise Online, module Windows PowerShell**, puis **désinstaller**.</span><span class="sxs-lookup"><span data-stu-id="a5ebf-109">To do this, in Control Panel, go **Programs and Features**, select **Skype for Business Online, Windows PowerShell Module**, and then select **Uninstall**.</span></span> 
3. <span data-ttu-id="a5ebf-110">Dans vos scripts PowerShell, modifiez le nom du module référencé dans ```Import-Module``` ```SkypeOnlineConnector``` ou ```LyncOnlineConnector``` à ```MicrosoftTeams``` .</span><span class="sxs-lookup"><span data-stu-id="a5ebf-110">In your PowerShell scripts, change the module name that's referenced in ```Import-Module``` from ```SkypeOnlineConnector``` or ```LyncOnlineConnector``` to ```MicrosoftTeams```.</span></span>

    <span data-ttu-id="a5ebf-111">Par exemple, remplacez ```Import-Module -Name SkypeOnlineConnector``` par ```Import-Module -Name MicrosoftTeams``` .</span><span class="sxs-lookup"><span data-stu-id="a5ebf-111">For example, change ```Import-Module -Name SkypeOnlineConnector``` to ```Import-Module -Name MicrosoftTeams```.</span></span>

> [!NOTE]
> <span data-ttu-id="a5ebf-112">Les administrateurs doivent continuer à utiliser [New-CsOnlineSession](https://docs.microsoft.com/powershell/module/skype/new-csonlinesession) et importer la session avant d’utiliser les applets de applet Skype entreprise online.</span><span class="sxs-lookup"><span data-stu-id="a5ebf-112">Admins should continue to use [New-CsOnlineSession](https://docs.microsoft.com/powershell/module/skype/new-csonlinesession) and import the session before using Skype for Business Online cmdlets.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="a5ebf-113">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="a5ebf-113">Related topics</span></span>

[<span data-ttu-id="a5ebf-114">Installer Microsoft teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="a5ebf-114">Install Microsoft Teams Powershell</span></span>](teams-powershell-install.md)

[<span data-ttu-id="a5ebf-115">Gestion des équipes avec PowerShell teams</span><span class="sxs-lookup"><span data-stu-id="a5ebf-115">Manage Teams with Teams PowerShell</span></span>](teams-powershell-managing-teams.md)

[<span data-ttu-id="a5ebf-116">Notes de publication teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="a5ebf-116">Teams PowerShell release notes</span></span>](teams-powershell-release-notes.md)

[<span data-ttu-id="a5ebf-117">Référence sur les applets de passe Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="a5ebf-117">Microsoft Teams cmdlet reference</span></span>](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[<span data-ttu-id="a5ebf-118">Référence sur les applets de fonction Skype entreprise</span><span class="sxs-lookup"><span data-stu-id="a5ebf-118">Skype for Business cmdlet reference</span></span>](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)
