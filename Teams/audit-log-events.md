---
title: Rechercher des événements Microsoft Teams dans le journal d'audit
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/12/2018
ms.topic: article
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
ms.reviewer: anach
search.appverid: MET150
description: Découvrez comment récupérer les données de Microsoft teams à partir du journal d’audit.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9b1235dcd1a33800185eb005f5e309204790c5b1
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/22/2020
ms.locfileid: "43778890"
---
# <a name="search-the-audit-log-for-events-in-microsoft-teams"></a><span data-ttu-id="fc25c-103">Rechercher des événements Microsoft Teams dans le journal d'audit</span><span class="sxs-lookup"><span data-stu-id="fc25c-103">Search the audit log for events in Microsoft Teams</span></span>

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="fc25c-104">Le journal d’audit peut vous aider à vérifier des activités spécifiques dans les services Office 365.</span><span class="sxs-lookup"><span data-stu-id="fc25c-104">The audit log can help you investigate specific activities across Office 365 services.</span></span> <span data-ttu-id="fc25c-105">Pour Teams, voici certaines des activités qui sont vérifiées :</span><span class="sxs-lookup"><span data-stu-id="fc25c-105">For Teams, here are some of the activities that are audited:</span></span>

- <span data-ttu-id="fc25c-106">Création d'une équipe</span><span class="sxs-lookup"><span data-stu-id="fc25c-106">Team creation</span></span>

- <span data-ttu-id="fc25c-107">Suppression d'une équipe</span><span class="sxs-lookup"><span data-stu-id="fc25c-107">Team deletion</span></span>

- <span data-ttu-id="fc25c-108">Ajout d'un canal</span><span class="sxs-lookup"><span data-stu-id="fc25c-108">Added channel</span></span>

- <span data-ttu-id="fc25c-109">Modification d'un paramètre</span><span class="sxs-lookup"><span data-stu-id="fc25c-109">Changed setting</span></span>

> [!NOTE]
> <span data-ttu-id="fc25c-110">Les événements d’audit provenant de canaux privés sont également enregistrés tels qu’ils sont destinés aux canaux des équipes et des canaux standard.</span><span class="sxs-lookup"><span data-stu-id="fc25c-110">Audit events from private channels are also logged as they are for teams and standard channels.</span></span>

