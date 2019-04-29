---
title: Plan de test d’entreprise de l’audioconférence dans Microsoft Teams
author: rmw2890
ms.author: Rowille
manager: serdars
ms.date: 03/13/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: Valider que les attentes de votre organisation sont remplies par le biais de test d’audioconférence dans les fonctionnalités d’équipes, les fonctionnalités et les possibilités d’utilisation.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 597944137ea4e2954165fb71fef2126c1d37c18e
ms.sourcegitcommit: 79ec789a22acf1686c33a5cc8ba3bd50049f94b8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/28/2019
ms.locfileid: "33401072"
---
<a name="define-and-document-your-audio-conferencing-in-teams-test-plan-for-enterprises"></a>Définissez et documentez votre conférence Audio dans le plan de test des équipes pour les entreprises 
===============================================================================

Une fois que vous avez définies et documentées votre conférence dans la réussite de l’entreprise équipes et techniques de mise en œuvre dans le cadre de la phase de prévoir, l’étape suivante est validation que les attentes et les exigences de votre organisation sont remplies par le biais de fonctionnalité, fonctionnalités et convivialité. Vous devez effectuer cette étape de validation avant de déployer un déploiement pilote ou final dans votre environnement de production.

Vous pouvez vous appuyer sur le plan de réussite définis lors de la phase de prévoir pour servir de base pour déterminer les activités, les attentes, caractéristiques et fonctionnalités des cas de test et étendue globale pour être évaluée pendant la phase de test.

<a name="identify-testing-support-stakeholders"></a>Identifier les parties prenantes de prise en charge de test
-------------------------------------

Lorsque vous préparez évaluer les fonctionnalités de conférence Audio, créez une matrice de parties prenantes prise en charge de test pour identifier les rôles requis pour prendre en charge de la phase de test.

> [!TIP]
> Lorsque vous remplissez les équipes de prise en charge des parties prenantes matrice de test, vous pouvez voir que certains rôles sont les mêmes que celles identifiées pendant la phase de prévoir, mais avec les descriptions de rôle inclinées lors du test. Vous devrez peut-être identifier les rôles supplémentaires, selon les besoins de vos scénarios de tests.

#### <a name="teams-testing-support-stakeholder-matrix"></a>Test de matrice des parties prenantes de prise en charge des équipes

> [!TIP]
> Voici un exemple d’un modèle de test prise en charge des parties prenantes que vous pouvez utiliser pour documenter les parties prenantes que vous avez besoin pour prendre en charge de la phase de test.

| Rôle                          | Description du rôle                                                                                                                                                                          | Ressource affectée, informations de contact et l’emplacement |
|-------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------|
| Test de dirigeants  | <ul><li>Vérifier les fonctionnalités des équipes répondant aux besoins ; les relations privilégiées sont fluent commerciaux clés des scénarios par ordre de priorité.</li><li>Servir d’autorité ultime et supposent accountability, de fonctionnalité équipes objectifs d’évaluation.</li><li>Résoudre les problèmes transmis par le responsable de test.</li><li>Promotion de communication au sein de la société sur le test des objectifs.</li><li>Est responsable de la prise de décisions stratégiques clées.</li><li>Être responsable de la disponibilité des ressources nécessaires et de budget pour prendre en charge les efforts de test.</li><li>Lecteur de sensibilisation et acheter dans la campagne de test avec les autres parties prenantes.</li><li>Servir au sponsor test pendant la phase d’évaluation de test.</li></ul>                                                 | TBD                                                  |
| Membres comité    | <ul><li>Intérêt de mettre à jour et des conseils sur la direction générale du déploiement du service de conférence Audio.<li>Aider à conduite insight stratégique par le biais de conduite d’acheter dans l’organisation.</li></ul>                                                                        | TBD                                                  |
| Chef de projet                  |<ul><li> Gérer et responsable de l’équipe de projet.</li><li>Coordonner les partenaires et les équipes de travail dans le projet.</li><li>Être responsable de la création et des plans de gestion de projet répondre aux résultats clés trimestriels.</li><li>Résoudre les problèmes fonctionnel.</li><li>Fournissent des mises à jour régulières aux organisateurs de projet.</li><li>Incorporer les connaissances de l’expérience utilisateur clés identifiés dans les résultats de test dans le plan d’adoption utilisateur globale.</li><li>Prospect business tous les mois et les avis opérationnels, contribuent à analyses d’activité trimestriels.</li></ul>                                                                                                                                                         | TBD                                                  |
| Chef/architecte de la collaboration  | <ul><li>Est responsable de l’exécution de la stratégie de collaboration définie par les dirigeants de l’entreprise.</li><li>Analyser et choisir les produits de collaboration pour la société qui répondent aux objectifs de l’entreprise.</li><li>Est responsable de la conception des opérations pour les produits de collaboration.</li><li>Définir les modèles opération et prise en charge.</li><li>Contribuer aux analyses d’activité mensuels et trimestriels.</li></ul>                                                                                                 | TBD                                                  |
| Gestionnaire de projets               | <ul><li>Développer et mettre à jour le plan de projet.</li><li>Gérer les livrables du projet inséré dans le plan de projet et le budget.</li><li>Enregistrer et de gérer les problèmes du projet, y compris les problèmes.</li><li>Mener des appels quotidienne toutes les semaines.</li><li>Sécurité de collaborer avec et fournir des mises à jour pour privilégiées project.</li><li>Travailler avec les équipes de gestion et la communication de modification interne à mettre à jour les modification approche et la communication des plans de gestion selon vos besoins.</li></ul>                                                                                                                                                   | TBD                                                  |
| Directeur de réseau                  | <ul><li>Fournir l’entrée sur la conception du réseau pendant la phase de découverte.</li><li>Participer à des ateliers de phase de prévoir une planification.</li><li>Coordonner le travail de l’équipe de mise en réseau durant l’exécution du projet.</li></ul>                                                                                                                               | TBD                                                  |
| Directeur de la sécurité                 | <ul><li>Fournir l’entrée sur la conception de la sécurité et les processus au cours de la phase de découverte.</li><li>Participer à des ateliers de phase de prévoir une planification.</li><li>Coordonner le travail de l’équipe de sécurité lors de l’exécution du projet.</li></ul>                                                                                                                | TBD                                                  |
| Directeur de la téléphonie                | <ul><li>Fournir l’entrée sur la conception de téléphonie pendant la phase de découverte.</li><li>Participer à des ateliers de phase de prévoir une planification.</li><li>Coordonner le travail de l’équipe de téléphonie durant l’exécution du projet.</li></ul>                                                                                                                           | TBD                                                  |
| Directeur de bureau                  | <ul><li>Fournir l’entrée sur les clients et le processus de mise à jour pendant la phase de découverte.</li><li>Participer à des ateliers de phase de prévoir une planification.</li><li>Coordonner le travail de l’équipe du bureau pendant l’exécution du projet.</li></ul>                                                                                                              | TBD                                                  |
| Représentants d'unité commerciale | <ul><li>Contribuer à guides utilisateur Kit d’adoption et de la documentation.</li><li>Contribuent à et passer en revue, des exemples d’utilisation.</li></ul>                                                                                                                                   | TBD                                                  |
| Administrateurs informatiques                     | <ul><li>Aide à la planification de test et de l’exécution (ce rôle n’est pour les professionnels de l’informatique).                                                                                                                       | TBD                                                  |
| Propriétaire de service                 | <ul><li>Être responsable de l’opération du service de conférence Audio, ascendants.</li><li>Traiter en tant que propriétaire du service de conférence Audio.</li></ul>                                                                                                               | TBD                                                  |
| Responsable en chef de test             | <ul><li>Définir le plan de test, y compris les activités, dépendances, environnement, objectifs, stratégie, varieront (environnemental et humaine) et la chronologie requis pour la prise en charge de la phase de test.</li><li>Coordonner la préparation des dépendances de plan de test et remise.</li><li>Aligner sur la priorité pour la résolution de l’erreur de droite.</li><li>Servir le chemin de réaffectation pour le test des problèmes qui surviennent.</li><li>Communiquer et de rapport d’état de plan de test avec vos équipes internes et les parties prenantes désignés.</li><li>Documenter et présenter les résultats du test final.</li></ul> | TBD                                                  |
| Testeur de services d’audioconférence     | <ul><li>Passez en revue le plan de test de comprendre test requise, objectifs, chronologie, résolution des problèmes et des cas de test à exécuter.</li><li>Passez en revue et développer des cas de test de prise en charge de la configuration requise pour acceptation et les fonctionnalités de conférence audio.</li><li>Exécuter des cas de test et les résultats des tests de document.</li><li>Défauts de documents qu’ils se présentent et transformer les le responsable de Test pour la définition des priorités et la résolution.</li><li>Test de régression pour fermer défauts après que défaillance résolution a été confirmée.</li></ul>                                                                | TBD                                                  |
| Testeur de réseau                | <ul><li>Passez en revue le plan de test de comprendre test requise, objectifs, chronologie, résolution des problèmes et des cas de test à exécuter.</li><li>Passez en revue les exigences de performances et d’acceptation de la préparation du réseau de prise en charge des cas de test.</li><li>Exécuter les tests liés à la préparation du réseau, y compris la connectivité réseau et validation des performances, la validation de QoS et validation de la configuration de double-tunnel.</li><li>Effectuez validation de bande passante pour les sites dans l’étendue à l’aide du Planificateur de réseau par le biais de MyAdvisor.</li><li>Préparation du réseau résultats des tests du document.</li><li>Défauts de documents qu’ils se présentent et transformer les le responsable de Test pour la définition des priorités et la résolution.</li><li>Test de régression pour fermer défauts après que défaillance résolution a été confirmée.</li></ul>                                                                | TBD                                                  |
| Test de la sécurité               | <ul><li>Passez en revue le plan de test de comprendre test requise, objectifs, chronologie, résolution des problèmes et des cas de test à exécuter.</li><li>Passez en revue et développer des cas de test en matière de sécurité acceptation de prise en charge.</li><li>Exécutez le test relatif à l’acceptation de sécurité pour les cas de test.</li><li>Document sécurité aux tests d’acceptation des résultats.</li><li>Défauts de documents qu’ils se présentent et transformer les le responsable de Test pour la définition des priorités et la résolution.</li><li>Test de régression pour fermer défauts après que défaillance résolution a été confirmée.</li></ul>                                                                | TBD                                                  |
| Testeur de téléphonie              | <ul><li>Passez en revue le plan de test de comprendre test requise, objectifs, chronologie, résolution des problèmes et des cas de test à exécuter.</li><li>Passez en revue les cas de test de prise en charge du service numéros portage acceptation et fonctionnalités requises.</li><li>Exécutez le test au service portage numéro, y compris le port numéro de service vers Office 365.</li><li>Exécuter des cas de test et les résultats des cas de test de document.</li><li>Défauts de documents qu’ils se présentent et transformer les le responsable de Test pour la définition des priorités et la résolution.</li><li>Test de régression pour fermer défauts après que défaillance résolution a été confirmée.</li></ul>                                                                | TBD                                                  |
| Test d’administration de services d’audioconférence | <ul><li>Passez en revue le plan de test de comprendre test requise, objectifs, chronologie, résolution des problèmes et des cas de test à exécuter.</li><li>Passez en revue et développer des cas de test de prise en charge des services d’audioconférence administration acceptation et fonctionnalités requises.</li> <li>Exécuter des cas de test et les résultats des cas de test de document.</li><li>Défauts de documents qu’ils se présentent et transformer les le responsable de Test pour la définition des priorités et la résolution.</li><li>Test de régression pour fermer défauts après que défaillance résolution a été confirmée.</li></ul>                                                                | TBD                                                  |


