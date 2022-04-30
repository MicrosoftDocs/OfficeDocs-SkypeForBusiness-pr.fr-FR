---
title: Chat, équipes, canaux et applications dans Microsoft Teams
ms.reviewer: ''
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
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
appliesto:
- Microsoft Teams
- seo-marvel-apr2020
- seo-marvel-may2020
ms.openlocfilehash: a2d6ee4129128df8acf17906b0bc45140b57f6f4
ms.sourcegitcommit: d16fb01f752d186445893ea8e3b0d4450a4a0e67
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/29/2022
ms.locfileid: "65125499"
---
# <a name="chat-teams-channels--apps-in-microsoft-teams"></a>Chat, équipes, canaux et applications dans Microsoft Teams

Teams offre une expérience de collaboration prête à l’utilisation pour votre organisation, et la plupart des organisations trouvent que les paramètres par défaut leur conviennent. Cet article vous permet de décider si vous voulez modifier les paramètres par défaut en fonction du profil de votre organisation et vos exigences professionnelles, puis il vous guide pour chaque modification. Nous avons fractionné les paramètres en deux groupes, en commençant par l’ensemble des [modifications principales que vous êtes le plus susceptible d’apporter](#core-deployment-decisions). Le deuxième groupe inclut les [paramètres supplémentaires](#additional-deployment-decisions) vous pouvez configurer en fonction des besoins de votre organisation.

Pour commencer, regardez notre courte vidéo sur les conversations, équipes et canaux Teams (4:30 minutes) :

<br/>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE476Yj]

Vous pouvez utiliser [Advisor pour Teams](use-advisor-teams-roll-out.md) pour vous aider à déployer Microsoft Teams. Advisor for Teams vous guide tout au long de votre déploiement Teams. Il évalue votre environnement Microsoft 365 et identifie les configurations les plus courantes que vous devrez peut-être mettre à jour ou modifier avant de pouvoir déployer Teams.

> [!TIP]
> Nous vous recommandons d’inclure nos applications proposées (par exemple, le Planificateur) dans votre déploiement initial concernant Teams. Ajoutez d’autres [applications, bots et connecteurs](deploy-apps-microsoft-teams-landing-page.md) pour favoriser l’adoption des services Teams.

 > [!Note]
 > Pour plus d’informations sur les fonctionnalités Teams sur différentes plateformes, consultez [Fonctionnalités Teams par plateforme](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).

## <a name="chat-deployment-prerequisites"></a>Conditions préalables pour le déploiement de Chat

Avant de déployer Teams dans votre organisation, prenez le temps de confirmer que votre environnement est prêt pour Teams. Consultez la section [Préparer le réseau de votre organisation pour les équipes](prepare-network.md) et apportez les modifications nécessaires à votre environnement.

