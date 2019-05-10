---
title: Exécuter un rapport à afficher active StaffHub d’utilisation
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.date: 05/10/2019
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: Découvrez comment exécuter un rapport pour obtenir une liste d’utilisateurs StaffHub actifs dans votre organisation.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e66e889fbc7fb26b8fda55beb889bc95b155666d
ms.sourcegitcommit: b2acf18ba6487154ebb4ee46938e96dc56cb2c9a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/09/2019
ms.locfileid: "33868191"
---
# <a name="run-a-report-to-show-active-staffhub-usage"></a><span data-ttu-id="33a37-103">Exécuter un rapport à afficher active StaffHub d’utilisation</span><span class="sxs-lookup"><span data-stu-id="33a37-103">Run a report to show active StaffHub usage</span></span>

> [!IMPORTANT]
> <span data-ttu-id="33a37-104">Effet 2019, octobre 1, Microsoft StaffHub sera être retirée.</span><span class="sxs-lookup"><span data-stu-id="33a37-104">Effective October 1, 2019, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="33a37-105">Nous créons StaffHub fonctionnalités dans Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="33a37-105">We’re building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="33a37-106">Aujourd'hui, les équipes inclut l’application des équipes de gestion de la planification et des fonctionnalités supplémentaires seront intégrées au fil du temps.</span><span class="sxs-lookup"><span data-stu-id="33a37-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="33a37-107">StaffHub cessera de fonctionner pour tous les utilisateurs sur le 1 octobre 2019.</span><span class="sxs-lookup"><span data-stu-id="33a37-107">StaffHub will stop working for all users on October 1, 2019.</span></span> <span data-ttu-id="33a37-108">Toute personne qui essaie d’ouvrir StaffHub s’affichera un message pronom pour télécharger les équipes.</span><span class="sxs-lookup"><span data-stu-id="33a37-108">Anyone who tries to open StaffHub will be shown a message directing them to download Teams.</span></span> <span data-ttu-id="33a37-109">Pour plus d’informations, voir [Microsoft StaffHub à retirer](microsoft-staffhub-to-be-retired.md).</span><span class="sxs-lookup"><span data-stu-id="33a37-109">To learn more, see [Microsoft StaffHub to be retired](microsoft-staffhub-to-be-retired.md).</span></span>  

<span data-ttu-id="33a37-110">Utilisez les étapes décrites dans cet article pour exécuter un rapport pour obtenir une liste d’utilisateurs StaffHub actifs dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="33a37-110">Use the steps in this article to run a report to get a list of active StaffHub users in your organization.</span></span> <span data-ttu-id="33a37-111">Cette information peut être utile lorsque vous vous préparez à [déplacer vos équipes StaffHub aux équipes de Microsoft](move-staffhub-teams-to-shifts-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="33a37-111">This information may come in handy when you prepare to [move your StaffHub teams to Microsoft Teams](move-staffhub-teams-to-shifts-in-teams.md).</span></span> <span data-ttu-id="33a37-112">À partir du rapport, vous savez qui vous devez inclure dans vos communications lorsque vous effectuez le commutateur dans StaffHub aux équipes.</span><span class="sxs-lookup"><span data-stu-id="33a37-112">From the report, you'll know who you need to include in your communications when you make the switch from StaffHub to Teams.</span></span>

<span data-ttu-id="33a37-113">Vous devez disposer d’Azure AD Premium pour effectuer les étapes décrites dans cet article.</span><span class="sxs-lookup"><span data-stu-id="33a37-113">You need to have Azure AD Premium to perform the steps in this article.</span></span>

1. <span data-ttu-id="33a37-114">Connectez-vous au portail Azure.</span><span class="sxs-lookup"><span data-stu-id="33a37-114">Sign in to the Azure portal.</span></span>
2. <span data-ttu-id="33a37-115">Dans le volet gauche, cliquez sur la ressource **d’Azure Active Directory** .</span><span class="sxs-lookup"><span data-stu-id="33a37-115">In the left pane, click the **Azure Active Directory** resource.</span></span>
3. <span data-ttu-id="33a37-116">Sous **analyse**, cliquez sur **connexions**.</span><span class="sxs-lookup"><span data-stu-id="33a37-116">Under **Monitoring**, click **Sign-ins**.</span></span>
4. <span data-ttu-id="33a37-117">Sous **Application**, tapez **StaffHub Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="33a37-117">Under **Application**, type **Microsoft StaffHub**.</span></span>
5. <span data-ttu-id="33a37-118">Définir la plage de dates souhaitée pour le rapport, puis cliquez sur **Appliquer**.</span><span class="sxs-lookup"><span data-stu-id="33a37-118">Set the date range that you want for the report, and then click **Apply**.</span></span> 

    ![Capture d’écran montrant les étapes pour l’exécution de l’état affiche actif StaffHub d’utilisation dans le portail Azure](../../media/staffhub-active-usage-report.png)

## <a name="related-topics"></a><span data-ttu-id="33a37-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="33a37-120">Related topics</span></span>

- [<span data-ttu-id="33a37-121">Atteindre vos équipes Microsoft StaffHub équipes dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="33a37-121">Move your Microsoft StaffHub teams to Shifts in Microsoft Teams</span></span>](move-staffhub-teams-to-shifts-in-teams.md)
