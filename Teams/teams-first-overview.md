---
title: Commencez par déployer Microsoft teams
author: LaszloSomi
ms.author: lsomi
manager: swerth
audience: Admin
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: lsomi
localization_priority: Normal
search.appverid: MET150
description: Suivez ces instructions pour déployer Microsoft teams en tant que premier Microsoft 365 ou Workload 365.
ROBOTS: NOINDEX, NOFOLLOW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 84408fdb6d58e755d0eb4c775d1954f22791264c
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/10/2020
ms.locfileid: "44691000"
---
# <a name="roll-out-microsoft-teams-first"></a><span data-ttu-id="1a474-103">Commencez par déployer Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="1a474-103">Roll out Microsoft Teams First</span></span>

<span data-ttu-id="1a474-104">Microsoft teams permet à vos employés de rester connectés et de collaborer entre eux, en particulier dans le temps sans précédent où le Bureau à distance est une réalité de personnes dans le monde entier.</span><span class="sxs-lookup"><span data-stu-id="1a474-104">Microsoft Teams can help your employees stay connected and collaborate with each other, especially in the current unprecedented time where remote work is a reality of employees around the world.</span></span> <span data-ttu-id="1a474-105">Être en mesure de discuter, faire des réunions vidéo et collaborer sur des documents Office dans teams peut aider les entreprises à rester productifs.</span><span class="sxs-lookup"><span data-stu-id="1a474-105">Being able to chat, do video meetings and collaborate on Office documents within Teams can help companies stay productive.</span></span> <span data-ttu-id="1a474-106">Qu’il s’agisse d’une petite entreprise, d’une entreprise à but non lucratif ou d’une grande entreprise, vous pouvez commencer à utiliser teams comme première charge de travail dans Microsoft 365 ou la suite Office 365 avant de déployer une application ou un service Office.</span><span class="sxs-lookup"><span data-stu-id="1a474-106">Whether you are a small business, a non-profit or a large organization, you can get started with Teams as the first workload within Microsoft 365 or Office 365 suite before deploying any other Office app or service.</span></span>

<span data-ttu-id="1a474-107">Cet article décrit les éléments à prendre en compte lors de l’approche « commencer par Teams ».</span><span class="sxs-lookup"><span data-stu-id="1a474-107">This article details the considerations you must make with the "Teams First" approach.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1a474-108">Bien que les équipes puissent être déployées sur le premier Cloud de votre organisation, le déploiement d’équipes devrait faire partie de votre stratégie de déploiement de Cloud globale.</span><span class="sxs-lookup"><span data-stu-id="1a474-108">While Teams can be your organization's first cloud deployed workload, deploying Teams should be part of your overall cloud deployment strategy.</span></span>

<span data-ttu-id="1a474-109">Si vous avez déjà déployé d’autres services Microsoft 365 ou Office 365 et que teams est votre prochain travail de déploiement (plutôt que le premier), commencez par [déployer teams](How-to-roll-out-teams.md).</span><span class="sxs-lookup"><span data-stu-id="1a474-109">If you have already rolled out other Microsoft 365 or Office 365 services and Teams is your next workload to roll out (instead of the first), start with [How to roll out Teams](How-to-roll-out-teams.md).</span></span>

## <a name="start-here"></a><span data-ttu-id="1a474-110">Démarrez ici</span><span class="sxs-lookup"><span data-stu-id="1a474-110">Start here</span></span>

<span data-ttu-id="1a474-111">Pour commencer à utiliser votre premier déploiement de Microsoft Teams, vous devez effectuer une réunion au minimum.</span><span class="sxs-lookup"><span data-stu-id="1a474-111">To get started with your Teams First deployment you will need to meet at minimum some pre-requisites.</span></span> <span data-ttu-id="1a474-112">La liste suivante indique les éléments à mettre en place pour votre organisation afin que les équipes puissent être activées :</span><span class="sxs-lookup"><span data-stu-id="1a474-112">The following list will show what you must have in place for your organization before Teams can be enabled:</span></span>

1.  <span data-ttu-id="1a474-113">Organisation Microsoft 365 ou Office 365 configurée avec votre nom de domaine</span><span class="sxs-lookup"><span data-stu-id="1a474-113">A Microsoft 365 or Office 365 organization configured with your domain name</span></span>

2.  <span data-ttu-id="1a474-114">Une solution de synchronisation Azure Active Directory (AAD Connect) ou d’identité Cloud similaire, avec tous les attributs requis synchronisés avec votre client</span><span class="sxs-lookup"><span data-stu-id="1a474-114">Azure Active Directory connectivity (AAD connect) or similar cloud identity sync solution – with all required attributes synched with your tenant</span></span>  
    <span data-ttu-id="1a474-115">Pour comprendre les attributs synchronisés avec la synchronisation AAD, voir [synchronisation d’Azure ad Connect : attributs synchronisés avec Azure Active Directory](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)</span><span class="sxs-lookup"><span data-stu-id="1a474-115">To understand the attributes synchronized with AAD sync, read [Azure AD Connect sync: Attributes synchronized to Azure Active Directory](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)</span></span>

3.  <span data-ttu-id="1a474-116">Licences utilisateur appropriées affectées aux équipes</span><span class="sxs-lookup"><span data-stu-id="1a474-116">Appropriate user licenses assigned for Teams</span></span>  
    <span data-ttu-id="1a474-117">Pour comprendre les licences d’équipe, voir [Description du service Microsoft teams](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).</span><span class="sxs-lookup"><span data-stu-id="1a474-117">To understand Teams licensing, read [Microsoft Teams service description](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).</span></span>

