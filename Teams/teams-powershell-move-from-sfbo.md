---
title: Passer de Skype Entreprise Online Connector au module Teams PowerShell
author: pupara
ms.author: pupara
ms.reviewer: pupara
manager: bulenteg
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: Découvrez comment passer de Skype Entreprise Online Connector au module Teams PowerShell pour gérer Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5a2b502edc84c853a0a140a11f8c028b7c78aca6
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094125"
---
# <a name="move-from-skype-for-business-online-connector-to-the-teams-powershell-module"></a><span data-ttu-id="6e787-103">Passer de Skype Entreprise Online Connector au module Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="6e787-103">Move from Skype for Business Online Connector to the Teams PowerShell module</span></span>

<span data-ttu-id="6e787-104">Pour passer de l’utilisation de Skype Entreprise Online Connector au module Teams PowerShell afin de gérer Teams, vous devez mettre à jour vos scripts PowerShell existants.</span><span class="sxs-lookup"><span data-stu-id="6e787-104">To move from using Skype for Business Online Connector to the Teams PowerShell module to manage Teams, you'll need to update your existing PowerShell scripts.</span></span> <span data-ttu-id="6e787-105">Cet article explique comment faire.</span><span class="sxs-lookup"><span data-stu-id="6e787-105">This article explains how to do this.</span></span>

1. <span data-ttu-id="6e787-106">Installez le module Teams PowerShell le plus récent.</span><span class="sxs-lookup"><span data-stu-id="6e787-106">Install the latest Teams PowerShell module.</span></span> <span data-ttu-id="6e787-107">Pour consulter la procédure, [voir Installer Microsoft Teams PowerShell.](teams-powershell-install.md)</span><span class="sxs-lookup"><span data-stu-id="6e787-107">For steps, see [Install Microsoft Teams Powershell](teams-powershell-install.md).</span></span>
2. <span data-ttu-id="6e787-108">Désinstallez Skype Entreprise Online Connector.</span><span class="sxs-lookup"><span data-stu-id="6e787-108">Uninstall Skype For Business Online Connector.</span></span> <span data-ttu-id="6e787-109">Pour ce faire, dans le Panneau de contrôle, sélectionnez Programmes et fonctionnalités, Skype Entreprise **Online, Windows PowerShell Module,** puis **Désinstaller.**</span><span class="sxs-lookup"><span data-stu-id="6e787-109">To do this, in Control Panel, go **Programs and Features**, select **Skype for Business Online, Windows PowerShell Module**, and then select **Uninstall**.</span></span> 
3. <span data-ttu-id="6e787-110">Dans vos scripts PowerShell, modifiez le nom du module référencé. ```Import-Module``` ```SkypeOnlineConnector``` ```LyncOnlineConnector``` ```MicrosoftTeams```</span><span class="sxs-lookup"><span data-stu-id="6e787-110">In your PowerShell scripts, change the module name that's referenced in ```Import-Module``` from ```SkypeOnlineConnector``` or ```LyncOnlineConnector``` to ```MicrosoftTeams```.</span></span>

    <span data-ttu-id="6e787-111">Par exemple, ```Import-Module -Name SkypeOnlineConnector``` changez pour ```Import-Module -Name MicrosoftTeams``` .</span><span class="sxs-lookup"><span data-stu-id="6e787-111">For example, change ```Import-Module -Name SkypeOnlineConnector``` to ```Import-Module -Name MicrosoftTeams```.</span></span>
4. <span data-ttu-id="6e787-112">Lorsque vous utilisez Teams PowerShell Module 2.0 ou une génération ultérieure, modifiez New-csOnlineSession en Connect-MicrosoftTeams.</span><span class="sxs-lookup"><span data-stu-id="6e787-112">When using Teams PowerShell Module 2.0 or later, change New-csOnlineSession to Connect-MicrosoftTeams.</span></span> 

```powershell
  # When using Teams PowerShell Module 1.1.6
   Import-Module MicrosoftTeams
   $credential = Get-Credential
   $sfbSession = New-CsOnlineSession -Credential $credential
   Import-PSSession $sfbSession
   
   # When using Teams PowerShell Module 2.0 or later
   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```

## <a name="related-topics"></a><span data-ttu-id="6e787-113">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="6e787-113">Related topics</span></span>

[<span data-ttu-id="6e787-114">Installer Microsoft Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="6e787-114">Install Microsoft Teams Powershell</span></span>](teams-powershell-install.md)

[<span data-ttu-id="6e787-115">Gérer Teams avec Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="6e787-115">Manage Teams with Teams PowerShell</span></span>](teams-powershell-managing-teams.md)

[<span data-ttu-id="6e787-116">Notes de publication de Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="6e787-116">Teams PowerShell release notes</span></span>](teams-powershell-release-notes.md)

[<span data-ttu-id="6e787-117">Référence de l’cmdlet Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6e787-117">Microsoft Teams cmdlet reference</span></span>](/powershell/teams/?view=teams-ps)

[<span data-ttu-id="6e787-118">Référence de l’cmdlet Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="6e787-118">Skype for Business cmdlet reference</span></span>](/powershell/skype/intro?view=skype-ps)