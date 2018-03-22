---
title: Entreprise plan de test pour le système téléphonique avec Plans d’appel dans Microsoft Teams
author: rmw2890
ms.author: MyAdvisor
manager: lehewe
ms.date: 03/13/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: Valider que les attentes de votre entreprise sont remplies par le biais de tests système téléphonique dans les fonctions des équipes, des fonctionnalités et de convivialité.
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: b07aa459f5512c30967efe65d011d6911b6f4967
ms.sourcegitcommit: b985035b91ebd7ceff8d50e9e0fa9aa6ff971f3a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/15/2018
---
<a name="define-and-document-your-phone-system-with-calling-plans-in-teams-test-plan-for-enterprises"></a>Définissez et documentez les Plans d’appel de votre système téléphonique dans le plan de test des équipes pour les entreprises 
============================================================================================

Après avoir défini et documenté votre système téléphonique avec les Plans d’appel dans réussite aux équipes de l’entreprise et des plans d’implémentation technique dans le cadre de la phase de Envision, l’étape suivante est validation que les attentes et les exigences de votre organisation sont remplies par le biais de fonctionnalité, la fonctionnalité et facilité d’utilisation. Vous devez effectuer cette étape de validation avant de déployer un déploiement pilote ou final dans votre environnement de production.

Vous pouvez utiliser le plan de réussite définis lors de la phase de Envision pour servir de base pour déterminer les activités, les attentes, caractéristiques et fonctionnalités des cas de test et étendue globale doit être évaluée au cours de la phase de test.

<a name="identify-testing-support-stakeholders"></a>Identifier les parties prenantes de prise en charge du test
-------------------------------------

Lorsque vous préparez évaluer le système téléphonique avec les Plans d’appel de fonctionnalités, créez une matrice des parties prenantes de prise en charge de test pour identifier les rôles requis pour prendre en charge de la phase de test.

> [!TIP]
> Que vous remplissez les équipes de prise en charge des parties prenantes matrice de test, vous pouvez voir que certains rôles sont les mêmes que celles identifiées au cours de la phase de Envision, mais avec les descriptions de rôle inclinées lors du test. Vous devrez peut-être identifier des rôles supplémentaires, en fonction des besoins spécifiques de vos scénarios de tests.

#### <a name="teams-testing-support-stakeholder-matrix"></a>Équipes de test de matrice de prise en charge des parties prenantes

> [!TIP]

> Voici un exemple d’un modèle de test prise en charge des parties prenantes que vous pouvez utiliser pour documenter les parties prenantes que vous avez besoin pour prendre en charge de la phase de test.

| Rôle                          | Description du rôle                                                                                                                                                                          | Ressource affectée, informations de contact et emplacement |
|-------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------|
| Test des dirigeants  | <ul><li>Assurez-vous que les fonctionnalités d’équipes répondent aux besoins de l’entreprise ; les promoteurs exécutifs sont fluent dans résultats métiers clés et les scénarios par ordre de priorité.</li><li>Comme l’autorité ultime et assumer la responsabilité, de fonctionnalité d’équipes objectifs d’évaluation.</li><li>Aider à résoudre les problèmes transmis par le responsable des tests.</li><li>Parrainent des communications au sein de la société sur les objectifs de test.</li><li>Être responsable des décisions stratégiques clés.</li><li>Être responsable de la disponibilité des ressources nécessaires et de budget pour soutenir les efforts de test.</li><li>Lecteur de sensibilisation et acheter dans la campagne de test avec les autres parties prenantes.</li><li>Servir le sponsor de test pendant la phase d’évaluation de test.</li></ul>                                                 | À DÉFINIR                                                  |
| Membres du comité de direction    | <ul><li>Maintenir l’intérêt et fournissent des conseils pour la direction générale du système téléphonique avec appel de Plans de déploiement de service.<li>Aider à la conduite de vue stratégique, par le biais de conduite d’acheter de l’organisation.</li></ul>                                                                        | À DÉFINIR                                                  |
| Chef de projet                  |<ul><li> Gérer et responsable de l’équipe de projet.</li><li>Coordonnées des partenaires et des équipes de travail dans le projet.</li><li>Être responsable de la création et des plans de gestion de projet afin de répondre aux résultats clés trimestriels.</li><li>Résoudre les problèmes de fonctionnel.</li><li>Fournir des mises à jour régulières pour les sponsors du projet.</li><li>Incorporer les apprentissages d’expérience utilisateur clé identifiées dans les résultats de test dans le plan d’adoption utilisateur globale.</li><li>Entraîner l’entreprise mensuel et les revues, contribuer à des analyses d’activité trimestriel.</li></ul>                                                                                                                                                         | À DÉFINIR                                                  |
| Chef/architecte de la collaboration  | <ul><li>Être responsable de l’exécution de la stratégie de collaboration définie par les dirigeants de l’entreprise.</li><li>Analyser et choisir des produits de collaboration de la société qui répondent aux objectifs de l’entreprise.</li><li>Être responsable de la conception des opérations pour les produits de collaboration.</li><li>Définir les modèles d’exploitation et de support.</li><li>Contribuer à des analyses d’activité mensuels et trimestriels.</li></ul>                                                                                                 | À DÉFINIR                                                  |
| Gestionnaire de projets               | <ul><li>Développer et gérer le plan de projet.</li><li>Gérer les livrables dans le plan de projet et le budget du projet.</li><li>Enregistrer et de gérer les problèmes du projet, y compris les procédures d’escalade.</li><li>Effectuer des appels quotidienne hebdomadaires.</li><li>Assurer la liaison avec et fournissent des mises à jour aux sponsors exécutifs de projet.</li><li>Travailler avec les équipes de gestion et la communication interne modifier mettre à jour les modifications approche et communication plans de gestion en fonction des besoins.</li></ul>                                                                                                                                                   | À DÉFINIR                                                  |
| Directeur de réseau                  | <ul><li>Fournir l’entrée sur la conception du réseau lors de la phase de découverte.</li><li>Participer aux ateliers de phase de prévoir une planification.</li><li>Coordonner le travail de l’équipe de mise en réseau au cours de l’exécution du projet.</li></ul>                                                                                                                               | À DÉFINIR                                                  |
| Directeur de la sécurité                 | <ul><li>Fournir l’entrée sur la conception de la sécurité et les processus lors de la phase de découverte.</li><li>Participer aux ateliers de phase de prévoir une planification.</li><li>Coordonner le travail de l’équipe de sécurité pendant l’exécution du projet.</li></ul>                                                                                                                | À DÉFINIR                                                  |
| Directeur de la téléphonie                | <ul><li>Fournir l’entrée sur la conception de téléphonie lors de la phase de découverte.</li><li>Participer aux ateliers de phase de prévoir une planification.</li><li>Coordonner le travail de l’équipe de téléphonie lors de l’exécution du projet.</li></ul>                                                                                                                           | À DÉFINIR                                                  |
| Directeur de bureau                  | <ul><li>Fournir l’entrée sur les clients et le processus de mise à jour lors de la phase de découverte.</li><li>Participer aux ateliers de phase de prévoir une planification.</li><li>Coordonner le travail de l’équipe de bureau lors de l’exécution du projet.</li></ul>                                                                                                              | À DÉFINIR                                                  |
| Représentants d'unité commerciale | <ul><li>Contribuer aux guides de l’utilisateur l’adoption et de matériaux.</li><li>Contribuer à et passer en revue des exemples d’utilisation.</li></ul>                                                                                                                                   | À DÉFINIR                                                  |
| Administrateurs informatiques                     | <ul><li>Aider à la planification de test et de l’exécution (ce rôle est pour les professionnels de l’informatique).                                                                                                                       | À DÉFINIR                                                  |
| Propriétaire de service                 | <ul><li>Être responsable du fonctionnement du système téléphonique avec les Plans d’appel de service, tout.</li><li>Servir en tant que propriétaire du système téléphonique avec les Plans d’appel de service.</li></ul>                                                                                                               | À DÉFINIR                                                  |
| Responsable en chef de test             | <ul><li>Définir le plan de test, y compris les activités, les dépendances, environnement, objectifs, stratégie, varieront (environnementale et humaine) et le délai requis pour la prise en charge de la phase de test.</li><li>Coordonner la préparation pour les dépendances de plan de test et livraison.</li><li>Aligner sur la droite priorité pour la résolution de l’erreur.</li><li>Servir le chemin de réaffectation pour le test des problèmes qui surviennent.</li><li>Communiquer et signaler l’état du plan de test avec vos équipes internes et les parties prenantes désignés.</li><li>Documenter et présenter les résultats de test final.</li></ul> | À DÉFINIR                                                  |
| Système de téléphone avec le testeur de Plans d’appel     | <ul><li>Passez en revue le plan de test pour comprendre le test besoins, objectifs, planning, résolution des problèmes et des cas de test à exécuter.</li><li>Passez en revue et développer des cas de test avec les Plans d’appel des exigences d’acceptation et de fonctionnalités de prise en charge système téléphonique.</li><li>Exécuter des cas de test et résultats des tests.</li><li>Défauts de documents lorsqu’ils surviendront et les remonter pour le responsable de Test pour l’ordre de priorité et de la résolution.</li><li>Tester les régressions de fermer les défauts après que la résolution de l’erreur a été confirmée.</li></ul>                                                                | À DÉFINIR                                                  |
| Testeur de réseau                | <ul><li>Passez en revue le plan de test pour comprendre le test besoins, objectifs, planning, résolution des problèmes et des cas de test à exécuter.</li><li>Passez en revue les cas de test de prise en charge des exigences de performances et d’acceptation de la préparation du réseau.</li><li>Exécuter les tests liés à la préparation de son réseau, y compris la connectivité réseau et validation de performance, la validation de QoS et validation de la configuration de tunnel de la division.</li><li>Terminer la validation de la bande passante pour les sites dans la portée à l’aide du Gestionnaire de réseau par l’intermédiaire de MyAdvisor.</li><li>Document de préparation de son réseau résultats des tests.</li><li>Défauts de documents lorsqu’ils surviendront et les remonter pour le responsable de Test pour l’ordre de priorité et de la résolution.</li><li>Tester les régressions de fermer les défauts après que la résolution de l’erreur a été confirmée.</li></ul>                                                                | À DÉFINIR                                                  |
| Test de la sécurité               | <ul><li>Passez en revue le plan de test pour comprendre le test besoins, objectifs, planning, résolution des problèmes et des cas de test à exécuter.</li><li>Passez en revue et développer des exigences d’acceptation sécurité de prise en charge des cas de test.</li><li>Exécuter le test relatif à l’acceptation de sécurité pour les cas de test.</li><li>Acceptation de sécurité document résultats des tests.</li><li>Défauts de documents lorsqu’ils surviendront et les remonter pour le responsable de Test pour l’ordre de priorité et de la résolution.</li><li>Tester les régressions de fermer les défauts après que la résolution de l’erreur a été confirmée.</li></ul>                                                                | À DÉFINIR                                                  |
| Testeur de téléphonie              | <ul><li>Passez en revue le plan de test pour comprendre le test besoins, objectifs, planning, résolution des problèmes et des cas de test à exécuter.</li><li>Passez en revue les cas de test numéro portage acceptation exigences et de service des fonctionnalités de prise en charge.</li><li>Exécuter les tests liés aux service portage numéro, y compris le port numéro de service vers Office 365.</li><li>Exécuter des cas de test et documenter les résultats de cas de test.</li><li>Défauts de documents lorsqu’ils surviendront et les remonter pour le responsable de Test pour l’ordre de priorité et de la résolution.</li><li>Tester les régressions de fermer les défauts après que la résolution de l’erreur a été confirmée.</li></ul>                                                                | À DÉFINIR                                                  |
| Système de téléphone à appeler Plans de Test d’administration | <ul><li>Passez en revue le plan de test pour comprendre le test besoins, objectifs, planning, résolution des problèmes et des cas de test à exécuter.</li><li>Passez en revue et développer des cas de test système téléphonique de la prise en charge avec l’appel de Plans d’acceptation et de fonctionnalités exigences d’administration.</li> <li>Exécuter des cas de test et documenter les résultats de cas de test.</li><li>Défauts de documents lorsqu’ils surviendront et les remonter pour le responsable de Test pour l’ordre de priorité et de la résolution.</li><li>Tester les régressions de fermer les défauts après que la résolution de l’erreur a été confirmée.</li></ul>                                                                | À DÉFINIR                                                  |


