---
title: Plan de test d’entreprise de l’audioconférence dans Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 03/13/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: Vérifiez que les attentes de votre organisation sont satisfaites en testant l’audioconférence dans les fonctionnalités, les fonctionnalités et la convivialité de votre organisation.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 24e2ba6a1f146168013e3283afca04849e84ddc0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33898728"
---
<a name="define-and-document-your-audio-conferencing-in-teams-test-plan-for-enterprises"></a>Définir et documenter votre audioconférence dans le plan de test teams pour les entreprises 
===============================================================================

Une fois que vous avez défini et documenté votre audioconférence dans teams réussite et implémentation technique dans le cadre de la phase enVision, l’étape suivante consiste à valider la satisfaction des attentes et des exigences de votre organisation par le biais de la fonctionnalité. fonctionnalités et convivialité. Avant de déployer un déploiement pilote ou final dans votre environnement de production, vous devez effectuer cette étape de validation.

Vous pouvez utiliser le plan de réussite pour les entreprises que vous avez défini lors de la phase enVision afin de baser la détermination des activités, des attentes, des cas de test des fonctionnalités et des fonctionnalités ainsi que de l’étendue globale de la phase de test.

<a name="identify-testing-support-stakeholders"></a>Identifier les personnes prenant en charge les tests
-------------------------------------

À mesure que vous vous préparez à évaluer les fonctionnalités de l’audioconférence, créez une matrice des parties prenantes du support de test pour identifier les rôles nécessaires à la prise en charge de la phase de test.

> [!TIP]
> Lorsque vous remplissez la matrice des parties prenantes en charge des tests d’équipes, il est possible que certains rôles soient les mêmes que ceux identifiés lors de la phase enVision, mais avec des descriptions de rôles penchées sur les tests. Vous devrez peut-être identifier des rôles supplémentaires en fonction de la configuration requise pour vos scénarios de test.

#### <a name="teams-testing-support-stakeholder-matrix"></a>Matrice des parties prenantes en matière de tests teams

> [!TIP]
> Vous trouverez ci-dessous un exemple de modèle de parties prenantes en charge de tests que vous pouvez utiliser pour documenter les parties prenantes nécessaires à la prise en charge de la phase de test.

| Rôle                          | Description du rôle                                                                                                                                                                          | Ressource affectée, informations de contact et emplacement |
|-------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------|
| Test du ou des sponsors de la direction  | <ul><li>Vérifiez que les fonctionnalités d’équipe répondent aux besoins de votre entreprise. les sponsors de la direction maîtrisent les résultats clés des entreprises et les scénarios d’utilisation prioritaires.</li><li>Faire office de service ultime et supposer une responsabilité, pour les objectifs de test des fonctionnalités d’équipe.</li><li>Aidez-vous à résoudre les problèmes que le responsable des tests a escaladé.</li><li>Communication du parrainement au sein de l’entreprise concernant les objectifs de test.</li><li>Être tenu de prendre des décisions stratégiques clés.</li><li>Être tenu de veiller à la disponibilité des ressources et du budget requis pour soutenir les efforts de test.</li><li>Sensibilisation et acquisition pour la campagne de test avec d’autres parties prenantes.</li><li>Faire office de sponsors lors de la phase d’évaluation du test.</li></ul>                                                 | DÉFINIR                                                  |
| Membres du Comité de direction    | <ul><li>Soyez intéressé (e) et donnez des instructions pour la direction générale du déploiement du service de conférence audio.<li>Assistez à la sensibilisation des connaissances stratégiques par le biais de l’achat au sein de l’organisation.</li></ul>                                                                        | DÉFINIR                                                  |
| Chef de projet                  |<ul><li> Gérer et diriger l’équipe du projet.</li><li>Coordonnées des partenaires et équipes travaillant dans le projet.</li><li>Soyez responsable de la création et de la gestion des plans de projet pour les résultats de clés trimestrielles.</li><li>Résoudre les problèmes liés aux fonctions transversales.</li><li>Fournir des mises à jour régulières aux sponsors de Project.</li><li>Incorporation d’une connaissance clé de l’utilisateur les enseignements identifiés dans les résultats des tests dans l’offre globale d’adoption des utilisateurs.</li><li>Envoiez des revues mensuelles et opérationnelles et participez à des examens trimestriels de l’entreprise.</li></ul>                                                                                                                                                         | DÉFINIR                                                  |
| Chef/architecte de la collaboration  | <ul><li>Être responsable de l’exécution de la stratégie de collaboration définie par les dirigeants de l’entreprise.</li><li>Analysez et sélectionnez des produits de collaboration pour l’entreprise qui répondent aux objectifs de votre entreprise.</li><li>Être responsable du design des opérations pour les produits de collaboration.</li><li>Définissez les modèles de fonctionnement et de support.</li><li>Contribuez aux révisions mensuelles et trimestrielles de l’entreprise.</li></ul>                                                                                                 | DÉFINIR                                                  |
| Gestionnaire de projets               | <ul><li>Développement et mise à jour du plan de projet.</li><li>Gérer les livrables du projet en fonction du plan de projet et du budget.</li><li>Enregistrez et gérez les problèmes du projet, y compris les escalades.</li><li>Organisez des appels standup hebdomadaires.</li><li>Mettre en personne et fournir des mises à jour aux sponsors de Project Executive.</li><li>Utiliser la gestion des modifications internes et les équipes de communication pour mettre à jour l’approche de gestion des modifications et les plans de communication selon les besoins.</li></ul>                                                                                                                                                   | DÉFINIR                                                  |
| Directeur de réseau                  | <ul><li>Fournir des informations sur la conception du réseau lors de la phase de découverte;</li><li>Participez à la planification des ateliers de phase enVision.</li><li>Coordonner le travail de l’équipe du réseau lors de l’exécution du projet.</li></ul>                                                                                                                               | DÉFINIR                                                  |
| Directeur de la sécurité                 | <ul><li>Fournir des informations sur la conception et les processus de sécurité pendant la phase de découverte;</li><li>Participez à la planification des ateliers de phase enVision.</li><li>Coordonner le travail de l’équipe de sécurité lors de l’exécution du projet.</li></ul>                                                                                                                | DÉFINIR                                                  |
| Directeur de la téléphonie                | <ul><li>Fournir une entrée lors de la phase de découverte;</li><li>Participez à la planification des ateliers de phase enVision.</li><li>Coordonner le travail de l’équipe de téléphonie lors de l’exécution du projet;</li></ul>                                                                                                                           | DÉFINIR                                                  |
| Directeur de bureau                  | <ul><li>Fournir des informations sur les clients et le processus de mise à jour lors de la phase de découverte;</li><li>Participez à la planification des ateliers de phase enVision.</li><li>Coordonner le travail de l’équipe de bureau lors de l’exécution du projet;</li></ul>                                                                                                              | DÉFINIR                                                  |
| Représentants d'unité commerciale | <ul><li>Contribuez aux guides d’adoption d’utilisateurs et aux matériaux.</li><li>Contribuer aux cas d’utilisation de votre entreprise.</li></ul>                                                                                                                                   | DÉFINIR                                                  |
| Administrateurs informatiques                     | <ul><li>Assistez à la planification et à l’exécution des tests (ce rôle est destiné aux professionnels de l’informatique).                                                                                                                       | DÉFINIR                                                  |
| Propriétaire de service                 | <ul><li>Prendre en charge le fonctionnement du service de visioconférence audio.</li><li>Servent de propriétaire du service de conférence audio.</li></ul>                                                                                                               | DÉFINIR                                                  |
| Test/responsable             | <ul><li>Définissez le plan de test, y compris les activités, les dépendances, l’environnement, les objectifs, la stratégie, la réapprovisionnement (environnemental et humaine) et la chronologie requise pour la prise en charge de la phase de test.</li><li>Coordonnées de la remise et de la disponibilité des dépendances de plan de test.</li><li>Aligner selon la priorité appropriée pour la résolution des défauts.</li><li>Faire office de chemin d’escalade pour les problèmes de tests qui surviennent.</li><li>Communiquez et signalez le statut d’un plan de test auprès d’équipes internes et de parties prenantes spécifiques.</li><li>Documenter et présenter les résultats des tests finaux.</li></ul> | DÉFINIR                                                  |
| Testeur de services d’audioconférence     | <ul><li>Passez en revue le plan de test pour comprendre les exigences de tests, les objectifs, la chronologie, la résolution des problèmes et les scénarios de test à exécuter.</li><li>Passez en revue et développez des cas de test prenant en charge les exigences d’acceptation et de fonctionnalités des conférences audio.</li><li>Exécuter des cas de test et des résultats de test de document.</li><li>Donnez des défauts de document au fur et à mesure qu’ils se produisent, et transformez-les en test de priorité et de résolution des problèmes.</li><li>Testez les régressions pour identifier les défauts après confirmation de la résolution de l’erreur.</li></ul>                                                                | DÉFINIR                                                  |
| Testeur réseau                | <ul><li>Passez en revue le plan de test pour comprendre les exigences de tests, les objectifs, la chronologie, la résolution des problèmes et les scénarios de test à exécuter.</li><li>Passez en revue les cas de test prenant en charge l’acceptation et les exigences de performance du réseau.</li><li>Exécution de tests liés à la préparation du réseau, y compris la connectivité réseau, la validation de performance, la validation de la qualité de service (QoS) et la validation de la configuration du tunnel scindé.</li><li>Achever la validation de la bande passante pour les sites en étendue en utilisant le planificateur de réseau via MyAdvisor.</li><li>Documentation des résultats du test de disponibilité du réseau.</li><li>Donnez des défauts de document au fur et à mesure qu’ils se produisent, et transformez-les en test de priorité et de résolution des problèmes.</li><li>Testez les régressions pour identifier les défauts après confirmation de la résolution de l’erreur.</li></ul>                                                                | DÉFINIR                                                  |
| Testeur de sécurité               | <ul><li>Passez en revue le plan de test pour comprendre les exigences de tests, les objectifs, la chronologie, la résolution des problèmes et les scénarios de test à exécuter.</li><li>Passez en revue et développez des cas de test prenant en charge les exigences d’approbation de sécurité.</li><li>Exécution de tests liés à l’approbation de sécurité des cas de test.</li><li>Les résultats des tests d’approbation de la sécurité des documents.</li><li>Donnez des défauts de document au fur et à mesure qu’ils se produisent, et transformez-les en test de priorité et de résolution des problèmes.</li><li>Testez les régressions pour identifier les défauts après confirmation de la résolution de l’erreur.</li></ul>                                                                | DÉFINIR                                                  |
| Testeur de téléphonie              | <ul><li>Passez en revue le plan de test pour comprendre les exigences de tests, les objectifs, la chronologie, la résolution des problèmes et les scénarios de test à exécuter.</li><li>Passez en revue les cas de test prenant en charge le transfert de numéro de service et les exigences de fonctionnalités.</li><li>Exécutez des tests liés au transfert de numéro de service, notamment sur le port de numéro de service vers Office 365.</li><li>Exécuter des cas de test et des résultats de cas de test de documents.</li><li>Donnez des défauts de document au fur et à mesure qu’ils se produisent, et transformez-les en test de priorité et de résolution des problèmes.</li><li>Testez les régressions pour identifier les défauts après confirmation de la résolution de l’erreur.</li></ul>                                                                | DÉFINIR                                                  |
| Test d’administration de l’audioconférence | <ul><li>Passez en revue le plan de test pour comprendre les exigences de tests, les objectifs, la chronologie, la résolution des problèmes et les scénarios de test à exécuter.</li><li>Passez en revue et développez des cas de test prenant en charge les exigences en matière d’acceptation et de fonctionnalités de l’administration.</li> <li>Exécuter des cas de test et des résultats de cas de test de documents.</li><li>Donnez des défauts de document au fur et à mesure qu’ils se produisent, et transformez-les en test de priorité et de résolution des problèmes.</li><li>Testez les régressions pour identifier les défauts après confirmation de la résolution de l’erreur.</li></ul>                                                                | DÉFINIR                                                  |


