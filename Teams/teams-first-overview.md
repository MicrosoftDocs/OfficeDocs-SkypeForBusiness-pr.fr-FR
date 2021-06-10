---
title: Déployer et Microsoft Teams d’abord
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
description: Utilisez ces instructions pour déployer votre Microsoft Teams charge de travail Microsoft 365 votre Office 365 travail.
ROBOTS: NOINDEX, NOFOLLOW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 81ecf9a0f963a1be577149c585424c140df2abd5
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119353"
---
# <a name="roll-out-microsoft-teams-first"></a><span data-ttu-id="bfd17-103">Déployer et Microsoft Teams d’abord</span><span class="sxs-lookup"><span data-stu-id="bfd17-103">Roll out Microsoft Teams First</span></span>

<span data-ttu-id="bfd17-104">Microsoft Teams peuvent aider vos employés à rester en contact et à collaborer, en particulier au moment du moment où le travail à distance est une réalité d’employés dans le monde entier.</span><span class="sxs-lookup"><span data-stu-id="bfd17-104">Microsoft Teams can help your employees stay connected and collaborate with each other, especially in the current unprecedented time where remote work is a reality of employees around the world.</span></span> <span data-ttu-id="bfd17-105">La possibilité de discuter, d’utiliser des réunions vidéo et de collaborer sur Office documents au sein de Teams peut aider les entreprises à rester productives.</span><span class="sxs-lookup"><span data-stu-id="bfd17-105">Being able to chat, do video meetings and collaborate on Office documents within Teams can help companies stay productive.</span></span> <span data-ttu-id="bfd17-106">Qu’il s’agit d’une petite entreprise, d’une association ou d’une grande organisation, vous pouvez commencer à utiliser Teams comme première charge de travail au sein de la suite Microsoft 365 ou Office 365 avant de déployer un autre application Office ou service.</span><span class="sxs-lookup"><span data-stu-id="bfd17-106">Whether you are a small business, a non-profit or a large organization, you can get started with Teams as the first workload within Microsoft 365 or Office 365 suite before deploying any other Office app or service.</span></span>

<span data-ttu-id="bfd17-107">Cet article détaille les considérations que vous devez prendre en considération avec l’approche « Teams première ».</span><span class="sxs-lookup"><span data-stu-id="bfd17-107">This article details the considerations you must make with the "Teams First" approach.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bfd17-108">Bien Teams pouvez être la première charge de travail déployée dans le cloud au niveau de votre organisation, le déploiement d’Teams devrait faire partie de votre stratégie de déploiement globale dans le cloud.</span><span class="sxs-lookup"><span data-stu-id="bfd17-108">While Teams can be your organization's first cloud deployed workload, deploying Teams should be part of your overall cloud deployment strategy.</span></span>

<span data-ttu-id="bfd17-109">Si vous avez déjà déployé d’autres services Microsoft 365 ou Office 365 et Teams est votre prochaine charge de travail à déployer (au lieu de la première), commencez par découvrir comment déployer [Teams.](./deploy-overview.md)</span><span class="sxs-lookup"><span data-stu-id="bfd17-109">If you have already rolled out other Microsoft 365 or Office 365 services and Teams is your next workload to roll out (instead of the first), start with [How to roll out Teams](./deploy-overview.md).</span></span>

## <a name="start-here"></a><span data-ttu-id="bfd17-110">Démarrez ici</span><span class="sxs-lookup"><span data-stu-id="bfd17-110">Start here</span></span>

<span data-ttu-id="bfd17-111">Pour commencer à travailler avec votre Teams premier déploiement, vous devez répondre à au moins quelques conditions préalables.</span><span class="sxs-lookup"><span data-stu-id="bfd17-111">To get started with your Teams First deployment you will need to meet at minimum some pre-requisites.</span></span> <span data-ttu-id="bfd17-112">La liste suivante indique ce que vous devez mettre en place pour votre organisation pour Teams’être activée :</span><span class="sxs-lookup"><span data-stu-id="bfd17-112">The following list will show what you must have in place for your organization before Teams can be enabled:</span></span>

1.  <span data-ttu-id="bfd17-113">Organisation Microsoft 365 ou Office 365 configurée avec votre nom de domaine</span><span class="sxs-lookup"><span data-stu-id="bfd17-113">A Microsoft 365 or Office 365 organization configured with your domain name</span></span>

2.  <span data-ttu-id="bfd17-114">Azure Active Directory connectivité (connexion AAD) ou solution de synchronisation d’identité de cloud similaire, avec tous les attributs requis synchronisés avec votre client</span><span class="sxs-lookup"><span data-stu-id="bfd17-114">Azure Active Directory connectivity (AAD connect) or similar cloud identity sync solution – with all required attributes synched with your tenant</span></span>  
    <span data-ttu-id="bfd17-115">Pour comprendre les attributs synchronisés avec la synchronisation AAD, lisez [Azure AD Connecter synchronisation : Attributs synchronisés avec](/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized) les Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="bfd17-115">To understand the attributes synchronized with AAD sync, read [Azure AD Connect sync: Attributes synchronized to Azure Active Directory](/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)</span></span>

3.  <span data-ttu-id="bfd17-116">Licences utilisateur appropriées affectées à Teams</span><span class="sxs-lookup"><span data-stu-id="bfd17-116">Appropriate user licenses assigned for Teams</span></span>  
    <span data-ttu-id="bfd17-117">Pour comprendre Teams de licences, lisez Microsoft Teams [description du service.](/office365/servicedescriptions/teams-service-description)</span><span class="sxs-lookup"><span data-stu-id="bfd17-117">To understand Teams licensing, read [Microsoft Teams service description](/office365/servicedescriptions/teams-service-description).</span></span>

