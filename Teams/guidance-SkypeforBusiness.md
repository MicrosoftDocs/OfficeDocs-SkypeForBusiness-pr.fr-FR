---
title: "Activer Microsoft Teams côte à côte avec Skype Entreprise"
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "Guide d’utilisation de Skype Entreprise et Microsoft Teams côte à côte"
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: 8e4c93d3b33a6b1fa5322bd8a18ff193f8eaa93a
ms.sourcegitcommit: 9756856140ea56a94e986c134c5c04e53e5c0fa6
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2017
---
<a name="enable-microsoft-teams-side-by-side-with-skype-for-business"></a><span data-ttu-id="d2d44-103">Activer Microsoft Teams côte à côte avec Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="d2d44-103">Enable Microsoft Teams side-by-side with Skype for Business</span></span> 
=============================================================

<span data-ttu-id="d2d44-104">Pour les organisations ayant déployé Skype Entreprise Online, le lancement récent de Microsoft Teams offre la possibilité d’évaluer le potentiel de Teams comme solution unique de communication et de collaboration, ainsi que les différences entre les deux solutions et comment elles peuvent coexister dans votre environnement.</span><span class="sxs-lookup"><span data-stu-id="d2d44-104">For organizations with existing deployments of Skype for Business Online, the recent introduction of Microsoft Teams presents an opportunity to evaluate the potential of Teams as a sole, communications and collaboration solution, and a challenge to tip the scale between the two solutions and how they can coexist in your environment.</span></span>

<span data-ttu-id="d2d44-105">Si Teams peut répondre à vos besoins actuellement, vous pouvez commencer à l’adopter comme solution unique de communication et de collaboration pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="d2d44-105">If Teams can meet your business requirements today, you can start adopting Teams to become your single communications and collaboration solution for your organization.</span></span>

<span data-ttu-id="d2d44-106">Teams est activée par défaut, sur tous les clients éligibles.</span><span class="sxs-lookup"><span data-stu-id="d2d44-106">Teams is enabled by default, on all eligible tenants.</span></span> <span data-ttu-id="d2d44-107">Vous devez donc décider de la manière de gérer Teams cote à côte avec Skype Entreprise et continuer à répondre aux attentes des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="d2d44-107">Therefore, you need to decide on how to manage Teams side-by-side with Skype for Business, and continue to meet user expectations.</span></span>

<span data-ttu-id="d2d44-108">De manière générale, il existe deux parcours du client côte à côte principaux.</span><span class="sxs-lookup"><span data-stu-id="d2d44-108">In general, there are two major side-by-side customer journeys.</span></span> <span data-ttu-id="d2d44-109">Ce sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="d2d44-109">They are:</span></span>

-   <span data-ttu-id="d2d44-110">**Option 1 :** parcours du client côte à côte non géré.</span><span class="sxs-lookup"><span data-stu-id="d2d44-110">**Option 1:** Unmanaged side-by-side customer journey.</span></span>

    <span data-ttu-id="d2d44-111">Le service informatique ne contrôle pas activement l’expérience côte à côte, et les utilisateurs ont la possibilité de choisir leur application favorite.</span><span class="sxs-lookup"><span data-stu-id="d2d44-111">IT does not actively control the side-by-side experience, and users are empowered to make the choice of preferred app.</span></span>

-   <span data-ttu-id="d2d44-112">**Option 2 :** parcours du client côte à côte géré.</span><span class="sxs-lookup"><span data-stu-id="d2d44-112">**Option 2:** Managed side-by-side customer journey.</span></span>

    <span data-ttu-id="d2d44-113">Le service informatique contrôle l’expérience côte à côte, et présente Teams aux utilisateurs progressivement en leur présentant d’abord un nouvel espace de travail en collaboration basé sur la conversation avec des expériences de conversation privée puis de réunion, et enfin les expériences d’appels dans Teams.</span><span class="sxs-lookup"><span data-stu-id="d2d44-113">IT controls the side-by-side experience, taking users through a journey of gradually introducing Teams to first introduce a new chat-based collaboration workspace with private chat, then meeting experiences, and finally the calling experiences in Teams.</span></span>

![Diagramme de deux parcours du client côte-à-côte : Géré et non géré.](media/guidance_SkypeforBusiness_image1.png)

<a name="side-by-side-benefits-and-considerations"></a><span data-ttu-id="d2d44-115">Avantages et inconvénients de l’expérience côte à côte</span><span class="sxs-lookup"><span data-stu-id="d2d44-115">Side-by-side benefits and considerations</span></span>
----------------------------------------

<span data-ttu-id="d2d44-116">Chaque parcours présente des avantages et des inconvénients à évaluer pour déterminer la bonne direction en fonction du profil de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="d2d44-116">Each journey has benefits and considerations to evaluate when determining the right path forward based on your organization's profile.</span></span> <span data-ttu-id="d2d44-117">Le tableau ci-dessous compare les parcours du client côte à côte géré et non géré.</span><span class="sxs-lookup"><span data-stu-id="d2d44-117">The table below provides the comparisons between managed and unmanaged side-by-side customer journeys.</span></span>


