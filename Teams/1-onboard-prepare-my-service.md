---
title: Préparer le déploiement du service vocal cloud de Microsoft Teams
author: rmw2890
ms.author: MyAdvisor
manager: serdars
ms.date: 09/11/2018
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: Utilisez des listes de vérification embarquement préparer Office 365 pour les équipes et la configuration des fonctionnalités principales d’équipes, mise en réseau et les charges de travail voix en nuage.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 203a819eb3732d37aa65f92372eb21ffd59aea08
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/07/2019
ms.locfileid: "30462067"
---
# <a name="prepare-my-service"></a>Préparer mon service

Cet article donne une vue d’ensemble de la configuration requise pour la préparation des services de téléphonie pour votre organisation en nuage. Préparer correctement, vous pouvez être que vous êtes prêt à fournir la communication vocale à votre organisation en nuage.

## <a name="onboarding-checklists-for-microsoft-teams-voice-workloads"></a>Intégration des listes de contrôle pour Microsoft Teams vocale des charges de travail

Listes de vérification suivantes vous guident tout au long de la procédure pour l’implémentation de conférence Audio, système téléphonique avec l’appel (« appel Plans ») des Plans et fonctionnalités téléphone système routage Direct (« routage Direct ») dans Microsoft Teams.

*  [Préparation d’Office 365 pour les équipes](onboarding-checklist-enable-office-365.md)

*  [Configurer les fonctionnalités principales d’équipes](onboarding-checklist-configure-microsoft-teams-core-capabilities.md)

*  [Configurer la mise en réseau](onboarding-checklist-configure-networking.md)

*  [Configurer des charges de travail dans le nuage vocale dans les équipes](onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams.md)

*  [Configurer le routage Direct dans les équipes](onboarding-checklist-configure-direct-routing-in-Microsoft-Teams.md)

Les tâches et activités dans ces listes de contrôle sont les éléments principaux « tâches » qui s’appliquent à chaque déploiement de fonctionnalités vocales de nuage avec les équipes. Vous pouvez personnaliser les listes de vérification pour inclure les activités et les tâches qui sont spécifiques à votre propre parcours équipes.

>[!NOTE]
>Ce guide porte uniquement sur les Plans de l’appel, conférence Audio et au routage Direct. Si vous êtes novice en équipes, consultez [Vue d’ensemble des équipes de Microsoft](teams-overview.md). Pour obtenir des instructions générales pour la planification de votre déploiement d’équipes, commencer par [déployer conversation, équipes, les canaux et applications dans les équipes Microsoft](deploy-chat-teams-channels-microsoft-teams-landing-page.md).

Utilisez les listes de vérification fournies pour suivre l’état de chaque tâche et de l’activité individuelle et effectué pour vous assurer que toutes les étapes critiques. Chaque activité comprend une description détaillée des actions requises et des références à des informations supplémentaires que vous pouvez utiliser pour effectuer cette activité.

Bien que nous vous conseillons de suivre les listes de contrôle dans l’ordre, l’ordre exact dépend de l’étendue de votre déploiement et de la configuration et la complexité de votre environnement. Elles sont organisées pour prendre en charge soit une » dans un environnement vierge » des équipes de déploiement (une avec aucun Skype précédent de la présence en ligne Business) ou la migration à partir de Skype pour Business Online aux équipes. Si vous migrez à partir de Skype pour Business Online, vous pourrez avoir déjà effectué certaines de ces activités et pourrez ignorer maintenant.

Lorsque vous êtes embarquement utilisateurs sur site par site, que nous vous recommandons vivement d’utiliser la [Lecture d’activation de Site pour la voix (lecture)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) comme un guide supplémentaire à ces listes de contrôle.

>[!NOTE]
>La plupart des paramètres de configuration sont communes entre les équipes et Skype pour Business Online. Vous utilisez le centre d’administration centre d’administration d’Office 365 et Microsoft Teams pour configurer ces paramètres.

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/> <br/>Points de décision</td><td><ul><li>Qui sera responsable de la surveillance de l’exécution de l’intégration des listes de contrôle ?</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Étapes suivantes</td><td><ul><li>Télécharger les listes de vérification embarquement.</li><li>Parcourez les éléments de liste de vérification embarquement détaillées conformément au plan de déploiement de votre organisation.</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="continue-onboarding"></a>Continuez d’intégration

Après avoir terminé ces listes de contrôle, vous allez avez ajouté des fonctionnalités vocales pour votre déploiement d’équipes.