<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/> <br/>Points de décision</td><td><ul><li>Déterminez les rôles de support technique et d’intervenant requis pour le test des fonctionnalités de l’audioconférence dans votre environnement.</li><li>Déterminez les ressources que vous affecterez aux rôles d’assistance technique de test et d’intervenant que vous avez identifiés.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Étapes suivantes</td><td><ul><li>Documentez les rôles d’assistance technique de test et d’intervenant requis dans votre matrice des parties prenantes du support de test.</li><li>Documentez les informations de contact et les détails d’emplacement de chaque ressource que vous listez dans la matrice des parties prenantes du support de test.
</table>


<a name="define-audio-conferencing-feature-requirements"></a>Définir les exigences de la fonctionnalité de conférence audio 
-----------------------------------------------

Dans le cadre de la définition de la configuration requise pour les conférences audio pour les utilisateurs dans le cadre de l’application, l’une des premières étapes que vous devez effectuer lors de la phase enVision fut l' [analyse du personnage](https://docs.microsoft.com/MicrosoftTeams/audio-conferencing#assess-environment-and-evaluate-adoption-readiness), dans laquelle vous avez défini votre personnage et les scénarios de conférence audio. Avec ce planning de référence identifié, l’étape suivante consiste à évaluer la planification publique la plus récente d’équipes pour déterminer:

-   Les fonctionnalités de conférences audio que vous déploierez pour les utilisateurs de l’étendue.

-   La fonction de service de conférence rendez-vous de l’utilisateur est attendue, en fonction de votre environnement de déploiement actuel Skype entreprise, Exchange et SharePoint.

-   Si vous pouvez vérifier que les fonctionnalités de l’audioconférence décrite dans la dernière barre d’évolution publique répondent à vos besoins en matière d’utilisation, de fonctionnalités et d’étendue dans la chronologie de votre déploiement;

> [!TIP]
> Pour plus d’informations sur l’identification des fonctionnalités de l’audioconférence dans le cadre de votre déploiement <https://aka.ms/O365Roadmap>, reportez-vous à la documentation la plus récente sur.

