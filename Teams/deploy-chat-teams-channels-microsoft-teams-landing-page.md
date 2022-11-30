---
title: Chat, équipes, canaux et applications dans Microsoft Teams
ms.reviewer: ''
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
ms.subservice: teams-chat
audience: admin
search.appverid: MET150
description: Contient des instructions pas à pas pour configurer les paramètres Teams pour les conversations, les équipes, les applications et les canaux dans Microsoft Teams.
ms.localizationpriority: high
ms.collection:
- M365-collaboration
- m365initiative-deployteams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.quickstartteamsadmin
- intro-get-started
- seo-marvel-apr2020
- seo-marvel-may2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 10063b2b6c8c0f92de8d949578133b2577ff6d9f
ms.sourcegitcommit: ed7d3b12d4bfe48863de873360c2ae90bbb15530
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/30/2022
ms.locfileid: "69194915"
---
# <a name="chat-teams-channels--apps-in-microsoft-teams"></a>Chat, équipes, canaux et applications dans Microsoft Teams

Teams provides a great out-of-the-box collaboration experience for your organization, and most organizations find that the default settings work for them. This article helps you decide whether to change any of the default settings, based on your organization's profile and business requirements, then it walks you through each change. We've split the settings into two groups, starting with the core set of [changes you're more likely to make](#core-deployment-decisions). The second group includes the [additional settings](#additional-deployment-decisions) you may want to configure, based on your organization's needs.

Pour commencer, regardez notre courte vidéo sur les conversations, équipes et canaux Teams (4:30 minutes) :

<br/>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE476Yj?autoplay=false]

You can use [Advisor for Teams](use-advisor-teams-roll-out.md) to help you roll out Microsoft Teams. Advisor for Teams walks you through your Teams rollout. It assesses your Microsoft 365 environment and identifies the most common configurations that you may need to update or modify before you can successfully roll out Teams.

> [!TIP]
> Nous vous recommandons d’inclure nos applications proposées (par exemple, le Planificateur) dans votre déploiement initial concernant Teams. Ajoutez d’autres [applications Teams](deploy-apps-microsoft-teams-landing-page.md) à mesure que vous pilotez l’adoption de Teams.

 > [!Note]
 > Pour plus d’informations sur les fonctionnalités Teams sur différentes plateformes, consultez [Fonctionnalités Teams par plateforme](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).

## <a name="chat-deployment-prerequisites"></a>Conditions préalables pour le déploiement de Chat