<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="d2d44-118">Chemins de migration</span><span class="sxs-lookup"><span data-stu-id="d2d44-118">Migration Paths</span></span></th>
<th align="left"><span data-ttu-id="d2d44-119">Côte à côte non géré</span><span class="sxs-lookup"><span data-stu-id="d2d44-119">Unmanaged Side-by-Side</span></span></th>
<th align="left"><span data-ttu-id="d2d44-120">Côte à côte géré</span><span class="sxs-lookup"><span data-stu-id="d2d44-120">Managed Side-by-Side</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="d2d44-121"><strong>Profil de l’organisation</strong></span><span class="sxs-lookup"><span data-stu-id="d2d44-121"><strong>Organization profile</strong></span></span></td>
<td align="left"><ul>
<li><span data-ttu-id="d2d44-122">Généralement les organisations plus petites sans ressources informatiques dédiées</span><span class="sxs-lookup"><span data-stu-id="d2d44-122">Typically, smaller organizations with no dedicated IT resources</span></span></li>
<li><span data-ttu-id="d2d44-123">Le service informatique laisse les utilisateurs sélectionner les outils appropriés pour leur travail</span><span class="sxs-lookup"><span data-stu-id="d2d44-123">IT allows user discretion in selecting right tools for their work</span></span></li>
<li><span data-ttu-id="d2d44-124">Skype Entreprise utilisé principalement pour la messagerie instantanée et les réunions</span><span class="sxs-lookup"><span data-stu-id="d2d44-124">Primary Skype for Business usage is IM/P and meetings</span></span></li>
</ul></td>
<td align="left"><ul><li><span data-ttu-id="d2d44-125">Généralement, les moyennes et grandes organisations</span><span class="sxs-lookup"><span data-stu-id="d2d44-125">Typically, mid-size to larger organizations</span></span></li>
<li><span data-ttu-id="d2d44-126">Le service informatique souhaite contrôler le lancement des nouveaux outils plus rigoureusement</span><span class="sxs-lookup"><span data-stu-id="d2d44-126">IT wants to control roll out of new tools more rigorously</span></span></li>
<li><span data-ttu-id="d2d44-127">Adoption plus grande de Skype Entreprise actuellement</span><span class="sxs-lookup"><span data-stu-id="d2d44-127">Deeper adoption of Skype for Business today</span></span></li>
<li><span data-ttu-id="d2d44-128">Complexité accrue au niveau du réseau et de l'infrastructure</span><span class="sxs-lookup"><span data-stu-id="d2d44-128">Increased complexity in network and infrastructure</span></span></li>
<li><span data-ttu-id="d2d44-129">Plusieurs emplacements</span><span class="sxs-lookup"><span data-stu-id="d2d44-129">Multiple locations</span></span></p>
<li><span data-ttu-id="d2d44-130">Préférence pour une application unique avec des fonctionnalités de communications unifiées uniques</span><span class="sxs-lookup"><span data-stu-id="d2d44-130">Preference for single app with unique UC capabilities</span></span></li></ul></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="d2d44-131"><strong>Avantages</strong></span><span class="sxs-lookup"><span data-stu-id="d2d44-131"><strong>Benefits</strong></span></span></td>
<td align="left"><ul>
<li><span data-ttu-id="d2d44-132">Permet d’utiliser des fonctionnalités dans Teams qui ne sont pas disponibles dans Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="d2d44-132">Leverage capabilities in Teams that are not available in Skype for Business</span></span></li>
<li><span data-ttu-id="d2d44-133">Espace de travail plus moderne dans Office 365</span><span class="sxs-lookup"><span data-stu-id="d2d44-133">Enhanced modern workplace within Office 365</span></span></li>
<li><span data-ttu-id="d2d44-134">Plus de flexibilité pour les utilisateurs</span><span class="sxs-lookup"><span data-stu-id="d2d44-134">Increased user flexibility</span></span></li>
<li><span data-ttu-id="d2d44-135">Permet d’utiliser toutes les fonctionnalités simultanément</span><span class="sxs-lookup"><span data-stu-id="d2d44-135">Enable all capabilities at once</span></span></li>
</ul></td>
<td align="left"><ul><li><span data-ttu-id="d2d44-136">Permet d’utiliser des fonctionnalités dans Teams qui ne sont pas disponibles dans Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="d2d44-136">Leverage capabilities in Teams that are not available in Skype for Business</span></span></li>
<li><span data-ttu-id="d2d44-137">Espace de travail plus moderne dans Office 365</span><span class="sxs-lookup"><span data-stu-id="d2d44-137">Enhanced modern workplace within Office 365</span></span></li>
<li><span data-ttu-id="d2d44-138">Réduit l’impact sur la productivité des utilisateurs</span><span class="sxs-lookup"><span data-stu-id="d2d44-138">Minimize user productivity impact</span></span></li>
<li><span data-ttu-id="d2d44-139">Réduit la superposition des fonctionnalités</span><span class="sxs-lookup"><span data-stu-id="d2d44-139">Reduce capability overlap</span></span></li>
<li><span data-ttu-id="d2d44-140">Rationalise le choix des outils pour les scénarios de communications unifiées</span><span class="sxs-lookup"><span data-stu-id="d2d44-140">Streamline tool choice for UC scenarios</span></span></li>
<li><span data-ttu-id="d2d44-141">Permet au service informatique et à l’entreprise d’activer les fonctionnalités en fonction des besoins de l’organisation</span><span class="sxs-lookup"><span data-stu-id="d2d44-141">Empower IT and business to enable capabilities as appropriate in organization</span></span></li>
<li><span data-ttu-id="d2d44-142">Contrôle le rythme des changements pour les utilisateurs</span><span class="sxs-lookup"><span data-stu-id="d2d44-142">Control the pace of change for users</span></span></li></ul></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="d2d44-143"><strong>Inconvénients</strong></span><span class="sxs-lookup"><span data-stu-id="d2d44-143"><strong>Considerations</strong></span></span></td>
<td align="left"><ul>
<li><span data-ttu-id="d2d44-144">Plusieurs applications avec des fonctionnalités similaires qui se superposent</span><span class="sxs-lookup"><span data-stu-id="d2d44-144">Multiple apps with similar, overlapping capabilities</span></span></li>
<li><span data-ttu-id="d2d44-145">Plus de possibilités de confusion de la part des utilisateurs, ce qui peut entraîner plus d’appels de l’assistance, de l'informatique fantôme et avoir un impact sur la productivité</span><span class="sxs-lookup"><span data-stu-id="d2d44-145">Increased potential for user confusion which can lead to increased support calls, shadow IT, impacted productivity</span></span></li>
<li><span data-ttu-id="d2d44-146">La planification et la supervision du réseau doivent prendre en compte deux services</span><span class="sxs-lookup"><span data-stu-id="d2d44-146">Network planning and monitoring must take usage of two services into consideration</span></span></li>
<li><span data-ttu-id="d2d44-147">Travail de gestion des changements accru et immédiat : sensibilisation, formation et support</span><span class="sxs-lookup"><span data-stu-id="d2d44-147">Increased and immediate change management efforts required: awareness, training, and support</span></span></li>
<li><span data-ttu-id="d2d44-148">Les utilisateurs peuvent rencontrer des limitations de l'interopérabilité entre les applications</span><span class="sxs-lookup"><span data-stu-id="d2d44-148">Users may experience interoperability limitations between apps</span></span></li>
</ul></td>
<td align="left"><ul><li><span data-ttu-id="d2d44-149">Le service a un contrôle précis, des licences aux expériences des utilisateurs, ce qui nécessite des cycles de planification et d’implémentation supplémentaires</span><span class="sxs-lookup"><span data-stu-id="d2d44-149">IT has granular control, from licensing to user experiences, requiring additional cycles of planning and implementation</span></span></li>
<li><span data-ttu-id="d2d44-150">Formation des utilisateurs et action requises pour désactiver les fonctionnalités sélectionnées dans Teams</span><span class="sxs-lookup"><span data-stu-id="d2d44-150">User education and action required to disable select capabilities in Teams</span></span></li>
<li><span data-ttu-id="d2d44-151">Travail de gestion des changements requis pour désactiver les fonctionnalités sélectionnées dans Teams</span><span class="sxs-lookup"><span data-stu-id="d2d44-151">Change management efforts required to disable select capabilities in Teams</span></span></li>
<li><span data-ttu-id="d2d44-152">La planification et la supervision du réseau doivent prendre en compte deux services</span><span class="sxs-lookup"><span data-stu-id="d2d44-152">Network planning and monitoring must take usage of two services into consideration</span></span></li>
<li><span data-ttu-id="d2d44-153">Les utilisateurs peuvent rencontrer des limitations de l'interopérabilité entre les applications</span><span class="sxs-lookup"><span data-stu-id="d2d44-153">Users may experience interoperability limitations between apps</span></span></li></ul></td>
</tr>
</tbody>
</table>


