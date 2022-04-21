---
title: Configurer Microsoft Teams dans votre entreprise
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
description: Configurer Teams dans votre entreprise pour permettre à vos utilisateurs de collaborer à l’aide de la conversation et du partage de fichiers, configurer et participer à des réunions de petite et grande taille, et discuter par vidéo et voix.
ms.localizationpriority: high
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-deployteams
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6d5a9e3318ac0c72360487dbfc08b63bd39dc55e
ms.sourcegitcommit: 1d990582e2deb5f55ba9adada3e17377f792a141
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/19/2022
ms.locfileid: "64922425"
---
# <a name="set-up-microsoft-teams-in-your-enterprise"></a>Configurer Microsoft Teams dans votre entreprise

Les informations de cet article vous guident dans le déploiement de Teams dans votre organisation.

> [!NOTE]
> Si vous ne l’avez pas déjà fait, nous vous suggérons vivement de commencer votre déploiement Teams avec un pilote. Un pilote vous permettra, ainsi qu’à quelques utilisateurs précoces, de vous familiariser avec Teams et ses fonctionnalités avant votre planification et votre déploiement éventuel. Pour plus d’informations sur le démarrage de votre pilote, consultez [Démarrage avec Microsoft Teams](get-started-with-teams-quick-start.md).

Avant de déployer Teams à grande échelle, assurez-vous que votre organisation est prête en consultant les points de la section [Assurez-vous que vous êtes prêt](get-started-with-teams-quick-start.md#make-sure-youre-ready).

## <a name="plan-your-deployment"></a>Planifier votre déploiement

Avant de commencer à déployer Teams, assurez-vous que vous avez terminé votre processus de planification. Votre processus de planification doit inclure :

- Présentation de l’architecture Teams
- Examen et compréhension des charges de travail Teams et de leur mode de fonctionnement avec Microsoft 365
- Configuration réseau calculée requise et garantie du matériel et de la capacité de votre réseau et de votre connexion Internet nécessaires à la prise en charge d’exigences critiques telles que les communications en temps réel
- Compréhension des exigences réglementaires et de conformité pour les informations stockées dans Teams et les autres services Microsoft 365
- Création d’un plan d’adoption pour aider les utilisateurs à comprendre les avantages de l’utilisation de Teams

Nous vous recommandons vivement d’utiliser le [Conseiller pour Teams](https://admin.teams.microsoft.com/teams-deployment) pour vous aider dans le déploiement. Pour plus d’informations sur le fonctionnement du conseiller Teams, consultez [Utiliser Conseiller pour Teams pour faciliter le déploiement de Microsoft Teams](use-advisor-teams-roll-out.md).

> [!TIP]
> Découvrez comment utiliser le Conseiller pour Teams pour vous aider à planifier votre déploiement Teams en complétant le module[Déployer à l’aide de Conseiller pour Teams](/learn/modules/m365-teams-rollout-using-advisor/) sur Microsoft Learn.

Pour plus d’informations sur la planification pour Teams, consultez [Vue d’ensemble du déploiement d'entreprise Teams](deploy-enterprise-overview.md).

## <a name="workloads"></a>Charges de travail

Il existe de nombreuses façons de personnaliser Teams. Les sections suivantes vous montrent comment configurer chaque charge de travail Teams : **conversations, équipes et canaux**; **réunions et conférences**; et **système téléphonique**. Vous devez définir l’ordre dans lequel vous définissez chaque charge de travail. Bien que nous vous recommandons de commencer par définir les conversations, les équipes et les canaux de charge de travail, vous pouvez commencer par des réunions et des conférences, voire même un Système téléphonique.

#### <a name="chat-teams-and-channels"></a>[Conversations, équipes et canaux](#tab/ChatTeamsChannels)

La conversation, les équipes et les canaux sont la clé de l’utilisation de Teams. La **conversation** permet à un ou plusieurs utilisateurs de discuter, de partager des fichiers, puis de se réunir en privé. Les **équipes**, visibles par tous les membres de votre organisation ou seulement par les membres de l’équipe, permettent aux bonnes personnes collaborer quelle que soit la tâche ou l’occasion, qu’il s’agisse d’un projet de longue durée ou d’une fête d’anniversaire. Les **canaux** au sein des équipes peuvent segmenter des sujets, des projets, des services ou toute autre chose qui a du sens pour votre équipe. Si vous souhaitez en savoir plus sur les conversations, les équipes et les canaux, veuillez consulter la rubrique [Vue d’ensemble des équipes et canaux](teams-channels-overview.md).

> [!TIP]
> Découvrez comment gérer les rôles d’équipe, l’accès et les stratégies de messagerie en complétant le module [Gérer Microsoft Teams](/learn/modules/m365-teams-collab-manage-teams/) dans Microsoft Learn.

### <a name="administration-and-team-ownership"></a>Administration et propriété de l’équipe

| Decision | Description |
|--|--|
| Qui doit être administrateur Teams ? | Les rôles d'administrateur vous permettent d’accorder des autorisations spécifiques aux personnes qui doivent, selon vous, administrer Teams. Les petites entreprises n’ont pas besoin de ces rôles supplémentaires, car la même personne peut être responsable de tous les aspects de Teams. Vous pouvez toujours ajouter ou supprimer des administrateurs ultérieurement.<p>[Utiliser des rôles d’administrateur de Microsoft Teams pour gérer Teams](using-admin-roles.md) |
| Qui doivent être propriétaires et membres d’une équipe ? | Les propriétaires d’équipe contrôlent qui peut accéder à une équipe et à ses canaux. Ils peuvent décider si une équipe ou un canal est public (pour l’organisation) ou privé, puis définir des stratégies telles que la modération d’un canal. Les membres peuvent accéder à l’équipe et à ses canaux (sauf si un canal est donné comme privé et qu’ils ne sont pas membres de ce canal) et peuvent être désignés comme modérateurs.<p>[Affecter des propriétaires d’équipe et des membres dans Microsoft Teams](assign-roles-permissions.md) |

### <a name="default-settings-and-lifecycle-policies"></a>Paramètres et stratégies de cycle de vie par défaut

| Decision | Description |
|--|--|
| Quelles stratégies de messagerie doivent être appliquées ? | Les stratégies de messagerie contrôlent les fonctionnalités de messagerie instantanée et de canal (par exemple, utilisateurs ayant la fonctionnalité de conversation, personnes ayant la fonctionnalité de modification et de suppression des messages envoyés, etc.) disponibles pour les utilisateurs de Teams. Teams a une stratégie globale qui s’applique à tout le monde. Toutes les fonctionnalités de la stratégie globale sont **Activées** par défaut.<p>Si vous voulez que la même stratégie s’applique à tout le monde, il vous suffit d’apporter des modifications à cette stratégie globale (par exemple, désactiver la prise en charge mème dans les conversations).<p>Si vous souhaitez utiliser différentes stratégies pour différents groupes de personnes (par exemple, une stratégie pour les employés de bureau et une autre pour les employés d’usine), vous pouvez créer et attribuer des stratégies. Lorsque vous affectez une stratégie à un utilisateur, la stratégie globale ne s’applique plus à celui-ci.<p>[Gérer les stratégies de messagerie dans Teams](messaging-policies-in-teams.md) |
| Quels paramètres d’équipe doivent être appliqués ? | Les paramètres de Teams permettent de configurer les fonctionnalités pour vos équipes, comme par exemple l’intégration courrier, les options de stockage dans le cloud, l’onglet organisation, la configuration des salles de conférence et l’étendue des recherches. Lorsque vous apportez des modifications à ces paramètres, ils s’appliquent à toutes les équipes au sein de votre organisation.<p>[Paramètres de Teams](enable-features-office-365.md#teams-settings)  |

### <a name="external-and-guest-access"></a>Comparer l’accès externe et l’accès invité

| Decision | Description |
|--|--|
| L’accès externe doit-il être activé ? | L’accès externe permet aux membres d’une autre organisation de parler aux utilisateurs de votre organisation. Cela est utile lorsque vous avez une relation étroite avec une autre organisation, telle qu’un fournisseur, et que vous souhaitez faciliter la discussion entre les membres d’une organisation, la tenue de réunions, etc. <p>L’accès externe est différent de celui des invités. L’accès externe permet à tous les membres d’une organisation d’interagir avec les membres de votre organisation. L'accès invité invite des personnes spécifiques à interagir avec les contacts de votre organisation.<p>L’accès externe est **Désactivé** par défaut.<p>[Gérer l’accès externe dans Microsoft Teams](manage-external-access.md)  |
| L’accès invité doit-il être activé ? |L’accès invité permet aux contacts de votre organisation d’inviter des contacts externes à votre organisation à accéder à vos équipes et canaux. L’accès invité sert souvent à collaborer avec des contacts extérieurs à votre organisation qui n’ont pas de relation officielle avec la vôtre. Par exemple, vous pouvez inviter un planificateur de projet à travailler temporairement sur un projet.<p>L’accès invité est différent de l’accès externe. L'accès invité invite des personnes spécifiques à interagir avec les contacts de votre organisation. L’accès externe permet à tous les membres d’une autre organisation d’interagir avec les membres de votre organisation. <p>L’accès invité est **activé** par défaut. <p>[Collaborer avec des invités au sein d’une équipe](/microsoft-365/solutions/collaborate-as-team)  |

#### <a name="meetings-and-audio-conferencing"></a>[Réunions et audioconférence](#tab/MeetingsAudioConferencing)

Les réunions et conférences permet aux contacts de votre organisation de se réunir ainsi qu’à l’extérieur de votre organisation. Toute personne possédant un client Teams ou Skype Entreprise peut participer aux **réunions** auxquelles elle a été invitée. L’utilisation du microphone, de la caméra et de l’écran de leur appareil permet aux participants de rejoindre la conversation sans avoir besoin d’un téléphone. Les participants peuvent converser, passer des appels vocaux et partager des vidéos et applications avec d’autres participants à l’aide d’un PC ou d’un appareil mobile.

Le **système d’audioconférence** permet aux participants de rejoindre les réunions par téléphone normal en appelant un numéro de téléphone de conférence, puis en entrant un ID de réunion. L’audioconférence est utile lorsqu’un participant n’a pas une bonne connexion Internet, que la réunion est à voix seule ou qu’une autre circonstance ne lui permet pas de rejoindre la réunion via le client Teams.

> [!TIP]
> Familiarisez-vous avec les réunions et événements en complétant le module [Gérer les réunions, conférences et événements avec Microsoft Teams](/learn/modules/m365-teams-collab-manage-meetings) sur Microsoft Learn.

### <a name="meetings"></a>Réunions

| Decision | Description |
|--|--|
| Paramètres de réunion à l’échelle de l’organisation qui doivent être appliqués| Les stratégies de réunion contrôlent les fonctionnalités de réunion disponibles pour les organisateurs et les participants aux réunions. Vous pouvez contrôler si les participants anonymes peuvent rejoindre des réunions, personnaliser les invitations, contrôler la gestion des médias en temps réel, etc. Lorsque vous apportez des modifications à ces paramètres, ils s’appliquent à toutes les réunions de votre organisation. <p>[Gérer les paramètres de réunion dans Microsoft Teams](meeting-settings-in-teams.md)|
| Quelles stratégies de réunion doivent être appliquées ? | Stratégies de réunion: elles sont utilisées pour contrôler les fonctionnalités disponibles aux participants à la réunion pour les réunions planifiées par des utilisateurs au sein de votre organisation. Vous pouvez contrôler si les utilisateurs peuvent planifier des réunions privées, activer l’option Conférence maintenant, autoriser l’enregistrement des réunions, etc. Teams a une stratégie globale qui s’applique à tout le monde.<p> Si vous voulez que la même stratégie s’applique à tout le monde, il vous suffit d’apporter des modifications à cette stratégie globale (par exemple, désactiver l’enregistrement des réunions). <p>Si vous souhaitez utiliser différentes stratégies pour différents groupes de personnes (par exemple, une stratégie pour les employés de bureau et une autre pour les cadres), vous pouvez créer et attribuer des stratégies. Lorsque vous affectez une stratégie à un utilisateur, la stratégie globale ne s’applique plus à celui-ci.<p> [Gérer les stratégies de réunion dans Teams](meeting-policies-overview.md)|
| Voulez-vous autoriser l’enregistrement et l’archivage des réunions ?| Les organisateurs de réunion peuvent enregistrer et archiver des réunions dans le cloud. Vous pouvez activer ou désactiver l’enregistrement et l’archivage des réunions à l’aide de stratégies de réunion.<p> [Enregistrement de réunion cloud Teams](cloud-recording.md) |

### <a name="audio-conferencing"></a>Audioconférence

| Decision | Description |
|--|--|
| Voulez-vous configurer l’interopérabilité vidéo avec des solutions tierces ?| L’interopérabilité vidéo dans le cloud permet à des tiers de téléprésence et à des appareils vidéo personnels de participer à des réunions Teams. Si vous avez déjà investi dans la vidéoconférence et les appareils vidéo personnels, vous pouvez utiliser l’interopérabilité vidéo pour intégrer ces appareils à Teams.<p> [Interopérabilité de la vidéo cloud de Microsoft Teams](cloud-video-interop.md)|
| Quels paramètres de l’audioconférence à l’échelle de l’organisation doivent être appliqués ?| Les paramètres de l’audioconférence vous permet de contrôler la manière dont les participants à la réunion participent aux réunions à l’aide d’un téléphone. Vous pouvez définir la longueur des codes PIN nécessaires pour participer aux réunions, réinitialiser les identifiants de conférence, activer ou désactiver l'envoi d'informations d'audioconférence aux participants, etc. Les modifications apportées aux paramètres d’audioconférence s’appliquent à tous les membres de votre organisation.<p>[Gérer les paramètres d'audioconférence de votre organisation dans Microsoft Teams](manage-the-audio-conferencing-settings-for-my-organization-in-teams.md). |
| Les organisateurs de réunion doivent-ils appeler des personnes vers une destination quelconque ?| Les crédits de communication sont utilisés lors des appels d’une réunion d’audioconférence vers des numéros de téléphone externes à votre organisation. Vous devez acheter suffisamment de crédits de communications pour être assuré de ne pas être à court lors des appels audioconférences.<p>Certains abonnements d’audioconférence peuvent inclure des appels sortants. Pour plus d’informations, consultez les informations de votre abonnement.<p> [Configurer les crédits de communication pour votre organisation](set-up-communications-credits-for-your-organization.md)|
| Quelles restrictions d’appels sortants doivent être appliquées ?| Vous pouvez utiliser les contrôles d'appels sortants pour restreindre le type des appels de conférence audio pouvant être effectués par les utilisateurs de votre organisation. Par exemple, vous pouvez contrôler si les réunions peuvent appeler des numéros de téléphone internationaux, effectuer des appels sortants, appeler uniquement des pays ou régions spécifiques, et ainsi de suite.<p>[Stratégies de restriction des appels sortants pour l’audioconférence et les appels RTC des utilisateurs](outbound-calling-restriction-policies.md) |
| Voulez-vous modifier la manière dont les numéros de téléphone composés sont interprétés par Teams ? | Vous pouvez contrôler la façon dont les numéros de téléphone sont interprétés à l’aide des plans de numérotation. Par exemple, vous pouvez définir le numéro à composer pour atteindre une ligne de téléphone extérieure, contrôler la façon dont les extensions de téléphone sont gérées, définir un préfixe de sorte qu’une extension à numérotation soit convertie en numéro de téléphone complet, etc.<p> [Créer et gérer les plans de numérotation](create-and-manage-dial-plans.md) |
| Voulez-vous activer des événements en direct ? | Les événements en direct vous permet de diffuser du contenu vidéo et de réunion auprès d’un public large. Si vous activez des événements en direct, vous pouvez définir des stratégies pour leur permettre de contrôler leur utilisation. Par exemple, vous pouvez configurer l’URL que les participants doivent utiliser pour la prise en charge, configurer un fournisseur de distribution de vidéos tiers s’il en a un, et ainsi de suite. Teams a une stratégie globale qui s’applique à tout le monde.<p>Si vous voulez que la même stratégie s’applique à tout le monde, il vous suffit d’apporter des modifications à cette stratégie globale. <p>Si vous souhaitez utiliser différentes stratégies pour différents groupes de personnes (par exemple, une stratégie pour les employés de bureau et une autre pour les cadres), vous pouvez créer et attribuer des stratégies. Lorsque vous affectez une stratégie à un utilisateur, la stratégie globale ne s’applique plus à celui-ci.<p> [Configurer des événements en direct dans Microsoft Teams](teams-live-events/set-up-for-teams-live-events.md) |

#### <a name="phone-system-and-pstn-connectivity"></a>[Système téléphonique et connectivité PSTN](#tab/PhoneSystem)

Votre système téléphonique vous permet de remplacer votre système téléphonique local par un ensemble de fonctionnalités de Microsoft 365 étroitement intégrées à votre expérience cloud.

| Decision | Description |
|--|--|
| Voulez-vous remplacer votre système téléphonique local ? | Configurez le système téléphonique, configurez les attendants automatiques, les forfaits d’appels, les files d’attente d’appels, etc. <p> [La configuration système téléphonique de votre organisation](setting-up-your-phone-system.md)|
| Voulez-vous définir les stratégies de messagerie vocale dans le cloud ?| Vous pouvez contrôler les fonctionnalités de messagerie vocale cloud accessibles à vos utilisateurs et leur fonctionnement. Par exemple, vous pouvez activer ou désactiver la transcription de la messagerie vocale pour l’ensemble de votre organisation, activer ou désactiver le masquage de la messagerie vocale pour des utilisateurs spécifiques, etc.<p> [Configurer la Messagerie vocale cloud](set-up-phone-system-voicemail.md) |
| Voulez-vous activer les appels d’urgence dynamiques ?| L’appel d’urgence dynamique vous permet de configurer une carte d’emplacement en fonction des paramètres réseau et d’autres métadonnées pour déterminer où envoyer le personnel d’urgence en cas d’appel d’urgence d’un utilisateur. Vous pouvez configurer les paramètres réseau, attribuer des adresses d’urgence à des emplacements géographiques, etc.<p>[Planifier et configurer un appel d’urgence dynamique](configure-dynamic-emergency-calling.md) |
| Voulez-vous personnaliser le comportement de l’ID d’appelant ? | Par défaut, le numéro de téléphone qui s’affiche lorsqu’un utilisateur Teams passe un appel est le numéro de téléphone de l’utilisateur. Vous pouvez modifier ce numéro pour en faire le numéro principal de l'entreprise, bloquer le numéro de téléphone, rendre le numéro anonyme ou un autre numéro de service. Teams a une stratégie globale qui s’applique à tout le monde.<p>Si vous voulez que la même stratégie s’applique à tout le monde, il vous suffit d’apporter des modifications à cette stratégie globale. <p>Si vous souhaitez utiliser différentes stratégies pour différents groupes de personnes (par exemple, une stratégie pour les employés de bureau et une autre pour les cadres), vous pouvez créer et attribuer des stratégies. Lorsque vous affectez une stratégie à un utilisateur, la stratégie globale ne s’applique plus à celui-ci.<p> [Gérer les stratégies d’ID d’appelant dans Microsoft Teams](caller-id-policies.md) |

---

## <a name="security"></a>Sécurité

Teams est conçue et développée dans le respect du Microsoft[ Trustworthy Computing Security Development Lifecycle (SDL)](https://www.microsoft.com/sdl/default.aspx). Pour être conforme au SDL, Teams incorpore des technologies de sécurité standard en tant que partie fondamentale de son architecture, notamment :

- Conception de modèles de menaces contre les fonctionnalités qui sont ensuite testées
- Plusieurs améliorations liées à la sécurité ont été intégrées au processus et aux pratiques de codage.
- Création d’outils de build permettant de détecter les dépassements de mémoire tampon et autres menaces potentielles pour la sécurité avant l’accès au code dans le produit

Bien que Teams s’inspire d’une méthodologie « Trustworthy by Design », il est impossible de le concevoir contre toutes les menaces de sécurité inconnues. Pour cette raison, il est important de comprendre le fonctionnement de Teams et l’interaction avec les autres systèmes. Il est également important de comprendre la manière dont les menaces courantes, telles que l’usurpation d’adresse IP, les attaques de l'homme du milieu, etc., fonctionnent de telle sorte que vous pouvez concevoir votre réseau et votre configuration Teams afin de réduire les risques de ces attaques.

Pour mieux comprendre comment Teams intègre les principes fondamentaux de la sécurité dans sa conception et pour en savoir plus sur les menaces courantes, consultez [Sécurité et Microsoft Teams](teams-security-guide.md).

## <a name="compliance"></a>Conformité

Teams et Microsoft 365 fournissent de nombreux outils qui peuvent vous aider à vous conformer aux exigences réglementaires en vigueur au pays de votre entreprise et dans les utilisateurs. Pour plus d’informations sur la configuration de chaque fonctionnalité de conformité dans Teams, consultez les articles suivants :

| Fonctionnalité | Description|
|-|-|
| [Obstacles aux informations](information-barriers-in-teams.md)| Empêche les individus ou groupes de communiquer entre eux ou de trouver du contenu dans le sélecteur d’utilisateur.|
| [Stratégies de rétention](retention-policies.md)| Vous permet de contrôler la durée de conserve des données dans Teams ou si les données doivent être supprimées après un certain temps.|
| [Conformité des communications](communication-compliance.md)| Permet de réduire les risques de communication en identifiant et en agissant sur le langage choquant, blasphématoire et harcelant, sur les images racées et sanglantes des adultes et sur le partage d'informations sensibles. |
| [Enregistrement basé sur une stratégie pour les appels et réunions](teams-recording-policy.md)| Vous permet de contrôler quand et si les appels et réunions doivent être enregistrés et stockés automatiquement pour traitement ultérieur, rétention ou analyse.|
| [Étiquettes de confidentialité](sensitivity-labels.md)| Permet de protéger et de contrôler l’accès aux informations sensibles en créant des étiquettes qui appliquent les options de confidentialité sélectionnées.|
| [Protection contre la perte de données Microsoft Purview](/microsoft-365/compliance/dlp-microsoft-teams?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoftteams%2ftoc.json)| Permet de créer des règles qui déterminent la manière dont certaines informations, telles que les numéros de sécurité sociale, les numéros de carte de crédit, etc. doivent être gérées. Vous pouvez empêcher l’envoi de certaines informations, les empêcher de quitter votre organisation, etc.|
| [eDiscovery](eDiscovery-investigation.md)| Vous permet de rechercher et de récupérer du contenu dans votre organisation lorsque votre organisation reçoit des demandes de découverte dans le cadre de procédures légales. |
| [Conservation légale](legal-hold.md)| Vous permet de conserver les informations de votre organisation, même si elles sont supprimées par un utilisateur, au besoin pendant une procédure légale afin de pouvoir les découvrir dans le cadre d’enquêtes eDiscovery. |
| [Recherche de contenu](content-search.md)| Fournit un moyen de interroger les informations Teams sur Exchange, SharePoint Online et OneDrive Entreprise.|
| [Auditing](audit-log-events.md)| Vous permet de voir des informations sur une action spécifique, y compris qui a effectué l'action, quand l'action a été effectuée, l'adresse IP qui a été utilisée, et ainsi de suite. Les actions comprennent la création ou la suppression d'équipes, la création de canaux, la modification des paramètres Teams, etc.|
| [Clé client](/microsoft-365/compliance/customer-key-tenant-level?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoftteams%2ftoc.json)| Vous permet de créer une stratégie de chiffrement des données à l’aide de clés de chiffrement que vous fournissez.|

## <a name="clients"></a>Clients

Lorsque vous êtes prêt à aider vos utilisateurs à utiliser Teams, ils peuvent installer le client Teams sur leur PC Windows, Mac ou Linux, ou sur leur appareil Android ou iOS. Les utilisateurs peuvent télécharger le client Teams directement à partir de <https://teams.microsoft.com/downloads>.

Vérifiez que toutes les personnes qui utiliseront Teams ont une licence Teams. Si vous souhaitez en savoir plus sur l’attribution d’une licence Teams, veuillez consulter la rubrique [Gérer l’accès des utilisateurs à Teams](user-access.md#using-the-microsoft-365-admin-center).

> [!TIP]
> Obtenez des recommandations sur la façon de planifier le déploiement de votre client Teams en complétant le module [Déployer les clients Microsoft Teams](/learn/modules/m365-teams-collab-deploy-clients/) sur Microsoft Learn.

Si votre organisation utilise Microsoft Endpoint Configuration Manager, une stratégie de groupe ou un mécanisme de distribution tiers, pour déployer des logiciels sur les ordinateurs de vos utilisateurs, veuillez consulter la rubrique [Installer Microsoft Teams à l’aide de Microsoft Endpoint Configuration Manager](msi-deployment.md).

Si vous souhaitez en savoir plus sur le déploiement des clients Teams, veuillez consulter la rubrique [Obtenir les clients pour Microsoft Teams](get-clients.md).

## <a name="training"></a>Formation

Pour plus d’informations sur la formation de vos utilisateurs et administrateurs à l’utilisation de Teams, consultez [Formation Microsoft Teams](training-microsoft-teams-landing-page.md).
