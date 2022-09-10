---
title: Configurer les paramètres de conférence audio-Microsoft Teams
ms.reviewer: ''
description: Utilisez ces ressources de déploiement pour vous aider à mettre en place des conférence audio dans le cadre de la charge de travail de réunions dans Microsoft Teams.
ms.topic: article
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
audience: admin
ms.date: 01/28/2019
ms.service: msteams
ms.collection:
- M365-voice
- M365-collaboration
ms.custom:
- seo-marvel-mar2020
f1.keywords:
- NOCSH
ms.localizationpriority: high
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1da45446c2ab1879dd8064537dc50dafd99ea013
ms.sourcegitcommit: 5abfb6f1abe10b6d32cf6eb97a890cf3138ed0e6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/10/2022
ms.locfileid: "67641745"
---
# <a name="learn-how-to-deploy-audio-conferencing-in-microsoft-teams"></a>Découvrir comment déployer la conférence audio dans Microsoft Teams

Une conférence audio permet de participer à une réunion d’équipes à partir d’un téléphone standard en appelant simplement le numéro de téléphone de la réunion. Vérifiez que vous avez revu le [Déploiement des réunions](deploy-meetings-microsoft-teams-landing-page.md) dans le cadre du déploiement des conférences audio dans votre organisation.

## <a name="audio-conferencing-deployment-decisions"></a>Décisions de déploiement des conférences audio