<a name="unmanaged-side-by-side-customer-journey"></a><span data-ttu-id="d2d44-154">Parcours du client côte à côte non géré</span><span class="sxs-lookup"><span data-stu-id="d2d44-154">Unmanaged side-by-side customer journey</span></span>
---------------------------------------


![Diagramme de parcours du client côte à côte non géré.](media/guidance_SkypeforBusiness_image4.png)

<span data-ttu-id="d2d44-156">Dans un parcours du client côte à côte non géré, Teams est présenté comme solution de collaboration (espace de travail basé sur les conversations, canaux, applications, intégration avec les autres charges de travail Office 365, etc.) qui implique un logiciel client et un client Web sur les ordinateurs de bureau (PC ou Mac) et les appareils mobiles.</span><span class="sxs-lookup"><span data-stu-id="d2d44-156">In an unmanaged side-by-side customer journey, Teams is introduced as a collaboration solution (chat-based workspace, channels, apps, integration with other Office 365 workloads, etc.) that involves client software and web client on desktop computers (PC or Mac) and mobile devices.</span></span>


<span data-ttu-id="d2d44-157">Par défaut, Teams présente également des fonctionnalités qui se superposent avec Skype Entreprise, incluant la conversation et les appels privés, ainsi que les réunions planifiées.</span><span class="sxs-lookup"><span data-stu-id="d2d44-157">By default, Teams also presents overlapping capabilities with Skype for Business, these include private chat and calling, and scheduled meetings.</span></span> <span data-ttu-id="d2d44-158">Cela signifie que Teams fournit des fonctions de communication et de collaboration complètes à l’organisation, tandis que Skype Entreprise fournit en même temps des fonctionnalités similaires.</span><span class="sxs-lookup"><span data-stu-id="d2d44-158">This means Teams ends up providing complete communications and collaboration for the organization, while at the same time Skype for Business provides similar capabilities.</span></span>

<span data-ttu-id="d2d44-159">Teams prend en charge l’interopérabilité avec les utilisateurs de Skype Entreprise Online, et les utilisateurs ont la possibilité de choisir leur application de conversation et d’appels favorite lorsqu'ils lancent Teams.</span><span class="sxs-lookup"><span data-stu-id="d2d44-159">Teams supports interoperability with Skype for Business Online users, and users will be given an opportunity to choose their preferred chat and calling app when they launch Teams.</span></span> <span data-ttu-id="d2d44-160">Si un utilisateur choisit Teams comme application favorite, et qu'un autre utilisateur n’a pas installé Teams ou a choisi Skype Entreprise comme application de conversation et d’appels favorite, ils peuvent continuer à discuter et s’appeler par le biais des fonctionnalités d’interopérabilité intégrées dans Teams.</span><span class="sxs-lookup"><span data-stu-id="d2d44-160">If one user picks Teams as the preferred app, and another user hasn’t installed Teams or picked Skype for Business as the preferred chat and calling app, they can continue to chat and call each other through the interop capabilities that are part of Teams.</span></span>

<span data-ttu-id="d2d44-161">Microsoft améliore en permanence les expériences d’interopérabilité.</span><span class="sxs-lookup"><span data-stu-id="d2d44-161">Microsoft is continuously improving the interop experiences.</span></span> <span data-ttu-id="d2d44-162">Au début, il a pu arriver que les expériences d'interopérabilité ne répondent pas aux attentes des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="d2d44-162">In the beginning, there may be some cases whereby the interop experiences are not meeting user expectations.</span></span> <span data-ttu-id="d2d44-163">Skype Entreprise restant disponible pour les utilisateurs, ils peuvent basculer sur Skype Entreprise pour les fonctionnalités qui ne peuvent pas être fournies actuellement par Teams.</span><span class="sxs-lookup"><span data-stu-id="d2d44-163">Since Skype for Business is still available to users, they can switch to Skype for Business for the capabilities that currently cannot be served by Teams.</span></span>

<span data-ttu-id="d2d44-164">Les réunions planifiées dans Teams sont une autre fonctionnalité qui se superpose permettant aux utilisateurs de planifier des réunions Teams ou Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="d2d44-164">Scheduled meetings in Teams is another overlapping capability that lets users schedule Teams meetings, or Skype for Business meetings.</span></span> <span data-ttu-id="d2d44-165">Chaque application a ses propres avantages et au fil du temps, lorsque l’expérience de réunion répondra aux besoins de l’entreprise ou dépassera les fonctionnalités de Skype Entreprise pour les réunions, les utilisateurs devraient basculer naturellement sur les réunions Teams.</span><span class="sxs-lookup"><span data-stu-id="d2d44-165">Each has its own advantages, and over time, when Teams meeting experience meets business requirements or surpasses the functionalities of Skype for Business meetings, we expect users to naturally switch to Teams meetings.</span></span>

