---
title: Autorisations d’applications Microsoft Teams et points à prendre en compte
author: rmw2890
ms.author: rowille
manager: serdars
ms.date: 06/27/2019
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-voice
- M365-collaboration
search.appverid: MET150
ms.reviewer: rowille
description: L’administrateur peut découvrir quelles sont les données et les autorisations que les applications Microsoft teams demandent à leur organisation.
f1.keywords:
- NOCSH
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f19cbbba6df7c43c69af35893466344e8df1d17d
ms.sourcegitcommit: 296aeac481f901eb9d52b4f12a8c037afc49fa77
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2020
ms.locfileid: "44256479"
---
# <a name="microsoft-teams-apps-permissions-and-considerations"></a><span data-ttu-id="4bb35-103">Autorisations d’applications Microsoft Teams et points à prendre en compte</span><span class="sxs-lookup"><span data-stu-id="4bb35-103">Microsoft Teams apps permissions and considerations</span></span>

<span data-ttu-id="4bb35-104">Les applications Microsoft Teams permettent de regrouper une ou plusieurs fonctionnalités dans un _package d’applications_ qui peut être installé, mis à niveau et désinstallé.</span><span class="sxs-lookup"><span data-stu-id="4bb35-104">Microsoft Teams apps are a way to aggregate one or more capabilities into an _app package_ that can be installed, upgraded, and uninstalled.</span></span> <span data-ttu-id="4bb35-105">Ces fonctionnalités incluent les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="4bb35-105">The capabilities include:</span></span>

- <span data-ttu-id="4bb35-106">Bots</span><span class="sxs-lookup"><span data-stu-id="4bb35-106">Bots</span></span>
- <span data-ttu-id="4bb35-107">Extensions de messagerie</span><span class="sxs-lookup"><span data-stu-id="4bb35-107">Messaging extensions</span></span>
- <span data-ttu-id="4bb35-108">Onglets</span><span class="sxs-lookup"><span data-stu-id="4bb35-108">Tabs</span></span>
- <span data-ttu-id="4bb35-109">Connecteurs</span><span class="sxs-lookup"><span data-stu-id="4bb35-109">Connectors</span></span>

<span data-ttu-id="4bb35-110">Les bots sont acceptés par les utilisateurs et gérés par le service informatique de vue stratégique.</span><span class="sxs-lookup"><span data-stu-id="4bb35-110">Apps are consented to by users and managed by IT from a policy perspective.</span></span> <span data-ttu-id="4bb35-111">Toutefois, pour la plupart des cas, les autorisations et le profil de risques d’une application sont définis par les autorisations et les profils de risques des fonctionnalités contenues dans l’application.</span><span class="sxs-lookup"><span data-stu-id="4bb35-111">However, for the most part, an app's permissions and risk profile are defined by the permissions and risk profiles of the capabilities that the app contains.</span></span> <span data-ttu-id="4bb35-112">Cet article est donc axé sur les autorisations et les éléments à prendre en compte au niveau des fonctionnalités.</span><span class="sxs-lookup"><span data-stu-id="4bb35-112">Therefore, this article focuses on permissions and considerations at the capability level.</span></span>

