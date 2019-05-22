---
title: Préparer le déploiement du service vocal cloud de Microsoft Teams
author: rmw2890
ms.author: Rowille
manager: serdars
ms.date: 03/18/2019
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: Utilisez les listes de contrôle d’intégration pour préparer Office 365 pour teams et configurer les fonctionnalités principales, la mise en réseau et les charges de travail de l’équipe Cloud.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c2316376bd2dfddce99e63fe4ab66c5e33eb813e
ms.sourcegitcommit: 30995da65ff6a9b33534c3818833cf0ae1952ab9
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/22/2019
ms.locfileid: "34344828"
---
# <a name="prepare-my-service"></a>Préparer mon service

Cet article fournit une vue d’ensemble des exigences relatives à la préparation des services vocaux Cloud pour votre organisation. En préparant correctement, vous pouvez être sûr que vous êtes prêt à fournir des fonctionnalités de voix Cloud à votre organisation.

## <a name="onboarding-checklists-for-microsoft-teams-voice-workloads"></a>Listes de vérification de l’intégration des charges de travail vocales de Microsoft teams

Les listes de vérification suivantes vous guident tout au long des étapes d’implémentation des fonctionnalités de conférence audio, de système téléphonique avec des plans d’appel («plans d’appel») et de routage direct du système téléphonique («routage directe») dans Microsoft Teams.

*  [Préparer Office 365 pour teams](onboarding-checklist-enable-office-365.md)

*  [Configurer les fonctionnalités principales de teams](onboarding-checklist-configure-microsoft-teams-core-capabilities.md)

*  [Configurer la mise en réseau](onboarding-checklist-configure-networking.md)

*  [Configurer des charges de travail vocales Cloud dans teams](onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams.md)

*  [Configurer le routage direct dans teams](onboarding-checklist-configure-direct-routing-in-Microsoft-Teams.md)

Les tâches et les activités de ces listes de vérification constituent les éléments de «tâches de base» qui s’appliquent à tous les déploiements de fonctionnalités de voix Cloud avec Teams. Vous pouvez personnaliser les listes de contrôle de façon à inclure les activités et tâches spécifiques à votre propre équipe.

>[!NOTE]
>Ce guide est axé uniquement sur les offres d’appel, l’audioconférence et le routage direct. Si vous débutez avec Teams, passez en revue la [vue d’ensemble de Microsoft teams](teams-overview.md). Pour obtenir des instructions générales sur la planification du déploiement de teams, commencez par [déployer la discussion, les équipes, les canaux et les applications dans Microsoft teams](deploy-chat-teams-channels-microsoft-teams-landing-page.md).

Utilisez les listes de vérification fournies pour effectuer le suivi de l’état de chacune des activités et tâches individuelles et être sûr de ne pas ignorer les étapes critiques. Chaque activité inclut une description détaillée des actions et références requises pour les informations supplémentaires que vous pouvez utiliser pour effectuer cette activité.

Bien que nous vous recommandons de suivre les listes de vérification dans l’ordre, la séquence exacte dépend de la portée de votre déploiement, de la configuration et de la complexité de votre environnement. Ils sont organisés pour prendre en charge un déploiement d’équipes «Greenfield» (un seul qui ne dispose pas de la présence d’une version précédente de Skype entreprise Online) ou la migration de Skype entreprise Online vers Teams. Si vous effectuez une migration à partir de Skype entreprise Online, vous avez peut-être déjà terminé certaines de ces activités et vous pouvez les ignorer maintenant.

Lorsque vous intégrez des utilisateurs au niveau de chaque site, nous vous conseillons vivement d’utiliser le [Manuel d’utilisation du site pour les appels vocaux (Guide d’utilisation des sites)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) comme guide supplémentaire de ces listes de vérification.

>[!NOTE]
>La plupart des paramètres de configuration sont communs entre teams et Skype entreprise online. Pour configurer ces paramètres, vous devez utiliser le centre d’administration Microsoft 365 et le centre d’administration Microsoft Teams.

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>Points de décision</td><td><ul><li>Qui est responsable de l’affichage des listes de vérification d’intégration?</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Étapes suivantes</td><td><ul><li>Téléchargez les listes de vérification de l’intégration.</li><li>Parcourez les éléments de liste de vérification d’intégration conformément au plan de déploiement de votre organisation.</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="continue-onboarding"></a>Poursuite de l’intégration

Après avoir effectué ces listes de vérification, vous aurez bien ajouté les fonctionnalités de voix à votre déploiement d’équipes.