<span data-ttu-id="d2d44-166">Dans ce parcours du client côte à côte non géré, préparez votre équipe de support technique à gérer les appels de support des utilisateurs lorsqu'ils rencontrent des problèmes avec les fonctionnalités d’interopérabilité.</span><span class="sxs-lookup"><span data-stu-id="d2d44-166">In this unmanaged side-by-side customer journey, prepare your helpdesk team to handle support calls from users when facing issues with interop capabilities.</span></span> <span data-ttu-id="d2d44-167">Ou bien, conseillez aux utilisateurs de choisir les réunions Teams au lieu des réunions Skype Entreprise, et vice-versa.</span><span class="sxs-lookup"><span data-stu-id="d2d44-167">Or advise users when to choose Teams meetings over Skype for Business meetings, and vice versa.</span></span>

<span data-ttu-id="d2d44-168">Ce parcours du client côte à côte peut s’appliquer à votre organisation, les utilisateurs étant plus réceptifs à la nature de l’expérience côte à côte non gérée, et l’organisation permettant ouvertement aux utilisateurs de choisir les outils de communication et de collaboration qui répondent le mieux à leurs besoins.</span><span class="sxs-lookup"><span data-stu-id="d2d44-168">This side-by-side customer journey may be applicable to your organization, whereby the users are more receptive to the nature of the unmanaged side-by-side experience, and the organization openly allows the users to pick the best communications and collaboration tools that suit their requirements.</span></span>

<a name="managed-side-by-side-customer-journey"></a><span data-ttu-id="d2d44-169">Parcours du client côte à côte géré</span><span class="sxs-lookup"><span data-stu-id="d2d44-169">Managed side-by-side customer journey</span></span>
-------------------------------------

![Diagramme de parcours du client côte à côte géré.](media/guidance_SkypeforBusiness_image2.png)

<span data-ttu-id="d2d44-171">Un parcours du client côte à côte géré est la solution si l’organisation souhaite avoir plus de contrôle sur la manière dont Teams est introduit.</span><span class="sxs-lookup"><span data-stu-id="d2d44-171">A managed side-by-side customer journey starts with organization wanting more control over how Teams is introduced.</span></span>

-   <span data-ttu-id="d2d44-172">La **première étape** de ce parcours est une phase pilote limitée de Teams axée sur les besoins de collaboration modernes (espace de travail basé sur les conversations, canaux, applications, intégration avec les autres charges de travail Office 365, etc.).</span><span class="sxs-lookup"><span data-stu-id="d2d44-172">The **first step** of this journey is a limited pilot of Teams scoped to modern collaboration requirements (chat-based workspace, channels, apps, integration with other Office 365 workloads, etc.).</span></span> <span data-ttu-id="d2d44-173">Les réunions de canal et les conversations privées ponctuelles dans Teams sont également activées pour permettre aux utilisateurs pilotes d’évaluer l’expérience de réunions et les expériences de conversation privée de Teams.</span><span class="sxs-lookup"><span data-stu-id="d2d44-173">Ad-hoc channel meetings and private chat in Teams is also enabled to provide a chance for pilot users to evaluate the Teams meetings experience and private chat experiences.</span></span> <span data-ttu-id="d2d44-174">À ce stade, les fonctionnalités de réunions planifiées et d’appels privés sont désactivées.</span><span class="sxs-lookup"><span data-stu-id="d2d44-174">Scheduled meetings and private calling capabilities in Teams are disabled at this stage.</span></span> <span data-ttu-id="d2d44-175">Pour démarrer une phase pilote, accédez à la rubrique [Équipes pilotes avec Skype Entreprise](pilot-essentials.md).</span><span class="sxs-lookup"><span data-stu-id="d2d44-175">To get started with a pilot, go to [Pilot Teams with Skype for Business](pilot-essentials.md).</span></span>
    
-   <span data-ttu-id="d2d44-176">La **seconde étape** de ce parcours consiste à étendre le lancement de Teams pour la collaboration moderne avec la conversation privée dans toute l’organisation.</span><span class="sxs-lookup"><span data-stu-id="d2d44-176">The **second step** of this journey is extending the rollout of Teams for modern collaboration with private chat throughout the organization.</span></span> <span data-ttu-id="d2d44-177">Les réunions planifiées et les appels privés restent désactivés dans Teams pour limiter la superposition avec les fonctionnalités de Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="d2d44-177">Scheduled meetings, and private calling continue to be disabled in Teams to reduce the overlap  with with Skype for Business capabilities.</span></span>

    <span data-ttu-id="d2d44-178">À ce stade, vous pouvez déterminer si l’application de conversation favorite doit être définie sur Teams ou Skype Entreprise pour l’ensemble de l’organisation.</span><span class="sxs-lookup"><span data-stu-id="d2d44-178">At this stage, you may need to consider whether preferred chat application should be set to Teams or Skype for Business for the entire organization.</span></span>

    - <span data-ttu-id="d2d44-179">Si vous définissez Teams, préparez vos utilisateurs à gérer les problèmes d’interopérabilité initiaux lorsqu’ils communiquent avec les autres parties au sein et au-delà de l’organisation.</span><span class="sxs-lookup"><span data-stu-id="d2d44-179">If set to Teams, prepare your users to handle early interoperability challenges when communicating with other parties within and across the organization.</span></span>
    
    - <span data-ttu-id="d2d44-180">Si vous définissez Skype Entreprise, les conversations privées au sein de Teams restent dans Teams, et les utilisateurs finaux peuvent bénéficier immédiatement de la nature permanente multiplateforme des fonctionnalités de conversation au sein de Teams, et continueront à utiliser Skype Entreprise pour les conversations privées avec les utilisateurs de Skype Entreprise, au sein et au-delà de l’organisation.</span><span class="sxs-lookup"><span data-stu-id="d2d44-180">If set to Skype for Business, private chats within Teams will remain in Teams, and end users can immediately take advantage of the cross-platform persistent nature of chat capabilities within Teams, and they will continue to use Skype for Business for private chats among Skype for Business users, within the organization and across the organization.</span></span>