<span data-ttu-id="4bb35-113">Les autorisations répertoriées ci-dessous en majuscules, comme par exemple RECEIVE_MESSAGE et REPLYTO_MESSAGE, n’apparaissent pas partout dans la [documentation destinée aux développeurs Microsoft Teams](https://aka.ms/teamsdevdocs) ou les [autorisations de Microsoft Graph](https://developer.microsoft.com/graph/docs/concepts/permissions_reference).</span><span class="sxs-lookup"><span data-stu-id="4bb35-113">The permissions listed below in capital letters, for example RECEIVE_MESSAGE and REPLYTO_MESSAGE, don't appear anywhere in the [Microsoft Teams developer documentation](https://aka.ms/teamsdevdocs) or the [permissions for Microsoft Graph](https://developer.microsoft.com/graph/docs/concepts/permissions_reference).</span></span> <span data-ttu-id="4bb35-114">Il ne s’agit que d’une description aux fins de cet article.</span><span class="sxs-lookup"><span data-stu-id="4bb35-114">They're simply a descriptive shorthand for the purpose of this article.</span></span>


|    |     |
|-----------|------------|
| ![Icône montrant les points de décision](media/audio_conferencing_image7.png) <br/><span data-ttu-id="4bb35-116">Point de décision</span><span class="sxs-lookup"><span data-stu-id="4bb35-116">Decision point</span></span>|<ul><li><span data-ttu-id="4bb35-117">Utilisez le tableau ci-dessous pour connaître les autorisations que les applications que vous recherchez demandent.</span><span class="sxs-lookup"><span data-stu-id="4bb35-117">Use the tables below as a guide to understand which permissions the apps you're investigating are requesting.</span></span></li></ul> |
| ![Icône montrant l’étape suivante](media/audio_conferencing_image9.png)<br/><span data-ttu-id="4bb35-119">Étape suivante</span><span class="sxs-lookup"><span data-stu-id="4bb35-119">Next step</span></span>|<ul><li><span data-ttu-id="4bb35-120">Recherchez l’application ou le service proprement dit pour décider si vous voulez autoriser l’accès au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="4bb35-120">Research the app or service itself to decide whether you want to allow access to it within your organization.</span></span> <span data-ttu-id="4bb35-121">Par exemple, les robots envoient des messages à des utilisateurs et, à l’exception des robots personnalisés d’entreprise, qui sont situés en dehors de la limite de conformité.</span><span class="sxs-lookup"><span data-stu-id="4bb35-121">For example, bots send and receive messages from users, and—except for enterprise custom bots—they're located outside the compliance boundary.</span></span> <span data-ttu-id="4bb35-122">Par conséquent, toute application incluant un bot nécessite ces autorisations et possède au moins ce profil de risques.</span><span class="sxs-lookup"><span data-stu-id="4bb35-122">Therefore, any app that includes a bot requires those permissions and has that risk profile, at a minimum.</span></span> </li></ul>|

## <a name="global-app-permissions-and-considerations"></a><span data-ttu-id="4bb35-123">Autorisations et considérations générales pour les applications</span><span class="sxs-lookup"><span data-stu-id="4bb35-123">Global app permissions and considerations</span></span>

### <a name="required-permissions"></a><span data-ttu-id="4bb35-124">Autorisations requises</span><span class="sxs-lookup"><span data-stu-id="4bb35-124">Required permissions</span></span>

<span data-ttu-id="4bb35-125">Aucun</span><span class="sxs-lookup"><span data-stu-id="4bb35-125">None</span></span>

### <a name="optional-permissions"></a><span data-ttu-id="4bb35-126">Autorisations facultatives</span><span class="sxs-lookup"><span data-stu-id="4bb35-126">Optional permissions</span></span>

<span data-ttu-id="4bb35-127">Aucun</span><span class="sxs-lookup"><span data-stu-id="4bb35-127">None</span></span>

### <a name="considerations"></a><span data-ttu-id="4bb35-128">Inconvénients</span><span class="sxs-lookup"><span data-stu-id="4bb35-128">Considerations</span></span>

- <span data-ttu-id="4bb35-129">Une application doit divulguer les données qu’elle utilise et quelles sont les données utilisées dans ses conditions générales d’utilisation et de politique de confidentialité.</span><span class="sxs-lookup"><span data-stu-id="4bb35-129">An app must disclose what data it uses and what the data is used for in its terms of use and privacy policy links.</span></span>

- <span data-ttu-id="4bb35-130">Le [consentement spécifique aux ressources](resource-specific-consent.md) fournit un ensemble d’autorisations que les applications peuvent demander, qui s’affichent sur l’écran d’installation de l’application.</span><span class="sxs-lookup"><span data-stu-id="4bb35-130">[Resource-specific consent](resource-specific-consent.md) provides a set of permissions that apps can request, which appears on the installation screen of the app.</span></span> <span data-ttu-id="4bb35-131">Pour en savoir plus sur les autorisations de consentement spécifiques aux ressources, voir informations de référence sur les [autorisations de graphique](https://docs.microsoft.com/graph/permissions-reference).</span><span class="sxs-lookup"><span data-stu-id="4bb35-131">To learn more about resource-specific consent permissions, see [Graph permissions reference](https://docs.microsoft.com/graph/permissions-reference).</span></span>

- <span data-ttu-id="4bb35-132">Les applications doivent également disposer d’autorisations autres que des autorisations de consentement spécifiques aux ressources.</span><span class="sxs-lookup"><span data-stu-id="4bb35-132">Apps may also need permissions other than resource-specific consent permissions.</span></span> <span data-ttu-id="4bb35-133">Après l’installation d’une application, l’application peut demander des autorisations de graphique à l’aide d’une invite de consentement.</span><span class="sxs-lookup"><span data-stu-id="4bb35-133">After an app is installed, the app may request Graph permissions through a consent prompt.</span></span> <span data-ttu-id="4bb35-134">Pour en savoir plus, voir [Présentation des expériences de consentement des applications Azure ad](https://docs.microsoft.com/azure/active-directory/develop/application-consent-experience).</span><span class="sxs-lookup"><span data-stu-id="4bb35-134">To learn more, see [Understanding Azure AD application consent experiences](https://docs.microsoft.com/azure/active-directory/develop/application-consent-experience).</span></span> <span data-ttu-id="4bb35-135">Vous pouvez configurer les autorisations et l’autorisation d’API dans le portail Azure.</span><span class="sxs-lookup"><span data-stu-id="4bb35-135">You can configure API permissions and consent in the Azure portal.</span></span> <span data-ttu-id="4bb35-136">Pour en savoir plus, voir [infrastructure d’autorisation d’Azure Active Directory](https://docs.microsoft.com/azure/active-directory/develop/consent-framework).</span><span class="sxs-lookup"><span data-stu-id="4bb35-136">To learn more, see [Azure Active Directory consent framework](https://docs.microsoft.com/azure/active-directory/develop/consent-framework).</span></span>

## <a name="bots-and-messaging-extensions"></a><span data-ttu-id="4bb35-137">Robots et extensions de messagerie</span><span class="sxs-lookup"><span data-stu-id="4bb35-137">Bots and messaging extensions</span></span>

### <a name="required-permissions"></a><span data-ttu-id="4bb35-138">Autorisations requises</span><span class="sxs-lookup"><span data-stu-id="4bb35-138">Required permissions</span></span>

- <span data-ttu-id="4bb35-139">RECEIVE_MESSAGE REPLYTO_MESSAGE.</span><span class="sxs-lookup"><span data-stu-id="4bb35-139">RECEIVE_MESSAGE, REPLYTO_MESSAGE.</span></span> <span data-ttu-id="4bb35-140">Le bot peut recevoir des messages des utilisateurs et y répondre. <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="4bb35-140">The bot can receive messages from users and reply to them.<sup>1</sup></span></span>

- <span data-ttu-id="4bb35-141">POST_MESSAGE_USER.</span><span class="sxs-lookup"><span data-stu-id="4bb35-141">POST_MESSAGE_USER.</span></span> <span data-ttu-id="4bb35-142">Dès qu’un utilisateur a envoyé un message à un bot, le bot peut lui envoyer des messages directs (également appelés *messages proactifs* à tout moment.</span><span class="sxs-lookup"><span data-stu-id="4bb35-142">After a user has sent a message to a bot, the bot can send the user direct messages (also called *proactive messages* at any time.</span></span>

- <span data-ttu-id="4bb35-143">GET_CHANNEL_LIST.</span><span class="sxs-lookup"><span data-stu-id="4bb35-143">GET_CHANNEL_LIST.</span></span> <span data-ttu-id="4bb35-144">Les robots ajoutés aux équipes peuvent obtenir une liste de noms et d’ID des canaux d’une équipe.</span><span class="sxs-lookup"><span data-stu-id="4bb35-144">Bots added to teams can get a list of names and IDs of the channels in a team.</span></span>

### <a name="optional-permissions"></a><span data-ttu-id="4bb35-145">Autorisations facultatives</span><span class="sxs-lookup"><span data-stu-id="4bb35-145">Optional permissions</span></span>

- <span data-ttu-id="4bb35-146">Stockage.</span><span class="sxs-lookup"><span data-stu-id="4bb35-146">IDENTITY.</span></span> <span data-ttu-id="4bb35-147">Lorsqu’il est utilisé dans un canal, les robots de l’application peuvent accéder aux informations d’identité de base des membres de l’équipe (prénom, nom, nom d’utilisateur principal [UPN], adresse de messagerie). lorsqu’il est utilisé dans une conversation personnelle ou de groupe, le bot peut accéder aux mêmes informations pour ces utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="4bb35-147">When it's used in a channel, the app's bots can access basic identity information of team members (first name, last name, user principal name [UPN], email address); when it's used in a personal or group chat, the bot can access the same information for those users.</span></span>

- <span data-ttu-id="4bb35-148">POST_MESSAGE_TEAM.</span><span class="sxs-lookup"><span data-stu-id="4bb35-148">POST_MESSAGE_TEAM.</span></span> <span data-ttu-id="4bb35-149">Permet aux robots d’une application de lui envoyer des messages directs (proactif) à tout moment, même si l’utilisateur n’a jamais parlé au bot auparavant.</span><span class="sxs-lookup"><span data-stu-id="4bb35-149">Allows an app's bots to send direct (proactive) messages to any team member at any time, even if the user has never talked to the bot before.</span></span>

- <span data-ttu-id="4bb35-150">Les éléments suivants ne sont pas des autorisations explicites, mais sont implicites en RECEIVE_MESSAGE et REPLYTO_MESSAGE et les étendues dans lesquelles les robots peuvent être utilisés, déclarées dans le manifeste :</span><span class="sxs-lookup"><span data-stu-id="4bb35-150">The following are not explicit permissions, but are implied by RECEIVE_MESSAGE and REPLYTO_MESSAGE and the scopes into which the bots can be used, declared in the manifest:</span></span>
 
    - <span data-ttu-id="4bb35-151">RECEIVE_MESSAGE_PERSONAL REPLYTO_MESSAGE_PERSONAL</span><span class="sxs-lookup"><span data-stu-id="4bb35-151">RECEIVE_MESSAGE_PERSONAL, REPLYTO_MESSAGE_PERSONAL</span></span>
    - <span data-ttu-id="4bb35-152">RECEIVE_MESSAGE_GROUPCHAT REPLYTO_MESSAGE_GROUPCHAT</span><span class="sxs-lookup"><span data-stu-id="4bb35-152">RECEIVE_MESSAGE_GROUPCHAT, REPLYTO_MESSAGE_GROUPCHAT</span></span>
    - <span data-ttu-id="4bb35-153">RECEIVE_MESSAGE_TEAM REPLYTO_MESSAGE_TEAM</span><span class="sxs-lookup"><span data-stu-id="4bb35-153">RECEIVE_MESSAGE_TEAM, REPLYTO_MESSAGE_TEAM</span></span>

- <span data-ttu-id="4bb35-154">SEND_FILES RECEIVE_FILES. <sup>2</sup> contrôle si un bot peut envoyer et recevoir des fichiers dans la conversation personnelle (pas encore pris en charge pour les conversations ou canaux de groupe).</span><span class="sxs-lookup"><span data-stu-id="4bb35-154">SEND_FILES, RECEIVE_FILES.<sup>2</sup> Controls whether a bot can send and receive files in personal chat (not yet supported for group chat or channels).</span></span>

### <a name="considerations"></a><span data-ttu-id="4bb35-155">Inconvénients</span><span class="sxs-lookup"><span data-stu-id="4bb35-155">Considerations</span></span>

- <span data-ttu-id="4bb35-156">Les robots ont uniquement accès aux équipes auxquelles ils ont été ajoutés ou aux utilisateurs qui les ont installés.</span><span class="sxs-lookup"><span data-stu-id="4bb35-156">Bots only have access to teams to which they've been added or to users who have installed them.</span></span>

- <span data-ttu-id="4bb35-157">Les robots reçoivent uniquement les messages dans lesquels ils sont explicitement indiqués par les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="4bb35-157">Bots only receive messages in which they're explicitly mentioned by users.</span></span> <span data-ttu-id="4bb35-158">Ces données quittent le réseau d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="4bb35-158">This data leaves the corporate network.</span></span>

- <span data-ttu-id="4bb35-159">Les robots peuvent uniquement répondre aux conversations dans lesquelles ils sont mentionnés.</span><span class="sxs-lookup"><span data-stu-id="4bb35-159">Bots can only reply to conversations in which they're mentioned.</span></span>

- <span data-ttu-id="4bb35-160">Après que l’utilisateur a adressé son ID de robot, si ce dernier l’a stocké, il peut lui envoyer un message direct à tout moment.</span><span class="sxs-lookup"><span data-stu-id="4bb35-160">After a user has conversed with a bot, if the bot stores that user's ID, it can send that user direct messages at any time.</span></span>

- <span data-ttu-id="4bb35-161">Le message bot peut en théorie contenir des liens vers des sites de hameçonnage ou des logiciels malveillants, mais les robots peuvent être bloqués par l’utilisateur, l’administrateur client ou globalement par Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4bb35-161">It is theoretically possible for bot messages to contain links to phishing or malware sites, but bots can be blocked by the user, the tenant admin, or globally by Microsoft.</span></span>

- <span data-ttu-id="4bb35-162">Un bot peut récupérer (et peut stocker) des informations d’identité de base pour les membres de l’équipe auxquelles l’application a été ajoutée ou pour des utilisateurs individuels dans des discussions personnelles ou de groupe.</span><span class="sxs-lookup"><span data-stu-id="4bb35-162">A bot can retrieve (and might store) very basic identity information for the team members the app has been added to, or for individual users in personal or group chats.</span></span> <span data-ttu-id="4bb35-163">Pour plus d’informations sur ces utilisateurs, le bot doit avoir besoin de se connecter à Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="4bb35-163">To get further information about these users, the bot must require them to sign in to Azure Active Directory (Azure AD).</span></span>

- <span data-ttu-id="4bb35-164">Les robots peuvent récupérer (et peut-être stocker) la liste de canaux dans une équipe ; ces données quittent le réseau d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="4bb35-164">Bots can retrieve (and might store) the list of channels in a team; this data leaves the corporate network.</span></span>

- <span data-ttu-id="4bb35-165">Lorsqu’un fichier est envoyé à un bot, le fichier quitte le réseau d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="4bb35-165">When a file is sent to a bot, the file leaves the corporate network.</span></span> <span data-ttu-id="4bb35-166">Pour envoyer et recevoir des fichiers, l’utilisateur doit approuver chaque fichier.</span><span class="sxs-lookup"><span data-stu-id="4bb35-166">Sending and receiving files requires user approval for each file.</span></span> 

- <span data-ttu-id="4bb35-167">Par défaut, les robots ne peuvent pas agir de la part de l’utilisateur, mais les robots peuvent demander aux utilisateurs de se connecter ; dès que l’utilisateur se connecte, le bot dispose d’un jeton d’accès permettant d’effectuer d’autres actions.</span><span class="sxs-lookup"><span data-stu-id="4bb35-167">By default, bots don't have the ability to act on behalf of the user, but bots can ask users to sign in; as soon as the user signs in, the bot will have an access token with which it can do additional things.</span></span> <span data-ttu-id="4bb35-168">Exactement ce que ces éléments supplémentaires dépendent du bot et de l’endroit où l’utilisateur se connecte : un bot est une application Azure AD inscrite sur https://apps.dev.microsoft.com/ et peut avoir son propre jeu d’autorisations.</span><span class="sxs-lookup"><span data-stu-id="4bb35-168">Exactly what those additional things are depends on the bot and where the user signs in: a bot is an Azure AD app registered at https://apps.dev.microsoft.com/ and can have its own set of permissions.</span></span>

- <span data-ttu-id="4bb35-169">Les robots sont informés lorsque les utilisateurs sont ajoutés ou supprimés d’une équipe.</span><span class="sxs-lookup"><span data-stu-id="4bb35-169">Bots are informed whenever users are added to or deleted from a team.</span></span>

- <span data-ttu-id="4bb35-170">Les robots ne voient pas les adresses IP des utilisateurs ou d’autres informations de renvoi.</span><span class="sxs-lookup"><span data-stu-id="4bb35-170">Bots don't see users' IP addresses or other referrer information.</span></span> <span data-ttu-id="4bb35-171">Toutes les informations proviennent de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4bb35-171">All information comes from Microsoft.</span></span> <span data-ttu-id="4bb35-172">(Il existe une seule exception : si un bot implémente son propre utilisateur de connexion, l’interface utilisateur de connexion verra les adresses IP et les informations de renvoi des utilisateurs.)</span><span class="sxs-lookup"><span data-stu-id="4bb35-172">(There is one exception: if a bot implements its own sign-in experience, the sign-in UI will see users' IP addresses and referrer information.)</span></span>

- <span data-ttu-id="4bb35-173">En revanche, les extensions de messagerie s’affichent avec les adresses IP des utilisateurs et les informations de renvoi.</span><span class="sxs-lookup"><span data-stu-id="4bb35-173">Messaging extensions, on the other hand, do see users' IP addresses and referrer information.</span></span>

- <span data-ttu-id="4bb35-174">Recommandations en matière d’applications (et notre processus de vérification AppSource) exigez la discrétion lors de l’envoi de messages de discussion personnelles aux utilisateurs (via l’autorisation POST_MESSAGE_TEAM) à des fins valides.</span><span class="sxs-lookup"><span data-stu-id="4bb35-174">App guidelines (and our AppSource review process) require discretion in posting personal chat messages to users (via the POST_MESSAGE_TEAM permission) for valid purposes.</span></span> <span data-ttu-id="4bb35-175">En cas d’abus, les utilisateurs peuvent bloquer le bot, les administrateurs de clients peuvent bloquer l’application et Microsoft peut bloquer les robots de manière centralisée, le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="4bb35-175">In the event of abuse, users can block the bot, tenant admins can block the app, and Microsoft can block bots centrally if necessary.</span></span>

<span data-ttu-id="4bb35-176"><sup>1</sup> certains robots envoient uniquement des messages (POST_MESSAGE_USER).</span><span class="sxs-lookup"><span data-stu-id="4bb35-176"><sup>1</sup> Some bots only send messages (POST_MESSAGE_USER).</span></span> <span data-ttu-id="4bb35-177">Il s’agit de robots « notifications uniquement », mais le terme ne fait pas référence à ce qu’un bot est autorisé ou qu’il n’est pas autorisé à faire, cela signifie que le bot ne veut pas exposer une conversation.</span><span class="sxs-lookup"><span data-stu-id="4bb35-177">They're called "notification-only" bots, but the term doesn't refer to what a bot is allowed or not allowed to do, it means that the bot doesn't want to expose a conversational experience.</span></span> <span data-ttu-id="4bb35-178">Teams utilise ce champ pour désactiver les fonctionnalités de l’interface utilisateur qui seraient en principe activées ; Ce robot n’est pas limité à ce qu’il est autorisé à faire comparé aux robots qui présentent une connaissance de conversation.</span><span class="sxs-lookup"><span data-stu-id="4bb35-178">Teams uses this field to disable functionality in the UI that would ordinarily be enabled; the bot isn't restricted in what it's allowed to do compared to bots that do expose a conversational experience.</span></span>

<span data-ttu-id="4bb35-179"><sup>2</sup> soumis à la propriété booléenne supportsFiles sur l’objet bot dans le fichier manifest. JSON de l’application.</span><span class="sxs-lookup"><span data-stu-id="4bb35-179"><sup>2</sup> Governed by the supportsFiles Boolean property on the bot object in the manifest.json file for the app.</span></span>

> [!NOTE]
> <span data-ttu-id="4bb35-180">Si un bot dispose de sa propre connexion, il y a une deuxième fonction de consentement pour la première fois que l’utilisateur se connecte.</span><span class="sxs-lookup"><span data-stu-id="4bb35-180">If a bot has its own sign-in, there's a second—different—consent experience the first time the user signs in.</span></span>
>
><span data-ttu-id="4bb35-181">Pour l’instant, les autorisations Azure AD associées à toutes les fonctionnalités à l’intérieur d’une application Teams (bot, onglet, connecteur ou extension de messagerie) sont entièrement distinctes des autorisations d’équipe répertoriées ici.</span><span class="sxs-lookup"><span data-stu-id="4bb35-181">Currently, the Azure AD permissions associated with any of the capabilities inside a Teams app (bot, tab, connector, or messaging extension) are completely separate from the Teams permissions listed here.</span></span>

## <a name="tabs"></a><span data-ttu-id="4bb35-182">Onglets</span><span class="sxs-lookup"><span data-stu-id="4bb35-182">Tabs</span></span>

<span data-ttu-id="4bb35-183">Un onglet est un site Web qui s’exécute dans Teams.</span><span class="sxs-lookup"><span data-stu-id="4bb35-183">A tab is a website running inside Teams.</span></span>

### <a name="required-permissions"></a><span data-ttu-id="4bb35-184">Autorisations requises</span><span class="sxs-lookup"><span data-stu-id="4bb35-184">Required permissions</span></span>

<span data-ttu-id="4bb35-185">SEND_AND_RECEIVE_WEB_DATA</span><span class="sxs-lookup"><span data-stu-id="4bb35-185">SEND_AND_RECEIVE_WEB_DATA</span></span>

### <a name="optional-permissions"></a><span data-ttu-id="4bb35-186">Autorisations facultatives</span><span class="sxs-lookup"><span data-stu-id="4bb35-186">Optional permissions</span></span>

<span data-ttu-id="4bb35-187">Aucun (actuellement)</span><span class="sxs-lookup"><span data-stu-id="4bb35-187">None (currently)</span></span>

### <a name="considerations"></a><span data-ttu-id="4bb35-188">Inconvénients</span><span class="sxs-lookup"><span data-stu-id="4bb35-188">Considerations</span></span>

- <span data-ttu-id="4bb35-189">Le profil de risque d’un onglet est presque identique au même site Web exécuté dans un onglet de navigateur.</span><span class="sxs-lookup"><span data-stu-id="4bb35-189">The risk profile for a tab is almost identical to that same website running in a browser tab.</span></span> 

- <span data-ttu-id="4bb35-190">Un objet Tab obtient également le contexte dans lequel il est en cours d’exécution, y compris le nom de connexion et le nom d’utilisateur principal de l’utilisateur actuel, l’ID d’objet Azure AD pour l’utilisateur actuel, l’ID du groupe Office 365 dans lequel il se trouve (s’il s’agit d’une équipe), l’ID de locataire et les paramètres régionaux actuels de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="4bb35-190">A tab also gets the context in which it's running, including the sign-in name and UPN of the current user, the Azure AD Object ID for the current user, the ID of the Office 365 Group in which it resides (if it's a team), the tenant ID, and the current locale of the user.</span></span> <span data-ttu-id="4bb35-191">Toutefois, pour mapper ces ID aux informations d’un utilisateur, l’onglet doit permettre à l’utilisateur de se connecter à Azure AD.</span><span class="sxs-lookup"><span data-stu-id="4bb35-191">However, to map these IDs to a user's information, the tab would have to make the user sign in to Azure AD.</span></span>

## <a name="connectors"></a><span data-ttu-id="4bb35-192">Connecteurs</span><span class="sxs-lookup"><span data-stu-id="4bb35-192">Connectors</span></span>

<span data-ttu-id="4bb35-193">Un connecteur publie des messages vers un canal lorsque des événements dans un système externe se produisent.</span><span class="sxs-lookup"><span data-stu-id="4bb35-193">A connector posts messages to a channel when events in an external system occur.</span></span>

### <a name="required-permissions"></a><span data-ttu-id="4bb35-194">Autorisations requises</span><span class="sxs-lookup"><span data-stu-id="4bb35-194">Required permissions</span></span>

<span data-ttu-id="4bb35-195">POST_MESSAGE_CHANNEL</span><span class="sxs-lookup"><span data-stu-id="4bb35-195">POST_MESSAGE_CHANNEL</span></span>

### <a name="optional-permissions"></a><span data-ttu-id="4bb35-196">Autorisations facultatives</span><span class="sxs-lookup"><span data-stu-id="4bb35-196">Optional permissions</span></span>

<span data-ttu-id="4bb35-197">REPLYTO_CONNECTOR_MESSAGE.</span><span class="sxs-lookup"><span data-stu-id="4bb35-197">REPLYTO_CONNECTOR_MESSAGE.</span></span> <span data-ttu-id="4bb35-198">Certains connecteurs prennent en charge des messages interactifs, ce qui permet aux utilisateurs de publier des réponses ciblées au message du connecteur, par exemple en ajoutant une réponse à un problème de GitHub ou en ajoutant une date à une carte Trello.</span><span class="sxs-lookup"><span data-stu-id="4bb35-198">Certain connectors support actionable messages, which allow users to post targeted replies to the connector message, for example by adding a response to a GitHub issue or adding a date to a Trello card.</span></span>

### <a name="considerations"></a><span data-ttu-id="4bb35-199">Inconvénients</span><span class="sxs-lookup"><span data-stu-id="4bb35-199">Considerations</span></span>

- <span data-ttu-id="4bb35-200">Le système qui publie des messages de connecteur ne sait pas à qui il envoie des messages ou qui les reçoit : aucune information sur le destinataire n’est divulguée.</span><span class="sxs-lookup"><span data-stu-id="4bb35-200">The system that posts connector messages doesn't know who it's posting to or who receives the messages: no information about the recipient is disclosed.</span></span> <span data-ttu-id="4bb35-201">(Microsoft est le destinataire réel, et non le locataire ; Microsoft effectue le billet réel sur le canal.)</span><span class="sxs-lookup"><span data-stu-id="4bb35-201">(Microsoft is the actual recipient, not the tenant; Microsoft does the actual post to the channel.)</span></span>

- <span data-ttu-id="4bb35-202">Aucune donnée ne quitte le réseau d’entreprise lorsque des messages de connecteur sont publiés dans un canal.</span><span class="sxs-lookup"><span data-stu-id="4bb35-202">No data leaves the corporate network when connector messages are posted to a channel.</span></span>

- <span data-ttu-id="4bb35-203">Les connecteurs qui prennent en charge les messages interactifs (autorisation REPLYTO_CONNECTOR_MESSAGE) ne voient pas les informations d’adresse IP et de renvoi. ces informations sont envoyées à Microsoft, puis routées aux points de terminaison HTTP déjà enregistrés auprès de Microsoft dans le portail de connecteurs.</span><span class="sxs-lookup"><span data-stu-id="4bb35-203">Connectors that support actionable messages (REPLYTO_CONNECTOR_MESSAGE permission) also don't see IP address and referrer information; this information is sent to Microsoft and then routed to HTTP endpoints that were previously registered with Microsoft in the Connectors portal.</span></span>

- <span data-ttu-id="4bb35-204">Chaque fois qu’un connecteur est configuré pour un canal, une URL unique est créée pour cette instance de connecteur.</span><span class="sxs-lookup"><span data-stu-id="4bb35-204">Each time a connector is configured for a channel, a unique URL for that connector instance is created.</span></span> <span data-ttu-id="4bb35-205">Si cette instance de connecteur est supprimée, l’URL ne peut plus être utilisée.</span><span class="sxs-lookup"><span data-stu-id="4bb35-205">If that connector instance is deleted, the URL can no longer be used.</span></span>

- <span data-ttu-id="4bb35-206">Les messages de connexion ne peuvent pas contenir de pièces jointes.</span><span class="sxs-lookup"><span data-stu-id="4bb35-206">Connector messages can't contain file attachments.</span></span>

- <span data-ttu-id="4bb35-207">L’URL d’instance du connecteur doit être considérée comme secrète/confidentiel : toute personne disposant de cette URL peut la publier dans celle-ci, comme une adresse de messagerie.</span><span class="sxs-lookup"><span data-stu-id="4bb35-207">The connector instance URL should be treated as secret/confidential: anyone who has that URL can post to it, like an email address.</span></span> <span data-ttu-id="4bb35-208">Par conséquent, il existe du courrier indésirable ou des liens vers des sites de hameçonnage ou de Malware.</span><span class="sxs-lookup"><span data-stu-id="4bb35-208">Therefore, there's some risk of spam or links to phishing or malware sites.</span></span> <span data-ttu-id="4bb35-209">Si tel est le cas, les propriétaires d’équipe peuvent supprimer l’instance de connecteur.</span><span class="sxs-lookup"><span data-stu-id="4bb35-209">If that were to happen, team owners can delete the connector instance.</span></span>

- <span data-ttu-id="4bb35-210">Si le service qui envoie des messages de connecteur a été compromis et qu’ils commencent à envoyer des courriers indésirables/de hameçonnage/malveillants, un administrateur client peut empêcher la création d’instances de connecteur et Microsoft peut les bloquer de manière centralisée.</span><span class="sxs-lookup"><span data-stu-id="4bb35-210">If the service that sends connector messages were to become compromised and start sending spam/phishing/malware links, a tenant administrator can prevent new connector instances from being created and Microsoft can block them centrally.</span></span>

> [!NOTE]
> <span data-ttu-id="4bb35-211">Il n’est pas possible actuellement de savoir quels connecteurs prennent en charge les messages exploitables (autorisation REPLYTO_CONNECTOR_MESSAGE).</span><span class="sxs-lookup"><span data-stu-id="4bb35-211">It's not currently possible to know which connectors support actionable messages (REPLYTO_CONNECTOR_MESSAGE permission).</span></span>

## <a name="outgoing-webhooks"></a><span data-ttu-id="4bb35-212">Raccordements Web sortants</span><span class="sxs-lookup"><span data-stu-id="4bb35-212">Outgoing webhooks</span></span>

<span data-ttu-id="4bb35-213">Les *webhook sortants* sont créés à la volée par les propriétaires d’équipe ou les membres de l’équipe.</span><span class="sxs-lookup"><span data-stu-id="4bb35-213">*Outgoing webhooks* are created on the fly by team owners or team members.</span></span> <span data-ttu-id="4bb35-214">Elles ne sont pas des fonctionnalités des applications Teams. ces informations sont disponibles à des fins d’exhaustivité.</span><span class="sxs-lookup"><span data-stu-id="4bb35-214">They aren't capabilities of Teams apps; this information is included for completeness.</span></span>

### <a name="required-permissions"></a><span data-ttu-id="4bb35-215">Autorisations requises</span><span class="sxs-lookup"><span data-stu-id="4bb35-215">Required permissions</span></span>

<span data-ttu-id="4bb35-216">RECEIVE_MESSAGE REPLYTO_MESSAGE.</span><span class="sxs-lookup"><span data-stu-id="4bb35-216">RECEIVE_MESSAGE, REPLYTO_MESSAGE.</span></span> <span data-ttu-id="4bb35-217">Peut recevoir des messages des utilisateurs et y répondre.</span><span class="sxs-lookup"><span data-stu-id="4bb35-217">Can receive messages from users and reply to them.</span></span>

### <a name="optional-permissions"></a><span data-ttu-id="4bb35-218">Autorisations facultatives</span><span class="sxs-lookup"><span data-stu-id="4bb35-218">Optional permissions</span></span>

<span data-ttu-id="4bb35-219">Aucun</span><span class="sxs-lookup"><span data-stu-id="4bb35-219">None</span></span>

### <a name="considerations"></a><span data-ttu-id="4bb35-220">Inconvénients</span><span class="sxs-lookup"><span data-stu-id="4bb35-220">Considerations</span></span>

- <span data-ttu-id="4bb35-221">Les raccordements Web sortants sont similaires aux robots, mais ils ont moins de privilèges.</span><span class="sxs-lookup"><span data-stu-id="4bb35-221">Outgoing webhooks are similar to bots but have fewer privileges.</span></span> <span data-ttu-id="4bb35-222">Elles doivent être mentionnées explicitement, comme les robots.</span><span class="sxs-lookup"><span data-stu-id="4bb35-222">They must be explicitly mentioned, just like bots.</span></span>

- <span data-ttu-id="4bb35-223">Lors de l’enregistrement d’un webhook sortant, une clé secrète est générée, ce qui permet au webhook sortant de vérifier que l’expéditeur est Microsoft teams plutôt qu’à un attaquant malveillant.</span><span class="sxs-lookup"><span data-stu-id="4bb35-223">When an outgoing webhook is registered, a secret is generated, which allows the outgoing webhook to verify that the sender is Microsoft Teams as opposed to a malicious attacker.</span></span> <span data-ttu-id="4bb35-224">Ce secret doit rester secret ; toute personne qui y a accès peut emprunter l’identité de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="4bb35-224">This secret should remain a secret; anyone who has access to it can impersonate Microsoft Teams.</span></span> <span data-ttu-id="4bb35-225">Si la clé secrète est compromise, le webhook sortant peut être supprimé, recréé et un nouveau secret est généré.</span><span class="sxs-lookup"><span data-stu-id="4bb35-225">If the secret is compromised, the outgoing webhook can be deleted and re-created, and a new secret will be generated.</span></span>

- <span data-ttu-id="4bb35-226">Même s’il est possible de créer un webhook sortant qui ne valide pas le secret, nous vous recommandons de le faire contre.</span><span class="sxs-lookup"><span data-stu-id="4bb35-226">Although it's possible to create an outgoing webhook that doesn't validate the secret, we recommend against it.</span></span>

- <span data-ttu-id="4bb35-227">Hormis le fait de recevoir et de répondre à des messages, les Cross Hook sortantes ne peuvent pas faire beaucoup : les utilisateurs ne peuvent pas envoyer de messages de manière proactive, ils ne peuvent pas envoyer ou recevoir des fichiers, ils ne peuvent pas effectuer d’autres opérations que les robots peuvent effectuer, sauf recevoir des messages et y répondre.</span><span class="sxs-lookup"><span data-stu-id="4bb35-227">Other than receiving and replying to messages, outgoing webhooks can't do much: they can't proactively send messages, they can't send or receive files, they can't do anything else that bots can do except receive and reply to messages.</span></span>