À l’étape suivante, utilisez le [Manuel d’utilisation du site pour les appels vocaux](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) pour vous aider à intégrer vos utilisateurs sur chaque site et à veiller à planifier et à exécuter des activités importantes de votre site.

-   Site prêt par le plan de déploiement du site

-   Définir le processus de gestion des services

-   Exécution des tests et de la correction

<!--ENDOFSECTION-->

## <a name="test-cloud-voice-workloads-in-teams"></a>Test des charges de travail vocales Cloud dans teams

Une fois que vous avez défini et documenté les plans de réussite et de mise en œuvre technique de votre équipe dans le centre d’administration, l’étape suivante consiste à confirmer que votre organisation a effectué la configuration souhaitée. les attentes et les exigences sont satisfaites par le biais des fonctionnalités, des fonctionnalités et de la facilité d’utilisation. Avant de déployer un déploiement pilote ou final dans votre environnement de production, vous devez effectuer cette étape de validation.

Vous pouvez utiliser le plan de réussite pour les entreprises que vous avez défini lors de la phase enVision afin de baser la détermination des activités, des attentes, des cas de test des fonctionnalités et des fonctionnalités ainsi que de l’étendue globale de la phase de test.

## <a name="define-your-testing-approach"></a>Définir votre approche de test

Dans sa forme la plus simple, votre approche de test est basée sur les fonctionnalités de la fonction d’audioconférence, des plans d’appel ou du service de routage direct, et le développement d’un plan de test pour vérifier que les exigences relatives aux fonctionnalités sont satisfaites pour les utilisateurs concernés. Voici un exemple de plan de test pour la phase intégrée d’une implémentation de l’audioconférence.


| Fonction de conférence audio à tester | Résumé des résultats | Remarques supplémentaires |
|------------|-----------------|------------------|
| Planifier une réunion teams ad hoc contenant des informations de conférence rendez-vous | Réussite/échec   | DÉFINIR |
| Utiliser un téléphone pour la partie audio d’une réunion en composant une réunion à partir du RTC grâce aux informations de connexion fournies | Réussite/échec | DÉFINIR |
| Joindre d’autres personnes à une réunion existante en composant un numéro de téléphone via le RTC | Réussite/échec | DÉFINIR |



| Fonction d’appel ou plan de routage direct à tester | Résumé des résultats | Remarques supplémentaires |
|----------------------------------------------------|-----------------|------------------|
| Passer un appel RTC en composant un numéro PSTN       | Réussite/échec       | DÉFINIR |
| Recevez un appel RTC en composant votre numéro RTC depuis une ligne externe (mobile, fixe) | Réussite/échec | DÉFINIR|
| Transférer un appel PSTN d’un utilisateur de teams vers un autre | Réussite/échec | DÉFINIR |