<table>
<thead>
<tr class="header">
<td align="center"><p><img src="media/guidance_SkypeforBusiness_image3.png" /></p>
<p><span data-ttu-id="d2d44-181">Remarque</span><span class="sxs-lookup"><span data-stu-id="d2d44-181">Note</span></span></p></td>
<td align="left"><br><br><span data-ttu-id="d2d44-182">Le paramètre d’application de conversation favorite n’est disponible actuellement qu’au niveau du client.</span><span class="sxs-lookup"><span data-stu-id="d2d44-182">Currently the preferred chat application setting is available only at the client level.</span></span> <span data-ttu-id="d2d44-183">Une formation des utilisateurs et une campagne d’adoption seront nécessaires pour effectuer la configuration à l’échelle de l’organisation prévue.</span><span class="sxs-lookup"><span data-stu-id="d2d44-183">User training and adoption campaign will be required to drive the intended organization-wide configuration.</span></span></td>
</tr>
</thead>
<tbody>
</tbody>
</table>

<span data-ttu-id="d2d44-184">La **troisième étape** du parcours du client côte à côte géré commence lorsque l’organisation décide que l’expérience de réunion et les fonctionnalités de Teams répondent à ses besoins.</span><span class="sxs-lookup"><span data-stu-id="d2d44-184">The **third step** of the managed side-by-side customer journey starts when the organization decides that Teams meeting experience and capabilities meet their business requirements.</span></span> <span data-ttu-id="d2d44-185">En activant les réunions privées et de canal dans Teams, des options permettant de planifier des réunions Teams et des réunions Skype Entreprise sont présentées aux utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="d2d44-185">By enabling private and channel meetings in Teams, users are presented with options to schedule both Teams meetings and Skype for Business meetings.</span></span> <span data-ttu-id="d2d44-186">Les utilisateurs devraient donc basculer naturellement sur les réunions Teams étant donné les innovations permanentes introduites dans Teams.</span><span class="sxs-lookup"><span data-stu-id="d2d44-186">Therefore, it is expected that over time users will naturally switch to Teams meetings given the continued innovations in Teams.</span></span> <span data-ttu-id="d2d44-187">Pour amener les utilisateurs à passer de l’utilisation de Skype Entreprise à celle de Teams, implémentez un programme de gestion des changements solide incluant une formation, un support et des communications expliquant la valeur ajoutée de Teams, avec des orientations claires sur la prise en main de Teams.</span><span class="sxs-lookup"><span data-stu-id="d2d44-187">To be successful in steering usage from Skype for Business to Teams, implement a robust change management program inclusive of training, support and communications that explains the value-add that Teams offers to the user, with clear guidance on how to get started with Teams.</span></span> <span data-ttu-id="d2d44-188">Utilisez nos ressources de [Préparation des utilisateurs](http://aka.ms/UserReadiness) pour vous aider à concevoir une campagne de sensibilisation.</span><span class="sxs-lookup"><span data-stu-id="d2d44-188">Leverage our [User Readiness](http://aka.ms/UserReadiness) resources to help design your awareness campaign.</span></span>


<span data-ttu-id="d2d44-189">La **quatrième étape** du parcours du client côte à côte géré commence par l’activation des appels dans Teams.</span><span class="sxs-lookup"><span data-stu-id="d2d44-189">The **fourth step** of the managed side-by-side customer journey begins with enabling calling in Teams.</span></span> <span data-ttu-id="d2d44-190">Les fonctionnalités d'interopérabilité de Teams seront privilégiées dans cette étape pour assurer une expérience côte à côte transparente.</span><span class="sxs-lookup"><span data-stu-id="d2d44-190">Teams interoperability capabilities will feature heavily in this step to ensure a seamless side-by-side experience.</span></span> <span data-ttu-id="d2d44-191">Dans l’idéal, pour imposer l’utilisation de Teams pour les appels privés, Teams est défini comme application d’appels par défaut.</span><span class="sxs-lookup"><span data-stu-id="d2d44-191">Ideally, to enforce the use of Teams for private calling, Teams is set as the default calling app.</span></span> 

<span data-ttu-id="d2d44-192">Au fil du temps, l’ensemble de l’organisation peut théoriquement s’appuyer uniquement sur Teams pour répondre aux besoins de communication et de collaboration et passer à la **cinquième étape**.</span><span class="sxs-lookup"><span data-stu-id="d2d44-192">Over time, potentially the whole organization can rely solely on Teams to meet communications and collaboration requirements and take the **fifth step**.</span></span> <span data-ttu-id="d2d44-193">Pour savoir quand de nouvelles fonctionnalités seront disponibles dans Teams, reportez-vous à la [Feuille de route Office 365](http://aka.ms/TeamsRoadmap).</span><span class="sxs-lookup"><span data-stu-id="d2d44-193">To see when new features are coming in Teams, see the [Office 365 Roadmap](http://aka.ms/TeamsRoadmap).</span></span> 

<a name="managing-side-by-side-experience"></a><span data-ttu-id="d2d44-194">Gestion de l’expérience côte à côte</span><span class="sxs-lookup"><span data-stu-id="d2d44-194">Managing side-by-side experience</span></span>
--------------------------------

<span data-ttu-id="d2d44-195">Par défaut, pour les organisations disposant d’abonnements Office 365 éligibles, Microsoft Teams est activée.</span><span class="sxs-lookup"><span data-stu-id="d2d44-195">By default, for organizations with eligible Office 365 subscriptions, Microsoft Teams is enabled.</span></span> <span data-ttu-id="d2d44-196">Si votre organisation répond aux critères pour le parcours du client côte à côte non géré, nous vous recommandons vivement de conserver ce paramètre tel quel pour favoriser l’adoption systématique de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d2d44-196">If your organization fits the profile for unmanaged side-by-side customer journey, we highly recommend you keep it as-is to foster organic adoption of Microsoft Teams.</span></span>

<span data-ttu-id="d2d44-197">Teams est accessible par le biais de clients de bureau avec un navigateur Web moderne ne nécessitant pas de droits d’administrateur informatique (pour l'installation, s’applique uniquement aux PC actuellement) et de clients mobiles.</span><span class="sxs-lookup"><span data-stu-id="d2d44-197">Teams is accessible via modern Web browser desktop clients which require no IT administrative privilege (for installation, currently applicable to PC only) and mobile clients.</span></span>

<span data-ttu-id="d2d44-198">Toutes les fonctionnalités dans Teams, de la conversation privée aux appels, aux réunions ponctuelles et planifiées et aux applications sont activées par défaut, ce qui permet aux utilisateurs d’expérimenter et d’utiliser les fonctionnalités qui répondent à leurs besoins.</span><span class="sxs-lookup"><span data-stu-id="d2d44-198">All capabilities in Teams, from private chat and calling, ad-hoc and scheduled meetings, and apps are enabled by default, allowing users to experiment and use the capabilities that suit their needs.</span></span> <span data-ttu-id="d2d44-199">Une expérience de première utilisation dans Teams guide les utilisateurs dans le choix de leur application de conversation et d’appels favorite (Microsoft Teams ou Skype Entreprise).</span><span class="sxs-lookup"><span data-stu-id="d2d44-199">A first-run experience in Teams guides users to pick their preferred chat and calling application (Microsoft Teams or Skype for Business).</span></span>

<span data-ttu-id="d2d44-200">Si votre organisation requiert une version plus contrôlée des nouveaux outils comme Teams, les options suivantes peuvent être envisagées pour votre parcours du client côte à côte géré :</span><span class="sxs-lookup"><span data-stu-id="d2d44-200">Should your organization require a more controlled release of new tools such as Teams, the following options can be considered for your managed side-by-side customer journey, they are:</span></span>

-   <span data-ttu-id="d2d44-201">Phase pilote et lancement de Teams pour la collaboration.</span><span class="sxs-lookup"><span data-stu-id="d2d44-201">Pilot and rollout of Teams for collaboration.</span></span> <span data-ttu-id="d2d44-202">Consultez la rubrique [Équipes pilotes avec Skype Entreprise](pilot-essentials.md).</span><span class="sxs-lookup"><span data-stu-id="d2d44-202">See [Pilot Teams with Skype for Business](pilot-essentials.md).</span></span>

-   <span data-ttu-id="d2d44-203">Lancement de Teams pour les réunions</span><span class="sxs-lookup"><span data-stu-id="d2d44-203">Rollout of Teams for meetings</span></span>

-   <span data-ttu-id="d2d44-204">Lancement de Teams pour les appels</span><span class="sxs-lookup"><span data-stu-id="d2d44-204">Rollout of Teams for calling</span></span>

### <a name="teams-pilot-and-rollout-for-collaboration"></a><span data-ttu-id="d2d44-205">Phase pilote et lancement de Teams pour la collaboration</span><span class="sxs-lookup"><span data-stu-id="d2d44-205">Teams pilot and rollout for collaboration</span></span>

<span data-ttu-id="d2d44-206">Microsoft Teams a été conçu essentiellement autour de la conversation permanente et l’intégration avec Office 365 en améliorant les groupes Office 365.</span><span class="sxs-lookup"><span data-stu-id="d2d44-206">At its core, Microsoft Teams was built around persistent chat and integration with Office 365 by enhancing Office 365 Groups.</span></span>

<span data-ttu-id="d2d44-207">Étant donné que, par défaut, Teams est activé pour les utilisateurs dans votre organisation disposant d'une licence d’abonnement à Office 365 éligible, la version pilote de Teams impliquera de désactiver la licence Teams de tous les utilisateurs qui ne font pas partie du groupe pilote.</span><span class="sxs-lookup"><span data-stu-id="d2d44-207">Since by default users in your organization with an eligible Office 365 subscription license are enabled for Teams, a limited Teams pilot will involve disabling the Teams license for all users who are outside of the pilot group.</span></span>

<span data-ttu-id="d2d44-208">Pour orienter la solution de collaboration et de conversation privée sur la version de Teams, et pour réduire la confusion des utilisateurs due aux fonctionnalités qui se superposent avec Skype Entreprise, vous pouvez modifier les paramètres suivants au niveau du client Office 365.</span><span class="sxs-lookup"><span data-stu-id="d2d44-208">To focus the Teams release as a collaboration and private chat solution, and to reduce user confusion due to overlapping capabilities with Skype for Business, you can change the following settings at the Office 365 tenant level.</span></span> <span data-ttu-id="d2d44-209">Pour modifier ces paramètres Office 365, consultez la rubrique [Configurer Microsoft Teams dans votre organisation Office 365](Office-365-set-up.md).</span><span class="sxs-lookup"><span data-stu-id="d2d44-209">To change these Office 365 settings, see [Set up Microsoft Teams in your Office 365 organization](Office-365-set-up.md).</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="d2d44-210">Section</span><span class="sxs-lookup"><span data-stu-id="d2d44-210">Section</span></span></th>
<th align="left"><span data-ttu-id="d2d44-211">Paramètre</span><span class="sxs-lookup"><span data-stu-id="d2d44-211">Setting</span></span></th>
<th align="left"><span data-ttu-id="d2d44-212">Description</span><span class="sxs-lookup"><span data-stu-id="d2d44-212">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><strong><br><span data-ttu-id="d2d44-213">Appels et réunions</strong></span><span class="sxs-lookup"><span data-stu-id="d2d44-213">Calls and meetings</strong></span></span></td>
<td align="left"><p><span data-ttu-id="d2d44-214">Autoriser la planification de réunions privées : <strong>désactivé</strong></span><span class="sxs-lookup"><span data-stu-id="d2d44-214">Allow scheduling for private meetings: <strong>Off</strong></span></span></p><p><span data-ttu-id="d2d44-215">Autoriser la planification de réunions de canal : <strong>désactivé</strong></span><span class="sxs-lookup"><span data-stu-id="d2d44-215">Allow scheduling for channel meetings: <strong>Off</strong></span></span></p><p><span data-ttu-id="d2d44-216">Autoriser les appels privés : <strong>désactivé</strong></span><span class="sxs-lookup"><span data-stu-id="d2d44-216">Allow private calling: <strong>Off</strong></span></span></p></td>
<td align="left"><p><span data-ttu-id="d2d44-217">Désactiver ce paramètre empêche les utilisateurs de planifier des réunions privées</span><span class="sxs-lookup"><span data-stu-id="d2d44-217">Disabling this setting prevents users from scheduling private meetings</span></span></p><p><span data-ttu-id="d2d44-218">Désactiver ce paramètre empêche les utilisateurs de planifier des réunions de canal</span><span class="sxs-lookup"><span data-stu-id="d2d44-218">Disabling this setting prevents users from scheduling channel meetings</span></span></p><p><span data-ttu-id="d2d44-219">Désactiver ce paramètre empêche les utilisateurs de passer des appels privés (audio et vidéo)</span><span class="sxs-lookup"><span data-stu-id="d2d44-219">Disabling this setting prevents users from making private calls (audio and video)</span></span></p></td>
</tr>
</tbody>
</table>


<table>
<thead>
<tr class="header">
<td align="center"><p><img src="media/guidance_SkypeforBusiness_image3.png" /></p>
<p><span data-ttu-id="d2d44-220">Remarque</span><span class="sxs-lookup"><span data-stu-id="d2d44-220">Note</span></span></p></td>
<td align="left"><br><br><span data-ttu-id="d2d44-221">Vous devez désactiver les appels privés pour les utilisateurs professionnels et de l’entreprise, et les utilisateurs invités (si l’accès invité s’applique à votre organisation).</span><span class="sxs-lookup"><span data-stu-id="d2d44-221">You must disable Private Calling to both Business and Enterprise users, and Guest users (if Guest Access is applicable to your organization).</span></span></td>
</tr>
</thead>
<tbody>
</tbody>
</table>



<span data-ttu-id="d2d44-222">Avec cette configuration, la manière dont les réunions fonctionnent dans Teams peut être présentée aux utilisateurs en préconisant l’utilisation de la réunion ponctuelle, qui permet d’utiliser les fonctions audio, vidéo et le partage d’écran dans le cadre de l’expérience de collaboration moderne.</span><span class="sxs-lookup"><span data-stu-id="d2d44-222">With this configuration, users can be introduced to how meetings work in Teams by advocating the use of ad-hoc channel meetup, enabling the use of voice, video, and screen sharing as part of the modern collaboration experience.</span></span> <span data-ttu-id="d2d44-223">Les utilisateurs finaux peuvent également bénéficier des fonctionnalités de conversation privée permanente et multiplateforme.</span><span class="sxs-lookup"><span data-stu-id="d2d44-223">End users can also benefit from Teams persistent, cross-platform, private chat capabilities.</span></span>

<span data-ttu-id="d2d44-224">Une phase pilote réussie de Teams pour la collaboration et la conversation privée peut être suivie d'un lancement dans l’ensemble de l’organisation en activant la licence Teams pour tous les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="d2d44-224">A successful Teams pilot for collaboration and private chat can be followed up with broad rollout throughout the organization by enabling Teams license for all users.</span></span>

<table>
<thead>
<tr class="header">
<td align="center"><p><img src="media/guidance_SkypeforBusiness_image3.png" /></p>
<p><span data-ttu-id="d2d44-225">Remarque</span><span class="sxs-lookup"><span data-stu-id="d2d44-225">Note</span></span></p></td>
<td align="left"><span data-ttu-id="d2d44-226">Pendant la phase pilote, et pendant la phase deux lorsque la conversation privée est activée, un utilisateur de Teams qui discute avec un utilisateur de Skype Entreprise ne pourra pas effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="d2d44-226">During the pilot, and in phase two when private chat is enabled, a Teams user chatting with a Skype for Business user will not be able to do the following:</span></span><br><span data-ttu-id="d2d44-227">
- Lancer un appel vidéo à partir d'une session de conversation</span><span class="sxs-lookup"><span data-stu-id="d2d44-227">
- Start video call from a chat session</span></span><br><span data-ttu-id="d2d44-228">
- Transférer des fichiers</span><span class="sxs-lookup"><span data-stu-id="d2d44-228">
- Transfers files</span></span> <br><span data-ttu-id="d2d44-229">
- Lancer un appel de groupe à partir de la session de conversation</span><span class="sxs-lookup"><span data-stu-id="d2d44-229">
- Initiate a multiparty call from the chat session</span></span><br><span data-ttu-id="d2d44-230">
- Les utilisateurs ne pourront pas démarrer une session de partage de bureau</span><span class="sxs-lookup"><span data-stu-id="d2d44-230">
- Users will not be able to start a desktop sharing session</span></span><br>

</td>
</tr>
</thead>
<tbody>
</tbody>
</table>


### <a name="rollout-of-teams-for-meetings"></a><span data-ttu-id="d2d44-231">Lancement de Teams pour les réunions</span><span class="sxs-lookup"><span data-stu-id="d2d44-231">Rollout of Teams for meetings</span></span>

<span data-ttu-id="d2d44-232">Lorsque les utilisateurs sont habitués à collaborer en utilisant Microsoft Teams, les réunions planifiées peuvent être envisagées comme prochaine fonctionnalité à activer dans l’organisation.</span><span class="sxs-lookup"><span data-stu-id="d2d44-232">As users are getting accustomed to collaborating using Microsoft Teams, scheduled meetings can be considered as the next capability to enable in the organization.</span></span>

<table>
<thead>
<tr class="header">
<td align="center"><p><img src="media/guidance_SkypeforBusiness_image3.png" /></p>
<p><span data-ttu-id="d2d44-233">Remarque</span><span class="sxs-lookup"><span data-stu-id="d2d44-233">Note</span></span></p></td>
<td align="left"><br><br><span data-ttu-id="d2d44-234">Les personnes qui organisent des réunions planifiées doivent leurs boîtes aux lettres dans Exchange Online mutualisées (ou vNext Exchange Online dédié).</span><span class="sxs-lookup"><span data-stu-id="d2d44-234">The organizers of scheduled meetings must have their mailboxes in Exchange Online multi-tenant (or Exchange Online Dedicated vNext).</span></span></td>
</tr>
</thead>
<tbody>
</tbody>
</table>

<span data-ttu-id="d2d44-235">Les paramètres suivants peuvent être configurés au niveau du client pour activer les réunions planifiées dans Teams, et les paramètres s’appliquent uniquement aux utilisateurs professionnels et de l’entreprise uniquement.</span><span class="sxs-lookup"><span data-stu-id="d2d44-235">The following settings can be configured at the tenant level to enable scheduled meetings in Teams, and the settings are applicable to Business and Enterprise users only.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="d2d44-236">Section</span><span class="sxs-lookup"><span data-stu-id="d2d44-236">Section</span></span></th>
<th align="left"><span data-ttu-id="d2d44-237">Paramètre</span><span class="sxs-lookup"><span data-stu-id="d2d44-237">Setting</span></span></th>
<th align="left"><span data-ttu-id="d2d44-238">Description</span><span class="sxs-lookup"><span data-stu-id="d2d44-238">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><strong><br><span data-ttu-id="d2d44-239">Appels et réunions</strong></span><span class="sxs-lookup"><span data-stu-id="d2d44-239">Calls and meetings</strong></span></span></td>
<td align="left"><p><span data-ttu-id="d2d44-240">Autoriser la planification de réunions privées : <strong>activé</strong></span><span class="sxs-lookup"><span data-stu-id="d2d44-240">Allow scheduling for private meetings: <strong>On</strong></span></span></p><p><span data-ttu-id="d2d44-241">Autoriser la planification de réunions de canal : <strong>activé</strong></span><span class="sxs-lookup"><span data-stu-id="d2d44-241">Allow scheduling for channel meetings: <strong>On</strong></span></span></p></td>
<td align="left"><p><span data-ttu-id="d2d44-242">Activer ce paramètre permet aux utilisateurs de planifier des réunions privées</span><span class="sxs-lookup"><span data-stu-id="d2d44-242">Enabling this setting allows users to schedule private meetings</span></span></p><p><span data-ttu-id="d2d44-243">Activer ce paramètre permet aux utilisateurs de planifier des réunions de canal</span><span class="sxs-lookup"><span data-stu-id="d2d44-243">Enabling this setting allows users to schedule channel meetings</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="d2d44-244">Les réunions planifiées peuvent être organisées par le biais du client de bureau Teams, d’un navigateur ou de Microsoft Outlook en utilisant le complément Réunion pour Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d2d44-244">Scheduled meetings can be organized via the Teams desktop client, a browser, or via Microsoft Outlook using the meeting add-in for Microsoft Teams.</span></span> <span data-ttu-id="d2d44-245">Une fois les réunions planifiées activées dans Teams, nous recommandons de commencer à former les utilisateurs à la création de nouvelles réunions Teams ou de mettre à jour les réunions Skype Entreprise sur les réunions Teams.</span><span class="sxs-lookup"><span data-stu-id="d2d44-245">Once scheduled meetings in Teams is enabled, we recommend you start educating users to create new Teams meetings or update existing Skype for Business meetings to Teams meetings.</span></span>

### <a name="rollout-of-teams-for-calling"></a><span data-ttu-id="d2d44-246">Lancement de Teams pour les appels</span><span class="sxs-lookup"><span data-stu-id="d2d44-246">Rollout of Teams for calling</span></span>

<span data-ttu-id="d2d44-247">La fonctionnalité d’appels privés de Teams sera développée en permanence, et fournira au fil du temps un remplacement attrayant de Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="d2d44-247">Private calling is the Teams capability that will be continuously developed, and over time provide a compelling replacement to Skype for Business.</span></span> <span data-ttu-id="d2d44-248">Lorsque votre organisation estime que les fonctionnalités d’appels privés de Teams répondent à ses besoins, les paramètres suivants peuvent être configurés au niveau du client pour activer les appels privés dans Teams.</span><span class="sxs-lookup"><span data-stu-id="d2d44-248">When your organization considers that Teams private calling capabilities meet key business requirements, the following settings can be configured at the tenant level to enable private calling in Teams.</span></span> 

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="d2d44-249">Section</span><span class="sxs-lookup"><span data-stu-id="d2d44-249">Section</span></span></th>
<th align="left"><span data-ttu-id="d2d44-250">Paramètre</span><span class="sxs-lookup"><span data-stu-id="d2d44-250">Setting</span></span></th>
<th align="left"><span data-ttu-id="d2d44-251">Description</span><span class="sxs-lookup"><span data-stu-id="d2d44-251">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><strong><br><span data-ttu-id="d2d44-252">Appels et réunions</strong></span><span class="sxs-lookup"><span data-stu-id="d2d44-252">Calls and meetings</strong></span></span></td>
<td align="left"><p><span data-ttu-id="d2d44-253">Autoriser les appels privés : <strong>activé</strong></span><span class="sxs-lookup"><span data-stu-id="d2d44-253">Allow private calling: <strong>On</strong></span></span></p></td>
<td align="left"><p><span data-ttu-id="d2d44-254">Activer ce paramètre permet aux utilisateurs de passer des appels privés (audio et vidéo)</span><span class="sxs-lookup"><span data-stu-id="d2d44-254">Enabling this setting allows users to place private calls (audio and video)</span></span></p></td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr class="header">
<td align="center"><p><img src="media/guidance_SkypeforBusiness_image3.png" /></p>
<p><span data-ttu-id="d2d44-255">Remarque</span><span class="sxs-lookup"><span data-stu-id="d2d44-255">Note</span></span></p></td>
<td align="left"><br><br><span data-ttu-id="d2d44-256">Autoriser les utilisateurs à discuter en privé : lorsque ce paramètre est activé, les utilisateurs peuvent discuter en privé avec les autres utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="d2d44-256">Allow users to chat privately: Enabling this setting allows users to chat with other users privately.</span></span></td>
</tr>
</thead>
<tbody>
</tbody>
</table>


<span data-ttu-id="d2d44-257">À cette étape, il doit être demandé à tous les utilisateurs de choisir Teams comme application d’appels favorite.</span><span class="sxs-lookup"><span data-stu-id="d2d44-257">At this stage, all users must be instructed to choose Teams as the preferred calling app.</span></span>

<span data-ttu-id="d2d44-258">Avec l’activation des appels privés, Teams offrira toutes les fonctionnalités fournies actuellement par Skype Entreprise, et les utilisateurs peuvent commencer à utiliser Teams pour répondre à leurs besoins en matière de communication et de collaboration.</span><span class="sxs-lookup"><span data-stu-id="d2d44-258">With the enablement of private calling, Teams will deliver all capabilities currently provided by Skype for Business, and users can start using Teams to fulfill their communications and collaboration requirements.</span></span>


<table>
<thead>
<tr class="header">
<td align="left"><p><img src="media/pilot_essentials_image2.png" /></p></td>
<td align="left">
<p><span data-ttu-id="d2d44-259"><strong>Action suivante :</strong> lorsque Teams est opérationnelle côte à côte avec Skype Entreprise, [générez une valeur ajoutée en incitant les utilisateurs à adopter Teams](continue-journey.md), en continuant votre parcours de remplacement de Skype Entreprise par Teams.</span><span class="sxs-lookup"><span data-stu-id="d2d44-259"><strong>Next Action:</strong> Once Teams is up and running side-by-side with Skype for Business, [Drive Value through user adoption of Teams](continue-journey.md), while continuing your journey from Skype for Business to Teams.</span></span></td>
</tr>
</thead>
<tbody>
</tbody>
</table>