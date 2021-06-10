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
description: Utilisez des listes de contrôle d’intégration pour préparer Microsoft 365 ou Office 365 messagerie pour Teams et configurer vos principales fonctionnalités, votre réseau et Teams charges de travail vocales dans le cloud.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 42ded974ba5f4400bdcb5796410a8277fbed4488
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103970"
---
# <a name="prepare-my-service"></a>Préparer mon service

Cet article donne une vue d’ensemble des conditions requises pour préparer les services vocaux cloud pour votre organisation. En vous préparez correctement, vous êtes certain d’être prêt à fournir des fonctionnalités de voix cloud à votre organisation.

## <a name="onboarding-checklists-for-microsoft-teams-voice-workloads"></a>Listes de contrôle d’intégration pour Microsoft Teams charges de travail vocales

Les listes de contrôle suivantes vous expliquent les étapes d’implémentation des fonctionnalités d’audioconférence, de Système téléphonique avec les plans d’appel (« plans d’appels ») et de routage direct Système téléphonique (« Routage direct ») dans Microsoft Teams.

*  [Préparer Microsoft 365 ou Office 365'Teams](onboarding-checklist-enable-office-365.md)

*  [Configurer Teams principales fonctionnalités](onboarding-checklist-configure-microsoft-teams-core-capabilities.md)

*  [Préparer votre réseau](prepare-network.md)

*  [Configurer les charges de travail vocales dans le cloud Teams](onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams.md)

*  [Configurer le routage direct dans Teams](onboarding-checklist-configure-direct-routing-in-Microsoft-Teams.md)

Les tâches et activités de ces listes de vérification sont les principales « choses à faire » qui s’appliquent à chaque déploiement de fonctionnalités vocales cloud avec Teams. Vous pouvez personnaliser les listes de vérification pour inclure les activités et tâches spécifiques à votre parcours Teams personnel.

>[!NOTE]
>Ces conseils portent uniquement sur les plans d’appels, l’audioconférence et le routage direct. Si vous débutez sur Teams, voir [Vue d’ensemble de Microsoft Teams.](teams-overview.md) Pour obtenir des instructions générales sur la planification de votre déploiement Teams, commencez par déployer la conversation, les équipes, les canaux et les [applications Microsoft Teams.](deploy-chat-teams-channels-microsoft-teams-landing-page.md)

Utilisez les listes de vérification fournies pour suivre l’état de chaque activité et tâche individuelle, et pour vous assurer que vous n’avez pas ignoré les étapes critiques. Chaque activité inclut une description détaillée des actions requises et des références à des informations supplémentaires que vous pouvez utiliser pour effectuer cette activité.

Bien qu’il soit recommandé de suivre les listes de vérification dans l’ordre, la séquence exacte dépend de l’étendue de votre déploiement, de la configuration et de la complexité de votre environnement. Ils sont organisés pour prendre en charge un déploiement Teams « champ vert » (c’est-à-dire, un déploiement sans présence Skype Entreprise Online précédente) ou la migration de Skype Entreprise Online vers Teams. Si vous migrez à partir d’Skype Entreprise Online, vous avez peut-être déjà effectué certaines de ces activités et pouvez les ignorer maintenant.

Lorsque vous intégration des utilisateurs sur une base par site, nous vous recommandons vivement d’utiliser le manuel d' allocation du site pour [Voix](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) comme guide supplémentaire pour ces listes de vérification.

>[!NOTE]
>La plupart des paramètres de configuration sont courants entre Teams et Skype Entreprise Online. Pour configurer ces paramètres, Microsoft 365 centre d’administration Microsoft Teams et le Centre d’administration central.

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>Points de décision</td><td><ul><li>Qui responsable de la surveillance de l’achèvement des listes de vérification d’intégration ?</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Étapes suivantes</td><td><ul><li>Téléchargez les listes de contrôle d’intégration.</li><li>Travaillez sur les éléments de liste de vérification d’intégration étape par étape, conformément au plan de déploiement de votre organisation.</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="continue-onboarding"></a>Continuer l’intégration

Une fois ces listes de vérification terminées, vous aurez ajouté des fonctionnalités vocales à votre Teams déploiement.

Dans l’étape suivante, utilisez le manuel d’enablement de site pour voix [pour](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) vous aider à intégrer vos utilisateurs sur chaque site et vous assurer que vous planifiez et exécutez des activités importantes spécifiques au site.

-   Site prêt par plan de déploiement de site

-   Établir le processus de gestion des services

-   Exécuter des tests et des corrections

<!--ENDOFSECTION-->

## <a name="test-cloud-voice-workloads-in-teams"></a>Tester les charges de travail vocales dans le cloud Teams

Après avoir défini et documenté vos plans de réussite et d’implémentation technique de voix cloud Teams dans le cadre de la phase de conception et d’entreprendre la configuration que vous souhaitez dans le Centre d’administration, l’étape suivante consiste à vérifier que les attentes et besoins de votre organisation sont satisfaits par le biais de fonctionnalités et d’utilisation. Vous devez effectuer cette étape de validation avant de déployer un déploiement pilote ou final dans votre environnement de production.

Vous pouvez tirer parti du plan de réussite des entreprises que vous avez défini au cours de la phase de conception pour servir de base à la détermination des activités, des attentes, des cas de test des fonctionnalités et de l’étendue globale à évaluer au cours de la phase de test.

## <a name="define-your-testing-approach"></a>Définir votre approche de test

Dans sa forme la plus simple, votre approche de test est basée sur votre examen des fonctionnalités de l’audioconférence, des plans d’appel ou du service de routage direct, et le développement d’un plan de test pour vérifier que vos exigences de fonctionnalité sont remplies pour les utilisateurs dans l’étendue. Voici un exemple de plan de test pour la phase Intégration d’une implémentation d’audioconférence.


| Fonctionnalité d’audioconférence à tester | Résumé des résultats | Notes supplémentaires |
|------------|-----------------|------------------|
| Planifier une réunion de réunion Teams conférence audio avec des informations de connexion ad hoc | Réussi/Échec   | TBD |
| Utiliser un téléphone pour la piste audio d’une réunion en composant un numéro de téléphone pour se composer d’une réunion à partir du RSTN avec les informations d’accès fournies | Réussi/Échec | TBD |
| Rejoindre d’autres personnes à une réunion existante en composant un numéro sortant via le réseau PSTN | Réussi/Échec | TBD |



| Forfaits d’appels ou fonctionnalité de routage direct à tester | Résumé des résultats | Notes supplémentaires |
|----------------------------------------------------|-----------------|------------------|
| Effectuer un appel RSTN en composant un numéro PSTN       | Réussi/Échec       | TBD |
| Recevoir un appel PSTN en composant votre numéro PSTN à partir d’une ligne externe (mobile, fixe) | Réussi/Échec | TBD|
| Transférer un appel PSTN d’un Teams utilisateur à un autre | Réussi/Échec | TBD |


>[!TIP]
>Pour vous aider à créer des cas de test comme point de départ, consultez la liste des conseils d’utilisateur disponibles Teams [réunions et appels.](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8#bkmk_havingmeetings)

<!--ENDOFSECTION-->

## <a name="set-up-cloud-voice-workloads-for-teams"></a>Configurer les charges de travail vocales cloud pour les Teams

À présent que vous avez défini votre approche de test, l’étape suivante consiste à configurer votre environnement de service et les utilisateurs dans l’étendue Teams fonctionnalités vocales cloud.

Pour plus d’informations, voir :

- [Planification technique de l’audioconférence](./cloud-voice-landing-page.md)

- [Configurer Audioconférence pour Microsoft Teams](set-up-audio-conferencing-in-teams.md)

- [Planification technique pour les Système téléphonique’aide de forfaits d’appels](calling-plan-landing-page.md)

- [Configurer des forfaits d’appels Skype Entreprise et Microsoft Teams](/skypeforbusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

- [Planifier le routage direct](./direct-routing-plan.md)

- [Configurer le routage direct](./direct-routing-configure.md)

### <a name="execute-the-test-plan"></a>Exécuter le plan de test

[//]: # (Modification d’accord ? « Utilisateur » me paraît un peu ambigu.)
Une fois l’environnement utilisateur et le service configurés, la dernière étape du test inclut l’exécution du plan de test, avec l’accent sur la validation des fonctionnalités et des fonctionnalités. 

**Test de l’audioconférence - Conditions préalables et hypothèses pour les utilisateurs et sites dans l’étendue :**

-   La définition des cas d’utilisation professionnelle du service d’audioconférence est terminée.

-   La licence requise pour l’audioconférence est disponible et a été attribuée.

-   La liste des sites organisationnels et des groupes d’utilisateurs a été identifiée.

-   La liste des numéros d’accès d’audioconférence dédiés et partagés avec une préférence de langue a été identifiée et configurée.

-   [Les crédits de](what-are-communications-credits.md) communication (le cas échéant) ont été créés pour votre organisation.

-   Les paramètres du pont de conférence Audioconférence ont été identifiés et configurés (longueur du code confidentiel, notifications d’entrée/sortie, préférence de notification d’enablement).

-   Les stratégies de conférence client et les paramètres de plan de numérotation qui supportent les scénarios d’appel sortant d’audioconférence ont été identifiés, configurés et appliqués.

-   Les exigences de conformité relatives à l’audioconférence ont été identifiées et configurées.

**Plans d’appel testant les conditions préalables et les hypothèses pour les utilisateurs et sites dans l’étendue :**

-   La définition des cas d’utilisation professionnelle du service Plans d’appels est terminée.

-   La licence requise pour les forfaits d’appels est disponible et a été attribuée.

-   La liste des sites organisationnels et des groupes d’utilisateurs a été identifiée.

-   Téléphone des numéros à attribuer aux utilisateurs ont été acquis ou portés à Microsoft et sont disponibles dans le portail client.

-   [Les crédits de](what-are-communications-credits.md) communication (le cas échéant) ont été créés pour votre organisation.

-   Les stratégies utilisateur client et les paramètres de plan de numérotation qui supportent les scénarios de plans d’appels ont été identifiés, configurés et appliqués.

-   Les exigences de conformité relatives aux plans d’appels ont été identifiées et configurées.

**Test direct du routage : conditions préalables et hypothèses pour les utilisateurs et sites dans l’étendue :**

-   La définition des cas d’utilisation professionnelle du service de routage direct est terminée.

-   La licence requise pour le routage direct est disponible et a été attribuée.

-   La liste des sites organisationnels et des groupes d’utilisateurs a été identifiée.

-   Un contrôleur de bordure de session certifié [(SBC)](./direct-routing-plan.md#supported-session-border-controllers-sbcs) a été déployé, configuré et couplé avec Système téléphonique.

-   Enterprise la voix est activée et les numéros de téléphone ont été affectés.

-   Les stratégies de routage voix ont été identifiées, configurées et attribuées.

-   Microsoft Teams a été définie comme client d’appel préféré pour les utilisateurs dans l’étendue.
 
-   Des exigences de conformité au routage direct ont été identifiées et configurées.

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>Points de décision</td><td><ul><li>Déterminez les fonctionnalités d’audioconférence qui seront déployées (décision de service).</li><li>Identifiez les conditions requises pour la fonctionnalité d’audioconférence.</li><li>Identifiez les exigences de configuration du service pour l’audioconférence.</li><br><li>Décidez si les plans de routage direct ou d’appel seront déployés et configurés.<li>Décidez Système téléphonique fonctionnalités seront déployées (décision de service).</li><li>Identifiez les fonctionnalités requises pour les plans d’appel ou le routage direct.</li><li>Identifiez les exigences de configuration du service pour les plans d’appel ou le routage direct.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Étapes suivantes</td><td><ul><li>Développez et documentez votre approche de plan de test.</li><li>Préparez votre environnement de service et les utilisateurs dans l’étendue des fonctionnalités d’audioconférence.</li><li>Préparez votre environnement de service et les utilisateurs dans l’étendue des plans d’appels ou des fonctionnalités de routage direct.</li><li>Exécutez la validation de test pour les fonctionnalités d’audioconférence que vous voulez activer.</li><li>Exécutez la validation de test pour les plans d’appel ou les fonctionnalités de routage direct que vous voulez activer.</li><li>En cas d’échec du test, confirmez que votre configuration est correcte, examinez les articles de la communauté et, si nécessaire, constituez un cas de support.</li></ul></td></tr>
</table>


Pour obtenir des instructions détaillées supplémentaires sur l’évaluation de l’audioconférence dans Teams, consultez le guide de test détaillé de [l’audioconférence.](./deploy-audio-conferencing-teams-landing-page.md)

Pour obtenir des instructions détaillées supplémentaires sur la façon d’effectuer des tests pour les plans d’appel dans Teams, consultez le guide de [test](./cloud-voice-landing-page.md)détaillé pour Système téléphonique.

<!--ENDOFSECTION-->