4.  <span data-ttu-id="bfd17-118">Le réseau de l’organisation est préparé pour l’Teams</span><span class="sxs-lookup"><span data-stu-id="bfd17-118">Organization's network prepared for Teams</span></span>  
    <span data-ttu-id="bfd17-119">Pour comprendre la préparation du réseau, lisez Préparer le réseau [de votre organisation pour l’Teams.](prepare-network.md)</span><span class="sxs-lookup"><span data-stu-id="bfd17-119">To understand network preparation, read [Prepare your organization's network for Teams](prepare-network.md).</span></span>

5.  <span data-ttu-id="bfd17-120">Autoriser l’accès réseau à Exchange, Sharepoint et OneDrive Entreprise dans Microsoft 365 ou Office 365 : Office 365 [URL et plages d’adresses IP.](/office365/enterprise/urls-and-ip-address-ranges)</span><span class="sxs-lookup"><span data-stu-id="bfd17-120">Allow network access to Exchange, Sharepoint, and OneDrive for Business in Microsoft 365 or Office 365: [Office 365 URLs and IP address ranges](/office365/enterprise/urls-and-ip-address-ranges).</span></span>

> [!NOTE]
> <span data-ttu-id="bfd17-121">Les locataires créés après le 1er septembre 2019 sont Teams mode d’accès uniquement.</span><span class="sxs-lookup"><span data-stu-id="bfd17-121">Tenants created after September 1, 2019 are provisioned in Teams Only mode.</span></span>
> 
> [!IMPORTANT]
> <span data-ttu-id="bfd17-122">Si vous avez Skype Entreprise Server et que votre client a été mis en service après le 1er septembre 2019, contactez le support technique pour activer les fonctionnalités de coexistence pour Teams.</span><span class="sxs-lookup"><span data-stu-id="bfd17-122">If you have Skype for Business Server deployed, and your tenant was provisioned AFTER September 1, 2019, please contact support to enable coexistence capabilities for Teams.</span></span> <span data-ttu-id="bfd17-123">Assurez-vous que votre « stratégie de mise <span class="underline"></span> à niveau à l’échelle de l’organisation » est définie sur « mode Île » avant d’attribuer Teams licences à un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="bfd17-123">Make sure your 'Organization wide upgrade policy' is set to 'Island mode' <span class="underline">before</span> you assign any Teams licenses to a user.</span></span>

## <a name="migration-starting-points"></a><span data-ttu-id="bfd17-124">Points de départ de la migration</span><span class="sxs-lookup"><span data-stu-id="bfd17-124">Migration Starting points</span></span>

<span data-ttu-id="bfd17-125">Votre chemin vers Microsoft 365 ou Office 365 fonctionnalités disponibles dans Teams en fonction de votre point de départ et de l’existence d’un serveur Skype Entreprise ou Lync local.</span><span class="sxs-lookup"><span data-stu-id="bfd17-125">Your journey to Microsoft 365 or Office 365 and features available in Teams depending on your starting point and the existence of on premises Skype for Business or Lync server.</span></span> <span data-ttu-id="bfd17-126">Les sections suivantes duivent les fonctionnalités de base et les options de configuration, en plus des conditions préalables ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="bfd17-126">The following sections will detail basic capabilities and configuration options in addition to the pre-requisites above.</span></span> <span data-ttu-id="bfd17-127">Nous avons décomposé les scénarios de point de départ des rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="bfd17-127">We have broken down the starting point scenarios to the following topics:</span></span>

<span data-ttu-id="bfd17-128">**Configuration Teams** client : les modes utilisateur et client sont utilisés pour contrôler le comportement du destinataire.</span><span class="sxs-lookup"><span data-stu-id="bfd17-128">**Tenant Teams Configuration**: Tenant and user modes are used to control the recipient's behavior.</span></span> <span data-ttu-id="bfd17-129">Ces paramètres peuvent être affectés au niveau du client ou de l’utilisateur dans une organisation.</span><span class="sxs-lookup"><span data-stu-id="bfd17-129">These settings can be assigned on the tenant level or the user level in an organization.</span></span> <span data-ttu-id="bfd17-130">Pour en savoir plus, lisez [Coexistence avec Skype Entreprise.](coexistence-chat-calls-presence.md)</span><span class="sxs-lookup"><span data-stu-id="bfd17-130">To learn more, read [Coexistence with Skype for Business](coexistence-chat-calls-presence.md).</span></span>

<span data-ttu-id="bfd17-131">**Conversation / Communication externe dans Teams**: les services de conversation font référence à des conversations d’égal à égal ou de groupe au sein et à l’organisation, ou externes à l’organisation.</span><span class="sxs-lookup"><span data-stu-id="bfd17-131">**Chat / External communication in Teams**: Chat services refer to peer to peer or group chat conversations within and organization or externally to the organization.</span></span> <span data-ttu-id="bfd17-132">La communication externe est également appelée fédération dans Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="bfd17-132">External communication is also referred to as federation in Skype for Business.</span></span>

<span data-ttu-id="bfd17-133">Créer et afficher des réunions dans Teams : un utilisateur peut toujours créer des réunions en ligne via le composant logiciel Outlook Teams et que la connexion RSTN est disponible dans tous les **scénarios** une fois l’utilisateur titulaire d’une licence.</span><span class="sxs-lookup"><span data-stu-id="bfd17-133">**Create and view meetings in Teams**: A user can always create online meetings via the Outlook Teams add-in and PSTN dial-in is available in all scenarios once the user is licensed.</span></span> <span data-ttu-id="bfd17-134">Teams et Skype Entreprise d’informations de calendrier dans la boîte aux lettres de l’Exchange utilisateur.</span><span class="sxs-lookup"><span data-stu-id="bfd17-134">Teams and Skype for Business store calendaring information in the user's Exchange mailbox.</span></span> <span data-ttu-id="bfd17-135">Sur un serveur Exchange doit être Exchange Server 2016 CU3 ou une interface supérieure pour que le client Teams puisse interagir avec la boîte aux lettres de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="bfd17-135">On premises Exchange server must be Exchange Server 2016 CU3 or above for the Teams client to be able to interact with the user's mailbox.</span></span> <span data-ttu-id="bfd17-136">Sans Exchange boîte aux lettres, l’icône Calendrier de Teams ne s’affiche pas et les utilisateurs ne pourront pas afficher, créer ou modifier des réunions dans le client Teams.</span><span class="sxs-lookup"><span data-stu-id="bfd17-136">Without Exchange mailbox access the Calendar icon in Teams will not appear and they user will not be able to view, create or modify meetings in the Teams client.</span></span>

<span data-ttu-id="bfd17-137">**Fonctionnalités d’appel VoIP/PSTN** dans Teams : l’appel peut être de voix sur IP (VoIP) ou de réseau téléphonique commuté (PSTN).</span><span class="sxs-lookup"><span data-stu-id="bfd17-137">**Calling features VoIP / PSTN in Teams**: Calling can be Voice over IP (VoIP) or Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="bfd17-138">La connectivité VoIP se produit en natif entre Teams clients, tandis qu’une connectivité RSTN se produit lorsqu’un utilisateur compose un numéro de téléphone extérieur.</span><span class="sxs-lookup"><span data-stu-id="bfd17-138">VoIP connectivity happens natively between Teams clients, while PSTN connectivity happen when a user dials an outside phone number.</span></span>  

<span data-ttu-id="bfd17-139">Teams deux types de connectivité PSTN.</span><span class="sxs-lookup"><span data-stu-id="bfd17-139">Teams support two types of PSTN connectivity.</span></span> <span data-ttu-id="bfd17-140">Microsoft Calling Plan, lorsque Microsoft fournit une infrastructure téléphonique comprenant le numéro de téléphone d’un utilisateur, ou une configuration de routage direct, où le client fournit la connectivité téléphonique sur un contrôleur de session border controller (SBC) pour l’Teams utilisateur.</span><span class="sxs-lookup"><span data-stu-id="bfd17-140">Microsoft Calling Plan, when Microsoft provides telephony infrastructure including the phone number for a user, or Direct Routing configuration, where the customer provides the telephony connectivity over a Session Border Controller (SBC) for the Teams user.</span></span>  
<span data-ttu-id="bfd17-141">Pour en savoir plus, [lisez quel plan d’appels](calling-plan-landing-page.md) vous est le mieux [? Système téléphonique routage direct.](direct-routing-landing-page.md)</span><span class="sxs-lookup"><span data-stu-id="bfd17-141">To learn more, read [Which Calling Plan is right for you?](calling-plan-landing-page.md) and [Phone System Direct Routing](direct-routing-landing-page.md).</span></span>

<span data-ttu-id="bfd17-142">**Teams la collaboration** dans les canaux Teams : dans Teams, les équipes sont des groupes de personnes rassemblées pour du travail, des projets ou des intérêts communs.</span><span class="sxs-lookup"><span data-stu-id="bfd17-142">**Teams and Channels collaboration in Teams**: In Teams, teams are groups of people brought together for work, projects, or common interests.</span></span> <span data-ttu-id="bfd17-143">Teams sont composés de canaux.</span><span class="sxs-lookup"><span data-stu-id="bfd17-143">Teams are made up of channels.</span></span> <span data-ttu-id="bfd17-144">Chaque canal est créé autour d’un sujet( par exemple, « Événements d’équipe », d’un nom de service ou tout simplement pour le plaisir).</span><span class="sxs-lookup"><span data-stu-id="bfd17-144">Each channel is built around a topic, like "Team Events," a department name, or just for fun.</span></span> <span data-ttu-id="bfd17-145">Les canaux sont l’endroit où vous organisez des réunions, organisez des conversations et travaillez ensemble sur des fichiers.</span><span class="sxs-lookup"><span data-stu-id="bfd17-145">Channels are where you hold meetings, have conversations, and work on files together.</span></span> <span data-ttu-id="bfd17-146">Pendant la collaboration</span><span class="sxs-lookup"><span data-stu-id="bfd17-146">During collaboration</span></span>

<span data-ttu-id="bfd17-147">OneDrive Entreprise (partage de fichiers **P2P)** dans Teams : en dehors de Teams et de canaux, les utilisateurs de Teams peuvent partager des fichiers d’égal à égal à l’aide d’OneDrive entreprise ou d’autres programmes de partage de fichiers P2P tels que Citrix Files, Dropbox, Box et Google Drive.</span><span class="sxs-lookup"><span data-stu-id="bfd17-147">**OneDrive for Business (P2P file sharing) in Teams**: Outside of Teams and Channels, Teams users can share files peer-to-peer using OneDrive for business or other P2P sharing file programs such as Citrix Files, DropBox, Box and Google Drive.</span></span> <span data-ttu-id="bfd17-148">Pour OneDrive entreprise, un utilisateur doit avoir une licence SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="bfd17-148">For OneDrive for business a user must have SharePoint Online license assigned.</span></span>

<span data-ttu-id="bfd17-149">**Plateforme d’application**: les applications offrent à votre organisation des outils pré-pratiques pour vous aider à mieux Teams.</span><span class="sxs-lookup"><span data-stu-id="bfd17-149">**Application Platform**: Apps provide out-of-the-box tools for your organization to get more out of Teams.</span></span> <span data-ttu-id="bfd17-150">Ces applications combinent les fonctionnalités des onglets, des extensions de messagerie, des connecteurs et des bots fournis par Microsoft, par un tiers ou par des développeurs de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="bfd17-150">These apps combine the functionality of tabs, messaging extensions, connectors, and bots provided by Microsoft, built by a third-party, or by developers in your organization.</span></span>

<span data-ttu-id="bfd17-151">Fonctionnalités de sécurité et de conformité : **Teams** dispose d’un vaste éventail d’informations pour vous aider dans les domaines de conformité, notamment les stratégies de rétention, la protection contre la perte de données, la découverte électronique et la conservation légale des canaux, des conversations et des fichiers, et la recherche dans le journal d’audit.</span><span class="sxs-lookup"><span data-stu-id="bfd17-151">**Security and Compliance features:** Teams has a wide range of information to help you with compliance areas, including retention policies, Data Loss Protection (DLP), eDiscovery and legal hold for channels, chats and files, audit log search.</span></span> <span data-ttu-id="bfd17-152">Pour en savoir plus, [lisez Sécurité et conformité dans Microsoft Teams.](security-compliance-overview.md)</span><span class="sxs-lookup"><span data-stu-id="bfd17-152">To learn more, read [Security and compliance in Microsoft Teams](security-compliance-overview.md).</span></span>  

> [!NOTE]
> <span data-ttu-id="bfd17-153">Les fonctionnalités de découverte électronique avancée nécessitent une licence E5.</span><span class="sxs-lookup"><span data-stu-id="bfd17-153">Advance eDiscovery features require E5 licensing.</span></span>

<span data-ttu-id="bfd17-154">[Comparer les options de licence.](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)</span><span class="sxs-lookup"><span data-stu-id="bfd17-154">[Compare licensing options](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans).</span></span>

<span data-ttu-id="bfd17-155">Découvrez [comment les Exchange et les Microsoft Teams](exchange-teams-interact.md) d’interagir pour découvrir les fonctionnalités de conformité disponibles dans votre scénario.</span><span class="sxs-lookup"><span data-stu-id="bfd17-155">Read [How Exchange and Microsoft Teams interact](exchange-teams-interact.md) to learn which compliance features are available in your scenario.</span></span>

## <a name="organizations-span-classunderlinewithoutspan-skype-for-business-or-lync-server"></a><span data-ttu-id="bfd17-156">Organisations **<span class="underline">sans</span>** Skype Entreprise ou Lync Server</span><span class="sxs-lookup"><span data-stu-id="bfd17-156">Organizations **<span class="underline">without</span>** Skype for Business or Lync Server</span></span>

<span data-ttu-id="bfd17-157">Ce point de départ suppose que votre organisation n’utilise pas Skype Entreprise ou Lync Server actuellement et Teams sera votre première application dans Microsoft 365 ou Office 365.</span><span class="sxs-lookup"><span data-stu-id="bfd17-157">This starting point assumes that your organization does not utilize Skype for Business or Lync Server currently and Teams will be your first application in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="bfd17-158">Le tableau suivant détaille la configuration de haut niveau et les capacités des utilisateurs finaux pour Teams services principaux.</span><span class="sxs-lookup"><span data-stu-id="bfd17-158">The following table details high level configuration and end user capabilities for Teams for core services.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="bfd17-159">Élément</span><span class="sxs-lookup"><span data-stu-id="bfd17-159">Item</span></span></th>
<th><span data-ttu-id="bfd17-160">Remarques</span><span class="sxs-lookup"><span data-stu-id="bfd17-160">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="bfd17-161">Configuration Teams client</span><span class="sxs-lookup"><span data-stu-id="bfd17-161">Tenant Teams configuration</span></span></td>
<td><span data-ttu-id="bfd17-162">Teams Seul le mode, toutes les fonctionnalités de conversation et d’appel sont Teams uniquement.</span><span class="sxs-lookup"><span data-stu-id="bfd17-162">Teams Only mode, all chat and calling features are in Teams Only.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="bfd17-163">Conversation / Communication externe dans Teams</span><span class="sxs-lookup"><span data-stu-id="bfd17-163">Chat / External Communication in Teams</span></span></td>
<td><p><span data-ttu-id="bfd17-164">Communication interne (intra Microsoft 365 ou Office 365) et communication de conversation externe à partir d’Teams.</span><span class="sxs-lookup"><span data-stu-id="bfd17-164">Internal (intra Microsoft 365 or Office 365 organization) and external chat communication possible from Teams.</span></span></p>
<p><span data-ttu-id="bfd17-165"><em>Remarque : les entrées DNS doivent être configurées pour l’accès externe.</span><span class="sxs-lookup"><span data-stu-id="bfd17-165"><em>Note: DNS entries must be configured for external access.</span></span> <span data-ttu-id="bfd17-166">Skype Entreprise Les enregistrements DNS sont nécessaires même si vous n’avez pas Skype Entreprise en local, ou dans Microsoft 365 ou Office 365, pour autoriser la fédération avec les environnements Lync et Skype Entreprise :</span><span class="sxs-lookup"><span data-stu-id="bfd17-166">Skype for Business DNS records are needed even though you don't have Skype for Business on-premises, or in Microsoft 365 or Office 365, to allow federation with Lync and Skype for Business environments:</span></span><br /><span data-ttu-id="bfd17-167">
<a href="/office365/enterprise/external-domain-name-system-records">Enregistrements système de noms de domaine externes</a></em></span><span class="sxs-lookup"><span data-stu-id="bfd17-167">
<a href="/office365/enterprise/external-domain-name-system-records">External Domain Name System records</a></em></span></span></p></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="bfd17-168">Créer et afficher des réunions dans Teams</span><span class="sxs-lookup"><span data-stu-id="bfd17-168">Create and view Meetings in Teams</span></span></td>
<td><p><span data-ttu-id="bfd17-169">Possibilité de créer des réunions internes et externes via Outlook-in.</span><span class="sxs-lookup"><span data-stu-id="bfd17-169">Able to create internal and external meetings via Outlook add-in.</span></span></p>
<p><span data-ttu-id="bfd17-170">Les fonctionnalités de connexion et d’appel sortant PSTN sont disponibles avec les licences d’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="bfd17-170">PSTN Dial in and Dial out capability is available with the Audio Conferencing licenses.</span></span></p>
<p><span data-ttu-id="bfd17-171">Teams accès au calendrier nécessite Exchange 2016 CU3+ en local déployé avec Exchange hybride établi : créer un déploiement hybride avec l’Assistant <a href="/exchange/hybrid-deployment/deploy-hybrid">Configuration hybride.</a> </span><span class="sxs-lookup"><span data-stu-id="bfd17-171">Teams calendar access requires Exchange 2016 CU3+ on-premises deployed with Exchange hybrid established: <a href="/exchange/hybrid-deployment/deploy-hybrid">Create a hybrid deployment with the Hybrid Configuration wizard.</a> </span></span></p>
<p><span data-ttu-id="bfd17-172">Outre une configuration Exchange hybride, établissez Exchange authentification OAuth : configurer l’authentification OAuth entre les Exchange et <a href="https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help"> Exchange Online utilisateurs ».</span><span class="sxs-lookup"><span data-stu-id="bfd17-172">In addition to Exchange hybrid configuration, establish Exchange OAuth authentication: <a href="https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help">Configure OAuth authentication between Exchange and Exchange Online organizations".</span></span></p>

</p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="bfd17-173">Fonctionnalités d’appel</span><span class="sxs-lookup"><span data-stu-id="bfd17-173">Calling Features</span></span><br />
<span data-ttu-id="bfd17-174">VoIP /PSTN dans Teams</span><span class="sxs-lookup"><span data-stu-id="bfd17-174">VoIP / PSTN in Teams</span></span></td>
<td><p><span data-ttu-id="bfd17-175">VoIP en interne et en externe vers le client est disponible.</span><span class="sxs-lookup"><span data-stu-id="bfd17-175">VoIP internally and externally to the tenant is available.</span></span></p>
<p><span data-ttu-id="bfd17-176">Les services RSTN peuvent être configurés via Téléphone Microsoft système informatique, ainsi que l’ajout d’un plan d’appel Microsoft ou d’un routage direct.</span><span class="sxs-lookup"><span data-stu-id="bfd17-176">PSTN services can be configured via Microsoft Phone System, plus adding a Microsoft Calling Plan or Direct Routing.</span></span></p></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="bfd17-177">Teams collaboration dans les canaux dans Teams</span><span class="sxs-lookup"><span data-stu-id="bfd17-177">Teams and Channels collaboration in Teams</span></span></td>
<td><p><span data-ttu-id="bfd17-178">Pour une expérience complète, y compris des fonctionnalités de conformité, une SharePoint Online doit être attribuée à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="bfd17-178">For full experience, including compliance features, a SharePoint Online license need to be assigned to the user.</span></span></p>
<p><span data-ttu-id="bfd17-179">La migration de sites locaux SharePoint n’est pas nécessaire.</span><span class="sxs-lookup"><span data-stu-id="bfd17-179">Migration of existing on-premises SharePoint sites is not required.</span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="bfd17-180">OneDrive Entreprise (partage de fichiers P2P)</span><span class="sxs-lookup"><span data-stu-id="bfd17-180">OneDrive for Business (P2P file sharing)</span></span></td>
<td><span data-ttu-id="bfd17-181">OneDrive Entreprise nécessite qu’un utilisateur soit affecté SharePoint licence Online.</span><span class="sxs-lookup"><span data-stu-id="bfd17-181">OneDrive for Business requires a user to have a SharePoint Online license assigned.</span></span> <span data-ttu-id="bfd17-182">Sans cette licence, le partage de fichiers d’égal à égal ne sera pas possible.</span><span class="sxs-lookup"><span data-stu-id="bfd17-182">Without this license peer-to-peer file sharing will not be possible.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="bfd17-183">Plateforme des applications</span><span class="sxs-lookup"><span data-stu-id="bfd17-183">Application platform</span></span></td>
<td><span data-ttu-id="bfd17-184">Les utilisateurs pourront utiliser les applications désignées disponibles en fonction des stratégies de votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="bfd17-184">Users will be able to use the apps that are designated available for them according to your company policies.</span></span><br />
<span data-ttu-id="bfd17-185">En savoir plus ici : <a href="/microsoftteams/admin-settings">Paramètres d’administration des applications dans Teams</a></span><span class="sxs-lookup"><span data-stu-id="bfd17-185">Learn more here: <a href="/microsoftteams/admin-settings">Admin settings for apps in Teams</a></span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="bfd17-186">Fonctionnalités de sécurité et de conformité</span><span class="sxs-lookup"><span data-stu-id="bfd17-186">Security and Compliance features</span></span></td>
<td><ul>
<li><p><span data-ttu-id="bfd17-187">Des stratégies de rétention sont disponibles.</span><span class="sxs-lookup"><span data-stu-id="bfd17-187">Retention policies are available.</span></span></p></li>
<li><p><span data-ttu-id="bfd17-188">EDiscovery et la mise en attente légale pour la conformité des messages de canal sont pris en charge.</span><span class="sxs-lookup"><span data-stu-id="bfd17-188">eDiscovery and Legal Hold for compliance on channel messages is supported.</span></span></p></li>
<li><p><span data-ttu-id="bfd17-189">Des stratégies de protection contre la perte de données (DLP) sont disponibles.</span><span class="sxs-lookup"><span data-stu-id="bfd17-189">Data Loss Prevention policies (DLP) are available.</span></span></p></li>
</ul>
<p><span data-ttu-id="bfd17-190">Jeu de fonctionnalités complet disponible avec Exchange Online ; Exchange local prend en charge la plupart de ces fonctionnalités.</span><span class="sxs-lookup"><span data-stu-id="bfd17-190">Full feature set available with Exchange Online; Exchange on-premises supports most of these features.</span></span> <span data-ttu-id="bfd17-191">Pour obtenir la liste complète, consultez <a href="/MicrosoftTeams/exchange-teams-interact">comment les Exchange et les Teams interagissent.</a></span><span class="sxs-lookup"><span data-stu-id="bfd17-191">For a full list, see <a href="/MicrosoftTeams/exchange-teams-interact">How Exchange and Teams interact</a>.</span></span></p></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-without-skype-for-business-or-lync-server"></a><span data-ttu-id="bfd17-192">Étapes d’enablement pour les organisations sans Skype Entreprise ou Lync Server</span><span class="sxs-lookup"><span data-stu-id="bfd17-192">Enablement steps for organizations without Skype for Business or Lync Server</span></span>

1.  <span data-ttu-id="bfd17-193">Répondre aux conditions préalables détaillées dans la section Démarrer ici ci-dessus</span><span class="sxs-lookup"><span data-stu-id="bfd17-193">Meet pre-requisites detailed in the Start Here section above</span></span>

2.  <span data-ttu-id="bfd17-194">Basculez vers Teams mode Client uniquement (pour les clients existants uniquement) : Définition de vos paramètres de coexistence et [de mise à niveau.](setting-your-coexistence-and-upgrade-settings.md)</span><span class="sxs-lookup"><span data-stu-id="bfd17-194">Switch tenant into Teams Only mode (for existing tenants only): [Setting your coexistence and upgrade settings](setting-your-coexistence-and-upgrade-settings.md).</span></span>

3.  <span data-ttu-id="bfd17-195">Configurez votre client conformément aux stratégies de votre entreprise ou de votre entreprise : gérez les paramètres Microsoft Teams [pour votre organisation.](enable-features-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="bfd17-195">Configure your tenant in accordance with your company's business/company policies: [Manage Microsoft Teams settings for your organization](enable-features-office-365.md).</span></span>

4.  <span data-ttu-id="bfd17-196">Déployer le client Teams client pour vos utilisateurs : [obtenir des clients pour Teams](get-clients.md)</span><span class="sxs-lookup"><span data-stu-id="bfd17-196">Deploy the Teams client to your users: [Get clients for Teams](get-clients.md)</span></span>

5.  <span data-ttu-id="bfd17-197">Pilotez votre programme d’adoption</span><span class="sxs-lookup"><span data-stu-id="bfd17-197">Drive your adoption program</span></span>  
    [<span data-ttu-id="bfd17-198">Adopter Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="bfd17-198">Adopt Microsoft Teams</span></span>](adopt-microsoft-teams-landing-page.md)
    
    [<span data-ttu-id="bfd17-199">Liste de contrôle de démarrage rapide pour l’adoption de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="bfd17-199">Microsoft Teams adoption quick start checklist</span></span>](teams-adoption-quick-start-checklist.md)

6.  <span data-ttu-id="bfd17-200">Commencez à planifier le déplacement d’autres charges de Microsoft 365 ou Office 365</span><span class="sxs-lookup"><span data-stu-id="bfd17-200">Begin planning moving other workloads to Microsoft 365 or Office 365</span></span>

## <a name="organizations-span-classunderlinewithspan-skype-for-business-or-lync-server"></a><span data-ttu-id="bfd17-201">Organisations **<span class="underline">avec</span>** Skype Entreprise ou Lync Server</span><span class="sxs-lookup"><span data-stu-id="bfd17-201">Organizations **<span class="underline">with</span>** Skype for Business or Lync server</span></span>

<span data-ttu-id="bfd17-202">Ce point de départ suppose que votre organisation utilise Skype Entreprise 2019, 2015 et Lync 2013+ en local.</span><span class="sxs-lookup"><span data-stu-id="bfd17-202">This starting point assumes that your organization utilizes Skype for Business 2019 or 2015+ or Lync 2013+ server on premises.</span></span> <span data-ttu-id="bfd17-203">Nous avons déjà d’importantes recommandations concernant la migration des serveurs locaux vers Teams organisations, qui doivent être suivies pour ces scénarios.</span><span class="sxs-lookup"><span data-stu-id="bfd17-203">We already have extensive guidance for organizations migrating from on premises servers to Teams and it should be followed for these scenarios.</span></span> <span data-ttu-id="bfd17-204">Ces instructions sont spécifiques au scénario Teams’application que vous utilisez en Microsoft 365 ou Office 365.</span><span class="sxs-lookup"><span data-stu-id="bfd17-204">This guidance is specific to the scenario that Teams is the first application you utilize in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="bfd17-205">Le tableau suivant détaille la configuration de haut niveau et les capacités des utilisateurs finaux pour Teams services principaux.</span><span class="sxs-lookup"><span data-stu-id="bfd17-205">The following table details high level configuration and end user capabilities for Teams for core services.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="bfd17-206">Élément</span><span class="sxs-lookup"><span data-stu-id="bfd17-206">Item</span></span></th>
<th><span data-ttu-id="bfd17-207">Remarques</span><span class="sxs-lookup"><span data-stu-id="bfd17-207">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="bfd17-208">Configuration Teams client</span><span class="sxs-lookup"><span data-stu-id="bfd17-208">Tenant Teams configuration</span></span></td>
<td><span data-ttu-id="bfd17-209">Mode Îles.</span><span class="sxs-lookup"><span data-stu-id="bfd17-209">Islands mode.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="bfd17-210">Conversation / Communication externe dans Teams</span><span class="sxs-lookup"><span data-stu-id="bfd17-210">Chat / External Communication in Teams</span></span></td>
<td><span data-ttu-id="bfd17-211">En interne uniquement au sein de votre propre client, les communications externes (fédération) sont accessibles via votre Skype Entreprise ou votre serveur Lync.</span><span class="sxs-lookup"><span data-stu-id="bfd17-211">Internal within your own tenant only, external communication (federation) is via your Skype for Business or Lync server deployment.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="bfd17-212">Créer et afficher des réunions dans Teams</span><span class="sxs-lookup"><span data-stu-id="bfd17-212">Create and view Meetings in Teams</span></span></td>
<td><p><span data-ttu-id="bfd17-213">Possibilité de créer des réunions internes et externes via Outlook-in.</span><span class="sxs-lookup"><span data-stu-id="bfd17-213">Able to create internal and external meetings via Outlook add-in.</span></span></p>
<p><span data-ttu-id="bfd17-214">Les fonctionnalités de connexion et d’appel sortant PSTN sont disponibles avec les licences d’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="bfd17-214">PSTN Dial in and Dial out capability is available with the Audio Conferencing licenses.</span></span></p>
<p><span data-ttu-id="bfd17-215">Teams accès au calendrier nécessite Exchange 2016 CU3+ en local déployé avec une version Exchange hybride établie :</span><span class="sxs-lookup"><span data-stu-id="bfd17-215">Teams calendar access requires Exchange 2016 CU3+ on-premises deployed with Exchange hybrid established:</span></span><br /><span data-ttu-id="bfd17-216">
<a href="/exchange/hybrid-deployment/deploy-hybrid">Créez un déploiement hybride à l’aide de l’Assistant Configuration hybride.</a></span><span class="sxs-lookup"><span data-stu-id="bfd17-216">
<a href="/exchange/hybrid-deployment/deploy-hybrid">Create a hybrid deployment with the Hybrid Configuration wizard.</a></span></span></p>
<p><span data-ttu-id="bfd17-217">Un administrateur peut contrôler le Skype Entreprise Outlook par le biais de l’attribut PreferredMeetingProviderForIslandsMode de la stratégie de réunion Teams :<a href="/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps"> set-csteamsmeetingpolicy.</a></span><span class="sxs-lookup"><span data-stu-id="bfd17-217">Administrator can control the Skype for Business Outlook add-in via the Teams meeting policy’s PreferredMeetingProviderForIslandsMode attribute:<a href="/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps"> set-csteamsmeetingpolicy</a>.</span></span></p> 
</td>
</tr>
<tr class="even">
<td><span data-ttu-id="bfd17-218">Fonctionnalités d’appel</span><span class="sxs-lookup"><span data-stu-id="bfd17-218">Calling Features</span></span><br />
<span data-ttu-id="bfd17-219">VoIP /PSTN dans Teams</span><span class="sxs-lookup"><span data-stu-id="bfd17-219">VoIP / PSTN in Teams</span></span></td>
<td><p><span data-ttu-id="bfd17-220">VoIP en interne pour le client est disponible.</span><span class="sxs-lookup"><span data-stu-id="bfd17-220">VoIP internally to the tenant is available.</span></span></p>
<p><span data-ttu-id="bfd17-221">Les services PSTN ou Calling Plan ne sont pas disponibles tant que l’utilisateur n’a pas été déplacé vers Teams expérience uniquement.</span><span class="sxs-lookup"><span data-stu-id="bfd17-221">PSTN or Calling Plan services are not available until the user is moved to Teams Only experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="bfd17-222">Teams collaboration dans les canaux dans Teams</span><span class="sxs-lookup"><span data-stu-id="bfd17-222">Teams and Channels collaboration in Teams</span></span></td>
<td><p><span data-ttu-id="bfd17-223">Pour une expérience complète, y compris des fonctionnalités de conformité, une SharePoint Online doit être attribuée à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="bfd17-223">For full experience, including compliance features, a SharePoint Online license need to be assigned to the user.</span></span></p>
<p><span data-ttu-id="bfd17-224">La migration de sites locaux SharePoint n’est pas nécessaire.</span><span class="sxs-lookup"><span data-stu-id="bfd17-224">Migration of existing on-premises SharePoint sites is not required.</span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="bfd17-225">OneDrive Entreprise (partage de fichiers P2P)</span><span class="sxs-lookup"><span data-stu-id="bfd17-225">OneDrive for Business (P2P file sharing)</span></span></td>
<td><span data-ttu-id="bfd17-226">OneDrive Entreprise nécessite qu’un utilisateur soit affecté SharePoint licence Online.</span><span class="sxs-lookup"><span data-stu-id="bfd17-226">OneDrive for Business requires a user to have a SharePoint Online license assigned.</span></span> <span data-ttu-id="bfd17-227">Sans cette licence, le partage de fichiers entre homologues ne sera pas possible.</span><span class="sxs-lookup"><span data-stu-id="bfd17-227">Without this license per-to-peer file sharing will not be possible.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="bfd17-228">Plateforme des applications</span><span class="sxs-lookup"><span data-stu-id="bfd17-228">Application platform</span></span></td>
<td><span data-ttu-id="bfd17-229">Les utilisateurs pourront utiliser les applications désignées disponibles en fonction des stratégies de votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="bfd17-229">Users will be able to use the apps that are designated available for them according to your company policies.</span></span><br />
<span data-ttu-id="bfd17-230">En savoir plus ici : <a href="/microsoftteams/admin-settings">Paramètres d’administration des applications dans Teams</a></span><span class="sxs-lookup"><span data-stu-id="bfd17-230">Learn more here: <a href="/microsoftteams/admin-settings">Admin settings for apps in Teams</a></span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="bfd17-231">Fonctionnalités de sécurité et de conformité</span><span class="sxs-lookup"><span data-stu-id="bfd17-231">Security and Compliance features</span></span></td>
<td><ul>
<li><p><span data-ttu-id="bfd17-232">Des stratégies de rétention sont disponibles.</span><span class="sxs-lookup"><span data-stu-id="bfd17-232">Retention policies are available.</span></span></p></li>
<li><p><span data-ttu-id="bfd17-233">EDiscovery et la mise en attente légale pour la conformité des messages de canal sont pris en charge.</span><span class="sxs-lookup"><span data-stu-id="bfd17-233">eDiscovery and Legal Hold for compliance on channel messages is supported.</span></span></p></li>
<li><p><span data-ttu-id="bfd17-234">Des stratégies de protection contre la perte de données (DLP) sont disponibles.</span><span class="sxs-lookup"><span data-stu-id="bfd17-234">Data Loss Prevention policies (DLP) are available.</span></span></p></li>
</ul>
<p><span data-ttu-id="bfd17-235">Jeu de fonctionnalités complet disponible avec Exchange Online ; Exchange local prend en charge la plupart de ces fonctionnalités.</span><span class="sxs-lookup"><span data-stu-id="bfd17-235">Full feature set available with Exchange Online; Exchange on-premises supports most of these features.</span></span> <span data-ttu-id="bfd17-236">Pour consulter la liste complète, voir <a href="/MicrosoftTeams/exchange-teams-interact">comment les utilisateurs Exchange et Teams interagir.</a></span><span class="sxs-lookup"><span data-stu-id="bfd17-236">For a complete list, see <a href="/MicrosoftTeams/exchange-teams-interact">How Exchange and Teams interact.</a></span></span></p>
<ul>
</ul></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-with-skype-for-business-server"></a><span data-ttu-id="bfd17-237">Étapes d’activement pour les organisations avec Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="bfd17-237">Enablement steps for organizations with Skype for Business Server</span></span>  

1.  <span data-ttu-id="bfd17-238">Respectez les conditions préalables détaillées dans la section Démarrer ici ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="bfd17-238">Meet pre-requisites detailed in the Start Here section above.</span></span>

2.  <span data-ttu-id="bfd17-239">Basculer vers le mode Îles (pour les locataires mis en service APRÈS le 01/09/2019, contactez le support pour apporter cette modification)</span><span class="sxs-lookup"><span data-stu-id="bfd17-239">Switch tenant into Islands mode (for tenants provisioned AFTER 9/1/2019, please contact support to make this change)</span></span>  
    [<span data-ttu-id="bfd17-240">Configuration de vos paramètres de coexistence et de mise à niveau</span><span class="sxs-lookup"><span data-stu-id="bfd17-240">Setting your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)

3.  <span data-ttu-id="bfd17-241">Configurer votre client conformément aux stratégies de votre entreprise</span><span class="sxs-lookup"><span data-stu-id="bfd17-241">Configure your tenant in accordance with your company's business/company policies</span></span>  
    [<span data-ttu-id="bfd17-242">Gérer les paramètres de Microsoft Teams pour votre organisation</span><span class="sxs-lookup"><span data-stu-id="bfd17-242">Manage Microsoft Teams settings for your organization</span></span>](enable-features-office-365.md)

4.  <span data-ttu-id="bfd17-243">Déployer le client Teams client</span><span class="sxs-lookup"><span data-stu-id="bfd17-243">Deploy the Teams client</span></span>  
    [<span data-ttu-id="bfd17-244">Obtenir des clients pour Teams</span><span class="sxs-lookup"><span data-stu-id="bfd17-244">Get clients for Teams</span></span>](get-clients.md)

5.   <span data-ttu-id="bfd17-245">Pilotez votre programme d’adoption</span><span class="sxs-lookup"><span data-stu-id="bfd17-245">Drive your adoption program</span></span>  
    [<span data-ttu-id="bfd17-246">Adopter Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="bfd17-246">Adopt Microsoft Teams</span></span>](adopt-microsoft-teams-landing-page.md)<br/>
    [<span data-ttu-id="bfd17-247">Liste de contrôle de démarrage rapide pour l’adoption de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="bfd17-247">Microsoft Teams adoption quick start checklist</span></span>](teams-adoption-quick-start-checklist.md)

6.  <span data-ttu-id="bfd17-248">Commencez à planifier le déplacement d’autres charges de Microsoft 365 ou Office 365</span><span class="sxs-lookup"><span data-stu-id="bfd17-248">Begin planning moving other workloads to Microsoft 365 or Office 365</span></span>

7.  <span data-ttu-id="bfd17-249">Établissez Skype Entreprise hybride et suivez les chemins de mise à niveau recommandés pour Skype Entreprise serveurs Lync</span><span class="sxs-lookup"><span data-stu-id="bfd17-249">Establish Skype for Business hybrid and follow the recommended upgrade paths for Skype for Business and Lync servers</span></span>  
    [<span data-ttu-id="bfd17-250">Mettre à niveau Skype Entreprise locaux vers Teams</span><span class="sxs-lookup"><span data-stu-id="bfd17-250">Upgrade from Skype for Business on-premises to Teams</span></span>](upgrade-to-teams-execute-skypeforbusinesshybridonprem.md)

## <a name="closing-statement"></a><span data-ttu-id="bfd17-251">Déclaration de clôture</span><span class="sxs-lookup"><span data-stu-id="bfd17-251">Closing statement</span></span>

<span data-ttu-id="bfd17-252">Microsoft Teams peut permettre à votre organisation de rassembler l’ensemble des employés, des travailleurs de l’information et des employés en ligne, sur une seule plateforme.</span><span class="sxs-lookup"><span data-stu-id="bfd17-252">Microsoft Teams can be an enabler for your organization to bring all the employees, information workers and Frontline workers, together on a single platform.</span></span> <span data-ttu-id="bfd17-253">Vous pouvez [commencer dès aujourd’hui.](https://products.office.com/microsoft-teams/group-chat-software)</span><span class="sxs-lookup"><span data-stu-id="bfd17-253">You can [get started](https://products.office.com/microsoft-teams/group-chat-software) today.</span></span> <span data-ttu-id="bfd17-254">Vous pouvez rester en contact avec toutes nos dernières annonces et mises à jour mensuelles de [produits ici.](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/bg-p/MicrosoftTeamsBlog)</span><span class="sxs-lookup"><span data-stu-id="bfd17-254">You can keep in touch with all our latest announcements and monthly product updates [here](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/bg-p/MicrosoftTeamsBlog).</span></span>

<span data-ttu-id="bfd17-255">Par ailleurs, étant donne lieu à la gestion de l’état actuel de COVID-19 par des entreprises du monde entier, nous avons créé une série de contenus qui vous aideront à utiliser Teams pour un impact maximal sur votre organisation.</span><span class="sxs-lookup"><span data-stu-id="bfd17-255">Additionally, as companies around the world are managing the current COVID-19 situation, we have created a series of content that will help you utilize Teams for the maximum impact in your organization.</span></span>

  - <span data-ttu-id="bfd17-256">Notre [engagement auprès des clients pendant la période COVID-19](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/05/our-commitment-to-customers-during-covid-19/)</span><span class="sxs-lookup"><span data-stu-id="bfd17-256">Our [commitment to customers during COVID-19](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/05/our-commitment-to-customers-during-covid-19/)</span></span>

  - [<span data-ttu-id="bfd17-257">2 semaines en : ce que nous avons appris sur le travail à distance</span><span class="sxs-lookup"><span data-stu-id="bfd17-257">2 weeks in: what we've learned about remote work</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/18/making-the-switch-to-remote-work-5-things-weve-learned/)

  - [<span data-ttu-id="bfd17-258">Fournir des réunions et des événements en ligne</span><span class="sxs-lookup"><span data-stu-id="bfd17-258">Delivering online meetings and events</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/delivering-online-meetings-events/)

  - [<span data-ttu-id="bfd17-259">Aider les petites et moyennes entreprises à travailler à distance avec Teams</span><span class="sxs-lookup"><span data-stu-id="bfd17-259">Helping small and medium-sized businesses work remotely with Teams</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/helping-smb-customers-work-remotely-microsoft-teams/)

  - [<span data-ttu-id="bfd17-260">Transformation numérique d’événements en direct : les observations d’Bob Bejan à partir de la première ligne</span><span class="sxs-lookup"><span data-stu-id="bfd17-260">Digital transformation of live events: Bob Bejan's observations from the frontline</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/13/digital-transformation-live-events-bob-bejans-observations-frontline/)

  - [<span data-ttu-id="bfd17-261">Les 9 principaux moyens que Microsoft IT utilise pour activer le travail à distance de ses employés</span><span class="sxs-lookup"><span data-stu-id="bfd17-261">The top 9 ways Microsoft IT is enabling remote work for its employees</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/top-9-ways-microsoft-it-enabling-remote-work-employees/)

  - [<span data-ttu-id="bfd17-262">Travailler à distance, rester en sécurité : conseils pour les cisos</span><span class="sxs-lookup"><span data-stu-id="bfd17-262">Work remotely, stay secure—tips for CISOs</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/work-remotely-stay-secure-ciso-tips/)

  - [<span data-ttu-id="bfd17-263">Aider les enseignants et les étudiants à basculer vers l’apprentissage à distance</span><span class="sxs-lookup"><span data-stu-id="bfd17-263">Helping teachers and students make the switch to remote learning</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/11/helping-teachers-students-switch-remote-learning/)

  - [<span data-ttu-id="bfd17-264">Rester productif tout en travaillant à distance avec Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="bfd17-264">Staying productive while working remotely with Microsoft Teams</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/10/staying-productive-while-working-remotely-with-microsoft-teams/)

## <a name="support-services-reference"></a><span data-ttu-id="bfd17-265">Référence des services d’assistance technique</span><span class="sxs-lookup"><span data-stu-id="bfd17-265">Support Services reference</span></span>

<span data-ttu-id="bfd17-266">Teams s’appuie sur les groupes Exchange Online, SharePoint Online, OneDrive Entreprise et Microsoft 365 pour offrir à vos utilisateurs une expérience d’Microsoft 365 de Office 365 entièrement intégrée.</span><span class="sxs-lookup"><span data-stu-id="bfd17-266">Teams relies on Exchange Online, SharePoint Online, OneDrive for Business and Microsoft 365 Groups to provide your users with a fully integrated Microsoft 365 or Office 365 experience.</span></span> <span data-ttu-id="bfd17-267">Comme indiqué ci-dessus, Teams fonctionne sans un déploiement complet de ces services, avec des fonctionnalités limitées.</span><span class="sxs-lookup"><span data-stu-id="bfd17-267">As noted above, Teams will work without full deploying these services – with limited capabilities.</span></span> <span data-ttu-id="bfd17-268">Pour en savoir plus sur Teams et ses conditions préalables, voir : [Bienvenue dans Teams.](teams-overview.md)</span><span class="sxs-lookup"><span data-stu-id="bfd17-268">You can read more about Teams and its pre-requisites here: [Welcome to Teams](teams-overview.md).</span></span>

<span data-ttu-id="bfd17-269">Pour plus d’informations sur chacun des services répertoriés ci-dessus, suivez les liens ci-dessous :</span><span class="sxs-lookup"><span data-stu-id="bfd17-269">For specifics on each of the services listed above, please follow the links below:</span></span>

  - <span data-ttu-id="bfd17-270">Exchange Online est utilisé pour les fonctionnalités de calendrier et le stockage de messages d’égal à égal dans Teams.</span><span class="sxs-lookup"><span data-stu-id="bfd17-270">Exchange Online is used for calendaring features and storing peer to peer messages in Teams.</span></span> <span data-ttu-id="bfd17-271">Pour en savoir plus, [lisez comment Exchange et comment Teams interagissez](exchange-teams-interact.md)</span><span class="sxs-lookup"><span data-stu-id="bfd17-271">To learn more, read [How Exchange and Teams interact](exchange-teams-interact.md)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bfd17-272">Pour Teams opation avec Exchange locale, vous devez configurer le nouveau protocole d’authentification OAuth Exchange, comme décrit dans la procédure Configurer l’authentification [OAuth](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)entre les organisations Exchange et Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="bfd17-272">For Teams interop with Exchange on-premises, you must configure the new Exchange OAuth authentication protocol as described in [Configure OAuth authentication between Exchange and Exchange Online organizations](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help).</span></span>

  - <span data-ttu-id="bfd17-273">SharePoint est utilisé pour le partage de fichiers dans les canaux, tandis que /OneDrive Entreprise est utilisé pour le partage de fichiers dans une conversation en tête-à-tête ou en groupe.</span><span class="sxs-lookup"><span data-stu-id="bfd17-273">SharePoint is used for file sharing in channels, while /OneDrive for Business is used for file sharing in 1:1 or group chat.</span></span> <span data-ttu-id="bfd17-274">Pour en savoir plus, [lisez comment SharePoint Online et comment OneDrive Entreprise interagissez avec Microsoft Teams.](sharepoint-onedrive-interact.md)</span><span class="sxs-lookup"><span data-stu-id="bfd17-274">To learn more, read [How SharePoint Online and OneDrive for Business interact with Microsoft Teams](sharepoint-onedrive-interact.md).</span></span>

  - <span data-ttu-id="bfd17-275">[Microsoft 365 groupes sont](office-365-groups.md) utilisés pour la création/gestion d’équipes et de canaux.</span><span class="sxs-lookup"><span data-stu-id="bfd17-275">[Microsoft 365 Groups](office-365-groups.md) are used for team and channel creation/management.</span></span>


## <a name="related-topics"></a><span data-ttu-id="bfd17-276">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="bfd17-276">Related topics</span></span>

[<span data-ttu-id="bfd17-277">Illustrations architecture IT Microsoft Teams et solutions téléphonie</span><span class="sxs-lookup"><span data-stu-id="bfd17-277">Microsoft Teams IT architecture and telephony solutions posters</span></span>](teams-architecture-solutions-posters.md#teams-as-part-of-microsoft-365)

[<span data-ttu-id="bfd17-278">Planifier la connectivité hybride entre Skype Entreprise Server et Office 365</span><span class="sxs-lookup"><span data-stu-id="bfd17-278">Plan hybrid connectivity between Skype for Business Server and Office 365</span></span>](/SkypeForBusiness/hybrid/plan-hybrid-connectivity)

[<span data-ttu-id="bfd17-279">Prise en charge des travailleurs à distance à l’aide Teams</span><span class="sxs-lookup"><span data-stu-id="bfd17-279">Support remote workers using Teams</span></span>](support-remote-work-with-teams.md)

[<span data-ttu-id="bfd17-280">Travailler à distance avec des Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="bfd17-280">Work remotely with Microsoft 365</span></span>](https://aka.ms/remote-work)