Before you roll out Teams across your organization, take time to confirm that your environment is ready for Teams. Review [Prepare your organization's network for Teams](prepare-network.md) and make any required changes to your environment.

|Posez-vous la question|Action |
|------------|-------|
|Mon organisation est-elle prête à mettre en place Teams ?|Pour répondre à cette question, voir : <ul><li>[Préparer le réseau de votre organisation pour Microsoft Teams](prepare-network.md)</li><li>[URL et plages d’adresses IP](office-365-urls-ip-address-ranges.md)</li><li>[Planifier les groupes Microsoft 365 lors de la création d'équipes](plan-office-365-groups.md)</li></ul>|

## <a name="core-deployment-decisions"></a>Décisions liées au déploiement Core

Voici les paramètres de chat, d’équipe et de canaux que la plupart des organisations veulent modifier (si les paramètres par défaut ne fonctionnent pas pour elles).

### <a name="teams-administrators"></a>Administrateurs Teams

Teams provides a set of custom administrator roles that can be used to manage Teams for your organization. The roles provide various capabilities to administrators.

| Posez-vous la question | Action |
|--------------|--------|
|Qui va assumer le rôle d’Administrateur des Communications Teams ?|Pour en savoir plus sur les rôles d’administrateur Teams, voir [Utiliser les rôles d’administrateur Microsoft Teams pour gérer les équipes](using-admin-roles.md).|
|Qui va assumer le rôle d’ingénieur support des Communications Teams ?|Pour attribuer des rôles d’administrateur, voir [Attribuer des rôles administrateur et non administrateur aux utilisateurs avec Active Directory](/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal).|
|Qui va assumer le rôle de spécialiste d’assistance des Communications Teams ?||

### <a name="teams-owners-and-members"></a>Propriétaires d’équipes et membres

In addition to administrator roles, Teams lets you assign owner and member user roles, and selectively give them moderator capabilities (if moderation has been set up) to control who can perform certain actions within a channel. Moderation allows you to control who can start new posts in a channel, add and remove team members as moderators, and control whether team members can reply to existing channel messages.

|Posez-vous la question|Action |
|------------|-------|
|Qui doit être affecté à chaque rôle ? | Pour comparer les fonctionnalités de chaque rôle, voir [attribuer des propriétaires d’équipes, des modérateurs et des membres dans Microsoft Teams](assign-roles-permissions.md).
|Comment affecter un rôle d’utilisateur ? | Pour attribuer ou modifier un rôle, voir [attribuer un rôle d’utilisateur](assign-roles-permissions.md).
|Ai-je besoin de contrôler qui peut publier et répondre à un canal ? | Pour configurer la modération, voir[Configurer et gérer la modération des canaux dans Microsoft Teams](manage-channel-moderation-in-teams.md).

### <a name="messaging-policies"></a>Stratégies de messagerie

Messaging policies control which chat and channel messaging features are available to users in Teams. For example, who can edit and delete sent messages, who can use chat, who can use memes in conversations, and more. By default, users are assigned the global messaging policy and all features are **On**. You can use the default global policy or create one or more custom messaging policies for people in your organization.

|Posez-vous la question|Action |
|------------|-------|
|Est-ce que je vais personnaliser la stratégie générale de messagerie ?|Pour plus d’informations sur l’utilisation du centre d’administration de Microsoft Teams pour modifier la stratégie générale de messagerie ou ajouter une nouvelle stratégie, voir [Gérer les stratégies de messagerie dans Teams](messaging-policies-in-teams.md).|
|Est-ce que j’ai besoin de plusieurs stratégies de messagerie ?|Pour créer et attribuer une stratégie de messagerie dans PowerShell, voir [Exemple de script PowerShell : créer et attribuer une stratégie de messagerie](scripts/powershell-script-teams-messaging-policy-edu.md).|
|Comment déterminer quelles stratégies de réunion sont appliqués à quels groupes d’utilisateurs?|Pour en savoir plus sur les applets de commande CsTeamsMessagingPolicy, voir [Paramétrage de CsTeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy).|

### <a name="external-access"></a>Accès externe

External access (federation) lets your users communicate with people outside of your organization via chat. By turning this on and adding domains to the allowed list, your users can communicate with users in other domains and organizations. External access is turned on by default.

|Posez-vous la question|Action |
|------------|-------|
|<ul><li>Vais-je désactiver les réunions externes et les conversations pour mon organisation ?</li><li>Si l’accès est activé, est-ce que je vais limiter les domaines avec lesquels mon organisation peut communiquer ?</li></ul> |<br>Pour activer ou désactiver la réunion externe et la conversation, consultez [Gérer les réunions externes et des conversations](manage-external-access.md).|

### <a name="guest-access"></a>Accès invité

Guest access in Teams lets individuals outside your organization access teams and channels. You can use the guest access settings to control which features guests can or can't use. Guest access is turned on by default. To learn more, see [Guest access in Teams](./guest-access.md).

> [!NOTE]
> Pour plus d’informations sur l’accès externe et l’accès invité, consultez : [Communiquer avec les utilisateurs d’autres organisations dans Microsoft Teams](communicate-with-users-from-other-organizations.md)

|Posez-vous la question|Action |
|------------|-------|
|Vais-je désactiver l’accès invité pour mon organisation ?|Pour activer ou désactiver l’accès invité, consultez [Activer ou désactiver l’accès invité dans Teams](set-up-guests.md).|
|Si activé, est-ce que je vais personnaliser les fonctionnalités disponibles pour les invités dans mon organisation ?|Pour personnaliser la disponibilité des fonctionnalités d’accès invité, voir [Autoriser l’accès invité dans Teams](teams-dependencies.md).|

### <a name="private-channels"></a>Canaux privés

Les canaux privés permettent à un sous-ensemble de membres de l’équipe de collaborer dans un espace privé invisible et inaccessible pour les autres membres de l’équipe. Tous les utilisateurs, notamment les invités, peuvent être ajoutés en tant que membre d’un canal privé, dès lors qu’ils sont déjà membres de l’équipe.

|Posez-vous la question|Action |
|------------|-------|
|Dois-je autoriser les propriétaires et membres d’équipe à créer des canaux privés ?|Pour définir une stratégie de canaux privés pour votre organisation, consultez [Gérer les stratégies de canal dans Microsoft Teams](teams-policies.md)|

### <a name="shared-channels"></a>Canaux partagés

Les canaux partagés vous permettent d’ajouter à un canal des personnes qui ne sont pas membres d’une équipe. Cela inclut les personnes extérieures à votre organisation. Les canaux partagés offrent des avantages par rapport à l’accès invité, car les personnes extérieures à votre organisation n’ont pas besoin d’un compte invité dans votre annuaire.

|Posez-vous la question|Action |
|------------|-------|
|Quand utiliser les canaux partagés et l’accès invité ?|Consultez [Canaux partagés dans Microsoft Teams](shared-channels.md).|
|<ul><li>Vais-je autoriser les propriétaires d’équipe à créer des canaux partagés ?</li><li>Vais-je autoriser les propriétaires d’équipe à partager des canaux avec des personnes extérieures à l’organisation ?</li><li>Vais-je autoriser les utilisateurs à participer à des canaux partagés qui se trouveraient en dehors de l’organisation ?</li></ul> |<br>Pour définir une stratégie de canaux partagés pour votre organisation, consultez [Gérer les stratégies de canal dans Microsoft Teams](teams-policies.md).|

### <a name="teams-settings"></a>Paramètres de Teams

Teams settings let you set up your teams for features such as email integration, cloud storage options, organization tab, meeting room device setup, and search scope. When you make changes to these settings, they apply to all the teams in your organization. To learn more, see [Teams settings](enable-features-office-365.md#teams-settings).

|Posez-vous la question|Action |
|------------|-------|
|Est-ce que je vais personnaliser les paramètres Teams pour mon organisation ? | Pour en savoir plus sur les paramètres Teams et comment les personnaliser, voir [Paramètres Teams](enable-features-office-365.md#teams-settings).|

### <a name="teams-clients"></a>Clients Teams

Teams supports a number of clients from web to desktop to mobile, and the default configuration lets users choose whichever clients they want. To learn more, see [Get clients for Teams](get-clients.md).

|Posez-vous la question|Action |
|------------|-------|
|Est-ce que je vais personnaliser la disponibilité des clients Teams pour mon organisation ?|Vérifiez la [Configuration matérielle requise pour l’application Microsoft Teams](hardware-requirements-for-the-teams-app.md). |
|Est-ce que je vais personnaliser les paramètres client Teams pour mon organisation ?|Découvrez comment [installer Teams à l’aide de MSI](msi-deployment.md).|

### <a name="teams-usage-reporting"></a>Rapports d’utilisation Teams

The Global Admin, Teams Service Admin, and Reports Readers roles can view Teams usage reports. To learn more, see the [Microsoft 365 usage analytics](/microsoft-365/admin/usage-analytics/usage-analytics).

|Posez-vous la question|Action |
|------------|-------|
|<br> Qui a besoin de voir les rapports d’utilisation Teams et est-ce qu’ils ont le rôle approprié pour les afficher ? |<ul><li>Si l’utilisateur n’est pas un administrateur, [attribuer le rôle de lecteur de rapports](teams-activity-reports.md#reports-reader-role).</li><li>Voir [Rôles et autorisations](/azure/active-directory/users-groups-roles/directory-assign-admin-roles) et [Afficher et attribuer des rôles](/azure/active-directory/users-groups-roles/directory-manage-roles-portal) pour découvrir comment attribuer des rôles d’administrateur dans Azure Active Directory.|

### <a name="teams-default-apps"></a>Applications Teams par défaut

Teams provides a number of first-party (Microsoft provided) and third-party apps to engage users, support productivity, and integrate commonly used business services into Teams. Get apps from the Teams Store. Apps are turned on by default in Teams.

Pour en savoir plus sur le déploiement et la gestion des applications dans Teams, consultez nos conseils détaillés sur [la gestion des](deploy-apps-microsoft-teams-landing-page.md) applications.

## <a name="additional-deployment-decisions"></a>Décisions de déploiement supplémentaires

Vous souhaiterez peut-être modifier ces paramètres en fonction des besoins et de la configuration de votre organisation.

### <a name="teams-licensing"></a>Licences Teams

Teams est fourni dans le cadre de nombreuses licences Microsoft 365.

|Posez-vous la question|Action |
|------------|-------|
|Mes utilisateurs ont-ils les licences dont ils ont besoin pour pouvoir utiliser toutes les fonctionnalités Teams que je souhaite mettre en place ? | Pour en savoir plus sur les conditions de licence, consultez [Description du service Microsoft Teams](/office365/servicedescriptions/teams-service-description).|

### <a name="exchange-and-sharepoint-interoperability"></a>Interopérabilité Exchange et SharePoint

For the full Teams experience, every user should be enabled for Exchange, SharePoint, and Microsoft 365 group creation. The following articles outline information related to Exchange mailboxes hosted in various environments, how Exchange and Teams interact, and similar considerations for SharePoint and OneDrive.

|Posez-vous la question|Action |
|------------|-------|
| Est-ce que je pourrai déployer les fonctionnalités Teams dont j’ai besoin avec les déploiements Exchange et SharePoint actuels ? |Pour plus d’informations sur Exchange et SharePoint dans Teams, voir :<ul><li> [Interaction entre Exchange et Microsoft Teams](exchange-teams-interact.md)</li><li>[Interaction entre SharePoint Online et OneDrive avec Teams](sharepoint-onedrive-interact.md)|

### <a name="teams-limits-and-specifications"></a>Spécifications et limites de Teams

Lorsque vous planifiez un déploiement d’entreprise avec Teams, vous devez tenir compte des limitations et spécifications pertinentes, telles que le nombre maximal de membres dans une équipe, le nombre maximal d’équipes qu’un utilisateur peut créer et ainsi de suite.

|Posez-vous la question|Action |
|------------|-------|
| Quelles sont les limites que je risque de dépasser avec mon déploiement Teams ? | Pour en savoir plus, voir [Limites et spécifications pour Teams](limits-specifications-teams.md). |

### <a name="urls-and-ports"></a>Ports et URL

Organizations that maintain fine-grained control of their internet traffic should read [URLs and IP address ranges](/office365/enterprise/urls-and-ip-address-ranges) for an up-to-date list of the URLs, IP addresses, ports, and protocols that must be correctly configured for Teams. Microsoft is continuously improving the Microsoft 365 services and adding new functionality, which means the required ports, URLs, and IP addresses may change over time. We recommend that you subscribe via RSS to receive notifications when this information is updated or changed. At a minimum, make sure you've opened the ports listed above in [Chat deployment prerequisites](#chat-deployment-prerequisites).

|Posez-vous la question|Action |
|------------|-------|
| Est-ce que j’ai besoin de règles d’accès internet pour permettre aux utilisateurs d’utiliser Teams ou est-ce suffisant d’ouvrir le minimum de ports requis ? | Pour plus d’informations, consultez [URL et plages d’adresses IP ](office-365-urls-ip-address-ranges.md).|

### <a name="governance-naming-conventions-who-can-create-teams"></a>Gouvernance (conventions de création des noms, qui peut créer des équipes)

Your organization might require that you implement controls on how teams are named and classified, who can create teams, and team expiration, retention, and archiving. This is called governance. You can use Azure Active Directory (Azure AD) to configure each of these areas.

| Posez-vous la question | Action |
|--------------|--------|
|Est-ce que je vais devoir implémenter des contrôles sur qui peut créer des équipes ?| Voir [Planifiez la gouvernance dans Teams](plan-teams-governance.md).|
|Est-ce que je vais devoir implémenter des contrôles sur comment on peut nommer des équipes ?|Lisez [Appliquer une stratégie d’attribution de noms pour les groupes Microsoft 365 dans Azure AD](/azure/active-directory/users-groups-roles/groups-naming-policy).|

### <a name="teams-application-policy-side-rail-control"></a>Stratégie d’application Teams (contrôle réglette latérale)

A pinned app shows up in the side rail in Teams. By creating Teams application policies, you can preconfigure sets of pinned Teams apps to personalize Teams for select groups of users. By default, the **Allow external apps in Microsoft Teams** setting is turned on.

| Posez-vous la question | Action |
|--------------|--------|
|Dois-je créer des ensembles préconfigurés d’applications Teams épinglées ? | Voir [Paramètres d'administration pour les applications dans Microsoft Teams](admin-settings.md).|
|Comment est-ce que je vais choisir les groupes qui vont recevoir ces blocs d’applications ?|Voir [Autorisations d’applications Microsoft Teams et points à prendre en compte](app-permissions.md).|

### <a name="archiving-and-compliance"></a>Archivage et conformité

Your organization might require that you implement controls on how teams are archived and the types of data that are held in certain types of teams. Read [Overview of security and compliance in Teams](security-compliance-overview.md) to learn which Teams settings are turned on by default.

| Posez-vous la question | Action |
|--------------|--------|
|Est-ce que je devrai configurer la rétention pour les équipes ?|Pour configurer des stratégies de rétention, voir [Établir des stratégies de rétention dans Teams](retention-policies.md).|
|Est-ce que je dois configurer l’archivage pour les équipes ?|Pour archiver ou restaurer une équipe, voir [Archiver ou restaurer une équipe](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7).|
|Est-ce que je dois configurer des paramètres de conformité additionnels ?|Pour plus d’informations sur la sécurité et la conformité, voir [Vue d’ensemble concernant le sécurité et la conformité dans Teams](security-compliance-overview.md).|

### <a name="conditional-access"></a>Accès conditionnel

Teams relies heavily on Exchange and SharePoint for core productivity scenarios, including meetings, calendars, interop chats, and file sharing. Conditional access policies that are set for these cloud apps apply to Teams when a user signs in directly to Teams, on any client. Conditional access policies that are set for the Teams cloud app control aspects such as whether users can access Teams services from certain networks.

| Posez-vous la question | Action |
|--------------|--------|
|<br>Est-ce que je devrai configurer l’accès conditionnel pour Teams ?|<ul><li>Pour comprendre comment fonctionnent les stratégies, voir [Comment fonctionnent les stratégies d’accès conditionnel pour Teams ?](security-compliance-overview.md#how-conditional-access-policies-work-for-teams)</li><li>Pour configurer l’authentification multifacteur (MFA) Multi-Factor Authentication pour Teams, voir :<ul><li>[Démarrage rapide : exiger l’authentification multifacteur MFA pour des applications spécifiques avec l’accès conditionnel Azure Active Directory](/azure/active-directory/conditional-access/app-based-mfa)</li><li>[Paramètres d’accès conditionnel Azure Active Directory : guide de référence](/azure/active-directory/conditional-access/technical-reference)</li></ul></ul>|

### <a name="education-edu"></a>Éducation (EDU)

Les professionnels de l’informatique travaillant dans le secteur de l’éducation peuvent tirer parti de Teams pour l’éducation, qui inclus un certain nombre de fonctionnalités adaptées pour répondre à des scénarios spécifiques à l’éducation pour les élèves et étudiants, les enseignants et en général pour la conduite des opérations administratives.

| Posez-vous la question | Action |
|--------------|--------|
|Est-ce que je vais utiliser des modèles Teams spécifiques à l’éducation ? |Pour en savoir plus sur Teams pour l’éducation, voir [FAQ sur la gouvernance Microsoft Éducation pour les administrateurs](plan-teams-governance-edu.md).|
|Est-ce que je vais déployer des recherches définies ?|Pour configurer Teams pour l’éducation, voir [Démarrage rapide : administrateurs de Teams pour l’éducation](teams-quick-start-edu.yml).|
|Est-ce que je vais intégrer Teams au service School Data Sync pour configurer des comptes utilisateur ?|[Administrateurs de ressources Teams pour l’éducation](resources-teams-edu.md)|

### <a name="government---gcc-considerations"></a>Secteur public : considérations « GCC »

Office 365 pour le secteur public : GCC (cloud de communauté pour le secteur public) répond aux exigences des professionnels de l’informatique qui procèdent au déploiement d’Office 365 auprès d’entités américaines au niveau fédéral, des états, des administrations locale, tribales ou territoriales ou autres entités qui traitent des données assujetties à la réglementation et aux exigences gouvernementales.

| Posez-vous la question | Action |
|--------------|--------|
| Devrai-je déployer Teams dans un environnement Office 365 dans le secteur public (GCC) ? | Pour les considérations relatives au déploiement, voir [Plan pour les déploiements de Office 365 pour le secteur public : déploiements GCC](plan-for-government-gcc.md).|

## <a name="next-steps"></a>Étapes suivantes

- [Favoriser l’adoption](adopt-microsoft-teams-landing-page.md) de chat, Teams, les canaux et les applications.
- Inclure des applications proposées (par exemple, le Planificateur) dans votre déploiement initial concernant Teams. Ajoutez une autre [application Teams](deploy-apps-microsoft-teams-landing-page.md) à mesure que vous pilotez l’adoption de Teams.
- [Mettre en place des réunions et des conférences](deploy-meetings-microsoft-teams-landing-page.md)
- [Mettre en place les services audio dans le nuage](cloud-voice-landing-page.md)