À présent que l’utilisateur et les fonctionnalités de l’audioconférence ont été définis, le prochain critère d’évaluation sera l’efficacité de l’interopérabilité avec Teams. Pour plus d’informations sur l’interopérabilité et sur les options de configuration disponibles, reportez-vous à la rubrique [Microsoft teams et interopérabilité de Skype entreprise](https://docs.microsoft.com/microsoftteams/teams-and-skypeforbusiness-coexistence-and-interoperability).

#### <a name="audio-conferencing-feature-definition"></a>Définition de la fonctionnalité de conférence audio

> [!TIP]
> 
> Vous trouverez ci-dessous un exemple de modèle de définition de la conférence audio que vous pouvez utiliser pour documenter les fonctionnalités d’administration de l’audioconférence et de groupe d’utilisateurs à évaluer.

| Niveau entreprise   | Réunions de collaboration    | Plateforme et périphériques   | Professionnels de l’informatique  | Groupe professionnel supplémentaire, propre à un site  | Exigences remplies par le plan de la dernière équipe teams |
|-------------------------------------------|----------------------------|------------------|------------------------|-------------------|-------------------|
| <ul><li>Planifier des réunions d’audioconférence par le biais de:<ul><li>Complément planification Outlook</li><li>Client Teams</li></ul></li><li>Canaux d’hébergement et réunions privées</li><li>Héberger des réunions avec jusqu’à 80 participants</li><li>Fonctionnalité de conférence audio</li><li>Jointure anonyme</li><li>Support salle d’attente</li><li>Gestion des participants</li><li>Désactiver le son des autres participants</li><li>Gestion des périphériques via le client teams</li></ul> |<ul><li>Gestion du cycle de vie d’une réunion avant/après/après la réunion</li><li>Partage de Bureau</li><li>Conversations</li><li>Expériences de réunion immersive</li><li>Partage d'application</li><li>Accorder/prendre le contrôle au sein du partage d’application</li></ul> |<ul><li> Windows, prise en charge des fonctionnalités de réunion du client de Mac teams</li><li>La prise en charge des réunions du client teams du navigateur pour:<ul><li>Chrome</li><li>Microsoft Edge</li></ul></li><li>support technique pour les réunions iOS et Android</li></ul> | <ul><li>Portail de diagnostic de la qualité des appels</li><li>Stratégies de l’audioconférence client</li><li>Activer l’analyse de la qualité des appels (bord)</li></ul> | <ul><li>Valider les fonctionnalités des réunions teams en fonction de l’image d’un ordinateur portable</li><li>Prise en charge de langues spécifiques</li><li>Paramètres d’objets de stratégie de groupe appliqués pour un scénario utilisateur ou un site spécifique donné</li></ul> | Oui  |

#### <a name="audio-conferencing-user-functionality-definition"></a>Définition des fonctionnalités d’utilisation de l’audioconférence

> [!TIP]
> Vous trouverez ci-dessous un exemple de modèle de fonctionnalité utilisateur que vous pouvez utiliser pour documenter l’utilisation requise basée sur les fonctionnalités de l’audioconférence qui doivent être évaluées.

| Découverte d’Exchange                          | Découverte de SharePoint                            | Expertise de la stratégie d’interopérabilité dans teams |
|----------------------------------------------|--------------------------------------------------|------------------------------------------|
| <ul><li>Créer des équipes (la création de groupes Office est activée)</li><li>Rejoindre des équipes</li><li>Créer des canaux</li><li>Créer et afficher des réunions</li><li>Modifier une image de profil utilisateur</li><li>Ajouter et configurer des connecteurs</li><li>Ajouter et configurer des onglets</li><li>Ajouter et configurer des bots</li></ul> | <ul><li>Stocker et partager des fichiers dans les conversations d’équipe</li><li>Stocker et partager des fichiers et des fichiers dans des discussions privées (en fonction de OneDrive)</li></ul> | <ul><li>ChatDefaultClient: par défaut</li><li>CallingDefaultClient: par défaut</li></ul>      |



<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/> <br/>Points de décision</td><td><ul><li> Déterminez les fonctionnalités de catégorie d’audioconférence que vous déploierez dans votre environnement.</li><li>Identifiez les fonctionnalités de la fonction d’audioconférence de votre utilisateur pour votre environnement de déploiement Skype entreprise, Exchange et SharePoint actuel.</li><li>Déterminez l’efficacité de l’interopérabilité entre les équipes que vous déploierez.</li><li>Passez en revue la plan d’évolution publique de la dernière équipe et déterminez si les capacités de charge de travail actuelles répondent à votre chronologie de déploiement.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Étapes suivantes</td><td><ul><li>Documentez les fonctionnalités de catégorie d’audioconférence nécessaires à la prise en charge du déploiement de votre audioconférence.</li><li>Documentez les fonctionnalités de l’audioconférence pour les appels audio et les exigences d’interopérabilité fournies par votre environnement de déploiement Skype entreprise, Exchange et SharePoint actuel.</li><li>Rendez-vous sur le plan public le plus récent qui représente les fonctionnalités d’audioconférence qui répondent à vos besoins professionnels et au minutage de votre déploiement.</li></ul></td></tr>
</table>

<a name="define-and-document-your-audio-conferencing-test-plan"></a>Définir et documenter votre plan de test de l’audioconférence
-----------------------------------------------------

Une fois que vous avez défini les fonctionnalités de l’audioconférence dans l’étendue, l’étape suivante consiste à créer le plan de test. À un niveau élevé, le plan de test englobe la stratégie de test générale et la méthodologie que vous utiliserez pour la prise en charge de la validation des fonctionnalités dans le processus de test.

À un niveau élevé, le plan de test doit inclure:

-   **Étendue des tests:** Résume les zones ciblées (objectifs, scénarios et objectifs) à évaluer dans le cadre de la phase de test.

-   **Scénarios de test:** Ensemble de cas de test à valider pour les fonctionnalités de conférence audio de l’étendue

-   **Ressources de test:** Matrice de ressources nécessaires à la prise en charge des efforts de test d’un point de vue environnemental, technique et personnel

-   **Planning de test (chronologie):** Représente au début du test, la durée de la dernière tentative et la date de fin de la phase de test.

-   **Rapport de défectuosité et correction:** Recommandations en matière de rapports, de suivi et de triage des problèmes liés aux tests

-   **Triage et escalade de défaut:** Plan du mode et de la date de début d’une escalade de défaut

-   **Test de la sortie et du critère de suspension:** Recommandations en matière de contour pour la fermeture de la phase de test ou la mise en suspens

-   **Tests de livrables:** Résumé des résultats qui seront développés et fournis pour prendre en charge l’acceptation et la sortie de la signature

> [!TIP]
> 
>   Une méthodologie de test peut déjà exister au sein de votre organisation, mais les conseils ci-dessous illustrent des pratiques recommandées qui peuvent être incluses ou optimisées séparément pour le test des fonctionnalités d’équipes dans votre environnement.

Dans les sections qui suivent, vous trouverez des instructions prescrites supplémentaires qui vous aideront à prendre des décisions spécifiques et des modèles et des rubriques que vous devez prendre en considération lors de la fin de votre plan de test.

### <a name="define-and-document-testing-scope"></a>Définir et étendue de l’évaluation des documents

Lorsque vous travaillez pour développer votre plan de test, vous devez définir le niveau de l’étendue des tests avant, en mettant en évidence la charge de travail et la liste de fonctionnalités que vous évaluez.

L’objectif de l’évaluation correcte des fonctionnalités de l’audioconférence est généralement le suivant:

-   Préparation du site audioconférence

-   Fonctionnalité d’utilisation de l’audioconférence

-   Administration de l’audioconférence

#### <a name="audio-conferencing-testing-scope"></a>Portée de test de l’audioconférence

> [!TIP]
> Vous trouverez ci-dessous un exemple de modèle d’étendue de test que vous pouvez utiliser pour documenter les fonctionnalités d’administration de l’audioconférence et de groupe d’utilisateurs à évaluer.

| Préparation du site audioconférence                                                                                                                                                                                                 | Fonctionnalité d’utilisation de l’audioconférence                                                   | Expertise d’administration de l’audioconférence                                                                                                  |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------|
| <ul><li>Planification de la bande passante de planificateur de réseaux (via MyAdvisor)</li><li>Connexion réseau et validation des performances (via l’outil d’évaluation du réseau Skype entreprise)</li><li> Validation de la qualité de service (QoS)</li><li>Validation du tunnel d’accès distant</li></ul> |<ul><li>Planification de conférences rendez-vous</li><li> Rejoindre une réunion à partir d’un réseau PSTN</li><li>Ajouter des participants via le numéro RTC</li></ul> |<ul><li>Attribution de licence</li><li>Gestion des numéros de service</li><li>Portage des numéros de service vers Office 365</li><li>Rapports sur les conférences audio</li><li>Rapports sur la qualité des appels (bord)</li></ul> |


<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/> <br/>Points de décision</td><td><ul><li>Déterminez la portée de test de l’audioconférence en identifiant les fonctionnalités qui doivent être évaluées par la zone de focalisation.</li><li>Déterminez les objectifs et les objectifs supplémentaires à des fins d’évaluation.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Étapes suivantes</td><td><ul><li>Documentez les fonctionnalités de l’audioconférence à évaluer en fonction de la zone de focalisation.</li><li>Documenter des buts et objectifs supplémentaires pour l’évaluation.</li></ul></td></tr>
</table>


### <a name="define-and-document-audio-conferencing-test-cases"></a>Définir et documenter des scénarios de test de conférence audio

Une fois que vous avez défini les fonctionnalités de l’audioconférence, le déploiement du client et les scénarios côte à côte avec Skype entreprise (le cas échéant), l’étape suivante consiste à formuler les cas de test requis pour évaluer les fonctionnalités de l’audioconférence dans l’étendue. À un niveau élevé, les cas de test sont généralement groupés par zone de focalisation et incluent les éléments suivants:

-   **Titre du cas de test:** Zone focalisée de la fonctionnalité d’évaluation du test (par exemple, audioconférence)

-   **Description de cas de test:** Récapitulatif des buts des fonctions de test évaluées

-   **Instructions de cas de test:** Étapes à suivre pour exécuter correctement le cas de test exécuté

-   **Environnement requis (prérequis):** Instructions de configuration nécessaires à l’exécution correcte du test

-   **Ressource requise:** Ressources humaines requises pour l’évaluation et l’exécution appropriées du test

-   **Résultats attendus:** Résultat attendu après le test réussi

> [!NOTE]
> Dans la mesure où l’approche et le niveau de détail requis pour la création de cas de test peuvent varier au sein de votre organisation, il est recommandé de suivre une approche permettant d’obtenir un niveau de détail approprié pour la prise en charge des tests généraux. facilité.

> [!TIP]
> Pour vous aider à effectuer des tests de création de cas de test en tant que point de départ, voir la liste des recommandations en matière d’utilisation de l’audioconférence dans les [réunions et les appels teams](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8).

#### <a name="audio-conferencing-test-case"></a>Scénario de test de conférence audio

> [!TIP]
> Vous trouverez ci-dessous un exemple de modèle de cas de test que vous pouvez utiliser pour documenter les fonctionnalités d’administration de l’audioconférence et de groupe d’utilisateurs à évaluer.

Validation de l’audioconférence

| ID de cas de test | Titre du cas de test                             | Description de cas de test                                                                       | Environnement requis pour l’exécution de cas de test                                               | Étapes requises pour l’exécution de cas de test                                                                                                                                             | Ressource de test requise |
|--------------|---------------------------------------------|---------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------|
| 1            | Planifier une réunion de conférence audio dans teams | Planifiez une réunion en ligne et vérifiez que le pont de conférence est affiché dans l’invitation. |<ul><li>Client teams installé</li><li>Utilisateur activé avec les licences Office 365 suivantes attribuées:<ul><li>Office entreprise E5 avec audioconférence et Microsoft teams</li><li>Office entreprise E3 avec audioconférence et Microsoft teams</li></ul></li></ul> |<ol><li>Connectez-vous au client Teams.</li><li>Ouvrez Outlook et planifiez une nouvelle réunion Teams.</li><li>Vérifiez que la nouvelle invitation à une réunion affiche le numéro Microsoft Bridge affiché dans le client.</li></ol>      | Testeur de services d’audioconférence |


> [!TIP]
> Pour obtenir des recommandations supplémentaires sur la création d’un cas de test individuel et sur la création d’un plan global pour évaluer les fonctionnalités de l’audioconférence au sein de votre organisation, consultez le [plan de test de conférence audio](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_21) fourni par [MyAdvisor](https://myadvisor.fasttrack.microsoft.com/).


<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/> <br/>Points de décision</td><td><ul><li>Déterminez quelles sont les fonctionnalités d’administration et d’utilisation de l’audioconférence qui seront évaluées.</li><li>Déterminez quel environnement de test est requis pour prendre en charge l’exécution de cas de test.</li><li>Déterminez les étapes nécessaires à l’évaluation de cas de test.</li><li>Déterminez les ressources nécessaires à l’exécution correcte du test.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Étapes suivantes</td><td><ul><li>Documentez les cas de test à évaluer en fonction du modèle de cas de test fourni.</li><li>Incluez le modèle complet dans le cadre de votre plan de test global.</li></ul></td></tr>
</table>


### <a name="define-and-document-testing-resources"></a>Définition et documentation de ressources de test

Pour la prise en charge de la phase de test, il est important de mettre en place un plan de ressources détaillant les ressources humaines, le support et les ressources technologiques dont vous avez besoin. Une composante importante du plan de test global, le plan de ressources vous aide à déterminer les dépendances susceptibles d’exister et vous donne une idée générale de la prise en charge de ressources dont vous aurez besoin.

À un niveau élevé, il s’agit généralement des ressources suivantes:

-   **Personnes**: parties prenantes

-   **Technologie**: client, gestion des licences, appareils

-   **Support**: formation (cartes, vidéos), prise en charge de l’administration avec la trajectoire d’escalade définie

#### <a name="testing-resource-requirements"></a>Tests requis pour les ressources

> [!TIP]
> Vous trouverez ci-dessous un exemple de test de modèle de demande de ressources que vous pouvez utiliser pour documenter les différents types de ressources nécessaires à la prise en charge de la phase de test.

[//]: # (Est-ce que cet exemple parle d’offres d’appels?)

| Type de ressource | Ressources nécessaires                                           | Description de la ressource |
|---------------|--------------------------------------------------------------|----------------------|
| Personnes        | Testeurs de chef de projet                               | DÉFINIR                  |
| Technologie    | Un accès à Office 365 avec les services suivants activés:<ul><li>Gestion des licences Office 365 E5 affectées</li><li>Forfait d’appels nationaux et internationaux attribués</li></ul>    | DÉFINIR                  |
| Support       | Test de l’assistance de test de l’administrateur du technicien du support technique | DÉFINIR                  |




<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/> <br/>Points de décision</td><td><ul><li>Déterminez les types de ressources (personnes, technologie et support) dont vous aurez besoin pour prendre en charge la phase de test.</li><li>Déterminez les ressources spécifiques requises pour les types de ressources que vous avez identifiés.</li><li>Décidez si vous devez fournir des informations supplémentaires pour décrire les types de ressources dont vous avez besoin.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Étapes suivantes</td><td><ul><li>Documentez les types de ressources (personnes, technologies et support) dont vous aurez besoin pour prendre en charge la phase de test.</li><li>Documentez les ressources spécifiques requises pour les types de ressources que vous avez identifiés.</li><li>Si vous décidez qu’il est nécessaire, documentez les informations supplémentaires sur les types de ressources dont vous avez besoin pour prendre en charge la phase de test.</li></ul></td></tr>
</table>

### <a name="define-and-document-a-testing-timeline"></a>Définir et documenter une chronologie des tests

Dans le cadre de la définition d’un plan de test, créez une chronologie qui organise le planning en fonction de la manière dont vous envisagez de terminer les activités de test et de répondre aux jalons de haut niveau.

À un niveau élevé, il s’agit généralement de:

-   **Tâche:** Activité de haut niveau à accomplir

-   **Jalon:** Objectif de niveau supérieur, ou progression achevée

-   **Ressource requise:** Ressources de test requises pour prendre en charge la remise du jalon ou de la tâche identifiés

-   **Date de début:** Date à laquelle l’activité, le jalon ou la tâche a été lancée le

-   **Date d’achèvement:** Date à laquelle vous voulez que l’activité, le jalon ou la tâche se termine par

-   **Propriétaire:** Ressource affectée qui est chargée de vérifier que l’activité, le jalon ou la tâche est achevée à temps, en fonction de la date d’achèvement

-   **Estimation:** Nombre d’heures nécessaires aux ressources affectées pour s’assurer que l’activité, le jalon ou la tâche est achevée à temps

#### <a name="testing-scheduling-and-timeline-requirements"></a>Test de la planification et de la chronologie requise

> [!TIP]
> Vous trouverez ci-dessous un exemple de modèle de critères de chronologie des tests que vous pouvez utiliser pour documenter les dates prévues lors du déroulement d’activités de test spécifiques ou des jalons remis par.

| Tâche                                     | Consultation       | Date de début                                                             | Date d’achèvement | Propriétaire | Ressources affectées | Coût |
|------------------------------------------|-----------------|------------------------------------------------------------------------|-----------------|-------|--------------------|------------|
| Rapport de test                              | DÉFINIR             | DÉFINIR                                                                    | DÉFINIR             | DÉFINIR   | DÉFINIR                | Heures de TBD  |
| Exécution de cas de test: audioconférence  | DÉFINIR             | DÉFINIR                                                                    | DÉFINIR             | DÉFINIR   | DÉFINIR                | Heures de TBD  |
| Exécution du cas de test: disponibilité du réseau   | DÉFINIR             | DÉFINIR                                                                    | DÉFINIR             | DÉFINIR   | DÉFINIR                | Heures de TBD  |


<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/> <br/>Points de décision</td><td><ul><li>Déterminez l’activité de chronologie, le jalon et les tâches que vous devez suivre.</li><li>Déterminez les ressources que vous devez affecter.</li><li>Déterminez la date à laquelle vous pensez avoir besoin.</li><li>Identifiez le propriétaire de la livraison.</li><li>Déterminez le temps nécessaire à l’exécution de l’activité, du jalon ou de la tâche.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Étapes suivantes</td><td><ul><li>Documentez votre chronologie de test à l’aide du modèle fourni, et notamment:<ul><li>Activité de chronologie, jalon et tâches qui doivent être suivies.</li><li>Ressources devant être affectées.</li><li>Date d’achèvement prévue.</li><li>Propriétaire de la remise.</li><li>Temps requis pour terminer l’activité, le jalon ou la tâche.</li></ul></li><li>Incluez le modèle complet dans le cadre de votre plan de test global.</li></ul></td></tr>
</table>



### <a name="define-and-document-test-defect-report-criteria"></a>Définir et documenter les critères de rapport des défauts de test

Dans la mesure où les cas de test au sein d’une phase ou d’un flux donnés sont exécutés, des problèmes peuvent se produire lorsque le résultat du cas de test exécuté ne correspond pas à ce que vous attendiez.

Lorsque ces types de résultats se produisent, ils doivent être capturés dans un rapport de défaut et un plan de correction qui est escaladé au cadre du test désigné pour la révision, la création de rapports et la résolution des problèmes.

En règle générale, un rapport de défaut et un plan de correction incluent les éléments suivants:

-   **ID de défaut:** Le numéro affecté au problème;

-   **ID de cas de test**affecté: le numéro affecté au cas de test évalué au moment de l’identification du défaut

-   **Description de l’erreur:** Résumé du problème

-   **Environnement/étapes à reproduire:** Résumé de la configuration de l’environnement de test, ainsi que les étapes exactes requises pour reproduire le problème

-   **Gravité du défaut**: l’impact du problème, qu’il s’agisse d’empêcher l’approbation du cas de test en tant que risque minimal. Voici quelques exemples:

-   **Faible:** Le problème a peu d’impact et n’empêche pas l’acceptation du cas de test si le problème peut être résolu plus tard.

-   **Moyenne:** Le problème a un impact substantiel, mais n’empêche pas l’acceptation du cas de test si le problème peut être résolu avant la fin de la phase de test.

-   **Elevé:** -le problème a un impact critique sur le cas de test. Le problème doit être résolu avant que le cas de test ne puisse être accepté.

-   **État:** Le problème est-il résolu, ou encore en cours d’étude;

-   **Envoyé par:** Le testeur qui a signalé le problème;

-   **Propriétaire attribué:** Ressource attribuée par l’équipe de test qui est responsable de la résolution du problème.

-   **Informations de prise en charge:** Il peut s’agir d’un problème, mais n’est pas limité aux journaux, captures d’écran ou vidéos du problème côté client.

Dans la mesure où les testeurs exécutent les cas de test décrits dans votre plan de test, ils doivent veiller à remplir un rapport de défaut et un plan de correction pour les problèmes qui se produisent.
Cela met en évidence un impact potentiel qui peut entraver, voire arrêter le processus d’évaluation des tests.

#### <a name="testing-defect-report-and-remediation-plan"></a>Rapport sur les défauts de test et plan de correction

> [!TIP]
> Vous trouverez ci-dessous un exemple de rapport sur les défauts et de modèle de plan de correction que vous pouvez utiliser pour documenter des problèmes détectés lors de la phase de test.

| ID de défaut                                | ID de cas de test affecté | Description de l’erreur                                                                                                                           | /Steps environnement pour reproduire                                                                                                                    | Minimal | État | Envoyé par | Propriétaire affecté | Informations de support (journaux, captures d’écran, etc.) |
|------------------------------------------|-----------------------|----------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------|----------|--------|--------------|----------------|---------------------------------------------------|
| 1                                        | 1                     | Pour les utilisateurs qui sont activés pour les réunions hébergées en régional (RHM), les coordonnées de connexion n’ont pas été remplies via le complément de planification Outlook de teams | Déplacer un compte de test vers une autre région de RHM.<br/> Connectez-vous à Outlook et essayez de planifier une conférence audio teams via le complément de planification d’Outlook teams | Moyen   | Été | Louis Lahr   | Isabelle gris      | Journal côté client teams<br/> Capture d’écran du client teams     |


<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/> <br/>Points de décision</td><td><ul><li>Déterminez les niveaux de gravité du critère de défaut que vous attribuez à l’effort de test.</li><li>Déterminez les critères de signalement de problèmes que vous souhaitez utiliser pour le test.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Étapes suivantes</td><td><ul><li>Documentez les critères de signalement de défaut de test requis dans le modèle fourni.</li><li>Incluez le modèle complet dans le cadre de votre plan de test global.</li></ul></td></tr>
</table>


### <a name="define-and-document-exit-and-suspension-criteria"></a>Définir et définir les critères de sortie et de suspension d’un document

Dans le cadre de la procédure globale d’exécution d’un plan de test, vous devez définir des critères pour indiquer le point où vous devez suspendre les efforts de test et les exigences qui doivent être satisfaites pour obtenir une connexion et sortir de la phase de test.

#### <a name="test-plan-exit-and-suspension-criteria"></a>Critères de sortie et de suspension du plan de test

> [!TIP]
> Vous trouverez ci-dessous un exemple de modèle de critères de Exit et de suspension que vous pouvez utiliser dans votre plan de test pour vous permettre de vous connecter, de quitter la phase de test ou de suspendre des activités de test.

| Test de critères de sortie                            | Critères de suspension du test                      |
|--------------------------------------------------|--------------------------------------------------|
|<ul><li>Tous les cas de test doivent avoir atteint le taux de réussite de%.</li><li>Tous les cas de test doivent avoir été entièrement exécutés</li><li>Dans tous les cas de test évalués, tous les défauts de gravité élevée doivent être fermés</li></ul> | <ul><li>Tous les scénarios de test doivent parvenir au taux d’échec de% TBD</li><li>Tous les défauts identifiés comme ayant une gravité élevée doivent être résolus avant que les tests puissent continuer.</li></ul> |



<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/> <br/>Points de décision</td><td><ul><li>Déterminez les critères de suspension qui doivent être satisfaits en cas de problèmes de tests.</li><li>Déterminez les critères de sortie qui doivent être satisfaits pour obtenir une connexion d’approbation de test et pour la prise en charge de la sortie de la phase de test une fois toutes les activités de test effectuées.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Étapes suivantes</td><td><ul><li>Documentez les critères de sortie des tests et de suspension requis dans les modèles de test et de sortie fournis.</li></ul></td></tr>
</table>


### <a name="define-and-document-the-defect-escalation-process"></a>Définir et documenter le processus de réaffectation de défaut

Tout au long de la procédure d’exécution d’un plan de test, vous pouvez rencontrer un problème ou identifier un défaut qui nécessite une remontée vers la ressource appropriée pour piloter et déterminer la résolution requise pour autoriser les tests.

Étant donné que les défauts sont identifiés avec la gravité et la priorité appropriées, vous créez une matrice de remontée et un processus de révision de triage pour le mappage lors du déclenchement d’une remontée et de la manière dont vous pouvez affecter le défaut à des fins d’examen supplémentaire et Règlement.

En règle générale, un rapport de défaut et un plan de correction incluent les éléments suivants:

-   **ID de défaut:** Le numéro que vous avez affecté au problème;

-   **Description de l’erreur:** Résumé du problème

-   **Évaluation de priorité de défaut:** Niveau de priorité affecté à une erreur de résolution basée sur l’impact de l’entreprise et sur la gravité des défauts. Voici quelques exemples:

-   **Faible:** Le problème a peu d’impact sur l’interdiction de la phase de test d’obtenir une connexion si le problème peut être résolu plus tard.

-   **Moyenne:** Le problème a un impact important sur l’interdiction de la phase de test d’obtenir une connexion si le problème ne peut pas être résolu.

-   **Haut:** Le problème a un impact important sur l’interdiction de la phase de test d’obtenir une connexion si le problème ne peut pas être résolu.

-   **Propriétaire de défaut affecté:** Ressource attribuée par l’équipe de test qui est responsable de la résolution du problème.

-   **Point de réaffectation de défaut affecté:** La ressource qui a été affectée pour la résolution du problème au niveau de l’organisation (si nécessaire) pour la résolution du problème; sur la base d’une gravité de défaut

-   **État d’erreur:** Le problème est-il résolu, ou encore en cours d’étude;

-   **Résolution requise par date:** La date à laquelle le problème doit être résolu

-   **Date d’État:** Date reflétant le dernier État mis à jour comme résultat d’une révision de triage de défaut

#### <a name="test-plan-defect-escalation"></a>Réaffectation de défaut de plan de test

> [!TIP]
> Vous trouverez ci-dessous un exemple de modèle de réaffectation de défaut que vous pouvez utiliser dans le cadre de votre plan de test pour documenter le processus d’escalade requis pour la définition de priorités et la résolution des erreurs de test.

| ID de défaut                                | Description de l’erreur                                                                                          | Évaluation de priorité de défaut                                           | Propriétaire de défaut affecté | Point de réaffectation de défaut affecté | Méthode de réaffectation de défaut                                          | État d’erreur | Résolution requise par date | Date d’État |
|------------------------------------------|-------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------|-----------------------|----------------------------------|-------------------------------------------------------------------|---------------|-----------------------------|-------------|
| 1    | Pour les utilisateurs RHM, les coordonnées de numérotation en ligne ne sont pas renseignées via le complément de planification Outlook Teams. | Moyen                                                               | Isabelle gris             | Louis Lahr                       | Tri hebdomadaire-examen de la messagerie à haute priorité aux parties prenantes touchées | Ouvre          | DQP                        | 1/12/2018   |



<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/> <br/>Points de décision</td><td><ul><li>Décidez et acceptez les priorités des défauts pour la prise en charge de votre plan de test.</li><li>Déterminez le point d’escalade pour chaque zone de défaut.</li><li>Déterminez le plan de réaffectation et de triage des défauts à suivre en fonction de la priorité.</li><li>Déterminez le plan de communication et de triage des erreurs pour la réaffectation.</li><li>Déterminez la cadence de réunion d’examen de défaut.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Étapes suivantes</td><td><ul><li>Documentez les priorités relatives aux défauts approuvés.</li><li>Documentez le point d’escalade pour chaque zone de focalisation potentielle.</li><li>Documentez le plan de triage et de triage des défauts en fonction de critères approuvés.</li><li>Documentez les instructions relatives aux rapports de défectuosité.</li><li>Planifiez la série de réunions de triage des défauts.</li></ul></td></tr>
</table>



### <a name="define-and-document-testing-deliverables"></a>Définir et documenter des livrables

Le dernier et dernier composant de la création d’un plan de test consiste à identifier les résultats en termes de livrables spécifiques pour lesquels le plan de test global sera remis.

À un niveau élevé, il s’agit généralement de:

-   Plan de test

-   Scénarios de test

-   Rapports de défaut

-   Synthèse des résultats de test

-   Acceptation et approbation des tests

#### <a name="test-plan-deliverables"></a>Livrables du plan de test

> [!TIP]
> Vous trouverez ci-dessous un exemple de matrice de livrables d’un plan de test que vous pouvez utiliser pour documenter les livrables à créer, ainsi que les ressources nécessaires pour la révision, l’approbation et la connexion.

| Livrable du plan de test                    | Format livrable du plan de test | Propriétaire du plan de test                                                                                                      | Réviseur du plan de test | Approbateur du plan de test | Date de connexion du livrable du plan de test |
|------------------------------------------|------------------------------|----------------------------------------------------------------------------------------------------------------------------------|--------------------------------|--------------------------------|-------------------------------------|
| Plan de test                                | Mot                         | DÉFINIR                                                                                                                              | DÉFINIR                            | DÉFINIR                            | DÉFINIR                                 |
| Rapports sur la gestion des défauts                | Mot                         | DÉFINIR                                                                                                                              | DÉFINIR                            | DÉFINIR                            | DÉFINIR                                 |
| Rapports d’état des tests                   | Mot                         | DÉFINIR                                                                                                                              | DÉFINIR                            | DÉFINIR                            | DÉFINIR                                 |
| Synthèse des résultats de test                     | Word PPTX                    | DÉFINIR                                                                                                                              | DÉFINIR                            | DÉFINIR                            | DÉFINIR                                 |



<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/> <br/>Points de décision</td><td><ul><li>Déterminez quels produits seront créés et capturés en sortie de chaque phase de test. Pour chaque livrable, décidez de:<ul><li>RTF</li><li>Propriétaire</li><li>Relecteur</li><li>Approbateur</li></ul></li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Étapes suivantes</td><td><ul><li>Documentez une matrice de création et de remise d’un plan de test.</li></ul></td></tr>
</table>


<a name="evaluate-network-readiness"></a>Évaluer la disponibilité du réseau
--------------------------

En tant qu’élément critique prenant en charge votre déploiement d’équipe, la disponibilité du réseau est une partie essentielle des tests qui permettent de garantir l’optimisation du réseau pour la prise en charge des communications de l’équipe. Pour vous assurer que votre réseau est prêt pour les sites concernés, incluez les zones principales répertoriées ci-dessous dans votre stratégie de test générale:

-   Estimation de la bande passante et planification avec le planificateur réseau (via MyAdvisor)

-   Validation de la configuration de qualité de service (QoS)

-   Vérification de connectivité et de performance réseau via la simulation du trafic

-   Validation par tunneling fractionné

### <a name="execute-network-planner-through-myadvisor-for-sites-and-personas-in-scope"></a>Exécuter le planificateur de réseau (via MyAdvisor) pour les sites et les personnes dans l’étendue

Avant l’introduction de services de communication en temps réel tels que teams dans votre environnement, il est important de s’assurer que le réseau a été correctement optimisé et ajusté à partir d’une connexion Azure ExpressRoute (le cas échéant), d’Internet et de la bande passante WAN.

Pour vous aider à déterminer la quantité de bande passante et le niveau d’optimisation du réseau requis pour les sites de l’étendue prenant en charge votre déploiement, vous pouvez exécuter l’outil [Network Planner](https://myadvisor.fasttrack.microsoft.com/CloudVoice/NetworkPlanner/Help?sectionName=DashboardHelp) (via MyAdvisor) pour vérifier la disponibilité du réseau de votre organisation. Pour plus d’informations sur la façon de déterminer la configuration requise pour les équipes via le planificateur de réseaux, voir MyAdvisor: Network Planner.

> [!TIP]
> Pour plus d’informations sur l’onglet **recommandations** , avec des exemples sur la façon de configurer et d’interpréter les résultats, voir [vue d’ensemble des recommandations](https://myadvisor.fasttrack.microsoft.com/CloudVoice/NetworkPlanner/Help?sectionName=RecommendationHelp)du planificateur réseau.


<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/><br/>Points de décision</td><td><ul><li>Déterminez les sites réseau qui font l’objet d’un déploiement de services d’équipe.</li><li>Déterminez la personne requise pour les modalités d’équipe.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Étapes suivantes</td><td><ul><li>Complétez le planificateur de réseaux (via MyAdvisor) pour obtenir la liste des sites dans l’étendue.</li><li>Documentez les résultats de la validation du planificateur de réseaux dans le modèle de résultats de plan de test fourni.</li><li>Vérifiez que le ExpressRoute (le cas échéant), Internet et la bande passante WAN calculée pour les sites dans l’étendue sont alignés sur les valeurs de bande passante actuellement allouées.</li><li>Pour les sites disposant d’une bande passante suffisante, exécutez des plans de remontée et de correction pour résoudre les problèmes de bande passante.</li><li>Établissez une solution de surveillance réseau pour les sites dans le cadre de l’application afin de surveiller l’utilisation de la bande passante et la qualité de service (le cas échéant), les segments Internet et WAN.</li><li>Planifiez une réunion de Comité d’orientation pour vérifier les résultats du planificateur de réseaux.</li><li>Présenter les résultats de la planification de la bande passante au Comité de direction pour identifier les domaines qui nécessitent une correction.</li></ul></td></tr>
</table>


<a name="evaluate-qos-configuration-for-sites-in-scope"></a>Évaluer la configuration de QoS pour les sites dans l’étendue
---------------------------------------------

Dans le cadre de la validation du réseau pour la prise en charge des communications en temps réel, il est même important de s’assurer que le réseau a été correctement configuré et optimisé à partir d’un point de vue QoS.

Pour obtenir des instructions supplémentaires sur la configuration, le déploiement et la validation de la disponibilité du réseau QoS pour teams à l’aide d’une stratégie de groupe, voir [activation de la qualité de](https://docs.microsoft.com/MicrosoftTeams/qos-in-teams)service (QoS) pour Teams.


<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/><br/>Points de décision</td><td><ul><li>Déterminez la configuration de QoS à implémenter.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Étapes suivantes</td><td><ul><li>Configurer QoS.</li><li>Exécuter une validation de la qualité de service (QoS) par le biais des étapes indiquées par le biais des sections «valider via l’objet GPO» et «valider par l’analyseur de messages» ci-dessus.</li></ul></td></tr>
</table>



### <a name="document-qos-configuration-validation-test-results"></a>Résultats du test de validation de la configuration QoS du document

Après avoir effectué un test de validation QoS à l’aide d’une stratégie de groupe pour les sites dans l’étendue, créez un rapport qui résume les résultats de tests à présenter lors de la révision du Comité d’orientation final.

#### <a name="site-a-qos-configuration-validation-testing-summary-report"></a>Site A: rapport de synthèse de vérification de la configuration de QoS

> [!TIP]
> Vous trouverez ci-dessous un exemple de modèle de rapport de synthèse de tests que vous pouvez consulter lors de la réunion du Comité de direction suivant lorsque vous décidez de l’intégration des services d’audioconférence lors de la phase pilote.

**Validation de la configuration QoS via un objet de stratégie de groupe ou un analyseur de message**

**Résumé**des résultats&nbsp;&nbsp;&nbsp;: & # 9744; &nbsp; &nbsp; Pass&nbsp; & # 9744; &nbsp; &nbsp; Partial&nbsp; & # 9744; Réussi

<table>
<tr><th colspan="2">Recommandations en matière de tests </th></tr>
<tr><td>DÉFINIR</td><td>DÉFINIR</td></tr>
<tr><th colspan="2">Test de lowlights  </th></tr><br/><tr><td><strong>Problème</strong>: TBD</td><td><strong>Correction:</strong> DÉFINIR</td></tr>
<tr><th colspan="2">Bloqueurs identifiés </td></tr>
<tr><td><strong>Bloqueur</strong>: TBD</td><td><strong>Correction</strong>: TBD</td></tr>
</table>

> [!TIP]
> Pour faciliter les discussions ultérieures au cours de l’évaluation du Comité d’orientation final, vous pouvez utiliser la [matrice de résultats de test](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_21) mise à jour de [MyAdvisor](https://myadvisor.fasttrack.microsoft.com/) à un document et mettre en évidence des zones supplémentaires qui nécessitent une correction.


<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/><br/>Points de décision</td><td><ul><li>Évaluez les résultats des tests de qualité de service pour vérifier que les équipes du trafic multimédia en temps réel sont marquées et classées en priorité.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Étapes suivantes</td><td><ul><li>Documentez les résultats des tests QoS dans le modèle de résultats de plan de test fourni.</li><li>Exécutez des plans de réaffectation et de correction pour résoudre les problèmes dans lesquels la qualité de service (QoS) n’est pas correctement configurée ou ne fonctionne pas comme prévu pour la prise en charge du trafic multimédia d’équipes.</li></ul></td></tr><li>Planifiez une réunion de Comité d’orientation pour passer en revue les résultats de synthèse des tests.</li><li>Présenter des résultats de synthèse de test au Comité de direction pour identifier les domaines qui nécessitent une correction.</li>
</table>



<a name="execute-split-tunnel-enablement-validation"></a>Exécuter une validation d’activation de tunneling fractionné
------------------------------------------

Il est courant pour les entreprises d’utiliser une ou plusieurs solutions pour fournir un accès à distance, par exemple un réseau privé virtuel ou un réseau privé virtuel (VPN). Ces solutions permettent une connectivité sécurisée et fiable aux ressources et applications métier internes.

Bien que les solutions d’accès à distance puissent fonctionner très bien pour donner accès à certaines applications, lorsqu’il s’agit de l’utilisation d’un réseau multimédia en temps réel dans le cadre de l’utilisation d’un réseau multimédia en temps réel scénario de conférence ou d’appel.

Pour vous assurer que le trafic multimédia d’équipes ne traverse *pas* les solutions d’accès distant de votre environnement, une configuration de tunneling en tunnel sera requise.

Pour obtenir des instructions supplémentaires sur la configuration et la validation de la préparation du réseau de configuration de tunnel partagé pour Teams, voir préparation du [réseau](https://docs.microsoft.com/MicrosoftTeams/prepare-network) .

> [!NOTE]
> Outre le volume de solutions d’accès à distance disponibles sur Marketplace, ce document ne permet pas de fournir des informations spécifiques aux fournisseurs et seules les recommandations générales relatives aux solutions d’accès à distance.


<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/><br/>Points de décision</td><td><ul><li>Déterminez la configuration de tunneling fractionné à implémenter.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Étapes suivantes</td><td><ul><li>Mettre en œuvre une configuration de tunneling fractionné.</li><li>Testez et validez la configuration de tunneling fractionné.</li></ul></td></tr>
</table>


### <a name="document-split-tunnel-configuration-validation-test-results"></a>Résultats du test de vérification de la configuration du tunnel

Une fois que vous avez terminé de tester la configuration de tunneling fractionné pour les sites de l’application, créez un rapport qui résume les résultats des tests et présentez-le au cours de la révision du Comité de direction suivant.

#### <a name="site-a-split-tunnel-configuration-validation-testing-summary-report"></a>Site A: rapport de synthèse de vérification de la configuration du tunnel de fractionnement

> [!TIP]
> Vous trouverez ci-dessous un exemple de modèle de rapport de synthèse de tests que vous pouvez consulter lors de la réunion du Comité de direction suivant lorsque vous décidez de l’intégration des services d’audioconférence lors de la phase pilote.

**Validation de la configuration du tunnel scindé**

**Résumé**des résultats&nbsp;&nbsp;&nbsp;: & # 9744; &nbsp; &nbsp; Pass&nbsp; & # 9744; &nbsp; &nbsp; Partial&nbsp; & # 9744; Réussi

<table>
<tr><th colspan="2">Recommandations en matière de tests </th></tr>
<tr><td>DÉFINIR</td><td>DÉFINIR</td></tr>
<tr><th colspan="2">Test de lowlights  </th></tr><br/><tr><td><strong>Problème</strong>: TBD</td><td><strong>Correction:</strong> DÉFINIR</td></tr>
<tr><th colspan="2">Bloqueurs identifiés </td></tr>
<tr><td><strong>Bloqueur</strong>: TBD</td><td><strong>Correction</strong>: TBD</td></tr>
</table>

> [!TIP]
> Pour faciliter les discussions ultérieures au cours de l’évaluation du Comité d’orientation final, vous pouvez utiliser la [matrice de résultats de test](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_21) mise à jour de [MyAdvisor](https://myadvisor.fasttrack.microsoft.com/) à un document et mettre en évidence des zones supplémentaires qui nécessitent une correction.



<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/><br/>Points de décision</td><td><ul><li>Évaluez les résultats des tests de tunneling fractionné pour vous assurer que le trafic en temps réel des équipes est exclu de la solution d’accès à distance.</li></ol></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Étapes suivantes</td><td><ul><li>Résultats du test de connectivité de tunnel fractionné du document dans le modèle de résultat de plan de test fourni.</li><li>Exécutez des plans de remontée et de correction pour résoudre les problèmes sans qu’un routage approprié puisse exister pour la prise en charge du contenu multimédia d’équipes dans une configuration de tunneling fractionné.</li><li>Planifiez une réunion de Comité d’orientation pour passer en revue les résultats de synthèse des tests.</li><li>Présenter des résultats de synthèse de test au Comité de direction pour identifier les domaines qui nécessitent une correction.</li></ul></td></tr>
</table>



<a name="execute-network-connectivity-and-performance-validation-by-using-the-network-assessment-tool-from-microsoft"></a>Exécuter une connectivité réseau et une validation des performances à l’aide de l’outil d’évaluation réseau de Microsoft
-----------------------------------------------------------------------------------------------------------

L’outil d’analyse de réseau de Microsoft effectue des tests de connectivité et de simulation du trafic en diffusant les paquets audio à l’aide d’une fonction de diffusion en continu pour une période prédéfinie et le nombre d’itérations, sur le site Edge le plus proche qui fournit une connectivité au service Teams. L’un des objectifs de ce test est d’évaluer les métriques de performances réseau en matière de perte de paquets, de gigue, de latence d’aller-retour et de pourcentage de réorganisation de chaque appel simulé. Par ailleurs, le test vérifie qu’une connectivité appropriée est autorisée entre les éléments réseau interne et Edge à tous les points d’entrée Edge qui prennent en charge la connectivité aux services d’équipe.

Pour obtenir des instructions supplémentaires sur la façon de confirmer et d’évaluer la préparation du réseau d’équipes pour les sites désignés dans le cadre de l’application, voir préparation du [réseau](https://docs.microsoft.com/MicrosoftTeams/prepare-network) .

> [!TIP]
> Pour effectuer une analyse de la disponibilité du réseau et un niveau d’exhaustivité pour les sites dans le cadre de l’objet, indiquez un lead pour chaque site qui peut vous aider à améliorer les efforts d’évaluation de la disponibilité du réseau.

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/><br/>Points de décision</td><td><ul><li>Déterminez le profil de test Network Assessment et de connexion pour les sites dans l’étendue.</li><li>Déterminez la configuration requise pour le fichier de configuration de l’analyse réseau pour les sites dans l’étendue.</li></ol></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Étapes suivantes</td><td><ul><li>Configurez la configuration requise du fichier de configuration de l’analyse réseau pour les sites dans l’étendue.</li><li>Effectuer une validation des performances du réseau et de la connectivité pour les sites dans l’étendue.</li></ul></td></tr>
</table>



### <a name="document-network-connectivity-and-performance-validation-test-results"></a>Documentation sur les résultats des tests de connectivité du réseau et de validation des performances

Une fois que vous avez effectué toutes les opérations de connectivité et de performance réseau pour les sites dans le cadre de l’application, créez un rapport qui résume les résultats des tests et présentez-le pendant la prochaine révision du Comité de direction.

#### <a name="site-a-network-connectivity-and-performance-summary-report"></a>Site A: rapport sur la connectivité réseau et le rapport de performance

> [!TIP]
> Vous trouverez ci-dessous un exemple de modèle connectivité réseau et synthèse des performances que vous pouvez utiliser lors de l’évaluation du Comité d’orientation suivant lorsque vous déterminez la disponibilité globale du réseau pour les sites dans l’étendue.

**Emplacement: Seattle [Inside Wired] client vers Office 365**

**Résumé**des résultats&nbsp;&nbsp;&nbsp;: & # 9744; &nbsp; &nbsp; Pass&nbsp; & # 9744; &nbsp; &nbsp; Partial&nbsp; & # 9744; Réussi 



| Mesure                                                        | Cible                                                                                                            | Semaine: Office heures 9:30 AM à 11:00 AM                                                                                                                                                                                                                                                                                                 | Semaine: Office heures 2:30 PM à 4:30 PM | Semaine: après les heures 10:30 à 12:30 AM | Week-end: après heures 9:30 AM à 11:30 AM | Week-end: après heures de 2:30 à 4:30 PM |
|---------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------|-------------------------------------------|------------------------------------------|-----------------------------------------
| Latence (unidirectionnelle)                                             | \<50 ms                                                                                                           | 40 ms                                                                                                                                                                                                                                                                                                                                     | 38 ms                                    | 41 ms                                     | 35 ms                                    | 36 ms                                   |
| Latence (durée de l’aller-retour ou RTT)                             | \<100 ms                                                                                                          | 81 ms                                                                                                                                                                                                                                                                                                                                     | 77 ms                                    | 80 ms                                     | 72 ms                                    | 70 ms                                   |
| Perte de paquets en rafale                                             | \<10% pendant tout intervalle de 200-ms                                                                                  | 3%                                                                                                                                                                                                                                                                                                                                        | deuxième                                       | deuxième                                        | 0,2%                                     | 0,1%                                    |
| Perte de paquets                                                   | \<1% durant tout intervalle de 15 secondes                                                                                   | 0,4%                                                                                                                                                                                                                                                                                                                                      | 0,3%                                     | 0,3%                                      | 0,1%                                     | 0%                                      |
| Gigue entre les arrivées de paquets                                   | \<30 ms pendant tout intervalle de 15 secondes                                                                                | 12 ms                                                                                                                                                                                                                                                                                                                                     | 11 ms                                    | 13 ms                                     | 5 ms                                     | 5 ms                                    |
| Réorganisation des paquets                                                | \<0,05% de paquets en souffrance                                                                                      | 0 %                                                                                                                                                                                                                                                                                                                                        | 0 %                                       | 0 %                                        | 0 %                                       | 0 %                                      |


<table>
<tr><th colspan="2">Recommandations en matière de tests </th></tr>
<tr><td>DÉFINIR</td><td>DÉFINIR</td></tr>
<tr><th colspan="2">Test de lowlights  </th></tr><br/><tr><td><strong>Problème</strong>: latence élevée</td><td><strong>Correction:</strong> Recherchez le routage de paquets et implémentez l’itinéraire idéal.</td></tr>
<tr><td><strong>Problème</strong>: durée de l’aller-retour isn& # 39; t doubler la latence</td><td><strong>Correction:</strong> Recherchez un problème de configuration de routeur ou de pare-feu. Examen des chemins de trafic.</td></tr>
<tr><td><strong>Problème</strong>: perte de paquets élevée </td><td><strong>Correction:</strong> Assurez-vous que le planificateur réseau dispose d’une bande passante suffisante. </td></tr>
<tr><td><strong>Problème</strong>: scintillement élevé </td><td> <strong>Correction:</strong> Déterminez si les valeurs DSCP (Differentiated Services Code point) correctes sont utilisées. </td></tr>
<tr><td><strong>Problème</strong>: perte de paquets élevée </td><td><strong>Correction:</strong> Analyser la perte de paquets. </td></tr>
<tr><td><strong>Problème</strong>: réorganisation des paquets élevés </td><td><strong>Correction:</strong> Examiner la mise en file d’attente et la bande passante du routeur. </td></tr>
<tr><th colspan="2">Bloqueurs identifiés </td></tr>
<tr><td><strong>Bloqueur</strong>: TBD</td><td><strong>Correction</strong>: TBD</td></tr>
</table>


<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/><br/>Points de décision</td><td><ul><li>Évaluez les résultats des tests de connectivité et de l’évaluation réseau pour vous assurer que vous respectez les exigences décrites dans la section <a href="https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance" data-raw-source="[Media quality and network connectivity performance](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance)">qualité multimédia et performances de connectivité réseau</a> pour le segment d’arête et les segments de client.</li><li>Avez-vous évalué les fonctionnalités réseau pour la prise en charge des éléments multimédias en temps réel pour tous les sites dans l’étendue?</li><li> Si votre réseau n’a pas été correctement évalué ou si vous savez qu’il ne prend pas en charge les contenus multimédias en temps réel, vous pouvez désactiver la vidéo et les fonctionnalités de partage d’écran afin de réduire l’impact sur le réseau et d’améliorer les performances de l’équipe pour les utilisateurs.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Étapes suivantes</td><td><ul><li>Documentez les performances du réseau et les résultats des tests de connectivité.</li><li>Exécuter les plans de remontée et de correction pour résoudre les problèmes liés aux sites pour lesquels il n’y a pas assez de bande passante ou les performances du réseau et les exigences de connectivité ne sont pas satisfaites.</li><li>Planifiez une réunion de Comité d’orientation pour passer en revue les résultats de synthèse des tests.</li><li>Présenter des résultats de synthèse de test au Comité de direction pour identifier les domaines qui nécessitent une correction.</li></ul></td></tr>
</table>



<a name="execute-service-number-port-validation"></a>Exécuter une validation de port de numéro de service
--------------------------------------

Si vous devez transférer des numéros dans le cadre de la fourniture de fonctionnalités de numérotation dans les services d’audioconférence prises en charge par Teams, vous devez utiliser un port partiel pour un numéro de service. Cela vous permettra de valider les attentes, les exigences et les chronologies raisonnables dès que vous avez fini de préparer votre déploiement des services d’audioconférence dans votre environnement de production.

Pour effectuer un portage partiel d’un numéro de service de votre fournisseur de services RTC actuel vers Teams, suivez les étapes décrites ci-dessous.

#### <a name="step-1"></a>Étape 1

Identifiez le numéro de test que vous voulez transférer vers Office 365 en tant que numéro de connexion (numéro de service) pour les conférences audio

**Essentielles**

Lorsque vous planifiez votre test de transfert de numéro, veillez à consulter les dernières recommandations en matière de demandes de transfert de numéros dans les questions fréquentes sur le [port de numéro](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/transferring-phone-numbers-common-questions).

#### <a name="step-2"></a>Étape 2

Identifiez et documentez toutes les informations sur le compte (y compris le nom utilisé pour le compte en particulier) pour le transporteur actuel du numéro de test que vous allez transférer.
En règle générale, vous trouverez les informations dont vous avez besoin dans la dernière facture de votre fournisseur de services actuel.

> [!TIP]
> Vous pouvez porter ou transférer des numéros de téléphone dans les pays/régions actuellement pris en charge. Toutefois, le mode de soumission d’une demande de transfert peut varier en fonction du pays ou de la région à partir duquel les numéros de téléphone sont sources. Pour obtenir la liste actualisée des pays/régions actuellement pris en charge, consultez la rubrique [disponibilité des pays et de la région pour les conférences audio et les offres d’appels](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md). </br/><br/>
>   Pour plus d’informations sur le transfert de numéros de téléphone vers une audioconférence, ainsi que les restrictions potentielles, voir [transférer des numéros de téléphone vers office 365](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365) et [restrictions de numérotation gratuites dans Office 365](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/toll-free-dialing-limitations-and-restrictions.).

#### <a name="step-3"></a>Étape 3

Téléchargez et créez une lettre d’autorisation (LOA) pour votre pays/région, en fonction du numéro de service, comme type de transfert de numéro.

> [!NOTE]
> Dans la mesure où les formats LOA peuvent être différents selon le pays, la région ou le type de numéro (c’est-à-dire géographique ou non géographique ou numéro de téléphone ou numéro gratuit), vérifiez que vous utilisez le modèle LOA approprié pour votre type de scénario spécifique. Pour plus d’informations sur le choix de l’LOA, voir [Télécharger une lettre d’autorisation (LOA)](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/download-a-letter-of-authorization-loa) , ou accéder directement à la [page de téléchargement](https://www.microsoft.com/download/details.aspx?id=49167).

> [!NOTE]
> **États-Unis uniquement**<br/>
> Étant donné que nous ne transférons qu’un numéro de service pour ce test, veillez à sélectionner les champs appropriés dans le LOA, comme illustré ci-dessous:

Combien de ![numéros de téléphone transférerez-vous? Réponse: je ne transfère que certains de mes numéros de mon opérateur actuel.] Combien de (media/onboarding-test-plan-image1.png "numéros de téléphone transférerez-vous? Réponse: je ne transfère que certains de mes numéros de mon opérateur actuel.") 


![Quels types de numéros de téléphone allez-vous transférer? Réponse: je transfère des numéros de téléphone de service vocal comme pour les standards automatiques ou les ponts de conférence.] (media/onboarding-test-plan-image2.png "Quels types de numéros de téléphone allez-vous transférer? Réponse: je transfère des numéros de téléphone de service vocal comme pour les standards automatiques ou les ponts de conférence.")

> [!IMPORTANT]
> Si vous avez des numéros de service pour les ponts de visioconférence, les standards automatiques ou d’autres numéros de service, les numéros de téléphone gratuits ou si vous avez plus de 999 numéros de téléphone utilisateur que vous devez transférer à Teams, vous devez envoyer manuellement une demande de transfert.<br/><br/>
>   Lorsque vous transférez manuellement des numéros de téléphone à l’aide d’un LOA, veillez à sélectionner le type de numéro de téléphone correct. Vous devez soumettre des demandes de transfert distinctes pour chaque type de numéro de téléphone que vous voulez transférer.</br><br/>
>   Comme nous voulons tester le processus de transfert de numéro à l’aide d’un numéro de téléphone associé au même numéro de téléphone de facturation (BTN), vous devez vous assurer que le numéro de téléphone de facturation ne correspond *pas* au numéro de téléphone à transférer.

#### <a name="step-4"></a>Étape 4

Dans le portail d’administration du client, accédez à l’onglet **support** , puis créez et envoyez une demande de service. Joignez le fichier LOA Completed pour planifier le numéro de téléphone associé à votre fournisseur de services actuel pour la migration. Pour choisir la méthode de demande de service la plus appropriée à la taille de votre client, reportez-vous à la rubrique [envoi manuel d’une demande de service personnalisée](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/manually-submit-a-custom-service-request).

Après la réception de la demande d’assistance, le support Microsoft assurera le suivi en fonction de la méthode de communication que vous avez choisie et vous avertit de votre statut et des étapes suivantes pour terminer le processus de transfert de numéro.

#### <a name="step-5"></a>Étape 5

Une fois que le numéro a été transféré en tant que nouveau numéro de service dans Office 365, attribuez-lui le numéro en accédant au service d’audioconférence du portail \> d’administration de **Skype entreprise** \> ****. Dans l’onglet **numéros de téléphone** , attribuez le nouveau numéro de service au service de conférence audio.

> [!NOTE]
> Même si cette tâche attribue un nouveau numéro de service à l’audioconférence, au moment de la rédaction de ce code, l’administration de cette tâche est effectuée à l’aide du centre d’administration Skype entreprise.

#### <a name="step-6"></a>Étape 6

À présent que vous avez attribué le numéro de service au service de conférence audio, composez le numéro et confirmez que vous entendez le message d’accueil suivant du service de conférence:

>   «Bienvenue dans le centre de conférence audio. Veuillez entrer un ID de conférence suivi de dièse.»


<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/><br/>Points de décision</td><td><ul><li>Déterminez les numéros de service nationaux qu’il vous faudra transférer, par pays/région.</li><li>Décidez si vous allez exporter des numéros de téléphone gratuits.</li><li>Déterminez le modèle LOA que vous utiliserez.</li><li>Déterminez si votre opérateur actuel (opérateur de perte) permet de défragmenter le numéro de téléphone (c’est-à-dire autorisant les commandes de transfert partiel).</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Étapes suivantes</td><td><ul><li>Rassemblez les informations requises et préparez le LOAs.</li><li>Téléchargez et remplissez les modèles LOA dont vous avez besoin.</li><li>Envoyez des demandes de transfert de service et/ou de numéro gratuit.</li><li>Exécutez la validation des tests pour les numéros portés en les affectant au service d’audioconférence pour l’accès rendez-vous et confirmez qu’ils fonctionnent, comme décrit à l’étape 6, plus haut dans cette section.</li></ul></td></tr>
</table>


### <a name="document-service-number-porting-test-results"></a>Résultats du test de Portage du numéro de service de document

Après avoir effectué tous les tests de transfert de numéros, créez un rapport qui résume les résultats des tests à présenter lors de la révision du Comité de direction suivant.

#### <a name="site-a-number-porting-test-summary-report"></a>Site A: rapport de synthèse des tests de transfert de numéros

> [!TIP]
> Vous trouverez ci-dessous un exemple de modèle de rapport de synthèse de test que vous pouvez utiliser pour passer en revue lors de la réunion du Comité de direction suivant lorsque vous décidez de l’intégration des services d’audioconférence lors de la phase pilote.

**Transfert de numéro de service**

**Résumé**des résultats&nbsp;&nbsp;&nbsp;: & # 9744; &nbsp; &nbsp; Pass&nbsp; & # 9744; &nbsp; &nbsp; Partial&nbsp; & # 9744; Réussi 

<table>
<tr><th colspan="2">Recommandations en matière de tests </th></tr>
<tr><td>DÉFINIR</td><td>DÉFINIR</td></tr>
<tr><th colspan="2">Test de lowlights  </th></tr><br/><tr><td><strong>Problème</strong>: TBD</td><td><strong>Correction:</strong> DÉFINIR</td></tr>
<tr><th colspan="2">Bloqueurs identifiés </td></tr>
<tr><td><strong>Bloqueur</strong>: TBD</td><td><strong>Correction</strong>: TBD</td></tr>
</table>

> [!TIP]
> Pour faciliter la discussion supplémentaire au cours de l’évaluation du Comité d’orientation final, vous pouvez utiliser la [matrice de résultats de test](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_21) mise à jour fournie par [MyAdvisor](https://myadvisor.fasttrack.microsoft.com/) pour documenter et mettre en évidence des zones de test supplémentaires qui nécessitent une correction.


<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/><br/>Points de décision</td><td><ul><li>Déterminez si les numéros de service envoyés pour la migration ont été portés au service de conférence audio.</li><li>Déterminez si vous avez été en mesure d’affecter le numéro de service à un service de conférence audio.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Étapes suivantes</td><td><ul><li>Documentez les résultats des tests de portage de votre numéro.</li><li>Exécutez les plans de remontée et de mise à jour pour résoudre les problèmes rencontrés avec le processus de transfert de numéro, le cas échéant.</li><li>Planifiez une réunion de Comité d’orientation pour passer en revue les résultats de synthèse des tests.</li><li>Présenter les résultats du test de synthèse au Comité d’orientation pour identifier les domaines qui nécessitent une correction.</li></ul></td></tr>
</table>



<a name="execute-your-test-plan-for-audio-conferencing"></a>Exécuter votre plan de test pour les conférences audio
---------------------------------------------

Maintenant que vous avez défini votre plan de test, l’étape suivante consiste à parcourir les cas de test, en insistant sur l’évaluation des fonctionnalités d’administration et d’utilisation de l’audioconférence dans l’objectif. Avant le début du test, vérifiez que les conditions de test répertoriées ci-dessous sont en place.

### <a name="audio-conferencing-testing-prerequisites"></a>Conditions préalables pour le test de l’audioconférence

-   Des cas d’utilisation professionnelle ont été définis pour le service de conférence audio.

-   Les principales parties prenantes ont été identifiées.

-   Le contrat de licence requis pour les services d’audioconférence est disponible et attribué au groupe d’utilisateurs dans l’étendue.

-   La liste des sites d’entreprise et des groupes d’utilisateurs de l’étendue a été identifiée.

-   La liste des numéros de conférence rendez-vous en fonction de la langue des sites et des utilisateurs de votre entreprise qui ont été identifiés et configurés.

-   [Crédits de communication](what-are-communications-credits.md) (si nécessaire) ont été configurés pour permettre à votre organisation d’accéder à des numéros de téléphone de pont de conférence sans frais et de prendre en charge les scénarios de numérotation internationale de conférence.

-   Les paramètres du pont de conférence audio ont été identifiés et configurés pour tous les utilisateurs de l’étendue (longueur du code confidentiel, notifications d’entrée/sortie, préférence de notification d’activation).

-   Les paramètres du plan de numérotation client qui prennent en charge les scénarios de numérotation de l’audioconférence peuvent être identifiés, configurés et appliqués à tous les utilisateurs dans l’ensemble de l’application.

-   Des stratégies de conférence audio ont été identifiées et configurées pour tous les utilisateurs de l’application.

-   Les exigences en matière de conformité de l’audioconférence ont été identifiées et configurées pour tous les utilisateurs de l’étendue.

### <a name="document-audio-conferencing-test-case-passfail-status"></a>État de l’échec du test d’audioconférence du document audio

Comme les scénarios de test sont évalués pour les fonctionnalités d’administration des équipes et de l’audioconférence de l’utilisateur dans le cadre de l’application, effectuez le suivi des résultats de chaque cas de test pour refléter le statut de réussite/partielle/échec, ainsi que l’ID du défaut qui lui est affecté.

#### <a name="audio-conferencing-test-case-status"></a>État du cas de test de l’audioconférence

> [!TIP]
> Vous trouverez ci-dessous un exemple de modèle d’état de cas de test que vous pouvez utiliser pour documenter des résultats de test pour révision lors de la réunion du Comité de direction suivant lorsque vous décidez de l’intégration des services d’audioconférence lors de la phase pilote.


| ID de cas de test                             | Titre du cas de test                             | Description de cas de test                                                                            | Résumé des résultats de cas de test | ID de défaut affecté (le cas échéant)                                                                          |
|------------------------------------------|---------------------------------------------|---------------------------------------------------------|---------------------------|-------------------------------------------------------------------------------------------------------------|
| 1                                        | Planifier une réunion de conférence audio dans teams | Planifiez une réunion en ligne et vérifiez que le pont de conférence est affiché dans l’invitation. |  &#9744; Franchi<br/>&#9744; Couleur<br/> &#9744; Réussi   | Pour les utilisateurs RHM, les coordonnées de numérotation en option ne sont pas renseignées via le complément de planification d’Outlook teams |


<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/><br/>Points de décision</td><td><ul><li>Évaluez l’état de réussite et d’échec du test de haut niveau par site pour les fonctionnalités d’audioconférence de l’étendue.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Étapes suivantes</td><td><ul><li>Documentez les résultats de l’état de cas de test pour tous les cas de test remplis dans l’étendue.</li><li>Planifiez une réunion de Comité d’orientation pour passer en revue les résultats de synthèse des tests.</li><li>Présenter les résultats de l’état de cas de test au Comité d’orientation pour identifier les domaines qui nécessitent une correction.</li></ul></td></tr>
</table>


### <a name="document-audio-conferencing-testing-result-summary"></a>Résumé des résultats du test de conférences audio

Après l’exécution de tous les cas de test prenant en charge les fonctionnalités de conférence audio dans l’étendue, documentez les résultats à réviser au cours d’une réunion de Comité de pilotage lorsque vous décidez de l’activation des services d’audioconférence lors de la phase pilote.

#### <a name="site-a-audio-conferencing-test-case-summary-report"></a>Site A: rapport de synthèse de cas de test de l’audioconférence:

> [!TIP]
> Vous trouverez ci-dessous un exemple de modèle de rapport de synthèse de test que vous pouvez consulter lors de la réunion du Comité de direction suivant lorsque vous décidez de l’intégration des services d’audioconférence lors de la phase pilote.

**Audioconférence teams**

**Résumé**des résultats&nbsp;&nbsp;&nbsp;: & # 9744; &nbsp; &nbsp; Pass&nbsp; & # 9744; &nbsp; &nbsp; Partial&nbsp; & # 9744; Réussi 

<table>
<tr><th colspan="2">Recommandations en matière de tests </th></tr>
<tr><td>DÉFINIR</td><td>DÉFINIR</td></tr>
<tr><th colspan="2">Test de lowlights  </th></tr><br/><tr><td><strong>Problème</strong>: TBD</td><td><strong>Correction:</strong> DÉFINIR</td></tr>
<tr><th colspan="2">Bloqueurs identifiés </td></tr>
<tr><td><strong>Bloqueur</strong>: TBD</td><td><strong>Correction</strong>: TBD</td></tr>
</table>


> [!TIP]
> Pour faciliter les discussions ultérieures au cours de l’évaluation du Comité d’orientation final, vous pouvez utiliser la [matrice de résultats de test](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_21) mise à jour fournie par [MyAdvisor](https://myadvisor.fasttrack.microsoft.com/) pour documenter et mettre en évidence des zones supplémentaires qui nécessitent une correction.



<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/><br/>Points de décision</td><td><ul><li>Évaluez les résultats de synthèse de test de haut niveau par site pour les fonctionnalités de conférence audio dans l’étendue.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Étapes suivantes</td><td><ul><li>Documentez le rapport de synthèse de cas de test une fois tous les résultats de cas de test remplis.</li><li>Planifiez une réunion de Comité d’orientation pour passer en revue les résultats de synthèse des tests.</li><li>Présenter des résultats de synthèse de test au Comité de direction pour identifier les domaines qui nécessitent une correction.</li></ul></td></tr>
</table>


<a name="present-and-report-audio-conferencing-test-findings"></a>Présenter et signaler les résultats des tests de conférence audio
---------------------------------------------------

Une fois toutes les activités de test effectuées et les éventuels défauts ayant un impact sur le niveau faible, planifiez une réunion définitive de clôture avec les parties prenantes en matière de tests désignés. Dans la réunion, adresse:

-   Résumé de l’État

-   Mise en surbrillance/lowlights

-   Leçons apprises

-   Recommandation globale: passez à la phase pilote ou réévaluez les résultats des tests.

-   Résultats de matrice de test (ces valeurs doivent être entièrement documentées dans une annexe)

#### <a name="test-plan-deliverables"></a>Livrables du plan de test:

> [!TIP]
> Vous trouverez ci-dessous un exemple de modèle de livrable de plan de test que vous pouvez utiliser pour documenter les critères requis pour la connexion et la sortie de la phase de test, ou pour suspendre les tests jusqu’à ce que tous les problèmes identifiés soient entièrement résolus.

| Résumé de l’État               | Recommandations/lowlights | Leçons apprises | Recommandations en matière de conclusion |
|------------------------------|----------------------|-----------------|------------------------|
| <ul><li>Taux de tests de cas de test de% TBD</li><li>Tous les tests réussis</li></ul> | DÉFINIR                  | DÉFINIR             | Passer au programme pilote       |


<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/><br/>Points de décision</td><td><ul><li>Déterminez le résumé de l’état des tests.</li><li>Identifiez les tests de mise en surbrillance et lowlights.</li><li>Identifiez les leçons tirées.</li><li>Déterminez les actions de correction qui resteront, le cas échéant.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Étapes suivantes</td><td><ul><li>Vous pouvez inclure les résultats de synthèse du test de document comme suit:<ul><li>Résumé de l’État</li><li>Recommandations/lowlights</li><li>Leçons apprises</li></ul></li><li>Planifiez une réunion finale de Commission pour examiner les résultats des tests.</li><li>Présenter des résultats de synthèse lors d’une étude du Comité d’orientation afin d’obtenir une signature finale permettant de sortir de la phase de test.</li></ul></td></tr>
</table>