|Posez-vous la question|Action |
|------------|-------|
|Mon organisation est-elle prête à mettre en place Teams ?|Pour répondre à cette question, voir : <ul><li>[Préparer le réseau de votre organisation pour Microsoft Teams](prepare-network.md)</li><li>[URL et plages d’adresses IP](office-365-urls-ip-address-ranges.md)</li><li>[Planifier les groupes Microsoft 365 lors de la création d'équipes](plan-office-365-groups.md)</li></ul>|

## <a name="core-deployment-decisions"></a>Décisions liées au déploiement Core

Voici les paramètres de chat, d’équipe et de canaux que la plupart des organisations veulent modifier (si les paramètres par défaut ne fonctionnent pas pour elles).

### <a name="teams-administrators"></a>Administrateurs Teams

Teams fournit un ensemble de rôles d’administrateur personnalisé qui peuvent servir à gérer des équipes pour votre organisation. Ces rôles fournissent plusieurs fonctionnalités aux administrateurs.

| Posez-vous la question | Action |
|--------------|--------|
|Qui va assumer le rôle d’Administrateur des Communications Teams ?|Pour en savoir plus sur les rôles d’administrateur Teams, voir [Utiliser les rôles d’administrateur Microsoft Teams pour gérer les équipes](using-admin-roles.md).|
|Qui va assumer le rôle d’ingénieur support des Communications Teams ?|Pour attribuer des rôles d’administrateur, voir [Attribuer des rôles administrateur et non administrateur aux utilisateurs avec Active Directory](/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal).|
|Qui va assumer le rôle de spécialiste d’assistance des Communications Teams ?||

### <a name="teams-owners-and-members"></a>Propriétaires d’équipes et membres

En plus des rôles d’administrateur, Teams vous permet d’attribuer des rôles propriétaire et utilisateur, et de les attribuer de façon sélective (si la modération est configurée) pour contrôler qui peut effectuer certaines actions au sein d’un canal. La modération vous permet de contrôler qui peut commencer de nouvelles publications dans un canal, d’ajouter et de supprimer des membres de l’équipe comme modérateurs, et de contrôler si les membres d’une équipe peuvent répondre aux messages de canaux existants.

|Posez-vous la question|Action |
|------------|-------|
|Qui doit être affecté à chaque rôle ? | Pour comparer les fonctionnalités de chaque rôle, voir [attribuer des propriétaires d’équipes, des modérateurs et des membres dans Microsoft Teams](assign-roles-permissions.md).
|Comment affecter un rôle d’utilisateur ? | Pour attribuer ou modifier un rôle, voir [attribuer un rôle d’utilisateur](assign-roles-permissions.md#assign-a-user-role).
|Ai-je besoin de contrôler qui peut publier et répondre à un canal ? | Pour configurer la modération, voir[Configurer et gérer la modération des canaux dans Microsoft Teams](manage-channel-moderation-in-teams.md).

### <a name="messaging-policies"></a>Stratégies de messagerie

Les stratégies de messagerie contrôlent les fonctionnalités de conversation et de canal qui seront mis à disposition des utilisateurs dans Teams. Par exemple, qui peut modifier et supprimer des messages envoyés, qui peuvent utiliser le chat, qui peut utiliser des mèmes dans les conversations et bien plus encore. Par défaut, les stratégie de messagerie générales sont affectées aux utilisateurs et toutes les fonctionnalités sont **activées**. Vous pouvez utiliser la stratégie générale par défaut ou créer une ou plusieurs stratégies de réunion personnalisées pour certaines personnes qui hébergent des réunions dans votre organisation. 

|Posez-vous la question|Action |
|------------|-------|
|Est-ce que je vais personnaliser la stratégie générale de messagerie ?|Pour plus d’informations sur l’utilisation du centre d’administration de Microsoft Teams pour modifier la stratégie générale de messagerie ou ajouter une nouvelle stratégie, voir [Gérer les stratégies de messagerie dans Teams](messaging-policies-in-teams.md).|
|Est-ce que j’ai besoin de plusieurs stratégies de messagerie ?|Pour créer et attribuer une stratégie de messagerie dans PowerShell, voir [Exemple de script PowerShell : créer et attribuer une stratégie de messagerie](scripts/powershell-script-teams-messaging-policy-edu.md).|
|Comment déterminer quelles stratégies de réunion sont appliqués à quels groupes d’utilisateurs?|Pour en savoir plus sur les applets de commande CsTeamsMessagingPolicy, voir [Paramétrage de CsTeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy).|

### <a name="external-access"></a>Accès externe

L’accès externe (fédération) permet à vos utilisateurs de communiquer avec des personnes extérieures à votre organisation via une conversation. En activant cette option et en ajoutant des domaines à la liste autorisée, vos utilisateurs peuvent communiquer avec les utilisateurs d’autres domaines et organisations. L’accès externe est activé par défaut.

|Posez-vous la question|Action |
|------------|-------|
|<ul><li>Vais-je désactiver les réunions externes et les conversations pour mon organisation ?</li><li>Si l’accès est activé, est-ce que je vais limiter les domaines avec lesquels mon organisation peut communiquer ?</li></ul> |<br>Pour activer ou désactiver la réunion externe et la conversation, consultez [Gérer les réunions externes et des conversations](manage-external-access.md).|

### <a name="guest-access"></a>Accès invité

L’accès invité dans Teams permet à des personnes en dehors de votre organisation d’avoir accès aux équipes et canaux. Vous pouvez utiliser les paramètres d’accès invité pour contrôler les fonctionnalités que les invités peuvent ou ne peuvent pas utiliser. L’accès invité est désactivé par défaut. Pour plus d’informations, consultez [Accès invité dans Teams](./guest-access.md).

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

Les paramètres de Teams permettent de configurer les fonctionnalités pour vos équipes, comme par exemple l’intégration courrier, les options de stockage dans le nuage, l’onglet organisation, la configuration des salles de conférence et l’étendue des recherches. Lorsque vous apportez des modifications à ces paramètres, ils s’appliquent à toutes les équipes de votre organisation.Pour plus d’informations, consultez [Paramètres Teams](enable-features-office-365.md#teams-settings).

|Posez-vous la question|Action |
|------------|-------|
|Est-ce que je vais personnaliser les paramètres Teams pour mon organisation ? | Pour en savoir plus sur les paramètres Teams et comment les personnaliser, voir [Paramètres Teams](enable-features-office-365.md#teams-settings).|

### <a name="teams-clients"></a>Clients Teams

Teams prend en charge un nombre de clients, depuis le web ou au bureau ou en mobilité, et la configuration par défaut permet aux utilisateurs de choisir le client qu’ils veulent utiliser. Pour plus d’informations, consultez [Obtenir des clients pour Teams](get-clients.md).

|Posez-vous la question|Action |
|------------|-------|
|Est-ce que je vais personnaliser la disponibilité des clients Teams pour mon organisation ?|Vérifiez la [Configuration matérielle requise pour l’application Microsoft Teams](hardware-requirements-for-the-teams-app.md). |
|Est-ce que je vais personnaliser les paramètres client Teams pour mon organisation ?|Découvrez comment [installer Teams à l’aide de MSI](msi-deployment.md).|

### <a name="teams-usage-reporting"></a>Rapports d’utilisation Teams

L’administrateur général, l’administrateur de Service Teams et les lecteurs de rapports peuvent consulter les rapports d’utilisation Teams. Pour plus d’informations, consultez [Rapports analytiques d’utilisation de Microsoft 365](/microsoft-365/admin/usage-analytics/usage-analytics).

|Posez-vous la question|Action |
|------------|-------|
|<br> Qui a besoin de voir les rapports d’utilisation Teams et est-ce qu’ils ont le rôle approprié pour les afficher ? |<ul><li>Si l’utilisateur n’est pas un administrateur, [attribuer le rôle de lecteur de rapports](teams-activity-reports.md#reports-reader-role).</li><li>Voir [Rôles et autorisations](/azure/active-directory/users-groups-roles/directory-assign-admin-roles) et [Afficher et attribuer des rôles](/azure/active-directory/users-groups-roles/directory-manage-roles-portal) pour découvrir comment attribuer des rôles d’administrateur dans Azure Active Directory.|

### <a name="teams-default-apps"></a>Applications Teams par défaut 

Teams fournit un certain nombre d'applications premières (fournies par Microsoft) et d'applications tierces pour engager les utilisateurs, soutenir la productivité et intégrer les services métiers couramment utilisés dans Teams. Obtenez les applications à partir du Store Teams. Les applications sont activées par défaut dans Teams. 

Pour en savoir plus sur le déploiement et la gestion des applications dans Teams, consultez notre guide approfondi [Applications, robots et connecteurs](deploy-apps-microsoft-teams-landing-page.md).

## <a name="additional-deployment-decisions"></a>Décisions de déploiement supplémentaires

Vous souhaiterez peut-être modifier ces paramètres en fonction des besoins et de la configuration de votre organisation.

### <a name="teams-licensing"></a>Licences Teams

Teams est fourni dans le cadre de nombreuses licences Microsoft 365.

|Posez-vous la question|Action |
|------------|-------|
|Mes utilisateurs ont-ils les licences dont ils ont besoin pour pouvoir utiliser toutes les fonctionnalités Teams que je souhaite mettre en place ? | Pour en savoir plus sur les conditions de licence, consultez [Description du service Microsoft Teams](/office365/servicedescriptions/teams-service-description).|

### <a name="exchange-and-sharepoint-interoperability"></a>Interopérabilité Exchange et SharePoint

Pour profiter pleinement de Teams, chaque utilisateur doit être activé pour la création de groupes Exchange, SharePoint et Microsoft 365. Les articles suivants décrivent les informations relatives aux boîtes aux lettres Exchange hébergées dans différents environnements, la façon dont Exchange et Teams interagissent, ainsi que des considérations similaires pour SharePoint et OneDrive.

|Posez-vous la question|Action |
|------------|-------|
| Est-ce que je pourrai déployer les fonctionnalités Teams dont j’ai besoin avec les déploiements Exchange et SharePoint actuels ? |Pour plus d’informations sur Exchange et SharePoint dans Teams, voir :<ul><li> [Interaction entre Exchange et Microsoft Teams](exchange-teams-interact.md)</li><li>[Interaction entre SharePoint Online et OneDrive avec Teams](sharepoint-onedrive-interact.md)|

### <a name="teams-limits-and-specifications"></a>Spécifications et limites de Teams 

Lorsque vous planifiez un déploiement d’entreprise avec Teams, vous devez tenir compte des limitations et spécifications pertinentes, telles que le nombre maximal de membres dans une équipe, le nombre maximal d’équipes qu’un utilisateur peut créer et ainsi de suite.

|Posez-vous la question|Action |
|------------|-------|
| Quelles sont les limites que je risque de dépasser avec mon déploiement Teams ? | Pour en savoir plus, voir [Limites et spécifications pour Teams](limits-specifications-teams.md). |

### <a name="urls-and-ports"></a>Ports et URL

Les organisations qui conservent un contrôle précis de leur trafic Internet doivent lire [URL et plages d’adresses IP](/office365/enterprise/urls-and-ip-address-ranges) pour obtenir une liste à jour des URL, adresses IP, ports et protocoles qui doivent être correctement configurés pour Teams. Microsoft améliore en permanence les services Microsoft 365 et ajoute de nouvelles fonctionnalités, ce qui signifie que les ports, URL et adresses IP requis peuvent changer au fil du temps. Nous vous recommandons de vous abonner via RSS pour recevoir des notifications lorsque ces informations sont mises à jour ou modifiées. Au minimum, vérifiez que vous avez ouvert les ports répertoriés ci-dessus dans [Conditions préalables au déploiement de conversation](#chat-deployment-prerequisites).

|Posez-vous la question|Action |
|------------|-------|
| Est-ce que j’ai besoin de règles d’accès internet pour permettre aux utilisateurs d’utiliser Teams ou est-ce suffisant d’ouvrir le minimum de ports requis ? | Pour plus d’informations, consultez [URL et plages d’adresses IP ](office-365-urls-ip-address-ranges.md).|

### <a name="governance-naming-conventions-who-can-create-teams"></a>Gouvernance (conventions de création des noms, qui peut créer des équipes)

Votre organisation peut exiger l’implémentation de contrôles sur comment les équipes sont nommées et classifiées, qui peut créer des équipes et les règles d’expiration, de rétention et d’archivage des équipes. On appelle cela la « gouvernance ». Vous pouvez utiliser Azure Active Directory (Azure AD) pour configurer chacune de ces zones.


| Posez-vous la question | Action |
|--------------|--------|
|Est-ce que je vais devoir implémenter des contrôles sur qui peut créer des équipes ?| Voir [Planifiez la gouvernance dans Teams](plan-teams-governance.md).|
|Est-ce que je vais devoir implémenter des contrôles sur comment on peut nommer des équipes ?|Lisez [Appliquer une stratégie d’attribution de noms pour les groupes Microsoft 365 dans Azure AD](/azure/active-directory/users-groups-roles/groups-naming-policy).|

### <a name="teams-application-policy-side-rail-control"></a>Stratégie d’application Teams (contrôle réglette latérale)

Une application épinglée apparaît dans la réglette latérale dans Teams. En créant des stratégies d’application Teams, vous pouvez préconfigurer des ensembles d’applications épinglées Teams pour personnaliser Teams pour des groupes d’utilisateurs spécifiques. Par défaut, le paramètre **Autoriser les applications externes dans Microsoft Teams** est activé.

| Posez-vous la question | Action |
|--------------|--------|
|Dois-je créer des ensembles préconfigurés d’applications Teams épinglées ? | Voir [Paramètres d'administration pour les applications dans Microsoft Teams](admin-settings.md).|
|Comment est-ce que je vais choisir les groupes qui vont recevoir ces blocs d’applications ?|Voir [Autorisations d’applications Microsoft Teams et points à prendre en compte](app-permissions.md).|

### <a name="archiving-and-compliance"></a>Archivage et conformité 

Votre organisation peut exiger que vous implémentiez des contrôles sur l’archivage des équipes et sur les types de données qui sont conservées dans certains types d’équipes. Consultez [Vue d’ensemble sur la sécurité et la conformité dans Teams](security-compliance-overview.md) pour en savoir plus sur les paramètres Teams qui sont activés par défaut.

| Posez-vous la question | Action |
|--------------|--------|
|Est-ce que je devrai configurer la rétention pour les équipes ?|Pour configurer des stratégies de rétention, voir [Établir des stratégies de rétention dans Teams](retention-policies.md).|
|Est-ce que je dois configurer l’archivage pour les équipes ?|Pour archiver ou restaurer une équipe, voir [Archiver ou restaurer une équipe](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7).|
|Est-ce que je dois configurer des paramètres de conformité additionnels ?|Pour plus d’informations sur la sécurité et la conformité, voir [Vue d’ensemble concernant le sécurité et la conformité dans Teams](security-compliance-overview.md).|

### <a name="conditional-access"></a>Accès conditionnel 

Teams s’appuie largement sur Exchange et SharePoint pour les principaux scénarios de productivité, notamment les réunions, les calendriers, les conversations d’interopérabilité et le partage de fichiers. Les stratégies d’accès conditionnel définies pour ces applications cloud s’appliquent à Teams lorsqu’un utilisateur se connecte directement à Teams, sur n’importe quel client. Stratégies d’accès conditionnel définies pour les aspects du contrôle d’application cloud Teams, par exemple si les utilisateurs peuvent accéder aux services Teams à partir de certains réseaux.

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
- Inclure des applications proposées (par exemple, le Planificateur) dans votre déploiement initial concernant Teams. Ajoutez d’autres [applications, robots et connecteurs](deploy-apps-microsoft-teams-landing-page.md) pour favoriser l’adoption des services Teams.
- [Mettre en place des réunions et des conférences](deploy-meetings-microsoft-teams-landing-page.md)
- [Mettre en place les services audio dans le nuage](cloud-voice-landing-page.md)