4.  <span data-ttu-id="1a474-118">Réseau de l’organisation préparé pour teams</span><span class="sxs-lookup"><span data-stu-id="1a474-118">Organization's network prepared for Teams</span></span>  
    <span data-ttu-id="1a474-119">Pour mieux comprendre la préparation du réseau, voir [préparer le réseau de votre organisation pour teams](prepare-network.md).</span><span class="sxs-lookup"><span data-stu-id="1a474-119">To understand network preparation, read [Prepare your organization's network for Teams](prepare-network.md).</span></span>

5.  <span data-ttu-id="1a474-120">Autorisez l’accès réseau à Exchange, SharePoint et OneDrive entreprise dans Microsoft 365 ou Office 365 : [URL et plages d’adresses IP d’office 365](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).</span><span class="sxs-lookup"><span data-stu-id="1a474-120">Allow network access to Exchange, Sharepoint, and OneDrive for Business in Microsoft 365 or Office 365: [Office 365 URLs and IP address ranges](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).</span></span>

> [!NOTE]
> <span data-ttu-id="1a474-121">Les clients créés après le 1er septembre 2019 sont configurés en mode équipes uniquement.</span><span class="sxs-lookup"><span data-stu-id="1a474-121">Tenants created after September 1, 2019 are provisioned in Teams Only mode.</span></span>
> 
> [!IMPORTANT]
> <span data-ttu-id="1a474-122">Si vous avez déployé Skype entreprise Server et que votre client a été approvisionné après le 1er septembre 2019, contactez le support technique pour activer les fonctionnalités de coexistence pour Teams.</span><span class="sxs-lookup"><span data-stu-id="1a474-122">If you have Skype for Business Server deployed, and your tenant was provisioned AFTER September 1, 2019, please contact support to enable coexistence capabilities for Teams.</span></span> <span data-ttu-id="1a474-123">Assurez-vous que votre « stratégie de mise à niveau de l’organisation » est définie sur « mode insulaire » <span class="underline">avant</span> d’affecter des licences teams à un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="1a474-123">Make sure your 'Organization wide upgrade policy' is set to 'Island mode' <span class="underline">before</span> you assign any Teams licenses to a user.</span></span>

## <a name="migration-starting-points"></a><span data-ttu-id="1a474-124">Points de départ de la migration</span><span class="sxs-lookup"><span data-stu-id="1a474-124">Migration Starting points</span></span>

<span data-ttu-id="1a474-125">Le passage à Microsoft 365 ou Office 365 et aux fonctionnalités disponibles dans teams en fonction de votre point de départ et de l’existence de Skype entreprise ou de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1a474-125">Your journey to Microsoft 365 or Office 365 and features available in Teams depending on your starting point and the existence of on premises Skype for Business or Lync server.</span></span> <span data-ttu-id="1a474-126">Les sections suivantes décrivent en détail les fonctionnalités de base et les options de configuration, en plus de celles préalables ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="1a474-126">The following sections will detail basic capabilities and configuration options in addition to the pre-requisites above.</span></span> <span data-ttu-id="1a474-127">Nous avons scindé les scénarios de point de départ aux rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="1a474-127">We have broken down the starting point scenarios to the following topics:</span></span>

<span data-ttu-id="1a474-128">**Configuration des équipes de client**: les modes client et utilisateur permettent de contrôler le comportement du destinataire.</span><span class="sxs-lookup"><span data-stu-id="1a474-128">**Tenant Teams Configuration**: Tenant and user modes are used to control the recipient's behavior.</span></span> <span data-ttu-id="1a474-129">Ces paramètres peuvent être affectés au niveau du client ou au niveau de l’utilisateur dans une organisation.</span><span class="sxs-lookup"><span data-stu-id="1a474-129">These settings can be assigned on the tenant level or the user level in an organization.</span></span> <span data-ttu-id="1a474-130">Pour en savoir plus, voir [coexistence avec Skype entreprise](coexistence-chat-calls-presence.md).</span><span class="sxs-lookup"><span data-stu-id="1a474-130">To learn more, read [Coexistence with Skype for Business](coexistence-chat-calls-presence.md).</span></span>

<span data-ttu-id="1a474-131">**Discussions/communications externes dans teams**: les services de chat font référence à des conversations d’égal à égal ou à des conversations de groupe au sein de l’organisation ou à l’extérieur.</span><span class="sxs-lookup"><span data-stu-id="1a474-131">**Chat / External communication in Teams**: Chat services refer to peer to peer or group chat conversations within and organization or externally to the organization.</span></span> <span data-ttu-id="1a474-132">La communication externe est également appelée Fédération dans Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="1a474-132">External communication is also referred to as federation in Skype for Business.</span></span>

<span data-ttu-id="1a474-133">**Créer et afficher des réunions dans teams**: un utilisateur peut toujours créer des réunions en ligne via le complément Outlook teams et la fonction de numérotation RTC est disponible dans toutes les situations après la licence de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="1a474-133">**Create and view meetings in Teams**: A user can always create online meetings via the Outlook Teams add-in and PSTN dial-in is available in all scenarios once the user is licensed.</span></span> <span data-ttu-id="1a474-134">Équipes et informations de calendrier de Skype entreprise Store dans la boîte aux lettres Exchange de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="1a474-134">Teams and Skype for Business store calendaring information in the user's Exchange mailbox.</span></span> <span data-ttu-id="1a474-135">Dans le cas d’un serveur Exchange local, le client Microsoft teams doit 2016 être en mesure d’interagir avec la boîte aux lettres de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="1a474-135">On premises Exchange server must be Exchange Server 2016 CU3 or above for the Teams client to be able to interact with the user's mailbox.</span></span> <span data-ttu-id="1a474-136">Sans accès à la boîte aux lettres Exchange, l’icône calendrier dans Teams ne s’affiche pas et l’utilisateur ne pourra pas afficher, créer ou modifier des réunions dans le client Teams.</span><span class="sxs-lookup"><span data-stu-id="1a474-136">Without Exchange mailbox access the Calendar icon in Teams will not appear and they user will not be able to view, create or modify meetings in the Teams client.</span></span>

<span data-ttu-id="1a474-137">**Fonctions d’appel VoIP/PSTN dans teams**: les appels peuvent être vocaux sur IP (VoIP) ou réseau téléphonique commuté (RTC).</span><span class="sxs-lookup"><span data-stu-id="1a474-137">**Calling features VoIP / PSTN in Teams**: Calling can be Voice over IP (VoIP) or Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="1a474-138">La connectivité VoIP s’exécute en mode natif entre les clients Teams, tandis que la connectivité PSTN se produit lorsqu’un utilisateur compose un numéro de téléphone externe.</span><span class="sxs-lookup"><span data-stu-id="1a474-138">VoIP connectivity happens natively between Teams clients, while PSTN connectivity happen when a user dials an outside phone number.</span></span>  

<span data-ttu-id="1a474-139">Teams prend en charge deux types de connectivité PSTN.</span><span class="sxs-lookup"><span data-stu-id="1a474-139">Teams support two types of PSTN connectivity.</span></span> <span data-ttu-id="1a474-140">Plan d’appel Microsoft, lorsque Microsoft fournit une infrastructure de téléphonie dont le numéro de téléphone pour un utilisateur ou une configuration de routage directe, où le client fournit la connectivité téléphonique par le biais d’un contrôleur de bordure de session (SBC) pour l’utilisateur de teams.</span><span class="sxs-lookup"><span data-stu-id="1a474-140">Microsoft Calling Plan, when Microsoft provides telephony infrastructure including the phone number for a user, or Direct Routing configuration, where the customer provides the telephony connectivity over a Session Border Controller (SBC) for the Teams user.</span></span>  
<span data-ttu-id="1a474-141">Pour en savoir plus, consultez [l’offre qui vous convient le mieux ? et le](calling-plan-landing-page.md) [routage direct du système téléphonique](direct-routing-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="1a474-141">To learn more, read [Which Calling Plan is right for you?](calling-plan-landing-page.md) and [Phone System Direct Routing](direct-routing-landing-page.md).</span></span>

<span data-ttu-id="1a474-142">**Collaboration sur équipes et canaux dans teams**: en équipe, les équipes sont des groupes de personnes qui ont été réunis pour le travail, les projets ou les centres d’intérêt communs.</span><span class="sxs-lookup"><span data-stu-id="1a474-142">**Teams and Channels collaboration in Teams**: In Teams, teams are groups of people brought together for work, projects, or common interests.</span></span> <span data-ttu-id="1a474-143">Les équipes sont composées de canaux.</span><span class="sxs-lookup"><span data-stu-id="1a474-143">Teams are made up of channels.</span></span> <span data-ttu-id="1a474-144">Chaque canal est intégré à un sujet, tel qu’un « événements d’équipe », un nom de service ou un simple plaisir.</span><span class="sxs-lookup"><span data-stu-id="1a474-144">Each channel is built around a topic, like "Team Events," a department name, or just for fun.</span></span> <span data-ttu-id="1a474-145">Les canaux sont l’endroit où vous organisez des réunions, des conversations et travaillez ensemble.</span><span class="sxs-lookup"><span data-stu-id="1a474-145">Channels are where you hold meetings, have conversations, and work on files together.</span></span> <span data-ttu-id="1a474-146">Lors de la collaboration</span><span class="sxs-lookup"><span data-stu-id="1a474-146">During collaboration</span></span>

<span data-ttu-id="1a474-147">**OneDrive entreprise (partage de fichiers P2P) dans teams**: à l’extérieur des équipes et des canaux, les utilisateurs de teams peuvent partager des fichiers d’égal à égal à l’aide de OneDrive entreprise ou d’autres programmes de fichiers de partage P2P tels que les fichiers Citrix, Dropbox, Box et Google Drive.</span><span class="sxs-lookup"><span data-stu-id="1a474-147">**OneDrive for Business (P2P file sharing) in Teams**: Outside of Teams and Channels, Teams users can share files peer-to-peer using OneDrive for business or other P2P sharing file programs such as Citrix Files, DropBox, Box and Google Drive.</span></span> <span data-ttu-id="1a474-148">Pour OneDrive entreprise, un utilisateur doit avoir une licence SharePoint Online affectée.</span><span class="sxs-lookup"><span data-stu-id="1a474-148">For OneDrive for business a user must have SharePoint Online license assigned.</span></span>

<span data-ttu-id="1a474-149">**Plateforme d’application**: les applications fournissent des outils prédéfinis pour votre organisation afin de tirer le meilleur parti de teams.</span><span class="sxs-lookup"><span data-stu-id="1a474-149">**Application Platform**: Apps provide out-of-the-box tools for your organization to get more out of Teams.</span></span> <span data-ttu-id="1a474-150">Ces applications associent les fonctionnalités des onglets, des extensions de messagerie, des connecteurs et des robots proposés par Microsoft, par une tierce partie ou par les développeurs de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="1a474-150">These apps combine the functionality of tabs, messaging extensions, connectors, and bots provided by Microsoft, built by a third-party, or by developers in your organization.</span></span>

<span data-ttu-id="1a474-151">**Fonctionnalités de sécurité et de conformité :** Teams dispose d’une large gamme d’informations pour vous aider à utiliser les zones de conformité, notamment les stratégies de rétention, la protection contre la perte de données (DLP), la découverte électronique et la conservation légale pour les canaux, les conversations et les fichiers, la recherche dans le journal d’audit.</span><span class="sxs-lookup"><span data-stu-id="1a474-151">**Security and Compliance features:** Teams has a wide range of information to help you with compliance areas, including retention policies, Data Loss Protection (DLP), eDiscovery and legal hold for channels, chats and files, audit log search.</span></span> <span data-ttu-id="1a474-152">Pour en savoir plus, voir [sécurité et conformité dans Microsoft teams](security-compliance-overview.md).</span><span class="sxs-lookup"><span data-stu-id="1a474-152">To learn more, read [Security and compliance in Microsoft Teams](security-compliance-overview.md).</span></span>  

> [!NOTE]
> <span data-ttu-id="1a474-153">Les fonctionnalités de eDiscovery avancées nécessitent une licence E5.</span><span class="sxs-lookup"><span data-stu-id="1a474-153">Advance eDiscovery features require E5 licensing.</span></span>

<span data-ttu-id="1a474-154">[Comparer les options de licence](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans).</span><span class="sxs-lookup"><span data-stu-id="1a474-154">[Compare licensing options](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans).</span></span>

<span data-ttu-id="1a474-155">Découvrez [Comment Exchange et Microsoft teams interagissent](exchange-teams-interact.md) pour découvrir les fonctionnalités de conformité disponibles dans votre scénario.</span><span class="sxs-lookup"><span data-stu-id="1a474-155">Read [How Exchange and Microsoft Teams interact](exchange-teams-interact.md) to learn which compliance features are available in your scenario.</span></span>

## <a name="organizations-span-classunderlinewithoutspan-skype-for-business-or-lync-server"></a><span data-ttu-id="1a474-156">Organisations **<span class="underline">sans</span>** Skype entreprise ou Lync Server</span><span class="sxs-lookup"><span data-stu-id="1a474-156">Organizations **<span class="underline">without</span>** Skype for Business or Lync server</span></span>

<span data-ttu-id="1a474-157">Ce point de départ part du principe que votre organisation n’utilise pas Skype entreprise ou Lync Server actuellement et que teams sera votre première application dans Microsoft 365 ou Office 365.</span><span class="sxs-lookup"><span data-stu-id="1a474-157">This starting point assumes that your organization does not utilize Skype for Business or Lync server currently and Teams will be your first application in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="1a474-158">Le tableau suivant répertorie les fonctionnalités de configuration de haut niveau et d’utilisateur final pour les équipes de services principaux.</span><span class="sxs-lookup"><span data-stu-id="1a474-158">The following table details high level configuration and end user capabilities for Teams for core services.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="1a474-159">Élément</span><span class="sxs-lookup"><span data-stu-id="1a474-159">Item</span></span></th>
<th><span data-ttu-id="1a474-160">Remarques</span><span class="sxs-lookup"><span data-stu-id="1a474-160">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="1a474-161">Configuration des équipes client</span><span class="sxs-lookup"><span data-stu-id="1a474-161">Tenant Teams configuration</span></span></td>
<td><span data-ttu-id="1a474-162">Le mode équipes uniquement, les fonctionnalités de conversation et d’appel ne sont disponibles que dans teams</span><span class="sxs-lookup"><span data-stu-id="1a474-162">Teams Only mode, all chat and calling features are in Teams Only</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="1a474-163">Discussions/communications externes dans teams</span><span class="sxs-lookup"><span data-stu-id="1a474-163">Chat / External Communication in Teams</span></span></td>
<td><p><span data-ttu-id="1a474-164">Internal (organisation Microsoft 365 ou Office 365) et communications externes possibles depuis teams</span><span class="sxs-lookup"><span data-stu-id="1a474-164">Internal (intra Microsoft 365 or Office 365 organization) and external chat communication possible from Teams</span></span></p>
<p><span data-ttu-id="1a474-165"><em>Remarque : les entrées DNS doivent être configurées pour l’accès externe.</span><span class="sxs-lookup"><span data-stu-id="1a474-165"><em>Note: DNS entries must be configured for external access.</span></span> <span data-ttu-id="1a474-166">Les enregistrements DNS de Skype entreprise sont nécessaires même si vous n’avez pas Skype entreprise local ou dans Microsoft 365 ou Office 365, pour autoriser la Fédération avec Lync et les environnements Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="1a474-166">Skype for Business DNS records are needed even though you don't have Skype for Business on-premises, or in Microsoft 365 or Office 365, to allow federation with Lync and Skype for Business environments.</span></span><br /><span data-ttu-id="1a474-167">
<a href="https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records">Enregistrements système de noms de domaine externes</a></em></span><span class="sxs-lookup"><span data-stu-id="1a474-167">
<a href="https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records">External Domain Name System records</a></em></span></span></p></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="1a474-168"><em>Créer et afficher des réunions dans Microsoft teams</em></span><span class="sxs-lookup"><span data-stu-id="1a474-168"><em>Create and view Meetings in Teams</em></span></span></td>
<td><p><span data-ttu-id="1a474-169"><em>Possibilité de créer des réunions via le complément Outlook</em></span><span class="sxs-lookup"><span data-stu-id="1a474-169"><em>Able to create meetings via Outlook add-in</em></span></span></p>
<p><span data-ttu-id="1a474-170"><em>Les fonctionnalités de numérotation et de connexion RTC sont disponibles avec les licences de conférence audio.</span><span class="sxs-lookup"><span data-stu-id="1a474-170"><em>PSTN Dial in and Dial out capability is available with the Audio Conferencing licenses.</span></span><br />
<span data-ttu-id="1a474-171">Remarque : l’accès au calendrier teams nécessite Exchange 2016 CU3 + local déployé avec Exchange hybride établi : <a href="https://docs.microsoft.com/exchange/hybrid-deployment/deploy-hybrid">créer un déploiement hybride à l’aide de l’Assistant Configuration hybride</a></span><span class="sxs-lookup"><span data-stu-id="1a474-171">Note: Teams calendar access requires Exchange 2016 CU3+ on-premises deployed with Exchange hybrid established: <a href="https://docs.microsoft.com/exchange/hybrid-deployment/deploy-hybrid">Create a hybrid deployment with the Hybrid Configuration wizard</a></span></span><br />
<span data-ttu-id="1a474-172">En plus de la configuration hybride Exchange, établissez l’authentification OAuth Exchange : <a href="https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help">configurez l’authentification OAuth entre les organisations Exchange et Exchange Online</a> .</em></span><span class="sxs-lookup"><span data-stu-id="1a474-172">In addition to Exchange hybrid configuration, establish Exchange OAuth authentication: <a href="https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help">Configure OAuth authentication between Exchange and Exchange Online organizations</a></em></span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="1a474-173">Fonctions d’appel</span><span class="sxs-lookup"><span data-stu-id="1a474-173">Calling Features</span></span><br />
<span data-ttu-id="1a474-174">VoIP/PSTN dans teams</span><span class="sxs-lookup"><span data-stu-id="1a474-174">VoIP / PSTN in Teams</span></span></td>
<td><p><span data-ttu-id="1a474-175">VoIP est disponible en interne et en externe sur le client</span><span class="sxs-lookup"><span data-stu-id="1a474-175">VoIP internally and externally to the tenant is available</span></span></p>
<p><span data-ttu-id="1a474-176">Les services RTC peuvent être configurés via le système Microsoft Phone, ainsi que l’ajout d’un plan d’appel Microsoft ou du routage direct.</span><span class="sxs-lookup"><span data-stu-id="1a474-176">PSTN services can be configured via Microsoft Phone System, plus adding a Microsoft Calling Plan or Direct Routing.</span></span></p></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="1a474-177">Collaborer sur équipes et canaux dans teams</span><span class="sxs-lookup"><span data-stu-id="1a474-177">Teams and Channels collaboration in Teams</span></span></td>
<td><p><span data-ttu-id="1a474-178">Pour une utilisation complète, y compris les fonctionnalités de conformité, une licence SharePoint Online doit être attribuée à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="1a474-178">For full experience, including compliance features, a SharePoint Online license need to be assigned to the user.</span></span></p>
<p><span data-ttu-id="1a474-179">La migration de sites SharePoint locaux existants n’est pas requise.</span><span class="sxs-lookup"><span data-stu-id="1a474-179">Migration of existing on-premises SharePoint sites is not required.</span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="1a474-180">OneDrive entreprise (partage de fichiers P2P)</span><span class="sxs-lookup"><span data-stu-id="1a474-180">OneDrive for Business (P2P file sharing)</span></span></td>
<td><span data-ttu-id="1a474-181">OneDrive entreprise nécessite l’attribution d’une licence SharePoint Online à un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="1a474-181">OneDrive for Business requires a user to have a SharePoint Online license assigned.</span></span> <span data-ttu-id="1a474-182">Sans cette licence le partage de fichiers d’égal à égal n’est pas possible.</span><span class="sxs-lookup"><span data-stu-id="1a474-182">Without this license peer-to-peer file sharing will not be possible.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="1a474-183">Plateforme d’application</span><span class="sxs-lookup"><span data-stu-id="1a474-183">Application platform</span></span></td>
<td><span data-ttu-id="1a474-184">Les utilisateurs pourront utiliser les applications qui sont conçues pour eux conformément aux politiques de votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="1a474-184">Users will be able to use the apps that are designated available for them according to your company policies.</span></span><br />
<span data-ttu-id="1a474-185">Pour en savoir plus <a href="https://docs.microsoft.com/microsoftteams/admin-settings">, voir paramètres d’administration des applications dans Microsoft teams</a> .</span><span class="sxs-lookup"><span data-stu-id="1a474-185">Learn more here: <a href="https://docs.microsoft.com/microsoftteams/admin-settings">Admin settings for apps in Teams</a></span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="1a474-186">Fonctionnalités de sécurité et de conformité</span><span class="sxs-lookup"><span data-stu-id="1a474-186">Security and Compliance features</span></span></td>
<td><ul>
<li><p><span data-ttu-id="1a474-187">Des stratégies de rétention sont disponibles</span><span class="sxs-lookup"><span data-stu-id="1a474-187">Retention policies are available</span></span></p></li>
<li><p><span data-ttu-id="1a474-188">la découverte électronique et les conservations juridiques pour la conformité aux messages de canal sont prises en charge</span><span class="sxs-lookup"><span data-stu-id="1a474-188">eDiscovery and Legal Hold for compliance on channel messages is supported</span></span></p></li>
<li><p><span data-ttu-id="1a474-189">Les stratégies de protection contre la perte de données (DLP) sont disponibles</span><span class="sxs-lookup"><span data-stu-id="1a474-189">Data Loss Prevention policies (DLP) are available</span></span></p></li>
</ul>
<p><span data-ttu-id="1a474-190">Ensemble complet des fonctionnalités disponibles avec Exchange Online, Exchange local prend en charge la plupart de ces fonctionnalités, voir <a href="https://docs.microsoft.com/MicrosoftTeams/exchange-teams-interact">Comment Exchange et teams interagissent</a> pour la liste complète.</span><span class="sxs-lookup"><span data-stu-id="1a474-190">Full feature set available with Exchange Online, Exchange on-premises supports most of these features, see <a href="https://docs.microsoft.com/MicrosoftTeams/exchange-teams-interact">How Exchange and Teams interact</a> for full list.</span></span></p></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-without-skype-for-business-or-lync-server"></a><span data-ttu-id="1a474-191">Étapes d’activation pour les organisations sans Skype entreprise ou Lync Server</span><span class="sxs-lookup"><span data-stu-id="1a474-191">Enablement steps for organizations without Skype for Business or Lync Server</span></span>

1.  <span data-ttu-id="1a474-192">Répondez aux conditions préalables décrites dans la section début</span><span class="sxs-lookup"><span data-stu-id="1a474-192">Meet pre-requisites detailed in the Start Here section above</span></span>

2.  <span data-ttu-id="1a474-193">Basculer le client en mode équipes uniquement (pour les clients existants uniquement) : [définir vos paramètres de coexistence et de mise à niveau](setting-your-coexistence-and-upgrade-settings.md).</span><span class="sxs-lookup"><span data-stu-id="1a474-193">Switch tenant into Teams Only mode (for existing tenants only): [Setting your coexistence and upgrade settings](setting-your-coexistence-and-upgrade-settings.md).</span></span>

3.  <span data-ttu-id="1a474-194">Configurez votre client conformément aux politiques de votre entreprise : gérer les [paramètres de Microsoft teams pour votre organisation](enable-features-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="1a474-194">Configure your tenant in accordance with your company's business/company policies: [Manage Microsoft Teams settings for your organization](enable-features-office-365.md).</span></span>

4.  <span data-ttu-id="1a474-195">Déployer le client teams auprès de vos utilisateurs : [accéder aux clients pour teams](get-clients.md)</span><span class="sxs-lookup"><span data-stu-id="1a474-195">Deploy the Teams client to your users: [Get clients for Teams](get-clients.md)</span></span>

5.  <span data-ttu-id="1a474-196">Piloter votre programme d’adoption</span><span class="sxs-lookup"><span data-stu-id="1a474-196">Drive your adoption program</span></span>  
    [<span data-ttu-id="1a474-197">Adopter Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1a474-197">Adopt Microsoft Teams</span></span>](adopt-microsoft-teams-landing-page.md)
    
    [<span data-ttu-id="1a474-198">Liste de contrôle de démarrage rapide pour l’adoption de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1a474-198">Microsoft Teams adoption quick start checklist</span></span>](teams-adoption-quick-start-checklist.md)

6.  <span data-ttu-id="1a474-199">Commencer à planifier déplacer d’autres charges de travail vers Microsoft 365 ou Office 365</span><span class="sxs-lookup"><span data-stu-id="1a474-199">Begin planning moving other workloads to Microsoft 365 or Office 365</span></span>

## <a name="organizations-span-classunderlinewithspan-skype-for-business-or-lync-server"></a><span data-ttu-id="1a474-200">Organisations **<span class="underline">avec</span>** Skype entreprise ou Lync Server</span><span class="sxs-lookup"><span data-stu-id="1a474-200">Organizations **<span class="underline">with</span>** Skype for Business or Lync server</span></span>

<span data-ttu-id="1a474-201">Ce point de départ part du principe que votre organisation utilise Skype entreprise 2019 ou 2015 + ou Lync 2013 + Server en local.</span><span class="sxs-lookup"><span data-stu-id="1a474-201">This starting point assumes that your organization utilizes Skype for Business 2019 or 2015+ or Lync 2013+ server on premises.</span></span> <span data-ttu-id="1a474-202">Nous proposons déjà des recommandations complètes pour les organisations migrant de serveurs locaux vers équipes et elles doivent être suivies dans ces scénarios.</span><span class="sxs-lookup"><span data-stu-id="1a474-202">We already have extensive guidance for organizations migrating from on premises servers to Teams and it should be followed for these scenarios.</span></span> <span data-ttu-id="1a474-203">Ce guide est spécifique au scénario que teams est la première application utilisée dans Microsoft 365 ou Office 365.</span><span class="sxs-lookup"><span data-stu-id="1a474-203">This guidance is specific to the scenario that Teams is the first application you utilize in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="1a474-204">Le tableau suivant répertorie les fonctionnalités de configuration de haut niveau et d’utilisateur final pour les équipes de services principaux.</span><span class="sxs-lookup"><span data-stu-id="1a474-204">The following table details high level configuration and end user capabilities for Teams for core services.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="1a474-205">Élément</span><span class="sxs-lookup"><span data-stu-id="1a474-205">Item</span></span></th>
<th><span data-ttu-id="1a474-206">Remarques</span><span class="sxs-lookup"><span data-stu-id="1a474-206">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="1a474-207">Configuration des équipes client</span><span class="sxs-lookup"><span data-stu-id="1a474-207">Tenant Teams configuration</span></span></td>
<td><span data-ttu-id="1a474-208">Mode insulaire</span><span class="sxs-lookup"><span data-stu-id="1a474-208">Islands mode</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="1a474-209">Discussions/communications externes dans teams</span><span class="sxs-lookup"><span data-stu-id="1a474-209">Chat / External Communication in Teams</span></span></td>
<td><span data-ttu-id="1a474-210">Interne uniquement au sein de votre client, la communication externe (Fédération) est via le déploiement de Skype entreprise ou de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1a474-210">Internal within your own tenant only, external communication (federation) is via your Skype for Business or Lync server deployment</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="1a474-211">Créer et afficher des réunions dans Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="1a474-211">Create and view Meetings in Teams</span></span></td>
<td><p><span data-ttu-id="1a474-212">Possibilité de créer des réunions via le complément Outlook</span><span class="sxs-lookup"><span data-stu-id="1a474-212">Able to create meetings via Outlook add-in</span></span></p>
<p><span data-ttu-id="1a474-213">Les fonctionnalités de numérotation et de connexion RTC sont disponibles avec les licences de conférence audio.</span><span class="sxs-lookup"><span data-stu-id="1a474-213">PSTN Dial in and Dial out capability is available with the Audio Conferencing licenses.</span></span><br />
<span data-ttu-id="1a474-214">L’accès au calendrier teams nécessite Exchange 2016 CU3 + local déployé avec Exchange hybride établi :</span><span class="sxs-lookup"><span data-stu-id="1a474-214">Teams calendar access requires Exchange 2016 CU3+ on-premises deployed with Exchange hybrid established:</span></span><br /><span data-ttu-id="1a474-215">
<a href="https://docs.microsoft.com/exchange/hybrid-deployment/deploy-hybrid">Créer un déploiement hybride à l’aide de l’Assistant Configuration hybride</a></span><span class="sxs-lookup"><span data-stu-id="1a474-215">
<a href="https://docs.microsoft.com/exchange/hybrid-deployment/deploy-hybrid">Create a hybrid deployment with the Hybrid Configuration wizard</a></span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="1a474-216">Fonctions d’appel</span><span class="sxs-lookup"><span data-stu-id="1a474-216">Calling Features</span></span><br />
<span data-ttu-id="1a474-217">VoIP/PSTN dans teams</span><span class="sxs-lookup"><span data-stu-id="1a474-217">VoIP / PSTN in Teams</span></span></td>
<td><p><span data-ttu-id="1a474-218">Le VoIP est disponible en interne sur le client</span><span class="sxs-lookup"><span data-stu-id="1a474-218">VoIP internally to the tenant is available</span></span></p>
<p><span data-ttu-id="1a474-219">Les services RTC ou de plan d’appel ne sont pas disponibles tant que l’utilisateur n’a pas été déplacé vers l’interface uniquement</span><span class="sxs-lookup"><span data-stu-id="1a474-219">PSTN or Calling Plan services are not available until the user is moved to Teams Only experience</span></span></p></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="1a474-220">Collaborer sur équipes et canaux dans teams</span><span class="sxs-lookup"><span data-stu-id="1a474-220">Teams and Channels collaboration in Teams</span></span></td>
<td><p><span data-ttu-id="1a474-221">Pour une utilisation complète, y compris les fonctionnalités de conformité, une licence SharePoint Online doit être attribuée à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="1a474-221">For full experience, including compliance features, a SharePoint Online license need to be assigned to the user.</span></span></p>
<p><span data-ttu-id="1a474-222">La migration de sites SharePoint locaux existants n’est pas requise.</span><span class="sxs-lookup"><span data-stu-id="1a474-222">Migration of existing on-premises SharePoint sites is not required.</span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="1a474-223">OneDrive entreprise (partage de fichiers P2P)</span><span class="sxs-lookup"><span data-stu-id="1a474-223">OneDrive for Business (P2P file sharing)</span></span></td>
<td><span data-ttu-id="1a474-224">OneDrive entreprise nécessite l’attribution d’une licence SharePoint Online à un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="1a474-224">OneDrive for Business requires a user to have a SharePoint Online license assigned.</span></span> <span data-ttu-id="1a474-225">Sans ce partage de fichier de licence par poste à homologue, vous ne serez pas possible.</span><span class="sxs-lookup"><span data-stu-id="1a474-225">Without this license per-to-peer file sharing will not be possible.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="1a474-226">Plateforme d’application</span><span class="sxs-lookup"><span data-stu-id="1a474-226">Application platform</span></span></td>
<td><span data-ttu-id="1a474-227">Les utilisateurs pourront utiliser les applications qui sont conçues pour eux conformément aux politiques de votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="1a474-227">Users will be able to use the apps that are designated available for them according to your company policies.</span></span><br />
<span data-ttu-id="1a474-228">Pour en savoir plus <a href="https://docs.microsoft.com/microsoftteams/admin-settings">, voir paramètres d’administration des applications dans Microsoft teams</a> .</span><span class="sxs-lookup"><span data-stu-id="1a474-228">Learn more here: <a href="https://docs.microsoft.com/microsoftteams/admin-settings">Admin settings for apps in Teams</a></span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="1a474-229">Fonctionnalités de sécurité et de conformité</span><span class="sxs-lookup"><span data-stu-id="1a474-229">Security and Compliance features</span></span></td>
<td><ul>
<li><p><span data-ttu-id="1a474-230">Des stratégies de rétention sont disponibles</span><span class="sxs-lookup"><span data-stu-id="1a474-230">Retention policies are available</span></span></p></li>
<li><p><span data-ttu-id="1a474-231">la découverte électronique et les conservations juridiques pour la conformité aux messages de canal sont prises en charge</span><span class="sxs-lookup"><span data-stu-id="1a474-231">eDiscovery and Legal Hold for compliance on channel messages is supported</span></span></p></li>
<li><p><span data-ttu-id="1a474-232">Les stratégies de protection contre la perte de données (DLP) sont disponibles</span><span class="sxs-lookup"><span data-stu-id="1a474-232">Data Loss Prevention policies (DLP) are available</span></span></p></li>
</ul>
<p><span data-ttu-id="1a474-233">Ensemble des fonctionnalités disponibles avec Exchange Online, Exchange sur site prend en charge la plupart de ces fonctionnalités, reportez-vous à</span><span class="sxs-lookup"><span data-stu-id="1a474-233">Full feature set available with Exchange Online, Exchange on-premises supports most of these features, see</span></span></p>
<p><span data-ttu-id="1a474-234"><a href="https://docs.microsoft.com/MicrosoftTeams/exchange-teams-interact">Interaction entre Exchange et Microsoft Teams</a></span><span class="sxs-lookup"><span data-stu-id="1a474-234"><a href="https://docs.microsoft.com/MicrosoftTeams/exchange-teams-interact">How Exchange and Teams interact</a></span></span></p>
<ul>
<li><p><span data-ttu-id="1a474-235">pour la liste complète</span><span class="sxs-lookup"><span data-stu-id="1a474-235">for full list</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-with-skype-for-business-server"></a><span data-ttu-id="1a474-236">Étapes d’activation pour les organisations avec Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="1a474-236">Enablement steps for organizations with Skype for Business Server</span></span>  

1.  <span data-ttu-id="1a474-237">Répondez aux conditions préalables décrites dans la section début here ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="1a474-237">Meet pre-requisites detailed in the Start Here section above.</span></span>

2.  <span data-ttu-id="1a474-238">Changer de locataire en mode îlots (pour les clients approvisionnés après 9/1/2019, veuillez contacter le support technique pour apporter cette modification)</span><span class="sxs-lookup"><span data-stu-id="1a474-238">Switch tenant into Islands mode (for tenants provisioned AFTER 9/1/2019, please contact support to make this change)</span></span>  
    [<span data-ttu-id="1a474-239">Configuration de vos paramètres de coexistence et de mise à niveau</span><span class="sxs-lookup"><span data-stu-id="1a474-239">Setting your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)

3.  <span data-ttu-id="1a474-240">Configurer votre client conformément aux politiques de votre entreprise</span><span class="sxs-lookup"><span data-stu-id="1a474-240">Configure your tenant in accordance with your company's business/company policies</span></span>  
    [<span data-ttu-id="1a474-241">Gérer les paramètres de Microsoft Teams pour votre organisation</span><span class="sxs-lookup"><span data-stu-id="1a474-241">Manage Microsoft Teams settings for your organization</span></span>](enable-features-office-365.md)

4.  <span data-ttu-id="1a474-242">Déployer le client teams</span><span class="sxs-lookup"><span data-stu-id="1a474-242">Deploy the Teams client</span></span>  
    [<span data-ttu-id="1a474-243">Obtenir des clients pour Teams</span><span class="sxs-lookup"><span data-stu-id="1a474-243">Get clients for Teams</span></span>](get-clients.md)

5.   <span data-ttu-id="1a474-244">Piloter votre programme d’adoption</span><span class="sxs-lookup"><span data-stu-id="1a474-244">Drive your adoption program</span></span>  
    [<span data-ttu-id="1a474-245">Adopter Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1a474-245">Adopt Microsoft Teams</span></span>](adopt-microsoft-teams-landing-page.md)<br/>
    [<span data-ttu-id="1a474-246">Liste de contrôle de démarrage rapide pour l’adoption de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1a474-246">Microsoft Teams adoption quick start checklist</span></span>](teams-adoption-quick-start-checklist.md)

6.  <span data-ttu-id="1a474-247">Commencer à planifier déplacer d’autres charges de travail vers Microsoft 365 ou Office 365</span><span class="sxs-lookup"><span data-stu-id="1a474-247">Begin planning moving other workloads to Microsoft 365 or Office 365</span></span>

7.  <span data-ttu-id="1a474-248">Établissement de Skype entreprise hybride et suivi des chemins de mise à niveau recommandés pour les serveurs Skype entreprise et Lync</span><span class="sxs-lookup"><span data-stu-id="1a474-248">Establish Skype for Business hybrid and follow the recommended upgrade paths for Skype for Business and Lync servers</span></span>  
    [<span data-ttu-id="1a474-249">Mise à niveau de Skype entreprise local vers teams</span><span class="sxs-lookup"><span data-stu-id="1a474-249">Upgrade from Skype for Business on-premises to Teams</span></span>](upgrade-to-teams-execute-skypeforbusinesshybridonprem.md)

## <a name="closing-statement"></a><span data-ttu-id="1a474-250">Instruction de fermeture</span><span class="sxs-lookup"><span data-stu-id="1a474-250">Closing statement</span></span>

<span data-ttu-id="1a474-251">Microsoft teams permet à votre organisation de mettre en place tous les employés, travailleurs de l’information et personnes terrain sur une seule plate-forme.</span><span class="sxs-lookup"><span data-stu-id="1a474-251">Microsoft Teams can be an enabler for your organization to bring all the employees, information workers and Firstline workers, together on a single platform.</span></span> <span data-ttu-id="1a474-252">Vous pouvez [commencer](https://products.office.com/microsoft-teams/group-chat-software) dès aujourd’hui.</span><span class="sxs-lookup"><span data-stu-id="1a474-252">You can [get started](https://products.office.com/microsoft-teams/group-chat-software) today.</span></span> <span data-ttu-id="1a474-253">Vous pouvez garder le suivi de toutes les dernières annonces et des mises à jour mensuelles de nos [produits.](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/bg-p/MicrosoftTeamsBlog)</span><span class="sxs-lookup"><span data-stu-id="1a474-253">You can keep in touch with all our latest announcements and monthly product updates [here](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/bg-p/MicrosoftTeamsBlog).</span></span>

<span data-ttu-id="1a474-254">Par ailleurs, en tant qu’entreprises dans le monde de la gestion de la situation actuelle COVID-19, nous avons créé une série de contenus qui vous aideront à utiliser les équipes pour un impact maximal sur votre organisation.</span><span class="sxs-lookup"><span data-stu-id="1a474-254">Additionally, as companies around the world are managing the current COVID-19 situation, we have created a series of content that will help you utilize Teams for the maximum impact in your organization.</span></span>

  - <span data-ttu-id="1a474-255">Notre [engagement pour les clients pendant COVID-19](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/05/our-commitment-to-customers-during-covid-19/)</span><span class="sxs-lookup"><span data-stu-id="1a474-255">Our [commitment to customers during COVID-19](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/05/our-commitment-to-customers-during-covid-19/)</span></span>

  - [<span data-ttu-id="1a474-256">2 semaines dans : ce que nous avons appris sur le fonctionnement distant</span><span class="sxs-lookup"><span data-stu-id="1a474-256">2 weeks in: what we've learned about remote work</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/18/making-the-switch-to-remote-work-5-things-weve-learned/)

  - [<span data-ttu-id="1a474-257">Diffuser des réunions et des événements en ligne</span><span class="sxs-lookup"><span data-stu-id="1a474-257">Delivering online meetings and events</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/delivering-online-meetings-events/)

  - [<span data-ttu-id="1a474-258">Aider les petites et moyennes entreprises à travailler à distance avec Teams</span><span class="sxs-lookup"><span data-stu-id="1a474-258">Helping small and medium-sized businesses work remotely with Teams</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/helping-smb-customers-work-remotely-microsoft-teams/)

  - [<span data-ttu-id="1a474-259">Transformation numérique des événements en direct : les observations de Bob Bejan de la Frontline</span><span class="sxs-lookup"><span data-stu-id="1a474-259">Digital transformation of live events: Bob Bejan's observations from the frontline</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/13/digital-transformation-live-events-bob-bejans-observations-frontline/)

  - [<span data-ttu-id="1a474-260">Les 9 principaux moyens que Microsoft IT utilise pour activer le travail à distance de ses employés</span><span class="sxs-lookup"><span data-stu-id="1a474-260">The top 9 ways Microsoft IT is enabling remote work for its employees</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/top-9-ways-microsoft-it-enabling-remote-work-employees/)

  - [<span data-ttu-id="1a474-261">Travaillez à distance, restez sécurisé ; conseils pour CISOs</span><span class="sxs-lookup"><span data-stu-id="1a474-261">Work remotely, stay secure—tips for CISOs</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/work-remotely-stay-secure-ciso-tips/)

  - [<span data-ttu-id="1a474-262">Aider les enseignants et les étudiants à effectuer la transition vers une formation à distance</span><span class="sxs-lookup"><span data-stu-id="1a474-262">Helping teachers and students make the switch to remote learning</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/11/helping-teachers-students-switch-remote-learning/)

  - [<span data-ttu-id="1a474-263">Rester productif lorsque vous travaillez à distance à l’aide de Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="1a474-263">Staying productive while working remotely with Microsoft Teams</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/10/staying-productive-while-working-remotely-with-microsoft-teams/)

## <a name="support-services-reference"></a><span data-ttu-id="1a474-264">Support technique services</span><span class="sxs-lookup"><span data-stu-id="1a474-264">Support Services reference</span></span>

<span data-ttu-id="1a474-265">Teams repose sur les groupes Exchange Online, SharePoint Online, OneDrive entreprise et Microsoft 365 pour fournir aux utilisateurs une connaissance complète de Microsoft 365 ou d’Office 365.</span><span class="sxs-lookup"><span data-stu-id="1a474-265">Teams relies on Exchange Online, SharePoint Online, OneDrive for Business and Microsoft 365 Groups to provide your users with a fully integrated Microsoft 365 or Office 365 experience.</span></span> <span data-ttu-id="1a474-266">Comme indiqué plus haut, teams fonctionne sans le déploiement complet de ces services, avec des fonctionnalités limitées.</span><span class="sxs-lookup"><span data-stu-id="1a474-266">As noted above, Teams will work without full deploying these services – with limited capabilities.</span></span> <span data-ttu-id="1a474-267">Pour en savoir plus sur les équipes et ses conditions préalables, consultez la [page Bienvenue dans teams](teams-overview.md).</span><span class="sxs-lookup"><span data-stu-id="1a474-267">You can read more about Teams and its pre-requisites here: [Welcome to Teams](teams-overview.md).</span></span>

<span data-ttu-id="1a474-268">Pour des détails spécifiques sur chacun des services indiqués ci-dessus, suivez les liens ci-dessous :</span><span class="sxs-lookup"><span data-stu-id="1a474-268">For specifics on each of the services listed above, please follow the links below:</span></span>

  - <span data-ttu-id="1a474-269">Exchange Online est utilisé pour les fonctionnalités de calendrier et le stockage des messages d’égal à égal dans Teams.</span><span class="sxs-lookup"><span data-stu-id="1a474-269">Exchange Online is used for calendaring features and storing peer to peer messages in Teams.</span></span> <span data-ttu-id="1a474-270">Pour en savoir plus, voir [Comment Exchange et teams interagissent](exchange-teams-interact.md)</span><span class="sxs-lookup"><span data-stu-id="1a474-270">To learn more, read [How Exchange and Teams interact](exchange-teams-interact.md)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1a474-271">Pour une interopérabilité entre les équipes avec Exchange en local, vous devez configurer le nouveau protocole d’authentification OAuth Exchange comme décrit dans [configurer l’authentification OAuth entre les organisations Exchange et Exchange Online](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help).</span><span class="sxs-lookup"><span data-stu-id="1a474-271">For Teams interop with Exchange on-premises, you must configure the new Exchange OAuth authentication protocol as described in [Configure OAuth authentication between Exchange and Exchange Online organizations](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help).</span></span>

  - <span data-ttu-id="1a474-272">SharePoint est utilisé pour le partage de fichiers dans les canaux, tandis que/OneDrive entreprise est utilisé pour le partage de fichiers dans 1:1 ou la discussion de groupe.</span><span class="sxs-lookup"><span data-stu-id="1a474-272">SharePoint is used for file sharing in channels, while /OneDrive for Business is used for file sharing in 1:1 or group chat.</span></span> <span data-ttu-id="1a474-273">Pour en savoir plus, voir [comment SharePoint Online et OneDrive entreprise interagissent avec Microsoft teams](sharepoint-onedrive-interact.md).</span><span class="sxs-lookup"><span data-stu-id="1a474-273">To learn more, read [How SharePoint Online and OneDrive for Business interact with Microsoft Teams](sharepoint-onedrive-interact.md).</span></span>

  - <span data-ttu-id="1a474-274">Les [groupes Microsoft 365](office-365-groups.md) sont utilisés pour la création et la gestion d’équipes et de canaux.</span><span class="sxs-lookup"><span data-stu-id="1a474-274">[Microsoft 365 Groups](office-365-groups.md) are used for team and channel creation/management.</span></span>


## <a name="related-topics"></a><span data-ttu-id="1a474-275">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="1a474-275">Related topics</span></span>

[<span data-ttu-id="1a474-276">Illustrations architecture IT Microsoft Teams et solutions téléphonie</span><span class="sxs-lookup"><span data-stu-id="1a474-276">Microsoft Teams IT architecture and telephony solutions posters</span></span>](teams-architecture-solutions-posters.md#teams-as-part-of-microsoft-365)

[<span data-ttu-id="1a474-277">Planifier la connectivité hybride entre Skype Entreprise Server et Office 365</span><span class="sxs-lookup"><span data-stu-id="1a474-277">Plan hybrid connectivity between Skype for Business Server and Office 365</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-hybrid-connectivity)

[<span data-ttu-id="1a474-278">Prendre en charge les travailleurs distants avec teams</span><span class="sxs-lookup"><span data-stu-id="1a474-278">Support remote workers using Teams</span></span>](support-remote-work-with-teams.md)

[<span data-ttu-id="1a474-279">Travailler à distance avec Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="1a474-279">Work remotely with Microsoft 365</span></span>](https://aka.ms/remote-work)
