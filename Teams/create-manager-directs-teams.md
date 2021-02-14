---
title: Créer des équipes de responsables de personnes dans Microsoft Teams
ms.reviewer: pbethi
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
description: Découvrez comment utiliser un script PowerShell pour créer une équipe pour chaque responsable avec ses directs en tant que membres de l’équipe.
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
# <a name="create-people-manager-teams-in-microsoft-teams"></a><span data-ttu-id="49592-103">Créer des équipes de responsables de personnes dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="49592-103">Create people manager teams in Microsoft Teams</span></span>


<span data-ttu-id="49592-104">Lorsque vous déployer Microsoft Teams, plutôt que de lancer avec une « page de vide » (pas d’équipes ni de canaux), nous vous recommandons vivement de configurer un cadre de base des équipes et des canaux.</span><span class="sxs-lookup"><span data-stu-id="49592-104">When you roll out Microsoft Teams, rather than launching with a "blank slate" (no teams or channels), we strongly recommend that you set up a base framework of teams and channels.</span></span> <span data-ttu-id="49592-105">Cela permet d’empêcher l'« événement d’équipe », car les utilisateurs créent de nombreuses équipes lorsqu’ils doivent créer des canaux dans des équipes existantes.</span><span class="sxs-lookup"><span data-stu-id="49592-105">This helps to prevent "team sprawl," where users create numerous teams when they should be creating channels in existing teams.</span></span> <span data-ttu-id="49592-106">Pour vous aider à commencer avec une structure d’équipes et de canaux bien conçue, nous avons créé un script PowerShell qui crée une équipe pour chacun de vos responsables de première et deuxième ligne, avec les rapports directs de chaque responsable en tant que membres de l’équipe.</span><span class="sxs-lookup"><span data-stu-id="49592-106">To help you get started with a well-designed teams and channels structure, we've created a PowerShell script that creates a team for each of your first and second line people managers, with each manager's direct reports as team members.</span></span> <span data-ttu-id="49592-107">Il s’agit d’un script « à un moment donné » (il ne met pas à jour vos équipes ou canaux automatiquement lorsque des personnes sont ajoutées ou supprimées d’une organisation).</span><span class="sxs-lookup"><span data-stu-id="49592-107">This is a "point-in-time" script (it doesn't update your teams or channels automatically when people are added or removed from an organization).</span></span> <span data-ttu-id="49592-108">Il s’agit toutefois d’un outil précieux que vous pouvez utiliser dès le départ pour imposer un ordre dans votre structure Teams.</span><span class="sxs-lookup"><span data-stu-id="49592-108">But it's a valuable tool you can use to impose some order on your Teams structure from the start.</span></span> <span data-ttu-id="49592-109">Ce script lit votre azure AD, reçoit une liste des responsables et leurs rapports directs.</span><span class="sxs-lookup"><span data-stu-id="49592-109">This script reads your Azure AD, gets a list of managers and their direct reports.</span></span> <span data-ttu-id="49592-110">Elle utilise cette liste pour créer une équipe par responsable de personnes.</span><span class="sxs-lookup"><span data-stu-id="49592-110">It uses this list to create one team per people manager.</span></span> 

## <a name="how-to-use-the-powershell-script"></a><span data-ttu-id="49592-111">Comment utiliser le script PowerShell</span><span class="sxs-lookup"><span data-stu-id="49592-111">How to use the PowerShell script</span></span> 