<span data-ttu-id="fc25c-111">Pour afficher la liste complète des activités auditées dans Microsoft 365, consultez la rubrique [effectuer une recherche dans le journal d’audit dans le centre de conformité microsoft 365](https://support.office.com/article/0d4d0f35-390b-4518-800e-0c7ec95e946c).</span><span class="sxs-lookup"><span data-stu-id="fc25c-111">To see the complete list of activities that are audited in Microsoft 365, read [Search the audit log in the Microsoft 365 Compliance Center](https://support.office.com/article/0d4d0f35-390b-4518-800e-0c7ec95e946c).</span></span>

## <a name="turn-on-auditing-in-teams"></a><span data-ttu-id="fc25c-112">Activer l’audit dans Teams</span><span class="sxs-lookup"><span data-stu-id="fc25c-112">Turn on auditing in Teams</span></span>

<span data-ttu-id="fc25c-113">Pour pouvoir voir les données d’audit, vous devez d’abord activer l’audit dans le [Centre de sécurité & conformité](https://protection.office.com).</span><span class="sxs-lookup"><span data-stu-id="fc25c-113">Before you can look at audit data, you have to first turn on auditing in the [Security & Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="fc25c-114">Pour obtenir de l’aide sur l’activation de l’audit, voir [activer ou désactiver la recherche dans le journal d’audit](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014).</span><span class="sxs-lookup"><span data-stu-id="fc25c-114">For help turning on auditing, read [Turn audit log search on or off](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fc25c-115">Les données d'audit sont disponibles uniquement à partir du point d'activation de la fonctionnalité d'audit.</span><span class="sxs-lookup"><span data-stu-id="fc25c-115">Audit data is only available from the point at which you turned on Auditing.</span></span>

## <a name="retrieve-teams-data-from-the-audit-log"></a><span data-ttu-id="fc25c-116">Récupérer des données Teams à partir du journal d'audit</span><span class="sxs-lookup"><span data-stu-id="fc25c-116">Retrieve Teams data from the audit log</span></span>

1. <span data-ttu-id="fc25c-117">Pour récupérer les journaux d’audit, accédez au [Centre de sécurité et de conformité](https://go.microsoft.com/fwlink/?linkid=855775).</span><span class="sxs-lookup"><span data-stu-id="fc25c-117">To retrieve audit logs, go to the [Security & Compliance Center](https://go.microsoft.com/fwlink/?linkid=855775).</span></span> <span data-ttu-id="fc25c-118">Sous **Rechercher**, sélectionnez **Rechercher dans le journal d’audit**.</span><span class="sxs-lookup"><span data-stu-id="fc25c-118">Under **Search**, select **Audit log search**.</span></span>
1. <span data-ttu-id="fc25c-119">Utilisez l’option **Rechercher** pour filtrer les données en fonction des activités, dates et utilisateurs que vous souhaitez vérifier.</span><span class="sxs-lookup"><span data-stu-id="fc25c-119">Use **Search** to filter by the activities, dates, and users you want to audit.</span></span>
1. <span data-ttu-id="fc25c-120">Pour une analyse plus approfondie, exportez les résultats dans Excel.</span><span class="sxs-lookup"><span data-stu-id="fc25c-120">Export your results to Excel for further analysis.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fc25c-121">Les données d’audit sont visibles dans le journal d’audit si la fonctionnalité d’audit est activée.</span><span class="sxs-lookup"><span data-stu-id="fc25c-121">Audit data is only visible in the Audit Log if auditing is turned on.</span></span>

## <a name="external-user-scenario"></a><span data-ttu-id="fc25c-122">Scénario d’utilisateur externe</span><span class="sxs-lookup"><span data-stu-id="fc25c-122">External user scenario</span></span>

<span data-ttu-id="fc25c-123">Dans le cas d’un scénario d’entreprise, l’ajout d’utilisateurs externes à votre environnement d’équipes peut être un scénario.</span><span class="sxs-lookup"><span data-stu-id="fc25c-123">One scenario you might want to keep an eye on, from a business perspective, is the addition of external users to your Teams environment.</span></span> <span data-ttu-id="fc25c-124">Si les utilisateurs externes sont activés, il est recommandé de surveiller leur présence.</span><span class="sxs-lookup"><span data-stu-id="fc25c-124">If external users are enabled, then monitoring their presence is a good idea.</span></span>

![Capture d’écran d’une liste d’événements déclenchés par des suppressions massiques](media/TeamsExternalUserAddPolicy.png)

<span data-ttu-id="fc25c-126">La capture d’écran de cette stratégie pour contrôler l’ajout d’utilisateurs externes vous permet d’attribuer un nom à la stratégie, de définir la gravité en fonction des besoins de votre entreprise, de la définir comme (dans ce cas) sur une activité unique, puis de définir les paramètres qui surveilleront spécifiquement l’ajout d’utilisateurs non internes et limiter cette activité à Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="fc25c-126">The screenshot of this policy to monitor external user adds allows you to name the policy, set the severity according to your business needs, set it as (in this case) a single activity, and then establish the parameters that will specifically monitor only the addition of non-internal users, and limit this activity to Microsoft Teams.</span></span>

<span data-ttu-id="fc25c-127">Les résultats de cette stratégie pourront alors être affichés dans le journal des activités :</span><span class="sxs-lookup"><span data-stu-id="fc25c-127">Then results from this policy will be able to be viewed in the activity log:</span></span>

![Capture d’écran d’une liste d’événements déclenchés par des suppressions massiques](media/TeamsExternalUserList.png)

<span data-ttu-id="fc25c-129">Dans cette section, vous pouvez passer en revue les correspondances à la stratégie que vous avez définie et procéder aux modifications nécessaires ou exporter les résultats pour les utiliser ailleurs.</span><span class="sxs-lookup"><span data-stu-id="fc25c-129">Here you can review matches to the policy you've set, and make any adjustments as needed, or export the results to use elsewhere.</span></span>

## <a name="mass-delete-scenario"></a><span data-ttu-id="fc25c-130">Scénario de suppression massive</span><span class="sxs-lookup"><span data-stu-id="fc25c-130">Mass delete scenario</span></span>

<span data-ttu-id="fc25c-131">Comme mentionné ci-dessus, vous pouvez surveiller des scénarios de suppression.</span><span class="sxs-lookup"><span data-stu-id="fc25c-131">As mentioned above, you can monitor deletion scenarios.</span></span> <span data-ttu-id="fc25c-132">Il est possible de créer une stratégie qui surveillerait la suppression massive des sites d’équipe :</span><span class="sxs-lookup"><span data-stu-id="fc25c-132">It's possible to create a policy that would monitor mass deletion of Teams sites:</span></span>

![Capture d’écran de la page de création d’une stratégie montrant la création d’une stratégie pour la détection de suppression d’équipe en masse](media/TeamsMassDeletePolicy.png)

<span data-ttu-id="fc25c-134">Comme le montre la capture d’écran, vous pouvez définir de nombreux paramètres différents pour cette stratégie afin de surveiller les suppressions d’équipe, y compris la gravité, l’action unique ou répétée, et les paramètres limitant ce paramètre à la suppression des équipes et des sites.</span><span class="sxs-lookup"><span data-stu-id="fc25c-134">As the screenshot shows, you can set many different parameters for this policy to monitor Teams deletions, including severity, single or repeated action, and parameters limiting this to Teams and site deletion.</span></span> <span data-ttu-id="fc25c-135">Cette opération peut être réalisée indépendamment d’un modèle, ou vous avez peut-être créé un modèle pour baser cette stratégie, en fonction des besoins de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="fc25c-135">This can be done independently of a template, or you may have a template created to base this policy off, depending on your organizational needs.</span></span>

<span data-ttu-id="fc25c-136">Après avoir établi une stratégie qui fonctionnera pour votre entreprise, vous pouvez passer en revue les résultats dans le journal d’activité en tant qu’événements déclenchés :</span><span class="sxs-lookup"><span data-stu-id="fc25c-136">Once you've established a policy that will work for your business, you can then review the results in the activity log as events are triggered:</span></span>

![Capture d’écran d’une liste d’événements déclenchés par des suppressions massiques](media/TeamsMassDeleteList.png)

<span data-ttu-id="fc25c-138">Vous pouvez filtrer vers le bas jusqu’à la stratégie que vous avez définie pour afficher les résultats de cette stratégie.</span><span class="sxs-lookup"><span data-stu-id="fc25c-138">You can filter down to the policy you've set to see the results of that policy.</span></span> <span data-ttu-id="fc25c-139">Si les résultats que vous obtenez dans le journal d’activité ne sont pas satisfaisants (il est possible que vous voyiez un grand nombre de résultats ou qu’il n’y en ait aucun), cela peut vous aider à peaufiner la requête afin de la rendre plus pertinente pour ce que vous en avez besoin.</span><span class="sxs-lookup"><span data-stu-id="fc25c-139">If the results you're getting in the activity log are not satisfactory (maybe you're seeing a lot of results, or nothing at all), this may help you to fine-tune the query to make it more relevant to what you need it to do.</span></span>

## <a name="video-techtip-using-audit-log-search-in-teams"></a><span data-ttu-id="fc25c-140">Vidéo : Conseil technique : utilisation de la recherche du journal d’audit dans Teams</span><span class="sxs-lookup"><span data-stu-id="fc25c-140">Video: TechTip: Using Audit Log Search in Teams</span></span>

<span data-ttu-id="fc25c-141">Rejoignez Ansuman Acharya, gestionnaire de programmes pour Teams, qui explique comment effectuer une recherche du journal d’audit pour Teams dans la Centre de sécurité et de conformité d’Office 365.</span><span class="sxs-lookup"><span data-stu-id="fc25c-141">Join Ansuman Acharya, a program manager for Teams, as he demonstrates conducting an Audit Log search for Teams in the Office 365 Security & Compliance Center.</span></span>

> [!VIDEO https://www.youtube.com/embed/UBxaRySAxyE]