L’étape suivante, utilisez la [Lecture d’activation de Site pour la voix (lecture)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) pour vous aider intégrée à vos utilisateurs sur chaque site et vous assurer que vous planifier et exécutez des activités spécifiques au site importantes.

-   Plan de déploiement de Site par Site prêt

-   Établir un processus de gestion de Service

-   Exécutez le test et correction

<!--ENDOFSECTION-->

## <a name="test-cloud-voice-workloads-in-teams"></a>Test cloud voix des charges de travail en équipe

Après avoir défini et documenté vos équipes cloud voix entreprise réussite et les techniques de mise en œuvre dans le cadre de la phase de prévoir et entreprendre la configuration souhaitée dans le centre d’administration, l’étape suivante consiste à confirmer que votre organisation attentes et les exigences sont remplies par le biais de fonctionnalités, les fonctionnalités et les possibilités d’utilisation. Vous devez effectuer cette étape de validation avant de déployer un déploiement pilote ou final dans votre environnement de production.

Vous pouvez vous appuyer sur le plan de réussite définis lors de la phase de prévoir pour servir de base pour déterminer les activités, les attentes, caractéristiques et fonctionnalités des cas de test et étendue globale pour être évaluée pendant la phase de test.

## <a name="define-your-testing-approach"></a>Définir votre approche de test

Dans sa forme la plus simple, votre approche de test est basée sur votre examen les fonctionnalités de conférence Audio, des Plans de l’appel, ou planifier le service de routage Direct et développement d’un test vérifier que vos besoins de fonctionnalités sont remplies pour les utilisateurs dans l’étendue. Vous trouverez ci-dessous un plan de test d’exemple pour la phase d’une implémentation de services d’audioconférence intégrée.


| Fonctionnalité de conférence audio à tester | Résumé des résultats | Remarques supplémentaires |
|------------|-----------------|------------------|
| Planifier une réunion ad hoc équipes qui contient les informations d’audioconférence rendez-vous | Réussite/échec   | TBD |
| Utiliser un téléphone pour la réunion audio en vous connectant à une réunion à partir de la passerelle PSTN avec les informations de numérotation fournies | Réussite/échec | TBD |
| Participer à d’autres personnes à une réunion existante à un appel sortant via le réseau téléphonique commuté | Réussite/échec | TBD |



| Plans d’appel ou de routage Direct des fonctionnalités à tester | Résumé des résultats | Remarques supplémentaires |
|----------------------------------------------------|-----------------|------------------|
| Émettre un appel RTC en composant un numéro RTC       | Réussite/échec       | TBD |
| Recevoir un appel RTC par votre numérotation PSTN à partir d’une ligne externe (mobile, fixe) | Réussite/échec | TBD|
| Transférer un appel PSTN d’un utilisateur d’équipes à un autre | Réussite/échec | TBD |