<span data-ttu-id="49592-112">Commencez par exécuter les responsables de l’exportation et leur script de [directs](scripts/powershell-script-create-teams-from-managers-export-managers.md) (qui suppose que vous avez déjà exécuté les modules [PowerShell Connect-AzureAd](https://docs.microsoft.com/powershell/module/azuread/connect-azuread?view=azureadps-2.0) et [Connect-MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams?view=teams-ps) PowerShell).</span><span class="sxs-lookup"><span data-stu-id="49592-112">Start by running the [Export managers and their directs script](scripts/powershell-script-create-teams-from-managers-export-managers.md) (which assumes you've already run the [Connect-AzureAd](https://docs.microsoft.com/powershell/module/azuread/connect-azuread?view=azureadps-2.0) and [Connect-MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams?view=teams-ps) PowerShell modules).</span></span> <span data-ttu-id="49592-113">Les *responsables de* l’exportation et leur script de direction créent un fichier délimité par des tabulations (ExportedManagerDirects.txt) qui répertorie tous les responsables avec leurs rapports directs.</span><span class="sxs-lookup"><span data-stu-id="49592-113">The *Export managers and their directs* script creates a tab-delimited file (ExportedManagerDirects.txt) that lists all managers with their direct reports.</span></span> 

<span data-ttu-id="49592-114">Ensuite, exécutez le [script Créer de nouvelles équipes de responsables de personnes.](scripts/powershell-script-create-teams-from-managers-new-teams.md)</span><span class="sxs-lookup"><span data-stu-id="49592-114">Then, run the [Create new people manager teams script](scripts/powershell-script-create-teams-from-managers-new-teams.md).</span></span> <span data-ttu-id="49592-115">Ce script est lu dans le ExportedManagerDirects.txt et crée une équipe pour chaque responsable, avec les rapports directs de ce responsable en tant que membres.</span><span class="sxs-lookup"><span data-stu-id="49592-115">This script reads in the ExportedManagerDirects.txt file and creates a team for each manager, with that manager's direct reports as members.</span></span> <span data-ttu-id="49592-116">Si un responsable ou un direct n’est pas activé pour Teams, le script les ignore et ne crée pas d’équipe.</span><span class="sxs-lookup"><span data-stu-id="49592-116">If any manager or direct isn't enabled for Teams, the script skips them and doesn't create a team.</span></span> <span data-ttu-id="49592-117">(Examinez le rapport, puis réexécutez le script après avoir désactivé Teams pour quiconque en a besoin.</span><span class="sxs-lookup"><span data-stu-id="49592-117">(Review the report, then rerun the script after you've turned on Teams for anybody who needs it.</span></span> <span data-ttu-id="49592-118">Le script ne crée pas de deuxième équipe pour un responsable pour qui il a déjà créé une équipe.)</span><span class="sxs-lookup"><span data-stu-id="49592-118">The script won't create a second team for any manager it's already created a team for.)</span></span>

<span data-ttu-id="49592-119">Pour chaque équipe, le script crée un canal Général et « Simplement pour le plaisir ».</span><span class="sxs-lookup"><span data-stu-id="49592-119">For each team, the script creates a General and "Just for fun" channel.</span></span> 

## <a name="best-practices"></a><span data-ttu-id="49592-120">Meilleures pratiques</span><span class="sxs-lookup"><span data-stu-id="49592-120">Best practices</span></span>

- <span data-ttu-id="49592-121">Demandez à chaque responsable d’ajouter le site web des communications de crise de votre organisation en tant qu’onglet au canal Général pour chaque équipe.</span><span class="sxs-lookup"><span data-stu-id="49592-121">Ask each people manager to add your organization's crisis communications website as a tab to the General channel for each team.</span></span> 

- <span data-ttu-id="49592-122">Consultez la nouvelle application Communications de crise en lisant ce billet de blog du 8 mars 2020 : Coordonnez la communication de crise à l’aide de [Microsoft Teams + Power Platform.](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/coordinate-crisis-communications-using-microsoft-teams-power/ba-p/1216715)</span><span class="sxs-lookup"><span data-stu-id="49592-122">Check out the new Crisis Communications app by reading this March 8, 2020 blog post: [Coordinate crisis communications using Microsoft Teams + Power Platform](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/coordinate-crisis-communications-using-microsoft-teams-power/ba-p/1216715).</span></span>

## <a name="related-topics"></a><span data-ttu-id="49592-123">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="49592-123">Related topics</span></span>

[<span data-ttu-id="49592-124">Meilleures pratiques pour organiser les équipes</span><span class="sxs-lookup"><span data-stu-id="49592-124">Best practices for organizing teams</span></span>](best-practices-organizing.md)

[<span data-ttu-id="49592-125">Créer une équipe à l’échelle de l’organisation dans Teams</span><span class="sxs-lookup"><span data-stu-id="49592-125">Create an org-wide team in Teams</span></span>](create-an-org-wide-team.md)