<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/> <br/>Points de décision</td><td><ul><li>Déterminez quels rôles prise en charge et des parties prenantes tests, vous avez besoin pour tester les fonctionnalités de conférence Audio dans votre environnement.</li><li>Choisir les ressources qui vous affecterez pour les rôles des parties prenantes et prise en charge de test que vous avez identifié.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Étapes suivantes</td><td><ul><li>Les rôles de prise en charge et des parties prenantes tests requis dans votre matrice des parties prenantes test de Support du document.</li><li>Informations de contact et les détails de l’emplacement pour chaque ressource que dans la matrice de parties prenantes de prise en charge de test de la liste de documents.
</table>


<a name="define-audio-conferencing-feature-requirements"></a>Définition des besoins de fonctionnalité de conférence Audio 
-----------------------------------------------

Dans le cadre de la définition des conditions requises de fonctionnalité de conférence Audio pour les utilisateurs dans la portée, une des premières étapes que vous devez avoir effectué pendant la phase de prévoir a été l' [Analyse personnage](https://docs.microsoft.com/MicrosoftTeams/audio-conferencing#assess-environment-and-evaluate-adoption-readiness), où vous avez défini votre audioconférence personnages et des scénarios. Avec cette base identifiée, l’étape suivante consiste à évaluer la dernière équipes public feuille de route pour déterminer :

-   Les fonctionnalités de conférence Audio que vous allez déployer pour les utilisateurs dans l’étendue.

-   Utilisateur attendue audioconférence fonctionnalités exigences, votre Skype actuel pour paysage de déploiement d’entreprise, Exchange et SharePoint.

-   Si vous pouvez confirmer que les fonctionnalités de conférence Audio décrites dans la feuille de route public le plus récent répondent à vos utilisateurs, les fonctionnalités et exigences d’étendue dans la chronologie de votre déploiement

> [!TIP]
> La feuille de route équipes le plus récent pour identifier les fonctionnalités de conférence Audio dans la portée de votre déploiement se trouvent à <https://aka.ms/O365Roadmap>.