<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/>Points de décision</td><td><ul><li>Décidez quels rôles prise en charge et des parties prenantes tests, vous avez besoin pour test système téléphonique avec les Plans d’appel de fonctionnalités dans votre environnement.</li><li>Déterminer les ressources que vous allez affecter les rôles prise en charge et des parties prenantes de test que vous avez identifié.</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Étapes suivantes</td><td><ul><li>Les rôles de support et des parties prenantes tests requis dans votre matrice de test de partie prenante prennent en charge du document.</li><li>Documenter les informations de contact et les détails de l’emplacement de chaque ressource que dans la matrice de test des parties prenantes prise en charge de la liste.
</table>


<a name="define-phone-system-with-calling-plans-feature-requirements"></a>Définir le système téléphonique avec exigences de Plans d’appel de la fonction 
------------------------------------------------------------

Dans le cadre de la définition de système téléphonique avec appel de Plans fonctionnelle requise pour les utilisateurs dans la portée, une des premières étapes que vous devez avoir effectué au cours de la phase de Envision a l' [Analyse de personnage](https://docs.microsoft.com/MicrosoftTeams/phone-system-with-calling-plans#assess-environment-and-evaluate-adoption-readiness), dans lequel vous avez défini votre système téléphonique avec des Plans d’appel personnages et des scénarios.
Avec cette configuration de référence identifiée, l’étape suivante consiste à évaluer l’équipes public actualisé pour déterminer :

-   Le système téléphonique avec les Plans d’appel de fonctionnalités que vous allez déployer pour les utilisateurs dans la portée.

-   Utilisateur système téléphonique attendus avec les Plans d’appel de fonctionnalités exigences, votre Skype en cours pour le paysage de déploiement d’entreprise, Exchange et SharePoint.

-   Si vous pouvez confirmer que système téléphonique avec les Plans d’appel de fonctionnalités décrits dans le dernier programme public répondre à votre utilisateur, la fonctionnalité et les exigences de portée dans la chronologie de votre déploiement

> [!TIP]
> L’équipes actualisé pour identification système téléphonique avec les Plans d’appel de fonctions dans la portée de votre déploiement, consultez <https://aka.ms/skype2teamsroadmap>.

