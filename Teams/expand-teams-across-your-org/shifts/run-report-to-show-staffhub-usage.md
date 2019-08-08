---
title: Exécuter un rapport pour afficher l’utilisation effective de StaffHub
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: Apprenez à exécuter un rapport pour obtenir la liste des utilisateurs de StaffHub actifs au sein de votre organisation.
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: eb337fdb79c0977f4bcacd782d6705947b5b8466
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36235385"
---
# <a name="run-a-report-to-show-active-staffhub-usage"></a><span data-ttu-id="dcb21-103">Exécuter un rapport pour afficher l’utilisation effective de StaffHub</span><span class="sxs-lookup"><span data-stu-id="dcb21-103">Run a report to show active StaffHub usage</span></span>

> [!IMPORTANT]
> <span data-ttu-id="dcb21-104">À compter du 1er octobre 2019, Microsoft StaffHub sera supprimé.</span><span class="sxs-lookup"><span data-stu-id="dcb21-104">Effective October 1, 2019, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="dcb21-105">Nous développons des fonctionnalités StaffHub dans Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="dcb21-105">We’re building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="dcb21-106">Aujourd’hui, teams inclut l’application Shifts pour la gestion des plannings et des fonctionnalités supplémentaires seront déployées dans le temps.</span><span class="sxs-lookup"><span data-stu-id="dcb21-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="dcb21-107">StaffHub ne fonctionnera pas pour tous les utilisateurs du 1er octobre 2019.</span><span class="sxs-lookup"><span data-stu-id="dcb21-107">StaffHub will stop working for all users on October 1, 2019.</span></span> <span data-ttu-id="dcb21-108">Tout utilisateur essayant d’ouvrir StaffHub verra s’afficher un message lui indiquant de télécharger Teams.</span><span class="sxs-lookup"><span data-stu-id="dcb21-108">Anyone who tries to open StaffHub will be shown a message directing them to download Teams.</span></span> <span data-ttu-id="dcb21-109">Pour en savoir plus, consultez la rubrique [Microsoft StaffHub](microsoft-staffhub-to-be-retired.md).</span><span class="sxs-lookup"><span data-stu-id="dcb21-109">To learn more, see [Microsoft StaffHub to be retired](microsoft-staffhub-to-be-retired.md).</span></span>  

<span data-ttu-id="dcb21-110">Suivez les étapes décrites dans cet article pour exécuter un rapport et obtenir la liste des utilisateurs de StaffHub actifs au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="dcb21-110">Use the steps in this article to run a report to get a list of active StaffHub users in your organization.</span></span> <span data-ttu-id="dcb21-111">Ces informations pourront vous être utiles lorsque vous préparez [le déplacement de vos équipes StaffHub vers Microsoft teams](move-staffhub-teams-to-shifts-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="dcb21-111">This information may come in handy when you prepare to [move your StaffHub teams to Microsoft Teams](move-staffhub-teams-to-shifts-in-teams.md).</span></span> <span data-ttu-id="dcb21-112">Dans le rapport, vous savez qui vous devez inclure dans vos communications lorsque vous passez de StaffHub à Teams.</span><span class="sxs-lookup"><span data-stu-id="dcb21-112">From the report, you'll know who you need to include in your communications when you make the switch from StaffHub to Teams.</span></span>

<span data-ttu-id="dcb21-113">Pour pouvoir effectuer les étapes décrites dans cet article, vous devez disposer d’Azure AD Premium.</span><span class="sxs-lookup"><span data-stu-id="dcb21-113">You need to have Azure AD Premium to perform the steps in this article.</span></span>

1. <span data-ttu-id="dcb21-114">Connectez-vous au portail Azure.</span><span class="sxs-lookup"><span data-stu-id="dcb21-114">Sign in to the Azure portal.</span></span>
2. <span data-ttu-id="dcb21-115">Dans le volet de gauche, cliquez sur la ressource **Azure Active Directory** .</span><span class="sxs-lookup"><span data-stu-id="dcb21-115">In the left pane, click the **Azure Active Directory** resource.</span></span>
3. <span data-ttu-id="dcb21-116">Sous **analyse**, cliquez sur **Sign-ins**.</span><span class="sxs-lookup"><span data-stu-id="dcb21-116">Under **Monitoring**, click **Sign-ins**.</span></span>
4. <span data-ttu-id="dcb21-117">Sous **application**, tapez **Microsoft StaffHub**.</span><span class="sxs-lookup"><span data-stu-id="dcb21-117">Under **Application**, type **Microsoft StaffHub**.</span></span>
5. <span data-ttu-id="dcb21-118">Définissez la plage de dates souhaitée pour le rapport, puis cliquez sur **appliquer**.</span><span class="sxs-lookup"><span data-stu-id="dcb21-118">Set the date range that you want for the report, and then click **Apply**.</span></span> 

    ![Capture d’écran montrant les étapes d’affichage de l’utilisation de StaffHub active](../../media/staffhub-active-usage-report.png)

## <a name="related-topics"></a><span data-ttu-id="dcb21-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="dcb21-120">Related topics</span></span>

- [<span data-ttu-id="dcb21-121">Déplacer vos équipes Microsoft StaffHub vers des équipes dans Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="dcb21-121">Move your Microsoft StaffHub teams to Shifts in Microsoft Teams</span></span>](move-staffhub-teams-to-shifts-in-teams.md)