Maintenant que les personnages d’audioconférence et les fonctionnalités ont été définies, les critères d’évaluation suivant sera l’expérience de l’interopérabilité avec des équipes. Pour plus d’informations sur l’expérience de l’interopérabilité avec les options de configuration disponibles, consultez [les équipes Microsoft et Skype pour l’interopérabilité de l’entreprise](https://docs.microsoft.com/microsoftteams/teams-and-skypeforbusiness-coexistence-and-interoperability).

#### <a name="audio-conferencing-feature-definition"></a>Définition de fonctionnalité de conférence audio

> [!TIP]
> 
> Voici un exemple d’un modèle de définition de conférence audio que vous pouvez utiliser pour l’administration de services d’audioconférence de document et les fonctionnalités de groupe utilisateur à évaluer.

| Échelle de l’entreprise   | Réunions de collaboration    | Plateforme et appareils   | Professionnels de l’informatique  | Groupe supplémentaires, spécifiques au site  | Conditions sont remplies par la dernière feuille de route équipes |
|-------------------------------------------|----------------------------|------------------|------------------------|-------------------|-------------------|
| <ul><li>Planifier des réunions de conférence Audio via :<ul><li>Complément planification Outlook</li><li>Client Teams</li></ul></li><li>Hébergement de réunions privées et canal</li><li>Hébergement de réunions avec des participants jusqu'à 80</li><li>Fonctionnalité de conférence audio</li><li>Participation anonyme</li><li>Prise en charge de la salle d’attente</li><li>Gestion des participants</li><li>Désactiver les autres participants</li><li>Gestion des périphériques via le client d’équipes</li></ul> |<ul><li>Réunion pré/pendant/post de gestion du cycle de vie Meeting</li><li>Partage de Bureau</li><li>Conversations</li><li>Expériences de réunion immersive</li><li>Partage d'application</li><li>Céder/prendre le contrôle au sein de partage d’application</li></ul> |<ul><li> Prise en charge des fonctionnalités Windows, les réunions de clients Mac équipes</li><li>Fonctionnalité de réunions client navigateur équipes en charge pour :<ul><li>Chrome</li><li>Microsoft Edge</li></ul></li><li>iOS et Android équipes client réunions fonctionnalité prise en charge</li></ul> | <ul><li>Portail de diagnostic de la qualité des appels</li><li>Stratégies de conférence Audio des clients</li><li>Activer l’appel de qualité analytique (CQD)</li></ul> | <ul><li>Valider les équipes basées sur un ordinateur portable d’entreprise image des fonctionnalités de réunion</li><li>Prise en charge des langues spécifiques</li><li>Paramètres de stratégie de groupe appliqués pour un scénario donné d’utilisateurs ou un site spécifique</li></ul> | Oui  |

#### <a name="audio-conferencing-user-functionality-definition"></a>Définition de fonctionnalités audio conférence utilisateur

> [!TIP]
> Vous trouverez ci-dessous un exemple d’un modèle de fonctionnalités utilisateur que vous pouvez utiliser l’expérience utilisateur requis de document repose sur les fonctionnalités de conférence Audio à évaluer.

| Expérience d’Exchange                          | Expérience de SharePoint                            | Expérience de stratégie d’interopérabilité équipes |
|----------------------------------------------|--------------------------------------------------|------------------------------------------|
| <ul><li>Créer des équipes (création d’un groupe Office activée)</li><li>Rejoindre des équipes</li><li>Créer des canaux</li><li>Créer et afficher des réunions</li><li>Modifier une image de profil utilisateur</li><li>Ajouter et configurer des connecteurs</li><li>Ajouter et configurer des onglets</li><li>Ajouter et configurer des bots</li></ul> | <ul><li>Stocker et partager des fichiers dans des conversations d’équipes</li><li>Magasin et de partage et de fichiers dans les salles de conversation privées (basés sur OneDrive)</li></ul> | <ul><li>ChatDefaultClient : par défaut</li><li>CallingDefaultClient : par défaut</li></ul>      |



<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/> <br/>Points de décision</td><td><ul><li> Choisir les fonctionnalités de catégorie de conférence Audio que vous allez déployer dans votre environnement.</li><li>Identifier vos besoins de fonctionnalités utilisateur audioconférence donnés votre actuel Skype pour paysage de déploiement d’entreprise, Exchange et SharePoint.</li><li>Décidez que vous envisagez de déployer l’expérience interopérabilité équipes.</li><li>Passez en revue la feuille de route public équipes le plus récent et déterminer si les fonctionnalités de la charge de travail en cours répondent à votre scénario de déploiement.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Étapes suivantes</td><td><ul><li>Les fonctionnalités de catégorie de conférence Audio requises pour prendre en charge votre déploiement de conférence Audio du document.</li><li>Services d’audioconférence fonctionnalité et interopérabilité besoins des utilisateurs donnés votre actuel Skype pour SharePoint, Exchange et Business paysage de déploiement du document.</li><li>Si l’équipes public actualisé qui représente les fonctionnalités de conférence Audio respecte les besoins et les exigences de minutage de votre déploiement du document.</li></ul></td></tr>
</table>

<a name="define-and-document-your-audio-conferencing-test-plan"></a>Définissez et documentez votre plan de test Audio conférence
-----------------------------------------------------

Une fois que vous avez défini les fonctionnalités de conférence Audio dans la portée, l’étape suivante consiste à créer le plan de test. À un niveau élevé, le plan de test comprend la stratégie globale de test et la méthodologie que vous allez utiliser pour prendre en charge la validation de la fonctionnalité dans le processus de test.

À un niveau élevé, le plan de test doit inclure :

-   **Test étendue :** Récapitule les domaines (objectifs, des scénarios et objectifs) doit être évaluée en tant que partie de la phase de test

-   **Cas de Test :** L’ensemble des cas de test à valider pour les fonctionnalités de conférence Audio dans la portée

-   **Test de ressources :** Une matrice des ressources requises pour prendre en charge de l’effort de test à partir d’un point de vue environnemental, techniques et le personnel

-   **Planification de test (chronologie) :** Représente les lors de tests commencera combien il est probable à la dernière, et lorsque vous prévoyez de mettre fin à la phase de test

-   **Annuler l’inscription de création de rapports et de correction :** Suivi des instructions pour comment les problèmes de test doivent être déclarées et triés

-   **Anomalies triage et escalade :** Plan pour comment et quand une escalade défaut doit être effectuée.

-   **Suspension et la sortie des critères de test :** Critères du plan d’orientation permettant l’approbation pour quitter la phase de test ou de test pause jusqu'à ce que les défauts par ordre de priorité sont résolus

-   **Tester livrables :** Résumé dont résultats seront développés et remis pour prendre en charge à l’acceptation et quitter le processus de test

> [!TIP]
> 
>   Une méthodologie de test peut déjà exister dans votre organisation, mais les conseils ci-dessous indique les meilleures pratiques qui peuvent être incluses ou exploitées séparément pour les fonctionnalités d’équipes tests dans votre environnement.

Dans les sections qui suivent vous trouverez des instructions prescrites supplémentaires qui vous aideront à des décisions spécifiques et les modèles et les rubriques vous permet de prendre en compte lorsque vous avez terminé votre plan de test.

### <a name="define-and-document-testing-scope"></a>Définissez et documentez la portée du test

Lorsque vous utilisez pour développer votre plan de test, vous devez définir la portée du test, de mise en surbrillance de la charge de travail et la liste des fonctionnalités que vous souhaitiez évaluer.

L’étendue pour correctement évaluer les fonctionnalités de conférence Audio généralement comprend :

-   Préparation de site de conférence audio

-   Expérience utilisateur de conférence audio

-   Administration de conférence audio

#### <a name="audio-conferencing-testing-scope"></a>Étendue de test audio conférence

> [!TIP]
> Voici un exemple de modèle étendue de test que vous pouvez utiliser au document l’administration de conférence Audio et des fonctionnalités de groupe utilisateur à évaluer.

| Préparation de site de conférence audio                                                                                                                                                                                                 | Expérience utilisateur de conférence audio                                                   | Expérience de l’administration de conférence audio                                                                                                  |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------|
| <ul><li>La bande passante planificateur planification (via MyAdvisor)</li><li>Validation de performances et de connectivité réseau (via Skype pour l’outil d’évaluation réseau Business)</li><li> Qualité de la validation du service (QoS)</li><li>Validation de fractionnement-tunnel l’accès à distance</li></ul> |<ul><li>Planification de la conférence rendez-vous</li><li> Participer à la réunion depuis PSTN</li><li>Ajouter des participants par le biais d’un numéro RTC</li></ul> |<ul><li>Attribution de licences</li><li>Gestion de numéro de service</li><li>Numéro de service portage vers Office 365</li><li>Création de rapports de conférence audio</li><li>Création de rapports (CQD) de la qualité des appels</li></ul> |


<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/> <br/>Points de décision</td><td><ul><li>Décider de conférence Audio test étendue en identifiant les fonctionnalités doit être évaluée par sujet.</li><li>Décider supplémentaires buts et objectifs pour l’évaluation.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Étapes suivantes</td><td><ul><li>Les fonctionnalités de conférence Audio doit être évaluée par sujet du document.</li><li>Autres buts et objectifs pour l’évaluation du document.</li></ul></td></tr>
</table>


### <a name="define-and-document-audio-conferencing-test-cases"></a>Définissez et documentez les cas de test d’audioconférence

Une fois que vous avez défini les fonctionnalités de conférence Audio, déploiement du client et les scénarios côte à côte avec Skype pour les entreprises (le cas échéant), l’étape suivante consiste à formuler les cas de test requis pour évaluer les fonctionnalités de conférence Audio dans la portée. À un niveau élevé, le cas de test sont regroupées par sujet généralement et incluent :

-   **Titre des cas de Test :** L’évaluation de sujet de la fonctionnalité de test (par exemple, conférence Audio)

-   **Description des cas de Test :** Les fonctionnalités de résumé décrivant les objectifs du test en cours d’évaluation

-   **Instructions de cas de Test :** Étapes à suivre afin d’exécuter correctement le cas de test en cours d’exécution

-   **Environnement requis (configuration requise) :** Instructions d’installation requises pour exécuter correctement le test

-   **Ressource requise :** Ressources humaines requises pour l’évaluation et l’exécution du test

-   **Résultat attendu :** Le résultat souhaité après que le test se termine avec succès

> [!NOTE]
> L’approche et le niveau de détail requis pour la création de cas de test peuvent varier au sein de votre organisation, il est préférable de suivre une approche qui autorise un niveau de détail adéquat encore allie minutie des raisons de commodité, pour prendre en charge de test global facilité de gestion.

> [!TIP]
> Pour faciliter la création des cas de test comme point de départ, vous trouverez la liste d’informations utilisateur audioconférence à des [réunions d’équipes et les appels](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8).

#### <a name="audio-conferencing-test-case"></a>Cas de test de conférence audio

> [!TIP]
> Voici un exemple de modèle de cas de test que vous pouvez utiliser au document l’administration de conférence Audio et des fonctionnalités de groupe utilisateur à évaluer.

Validation de services d’audioconférence

| ID de cas de test | Titre du cas de test                             | Description des cas de test                                                                       | Environnement requis pour l’exécution de cas de test                                               | Étapes requises pour l’exécution de cas de test                                                                                                                                             | Test des ressources nécessaires |
|--------------|---------------------------------------------|---------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------|
| 1            | Planifier une réunion de services d’audioconférence équipes | Planifier une réunion en ligne et vérifiez que le pont de conférence est affiché dans l’invitation. |<ul><li>Client équipes installé</li><li>Utilisateur activé avec les licences Office 365 suivantes affectés :<ul><li>Office entreprise E5 avec les services d’audioconférence et les équipes Microsoft</li><li>Office entreprise E3 avec les services d’audioconférence et les équipes Microsoft</li></ul></li></ul> |<ol><li>Connectez-vous au client d’équipes.</li><li>Ouvrez Outlook et planifier une nouvelle réunion équipes.</li><li>Vérifiez que la nouvelle invitation de réunion affiche le numéro de pont Microsoft affiché dans le client.</li></ol>      | Testeur de services d’audioconférence |


> [!TIP]
> Pour obtenir des instructions supplémentaires de faciliter le cas de test individuels et création de plan global pour l’évaluation des fonctionnalités de conférence Audio dans votre organisation, passez en revue le [Plan de Test de conférence Audio](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_21) fournis par [MyAdvisor](https://myadvisor.fasttrack.microsoft.com/).


<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/> <br/>Points de décision</td><td><ul><li>Déterminer les fonctionnalités d’administration et d’audioconférence seront évaluées.</li><li>Décider quel environnement de test est requis pour prendre en charge l’exécution de cas de test.</li><li>Déterminez les étapes requises pour l’évaluation des cas de test.</li><li>Choisir les ressources requises pour la bonne exécution du test.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Étapes suivantes</td><td><ul><li>Documenter les cas de test à évaluer, basé sur le modèle de cas de test fourni.</li><li>Inclure le modèle terminé dans le cadre de votre plan de test global.</li></ul></td></tr>
</table>


### <a name="define-and-document-testing-resources"></a>Définissez et documentez les ressources de test

Pour prendre en charge de la phase de test, il est important de développer un plan de ressources détaillant les ressources de personnes, prise en charge et la technologie dont vous aurez besoin. Un élément important du plan de test global, la ressource plan vous aide à que déterminer les dépendances qui peuvent exister et vous donne une idée de haut niveau de la ressource en charge vous pourriez avoir besoin.

À un niveau élevé, ces ressources sont généralement constituées de :

-   **Personnes**: parties prenantes

-   **Technologie**: client, gestion des licences, les périphériques

-   **Prise en charge**: formation (cartes vidéos), prise en charge de l’administration avec chemin de réaffectation défini

#### <a name="testing-resource-requirements"></a>Test des besoins en ressources

> [!TIP]
> Voici un exemple de modèle exigence ressource test que vous pouvez utiliser pour documenter les différents types de ressources requises pour prendre en charge votre phase de test.

[//]: # (Est OK que cet exemple montre comment parle appelant Plans ?)

| Type de ressource | Ressources requises                                           | Description de la ressource |
|---------------|--------------------------------------------------------------|----------------------|
| Personnes        | Parties prenantes tester les testeurs prospects                               | TBD                  |
| Technologie    | Accès à Office 365 avec les services suivants activé :<ul><li>Office 365 E5 licences affectés</li><li>Plan d’appel nationales et internationales affecté</li></ul>    | TBD                  |
| Support       | Responsable de prise en charge de Test administrateur technicien Test de test | TBD                  |




<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/> <br/>Points de décision</td><td><ul><li>Choisir les types de ressources (personnes, la technologie et prise en charge) que vous aurez besoin pour prendre en charge de la phase de test.</li><li>Choisir les ressources spécifiques requis pour les types de ressources que vous avez identifié.</li><li>Décider si vous devez fournir plus de détails pour décrire les types de ressources dont vous avez besoin.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Étapes suivantes</td><td><ul><li>Les types de ressources (personnes, la technologie et prise en charge) que vous aurez besoin pour prendre en charge de la phase de test du document.</li><li>Documenter les ressources spécifiques requis pour les types de ressources que vous avez identifié.</li><li>Si vous décidez qu’il est nécessaire, des détails supplémentaires sur les types de ressources que nécessaires pour prendre en charge de la phase de test du document.</li></ul></td></tr>
</table>

### <a name="define-and-document-a-testing-timeline"></a>Définissez et documentez un scénario de test

Dans le cadre de la définition de plan de test, créez une chronologie qui décrit la planification lorsque vous prévoyez d’effectuer des activités de test et d’atteindre des jalons de haut niveau.

À un niveau élevé, il se compose généralement de :

-   **Tâche :** Activité haut niveau

-   **Jalon :** Objectif de haut niveau, ou la progression qui s’est terminée

-   **Ressource requise :** Test des ressources requises pour prendre en charge la remise du jalon ou tâche identifiée

-   **La date de début :** La date de sur que l’activité, jalon ou la tâche a été effectuée

-   **Date de fin :** La date à par que laquelle l’activité, jalon ou la tâche se termine

-   **Propriétaire :** Ressource affectée qui doit s’assurer que l’activité, jalon ou la tâche est terminée sur le temps, selon la date de fin

-   **Estimation :** Nombre d’heures que les ressources affectées anticiper il aura pour s’assurer que l’activité, jalon ou la tâche est terminée sur le temps

#### <a name="testing-scheduling-and-timeline-requirements"></a>Test des exigences de planification et de la chronologie

> [!TIP]
> Voici un exemple d’un modèle de test chronologie exigence que vous pouvez utiliser pour documenter les dates prévues pour lors des activités de test doit se terminer ou jalons transmis par.

| Tâche                                     | Jalon       | Date de début                                                             | Date de fin | Propriétaire | Ressources affectées | Estimation |
|------------------------------------------|-----------------|------------------------------------------------------------------------|-----------------|-------|--------------------|------------|
| Rapport de test                              | TBD             | TBD                                                                    | TBD             | TBD   | TBD                | Heures à déterminer  |
| L’exécution de cas de test : Conférence Audio  | TBD             | TBD                                                                    | TBD             | TBD   | TBD                | Heures à déterminer  |
| D’exécution de cas de test : Préparation du réseau   | TBD             | TBD                                                                    | TBD             | TBD   | TBD                | Heures à déterminer  |


<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/> <br/>Points de décision</td><td><ul><li>Décider d’activité de chronologie, jalon et les tâches dont vous avez besoin pour effectuer le suivi.</li><li>Choisir les ressources que vous devrez affecter.</li><li>Choisir la date à que laquelle à effectuer.</li><li>Identifier le propriétaire de la remise.</li><li>Déterminer combien de temps faut-il pour effectuer l’activité, un jalon ou une tâche.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Étapes suivantes</td><td><ul><li>Documenter votre scénario de test à l’aide du modèle fourni et incluent :<ul><li>Activité de chronologie, de jalon et les tâches qui doivent être suivis.</li><li>Ressources qui doivent être attribués.</li><li>Date de fin prévue.</li><li>Propriétaire de remise.</li><li>Temps nécessaire pour effectuer l’activité, un jalon ou une tâche.</li></ul></li><li>Inclure le modèle terminé dans le cadre de votre plan de test global.</li></ul></td></tr>
</table>



### <a name="define-and-document-test-defect-report-criteria"></a>Définissez et documentez les critères de rapport de test défaut

Comme des cas de test au sein d’une phase donnée ou d’un flux de données sont exécutées, problèmes peuvent survenir lorsque le résultat du cas de test en cours d’exécution n’est pas attendue.

Lorsque ces types de résultats se produisent, ils doivent être consignés dans un plan de rapport et de correction de défaut qui est modifiée pour le responsable de test désigné pour passer en revue les, création de rapports et la résolution de l’erreur.

En règle générale, un plan de rapport et de correction de défaut inclut les éléments suivants :

-   **Anomalies ID :** Le numéro attribué à ce problème

-   **ID de cas de test est affectée**: le numéro assigné au cas de test qui a été évalué au moment où l’erreur a été identifié

-   **Anomalies description :** Résumé du problème

-   **Environnement/étapes à reproduire :** Résumé de la configuration de l’environnement test, ainsi que les étapes exactes requises à reproduire le problème

-   **Gravité de l’erreur**: l’impact du problème, allant empêche le cas de test de l’approbation son accepté avec un minimum de risques. Voici quelques exemples peuvent :

-   **Faible :** Le problème a peu d’impact et empêche le cas de test d’atteindre acceptation si le problème peut être résolu ultérieurement.

-   **Support :** Le problème a eu un impact important, mais ne sont pas empêcher le cas de test d’atteindre acceptation si le problème peut être résolu avant la fin de la phase de test.

-   **Haute :** -le problème a un impact majeur sur le cas de test. Le problème doit être résolu avant de pouvoir accepter le cas de test.

-   **État :** Présente le problème résolu, il est ouvert, ou encore à l’étude

-   **Envoyé par :** Le testeur qui a signalé le problème

-   **Propriétaire affecté :** La ressource affectée à partir de l’équipe de test qui est chargé de résoudre le problème

-   **Plus d’informations de prise en charge :** Cela peut inclure, mais n’est pas limité à : journaux côté client, captures d’écran ou vidéo du problème.

Comme les testeurs s’exécuter les cas de test dans votre plan de test, ils doivent être sûr effectuer un plan de rapport et de correction de défaut pour les problèmes qui surviennent.
Cela met en évidence impact potentiel qui pourrait entraver ou même interrompre le processus de test d’évaluation.

#### <a name="testing-defect-report-and-remediation-plan"></a>Planifier les tests de rapport et de correction

> [!TIP]
> Voici un exemple de modèle de rapport et de planifier la mise à jour que vous pouvez utiliser pour documenter les problèmes décelées au cours de la phase de test.

| ID d’erreur                                | ID de cas de test affecté | Description de l’erreur                                                                                                                           | Environnement /steps à reproduire                                                                                                                    | Niveau de gravité | État | Envoyé par | Propriétaire affecté | Prise en charge plus d’informations (journaux, captures d’écran, etc.) |
|------------------------------------------|-----------------------|----------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------|----------|--------|--------------|----------------|---------------------------------------------------|
| 1                                        | 1                     | Pour les utilisateurs qui sont activés pour les réunions hébergées régional (RHM), rendez-vous coordonnées ne sont pas remplies via Outlook équipes de planification des compléments | Déplacer un compte de test vers une autre région RHM.<br/> Se connecter à Outlook et essayez de planifier une conférence audio équipes via Outlook équipes de planification des compléments | Moyen   | Fermé | Louis Lahr   | Lisa gris      | Journal des équipes côté client<br/> Capture d’écran du client équipes     |


<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/> <br/>Points de décision</td><td><ul><li>Déterminez les niveaux de gravité critères défaut vous affecterez pour prendre en charge de l’effort de test.</li><li>Décider quels défaut test critères, que vous devez documenter si des problèmes se produisent pendant les tests de création de rapports.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Étapes suivantes</td><td><ul><li>Documenter l’erreur test de création de rapports critères requis dans le modèle fourni.</li><li>Inclure le modèle terminé dans le cadre de votre plan de test global.</li></ul></td></tr>
</table>


### <a name="define-and-document-exit-and-suspension-criteria"></a>Définissez et documentez les critères de sortie et de suspension

Dans le cadre du processus de l’exécution du test plan global, vous devez définir des critères pour indiquer le point auquel vous devez suspendre les efforts de test par rapport à des exigences qui doivent être remplies pour l’obtention d’approbation et de fermeture de la phase de test.

#### <a name="test-plan-exit-and-suspension-criteria"></a>Critères de suspension et la sortie de plan de test

> [!TIP]
> Vous trouverez ci-dessous un exemple de modèle de critères de suspension et la sortie que vous pouvez utiliser dans votre plan de test pour les critères de document est nécessaire pour obtenir l’approbation, quitter la phase de test ou suspendre des activités de test.

| Test des critères de sortie                            | Critères de suspension de test                      |
|--------------------------------------------------|--------------------------------------------------|
|<ul><li>Tous les cas de test doit atteindre un taux de réussite TBD %</li><li>Tous les cas de test doit avoir été entièrement exécutés</li><li>Tous les cas de test évaluées, toutes les erreurs de gravité élevée doivent être fermés.</li></ul> | <ul><li>Tous les cas de test doit atteindre un taux d’échec TBD %</li><li>Tous les défauts identifiées comme une gravité élevée doivent être résolus avant de test peut continuer.</li></ul> |



<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/> <br/>Points de décision</td><td><ul><li>Déterminez les critères de suspension qui doivent être remplies si les problèmes de test sont identifiés.</li><li>Déterminez les critères de sortie qui doivent être remplies pour obtenir test approbation et prennent en charge la sortie de la phase de test après tout test activités sont terminées.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Étapes suivantes</td><td><ul><li>Critères de suspension et la sortie test requis dans les modèles de test et de sortie fournies du document.</li></ul></td></tr>
</table>


### <a name="define-and-document-the-defect-escalation-process"></a>Définissez et documentez le processus d’escalade défaut

Tout au long de l’exécution de plan de test, vous pouvez découvrir un problème ou d’identifier le problème nécessitant l’escalade vers la ressource adéquate pour la conduite et la détermination de la résolution requise pour permettre le test continuer.

Comme défauts sont identifiés par la gravité appropriée et la priorité, vous créez une matrice d’escalade et triage réviser le processus de mise en correspondance des lorsqu’une escalade est déclenchée et comment, quand et qui est affecté à l’erreur pour approfondir passer en revue les et résolution.

En règle générale, un plan de rapport et de correction de défaut inclut les éléments suivants :

-   **Anomalies ID :** Le numéro que vous avez affecté à ce problème

-   **Anomalies description :** Résumé du problème

-   **Annuler l’inscription d’évaluation de la priorité :** Le niveau de priorité à une erreur de résolution en fonction de défauts et impact sur l’activité gravité. Voici quelques exemples peuvent :

-   **Faible :** Le problème a peu d’impact sur la prévention de la phase de test d’atteindre hors connexion si le problème peut être résolu ultérieurement.

-   **Support :** Le problème a eu un impact important sur la prévention de la phase de test d’atteindre hors connexion s’il ne peut pas être résolu.

-   **Haute :** Le problème a un impact majeur sur la prévention de la phase de test d’atteindre hors connexion s’il ne peut pas être résolu.

-   **Propriétaire de défaut affecté :** La ressource affectée à partir de l’équipe de test qui est chargé de résoudre le problème

-   **Affecté le point d’escalade défaut :** La ressource affectée qui est sur le point d’escalade le problème dans l’organisation (si nécessaire) pour la conduite résolution ; selon la gravité d’erreur

-   **Anomalies état :** Présente le problème résolu, il est ouvert, ou encore à l’étude

-   **Requis résolution par date :** La date à laquelle le problème doit être résolu en

-   **Date d’état :** La date qui reflète l’état de la dernière heure a été mis à jour comme résultat d’une révision du triage défaut

#### <a name="test-plan-defect-escalation"></a>Escalade de défaut de plan de test

> [!TIP]
> Voici un exemple d’un modèle de réaffectation défaut que vous pouvez utiliser dans le cadre de votre plan de test pour documenter le processus d’escalade requis pour la définition des priorités et résolution des erreurs de tests.

| ID d’erreur                                | Description de l’erreur                                                                                          | Évaluation de la priorité de la défaillance                                           | Propriétaire de défaut affecté | Point d’escalade défaut affecté | Méthode d’escalade de défaillance                                          | État d’erreur | Solution requise par date | Date d’état |
|------------------------------------------|-------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------|-----------------------|----------------------------------|-------------------------------------------------------------------|---------------|-----------------------------|-------------|
| 1    | Pour connecter les utilisateurs à extension RHM, coordonnées ne sont pas remplies via Outlook équipes de planification de complément. | Moyen                                                               | Lisa gris             | Louis Lahr                       | E-mail de révision Triage haute priorité hebdomadaire aux parties prenantes affectés | Ouvrir          | ASAP                        | 1/12/2018   |



<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/> <br/>Points de décision</td><td><ul><li>Décider et accord sur les priorités défauts pour prendre en charge votre plan de test.</li><li>Décider du point d’escalade pour chaque zone de défaillance.</li><li>Décider du plan de triage à suivre et une erreur de réaffectation en fonction de la priorité.</li><li>Décider de rapports d’erreur et triage du plan de communication pour escalade.</li><li>Déterminez la cadence de réunion de triage défauts.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Étapes suivantes</td><td><ul><li>Les priorités convenues défaut du document.</li><li>Le point d’escalade pour chaque zone focus potentiels du document.</li><li>Documenter la planification défaut escalade et trier en fonction des critères convenues.</li><li>Documenter votre défaut instructions de création de rapports.</li><li>Planifier la série de réunions de tri défauts.</li></ul></td></tr>
</table>



### <a name="define-and-document-testing-deliverables"></a>Définissez et documentez les livrables tests

Le composant dernière lors de la création d’un plan de test consiste à identifier les objectifs en termes de livrables spécifiques que le plan de test global.

À un niveau élevé, ces incluent généralement, mais ne sont pas limitées à :

-   Plan de test

-   Cas de test

-   Rapports d’erreur

-   Synthèse des résultats

-   Test d’acceptation et hors connexion

#### <a name="test-plan-deliverables"></a>Livrables de plan de test

> [!TIP]
> Voici un exemple d’une matrice de livrable plan test que vous pouvez utiliser les livrables à créer, ainsi que les ressources requises pour la révision, l’approbation et approbation de document.

| Plan de test du livrable                    | Format du livrable de plan de test | Propriétaire du livrable du plan de test                                                                                                      | Réviseur du livrable de plan de test | Approbateur du livrable de plan de test | Plan du livrable approbation date de test |
|------------------------------------------|------------------------------|----------------------------------------------------------------------------------------------------------------------------------|--------------------------------|--------------------------------|-------------------------------------|
| Plan de test                                | Mot                         | TBD                                                                                                                              | TBD                            | TBD                            | TBD                                 |
| Rapports de gestion des défauts                | Mot                         | TBD                                                                                                                              | TBD                            | TBD                            | TBD                                 |
| Test des rapports d’état                   | Mot                         | TBD                                                                                                                              | TBD                            | TBD                            | TBD                                 |
| Synthèse des résultats                     | Word PPTX                    | TBD                                                                                                                              | TBD                            | TBD                            | TBD                                 |



<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/> <br/>Points de décision</td><td><ul><li>Déterminer les livrables doivent être créés et capturé en sortie de chaque phase de test. Pour chaque livrable, décider de son :<ul><li>Format</li><li>Propriétaire</li><li>Réviseur</li><li>Approbateur</li></ul></li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Étapes suivantes</td><td><ul><li>Un plan du livrable création et la fourniture de matrice de test du document.</li></ul></td></tr>
</table>


<a name="evaluate-network-readiness"></a>Évaluer la préparation du réseau
--------------------------

Comme un élément critique de prise en charge de votre déploiement d’équipes, préparation du réseau est une partie essentielle des tests afin de garantir que le réseau est correctement optimisé pour prendre en charge les communications d’équipes. Pour vous assurer que votre réseau est prêt pour les sites dans la portée, inclure les domaines répertoriés ci-dessous dans votre stratégie de test global :

-   Estimation de la bande passante et de planification avec le Planificateur de réseau (via MyAdvisor)

-   Qualité de la validation de la configuration service (QoS)

-   Vérifier les performances et connectivité réseau par le biais de simulation de trafic

-   Tunnel de fractionnement de validation

### <a name="execute-network-planner-through-myadvisor-for-sites-and-personas-in-scope"></a>Exécuter le Planificateur de réseau (via MyAdvisor) pour les sites et les personnages étendue

Avant d’introduire des services de communication en temps réel comme équipes dans votre environnement, il est important pour s’assurer que le réseau a été correctement optimisé et taille Azure ExpressRoute (le cas échéant), internet, et point de vue de la bande passante WAN.

Pour aider à déterminer la quantité de bande passante et le niveau d’optimisation de réseau requise pour les sites dans la portée de prise en charge de votre déploiement, effectuez l’outil [Planificateur de réseau](https://myadvisor.fasttrack.microsoft.com/CloudVoice/NetworkPlanner/Help?sectionName=DashboardHelp) (via MyAdvisor) pour valider les besoins de disponibilité du réseau de votre organisation. Pour plus d’instructions sur la façon de déterminer la configuration réseau requise pour les équipes par le Planificateur de réseau, voir MyAdvisor : planificateur réseau.

> [!TIP]
> Pour plus d’informations sur l’onglet **recommandations** , avec des exemples de la configuration et interpréter les résultats, voir planificateur réseau [Vue d’ensemble des recommandations](https://myadvisor.fasttrack.microsoft.com/CloudVoice/NetworkPlanner/Help?sectionName=RecommendationHelp).


<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/><br/>Points de décision</td><td><ul><li>Déterminer les sites de réseau dans la portée de déploiement des équipes de services.</li><li>Déterminez les personnages requis pour les modalités d’équipes dans l’étendue.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Étapes suivantes</td><td><ul><li>Renseignez le Gestionnaire de réseau (via MyAdvisor) pour la liste des sites qui se trouvent dans l’étendue.</li><li>Résultats de la validation de réseau Planificateur de document dans le modèle de résultats de plan de test fourni.</li><li>Valider ExpressRoute (le cas échéant), internet et la bande passante WAN qui a été calculée pour les sites dans l’étendue s’aligne sur les valeurs de bande passante qui sont actuellement attribuées.</li><li>Pour les sites qui n’ont pas la bande passante adéquate, exécuter des plans de réaffectation et de correction pour résoudre les problèmes de bande passante.</li><li>Établir un réseau de surveillance solution pour les sites dans l’étendue pour surveiller l’utilisation de la bande passante et QoS pour ExpressRoute (le cas échéant), internet et les segments de réseau étendu.</li><li>Organiser une réunion du comité directeur pour passer en revue les résultats du Planificateur de réseau.</li><li>Présenter la bande passante de la planification des résultats au comité de direction pour identifier les zones qui nécessitent une conversion.</li></ul></td></tr>
</table>


<a name="evaluate-qos-configuration-for-sites-in-scope"></a>Évaluer la configuration de QoS pour les sites dans la portée
---------------------------------------------

Dans le cadre de la validation de préparation du réseau pour prendre en charge les communications en temps réel d’équipes, il est également important pour s’assurer que le réseau a été correctement configuré et optimisé du point de vue de la qualité de service.

Pour plus d’instructions sur la façon de configurer, déployer et valider la préparation du réseau QoS pour les équipes à l’aide de la stratégie de groupe, voir [Activation de QoS pour les équipes](https://docs.microsoft.com/MicrosoftTeams/qos-in-teams).


<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/><br/>Points de décision</td><td><ul><li>Déterminez la configuration de la qualité de service à mettre en œuvre.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Étapes suivantes</td><td><ul><li>Configurer la qualité de service.</li><li>Exécuter le contrôle de la qualité de service comme indiqué dans les étapes répertoriées via la « valider via la stratégie de groupe » et « valider à l’aide de l’Analyseur de Message » les sections ci-dessus.</li></ul></td></tr>
</table>



### <a name="document-qos-configuration-validation-test-results"></a>Résultats des tests QoS configuration validation de document

Une fois que vous avez terminé le test à l’aide de la stratégie de groupe pour les sites dans la portée de validation QoS, créez un rapport qui résume les résultats des tests de présenter lors de la révision finale comité directeur.

#### <a name="site-a-qos-configuration-validation-testing-summary-report"></a>Site r : validation de la configuration QoS test du rapport de synthèse

> [!TIP]
> Vous trouverez ci-dessous un exemple teste le modèle de rapport de synthèse que vous pouvez consulter lors de la prochaine réunion du comité lorsque vous décidez lorsqu’aux services d’audioconférence intégrée dans la phase pilote.

**Validation de la configuration QoS par le biais de la stratégie de groupe et de l’Analyseur de Message**

**Résumé des résultats**:&nbsp;&nbsp;&nbsp;& #9744 ; Transmettez&nbsp; &nbsp; &nbsp; & #9744 ; Partiel&nbsp; &nbsp; &nbsp; & #9744 ; Échec

<table>
<tr><th colspan="2">Test d’actualités </th></tr>
<tr><td>TBD</td><td>TBD</td></tr>
<tr><th colspan="2">Enseignements de test  </th></tr><br/><tr><td><strong>Problème</strong>: TBD</td><td><strong>Correction :</strong> TBD</td></tr>
<tr><th colspan="2">BLOQUEURS identifiés </td></tr>
<tr><td><strong>Bloqueur de fenêtres publicitaires</strong>: TBD</td><td><strong>Correction</strong>: TBD</td></tr>
</table>

> [!TIP]
> Pour faciliter la discussion supplémentaire lors de la révision finale comité directeur, vous pouvez utiliser la [matrice des résultats de tests](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_21) de mise à jour de [MyAdvisor](https://myadvisor.fasttrack.microsoft.com/) et mettre en surbrillance des zones supplémentaires qui nécessitent une conversion de documents.


<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/><br/>Points de décision</td><td><ul><li>Évaluer les résultats des tests de qualité de service pour vous assurer que les équipes correctement le trafic multimédia en temps réel est marquée et la priorité.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Étapes suivantes</td><td><ul><li>Résultats des tests QoS de document dans le modèle de résultat de plan de test fourni.</li><li>Exécuter des plans de réaffectation et de correction pour résoudre les problèmes où QoS ne peut pas être configuré correctement ou n’est pas travaille comme prévu pour prendre en charge le trafic multimédia équipes.</li></ul></td></tr><li>Organiser une réunion du comité directeur pour passer en revue les résultats des tests résumé.</li><li>Il est présent test synthèse des résultats au comité de direction pour identifier les zones qui nécessitent une conversion.</li>
</table>



<a name="execute-split-tunnel-enablement-validation"></a>Exécuter le contrôle de fractionnement-tunnel activation
------------------------------------------

Il est courant pour les entreprises à avoir une ou plusieurs solutions pour fournir l’accès à distance, par exemple un réseau privé virtuel ou VPN. Ces solutions permettent de connectivité à des ressources de métier internes et des applications en toute sécurité et de manière fiable.

Bien que les solutions d’accès distant peuvent fonctionne parfaitement pour donner accès à certaines applications, lorsqu’il s’agit du trafic multimédia en temps réel les équipes de tunnel, ces solutions fréquemment entraînent une expérience utilisateur moins optimale pour tous les participants à une audio d’équipes conférence ou appelant scénario.

Pour vous assurer que le trafic multimédia équipes ne *pas* traverser les solutions d’accès distant dans votre environnement, une configuration de double-tunnel seront requise.

Pour plus d’instructions sur la façon de configurer et valider la préparation du double-tunnel configuration réseau pour les équipes, voir Préparation du [réseau](https://docs.microsoft.com/MicrosoftTeams/prepare-network) .

> [!NOTE]
> En raison du volume élevé de solutions d’accès distant disponibles sur le marché, ce document ne peuvent pas fournir plus d’informations spécifiques au fournisseur, les consignes générales uniquement pour ce qui doivent être configurées sur les solutions d’accès à distance.


<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/><br/>Points de décision</td><td><ul><li>Déterminez la configuration de double-tunnel à implémenter.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Étapes suivantes</td><td><ul><li>Mettre en œuvre de la configuration de double-tunnel.</li><li>Tester et valider la configuration du double-tunnel.</li></ul></td></tr>
</table>


### <a name="document-split-tunnel-configuration-validation-test-results"></a>Résultats des tests de validation document configuration tunnel fractionné

Après avoir réalisé test configuration split-tunnel pour les sites dans la portée, créer un rapport qui résume les résultats des tests et présenter lors de la révision comité suivante.

#### <a name="site-a-split-tunnel-configuration-validation-testing-summary-report"></a>Site r : validation de la configuration Split-tunnel test du rapport de synthèse

> [!TIP]
> Vous trouverez ci-dessous un exemple teste le modèle de rapport de synthèse que vous pouvez consulter lors de la prochaine réunion du comité lorsque vous décidez lorsqu’aux services d’audioconférence intégrée dans la phase pilote.

**Validation de la configuration de double-tunnel**

**Résumé des résultats**:&nbsp;&nbsp;&nbsp;& #9744 ; Transmettez&nbsp; &nbsp; &nbsp; & #9744 ; Partiel&nbsp; &nbsp; &nbsp; & #9744 ; Échec

<table>
<tr><th colspan="2">Test d’actualités </th></tr>
<tr><td>TBD</td><td>TBD</td></tr>
<tr><th colspan="2">Enseignements de test  </th></tr><br/><tr><td><strong>Problème</strong>: TBD</td><td><strong>Correction :</strong> TBD</td></tr>
<tr><th colspan="2">BLOQUEURS identifiés </td></tr>
<tr><td><strong>Bloqueur de fenêtres publicitaires</strong>: TBD</td><td><strong>Correction</strong>: TBD</td></tr>
</table>

> [!TIP]
> Pour faciliter la discussion supplémentaire lors de la révision finale comité directeur, vous pouvez utiliser la [matrice des résultats de tests](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_21) de mise à jour de [MyAdvisor](https://myadvisor.fasttrack.microsoft.com/) et mettre en surbrillance des zones supplémentaires qui nécessitent une conversion de documents.



<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/><br/>Points de décision</td><td><ul><li>Évaluer les résultats de tests split-tunnel pour vous assurer que le trafic en temps réel équipes est exclu de la solution d’accès à distance.</li></ol></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Étapes suivantes</td><td><ul><li>Documenter les résultats des tests de connectivité tunnel fractionné dans le modèle de résultat de plan de test fourni.</li><li>Exécuter des plans de réaffectation et de correction pour résoudre les problèmes où un routage correct n’existe pas de prise en charge multimédia équipes au sein d’une configuration de double-tunnel.</li><li>Organiser une réunion du comité directeur pour passer en revue les résultats des tests résumé.</li><li>Il est présent test synthèse des résultats au comité de direction pour identifier les zones qui nécessitent une conversion.</li></ul></td></tr>
</table>



<a name="execute-network-connectivity-and-performance-validation-by-using-the-network-assessment-tool-from-microsoft"></a>Exécuter le contrôle de performances et de connectivité réseau à l’aide de l’outil d’évaluation de réseau à partir de Microsoft
-----------------------------------------------------------------------------------------------------------

L’outil d’évaluation de réseau à partir de Microsoft effectue des tests de connectivité et de la simulation du trafic à diffusion en continu de paquets audio simulés, pour une période prédéfinie et le nombre d’itérations, sur le site le plus proche edge qui permet la connexion au service équipes. Un objectif de ce test est d’évaluer les mesures de performances du réseau pour la perte de paquets, de gigue, latence du parcours circulaire et pourcentage de réapprovisionnement de paquet de chaque appel simulé. En outre, le test vérifie que la connectivité est autorisée entre interne et edge des éléments réseau à tous les points d’entrée edge qui prennent en charge la connexion aux services d’équipes.

Pour plus d’instructions sur la façon de vérifier et d’évaluer la préparation du réseau équipes pour les sites dans l’étendue, consultez la rubrique Préparation du [réseau](https://docs.microsoft.com/MicrosoftTeams/prepare-network) .

> [!TIP]
> Pour effectuer une analyse de disponibilité du réseau et de préparation des sites dans l’étendue, désigner un responsable pour chaque site qui peut vous aider à vos efforts d’évaluation de préparation au réseau.

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/><br/>Points de décision</td><td><ul><li>Décider de l’évaluation de réseau et d’un profil de test de connectivité pour les sites dans l’étendue.</li><li>Décider d’évaluation de la configuration réseau fichier requise pour les sites dans l’étendue.</li></ol></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Étapes suivantes</td><td><ul><li>Configurer l’évaluation de la configuration réseau fichier requise pour les sites dans l’étendue.</li><li>Exécuter la validation de performances et de connectivité réseau pour les sites dans l’étendue.</li></ul></td></tr>
</table>



### <a name="document-network-connectivity-and-performance-validation-test-results"></a>Document réseau connectivité et performances validation résultats des tests

Une fois que vous avez terminé toutes les connectivité réseau et test de performances pour les sites dans la portée, créer un rapport qui résume les résultats des tests et présenter lors de la révision comité suivante.

#### <a name="site-a-network-connectivity-and-performance-summary-report"></a>Site r : réseau connectivité et performances rapport Résumé

> [!TIP]
> Vous trouverez ci-dessous un exemple réseau connectivité et performances synthèse de modèle que vous pouvez utiliser lors de la révision comité suivante lorsque vous êtes détermination de préparation du réseau pour les sites dans l’étendue globale.

**Emplacement : Seattle [inside filaire] client aux résultats Office 365**

**Résumé des résultats**:&nbsp;&nbsp;&nbsp;& #9744 ; Transmettez&nbsp; &nbsp; &nbsp; & #9744 ; Partiel&nbsp; &nbsp; &nbsp; & #9744 ; Échec 



| Mesure                                                        | Cible                                                                                                            | Weekday : heures de bureau 9 h 30 à 11:00                                                                                                                                                                                                                                                                                                 | Weekday : heures de bureau 2:30 PM à 4:30 PM | Weekday : après les heures de 10 h 30 à 12:30 AM | Week-end : après les heures de 9 h 30 à 11:30 AM | Week-end : après les heures de 2:30 PM à 4:30 PM |
|---------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------|-------------------------------------------|------------------------------------------|-----------------------------------------
| Latence (unidirectionnelle)                                             | \<50 ms                                                                                                           | 40 ms                                                                                                                                                                                                                                                                                                                                     | 38 ms                                    | 41 ms                                     | 35 ms                                    | 36 ms                                   |
| Latence (temps d’aller-retour ou durée aller-retour)                             | \<100 ms                                                                                                          | 81 ms                                                                                                                                                                                                                                                                                                                                     | 77 ms                                    | 80 ms                                     | 72 ms                                    | 70 ms                                   |
| Perte de paquets en rafale                                             | \<10 % au cours de l’intervalle de 200-ms                                                                                  | 3%                                                                                                                                                                                                                                                                                                                                        | % 2                                       | % 2                                        | 0,2                                     | 0,1 %                                    |
| Perte de paquets                                                   | \<1 % au cours de l’intervalle de 15-s                                                                                   | 0,4 %                                                                                                                                                                                                                                                                                                                                      | 0,3 %                                     | 0,3 %                                      | 0,1 %                                     | 0%                                      |
| Gigue arrivée entre des batteries de paquets                                   | \<30 ms pendant l’intervalle de 15-s                                                                                | 12 ms                                                                                                                                                                                                                                                                                                                                     | 11 ms                                    | 13 ms                                     | 5 ms                                     | 5 ms                                    |
| Réorganisation des paquets                                                | \<paquets d’ordre 0,05 %                                                                                      | 0 %                                                                                                                                                                                                                                                                                                                                        | 0 %                                       | 0 %                                        | 0 %                                       | 0 %                                      |


<table>
<tr><th colspan="2">Test d’actualités </th></tr>
<tr><td>TBD</td><td>TBD</td></tr>
<tr><th colspan="2">Enseignements de test  </th></tr><br/><tr><td><strong>Problème</strong>: latence élevée</td><td><strong>Correction :</strong> Examiner le routage de paquets et implémentez l’itinéraire idéal.</td></tr>
<tr><td><strong>Problème</strong>: temps d’aller-retour isn& #39 ; t double de la latence</td><td><strong>Correction :</strong> Recherchez un problème de configuration du pare-feu ou votre routeur possible. Examinez les chemins de trafic.</td></tr>
<tr><td><strong>Problème</strong>: la perte de paquets haute </td><td><strong>Correction :</strong> Via le Planificateur de réseau, vérifiez que la bande passante requise a été affecté. </td></tr>
<tr><td><strong>Problème</strong>: gigue haute </td><td> <strong>Correction :</strong> Vérifiez si les valeurs de point (DSCP) de code de services différenciés corrects sont utilisés. </td></tr>
<tr><td><strong>Problème</strong>: la perte de paquets haute </td><td><strong>Correction :</strong> Examinez la perte de paquets. </td></tr>
<tr><td><strong>Problème</strong>: réorganiser les paquets haute </td><td><strong>Correction :</strong> Examinez la bande passante et la file d’attente routeur. </td></tr>
<tr><th colspan="2">BLOQUEURS identifiés </td></tr>
<tr><td><strong>Bloqueur de fenêtres publicitaires</strong>: TBD</td><td><strong>Correction</strong>: TBD</td></tr>
</table>


<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/><br/>Points de décision</td><td><ul><li>Évaluer l’évaluation du réseau et garantir la que satisfaction des exigences décrites dans les <a href="https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance" data-raw-source="[Media quality and network connectivity performance](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance)">performances de connectivité réseau et de qualité multimédia</a> du segment edge et les segments client résultats des tests de connectivité.</li><li>Avez-vous évalué pour prendre en charge des médias en temps réel pour tous les sites dans la portée des fonctionnalités de réseau ?</li><li> Si votre réseau n’a pas été correctement évalué, ou si vous connaissez qu'il ne prend pas en charge les médias en temps réel, désactivera vidéo et les fonctionnalités de partage d’écran afin de réduire le réseau impact et améliorent l’expérience des équipes pour les utilisateurs ?</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Étapes suivantes</td><td><ul><li>Performances du réseau et les résultats des tests de connectivité du document.</li><li>Exécuter des plans de réaffectation et de correction pour résoudre les problèmes avec les sites où il n’est pas suffisamment de bande passante, ou les exigences de performances et de connectivité réseau ne sont pas respectées.</li><li>Organiser une réunion du comité directeur pour passer en revue les résultats des tests résumé.</li><li>Il est présent test synthèse des résultats au comité de direction pour identifier les zones qui nécessitent une conversion.</li></ul></td></tr>
</table>



<a name="execute-service-number-port-validation"></a>Exécuter le contrôle du port numéro de service
--------------------------------------

Si vous devez transférer des nombres dans le cadre de fournir des fonctionnalités dans les services d’audioconférence pris en charge par les équipes de numérotation, vous devez effectuer un port partiel pour un numéro de service. Cela vous permettra de valider les attentes, les exigences et chronologie raisonnable que vous avez terminé la préparation de votre déploiement de services d’audioconférence dans votre environnement de production.

Pour effectuer un port partiel d’un numéro de service à partir de votre fournisseur de services PSTN actuel aux équipes, passez en revue les étapes décrites ci-dessous.

#### <a name="step-1"></a>Étape 1

Identifier le numéro de test que vous souhaitez port vers Office 365 comme un rendez-vous numéro (service) pour une audioconférence

**Important**

Lorsque vous planifiez votre test portage numéro, veillez à consulter les instructions le plus récent pour les demandes portage numéros dans [Numéro de Port questions les plus fréquentes](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/transferring-phone-numbers-common-questions).

#### <a name="step-2"></a>Étape 2

Identifier et documenter toutes les informations de compte (y compris le nom utilisé pour le compte spécifique) pour l’opérateur actuel du nombre de test que vous allez être portage.
En règle générale, vous pouvez trouver les informations que vous avez besoin dans la dernière lettre ou la facture à partir de votre fournisseur de services en cours.

> [!TIP]
> Vous pouvez déplacer ou transfert des numéros de téléphone dans toutes les actuellement pris en charge pays/régions ; Toutefois, la manière de vous soumettez une demande de commande de port peut-être différer en fonction du pays ou région dans lequel les numéros de téléphone sont issus. Pour connaître la liste des pays/régions actuellement pris en charge, consultez la rubrique .</br/> [pays et disponibilité dans la région de conférence Audio et des Plans de l’appel](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)<br/>
>   Pour plus d’informations sur le transfert des numéros de téléphone à la conférence Audio, ainsi que les restrictions potentielles — voir [transférer des numéros de téléphone vers Office 365](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365) et [composer le numéro payant restrictions dans Office 365](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/toll-free-dialing-limitations-and-restrictions.).

#### <a name="step-3"></a>Étape 3

Téléchargez et créer une lettre d’autorisation (lettre d’accord) pour votre pays/région qui repose sur « service nombre » comme type de numéro portage.

> [!NOTE]
> Étant donné que les formats lettre d’accord peuvent différer par type de numéro, région ou pays (qui est géographique et non géographiques ou numéro d’utilisateur et le service ou le numéro gratuit), vérifiez que vous utilisez le modèle de lettre d’accord approprié pour votre scénario spécifique. Pour plus d’informations sur le choix de la lettre d’accord, consultez [télécharger une lettre d’autorisation (lettre d’accord)](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/download-a-letter-of-authorization-loa) , ou accédez directement à la [page de téléchargement](https://www.microsoft.com/download/details.aspx?id=49167).

> [!NOTE]
> **États-Unis uniquement**<br/>
> Étant donné que nous allons portage uniquement un numéro de service pour ce test, veillez à sélectionner les champs appropriés dans la lettre d’accord comme indiqué ci-dessous :

![Comment plusieurs numéros de téléphone vous transférez ? Réponse : je suis à transférer certains de mes numéros de mon opérateur actuel.] (media/onboarding-test-plan-image1.png "Comment plusieurs numéros de téléphone vous transférez ? Réponse : je suis à transférer certains de mes numéros de mon opérateur actuel.") 


![Quel type de numéros de téléphone vous transférez ? Réponse : je suis transfert voice service numéro de téléphone pour les standards automatiques ou de ponts de conférence.] (media/onboarding-test-plan-image2.png "Quel type de numéros de téléphone vous transférez ? Réponse : je suis transfert voice service numéro de téléphone pour les standards automatiques ou de ponts de conférence.")

> [!IMPORTANT]
> Si vous avez des numéros de service pour les ponts de conférence audio, les standards automatiques ou autres numéros de service gratuit numéros de téléphone, ou avoir plus de 999 les numéros de téléphone que vous devez transférer aux équipes, vous devez envoyer manuellement un ordre de port.<br/><br/>
>   Lorsque vous portez manuellement les numéros de téléphone à l’aide d’une lettre d’accord, assurez-vous que vous sélectionnez le type de numéro de téléphone approprié. Vous devez soumettre des demandes de transfert distinctes pour chaque type de numéro de téléphone que vous voulez transférer.</br><br/>
>   Parce que nous voulons tester le numéro portage processus à l’aide d’un numéro de téléphone associé avec le même numéro de téléphone facturation (bouton), vous devez vous assurer que le numéro de téléphone de facturation n’est *pas* inclus avec le numéro de téléphone spécifique portage.

#### <a name="step-4"></a>Étape 4

Dans le portail d’administration de client, cliquez sur l’onglet **prise en charge** et créer et soumettre une demande de service. Joignez le fichier lettre d’accord terminé pour planifier le numéro de téléphone associé à votre fournisseur de services en cours pour la migration. Pour choisir la méthode de demande de service plus appropriée pour la taille de votre client, consultez la rubrique [manuellement pour soumettre une demande de service personnalisé](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/manually-submit-a-custom-service-request).

Une fois que la prise en charge de la demande, Support Microsoft sera suivi selon le mode de communication, vous avez choisi et de notification d’état et les étapes suivantes pour terminer le processus de portage numéro.

#### <a name="step-5"></a>Étape 5

Une fois que le nombre est confirmé comme ayant été portées comme un nouveau numéro de service dans Office 365, affecter le numéro pour le service de conférence Audio en accédant au portail d’administration client \> **Skype pour le centre d’administration Business** \> **vocale**. Sous l’onglet **Numéros de téléphone** , affectez le nouveau numéro de service pour le service de conférence Audio.

> [!NOTE]
> Bien que cela affecte un nouveau numéro de service à la conférence Audio, au moment de la rédaction de ce document, l’administration de cette tâche a été effectuée à l’aide de la Skype entreprise centre d’administration.

#### <a name="step-6"></a>Étape 6

Maintenant que vous avez affecté le nombre de ports de service pour le service de conférence Audio, composez le numéro et assurez-vous que vous entendez le message d’accueil du service de conférence suivants :

>   « Bienvenue dans le centre de conférence audio. Entrez un ID de conférence suivi dièse. »


<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/><br/>Points de décision</td><td><ul><li>Déterminer les numéros de service local que vous devrez port, par pays/région.</li><li>Décider si vous allez port les numéros de téléphone gratuit.</li><li>Choisir le modèle de lettre d’accord que vous allez utiliser.</li><li>Déterminer si votre opérateur actuel (opérateur perdre) autorise la fragmentation numérique de téléphone (autrement dit, permet de commandes port partielle).</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Étapes suivantes</td><td><ul><li>Collecter les informations nécessaires et préparez accord.</li><li>Télécharger et terminez les modèles de lettre d’accord que vous avez besoin.</li><li>Envoi de service et/ou le nombre de requêtes portage gratuit.</li><li>Exécuter le test de validation pour les numéros de ports en leur attribuant au service de conférence Audio pour l’accès à distance et vérifiez qu’ils fonctionnent, comme indiqué à l’étape 6, plus haut dans cette section.</li></ul></td></tr>
</table>


### <a name="document-service-number-porting-test-results"></a>Numéro de service portage des résultats des tests de document

Après avoir réalisé les tests portage des nombres, créez un rapport qui résume les résultats des tests de présenter lors de la révision comité suivante.

#### <a name="site-a-number-porting-test-summary-report"></a>Numéro du site a : portage rapport récapitulatif des tests

> [!TIP]
> Voici un exemple de modèle de rapport de synthèse test que vous pouvez utiliser pour passer en revue les lors de la prochaine réunion du comité lorsque vous décidez lorsqu’aux services d’audioconférence intégrée dans la phase pilote.

**Portage du numéro de service**

**Résumé des résultats**:&nbsp;&nbsp;&nbsp;& #9744 ; Transmettez&nbsp; &nbsp; &nbsp; & #9744 ; Partiel&nbsp; &nbsp; &nbsp; & #9744 ; Échec 

<table>
<tr><th colspan="2">Test d’actualités </th></tr>
<tr><td>TBD</td><td>TBD</td></tr>
<tr><th colspan="2">Enseignements de test  </th></tr><br/><tr><td><strong>Problème</strong>: TBD</td><td><strong>Correction :</strong> TBD</td></tr>
<tr><th colspan="2">BLOQUEURS identifiés </td></tr>
<tr><td><strong>Bloqueur de fenêtres publicitaires</strong>: TBD</td><td><strong>Correction</strong>: TBD</td></tr>
</table>

> [!TIP]
> Pour faciliter la discussion supplémentaire lors de la révision finale comité directeur, vous pouvez utiliser la mise à jour [matrice des résultats de Test](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_21) fourni par [MyAdvisor](https://myadvisor.fasttrack.microsoft.com/) et mettre en surbrillance des zones de test supplémentaires qui nécessitent une conversion de documents.


<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/><br/>Points de décision</td><td><ul><li>Déterminez si soumis à la migration des numéros de service ont été correctement prise en charge par le service de conférence Audio.</li><li>Déterminez si vous avez réussi à affecter le nombre de ports de service pour le service de conférence Audio.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Étapes suivantes</td><td><ul><li>Votre numéro de portage des résultats des tests du document.</li><li>Exécuter des plans de réaffectation et de correction pour résoudre les problèmes que vous avez rencontré avec le processus portage numéro, le cas échéant.</li><li>Organiser une réunion du comité directeur pour passer en revue les résultats des tests résumé.</li><li>Présenter les résultats des tests résumé au comité de direction pour identifier les zones qui nécessitent une conversion.</li></ul></td></tr>
</table>



<a name="execute-your-test-plan-for-audio-conferencing"></a>Exécuter votre plan de test pour une audioconférence
---------------------------------------------

Maintenant que vous avez défini votre plan de test, l’étape suivante consiste à parcourir les cas de test, en mettant l’accent sur l’évaluation de la conférence Audio administration et utilisateur bénéficier des fonctionnalités dans l’étendue. Avant de commencer réellement les tests, vérifiez que la configuration de test répertoriée ci-dessous est en place.

### <a name="audio-conferencing-testing-prerequisites"></a>Conditions préalables de test conférence audio

-   Exemples d’utilisation ont été définies pour le service de conférence Audio.

-   Les principales parties prenantes ont été identifiés.

-   Les licences requises pour les services de conférence Audio est disponible et a été affecté au groupe d’utilisateurs dans l’étendue.

-   La liste des sites d’organisation et des groupes d’utilisateurs dans la portée ont été identifiés.

-   La liste des dédié et partagés audioconférence rendez-vous numéros — avec la préférence de langue pour les sites d’organisation et les utilisateurs dans la portée — ont été identifiés et configuré.

-   [Communications générique](what-are-communications-credits.md) (si nécessaire) ont été configurés pour votre organisation pour fournir un accès gratuit conférence pont téléphone numéros et prise en charge les conférences internationales scénarios d’appel sortant.

-   Paramètres pont de conférence audio conférence ont été identifiés et configurés pour tous les utilisateurs d’étendue (longueur du code confidentiel, les notifications d’entrée/sortie, préférence de notification d’activation).

-   Planifier les paramètres qui prennent en charge la conférence rendez-vous scénarios identifiés, configurés et appliqués pour tous les utilisateurs dans la portée de numérotation du client.

-   Stratégies de conférence audio ont été identifiés et configurés pour tous les utilisateurs dans l’étendue.

-   Exigences de conformité de conférence audio ont été identifiés et configurés pour tous les utilisateurs dans l’étendue.

### <a name="document-audio-conferencing-test-case-passfail-status"></a>Statut de réussite/échec cas de test et de conférence Audio du document

Comme des cas de test sont évalués pour les équipes d’administration et les fonctionnalités de conférence audio d’utilisateur dans la portée, suivre les résultats de chaque cas de test afin de refléter le statut partielle/réussite/échec, ainsi que l’ID affecté de la défaillance en cas de problème imprévu.

#### <a name="audio-conferencing-test-case-status"></a>État de cas de test et de conférence audio

> [!TIP]
> Voici un exemple de modèle de l’état des cas de test que vous pouvez utiliser pour les résultats des tests pour passer en revue les lors de la prochaine réunion du comité lorsque vous décidez lorsqu’aux services d’audioconférence intégrée dans la phase pilote.


| ID de cas de test                             | Titre du cas de test                             | Description des cas de test                                                                            | Récapitulatif de résultats de cas de test | ID d’erreur affecté (le cas échéant)                                                                          |
|------------------------------------------|---------------------------------------------|---------------------------------------------------------|---------------------------|-------------------------------------------------------------------------------------------------------------|
| 1                                        | Planifier une réunion de services d’audioconférence équipes | Planifier une réunion en ligne et vérifiez que le pont de conférence est affiché dans l’invitation. |  & #9744 ; Passer<br/>& #9744 ; Partiel<br/> & #9744 ; Échec   | Pour connecter les utilisateurs à extension RHM, coordonnées ne sont pas remplies via Outlook équipes de planification de la macro complémentaire |


<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/><br/>Points de décision</td><td><ul><li>Évaluer l’état de réussite/échec de haut niveau des cas de test par site pour les fonctionnalités de conférence Audio dans la portée.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Étapes suivantes</td><td><ul><li>Les résultats de l’état cas de test pour tous les cas de test effectuées dans la portée du document.</li><li>Organiser une réunion du comité directeur pour passer en revue les résultats des tests résumé.</li><li>Présenter les résultats de l’état de cas de test au comité de direction pour identifier les zones qui nécessitent une conversion.</li></ul></td></tr>
</table>


### <a name="document-audio-conferencing-testing-result-summary"></a>Résumé des résultats test document audioconférence

Une fois que tous les cas de test dans la portée de prise en charge des fonctionnalités de conférence Audio ont été effectuées par site, les résultats pour passer en revue lors d’une réunion du comité lorsque vous décidez d’activer les services de conférence Audio dans la phase pilote du document.

#### <a name="site-a-audio-conferencing-test-case-summary-report"></a>Rapport Résumé du site audioconférence a : cas de test :

> [!TIP]
> Voici un exemple de modèle de rapport de synthèse test que vous pouvez consulter lors de la prochaine réunion du comité lorsque vous décidez lorsqu’aux services d’audioconférence intégrée dans la phase pilote.

**Services d’audioconférence équipes**

**Résumé des résultats**:&nbsp;&nbsp;&nbsp;& #9744 ; Transmettez&nbsp; &nbsp; &nbsp; & #9744 ; Partiel&nbsp; &nbsp; &nbsp; & #9744 ; Échec 

<table>
<tr><th colspan="2">Test d’actualités </th></tr>
<tr><td>TBD</td><td>TBD</td></tr>
<tr><th colspan="2">Enseignements de test  </th></tr><br/><tr><td><strong>Problème</strong>: TBD</td><td><strong>Correction :</strong> TBD</td></tr>
<tr><th colspan="2">BLOQUEURS identifiés </td></tr>
<tr><td><strong>Bloqueur de fenêtres publicitaires</strong>: TBD</td><td><strong>Correction</strong>: TBD</td></tr>
</table>


> [!TIP]
> Pour faciliter la discussion supplémentaire lors de la révision finale comité directeur, vous pouvez utiliser la mise à jour [matrice des résultats de tests](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_21) fournie par [MyAdvisor](https://myadvisor.fasttrack.microsoft.com/) et mettre en surbrillance des zones supplémentaires qui nécessitent une conversion de documents.



<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/><br/>Points de décision</td><td><ul><li>Évaluer les résultats de synthèse de test de haut niveau par site pour les fonctionnalités de conférence Audio dans la portée.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Étapes suivantes</td><td><ul><li>Une fois que tous les résultats de cas de test ont été effectuées du document du rapport récapitulatif des cas de test.</li><li>Organiser une réunion du comité directeur pour passer en revue les résultats des tests résumé.</li><li>Il est présent test synthèse des résultats au comité de direction pour identifier les zones qui nécessitent une conversion.</li></ul></td></tr>
</table>


<a name="present-and-report-audio-conferencing-test-findings"></a>Présenter et des résultats de test de conférence Audio de rapport
---------------------------------------------------

Une fois toutes les activités de tests ont été effectuées et défauts ayant un impact faible ont été résolus, organiser une réunion de clôture finale avec les parties prenantes tests désignés. Lors de la réunion, l’adresse :

-   Résumé de l’état

-   Mise en surbrillance/enseignements

-   Enseignements

-   Recommandation générale, réévaluez les résultats des tests ou de passer à la phase pilote ?

-   Résultats des tests de matrice (celles-ci doivent être entièrement renseignées dans l’annexe)

#### <a name="test-plan-deliverables"></a>Livrables du plan de test :

> [!TIP]
> Voici un exemple d’un plan de test du livrable modèle que vous pouvez utiliser les critères de document requis pour obtenir l’approbation et de quitter la phase de test ou de suspendre le test jusqu'à ce que tous les problèmes identifiés sont entièrement résolus.

| Résumé de l’état               | Actualités/enseignements | Enseignements | Recommandation de fermeture |
|------------------------------|----------------------|-----------------|------------------------|
| <ul><li>Taux de réussite des cas de test de TBD %</li><li>Tous les tests réussis</li></ul> | TBD                  | TBD             | Passez à pilote       |


<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/><br/>Points de décision</td><td><ul><li>Déterminer l’état des tests résumé.</li><li>Identifier les tests actualités et enseignements.</li><li>Identifier les enseignements.</li><li>Décider quels correction actions restent, le cas échéant.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Étapes suivantes</td><td><ul><li>Document test synthèse des résultats à inclure :<ul><li>Résumé de l’état</li><li>Actualités/enseignements</li><li>Enseignements</li></ul></li><li>Organiser une réunion du comité finale pour passer en revue les résultats des tests.</li><li>Passez en revue présent test synthèse des résultats pendant un comité directeur pour obtenir la signature finale pour la phase de test en quittant l’application.</li></ul></td></tr>
</table>