Maintenant que le système téléphonique avec les fonctionnalités et les Plans d’appel de personnage ont été définis, les critères d’évaluation suivant sera l’expérience de l’interopérabilité avec les équipes. Pour plus d’informations sur l’expérience de l’interopérabilité avec les options de configuration disponibles, consultez [les équipes Microsoft et Skype pour assurer l’interopérabilité de l’entreprise](https://docs.microsoft.com/MicrosoftTeams/teams-and-skypeforbusiness-interoperability).

#### <a name="phone-system-with-calling-plans-feature-definition"></a>Système de téléphone avec définition des Plans d’appel de la fonction

> [!TIP]
> Vous trouverez ci-dessous un exemple d’un système téléphonique avec le modèle de définition des Plans d’appel que vous pouvez utiliser pour documenter le système téléphonique avec les fonctionnalités de groupe d’administration et utilisateur appelant Plans à évaluer.


| À l’échelle de l’entreprise   | Réunions de collaboration    | Plates-formes et périphériques   | Professionnels de l’informatique  | Groupe de commerciaux supplémentaires, spécifiques au site  | Conditions sont remplies par actualisé des équipes |
|-------------------------------------------|----------------------------|------------------|------------------------|-------------------|-------------------|
| <ul><li>Système de téléphone appel de fonctionnalités :<ul><li>Transfert en aveugle</li><li>Appel de blocage</li><li>Transfert d’appel</li><li>ID de l’appelant de masquage</li><li>Prise en charge de E911</li><li>Numérotation d’extension</li><li>Suspendre un appel</li><li>Gestion d’appel multiples</li><li>Sonnerie simultanée</li><li>Messagerie vocale Azure</li></ul></li><li>Support de plan d’appel</li></ul> |<ul><li>Skype pour entreprise-à-appel des équipes</li></ul> |<ul><li> Prise en charge des fonctionnalités de Windows, les réunions d’équipes de Mac clients</li><li>Fonctionnalité de réunions du client navigateur équipes prise en charge pour :<ul><li>Chrome</li><li>Microsoft Edge</li></ul></li><li>iOS et Android équipes client réunions fonctionnalité prise en charge</li><li>Support TTY</li></ul> | <ul><li>Appelez le portail de diagnostic de qualité</li><li>Plan de numérotation de clients</li><li>Stratégies d’ID de l’appelant de clients</li><li>Activer l’appel de qualité analytique (CQD)</li></ul> | <ul><li>Valider des équipes de fonctionnalités basées sur l’image de l’ordinateur portable d’entreprise de la réunion</li><li>Prise en charge de la langue spécifique</li><li>Paramètres d’objet stratégie de groupe appliqués pour un scénario d’utilisateur donné ou d’un site spécifique</li></ul> | Oui  |




#### <a name="phone-system-with-calling-plans-user-functionality-definition"></a>Système de téléphone avec les Plans d’appel de définition de fonctionnalité utilisateur

> [!TIP]
> Ci-dessous un exemple d’un modèle de fonctionnalités utilisateur que vous pouvez utiliser pour documenter l’expérience utilisateur requise repose sur le système téléphonique avec les Plans d’appel de fonctionnalités à évaluer.


| Expérience d’Exchange                          | Expérience de SharePoint                            | Expérience de stratégie d’interopérabilité équipes |
|----------------------------------------------|--------------------------------------------------|------------------------------------------|
| <ul><li>Créer des équipes (création d’un groupe de bureau activée)</li><li>Rejoindre des équipes</li><li>Créer des canaux</li><li>Créer et afficher des réunions</li><li>Modifier une image de profil utilisateur</li><li>Ajouter et configurer des connecteurs</li><li>Ajouter et configurer des onglets</li><li>Ajouter et configurer des bots</li></ul> | <ul><li>Stocker et partager des fichiers dans les conversations d’équipes</li><li>Banque et de partage et de fichiers dans des conversations privées (basées sur OneDrive)</li></ul> | <ul><li>ChatDefaultClient : par défaut</li><li>CallingDefaultClient : par défaut</li></ul>      |


<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/>Points de décision</td><td><ul><li> Choisir quel système de téléphone avec les Plans d’appel de fonctions de catégorie que vous allez déployer dans votre environnement.</li><li>Identifier votre système téléphonique de l’utilisateur avec les Plans d’appel de fonctionnalités exigences votre Skype en cours pour le paysage de déploiement d’entreprise, Exchange et SharePoint.</li><li>Décider que vous allez déployer l’expérience interopérabilité équipes.</li><li>Passez en revue le public actualisé des équipes et décider si les capacités de charge de travail en cours répondent à votre barre de planning de déploiement.</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Étapes suivantes</td><td><ul><li>Le système téléphonique avec les Plans d’appel de fonctions de catégorie requis pour prendre en charge de votre système téléphonique avec le déploiement de Plans d’appel de document.</li><li>Document utilisateur système téléphonique avec les Plans d’appel de la fonctionnalité et les exigences d’interopérabilité donnés votre Skype en cours pour le paysage de déploiement d’entreprise, Exchange et SharePoint.</li><li>Si l’équipes public actualisé représentant le système téléphonique avec les Plans d’appel de fonctionnalités respecte les besoins et les exigences de minutage de votre déploiement du document.</li></ul></td></tr>
</table>

<a name="define-and-document-your-phone-system-with-calling-plans-test-plan"></a>Définissez et documentez votre système téléphonique avec les Plans d’appel de plan de test
------------------------------------------------------------------

Une fois que vous avez défini le système téléphonique avec les Plans d’appel de fonctions dans la portée, l’étape suivante consiste à créer le plan de test. À un niveau élevé, le plan de test englobe la stratégie générale de test et de la méthodologie que vous allez utiliser pour prendre en charge la validation de la fonctionnalité de test.

À un niveau élevé, le plan de test doit inclure :

-   **Test étendue :** Résume les domaines (objectifs, des scénarios et objectifs) à évaluer dans le cadre de la phase de test

-   **Cas de Test :** Le jeu de cas de test à valider pour système de téléphone avec des Plans d’appel de fonctions dans la portée

-   **Ressources de test :** Une matrice des ressources requises pour prendre en charge de l’effort de test à partir d’un point de vue environnemental, techniques et du personnel

-   **Planification de test (montage) :** Représente lorsque les tests commenceront, combien de temps il est susceptible de dernière, et lorsque vous prévoyez la phase de test à la fin

-   **Annuler l’inscription de reporting et la mise à jour :** Instructions pour comment les problèmes de test doivent être déclarés, suivi et triés

-   **Annuler l’inscription de triage et escalade :** Plan pour quand et comment une escalade de défaut devrait être lancée

-   **Les critères de sortie et de suspension de test :** Critères de plan d’orientation pour parvenir à une session quitte la phase de test ou de suspension de test jusqu'à la résolus des défauts par ordre de priorité

-   **Tester des livrables :** Résumé des résultats seront développés et remis pour prendre en charge de la déconnexion d’acceptation et de quitter le processus de test

> [!TIP]
>   Une méthodologie de test peut déjà exister dans votre organisation, mais les conseils ci-dessous reflètent les meilleures pratiques qui peuvent être inclus ou exploitées séparément de fonctionnalités aux équipes de test dans votre environnement.

Dans les sections qui suivent, vous trouverez les conseils prescrits supplémentaires qui aideront à des décisions spécifiques et les modèles et les sujets à prendre en compte lorsque vous réalisez votre plan de test.

### <a name="define-and-document-testing-scope"></a>Définissez et documentez la portée du test

À mesure que vous élaborez votre plan de test, vous devez définir la portée du test, la charge de travail et de la liste des fonctionnalités que vous souhaitiez évaluer la mise en surbrillance.

L’étendue pour évaluer correctement les système téléphonique avec les Plans d’appel de fonctionnalités généralement comprend :

-   Système de téléphone avec les Plans d’appel de la disponibilité du site

-   Système de téléphone avec les Plans d’appel de l’expérience utilisateur

-   Système de téléphone avec les Plans d’appel de l’administration

#### <a name="phone-system-with-calling-plans-testing-scope"></a>Système de téléphone avec l’appel de Plans de test étendue

> [!TIP]
>   Vous trouverez ci-dessous un exemple de modèle de portée de test que vous pouvez utiliser pour documenter le système téléphonique avec les fonctionnalités de groupe d’administration et utilisateur appelant Plans à évaluer.

| Système de téléphone avec les Plans d’appel de la disponibilité du site                                                                                                                                                                                    | Système de téléphone avec les Plans d’appel de l’expérience utilisateur                                                                                                                                                                                         | Système de téléphone avec l’expérience en administration de Plans d’appel                                                                           |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------|
| <ul><li>La bande passante du module Planification (via MyAdvisor)<li></li>Validation de connectivité et les performances du réseau (via le Skype pour l’outil d’évaluation réseau professionnel)<li></li>Qualité de la validation de service (QoS)<li></li>Validation de split-tunnel d’accès à distance</li></ul>|<ul><li>Fonctionnalités de PBX<li></li>RTPC appelant (national et international)<li></li> Passer et recevoir les appels RTPC<li></li>Messagerie vocale Azure<li></li>E911<li></li>Plan de numérotation de clients<li></li>Masquage des ID de l’appelant de clients <li></li>Fonctionnalités de contrôle d’appel avancées (par exemple, le transfert, d’appel sonnerie simultanée)</li></ul> |<ul><li>Attribution de licence</li><li>Numéro d’abonné portage vers Office 365</li><li>Système de téléphone avec appel de Plans de génération de rapports</li><li>Appeler le rapport sur la qualité (CQD)</li></ul> |

<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/>Points de décision</td><td><ul><li>Choisir le système téléphonique avec appel de Plans de test étendue en identifiant les fonctions doit être évaluée par centre d’intérêt.</li><li>Décider des objectifs supplémentaires et des objectifs d’évaluation.</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Étapes suivantes</td><td><ul><li>Le système téléphonique avec les Plans d’appel de fonctionnalités doit être évaluée par le sujet du document.</li><li>Document supplémentaire des objectifs d’évaluation.</li></ul></td></tr>
</table>

### <a name="define-and-document-phone-system-with-calling-plans-test-cases"></a>Définissez et documentez le système téléphonique avec les Plans d’appel de cas de test

Une fois que vous avez défini le système téléphonique avec les Plans d’appel de fonctionnalités, déploiement du client et les scénarios côte à côte avec Skype pour les entreprises (le cas échéant), l’étape suivante consiste à formuler les cas de test nécessaires pour évaluer le système téléphonique avec les Plans d’appel de fonctions de champ d’application. À un niveau élevé, cas de test sont regroupés par zone de focus en général et comprennent :

-   **Titre du cas de Test :** Centre d’intérêt de la fonctionnalité de test est évalué (par exemple, le système téléphonique avec des Plans d’appel)

-   **Description de cas de Test :** Fonctions de résumé décrivant les objectifs du test en cours d’évaluation

-   **Instructions de cas de Test :** Étapes à suivre pour le cas de test en cours d’exécution s’exécute correctement

-   **Environnement requis (prérequis) :** Instructions d’installation requises pour le test s’exécute correctement

-   **Ressource requise :** Ressources du personnel nécessaires pour l’évaluation et l’exécution du test

-   **Résultats attendus :** Le résultat que vous attendiez après que l’essai est effectué avec succès

> [!NOTE]
>   L’approche et le niveau de détail requis pour la création de cas de test peuvent varier au sein de votre organisation, il est conseillé de suivre une approche qui permet un niveau adéquat de détails mais les soldes de précision avec des raisons de commodité, pour prendre en charge le test global facilité de gestion.

> [!TIP]
>   Pour aider à la création de cas de test comme point de départ, consultez la liste de téléphone système Guide de l’utilisateur disponible à des [réunions d’équipes et d’appels](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8).

#### <a name="phone-system-with-calling-plans-test-case"></a>Système de téléphone à appeler des Plans de cas de test

> [!TIP]
>   Vous trouverez ci-dessous un exemple de modèle de cas de test que vous pouvez utiliser pour documenter le système téléphonique avec les fonctionnalités de groupe d’administration et utilisateur appelant Plans à évaluer.

Système de téléphone avec Validation de Plans d’appel

| ID de cas de test | Titre du cas de test               | Description du cas de test                                                  | Environnement requis pour l’exécution du cas de test                                               | Étapes requises pour l’exécution du cas de test                                                                                                                                                          | Test de ressource requise              |
|--------------|-------------------------------|------------------------------------------------------------------------|--------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------|
| 1            | Un appel sortant de RTPC | Vérifiez que vous pouvez placer un appel vocal externe à un numéro à 10 chiffres. |<ul><li>Client d’équipes installé.</li><li>Utilisateur activé avec les licences Office 365 suivantes affectées :<ul><li>E5 d’entreprise Office avec un système téléphonique, les équipes de Microsoft et les Plans d’appel nationaux et internationaux</li><li>E3 d’entreprise Office avec un système téléphonique, les équipes de Microsoft et les Plans d’appel nationaux et internationaux</li></ul></li></ul> | <ol><li>Connectez-vous au client d’équipes.</li><li>Sélectionnez le pavé de numérotation, puis entrez un numéro à 10 chiffres à composer.</li><li>Vérifiez que la connexion numérique est normalisée correctement et que l’appel RTC externe est établie.</li></ol>    | Système de téléphone avec le testeur de Plans d’appel |


> [!TIP]
>   Pour obtenir des conseils supplémentaires en facilitant des cas de test et de création de plan global d’évaluation de système téléphonique avec les Plans d’appel de fonctionnalités dans votre organisation, passez en revue le [Plan de Test du système téléphonique](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_21) fourni par [MyAdvisor](https://myadvisor.fasttrack.microsoft.com/).


<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/>Points de décision</td><td><ul><li>Choisir quel système de téléphone avec les Plans d’appel de l’administration et fonctionnalités de l’utilisateur seront évaluées.</li><li>Décidez quel environnement de test est requis pour prendre en charge de l’exécution du cas de test.</li><li>Déterminer les étapes requises pour l’évaluation des cas de test.</li><li>Déterminer les ressources nécessaires à la bonne exécution de l’essai.</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Étapes suivantes</td><td><ul><li>Documenter les cas de test à évaluer, basé sur le modèle de cas de test fourni.</li><li>Inclure le modèle terminé dans le cadre de votre plan de test global.</li></ul></td></tr>
</table>


### <a name="define-and-document-testing-resources"></a>Définissez et documentez les ressources de test

Pour prendre en charge de la phase de test, il est important de développer un plan de ressources détaillant les ressources humains, technologiques et de support dont vous aurez besoin. Un élément important du plan de test global, la ressource plan vous aide à que déterminer les dépendances qui peuvent exister et vous donne une idée générale de la ressource en charge, vous devrez peut-être.

À un niveau élevé, ces ressources sont généralement constituées de :

-   **Personnes**: les parties prenantes

-   **Technologie**: clients, le Gestionnaire de licences, périphériques

-   **Prise en charge**: formation (cartes vidéos), prise en charge de l’administration avec chemin d’escalade définie

#### <a name="testing-resource-requirements"></a>Besoins en ressources de test

> [!TIP]
>   Voici un exemple de test modèle de demande de ressources que vous pouvez utiliser pour documenter les différents types de ressources nécessaires à la prise en charge de votre phase de test.


| Type de ressource | Ressources requises                                           | Description de la ressource |
|---------------|--------------------------------------------------------------|----------------------|
| Personnes        | Les parties prenantes tester les testeurs de prospect                               | À DÉFINIR                  |
| Technologie    | Accéder à Office 365 avec les services suivants est activé :<ul><li>Office 365 E5 de licence attribuée</li><li>Plan d’appel national et International affecté</li></ul>    | À DÉFINIR                  |
| support       | Tester le responsable de la prise en charge de Test administrateur technicien de Test | À DÉFINIR                  |

<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/>Points de décision</td><td><ul><li>Choisir les types de ressources (personnes, la technologie et la prise en charge) que vous aurez besoin pour prendre en charge de la phase de test.</li><li>Choisir les ressources spécifiques requis pour les types de ressources que vous avez identifié.</li><li>Décider si vous devez fournir davantage de détails pour décrire les types de ressources dont vous avez besoin.</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Étapes suivantes</td><td><ul><li>Les types de ressources (personnes, la technologie et la prise en charge) que vous aurez besoin pour prendre en charge de la phase de test du document.</li><li>Documenter les ressources spécifiques requis pour les types de ressources que vous avez identifié.</li><li>Si vous décidez qu’il est nécessaire, des détails supplémentaires sur les types de ressources que nécessaires à la prise en charge de la phase de test du document.</li></ul></td></tr>
</table>


### <a name="define-and-document-a-testing-timeline"></a>Définissez et documentez un scénario de test

Dans le cadre de la définition de plan de test, créez une chronologie qui décrit la planification lorsque vous prévoyez d’effectuer des activités de test et d’atteindre les jalons de haut niveau.

À un niveau élevé, ceci en général comprend :

-   **Tâche :** Activité de haut niveau à effectuer

-   **Étape :** Objectif de haut niveau, ou une progression qui s’est terminée

-   **Ressource requise :** Test des ressources requises pour prendre en charge la livraison du jalon ou tâche identifiée

-   **La date de début :** La date de sur que l’activité, un jalon ou une tâche a été initiée

-   **Date d’achèvement :** La date à par que laquelle l’activité, un jalon ou une tâche se termine

-   **Propriétaire :** Ressource qui est chargé de s’assurer que l’activité, un jalon ou une tâche est terminée dans les délais, conformément à la date d’achèvement

-   **Estimation :** Nombre d’heures que les ressources affectées anticiper qu’il prend pour s’assurer que l’activité, un jalon ou une tâche est terminée à temps

#### <a name="testing-scheduling-and-timeline-requirements"></a>Besoins de test de la planification et de la chronologie

> [!TIP]
>   Voici un exemple d’un modèle de demande de chronologie test que vous pouvez utiliser pour documenter les dates prévues pour lors de la réalisation des activités de test spécifiques ou jalons fournis par.

| Tâche                                                 | Jalon       | Date de début                                                             | Date d’achèvement | Propriétaire | Ressources affectées | Estimation |
|------------------------------------------------------|-----------------|------------------------------------------------------------------------|-----------------|-------|--------------------|------------|
| Rapport de test                                          | À DÉFINIR             | À DÉFINIR                                                                    | À DÉFINIR             | À DÉFINIR   | À DÉFINIR                | Heures à déterminer  |
| L’exécution du cas de test : Système de téléphone avec des Plans d’appel | À DÉFINIR             | À DÉFINIR                                                                    | À DÉFINIR             | À DÉFINIR   | À DÉFINIR                | Heures à déterminer  |
| D’exécution de cas de test : Préparation de son réseau               | À DÉFINIR             | À DÉFINIR                                                                    | À DÉFINIR             | À DÉFINIR   | À DÉFINIR                | Heures à déterminer  |


<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/>Points de décision</td><td><ul><li>Décider d’activité de la barre de planning, de jalon et les tâches dont vous avez besoin pour assurer le suivi.</li><li>Déterminer les ressources que vous devez assigner.</li><li>Décider de la date prévue pour le faire.</li><li>Identifier le propriétaire de la livraison.</li><li>Décider combien de temps il faudra pour terminer l’activité, un jalon ou une tâche.</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Étapes suivantes</td><td><ul><li>Votre barre de planning de test du document en utilisant le modèle fourni et comprennent :<ul><li>Activité de la barre de planning, de jalon et les tâches qui doivent être suivis.</li><li>Ressources qui doivent être attribués.</li><li>Date de fin prévue.</li><li>Propriétaire de la livraison.</li><li>Temps nécessaire pour terminer l’activité, un jalon ou une tâche.</li></ul></li><li>Inclure le modèle terminé dans le cadre de votre plan de test global.</li></ul></td></tr>
</table>


### <a name="define-and-document-test-defect-report-criteria"></a>Définissez et documentez les critères de rapport de défaut de test

Comme les cas de test dans un flux ou une phase donnée sont exécutées, les problèmes peuvent survenir lorsque le résultat du cas de test en cours d’exécution n’est pas celui que vous attendiez.

Lorsque ces types de résultats se produisent, ils doivent être consignés dans un plan de rapport et de correction de défaut qui est affecté au prospect pour révision, le reporting et la résolution de l’erreur de test désigné.

En général, un plan d’état et de correction de défaut inclut les éléments suivants :

-   **Défaut ID :** Le numéro attribué à la demande

-   **ID de cas de test impacté**: le numéro affecté au cas de test qui a été évalué au moment où le problème a été identifié.

-   **Défaut description :** Résumé du problème

-   **Environnement/étapes à reproduire :** Résumé de la configuration de l’environnement test, ainsi que les étapes exactes à suivre pour reproduire le problème

-   **Gravité de l’erreur**: l’impact du problème, allant d’empêche que le cas de test en cours d’approbation à son acceptation en limitant les risques. Voici quelques exemples possibles :

-   **Faible :** Le problème a peu d’impact et empêche le cas de test à partir de la réalisation d’acceptation si le problème peut être résolu ultérieurement.

-   **Support :** Le problème a eu un impact important, mais il empêche le cas de test à partir de la réalisation d’acceptation si le problème peut être résolu avant la fin de la phase de test.

-   **Haute :** -le problème a un impact majeur sur le cas de test. Le problème doit être résolu avant le cas de test peuvent être accepté.

-   **État :** A le problème résolu, il est ouvert, ou encore à l’étude

-   **Envoyé par :** Le testeur qui a signalé le problème

-   **Affecté propriétaire :** La ressource affectée à partir de l’équipe de test qui est responsable de la résolution du problème

-   **Plus de détails :** Cela peut inclure, mais n’est pas limitée à, journaux de côté client, des captures d’écran ou vidéo du problème.

Que les testeurs s’exécuter les cas de test décrites dans votre plan de test, ils doivent être sûr terminer un plan de rapport et de correction de défaut pour tous les problèmes qui surviennent.
Cela met en évidence un impact potentiel qui pourrait entraver ou même interrompre le processus de test d’évaluation.

#### <a name="testing-defect-report-and-remediation-plan"></a>Plan de mise à jour et rapport de test

> [!TIP]
>   Voici un exemple de modèle de rapport et de la planification de la mise à jour que vous pouvez utiliser pour documenter les problèmes décelées au cours de la phase de test.

| ID de l’erreur                                | ID de cas de test impacté | Description de l’erreur                                                                                 | /Steps d’environnement à reproduire                                                                                                | Gravité | État | Soumis par | Propriétaire affecté | Prise en charge de détails (journaux, captures d’écran, etc.) |
|------------------------------------------|-----------------------|----------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------|----------|--------|--------------|----------------|---------------------------------------------------|
| 1                                        | 1                     | Lorsque l’utilisateur entre une extension de quatre chiffres, essayez de placer un appel sortant, l’appel est échoue. | Dans le client d’équipes, sélectionnez le pavé de numérotation, entrez une extension de quatre chiffres et sélectionnez l’icône de téléphone pour tenter d’effectuer l’appel. | Moyen   | Fermé | Louis Lahr   | Lisa gris      | Journal des équipes côté client<br/> Capture d’écran du client aux équipes     |


<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/>Points de décision</td><td><ul><li>Déterminer les niveaux de gravité des critères défaut vous allez attribuer au support technique de l’effort de test.</li><li>Décider quel défaut test reporting des critères, que vous devez documenter si des problèmes surgissent lors du test.</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Étapes suivantes</td><td><ul><li>Documenter la défaillance de test reporting critères requis dans le modèle fourni.</li><li>Inclure le modèle terminé dans le cadre de votre plan de test global.</li></ul></td></tr>
</table>


### <a name="define-and-document-exit-and-suspension-criteria"></a>Définissez et documentez les critères de sortie et de suspension

Dans le cadre du processus de l’exécution du plan test global, vous devez définir des critères pour indiquer le point auquel vous devez suspendre les efforts de test par rapport à des exigences qui doivent être remplies pour l’obtention de déconnexion et la fermeture de la phase de test.

#### <a name="test-plan-exit-and-suspension-criteria"></a>Critères de sortie et suspension de plan de test

> [!TIP]
>   Ci-dessous un exemple de modèle de critères de suspension et de la sortie que vous pouvez utiliser dans votre plan de test pour les critères de document doit parvenir à l’acceptation, quitter la phase de test ou de suspension des activités de tests.

| Critères de sortie test                            | Critères de suspension des tests                      |
|--------------------------------------------------|--------------------------------------------------|
|<ul><li>Tous les cas de test doivent permettre d’atteindre un taux de réussite de TBD %</li><li>Tous les cas de test doit avoir été complètement exécutés</li><li>Dans tous les cas de test évalués, toutes les erreurs de gravité élevée doivent être fermés.</li></ul> | <ul><li>Tous les cas de test doivent permettre d’atteindre un taux de défaillance TBD %</li><li>Tous les défauts identifiés comme critiques doivent être résolus avant que le test puisse continuer.</li></ul> |


<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/>Points de décision</td><td><ul><li>Choisissez les critères de suspension qui doivent être remplies si les problèmes liés aux tests sont identifiées.</li><li>Choisissez les critères de sortie qui doivent être remplies pour obtenir test approbation et la prise en charge de la sortie de la phase de test après tout test activités sont terminées.</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Étapes suivantes</td><td><ul><li>Documenter les critères de sortie et suspension tests requis dans les modèles de tests et la sortie fournies.</li></ul></td></tr>
</table>


### <a name="define-and-document-the-defect-escalation-process"></a>Définissez et documentez le processus d’escalade de défauts

Tout au long de l’exécution de plan de test, vous pouvez découvrir un problème ou d’identifier le problème qui nécessite la mise à niveau vers la ressource adéquate pour la conduite et la détermination de la résolution requise pour permettre le test continuer.

Comme les défauts sont identifiés par la gravité appropriée et la priorité attribuée, vous créez une matrice d’escalade et de triage révision pour le mappage des lorsqu’une escalade est déclenchée et comment, quand et qui sera affectée à la défaillance d’autres révision et résolution.

En général, un plan d’état et de correction de défaut inclut les éléments suivants :

-   **Défaut ID :** Le numéro attribué au problème

-   **Défaut description :** Résumé du problème

-   **Défaut évaluation de priorité :** Le niveau de priorité attribué à un défaut de résolution basée sur impact métier et du défaut de gravité. Certains exemples, citons :

-   **Faible :** Le problème a peu d’impact sur la prévention de la phase de test à partir de la réalisation de déconnexion si le problème peut être résolu ultérieurement.

-   **Support :** Le problème a eu un impact important sur la prévention de la phase de test à partir de la réalisation de déconnexion si le problème ne peut pas être résolu.

-   **Haute :** Le problème a un impact majeur sur la prévention de la phase de test à partir de la réalisation de déconnexion si le problème ne peut pas être résolu.

-   **Propriétaire de défaut attribué :** La ressource affectée à partir de l’équipe de test qui est responsable de la résolution du problème

-   **Affecté de défaut de point de promotion :** La ressource affectée qui est sur le point d’escalade du problème de l’organisation (si nécessaire) pour la conduite de résolution ; en fonction de la gravité de l’erreur

-   **Défaut Statut :** A le problème résolu, il est ouvert, ou encore à l’étude

-   **Requis de résolution par date :** La date à laquelle le problème doit être résolu par

-   **Date d’état :** La date qui reflète l’état de la dernière heure a été mis à jour comme résultat d’une révision de triage de défauts

#### <a name="test-plan-defect-escalation"></a>Escalade de défaut de plan de test

> [!TIP]
>   Voici un exemple d’un modèle d’escalade défaut que vous pouvez utiliser dans la partie de votre plan de test afin de documenter le processus d’escalade requis pour la définition des priorités et la résolution des erreurs de tests.

| ID de l’erreur                                | Description de l’erreur                                                                                 | Évaluation de priorité de défauts                                           | Propriétaire de défaut affectées | Point d’escalade défaut affectées | Procédé de transmission de défauts                                          | Statut de l’erreur | Résolution requise par date | Date d’état |
|------------------------------------------|----------------------------------------------------------------------------------------------------|----------------------------------------------------------------------|-----------------------|----------------------------------|-------------------------------------------------------------------|---------------|-----------------------------|-------------|
| 1                                        | Lorsque l’utilisateur entre une extension de quatre chiffres, essayez de placer un appel sortant, l’appel est échoue. | Moyen                                                               | Lisa gris             | Louis Lahr                       | E-mail de haute priorité Triage révision hebdomadaire pour les parties prenantes concernées | Ouvrir          | ASAP                        | 1/12/2018   |



<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/>Points de décision</td><td><ul><li>Décider et s’accordent sur les priorités de défaut pour prendre en charge de votre plan de test.</li><li>Déterminer le point d’escalade pour chaque zone de défaillance.</li><li>Décider l’escalade de défaut plan de versionnement et de suivre, en fonction de la priorité.</li><li>Choisir le rapport de défaut et plan de communication pour escalade de triage.</li><li>Décidez de la cadence de réunion de triage de défauts.</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Étapes suivantes</td><td><ul><li>Documenter les priorités convenues d’un défaut.</li><li>Le point d’escalade pour chaque centre d’intérêt potentiel du document.</li><li>Documenter le plan de remontée des problèmes et de triage défaut en fonction de critères de convenues.</li><li>Documentez votre défaillance directives de création de rapports.</li><li>Planifier la série de réunions de triage de défauts.</li></ul></td></tr>
</table>


### <a name="define-and-document-testing-deliverables"></a>Définissez et documentez les résultats de test

Le composant de dernière lors de la création d’un plan de test est d’identifier les résultats en fonction des livrables spécifiques que le plan de test global.

À un niveau élevé, ils incluent généralement, mais ne sont pas limitées à :

-   Plan de test

-   Cas de test

-   Rapports d’erreur

-   Synthèse des résultats

-   Test d’acceptation et de validation

#### <a name="test-plan-deliverables"></a>Livrables de plan de test

> [!TIP]
>   Vous trouverez ci-dessous un exemple d’un plan du livrable de matrice de test que vous pouvez utiliser pour documenter les livrables à créer, ainsi que les ressources requises pour la révision, l’approbation et validation.

| Plan de test du livrable                    | Format de livrable de plan de test | Propriétaire du livrable du plan de test                                                                                                      | Réviseur du livrable de plan de test | Approbateur du livrable de plan de test | Plan du livrable approbation date de test |
|------------------------------------------|------------------------------|----------------------------------------------------------------------------------------------------------------------------------|--------------------------------|--------------------------------|-------------------------------------|
| Plan de test                                | Word                         | À DÉFINIR                                                                                                                              | À DÉFINIR                            | À DÉFINIR                            | À DÉFINIR                                 |
| Rapports de gestion des défauts                | Word                         | À DÉFINIR                                                                                                                              | À DÉFINIR                            | À DÉFINIR                            | À DÉFINIR                                 |
| Test des rapports d’état                   | Word                         | À DÉFINIR                                                                                                                              | À DÉFINIR                            | À DÉFINIR                            | À DÉFINIR                                 |
| Synthèse des résultats                     | Word PPTX                    | À DÉFINIR                                                                                                                              | À DÉFINIR                            | À DÉFINIR                            | À DÉFINIR                                 |


<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/>Points de décision</td><td><ul><li>Décidez quels produits livrables doivent être créés et capturés en tant que sortie de chaque phase de test. Pour chaque livrable, décider de son :<ul><li>Format</li><li>Propriétaire</li><li>Réviseur</li><li>Approbateur</li></ul></li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Étapes suivantes</td><td><ul><li>Documenter un plan livrable création et la diffusion de matrice de test.</li></ul></td></tr>
</table>


<a name="evaluate-network-readiness"></a>Évaluer la préparation de son réseau
----------------------------

Comme un élément critique de prise en charge de votre déploiement d’équipes, préparation de son réseau est une partie essentielle du test pour garantir que le réseau est correctement optimisé pour prendre en charge les communications d’équipes. Pour vous assurer que votre réseau est prêt pour les sites dans la portée, inclure les domaines répertoriés ci-dessous dans votre stratégie globale de test :

-   Estimation de la bande passante et de la planification avec le Gestionnaire de réseau (via MyAdvisor)

-   Qualité de la validation de la configuration service (QoS)

-   Vérification de connectivité et de performances par le biais de simulation de trafic de réseau

-   Validation de tunneling fractionné

### <a name="execute-network-planner-through-myadvisor-for-sites-and-personas-in-scope"></a>Exécuter le Gestionnaire de réseau (via MyAdvisor) pour les sites et les personnages dans la portée

Avant d’introduire des services de communication en temps réel tels que des équipes dans votre environnement, il est important de s’assurer que le réseau a été correctement optimisé et de taille à partir d’un ExpressRoute d’Azure (si applicable), d’internet et point de vue de la bande passante WAN.

Pour aider à déterminer la quantité de bande passante et le niveau d’optimisation de réseau requis pour les sites dans la portée de votre déploiement de prise en charge, exécutez l’outil [Planificateur de réseau](https://myadvisor.fasttrack.microsoft.com/CloudVoice/NetworkPlanner/Help?sectionName=DashboardHelp) (via MyAdvisor) pour valider les besoins de disponibilité du réseau de votre organisation. Pour plus d’informations sur la façon de déterminer la configuration réseau requise pour les équipes par le Gestionnaire de réseau, reportez-vous à la section MyAdvisor : module de réseau.

> [!TIP]
>   Pour plus d’informations sur l’onglet de **recommandations** , avec des exemples de la façon de configurer et d’interpréter les résultats, consultez le Gestionnaire de réseau [Vue d’ensemble des recommandations](https://myadvisor.fasttrack.microsoft.com/CloudVoice/NetworkPlanner/Help?sectionName=RecommendationHelp).



<table>
<tr><td>![](media/audio_conferencing_image7.png)<br/>Points de décision</td><td><ul><li>Décidez quels sites réseau sont dans la portée pour le déploiement des équipes de services.</li><li>Choisir les personnages requis pour les modalités d’équipes dans la portée.</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Étapes suivantes</td><td><ul><li>Renseignez le Gestionnaire de réseau (via MyAdvisor) pour obtenir la liste des sites qui sont dans la portée.</li><li>Résultats de la validation de réseau Planificateur de document dans le modèle de résultats de plan de test fourni.</li><li>Valider que le ExpressRoute (si applicable), d’internet et la bande passante WAN qui a été calculée pour les sites dans la portée aligne les valeurs de bande passante qui sont actuellement alloués.</li><li>Pour les sites qui n’ont pas une bande passante suffisante, exécuter des plans de remontée des problèmes et la mise à jour pour résoudre les problèmes de bande passante.</li><li>Établir un réseau de surveillance de la solution de sites dans la portée pour surveiller l’utilisation de la bande passante et la qualité de service pour ExpressRoute (le cas échéant), internet et les segments de réseau étendu.</li><li>Planifier une réunion du comité de direction d’examiner les résultats du Gestionnaire de réseau.</li><li>Présenter les résultats au comité de direction pour identifier les zones qui nécessitent une conversion de planification de la bande passante.</li></ul></td></tr>
</table>


<a name="evaluate-qos-configuration-for-sites-in-scope"></a>Évaluer configuration de QoS pour les sites dans la portée
---------------------------------------------

Dans le cadre de la préparation de son réseau de communications en temps réel des équipes de prise en charge de la validation, il est tout aussi important de vous assurer que le réseau a été correctement configuré et optimisé du point de vue de la qualité de service.

Pour plus d’informations sur la façon de configurer, de déployer et de valider la préparation de son réseau QoS pour les équipes à l’aide de stratégie de groupe, reportez-vous à la section [Activation de QoS pour les équipes](https://docs.microsoft.com/MicrosoftTeams/qos-in-teams).


<table>
<tr><td>![](media/audio_conferencing_image7.png)<br/>Points de décision</td><td><ul><li>Déterminer la configuration de la qualité de service à mettre en oeuvre.</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Étapes suivantes</td><td><ul><li>Configurer la QoS.</li><li>Exécuter le contrôle de la qualité de service indiqué dans les étapes indiquées par l’intermédiaire du « valider via l’objet stratégie de groupe » et « valider via l’Analyseur de Message » ci-dessus.</li></ul></td></tr>
</table>


### <a name="document-qos-configuration-validation-test-results"></a>Documenter les résultats des tests de validation configuration QoS

Une fois que vous avez terminé le test à l’aide de la stratégie de groupe pour les sites dans la portée de validation de qualité de service, créer un rapport qui résume les résultats des tests à présenter au cours de l’examen du comité de direction finale.

#### <a name="site-a-qos-configuration-validation-testing-summary-report"></a>Site a : validation de la configuration QoS rapport de test

> [!TIP]
>   Voici un exemple de modèle de rapport de synthèse que vous pouvez consulter lors de la prochaine réunion du comité de direction lorsque vous choisissez lorsque pour système de téléphone intégré avec les Plans d’appel de services lors de la phase pilote de test.


**Validation de la configuration QoS via l’objet stratégie de groupe et l’Analyseur de Message**

**Résumé des résultats**:&nbsp;&nbsp;&nbsp;& #, 9744 ; Passer&nbsp; &nbsp; &nbsp; & #, 9744 ; Partielle&nbsp; &nbsp; &nbsp; & #, 9744 ; Échec

<table>
<tr><th colspan="2">Test des tons clairs </th></tr>
<tr><td>À DÉFINIR</td><td>À DÉFINIR</td></tr>
<tr><th colspan="2">Test des enseignements  </th></tr>  
<tr><td>**Problème**: TBD</td><td>**Mise à jour :** À DÉFINIR</td></tr>
<tr><th colspan="2">BLOQUEURS identifiés </td></tr>
<tr><td>**Bloqueur de fenêtres publicitaires**: TBD</td><td>**Mise à jour**: TBD</td></tr>
</table>


> [!TIP]
> Pour faciliter la discussion supplémentaire au cours de l’examen du comité de direction finale, vous pouvez utiliser la mise à jour [matrice des résultats de tests](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_21) à partir de [MyAdvisor](https://myadvisor.fasttrack.microsoft.com/) de documenter et de mettre en évidence les zones supplémentaires qui nécessitent une conversion.



<table>
<tr><td>![](media/audio_conferencing_image7.png)<br/>Points de décision</td><td><ul><li>Évaluer les résultats de test de QoS pour s’assurer que les équipes au trafic multimédia en temps réel sont correctement marqués et classés par priorité.</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Étapes suivantes</td><td><ul><li>Résultats du test de QoS de document dans le modèle de résultat de plan de test fourni.</li><li>Exécuter des plans d’escalade et de correction pour résoudre les problèmes où QoS n’est peut-être pas configuré correctement ou n’est pas travaille comme prévu pour prendre en charge le trafic de support d’équipes.</li></ul></td></tr><li>Planifier une réunion du comité de direction d’examiner les résultats de synthèse de test.</li><li>Résultats du résumé test présente au comité de direction pour identifier les zones qui nécessitent une conversion.</li>
</table>


<a name="execute-split-tunnel-enablement-validation"></a>Exécuter le contrôle de fractionnement-tunnel activation
------------------------------------------

Il est courant pour les entreprises aujourd'hui ont une ou plusieurs solutions pour fournir l’accès à distance, par exemple un réseau privé virtuel, ou VPN. Ces solutions permettent la connectivité internes métier des ressources et des applications en toute sécurité et fiabilité.

Bien que les solutions d’accès distant peuvent fonctionnent très bien pour donner accès à certaines applications, lorsqu’il s’agit de tunneling du trafic multimédia en temps réel d’équipes, ces solutions débouchent le plus souvent dans une expérience utilisateur moins qu’optimal pour tous les participants dans un audio d’équipes scénario d’appel ou de conférence.

Pour vous assurer que le trafic multimédia d’équipes ne *pas* traverser les solutions d’accès distant dans votre environnement, une configuration en tunnel-split sera nécessaire.

Pour plus d’informations sur la façon de configurer et valider la préparation de son réseau configuration de tunnel-split pour les équipes, reportez-vous à la section Préparation de son [réseau](https://docs.microsoft.com/MicrosoftTeams/prepare-network) .

> [!NOTE]
>   En raison du volume élevé des solutions d’accès à distance disponibles sur le marché, ce document ne peut pas fournir les informations spécifiques au fournisseur, simplement général de ce qui doit être configuré sur les solutions d’accès distant.


<table>
<tr><td>![](media/audio_conferencing_image7.png)<br/>Points de décision</td><td><ul><li>Décider de la configuration de tunnel-split pour mettre en œuvre.</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Étapes suivantes</td><td><ul><li>Mettre en œuvre la configuration de tunnel de la division.</li><li>Tester et valider la configuration de tunnel de la division.</li></ul></td></tr>
</table>


### <a name="document-split-tunnel-configuration-validation-test-results"></a>Résultats des tests de validation document configuration de tunnel de la division

Après avoir terminé les test configuration split-tunnel pour les sites dans la portée, créer un rapport qui résume les résultats des tests et les présenter au cours de l’examen du comité de direction suivant.

#### <a name="site-a-split-tunnel-configuration-validation-testing-summary-report"></a>Site a : validation de la configuration Split-tunnel rapport de test

> [!TIP]
>   Voici un exemple de modèle de rapport de synthèse que vous pouvez consulter lors de la prochaine réunion du comité de direction lorsque vous choisissez lorsque pour système de téléphone intégré avec les Plans d’appel de services lors de la phase pilote de test.

**Validation de la configuration de tunnel de la division**

**Résumé des résultats**:&nbsp;&nbsp;&nbsp;& #, 9744 ; Passer&nbsp; &nbsp; &nbsp; & #, 9744 ; Partielle&nbsp; &nbsp; &nbsp; & #, 9744 ; Échec

<table>
<tr><th colspan="2">Test des tons clairs </th></tr>
<tr><td>À DÉFINIR</td><td>À DÉFINIR</td></tr>
<tr><th colspan="2">Test des enseignements  </th></tr>  
<tr><td>**Problème**: TBD</td><td>**Mise à jour :** À DÉFINIR</td></tr>
<tr><th colspan="2">BLOQUEURS identifiés </td></tr>
<tr><td>**Bloqueur de fenêtres publicitaires**: TBD</td><td>**Mise à jour**: TBD</td></tr>
</table>


> [!TIP]
> Pour faciliter la discussion supplémentaire au cours de l’examen du comité de direction finale, vous pouvez utiliser la mise à jour [matrice des résultats de tests](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_21) à partir de [MyAdvisor](https://myadvisor.fasttrack.microsoft.com/) de documenter et de mettre en évidence les zones supplémentaires qui nécessitent une conversion.


<table>
<tr><td>![](media/audio_conferencing_image7.png)<br/>Points de décision</td><td><ul><li>Évaluer les résultats de tests de tunnel-split pour vous assurer que le trafic en temps réel d’équipes est exclu de la solution d’accès distant.</li></ol></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Étapes suivantes</td><td><ul><li>Documenter les résultats des tests de connectivité de tunnel-Fractionner dans le modèle de résultat de plan de test fourni.</li><li>Exécuter des plans d’escalade et de correction pour résoudre les problèmes où un routage correct n’existe ne peut-être pas de prise en charge de supports d’équipes au sein d’une configuration en tunnel-split.</li><li>Planifier une réunion du comité de direction d’examiner les résultats de synthèse de test.</li><li>Résultats du résumé test présente au comité de direction pour identifier les zones qui nécessitent une conversion.</li></ul></td></tr>
</table>


<a name="execute-network-connectivity-and-performance-validation-by-using-the-network-assessment-tool-from-microsoft"></a>Exécuter la validation de connectivité et les performances du réseau à l’aide de l’outil d’évaluation réseau de Microsoft
-----------------------------------------------------------------------------------------------------------

L’outil d’évaluation réseau de Microsoft effectue des tests de connectivité et de simulation du trafic en transférant des paquets audio simulés, pour une période prédéfinie et le nombre d’itérations, le site de bord le plus proche qui fournit la connectivité au service des équipes. Un des objectifs de ce test sont d’évaluer les mesures de performances de réseau pour la perte de paquets, gigue, latence du parcours circulaire et le pourcentage de réapprovisionnement de paquet de chaque appel simulée. En outre, le test vérifie qu’une connectivité adéquate est autorisée entre interne et contour des éléments de réseau à tous les points de pénétration de bord qui prennent en charge la connectivité aux services des équipes.

Pour obtenir des conseils supplémentaires sur la manière de confirmer et d’évaluer la préparation de son réseau équipes pour des sites désignés dans la portée, consultez Préparation de son [réseau](https://docs.microsoft.com/MicrosoftTeams/prepare-network) .

> [!TIP]
>   Pour terminer l’analyse de disponibilité du réseau et la disponibilité des sites dans la portée, désigner un responsable pour chaque site qui peut vous aider à vos efforts d’évaluation de disponibilité du réseau.



<table>
<tr><td>![](media/audio_conferencing_image7.png)<br/>Points de décision</td><td><ul><li>Décider de l’évaluation du réseau et le profil test de connectivité pour les sites dans la portée.</li><li>Décider d’évaluation configuration réseau fichier requise pour les sites dans la portée.</li></ol></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Étapes suivantes</td><td><ul><li>Configurer l’évaluation configuration réseau fichier requise pour les sites dans la portée.</li><li>Exécuter la validation de performances et de la connectivité réseau pour les sites dans la portée.</li></ul></td></tr>
</table>



### <a name="document-network-connectivity-and-performance-validation-test-results"></a>Documentation des résultats de test de validation connectivité et performances des réseau

Une fois que vous avez effectué toutes les connexion réseau et test de performance pour les sites dans la portée, créer un rapport qui résume les résultats des tests et les présenter au cours de l’examen du comité de direction suivant.

#### <a name="site-a-network-connectivity-and-performance-summary-report"></a>Site r : réseau connectivité et performances rapport Résumé

> [!TIP]
> Vous trouverez ci-dessous un exemple réseau connectivité et performances synthèse de modèle que vous pouvez utiliser lors de l’examen du comité de direction suivant lorsque vous êtes déterminer la préparation globale de son réseau de sites dans la portée.

**Emplacement : Seattle [wired intérieur] client à Office 365 résultats**

**Résumé des résultats**:&nbsp;&nbsp;&nbsp;& #, 9744 ; Passer&nbsp; &nbsp; &nbsp; & #, 9744 ; Partielle&nbsp; &nbsp; &nbsp; & #, 9744 ; Échec 



| Mesure                                                        | Cible                                                                                                            | Jour de la semaine : heures de bureau 09 h 30 à 11:00                                                                                                                                                                                                                                                                                                 | Jour de la semaine : heures de bureau 2 h 30 à 16 h 30 | Jour de la semaine : après les heures de 10 h 30 à 12:30 AM | Week-end : après les heures de 9 h 30 à 11:30 AM | Week-end : après les heures de 2 h 30 à 4:30 PM |
|---------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------|-------------------------------------------|------------------------------------------|-----------------------------------------
| Latence (unidirectionnel)                                             | \<50 ms                                                                                                           | 40 ms                                                                                                                                                                                                                                                                                                                                     | 38 ms                                    | ms 41                                     | ms 35                                    | 36 ms                                   |
| Latence (temps d’aller-retour ou RTT)                             | \<100 ms                                                                                                          | 81 ms                                                                                                                                                                                                                                                                                                                                     | ms 77                                    | 80 ms                                     | 72 ms                                    | ms 70                                   |
| Perte de paquets en mode rafale                                             | \<10 % au cours de n’importe quel intervalle de 200-ms                                                                                  | 3%                                                                                                                                                                                                                                                                                                                                        | 2 %                                       | 2 %                                        | 0,2 %                                     | 0,1 %                                    |
| Perte de paquets                                                   | \<1 % au cours de l’intervalle de 15-s                                                                                   | 0,4 %                                                                                                                                                                                                                                                                                                                                      | 0,3 %                                     | 0,3 %                                      | 0,1 %                                     | 0 %                                      |
| Variation de paquet arrivée entre                                   | \<30 ms pendant un intervalle de 15-s                                                                                | 12 ms                                                                                                                                                                                                                                                                                                                                     | 11 ms                                    | 13 ms                                     | 5 ms                                     | 5 ms                                    |
| Réorganisation des paquets                                                | \<paquets à la sortie de commande 0,05 %                                                                                      | 0 %                                                                                                                                                                                                                                                                                                                                        | 0 %                                       | 0 %                                        | 0 %                                       | 0 %                                      |



<table>
<tr><th colspan="2">Test des tons clairs </th></tr>
<tr><td>À DÉFINIR</td><td>À DÉFINIR</td></tr>
<tr><th colspan="2">Test des enseignements  </th></tr> 
<tr><td>**Problème**: une latence élevée</td><td>**Mise à jour :** Examinez le routage des paquets et implémenter l’itinéraire idéal.</td></tr>
<tr><td>**Problème**: temps d’aller-retour n’est pas le double de la latence</td><td>**Mise à jour :** Recherchez un éventuel problème de configuration de pare-feu ou de routeur. Examinez les chemins de trafic.</td></tr>
<tr><td>**Problème**: pertes de paquets </td><td>**Mise à jour :** Dans le Gestionnaire de réseau, vérifiez que suffisamment de bande passante a été affecté. </td></tr>
<tr><td>**Problème**: instabilité élevée </td><td> **Mise à jour :** Vérifiez si les valeurs de point (DSCP) de code de services différenciés corrects sont utilisés. </td></tr>
<tr><td>**Problème**: pertes de paquets </td><td>**Mise à jour :** Examinez la perte de paquets. </td></tr>
<tr><td>**Problème**: réorganisation des paquets </td><td>**Mise à jour :** Examinez la bande passante et la file d’attente routeur. </td></tr>
<tr><th colspan="2">BLOQUEURS identifiés </td></tr>
<tr><td>**Bloqueur de fenêtres publicitaires**: TBD</td><td>**Mise à jour**: TBD</td></tr>
</table>

 


<table>
<tr><td>![](media/audio_conferencing_image7.png)<br/>Points de décision</td><td><ul><li>Évaluer évaluation du réseau et les résultats afin de que vous satisfaire aux exigences décrites dans les [performances de connectivité réseau et la qualité de Media](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance) pour les segments de clients et de segment de bord des tests de connectivité.</li><li>Avez-vous évalué les capacités de réseau pour la prise en charge multimédia en temps réel pour tous les sites dans la portée ?</li><li> Si votre réseau n’a pas été correctement évalué, ou si vous savez qu’il ne prend pas en charge multimédia en temps réel, vous désactivera la vidéo et des fonctionnalités de partage d’écran afin de réduire le réseau, impact et améliorent l’expérience des équipes pour les utilisateurs ?</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Étapes suivantes</td><td><ul><li>Documenter les performances du réseau et les résultats des tests de connectivité.</li><li>Exécuter des plans d’escalade et de correction pour résoudre les problèmes liés à des sites où il n’a pas suffisamment de bande passante ou les exigences de performances et de la connectivité réseau ne sont pas respectées.</li><li>Planifier une réunion du comité de direction d’examiner les résultats de synthèse de test.</li><li>Résultats du résumé test présente au comité de direction pour identifier les zones qui nécessitent une conversion.</li></ul></td></tr>
</table>


<a name="execute-subscriber-number-port-validation"></a>Exécuter le contrôle du port numéro abonné
-----------------------------------------

Si vous devez transférer des nombres en tant que partie de fournir des fonctionnalités appel entrant et sortant dans le système téléphonique avec les Plans d’appel de services pris en charge par les équipes, vous devez effectuer un port partiel pour un numéro de service. Cela vous permettra de valider les attentes, les exigences et chronologie raisonnable que vous avez terminé la préparation de votre déploiement de système téléphonique avec les Plans d’appel de services dans votre environnement de production.

Pour terminer un port partiel d’un numéro d’abonné à partir de votre fournisseur de services RTPC en cours aux équipes, passez en revue les étapes décrites ci-dessous.

#### <a name="step-1"></a>Étape 1

Identifier le nombre de tests que vous souhaitez port vers Office 365, comme un numéro d’utilisateur peut être assigné (numéro d’abonné) d’être traitées via le système téléphonique avec les Plans d’appel de service dans des équipes.

> [!IMPORTANT]
>Lorsque vous planifiez votre test numéro de portage, veillez à passer en revue les dernières indications pour les demandes de portage nombres de [Questions courantes de numéro de Port](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/transferring-phone-numbers-common-questions).

#### <a name="step-2"></a>Étape 2

Identifiez et documentez toutes les informations de compte (y compris le nom utilisé pour le compte spécifique) pour le transporteur actuel du nombre de test que vous allez être portage.
En règle générale, vous pouvez trouver les informations que vous avez besoin de la dernière facture ou la facture de votre fournisseur de service en cours.

> [!TIP]
>   Vous pouvez porter ou de transfert des numéros de téléphone dans tous pris en charge actuellement les pays/régions ; Toutefois, le moyen de vous envoyez une demande de commande de port peut être différent selon le pays/la région où les numéros de téléphone sont issus. Pour connaître la liste des pays/régions pris en charge, consultez le [pays et la disponibilité dans la région pour les conférences Audio et les Plans d’appel](https://docs.microsoft.com/SkypeForBusiness/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans).

>   Pour plus d’informations sur le transfert des numéros de téléphone au système téléphonique avec des Plans d’appel, ainsi que les éventuelles restrictions — consultez le [transfert vers Office 365, les numéros de téléphone](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365) et la [numérotation d’appel payant restrictions dans Office 365](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/toll-free-dialing-limitations-and-restrictions.).

#### <a name="step-3"></a>Étape 3

Téléchargez et créez une lettre d’autorisation (LOA) pour votre pays/région qui est basée sur « service numéro » comme type de portage numéro.

>[!NOTE]
>   Comme formats LOA peuvent différer par type de numéro, région ou pays (qui est géographique et non géographiques ou numéro d’utilisateur et le service ou le numéro d’appel gratuit), vérifiez que vous utilisez le modèle LOA approprié pour le type de votre scénario spécifique. Voir [télécharger une lettre d’autorisation (LOA)](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/download-a-letter-of-authorization-loa) pour plus d’informations sur le choix de la lettre d’accord, ou accéder directement à la [page de téléchargement](https://www.microsoft.com/download/details.aspx?id=49167).

>[!NOTE]
> **États-Unis uniquement**<br/>
>   Étant donné que nous sommes uniquement porter un numéro de service pour ce test, veillez à sélectionner les champs appropriés dans la lettre d’accord comme indiqué ci-dessous :

![Comment plusieurs numéros de téléphone vous transférez ? Réponse : je suis uniquement en transférant certaines de mes numéros d’à partir de mon opérateur actuel.] (media/onboarding-test-plan-image1.png "Comment plusieurs numéros de téléphone vous transférez ? Réponse : je suis uniquement en transférant certaines de mes numéros d’à partir de mon opérateur actuel.")

![Ce type de numéros de téléphone vous transférez ? Réponse : je suis transfert voice service numéro de téléphone pour les surveillances automatiques ou des ponts de conférence.] (media/onboarding-test-plan-image2.png "Ce type de numéros de téléphone vous transférez ? Réponse : je suis transfert voice service numéro de téléphone pour les surveillances automatiques ou des ponts de conférence.")

>[!IMPORTANT]
>   Lorsque vous transférerez manuellement les numéros de téléphone à l’aide d’une lettre d’accord, assurez-vous de que sélectionner le type de numéro de téléphone approprié. Vous devez soumettre des commandes port distinct pour chaque type de numéro de téléphone que vous souhaitez transférer.<br/><br/>
>   Étant donné que nous voulons tester le numéro de portage de processus à l’aide d’un numéro de téléphone associé au même numéro de téléphone facturation (BTN), vous devez vous assurer que le numéro de téléphone de facturation n’est *pas* inclus avec le numéro de téléphone spécifique portage.

#### <a name="step-4"></a>Étape 4

Dans le portail d’administration clients, accédez à l’onglet **prise en charge** et créer et soumettre une demande de service. Joignez le fichier LOA terminé pour planifier le numéro de téléphone associé à votre fournisseur de service en cours de migration. Pour choisir la méthode de demande de service plus appropriée pour la taille de votre client, reportez-vous à la section [soumettre manuellement une demande de service personnalisé](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/manually-submit-a-custom-service-request).

Après réception de la demande de prise en charge, Microsoft Support sera suivi basé sur la méthode de communication, vous avez choisi et vous faire part de l’état et les prochaines étapes de ce processus de portage de numéro.

#### <a name="step-5"></a>Étape 5

Une fois que le nombre est confirmé comme ayant été portées comme un nouveau numéro d’abonné dans Office 365, affecter le numéro au système téléphonique avec des Plans d’appel de service via le portail d’administration locataire \> **Skype pour le centre d’administration Business** \> ** Voix**. Sous l’onglet **Numéros de téléphone** , affecter le nouveau numéro de service dans le système téléphonique avec les Plans d’appel de service.

> [!TIP]
>   Bien que cette tâche affecte un nouveau numéro de service au système téléphonique avec des Plans d’appel, au moment de la rédaction de ce document, l’administration de cette tâche est effectuée à l’aide de la Skype pour le centre d’administration Business.

#### <a name="step-6"></a>Étape 6

Maintenant que vous avez attribué le numéro d’abonné porté, connectez-vous à un client d’équipes en tant que l’utilisateur et composer un numéro à 10 chiffres externe via le réseau RTPC. Après avoir placé l’appel, vérifiez que l’appel a été connecté et que l’ID d’appelant affiché correspond à vous porté le numéro d’abonné.

#### <a name="step-7"></a>Étape 7

À partir d’un numéro RTC externe, passer un appel vers le numéro d’abonné que vous porté à Office 365 et vérifiez que la réception d’appel entrant et connectés via le client des équipes.



<table>
<tr><td>![](media/audio_conferencing_image7.png)<br/>Points de décision</td><td><ul><li>Choisir les numéros nationaux d’abonné vous devrez port, par pays/région.</li><li>Choisir le modèle de lettre d’accord que vous allez utiliser.</li><li>Déterminer si votre opérateur actuel (perte de porteuse) autorise la fragmentation de numéro de téléphone (c'est-à-dire permet d’ordres de voies partielles).</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Étapes suivantes</td><td><ul><li>Collecter les informations requises et préparer la lettre d’accord.</li><li>Télécharger et exécuter les modèles LOA dont vous avez besoin.</li><li>Soumettre une demande de portage numérique d’abonné.</li><li>Exécuter une validation de test pour les numéros de ports en les affectant au système téléphonique avec des Plans d’appel de service d’accès à distance et vérifiez qu’elles fonctionnent, comme indiqué dans les étapes 6 et 7, plus haut dans cette section.</li></ul></td></tr>
</table>


### <a name="document-service-number-porting-test-results"></a>Numéro de service portage des résultats des tests de document

Une fois que vous avez terminé tous les tests de numéro d’abonné, créez un rapport qui résume les résultats des tests à présenter au cours de l’examen du comité de direction suivant.

#### <a name="site-a-number-porting-test-summary-report"></a>Numéro du site a : porter le rapport récapitulatif des tests

> [!TIP]
>   Voici un exemple de modèle de rapport Résumé du test que vous pouvez utiliser pour la révision au cours de la prochaine réunion du comité de direction lorsque vous choisissez lorsque pour système de téléphone intégré avec les Plans d’appel de services lors de la phase pilote.

**Portage du numéro de service**

**Résumé des résultats**:&nbsp;&nbsp;&nbsp;& #, 9744 ; Passer&nbsp; &nbsp; &nbsp; & #, 9744 ; Partielle&nbsp; &nbsp; &nbsp; & #, 9744 ; Échec 

<table>
<tr><th colspan="2">Test des tons clairs </th></tr>
<tr><td>À DÉFINIR</td><td>À DÉFINIR</td></tr>
<tr><th colspan="2">Test des enseignements  </th></tr>  
<tr><td>**Problème**: TBD</td><td>**Mise à jour :** À DÉFINIR</td></tr>
<tr><th colspan="2">BLOQUEURS identifiés </td></tr>
<tr><td>**Bloqueur de fenêtres publicitaires**: TBD</td><td>**Mise à jour**: TBD</td></tr>
</table>


> [!TIP]
>   Pour faciliter la discussion supplémentaire au cours de l’examen du comité de direction finale, vous pouvez utiliser la mise à jour [la matrice de résultats des tests](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_21) fournis par [MyAdvisor](https://myadvisor.fasttrack.microsoft.com/) de documenter et de mettre en surbrillance des zones de test supplémentaires qui nécessitent une conversion.


<table>
<tr><td>![](media/audio_conferencing_image7.png)<br/>Points de décision</td><td><ul><li>Évaluer si les numéros d’abonnés soumis pour la migration ont été portées avec succès au système téléphonique avec des Plans d’appel de service...</li><li>Déterminez si vous avez pu affecter le nombre de ports de service pour le système téléphonique avec les Plans d’appel de service.</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Étapes suivantes</td><td><ul><li>Le portage des résultats des tests de numéro de document.</li><li>Exécuter des plans d’escalade et de correction pour résoudre les problèmes que vous avez rencontré avec le processus de portage numéro, le cas échéant.</li><li>Planifier une réunion du comité de direction d’examiner les résultats de synthèse de test.</li><li>Présenter les résultats de synthèse au comité de direction pour identifier les zones qui nécessitent une conversion.</li></ul></td></tr>
</table>


<a name="execute-your-test-plan-for-phone-system-with-calling-plans"></a>Exécuter votre plan de test pour le système téléphonique avec des Plans d’appel
----------------------------------------------------------

Maintenant que vous avez défini votre plan de test, l’étape suivante consiste à les guider dans les cas de test, en mettant l’accent sur l’évaluation du système téléphonique avec appel de Plans d’administration et utilisateur bénéficier des fonctionnalités dans la portée. Avant de commencer effectivement les tests, vérifiez que les tests requis répertoriés ci-dessous sont en place.

### <a name="phone-system-with-calling-plans-testing-prerequisites"></a>Système de téléphone avec l’appel de Plans de test des conditions requises

-   Exemples d’utilisation ont été définis pour le système de téléphone avec les Plans d’appel de service.

-   Les principales parties prenantes ont été identifiés.

-   La licence requise pour le système téléphonique avec les Plans d’appel de services est disponible et a été affectée au groupe d’utilisateurs dans la portée.

-   La liste des sites d’organisation et les groupes d’utilisateurs dans la portée ont été identifiés.

-   [Crédits de communications](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits) (si nécessaire) ont été configurés pour votre organisation.

-   Système de téléphone avec les paramètres de l’appel de Plans ont été identifiés et configuré.

-   Paramètres qui prennent en charge le système téléphonique avec des Plans d’appel ont été identifiés, configurés et appliquées pour le groupe d’utilisateurs dans la portée de plan de numérotation de clients.

-   Système de téléphone avec les Plans d’appel de stratégies ont été identifiés et configurée pour le groupe d’utilisateurs dans la portée.

-   Système de téléphone avec les Plans d’appel de respect de la réglementation ont été identifiés et configurée pour le groupe d’utilisateurs dans la portée.

### <a name="document-phone-system-with-calling-plans-test-case-passfail-status"></a>Système de téléphone de document avec les Plans d’appel d’un état de réussite ou d’échec de cas de test

En cas de test sont évalués pour les équipes d’administration et les fonctionnalités de système de téléphone utilisateur dans la portée, suivre les résultats de chaque cas de test afin de refléter l’état de réussite ou d’échec/partielle, ainsi que l’ID affecté du défaut en cas de problèmes imprévus se posent.

#### <a name="phone-system-with-calling-plans-test-case-status"></a>Système de téléphone avec les Plans d’appel de statut de cas de test

> [!TIP]
>   Voici un exemple de modèle de statut des cas de test que vous pouvez utiliser pour documenter les résultats de test de révision au cours de la prochaine réunion du comité de direction lorsque vous choisissez lorsque pour système de téléphone intégré avec les Plans d’appel de services lors de la phase pilote.

| Système téléphonique avec forfaits d’appels          |                              |                                                                                            |                           |                                                                            |
|------------------------------------------|------------------------------|--------------------------------------------------------------------------------------------|---------------------------|----------------------------------------------------------------------------|
| ID de cas de test                             | Titre du cas de test              | Description du cas de test                                                                      | Résumé des résultats de cas de test | ID d’erreur affectées (le cas échéant)                                         |
| 1                                        | Appel sortant RTPC. | Placez un appel sortant en composant un numéro à 10 chiffres nationaux.                              |    & #, 9744 ; Passer<br/>& #, 9744 ; Partielle<br/> & #, 9744 ; Échec                   | Lorsqu’un utilisateur entre un nombre à quatre chiffres, l’appel placé au RTC échoue. |



<table>
<tr><td>![](media/audio_conferencing_image7.png)<br/>Points de décision</td><td><ul><li>Évaluer l’état de réussite ou d’échec de haut niveau de cas de test par site pour système de téléphone avec les Plans d’appel de fonctions dans la portée.</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Étapes suivantes</td><td><ul><li>Les résultats d’état de cas de test pour tous les cas de test terminées dans la portée du document.</li><li>Planifier une réunion du comité de direction d’examiner les résultats de synthèse de test.</li><li>Présenter les résultats d’état de cas de test au comité de direction pour identifier les zones qui nécessitent une conversion.</li></ul></td></tr>
</table>


### <a name="document-phone-system-with-calling-plans-testing-result-summary"></a>Système de téléphone de document avec l’appel de Plans de résumé des résultats de tests

Une fois tous les tests système téléphonique de la prise en charge avec les Plans d’appel de fonctions dans la portée ont été effectuées par site, documentez les résultats en revue lors d’une réunion du comité de direction lorsque vous décidez d’activer le système téléphonique avec les Plans d’appel de services dans le projet pilote phase.

#### <a name="site-a-phone-system-with-calling-plans-test-case-summary-report"></a>Site A: système de téléphone avec les Plans d’appel le rapport Résumé du cas de test :

> [!TIP]
>   Voici un exemple de modèle de rapport Résumé du test que vous pouvez consulter lors de la prochaine réunion du comité de direction lorsque vous choisissez lorsque pour système de téléphone intégré avec les Plans d’appel de services lors de la phase pilote.


**Système de téléphone équipes avec les Plans d’appel**

**Résumé des résultats**:&nbsp;&nbsp;&nbsp;& #, 9744 ; Passer&nbsp; &nbsp; &nbsp; & #, 9744 ; Partielle&nbsp; &nbsp; &nbsp; & #, 9744 ; Échec 

<table>
<tr><th colspan="2">Test des tons clairs </th></tr>
<tr><td>À DÉFINIR</td><td>À DÉFINIR</td></tr>
<tr><th colspan="2">Test des enseignements  </th></tr>  
<tr><td>**Problème**: TBD</td><td>**Mise à jour :** À DÉFINIR</td></tr>
<tr><th colspan="2">BLOQUEURS identifiés </td></tr>
<tr><td>**Bloqueur de fenêtres publicitaires**: TBD</td><td>**Mise à jour**: TBD</td></tr>
</table>


> [!TIP]
>   Pour faciliter la discussion supplémentaire au cours de l’examen du comité de direction finale, vous pouvez utiliser la mise à jour [matrice de résultats de Test](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_21) fourni par [MyAdvisor](https://myadvisor.fasttrack.microsoft.com/) de documenter et de mettre en évidence les zones supplémentaires qui nécessitent une conversion.



<table>
<tr><td>![](media/audio_conferencing_image7.png)<br/>Points de décision</td><td><ul><li>Évaluer le test détaillée synthèse des résultats par site pour système de téléphone avec les Plans d’appel de fonctions dans la portée.</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Étapes suivantes</td><td><ul><li>Le rapport de synthèse de cas de test du document une fois que tous les résultats de cas de test ont été effectuées.</li><li>Planifier une réunion du comité de direction d’examiner les résultats de synthèse de test.</li><li>Résultats du résumé test présente au comité de direction pour identifier les zones qui nécessitent une conversion.</li></ul></td></tr>
</table>



<a name="present-and-report-phone-system-with-calling-plans-test-findings"></a>Présenter et signaler le système téléphonique avec les Plans d’appel de résultats de test
----------------------------------------------------------------

Une fois toutes les activités de tests ont été accomplies et les défauts avec un impact faible ont été résolus, planifier une réunion de clôture du dernier avec les parties prenantes de tests désignés. Lors de la réunion, adresse :

-   Résumé de l’état

-   Surbrillance/enseignements

-   Leçons apprises

-   Recommandation générale : passer à la phase pilote ou réévaluer les résultats des tests ?

-   Résultats de matrice de test (il doivent être entièrement documentés dans une annexe)

#### <a name="test-plan-deliverables"></a>Livrables du plan de test :

> [!TIP]
>   Voici un exemple d’un plan de test du livrable modèle que vous pouvez utiliser pour documenter les critères nécessaires pour respecter la déconnexion et quitter la phase de test ou interrompre le test jusqu'à ce que tous les problèmes identifiés sont entièrement résolus.

| Résumé de l’état               | Points forts/enseignements | Leçons apprises | Fermeture de recommandation |
|------------------------------|----------------------|-----------------|------------------------|
| <ul><li>Taux de réussite de cas de test de TBD %</li><li>Tous les tests réussis</li></ul> | À DÉFINIR                  | À DÉFINIR             | Passer au projet pilote       |

-   Tous les tests réussis


<table>
<tr><td>![](media/audio_conferencing_image7.png)<br/>Points de décision</td><td><ul><li>Déterminez l’état récapitulatif des tests.</li><li>Identifier des tons clairs et des enseignements test.</li><li>Identifier les leçons apprises.</li><li>Décider quelle conversion restent d’actions, le cas échéant.</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Étapes suivantes</td><td><ul><li>Document test de synthèse des résultats à inclure :<ul><li>Résumé de l’état</li><li>Points forts/enseignements</li><li>Leçons apprises</li></ul></li><li>Planifier une réunion de comité final à passer en revue les résultats de test.</li><li>Passez en revue présent test de synthèse des résultats au cours d’un comité de direction à obtenir la signature finale de la sortie de la phase de test.</li></ul></td></tr>
</table>