---
title: Créer des équipes du gestionnaire de personnes dans Microsoft teams
ms.reviewer: pbethi
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
description: Découvrez comment utiliser un script PowerShell pour créer une équipe pour chaque responsable en tant que membre de l’équipe.
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: fe57656eec61747dd0a43d475444e65d8600e222
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/06/2020
ms.locfileid: "46583673"
---
# <a name="create-people-manager-teams-in-microsoft-teams"></a><span data-ttu-id="05660-103">Créer des équipes du gestionnaire de personnes dans Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="05660-103">Create people manager teams in Microsoft Teams</span></span>


<span data-ttu-id="05660-104">Lorsque vous déployez Microsoft teams au lieu d’un « ardoise vierge » (sans équipes ou canaux), nous vous recommandons vivement de définir une infrastructure de base des équipes et des canaux.</span><span class="sxs-lookup"><span data-stu-id="05660-104">When you roll out Microsoft Teams, rather than launching with a "blank slate" (no teams or channels), we strongly recommend that you set up a base framework of teams and channels.</span></span> <span data-ttu-id="05660-105">Cela permet d’éviter une « prolifération des équipes », qui permet aux utilisateurs de créer de nombreuses équipes lorsqu’elles doivent créer des canaux dans les équipes existantes.</span><span class="sxs-lookup"><span data-stu-id="05660-105">This helps to prevent "team sprawl," where users create numerous teams when they should be creating channels in existing teams.</span></span> <span data-ttu-id="05660-106">Pour vous aider à prendre en main une structure d’équipes et de canaux bien conçue, nous avons créé un script PowerShell permettant de créer une équipe pour chacun de vos premiers et deuxièmes responsables de personnes, avec les rapports directs de chaque responsable en tant que membres de l’équipe.</span><span class="sxs-lookup"><span data-stu-id="05660-106">To help you get started with a well-designed teams and channels structure, we've created a PowerShell script that creates a team for each of your first and second line people managers, with each manager's direct reports as team members.</span></span> <span data-ttu-id="05660-107">Il s’agit d’un script « ponctuelle » (il n’est pas mis à jour automatiquement pour les équipes ou les canaux lors de l’ajout ou de la suppression de personnes d’une organisation).</span><span class="sxs-lookup"><span data-stu-id="05660-107">This is a "point-in-time" script (it doesn't update your teams or channels automatically when people are added or removed from an organization).</span></span> <span data-ttu-id="05660-108">C’est un outil précieux qui peut être utilisé pour imposer une commande dans votre structure teams depuis le début.</span><span class="sxs-lookup"><span data-stu-id="05660-108">But it's a valuable tool you can use to impose some order on your Teams structure from the start.</span></span> <span data-ttu-id="05660-109">Ce script lit votre Azure AD et obtient la liste des responsables et leurs rapports directs.</span><span class="sxs-lookup"><span data-stu-id="05660-109">This script reads your Azure AD, gets a list of managers and their direct reports.</span></span> <span data-ttu-id="05660-110">Il utilise cette liste pour créer une équipe par responsable de personnes.</span><span class="sxs-lookup"><span data-stu-id="05660-110">It uses this list to create one team per people manager.</span></span> 

## <a name="how-to-use-the-powershell-script"></a><span data-ttu-id="05660-111">Utiliser le script PowerShell</span><span class="sxs-lookup"><span data-stu-id="05660-111">How to use the PowerShell script</span></span> 

<span data-ttu-id="05660-112">Commencez par exécuter les [responsables d’exportation et leurs scripts de direction](scripts/powershell-script-create-teams-from-managers-export-managers.md) (ce qui suppose que vous avez déjà exécuté les modules [AzureAd](https://docs.microsoft.com/powershell/module/azuread/connect-azuread?view=azureadps-2.0) et [Connect-MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams?view=teams-ps) PowerShell).</span><span class="sxs-lookup"><span data-stu-id="05660-112">Start by running the [Export managers and their directs script](scripts/powershell-script-create-teams-from-managers-export-managers.md) (which assumes you've already run the [Connect-AzureAd](https://docs.microsoft.com/powershell/module/azuread/connect-azuread?view=azureadps-2.0) and [Connect-MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams?view=teams-ps) PowerShell modules).</span></span> <span data-ttu-id="05660-113">Les *gestionnaires d’exportation et leurs* scripts de direction créent un fichier délimité par des tabulations (ExportedManagerDirects.txt) qui recense tous les responsables avec leurs rapports directs.</span><span class="sxs-lookup"><span data-stu-id="05660-113">The *Export managers and their directs* script creates a tab-delimited file (ExportedManagerDirects.txt) that lists all managers with their direct reports.</span></span> 

<span data-ttu-id="05660-114">Ensuite, exécutez le [script créer de nouvelles équipes du gestionnaire de personnes](scripts/powershell-script-create-teams-from-managers-new-teams.md).</span><span class="sxs-lookup"><span data-stu-id="05660-114">Then, run the [Create new people manager teams script](scripts/powershell-script-create-teams-from-managers-new-teams.md).</span></span> <span data-ttu-id="05660-115">Ce script lit le fichier ExportedManagerDirects.txt et crée une équipe pour chaque responsable, avec ses rapports directs en tant que membres.</span><span class="sxs-lookup"><span data-stu-id="05660-115">This script reads in the ExportedManagerDirects.txt file and creates a team for each manager, with that manager's direct reports as members.</span></span> <span data-ttu-id="05660-116">Si un responsable ou une direction n’est pas activé pour Teams, le script les ignore et ne crée aucune équipe.</span><span class="sxs-lookup"><span data-stu-id="05660-116">If any manager or direct isn't enabled for Teams, the script skips them and doesn't create a team.</span></span> <span data-ttu-id="05660-117">(Consultez le rapport, puis relancez le script une fois que vous avez activé les équipes pour toute personne qui en a besoin.</span><span class="sxs-lookup"><span data-stu-id="05660-117">(Review the report, then rerun the script after you've turned on Teams for anybody who needs it.</span></span> <span data-ttu-id="05660-118">Le script ne crée pas de deuxième équipe pour les gestionnaires pour lesquels il a déjà créé une équipe.)</span><span class="sxs-lookup"><span data-stu-id="05660-118">The script won't create a second team for any manager it's already created a team for.)</span></span>

<span data-ttu-id="05660-119">S’il s’agit d’une équipe, le script crée une chaîne générale et « pour plaisir ».</span><span class="sxs-lookup"><span data-stu-id="05660-119">For each team, the script creates a General and "Just for fun" channel.</span></span> 

## <a name="best-practices"></a><span data-ttu-id="05660-120">Meilleures pratiques</span><span class="sxs-lookup"><span data-stu-id="05660-120">Best practices</span></span>

- <span data-ttu-id="05660-121">Demandez à chaque gestionnaire de personnes d’ajouter le site Web de communication de crise de votre organisation en tant qu’onglet au canal général de chaque équipe.</span><span class="sxs-lookup"><span data-stu-id="05660-121">Ask each people manager to add your organization's crisis communications website as a tab to the General channel for each team.</span></span> 

- <span data-ttu-id="05660-122">Consultez la nouvelle application de communications de crise en lisant ce 8 mars, billet de blog 2020 : [coordonner les communications de crise à l’aide de Microsoft teams + Power Platform](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/coordinate-crisis-communications-using-microsoft-teams-power/ba-p/1216715).</span><span class="sxs-lookup"><span data-stu-id="05660-122">Check out the new Crisis Communications app by reading this March 8, 2020 blog post: [Coordinate crisis communications using Microsoft Teams + Power Platform](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/coordinate-crisis-communications-using-microsoft-teams-power/ba-p/1216715).</span></span>

## <a name="related-topics"></a><span data-ttu-id="05660-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="05660-123">Related topics</span></span>

[<span data-ttu-id="05660-124">Recommandations en matière d’organisation des équipes</span><span class="sxs-lookup"><span data-stu-id="05660-124">Best practices for organizing teams</span></span>](best-practices-organizing.md)

[<span data-ttu-id="05660-125">Créer une équipe à l’échelle de l’organisation dans Teams</span><span class="sxs-lookup"><span data-stu-id="05660-125">Create an org-wide team in Teams</span></span>](create-an-org-wide-team.md)
