---
title: Préparation au déploiement du service vocal de cloud Microsoft Teams
author: rmw2890
ms.author: MyAdvisor
manager: lehewe
ms.date: 03/13/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: Intégration de listes de contrôle permet de préparer Office 365 pour les équipes et les équipes dotées de fonctionnalités fondamentales, mise en réseau, de configurer et charges de travail de voix en nuage.
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: a2b3d68d63661c988116f3b6729656eb3f34cf37
ms.sourcegitcommit: b985035b91ebd7ceff8d50e9e0fa9aa6ff971f3a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/15/2018
---
# <a name="prepare-my-service"></a>Préparer mon service

## <a name="onboarding-checklists-for-microsoft-teams-voice-workloads"></a>Intégration de listes de contrôle pour les charges de travail Teams de Microsoft voice

Les listes de contrôle suivantes vous guident dans les étapes d’implémentation d’audioconférence et système téléphonique avec les Plans d’appel de fonctions dans Teams de Microsoft.

*  [Préparer Office 365 pour les équipes](https://docs.microsoft.com/MicrosoftTeams/onboarding-checklist-enable-office-365)

*  [Configurer les fonctionnalités de base des équipes](https://docs.microsoft.com/MicrosoftTeams/onboarding-checklist-configure-microsoft-teams-core-capabilities)

*  [Configuration réseau](https://docs.microsoft.com/MicrosoftTeams/onboarding-checklist-configure-networking)

*  [Configurer nuage voix des charges de travail en équipe](https://docs.microsoft.com/MicrosoftTeams/onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams)

Les tâches et les activités dans ces listes de contrôle sont les éléments de « action » de base qui s’appliquent à chaque déploiement de fonctionnalités vocales de nuage avec les équipes. Vous pouvez personnaliser les listes de contrôle pour inclure les activités et les tâches qui sont spécifiques à votre propre parcours d’équipes.

>[!NOTE]
>Ce guide se concentre uniquement sur le système téléphonique avec les Plans d’appel et audioconférence. Si vous êtes novice en équipes, consultez [Vue d’ensemble des équipes de Microsoft](https://docs.microsoft.com/MicrosoftTeams/teams-overview). Pour obtenir des instructions générales pour la planification de votre déploiement d’équipes, consultez le [Guide de planification et les équipes Microsoft](https://docs.microsoft.com/MicrosoftTeams/quick-start-enable-teams).

Utilisez les listes de contrôle fournies pour suivre l’état de chaque tâche et chaque activité individuelle, et pour vous assurer que vous n’avez pas ignoré les étapes critiques. Chaque activité comprend une description détaillée des actions requises et des références vers des informations supplémentaires que vous pouvez utiliser pour terminer cette activité.

Bien que nous vous recommandons de suivre les listes de contrôle dans l’ordre, l’ordre exact dépend de la portée de votre déploiement et de la configuration et de la complexité de votre environnement. Elles sont organisées en charge soit un « nouveau » des équipes de déploiement (une avec aucun précédent Skype présence commerciale en ligne) ou à la migration à partir de Skype pour Business Online aux équipes. Si vous migrez à partir de Skype pour professionnels en ligne, vous avez peut-être déjà réalisé certaines de ces activités et les ignorer maintenant.

Lorsque vous avez des utilisateurs arrivant sur une base site par site, que nous vous recommandons vivement d’utiliser le [Manuel d’activation de Site pour la voix (manuel)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) comme un guide supplémentaire à ces listes de vérification.

>[!NOTE]
>La plupart des paramètres de configuration sont communes entre les équipes et Skype pour l’activité en ligne. Skype de 365 Office de centre d’Administration d’entreprise vous permet de configurer ces paramètres.

<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/>Points de décision</td><td><ul><li>Qui sera chargé de superviser la réalisation de l’intégration des listes de contrôle ?</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Étapes suivantes</td><td><ul><li>Télécharger les listes de contrôle d’intégration.</li><li>Parcourez les éléments de liste de contrôle d’intégration détaillées selon le plan de déploiement de votre organisation.</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="continue-onboarding"></a>Poursuivre l’intégration

Après avoir terminé cette liste de vérification, vous allez avoir ajouté des fonctionnalités vocales à votre déploiement d’équipes.

L’étape suivante, utiliser le [Manuel d’activation de Site pour la voix (manuel)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) pour vous aider à bord vos utilisateurs sur chaque site et garantir que planifier et exécuter les activités spécifiques au site importantes.

-   Plan de déploiement de Site par Site prêt

-   Établir le processus de gestion de Service

-   Exécuter des tests et de correction

<!--ENDOFSECTION-->

## <a name="test-cloud-voice-workloads-in-teams"></a>Charges de travail de test nuage voix dans des équipes

Après avoir défini et documenté votre réussite de l’entreprise aux équipes nuage voix et les plans d’implémentation technique dans le cadre de la phase de Envision et entreprendre la configuration souhaitée dans le centre d’administration, l’étape suivante consiste à confirmer que votre société attentes et les exigences sont satisfaites par le biais de fonctionnalité, de fonctionnalités et de convivialité. Vous devez effectuer cette étape de validation avant de déployer un déploiement pilote ou final dans votre environnement de production.

Vous pouvez utiliser le plan de réussite définis lors de la phase de Envision pour servir de base pour déterminer les activités, les attentes, caractéristiques et fonctionnalités des cas de test et étendue globale doit être évaluée au cours de la phase de test.

## <a name="define-your-testing-approach"></a>Définir votre approche de test

Dans sa forme la plus simple, votre approche de test est basée sur votre révision les fonctionnalités de la fonctionnalité de l’audioconférence ou système téléphonique avec les Plans d’appel de service et le développement d’un plan de test pour vérifier que vos besoins en matière de fonctionnalité sont respectées pour les utilisateurs dans la portée. Voici un plan de test d’exemple pour la phase intégré d’une implémentation de la fonction d’audioconférence.

| Pour tester la fonction de conférence audio | Résumé des résultats | Remarques supplémentaires |
|------------|-----------------|------------------|
| Planification d’une réunion d’équipes ad hoc qui contient les informations d’audioconférence | Réussite/échec   | À DÉFINIR |
| Utiliser un téléphone pour la réunion en vous connectant à une réunion à partir de RTPC audio avec les informations de connexion fournies | Réussite/échec | À DÉFINIR |
| Rejoindre d’autres personnes à une réunion existante par appel sortant via le réseau RTPC | Réussite/échec | À DÉFINIR |


| Système téléphonique avec fonction d’appel de Plans de test | Résumé des résultats | Remarques supplémentaires |
|----------------------------------------------------|-----------------|------------------|
| Appeler un RTPC en composant un numéro RTC       | Réussite/échec       | À DÉFINIR |
| Recevoir un appel RTC en appelant votre numéro RTC à partir d’une ligne externe (mobile, téléphone fixe) | Réussite/échec | À DÉFINIR|
|Transférer un appel RTC d’un utilisateur d’équipes à un autre | Réussite/échec | À DÉFINIR |


>[!TIP]
>Pour aider à la création de cas de test comme point de départ, consultez la liste d’informations utilisateur conférence audio à des [réunions d’équipes et d’appels](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8?ui=en-US&rs=en-US&ad=US#bkmk_havingmeetings).

<!--ENDOFSECTION-->

## <a name="set-up-cloud-voice-workloads-for-teams"></a>Paramétrer des charges de travail de voix cloud pour les équipes

Maintenant que vous avez défini votre approche de test, l’étape suivante configure votre environnement de service et les utilisateurs dans la portée pour les fonctionnalités vocales de nuage équipes. Pour plus d’informations, voir [Planification technique pour les conférences Audio](https://docs.microsoft.com/microsoftteams/audio-conferencing#technical-planning-for-audio-conferencing) et [paramétrer Skype pour les entreprises et les équipes Microsoft de participer aux conférences Audio](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/set-up-audio-conferencing) en plus de [Planification technique pour système de téléphone avec des Plans d’appel](https://docs.microsoft.com/microsoftteams/phone-system-with-calling-plans#technical-planning-for-phone-system-with-calling-plans) et jeu de [ Plans d’appel de Skype pour les entreprises et les équipes de Microsoft](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

<!--ENDOFSECTION-->

### <a name="execute-the-test-plan"></a>Exécuter le plan de test

Une fois les environnements de service de conférence audio et d’utilisateur ont été configurés, la dernière étape de test inclut l’exécution du plan de test avec le focus sur le contrôle des fonctionnalités. 

**Test des conditions préalables et les hypothèses pour les utilisateurs et les sites dans la portée de téléconférence audio :**

-   Entreprise utiliser la définition de cas pour la conférence Audio service a été effectuée.

-   Licences requises pour les conférences Audio ne sont disponible et a été affecté.

-   La liste des sites d’organisation et les groupes d’utilisateurs ont été identifiés.

-   La liste de numéros avec la préférence de langue de connexion dédiée et partagé de conférence audio ont été identifiés et configuré.

-   [Crédits de communications](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits) (si nécessaire) ont été configurés pour votre organisation.

-   Paramètres de pont de conférence conférence audio ont été identifiés et configuré (longueur du code confidentiel, notifications d’entrée et de sortie, préférence de notification d’activation).

-   Client les stratégies de conférence et des paramètres de planification qui prennent en charge la conférence Audio scénarios à distance ont été identifiés, configurés et appliqués de numérotation.

-   Exigences de conformité de conférence audio ont été identifiés et configurés.

**Système de téléphone avec l’appel de Plans de test des conditions préalables et les hypothèses pour les utilisateurs et les sites dans la portée :**

-   Utilisez définition du cas client pour le système de téléphone avec les Plans d’appel de service a été effectué.

-   Licence requise pour le système téléphonique avec des Plans d’appel est disponible et a été affectée.

-   La liste des sites d’organisation et les groupes d’utilisateurs ont été identifiés.

-   Numéros de téléphone pour être affectés aux utilisateurs ont été acquis ou prise en charge par Microsoft et qui sont disponibles sur le portail clients.

-   [Crédits de communications](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits) (si nécessaire) ont été configurés pour votre organisation.

-   Locataire des stratégies utilisateur et les paramètres de plan d’appel qui prennent en charge le système téléphonique avec des Plans d’appel de scénarios ont été identifiés, configurés et appliqués.

-   Système de téléphone avec les Plans d’appel de besoins de conformité ont été identifiés et configuré.

<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/>Points de décision</td><td><ul><li>Décider quelles fonctionnalités Audio conférence seront déployées (décision de service).</li><li>Identifier les exigences en matière de fonctionnalités utilisateur pour les conférences Audio.</li><li>Identifier les exigences de configuration de service d’audioconférence.</li><li>Décidez quels système téléphonique avec les Plans d’appel de fonctions sera déployé (décision de service).</li><li>Identifier les exigences en matière de fonctionnalités utilisateur pour système de téléphone avec des Plans d’appel.</li><li>Identifier les exigences de configuration de service pour système de téléphone avec des Plans d’appel de.</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Étapes suivantes</td><td><ul><li>Développez et documentez votre approche de plan de test.</li><li>Préparez votre environnement de service et les utilisateurs dans la portée pour les fonctionnalités d’audioconférence.</li><li>Préparez votre environnement de service et les utilisateurs dans la portée de système téléphonique avec les Plans d’appel de fonctionnalités.</li><li>Exécuter une validation de test pour les fonctionnalités de conférence de données Audio que vous souhaitez activer.</li><li>Exécuter une validation de test pour le système de téléphone avec les Plans d’appel de fonctionnalités que vous souhaitez activer.</li><li>Pour les échecs de test, vérifier que votre configuration est correcte, consultez les articles de la Communauté, et, si nécessaire, déclencher une demande de support.</li></ul></td></tr>
</table>


Pour plus d’informations détaillées sur la façon de réaliser des tests pour les conférences Audio dans des équipes de, consultez le [test guide détaillé pour les conférences Audio] (https://docs.microsoft.com/MicrosoftTeams/onboarding-test-plan-for-enterprises-Audio-Conferencing).

Pour plus d’informations détaillées sur la façon de réaliser des tests de système téléphonique avec appel de Plans dans des équipes, voir [détaillées guide pour le système téléphonique de test](https://docs.microsoft.com/MicrosoftTeams/onboarding-test-plan-for-enterprises-Phone-System).

<!--ENDOFSECTION-->