>[!TIP]
>Pour vous aider à effectuer des tests de création de cas de test en tant que point de départ, consultez la liste des recommandations en matière d’utilisateurs disponibles aux [réunions et aux appels d’équipe](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8#bkmk_havingmeetings).

<!--ENDOFSECTION-->

## <a name="set-up-cloud-voice-workloads-for-teams"></a>Configuration des charges de travail de voix Cloud pour teams

À présent que vous avez défini votre approche de test, l’étape suivante consiste à configurer votre environnement de services et vos utilisateurs dans le cadre des fonctionnalités de voix Cloud de teams.

Pour plus d’informations, consultez:

- [Planification technique de l’audioconférence](audio-conferencing.md#technical-planning-for-audio-conferencing)

- [Configurer Audioconférence pour Microsoft Teams](set-up-audio-conferencing-in-teams.md)

- [Planification technique du système téléphonique avec les offres d’appels](calling-plan-landing-page.md)

- [Configuration de forfaits d’appels pour Skype entreprise et Microsoft teams](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

- [Planifier le routage direct](https://docs.microsoft.com/microsoftteams/direct-routing-plan)

- [Configurer le routage direct](https://docs.microsoft.com/microsoftteams/direct-routing-configure)

### <a name="execute-the-test-plan"></a>Exécuter le plan de test

[//]: # (Puis-je modifier mon profil? «L’utilisateur» semblait un peu ambigu.)
Après la configuration de l’environnement de l’utilisateur et du service, la dernière étape de test inclut l’exécution du plan de test avec le focus sur la validation des fonctionnalités et des fonctionnalités. 

**Conditions préalables et hypothèses de test de l’audioconférence pour les utilisateurs et sites dans l’étendue:**

-   La définition d’un cas d’utilisation professionnelle pour le service de conférence audio a été effectuée.

-   Une licence est requise pour les conférences audio et est affectée.

-   La liste des sites d’entreprise et des groupes d’utilisateurs a été identifiée.

-   La liste des numéros de téléphone de conférence rendez-vous et des numéros en fonction de la langue que vous avez choisie a été identifiée et configurée.

-   [Crédits de communication](what-are-communications-credits.md) (si nécessaire) ont été configurés pour votre organisation.

-   Les paramètres du pont de conférence audio ont été identifiés et configurés (longueur du code confidentiel, notifications d’entrée/sortie, préférence d’activation de notification).

-   Les stratégies de conférences client et les paramètres de plan de numérotation qui prennent en charge les scénarios de numérotation de l’audioconférence peuvent être identifiés, configurés et appliqués.

-   Les exigences en matière de conformité de l’audioconférence ont été identifiées et configurées.

**Offres d’appel tests requis et hypothèses pour les utilisateurs et sites dans l’étendue:**

-   La définition d’un cas d’utilisation professionnelle pour le Service plans d’appel a été effectuée.

-   Les licences nécessaires pour les plans d’appel sont disponibles et ont été attribuées.

-   La liste des sites d’entreprise et des groupes d’utilisateurs a été identifiée.

-   Les numéros de téléphone à attribuer à des utilisateurs ou qui ont été portés à Microsoft et sont disponibles sur le portail du client.

-   [Crédits de communication](what-are-communications-credits.md) (si nécessaire) ont été configurés pour votre organisation.

-   Les stratégies utilisateur client et les paramètres de plan de numérotation prenant en charge les scénarios d’appel d’offres sont identifiés, configurés et appliqués.

-   Les plans d’appel doivent avoir été identifiés et configurés.

**Conditions préalables et hypothèses de test de routage directes pour les utilisateurs et sites dans l’étendue:**

-   La définition de cas d’utilisation professionnelle pour le service de routage direct a été effectuée.

-   La licence requise pour le routage direct est disponible et affectée.

-   La liste des sites d’entreprise et des groupes d’utilisateurs a été identifiée.

-   Un [contrôleur de bordure de session (SBC) certifié](https://docs.microsoft.com/microsoftteams/direct-routing-plan#supported-session-border-controllers-sbcs) a été déployé, configuré et associé au système téléphonique.

-   La voix entreprise est activée et les numéros de téléphone ont été attribués.

-   Les stratégies de routage de la voix ont été identifiées, configurées et attribuées.

-   Microsoft teams a été défini comme client appelant préféré pour les utilisateurs de l’étendue.
 
-   Les exigences en matière de conformité au routage direct ont été identifiées et configurées.

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>Points de décision</td><td><ul><li>Déterminez les fonctionnalités de la fonctionnalité de conférence audio qui seront déployées (décision du service).</li><li>Identifiez les exigences de fonctionnalités des utilisateurs pour les conférences audio.</li><li>Identifiez les exigences de configuration de service pour les conférences audio.</li><br><li>Déterminez si les plans de routage ou d’appel directs seront déployés et configurés.<li>Déterminez les fonctionnalités de fonctionnalités de système téléphonique qui seront déployées (décision de service).</li><li>Identifiez les exigences de fonctionnalités des utilisateurs pour les appels d’offres ou le routage direct.</li><li>Identifiez les exigences de configuration de service pour les abonnements d’appels ou le routage direct.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Étapes suivantes</td><td><ul><li>Développez et documentez l’approche de votre plan de test.</li><li>Préparez votre environnement et vos utilisateurs à l’étendue des fonctionnalités de conférence audio.</li><li>Préparez votre environnement et vos utilisateurs dans le cadre des appels d’offres ou du routage direct.</li><li>Exécutez la validation de test pour les fonctionnalités de conférence audio que vous souhaitez activer.</li><li>Exécutez la validation de test pour les offres d’appels ou les fonctionnalités de routage directes que vous souhaitez activer.</li><li>Pour les échecs de test, vérifiez que votre configuration est correcte, consultez les Articles de la communauté et, si nécessaire, déclenchez une demande de support.</li></ul></td></tr>
</table>


Pour obtenir des instructions détaillées supplémentaires sur l’exécution de tests pour l’audioconférence dans Teams, voir le [Guide de test détaillé pour audioconférence](onboarding-test-plan-for-enterprises-Audio-Conferencing.md).

Pour obtenir des instructions détaillées supplémentaires sur l’exécution de tests pour les plans d’appel dans Teams, voir le [Guide de test détaillé du système téléphonique](onboarding-test-plan-for-enterprises-Phone-System.md).

<!--ENDOFSECTION-->