Cet article vous permet de décider si vous voulez modifier les paramètres par défaut de conférence audio en fonction du profil de votre organisation et vos exigences professionnelles, puis il vous guide pour chaque modification. Nous avons fractionné les paramètres en deux groupes, en commençant par l’ensemble des [modifications principales que vous êtes le plus susceptible d’apporter](#core-deployment-decisions). Le deuxième groupe inclut les [paramètres supplémentaires](#additional-deployment-decisions) que vous souhaiterez peut-être configurer, en fonction des besoins de votre organisation.

Il vous suffit de configurer la fonctionnalité de conférence audio pour les utilisateurs qui comptent planifier ou organiser des réunions. Les participants à la réunion qui se connectent n’ont pas besoin de licence ni d’aucune configuration particulière. La connexion (connexion) aux réunions est très utile pour les utilisateurs qui sont sur la route et ne peuvent pas participer à une réunion à l’aide de l’application Teams sur leurs ordinateurs portables ou appareils mobiles.

## <a name="audio-conferencing-prerequisites"></a>Conditions requises pour une audioconférence

Avant de pouvoir mettre en place une conférence audio pour Teams, il faut prendre en compte ce qui suit :

|Posez-vous la question|Action |
|------------|-------|
|Est-ce que la fonctionnalité de conférence audio est disponible pour mon pays/ma région ?|Consultez cet article pour savoir si l’audioconférence est disponible dans votre pays ou région : [Disponibilité de l'audioconférence et des forfaits d'appels selon les régions et les pays](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).|
|Mes utilisateurs ont-ils la licence appropriée pour le service conférence audio de Teams ?|Les licences d’audioconférence sont disponibles dans le cadre des abonnements Microsoft 365 ou Office 365 E5, ou en tant que complément des abonnements Microsoft 365 Business Standard E1 ou E3. <ul><li>Pour obtenir et attribuer des licences, consultez [Affecter ou supprimer des licences pour Applications Microsoft 365 pour les PME](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</li><li> Pour en savoir plus, lire[Licences de module complémentaire Microsoft Teams](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md). </li><li>Pour voir quelles sont les fonctionnalités du nuage sont incluses dans chaque offre, consultez [Options en fonction de votre offre de licence](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</li></ul>|
|Est-ce que j’ai besoin d’acheter des crédits de communication pour les utilisateurs à qui sont attribuées les licences de conférence audio ?|Pour en savoir plus, voir [Les crédits de communication, qu’est-ce que c’est ?](what-are-communications-credits.md), puis consulter la section [Crédits de communication](#communications-credits) section ci-dessous.|
|||

## <a name="core-deployment-decisions"></a>Décisions liées au déploiement Core

Une fois que vous avez confirmé que vous remplissez les Conditions requises pour la conférence audio, effectuez les tâches suivantes pour configurer des conférences audio pour vos utilisateurs.

### <a name="teams-administrators"></a>Administrateurs Teams

Teams fournit un ensemble de rôles d’administrateur personnalisé qui peuvent servir à gérer des équipes pour votre organisation. Ces rôles fournissent plusieurs fonctionnalités aux administrateurs.

| Posez-vous la question | Action |
|--------------|--------|
|Qui va assumer le rôle d’Administrateur des Communications Teams ?|Pour en savoir plus sur les rôles d’administrateur Teams, voir [Utiliser les rôles d’administrateur Microsoft Teams pour gérer les équipes](using-admin-roles.md).|
|Qui va assumer le rôle d’ingénieur support des Communications Teams ?|Pour attribuer des rôles d’administrateur, voir [Attribuer des rôles administrateur et non administrateur aux utilisateurs avec Active Directory](/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal).|
|Qui va assumer le rôle de spécialiste d’assistance des Communications Teams ?||
|||

### <a name="conferencing-bridges-and-phone-numbers"></a>Ponts d’audioconférence et numéros de téléphone

Les ponts de conférence permettent aux utilisateurs de participer à des réunions à l’aide d’un téléphone. Vous pouvez utiliser les paramètres par défaut pour le pont d’audioconférence ou modifier les numéros de téléphone (numéro payant et numéro gratuit) et d’autres paramètres, par exemple, le code confidentiel ou les langues qui sont utilisées.

Voir [Audioconférence](audio-conferencing-in-office-365.md) pour en apprendre plus.

|Posez-vous la question|Action |
|------------|-------|
|Est-ce que j’ai besoin d’ajouter de nouveaux numéros pour le pont d’audioconférence ?| Pour ajouter de nouveaux numéros, voir [Obtention de numéros de téléphone de service](./getting-service-phone-numbers.md).|
|Est-ce que je vais devoir modifier les paramètres de pont ?|Pour modifier les paramètres de pont, voir [Modifier les paramètres d’un pont d’audioconférence](change-the-settings-for-an-audio-conferencing-bridge.md).|
|Est-ce que j’ai besoin de transférer des numéros de téléphone à utiliser avec les audioconférences ?|Pour savoir comment transférer des numéros de téléphone, consultez [Transfert des numéros de téléphone vers Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).|
|||

### <a name="default-and-alternate-languages"></a>Langues par défaut et autres langues

Vous pouvez configurer la langue par défaut et d’autres langues pour les audioconférences Teams pour le pont d’audioconférence.

|Posez-vous la question|Action |
|------------|-------|
| Quelles langues dois-je choisir pour les messages d’accueil du standard automatique ? | Pour choisir des langues, consultez [Définir les langues du standard automatique pour l’audioconférence dans Microsoft Teams](set-auto-attendant-languages-for-audio-conferencing-in-teams.md).|
|||

### <a name="conferencing-bridge-settings"></a>Paramètres du pont d’audioconférence

Après avoir configuré votre pont de conférence, y compris les langues par défaut et autres langues, vérifiez que les paramètres par défaut, tels que les notifications d’entrée/sortie et la longueur du code confidentiel sont ceux que vous souhaitez utiliser. Dans le cas contraire, vous pouvez les modifier.

|Posez-vous la question|Action |
|------------|-------|
| Est-ce que les participants vont entendre une notification lorsqu’un utilisateur rejoint ou quitte une réunion ? | Pour modifier ces paramètres, voir [Modifier les paramètres d’un pont d’audioconférence](change-the-settings-for-an-audio-conferencing-bridge.md).|
|Qu’est la longueur requise du code confidentiel qu’utilise un organisateur de réunion pour démarrer la réunion ?||
|||

### <a name="dial-in-phone-number-settings-for-users-who-lead-meetings"></a>Paramètres de numéro d’appel entrant pour les utilisateurs qui dirigent des réunions

Après avoir créé votre pont d’audioconférence, vous devez définir le numéro payant et/ou les numéros gratuits qu’utiliseront les utilisateurs qui dirigent les réunions.

|Posez-vous la question|Action |
|------------|-------|
| Quels sont les numéros de pont d’audioconférence qui seront attribués à chaque utilisateur qui organisent les réunions ? | Pour attribuer un numéro de téléphone de connexion à un utilisateur, voir [Étape 7 : affecter des numéros d’appel entrant aux utilisateurs qui dirigent des réunions](set-up-audio-conferencing-in-teams.md#step-7-assign-dial-in-phone-numbers-for-users-who-lead-meetings). |
|||

### <a name="communications-credits"></a>Crédits de communication

Pour fournir des numéros gratuits de pont de téléconférence et pour prendre en charge les appels de téléconférence vers des numéros internationaux, vous devez configurer des crédits de communication pour votre organisation. Pour en savoir plus sur les crédits de communication, voir [En quoi consistent les crédits de communication ?](what-are-communications-credits.md).

|Posez-vous la question|Action |
|------------|-------|
|Est-ce que les crédits de communications sont requis pour mon implémentation d’audioconférence ? |Pour savoir si vous devez configurer les Crédits de communications, voir [Configurer les Crédits de communications pour votre organisation](set-up-communications-credits-for-your-organization.md).|
|Si ceux-ci sont nécessaires, quel montant dois-je acheter ?|Pour déterminer la quantité de Crédits de communication, voir [Montants recommandés](what-are-communications-credits.md#recommended-funding-amounts).|
|Est-ce que je souhaite configurer un montant de recharge automatique ?|Pour configurer un montant de recharge automatique, voir [Configurer les crédits de communication pour votre organisation](set-up-communications-credits-for-your-organization.md).|
|||

## <a name="additional-deployment-decisions"></a>Décisions de déploiement supplémentaires

Vous souhaiterez peut-être modifier ces paramètres en fonction des besoins et de la configuration de votre organisation.

### <a name="outbound-calling-restriction-policies"></a>Stratégies de restriction des appels sortants

En tant qu'administrateur, vous pouvez utiliser les contrôles d'appels sortants pour restreindre le type de conférence audio et d'appels RTC d'utilisateur final pouvant être effectués par les utilisateurs de votre organisation.

|Posez-vous la question|Action |
|------------|-------|
| Est-ce que je vais limiter le type d’appels sortants qui sont autorisés ? | Pour limiter les appels sortants, voir [Stratégies de restriction des appels sortants pour l’audioconférence et les appels PSTN des utilisateurs](outbound-calling-restriction-policies.md).|
|||

### <a name="dial-plans"></a>Plan de numérotation

Un Plan de numérotation, fonctionnalité incluse dans le système téléphonique de Microsoft 365 ou Office 365, est un ensemble de règles de normalisation qui convertit les numéros de téléphone composés dans un autre format (généralement le format E.164) pour l’autorisation et le routage des appels.

Pour plus d'informations sur les plans d'appel, voir [Quels sont les plans de numérotation ?](what-are-dial-plans.md)

|Posez-vous la question|Action |
|------------|-------|
|Mon organisation a-t-elle besoin d’un plan de numérotation personnalisé ?|Pour vous aider à déterminer si vous avez besoin d’un plan de numérotation personnalisé, voir [Planification pour les plans de numérotation client](what-are-dial-plans.md#planning-for-tenant-dial-plans). |
|Quels sont les utilisateurs qui ont besoin d’un plan d’appel personnalisé et quel plan de numérotation client doit être attribué à chaque utilisateur ?|Pour ajouter des utilisateurs à un plan de numérotation personnalisé à l’aide de PowerShell, voir [Créer et gérer des plans de numérotation](create-and-manage-dial-plans.md).|
|||

### <a name="troubleshoot-meeting-and-call-quality"></a>Résoudre les problèmes de qualité de réunion et d’appel

Teams offre deux façons de surveiller et de résoudre les problèmes de qualité d’appel : [Analytique des appels et Tableau de bord de qualité des appels](monitor-call-quality-qos.md). L’analytique des appels affiche des informations détaillées sur les appareils, les réseaux et la connectivité liés aux appels et réunions spécifiques pour chaque utilisateur. L’analytique des appels est conçue pour aider les administrateurs et agents du support technique à résoudre les problèmes de qualité d’appel concernant des appels spécifiques, alors que le Tableau de bord de qualité des appels est conçu pour aider les administrateurs et les ingénieurs réseau à optimiser un réseau. Le Tableau de bord de qualité des appels se concentre sur des utilisateurs spécifiques et examine plutôt des informations globales pour l'ensemble d'une organisation Teams.

|Posez-vous la question|Action |
|------------|-------|
| Qui doit se charger de la surveillance et de la résolution des problèmes de qualité d’appel ? | Voir [Utiliser l’Analytique des appels pour résoudre les problèmes de qualité des appels médiocre](use-call-analytics-to-troubleshoot-poor-call-quality.md) pour plus d’informations sur les niveaux d’autorisation requis pour résoudre les problèmes de qualité d’appel.|
|||

## <a name="next-steps"></a>Étapes suivantes

- [Favoriser l’adoption](adopt-microsoft-teams-landing-page.md) des conférences audio dans votre organisation.
- [Mettre en place les services audio dans le nuage](cloud-voice-landing-page.md)
- Inclure des applications proposées (par exemple, le Planificateur) dans votre déploiement initial concernant Teams. Ajoutez d’autres [applications, robots et connecteurs](deploy-apps-microsoft-teams-landing-page.md) pour favoriser l’adoption des services Teams.
