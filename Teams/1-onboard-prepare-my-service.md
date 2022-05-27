---
title: Préparer le déploiement du service vocal cloud
author: rmw2890
ms.author: Rowille
manager: serdars
audience: ITPro
ms.date: 03/18/2019
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: Utilisez les listes de contrôle d’intégration pour préparer Microsoft 365 ou Office 365 pour Teams et configurer Teams fonctionnalités de base, la mise en réseau et les charges de travail de voix cloud.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: a91a57a077db38675a62238289ad2c204040a9cd
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675436"
---
# <a name="prepare-my-service"></a>Préparer mon service

Cet article fournit une vue d’ensemble des exigences de préparation des services vocaux cloud pour votre organisation. En vous préparant correctement, vous pouvez être sûr d’être prêt à fournir des fonctionnalités de voix cloud à votre organisation.

## <a name="onboarding-checklists-for-microsoft-teams-voice-workloads"></a>Listes de contrôle d’intégration pour Microsoft Teams charges de travail vocales

Les listes de vérification suivantes vous guident tout au long des étapes d’implémentation des Audioconférence, des Système téléphonique avec des forfaits d’appels (« Forfaits d’appels ») et des fonctionnalités de routage direct Système téléphonique (« Routage direct ») dans Microsoft Teams.

*  [Préparer Microsoft 365 ou Office 365 pour Teams](onboarding-checklist-enable-office-365.md)

*  [Configurer Teams fonctionnalités principales](onboarding-checklist-configure-microsoft-teams-core-capabilities.md)

*  [Préparer votre réseau](prepare-network.md)

*  [Configurer des charges de travail de voix cloud dans Teams](onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams.md)

*  [Configurer le routage direct dans Teams](onboarding-checklist-configure-direct-routing-in-Microsoft-Teams.md)

Les tâches et les activités de ces listes de vérification sont les principaux éléments « à faire » qui s’appliquent à chaque déploiement de fonctionnalités de voix cloud avec Teams. Vous pouvez personnaliser les listes de vérification pour inclure les activités et les tâches spécifiques à votre propre parcours Teams.

>[!NOTE]
>Ce guide se concentre uniquement sur les plans d’appel, les Audioconférence et le routage direct. Si vous débutez avec Teams, consultez [vue d’ensemble de Microsoft Teams](teams-overview.md). Pour obtenir des conseils généraux sur la planification de votre déploiement Teams, commencez par [déployer la conversation, les équipes, les canaux et les applications dans Microsoft Teams](deploy-chat-teams-channels-microsoft-teams-landing-page.md).

Utilisez les listes de vérification fournies pour suivre l’état de chaque activité et tâche individuelles, et pour vous assurer que vous n’avez pas ignoré les étapes critiques. Chaque activité inclut une description détaillée des actions requises et des références à des informations supplémentaires que vous pouvez utiliser pour effectuer cette activité.

Bien que nous vous recommandons de suivre les listes de vérification dans l’ordre, la séquence exacte dépend de l’étendue de votre déploiement et de la configuration et de la complexité de votre environnement. Ils sont organisés pour prendre en charge un déploiement Teams « greenfield » (sans aucune présence Skype Entreprise Online) ou la migration de Skype Entreprise Online vers Teams. Si vous effectuez une migration à partir de Skype Entreprise Online, vous avez peut-être déjà effectué certaines de ces activités et pouvez les ignorer maintenant.