>[!TIP]
>Pour faciliter la création des cas de test comme point de départ, voir la liste des [équipes de réunions et appels](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8#bkmk_havingmeetings)disponible Guide de l’utilisateur.

<!--ENDOFSECTION-->

## <a name="set-up-cloud-voice-workloads-for-teams"></a>Configurer des charges de travail voix dans le nuage pour les équipes

Maintenant que vous avez défini votre approche de test, l’étape suivante consiste à configurer votre environnement de service et les utilisateurs dans la portée de fonctionnalités vocales de nuage équipes.

Pour plus d’informations, voir :

- [Planification technique de l’audioconférence](audio-conferencing.md#technical-planning-for-audio-conferencing)

- [Configurer la conférence Audio pour Skype entreprise et Teams Microsoft](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/set-up-audio-conferencing)

- [Techniques de planification du système téléphonique avec les Plans d’appel](calling-plan-landing-page.md)

- [Configurer des Plans de l’appel pour Skype pour les entreprises et Microsoft Teams](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

- [Planifier le routage direct](https://docs.microsoft.com/microsoftteams/direct-routing-plan)

- [Configurer le routage direct](https://docs.microsoft.com/microsoftteams/direct-routing-configure)

### <a name="execute-the-test-plan"></a>Exécuter le plan de test

[//]: # (OK modifier ? « Utilisateur » semblaient un peu ambigu pour moi.)
Une fois que l’environnement de l’utilisateur et le service ont été configurés, la dernière étape de test inclut l’exécution du plan de test ayant le focus sur la validation des fonctionnalités. 

**Test des conditions préalables et hypothèses pour les utilisateurs et les sites dans l’étendue de conférence audio :**

-   Entreprise utiliser la définition de cas pour la conférence Audio service a été effectué.

-   Licences requises pour une audioconférence est disponible et a été affecté.

-   La liste des sites d’organisation et des groupes d’utilisateurs ont été identifiés.

-   La liste des dédié et partagés audioconférence rendez-vous numéros avec préférence linguistique ont été identifiés et configuré.

-   [Communications générique](what-are-communications-credits.md) (si nécessaire) ont été configurés pour votre organisation.

-   Paramètres pont de conférence audio conférence ont été identifiés et configuré (longueur du code confidentiel, les notifications d’entrée/sortie, préférence de notification d’activation).

-   Stratégies de conférence des clients et planifier les paramètres qui prennent en charge la conférence rendez-vous scénarios identifiés, configurés et appliqués de numérotation.

-   Exigences de conformité de conférence audio ont été identifiés et configurés.

**L’appel de Plans de test des conditions préalables et hypothèses pour les utilisateurs et les sites dans l’étendue :**

-   Entreprise utiliser la définition de cas pour l’appel des Plans de service a été effectué.

-   Licences requises pour l’appel des Plans est disponible et a été affecté.

-   La liste des sites d’organisation et des groupes d’utilisateurs ont été identifiés.

-   Numéros de téléphone à attribuer aux utilisateurs qui ont été acquis ou prise en charge par Microsoft et qui sont disponibles dans le portail client.

-   [Communications générique](what-are-communications-credits.md) (si nécessaire) ont été configurés pour votre organisation.

-   Stratégies de client utilisateur et les paramètres de plan de numérotation qui prennent en charge les scénarios d’appel de Plans ont été identifiés, configurés et appliqués.

-   Plans d’exigences de conformité ont été identifiés et configurés l’appel.

**Routage direct test des conditions préalables et hypothèses pour les utilisateurs et les sites dans l’étendue :**

-   Entreprise utiliser la définition de cas pour le routage Direct service a été effectué.

-   Licences requises pour le routage directe est disponible et a été affecté.

-   La liste des sites d’organisation et des groupes d’utilisateurs ont été identifiés.

-   Un [certifié contrôleur de session en périphérie (SBC)](https://docs.microsoft.com/microsoftteams/direct-routing-plan#supported-session-border-controllers-sbcs) a été déployé, configuré et associé à un système téléphonique.

-   Voix entreprise a été activé, et les numéros de téléphone ont été attribués.

-   Stratégies de routage voix ont été identifiés, configurés et affectés.

-   Microsoft Teams a été défini en tant que client appelant par défaut pour les utilisateurs dans l’étendue.
 
-   Exigences de conformité de routage directs ont été identifiés et configurés.

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/> <br/>Points de décision</td><td><ul><li>Déterminer les fonctionnalités de conférence Audio seront déployées (décision de service).</li><li>Identifiez les exigences de fonctionnalités utilisateur pour une audioconférence.</li><li>Identifiez les exigences de configuration de service pour une audioconférence.</li><br><li>Décider si routage Direct ou des Plans de l’appel sera déployés et configurés.<li>Déterminer les fonctionnalités du système téléphonique seront déployées (décision de service).</li><li>Identifiez les exigences de fonctionnalités utilisateur pour l’appel des Plans ou routage Direct.</li><li>Identifier le besoin de configuration de service pour l’appel des Plans ou routage Direct.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Étapes suivantes</td><td><ul><li>Développez et documentez votre approche de plan de test.</li><li>Préparer votre environnement de service et les utilisateurs dans la portée de fonctionnalités de conférence Audio.</li><li>Préparer votre environnement de service et les utilisateurs dans l’étendue pour les fonctionnalités de routage Direct ou de Plans de l’appel.</li><li>Exécuter le test de validation pour les fonctionnalités de conférence Audio que vous souhaitez activer.</li><li>Exécuter le test de validation pour les fonctionnalités de routage Direct ou de Plans de l’appel que vous souhaitez activer.</li><li>Pour les échecs de test, vérifiez que votre configuration est correcte, passez en revue les articles de la Communauté, et, si nécessaire, génère une demande de support.</li></ul></td></tr>
</table>


Pour plus d’instructions détaillées sur la façon d’effectuer les tests pour une audioconférence dans les équipes, voir le [détaillées test guide pour une audioconférence](onboarding-test-plan-for-enterprises-Audio-Conferencing.md).

Pour plus d’instructions détaillées sur la façon d’effectuer les tests de l’appel des Plans dans les équipes, voir le [détaillées test guide pour le système téléphonique](onboarding-test-plan-for-enterprises-Phone-System.md).

<!--ENDOFSECTION-->