Lorsque vous intègrez des utilisateurs par site, nous vous recommandons vivement d’utiliser le Playbook d’activation de site [pour voix (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) comme guide supplémentaire de ces listes de vérification.

>[!NOTE]
>La plupart des paramètres de configuration sont courants entre Teams et Skype Entreprise Online. Vous utilisez le centre de Administration Microsoft 365 et Microsoft Teams centre d’administration pour configurer ces paramètres.

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>Points de décision</td><td><ul><li>Qui serez chargé de superviser l’achèvement des listes de vérification d’intégration?</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Étapes suivantes</td><td><ul><li>Téléchargez les listes de contrôle d’intégration.</li><li>Suivez pas à pas les éléments de la liste de vérification d’intégration conformément au plan de déploiement de votre organisation.</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="continue-onboarding"></a>Continuer l’intégration

Une fois ces listes de vérification terminées, vous avez ajouté des fonctionnalités vocales à votre déploiement Teams.

À l’étape suivante, utilisez le Playbook d’activation de site [pour voix (Playbook) pour](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) vous aider à intégrer vos utilisateurs sur chaque site et à vous assurer que vous planifiez et exécutez des activités importantes spécifiques au site.

-   Plan de déploiement site par site prêt

-   Établir le processus de gestion des services

-   Exécuter des tests et des corrections

<!--ENDOFSECTION-->

## <a name="test-cloud-voice-workloads-in-teams"></a>Tester les charges de travail de voix cloud dans Teams

Une fois que vous avez défini et documenté votre Teams les plans de réussite et d’implémentation technique de votre entreprise de voix cloud dans le cadre de la phase Devis et que vous avez entrepris la configuration souhaitée dans le Centre d’administration, l’étape suivante consiste à vérifier que les attentes et les exigences de votre organisation sont satisfaites par le biais de fonctionnalités, de fonctionnalités et de facilité d’utilisation. Vous devez effectuer cette étape de validation avant de déployer un déploiement pilote ou final dans votre environnement de production.

Vous pouvez tirer parti du plan de réussite de l’entreprise que vous avez défini pendant la phase Devis pour servir de base pour déterminer les activités, les attentes, les cas de test de fonctionnalités/fonctionnalités et l’étendue globale à évaluer pendant la phase de test.

## <a name="define-your-testing-approach"></a>Définir votre approche de test

Dans sa forme la plus simple, votre approche de test est basée sur l’examen des fonctionnalités du service de Audioconférence, de forfaits d’appels ou de routage direct et sur l’élaboration d’un plan de test pour vérifier que vos besoins en fonctionnalités sont satisfaits pour les utilisateurs dans l’étendue. Voici un exemple de plan de test pour la phase d’intégration d’une implémentation d’audioconférence.


| Audioconférence fonctionnalité à tester | Résumé des résultats | Notes supplémentaires |
|------------|-----------------|------------------|
| Planifier une réunion de Teams ad hoc contenant des informations d’audioconférence rendez-vous | Réussite/Échec   | TBD |
| Utiliser un téléphone pour l’audio de réunion en entrant une réunion à partir du RTC avec les informations de connexion fournies | Réussite/Échec | TBD |
| Rejoindre d’autres personnes à une réunion existante en composant le rtc | Réussite/Échec | TBD |



| Forfaits d’appel ou fonctionnalité de routage direct à tester | Résumé des résultats | Notes supplémentaires |
|----------------------------------------------------|-----------------|------------------|
| Effectuer un appel RTC en composant un numéro RTC       | Réussite/Échec       | TBD |
| Recevoir un appel RTC en composant votre numéro RTC à partir d’une ligne externe (mobile, fixe) | Réussite/Échec | TBD|
| Transférer un appel RTC d’un utilisateur Teams vers un autre | Réussite/Échec | TBD |


>[!TIP]
>Pour faciliter la création de cas de test en tant que point de départ, consultez la liste des conseils utilisateur [disponibles dans Teams Réunions et appels](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8#bkmk_havingmeetings).

<!--ENDOFSECTION-->

## <a name="set-up-cloud-voice-workloads-for-teams"></a>Configurer des charges de travail de voix cloud pour Teams

Maintenant que vous avez défini votre approche de test, l’étape suivante consiste à configurer votre environnement de service et les utilisateurs dans l’étendue de Teams fonctionnalités de voix cloud.

Pour plus d’informations, consultez :

- [Planification technique de l’audioconférence](./cloud-voice-landing-page.md)

- [Configurer Audioconférence pour Microsoft Teams](set-up-audio-conferencing-in-teams.md)

- [Planification technique pour Système téléphonique avec forfaits d’appels](calling-plan-landing-page.md)

- [Configurer des forfaits d’appels pour Skype Entreprise et Microsoft Teams](/skypeforbusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

- [Planifier le routage direct](./direct-routing-plan.md)

- [Configurer le routage direct](./direct-routing-configure.md)

### <a name="execute-the-test-plan"></a>Exécuter le plan de test

[//]: # (Modifier correctement ? « Utilisateur » semblait un peu ambigu pour moi.)
Une fois que l’environnement utilisateur et le service ont été configurés, la dernière étape de test inclut l’exécution du plan de test avec le focus sur la validation des fonctionnalités et des fonctionnalités. 

**Audioconférence les prérequis et les hypothèses de test pour les utilisateurs et les sites dans l’étendue :**

-   La définition de cas d’usage métier pour le service Audioconférence est terminée.

-   Les licences requises pour Audioconférence sont disponibles et ont été attribuées.

-   La liste des sites organisationnels et des groupes d’utilisateurs a été identifiée.

-   La liste des numéros de numérotation d’audioconférence dédiés et partagés avec des préférences linguistiques a été identifiée et configurée.

-   [Les crédits de communication](what-are-communications-credits.md) (si nécessaire) ont été configurés pour votre organisation.

-   Audioconférence paramètres de pont de conférence ont été identifiés et configurés (longueur du code confidentiel, notifications d’entrée/sortie, préférence de notification d’activation).

-   Les stratégies de conférence client et les paramètres de plan de numérotation qui prennent en charge Audioconférence scénarios de numérotation ont été identifiés, configurés et appliqués.

-   Audioconférence exigences de conformité ont été identifiées et configurées.

**Conditions préalables et hypothèses de test des plans d’appel pour les utilisateurs et les sites dans l’étendue :**

-   La définition de cas d’usage métier pour le service Forfaits d’appels est terminée.

-   Les licences requises pour les forfaits d’appels sont disponibles et ont été attribuées.

-   La liste des sites organisationnels et des groupes d’utilisateurs a été identifiée.

-   Téléphone numéros à affecter aux utilisateurs ont été acquis ou portés vers Microsoft et sont disponibles dans le portail du locataire.

-   [Les crédits de communication](what-are-communications-credits.md) (si nécessaire) ont été configurés pour votre organisation.

-   Les stratégies utilisateur client et les paramètres de plan de numérotation qui prennent en charge les scénarios de forfaits d’appels ont été identifiés, configurés et appliqués.

-   Les exigences de conformité des plans d’appel ont été identifiées et configurées.

**Prérequis et hypothèses de test de routage direct pour les utilisateurs et les sites dans l’étendue :**

-   La définition de cas d’usage métier pour le service de routage direct est terminée.

-   Les licences requises pour le routage direct sont disponibles et ont été attribuées.

-   La liste des sites organisationnels et des groupes d’utilisateurs a été identifiée.

-   Un [contrôleur de frontière de session certifié (SBC)](./direct-routing-plan.md#supported-session-border-controllers-sbcs) a été déployé, configuré et associé à Système téléphonique.

-   Enterprise voix a été activée et les numéros de téléphone ont été attribués.

-   Les stratégies de routage vocal ont été identifiées, configurées et affectées.

-   Microsoft Teams a été défini comme client d’appel préféré pour les utilisateurs dans l’étendue.
 
-   Les exigences de conformité au routage direct ont été identifiées et configurées.

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>Points de décision</td><td><ul><li>Déterminez les fonctionnalités de Audioconférence qui seront déployées (décision de service).</li><li>Identifiez les exigences en matière de fonctionnalités utilisateur pour Audioconférence.</li><li>Identifiez les exigences de configuration du service pour Audioconférence.</li><br><li>Déterminez si le routage direct ou les plans d’appel seront déployés et configurés.<li>Déterminez les fonctionnalités de Système téléphonique qui seront déployées (décision de service).</li><li>Identifiez les exigences en matière de fonctionnalités utilisateur pour les forfaits d’appels ou le routage direct.</li><li>Identifiez les exigences de configuration du service pour les plans d’appel ou le routage direct.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Étapes suivantes</td><td><ul><li>Développez et documentez votre approche de plan de test.</li><li>Préparez votre environnement de service et les utilisateurs dans l’étendue pour Audioconférence fonctionnalités.</li><li>Préparez votre environnement de service et les utilisateurs dans l’étendue des forfaits d’appels ou des fonctionnalités de routage direct.</li><li>Exécutez la validation de test pour les fonctionnalités Audioconférence que vous souhaitez activer.</li><li>Exécutez la validation de test pour les plans d’appel ou les fonctionnalités de routage direct que vous souhaitez activer.</li><li>Pour toute défaillance de test, vérifiez que votre configuration est correcte, consultez les articles de la communauté et, le cas échéant, déclenchez un cas de support.</li></ul></td></tr>
</table>


Pour obtenir des instructions détaillées supplémentaires sur la façon d’effectuer des tests pour Audioconférence dans Teams, consultez le [guide de test détaillé pour Audioconférence](./deploy-audio-conferencing-teams-landing-page.md).

Pour obtenir des instructions détaillées supplémentaires sur la façon d’effectuer des tests pour les forfaits d’appels dans Teams, consultez le [guide de test détaillé pour Système téléphonique](./cloud-voice-landing-page.md).

<!--ENDOFSECTION-->