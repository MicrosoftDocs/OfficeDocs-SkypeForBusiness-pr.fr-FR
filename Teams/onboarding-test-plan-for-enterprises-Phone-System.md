---
title: Plan de test d’entreprise du système téléphonique avec forfaits d'appels dans Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 03/13/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: Vérifiez que les attentes de votre organisation sont satisfaites en testant le système téléphonique dans les fonctionnalités, les fonctionnalités et la facilité d’utilisation de teams.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1534c1b327e7fda146894430ca750f01c53e8fa4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33898753"
---
<a name="define-and-document-your-phone-system-with-calling-plans-in-teams-test-plan-for-enterprises"></a>Définir et documenter votre système téléphonique avec des plans d’appels dans le plan de test teams pour les entreprises 
============================================================================================

Une fois que vous avez défini et documenté votre système téléphonique avec des plans d’appels dans les offres de réussite et d’implémentation technique de teams dans le cadre de la phase enVision, l’étape suivante consiste à valider le respect des attentes et des exigences de votre organisation. fonctionnalité, fonctionnalités et convivialité. Avant de déployer un déploiement pilote ou final dans votre environnement de production, vous devez effectuer cette étape de validation.

Vous pouvez utiliser le plan de réussite pour les entreprises que vous avez défini lors de la phase enVision afin de baser la détermination des activités, des attentes, des cas de test des fonctionnalités et des fonctionnalités ainsi que de l’étendue globale de la phase de test.

<a name="identify-testing-support-stakeholders"></a>Identifier les personnes prenant en charge les tests
-------------------------------------

Lorsque vous préparez l’évaluation du système téléphonique avec les fonctionnalités d’appels de plan, créez une matrice des parties prenantes du support de test pour identifier les rôles nécessaires à la prise en charge de la phase de test.

> [!TIP]
> Lorsque vous remplissez la matrice des parties prenantes en charge des tests d’équipes, il est possible que certains rôles soient les mêmes que ceux identifiés lors de la phase enVision, mais avec des descriptions de rôles penchées sur les tests. Vous devrez peut-être identifier des rôles supplémentaires en fonction de la configuration requise pour vos scénarios de test.

#### <a name="teams-testing-support-stakeholder-matrix"></a>Matrice des parties prenantes en matière de tests teams

> [!TIP]
> 
> Vous trouverez ci-dessous un exemple de modèle de parties prenantes en charge de tests que vous pouvez utiliser pour documenter les parties prenantes nécessaires à la prise en charge de la phase de test.

| Rôle                          | Description du rôle                                                                                                                                                                          | Ressource affectée, informations de contact et emplacement |
|-------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------|
| Test du ou des sponsors de la direction  | <ul><li>Vérifiez que les fonctionnalités d’équipe répondent aux besoins de votre entreprise. les sponsors de la direction maîtrisent les résultats clés des entreprises et les scénarios d’utilisation prioritaires.</li><li>Faire office de service ultime et supposer une responsabilité, pour les objectifs de test des fonctionnalités d’équipe.</li><li>Aidez-vous à résoudre les problèmes que le responsable des tests a escaladé.</li><li>Communication du parrainement au sein de l’entreprise concernant les objectifs de test.</li><li>Être tenu de prendre des décisions stratégiques clés.</li><li>Être tenu de veiller à la disponibilité des ressources et du budget requis pour soutenir les efforts de test.</li><li>Sensibilisation et acquisition pour la campagne de test avec d’autres parties prenantes.</li><li>Faire office de sponsors lors de la phase d’évaluation du test.</li></ul>                                                 | DÉFINIR                                                  |
| Membres du Comité de direction    | <ul><li>Soyez intéressé et fournissez des recommandations en matière de direction générale du système téléphonique avec le déploiement de services d’offres d’appels.<li>Assistez à la sensibilisation des connaissances stratégiques par le biais de l’achat au sein de l’organisation.</li></ul>                                                                        | DÉFINIR                                                  |
| Chef de projet                  |<ul><li> Gérer et diriger l’équipe du projet.</li><li>Coordonnées des partenaires et équipes travaillant dans le projet.</li><li>Soyez responsable de la création et de la gestion des plans de projet pour les résultats de clés trimestrielles.</li><li>Résoudre les problèmes liés aux fonctions transversales.</li><li>Fournir des mises à jour régulières aux sponsors de Project.</li><li>Incorporation d’une connaissance clé de l’utilisateur les enseignements identifiés dans les résultats des tests dans l’offre globale d’adoption des utilisateurs.</li><li>Envoiez des revues mensuelles et opérationnelles et participez à des examens trimestriels de l’entreprise.</li></ul>                                                                                                                                                         | DÉFINIR                                                  |
| Chef/architecte de la collaboration  | <ul><li>Être responsable de l’exécution de la stratégie de collaboration définie par les dirigeants de l’entreprise.</li><li>Analysez et sélectionnez des produits de collaboration pour l’entreprise qui répondent aux objectifs de votre entreprise.</li><li>Être responsable du design des opérations pour les produits de collaboration.</li><li>Définissez les modèles de fonctionnement et de support.</li><li>Contribuez aux révisions mensuelles et trimestrielles de l’entreprise.</li></ul>                                                                                                 | DÉFINIR                                                  |
| Gestionnaire de projets               | <ul><li>Développement et mise à jour du plan de projet.</li><li>Gérer les livrables du projet en fonction du plan de projet et du budget.</li><li>Enregistrez et gérez les problèmes du projet, y compris les escalades.</li><li>Organisez des appels standup hebdomadaires.</li><li>Mettre en personne et fournir des mises à jour aux sponsors de Project Executive.</li><li>Utiliser la gestion des modifications internes et les équipes de communication pour mettre à jour l’approche de gestion des modifications et les plans de communication selon les besoins.</li></ul>                                                                                                                                                   | DÉFINIR                                                  |
| Directeur de réseau                  | <ul><li>Fournir des informations sur la conception du réseau lors de la phase de découverte;</li><li>Participez à la planification des ateliers de phase enVision.</li><li>Coordonner le travail de l’équipe du réseau lors de l’exécution du projet.</li></ul>                                                                                                                               | DÉFINIR                                                  |
| Directeur de la sécurité                 | <ul><li>Fournir des informations sur la conception et les processus de sécurité pendant la phase de découverte;</li><li>Participez à la planification des ateliers de phase enVision.</li><li>Coordonner le travail de l’équipe de sécurité lors de l’exécution du projet.</li></ul>                                                                                                                | DÉFINIR                                                  |
| Directeur de la téléphonie                | <ul><li>Fournir une entrée lors de la phase de découverte;</li><li>Participez à la planification des ateliers de phase enVision.</li><li>Coordonner le travail de l’équipe de téléphonie lors de l’exécution du projet;</li></ul>                                                                                                                           | DÉFINIR                                                  |
| Directeur de bureau                  | <ul><li>Fournir des informations sur les clients et le processus de mise à jour lors de la phase de découverte;</li><li>Participez à la planification des ateliers de phase enVision.</li><li>Coordonner le travail de l’équipe de bureau lors de l’exécution du projet;</li></ul>                                                                                                              | DÉFINIR                                                  |
| Représentants d'unité commerciale | <ul><li>Contribuez aux guides d’adoption d’utilisateurs et aux matériaux.</li><li>Contribuer aux cas d’utilisation de votre entreprise.</li></ul>                                                                                                                                   | DÉFINIR                                                  |
| Administrateurs informatiques                     | <ul><li>Assistez à la planification et à l’exécution des tests (ce rôle est destiné aux professionnels de l’informatique).                                                                                                                       | DÉFINIR                                                  |
| Propriétaire de service                 | <ul><li>Être responsable du fonctionnement du système téléphonique avec service d’appels, le tout vers le haut.</li><li>Faire office de propriétaire du système téléphonique avec le service forfaits d’appels.</li></ul>                                                                                                               | DÉFINIR                                                  |
| Test/responsable             | <ul><li>Définissez le plan de test, y compris les activités, les dépendances, l’environnement, les objectifs, la stratégie, la réapprovisionnement (environnemental et humaine) et la chronologie requise pour la prise en charge de la phase de test.</li><li>Coordonnées de la remise et de la disponibilité des dépendances de plan de test.</li><li>Aligner selon la priorité appropriée pour la résolution des défauts.</li><li>Faire office de chemin d’escalade pour les problèmes de tests qui surviennent.</li><li>Communiquez et signalez le statut d’un plan de test auprès d’équipes internes et de parties prenantes spécifiques.</li><li>Documenter et présenter les résultats des tests finaux.</li></ul> | DÉFINIR                                                  |
| Système téléphonique avec testeur d’offres d’appels     | <ul><li>Passez en revue le plan de test pour comprendre les exigences de tests, les objectifs, la chronologie, la résolution des problèmes et les scénarios de test à exécuter.</li><li>Passez en revue et développez des cas de test prenant en charge le système téléphonique grâce aux exigences d’acceptation et de fonctionnalités des plans d’appel.</li><li>Exécuter des cas de test et des résultats de test de document.</li><li>Donnez des défauts de document au fur et à mesure qu’ils se produisent, et transformez-les en test de priorité et de résolution des problèmes.</li><li>Testez les régressions pour identifier les défauts après confirmation de la résolution de l’erreur.</li></ul>                                                                | DÉFINIR                                                  |
| Testeur réseau                | <ul><li>Passez en revue le plan de test pour comprendre les exigences de tests, les objectifs, la chronologie, la résolution des problèmes et les scénarios de test à exécuter.</li><li>Passez en revue les cas de test prenant en charge l’acceptation et les exigences de performance du réseau.</li><li>Exécution de tests liés à la préparation du réseau, y compris la connectivité réseau, la validation de performance, la validation de la qualité de service (QoS) et la validation de la configuration du tunnel scindé.</li><li>Achever la validation de la bande passante pour les sites en étendue en utilisant le planificateur de réseau via MyAdvisor.</li><li>Documentation des résultats du test de disponibilité du réseau.</li><li>Donnez des défauts de document au fur et à mesure qu’ils se produisent, et transformez-les en test de priorité et de résolution des problèmes.</li><li>Testez les régressions pour identifier les défauts après confirmation de la résolution de l’erreur.</li></ul>                                                                | DÉFINIR                                                  |
| Testeur de sécurité               | <ul><li>Passez en revue le plan de test pour comprendre les exigences de tests, les objectifs, la chronologie, la résolution des problèmes et les scénarios de test à exécuter.</li><li>Passez en revue et développez des cas de test prenant en charge les exigences d’approbation de sécurité.</li><li>Exécution de tests liés à l’approbation de sécurité des cas de test.</li><li>Les résultats des tests d’approbation de la sécurité des documents.</li><li>Donnez des défauts de document au fur et à mesure qu’ils se produisent, et transformez-les en test de priorité et de résolution des problèmes.</li><li>Testez les régressions pour identifier les défauts après confirmation de la résolution de l’erreur.</li></ul>                                                                | DÉFINIR                                                  |
| Testeur de téléphonie              | <ul><li>Passez en revue le plan de test pour comprendre les exigences de tests, les objectifs, la chronologie, la résolution des problèmes et les scénarios de test à exécuter.</li><li>Passez en revue les cas de test prenant en charge le transfert de numéro de service et les exigences de fonctionnalités.</li><li>Exécutez des tests liés au transfert de numéro de service, notamment sur le port de numéro de service vers Office 365.</li><li>Exécuter des cas de test et des résultats de cas de test de documents.</li><li>Donnez des défauts de document au fur et à mesure qu’ils se produisent, et transformez-les en test de priorité et de résolution des problèmes.</li><li>Testez les régressions pour identifier les défauts après confirmation de la résolution de l’erreur.</li></ul>                                                                | DÉFINIR                                                  |
| Système téléphonique avec test d’administration de plans d’appel | <ul><li>Passez en revue le plan de test pour comprendre les exigences de tests, les objectifs, la chronologie, la résolution des problèmes et les scénarios de test à exécuter.</li><li>Passez en revue et développez des cas de test prenant en charge le système téléphonique grâce aux exigences d’approbation et de fonctionnalités d’assistance.</li> <li>Exécuter des cas de test et des résultats de cas de test de documents.</li><li>Donnez des défauts de document au fur et à mesure qu’ils se produisent, et transformez-les en test de priorité et de résolution des problèmes.</li><li>Testez les régressions pour identifier les défauts après confirmation de la résolution de l’erreur.</li></ul>                                                                | DÉFINIR                                                  |


<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/> <br/>Points de décision</td><td><ul><li>Déterminez la prise en charge des tests et des rôles des parties prenantes dont vous avez besoin pour tester le système téléphonique avec les fonctionnalités d’appel de plan dans votre environnement.</li><li>Déterminez les ressources que vous affecterez aux rôles d’assistance technique de test et d’intervenant que vous avez identifiés.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Étapes suivantes</td><td><ul><li>Documentez les rôles d’assistance technique de test et d’intervenant requis dans votre matrice des parties prenantes du support de test.</li><li>Documentez les informations de contact et les détails d’emplacement de chaque ressource que vous listez dans la matrice des parties prenantes du support de test.
</table>


<a name="define-phone-system-with-calling-plans-feature-requirements"></a>Définition d’un système téléphonique avec la configuration requise pour les offres d’appels 
------------------------------------------------------------

Dans le cadre de la définition d’un système téléphonique avec la configuration requise pour les utilisateurs dans le cadre de l’application, reportez-vous à la rubrique [système téléphonique avec forfaits d’appels](calling-plan-landing-page.md)
Ensuite, évaluez la procédure publique de la dernière équipe pour déterminer:

-   Le système téléphonique doté de fonctionnalités d’appels de plan que vous déploierez pour les utilisateurs de l’étendue.

-   Système de téléphonie de l’utilisateur attendu avec les offres d’appels d’offres en fonction de votre paysage de déploiement actuel de Skype entreprise, Exchange et SharePoint.

-   La possibilité de vérifier le système téléphonique avec les fonctionnalités d’appel d’appels décrite dans la dernière gamme publique qui répond à vos besoins en matière d’utilisation, de fonctionnalités et d’étendue dans la chronologie de votre déploiement;

> [!TIP]
> Le plan d’identification du système téléphonique avec les fonctionnalités d’appel de plan dans le cadre de votre déploiement est <https://aka.ms/O365Roadmap>disponible à l’adresse.

À présent que le système téléphonique doté de personnes et de fonctionnalités de plans d’appel a été défini, le prochain critère d’évaluation sera l’interface d’interopérabilité avec Teams. Pour plus d’informations sur l’interopérabilité et sur les options de configuration disponibles, reportez-vous à la rubrique [Microsoft teams et interopérabilité de Skype entreprise](https://docs.microsoft.com/microsoftteams/teams-and-skypeforbusiness-coexistence-and-interoperability).

#### <a name="phone-system-with-calling-plans-feature-definition"></a>Système téléphonique avec définition de la fonction plans d’appel

> [!TIP]
> Vous trouverez ci-dessous un exemple de système téléphonique avec un modèle de définition de plans d’appel que vous pouvez utiliser pour documenter le système téléphonique avec les fonctionnalités d’administration de plan d’appel et de groupe d’utilisateurs à évaluer.


| Niveau entreprise   | Réunions de collaboration    | Plateforme et périphériques   | Professionnels de l’informatique  | Groupe professionnel supplémentaire, propre à un site  | Exigences remplies par le plan de la dernière équipe teams |
|-------------------------------------------|----------------------------|------------------|------------------------|-------------------|-------------------|
| <ul><li>Fonctionnalités d’appel du système téléphonique:<ul><li>Transfert en aveugle</li><li>Blocage des appels</li><li>Transfert d’appel</li><li>Masquage de l’identification de l’appelant</li><li>Support E911</li><li>Numéro de téléphone</li><li>Mise en attente des appels</li><li>Gestion de plusieurs appels</li><li>Sonnerie simultanée</li><li>Boîte vocale Azure</li></ul></li><li>Support technique pour les appels</li></ul> |<ul><li>Appels Skype entreprise-à-teams</li></ul> |<ul><li> Windows, prise en charge des fonctionnalités de réunion du client de Mac teams</li><li>La prise en charge des réunions du client teams du navigateur pour:<ul><li>Chrome</li><li>Microsoft Edge</li></ul></li><li>support technique pour les réunions iOS et Android</li><li>Prise en charge TTY</li></ul> | <ul><li>Portail de diagnostic de la qualité des appels</li><li>Plan de numérotation client</li><li>Stratégies d’ID d’appelant client</li><li>Activer l’analyse de la qualité des appels (bord)</li></ul> | <ul><li>Valider les fonctionnalités des réunions teams en fonction de l’image d’un ordinateur portable</li><li>Prise en charge de langues spécifiques</li><li>Paramètres d’objets de stratégie de groupe appliqués pour un scénario utilisateur ou un site spécifique donné</li></ul> | Oui  |




#### <a name="phone-system-with-calling-plans-user-functionality-definition"></a>Système téléphonique avec la définition des fonctionnalités utilisateur de plans d’appel

> [!TIP]
> Vous trouverez ci-dessous un exemple de modèle de fonctionnalité utilisateur que vous pouvez utiliser pour documenter l’utilisation requise en fonction du système téléphonique dont sont évalués les fonctions d’appel.


| Découverte d’Exchange                          | Découverte de SharePoint                            | Expertise de la stratégie d’interopérabilité dans teams |
|----------------------------------------------|--------------------------------------------------|------------------------------------------|
| <ul><li>Créer des équipes (la création de groupes Office est activée)</li><li>Rejoindre des équipes</li><li>Créer des canaux</li><li>Créer et afficher des réunions</li><li>Modifier une image de profil utilisateur</li><li>Ajouter et configurer des connecteurs</li><li>Ajouter et configurer des onglets</li><li>Ajouter et configurer des bots</li></ul> | <ul><li>Stocker et partager des fichiers dans les conversations d’équipe</li><li>Stocker et partager des fichiers et des fichiers dans des discussions privées (en fonction de OneDrive)</li></ul> | <ul><li>ChatDefaultClient: par défaut</li><li>CallingDefaultClient: par défaut</li></ul>      |


<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/> <br/>Points de décision</td><td><ul><li> Déterminez le système téléphonique doté de la catégorie plans d’appel que vous déploierez dans votre environnement.</li><li>Identifiez votre système téléphonique utilisateur à l’aide de la fonctionnalité offres d’appels qui vous a donné votre environnement de déploiement actuel de Skype entreprise, Exchange et SharePoint.</li><li>Déterminez l’efficacité de l’interopérabilité entre les équipes que vous déploierez.</li><li>Passez en revue la plan d’évolution publique de la dernière équipe et déterminez si les capacités de charge de travail actuelles répondent à votre chronologie de déploiement.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Étapes suivantes</td><td><ul><li>Documentez le système téléphonique avec les fonctionnalités de catégorie offres d’appel requises pour prendre en charge votre système téléphonique avec le déploiement d’offres d’appels.</li><li>Le système téléphonique des utilisateurs avec des offres d’appel et des fonctionnalités d’interopérabilité pour le déploiement actuel de Skype entreprise, Exchange et SharePoint.</li><li>Documentez si la gamme de formations publiques de la dernière équipe qui représente le système téléphonique avec les fonctionnalités d’appels d’offre répond aux besoins en matière d’entreprise et au minutage de votre déploiement.</li></ul></td></tr>
</table>

<a name="define-and-document-your-phone-system-with-calling-plans-test-plan"></a>Définir et documenter votre système téléphonique avec le plan de test des offres d’appels
------------------------------------------------------------------

Après avoir défini le système téléphonique avec les fonctionnalités d’appels de plan dans l’objectif, l’étape suivante consiste à créer le plan de test. À un niveau élevé, le plan de test englobe la stratégie de test générale et la méthodologie que vous utiliserez pour la prise en charge de la validation des fonctionnalités dans le processus de test.

À un niveau élevé, le plan de test doit inclure:

-   **Étendue des tests:** Résume les zones ciblées (objectifs, scénarios et objectifs) à évaluer dans le cadre de la phase de test.

-   **Scénarios de test:** Ensemble de cas de test à valider pour le système téléphonique avec les fonctionnalités d’appels d’offres en matière d’étendue

-   **Ressources de test:** Matrice de ressources nécessaires à la prise en charge des efforts de test d’un point de vue environnemental, technique et personnel

-   **Planning de test (chronologie):** Représente au début du test, la durée de la dernière tentative et la date de fin de la phase de test.

-   **Rapport de défectuosité et correction:** Recommandations en matière de rapports, de suivi et de triage des problèmes liés aux tests

-   **Triage et escalade de défaut:** Plan du mode et de la date de début d’une escalade de défaut

-   **Test de la sortie et du critère de suspension:** Recommandations en matière de contour pour la fermeture de la phase de test ou la mise en suspens

-   **Tests de livrables:** Résumé des résultats qui seront développés et fournis pour prendre en charge l’acceptation et la sortie de la signature

> [!TIP]
>   Une méthodologie de test peut déjà exister au sein de votre organisation, mais les conseils ci-dessous illustrent des pratiques recommandées qui peuvent être incluses ou optimisées séparément pour le test des fonctionnalités d’équipes dans votre environnement.

Dans les sections qui suivent, vous trouverez des instructions prescrites supplémentaires qui vous aideront à prendre des décisions spécifiques et des modèles et des rubriques que vous devez prendre en considération lors de la fin de votre plan de test.

### <a name="define-and-document-testing-scope"></a>Définir et étendue de l’évaluation des documents

Lorsque vous travaillez pour développer votre plan de test, vous devez définir le niveau de l’étendue des tests avant, en mettant en évidence la charge de travail et la liste de fonctionnalités que vous évaluez.

L’objectif de l’évaluation correcte du système téléphonique et des plans d’appel inclut les fonctionnalités suivantes:

-   Système téléphonique avec les offres d’appels prêts sur le site

-   Système téléphonique avec l’interface utilisateur de offres d’appels

-   Système téléphonique avec administration de plans d’appel

#### <a name="phone-system-with-calling-plans-testing-scope"></a>Système téléphonique avec l’étendue des tests de plans d’appel

> [!TIP]
>   Vous trouverez ci-dessous un exemple de modèle d’étendue de test que vous pouvez utiliser pour documenter le système téléphonique avec les fonctionnalités d’administration de plans d’appel et de groupe d’utilisateurs à évaluer.

| Système téléphonique avec les offres d’appels prêts sur le site                                                                                                                                                                                    | Système téléphonique avec l’interface utilisateur de offres d’appels                                                                                                                                                                                         | Système téléphonique avec une interface d’administration de plans d’appel                                                                           |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------|
| <ul><li>Planification de la bande passante de planificateur de réseaux (via MyAdvisor)<li></li>Connexion réseau et validation des performances (via l’outil d’évaluation du réseau Skype entreprise)<li></li>Validation de la qualité de service (QoS)<li></li>Validation du tunnel d’accès distant</li></ul>|<ul><li>Fonctionnalités PBX<li></li>Appel RTC (national et international)<li></li> Placement et réception d’appels RTC<li></li>Boîte vocale Azure<li></li>E911<li></li>Plan de numérotation client<li></li>Masquage de l’ID d’appelant client <li></li>Fonctionnalités avancées de contrôle d’appel (par exemple, le transfert d’appel et la sonnerie simultanée)</li></ul> |<ul><li>Attribution de licence</li><li>Portage des numéros d’abonnés vers Office 365</li><li>Système téléphonique avec rapports d’offres d’appels</li><li>Rapports sur la qualité des appels (bord)</li></ul> |

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/> <br/>Points de décision</td><td><ul><li>Déterminez le système téléphonique avec les offres d’appels qui testent l’étendue en identifiant les fonctionnalités qui doivent être évaluées par la zone de focalisation.</li><li>Déterminez les objectifs et les objectifs supplémentaires à des fins d’évaluation.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Étapes suivantes</td><td><ul><li>Documentez le système téléphonique avec les fonctionnalités d’offres d’appels qui doivent être évaluées par la zone de focalisation.</li><li>Documenter des buts et objectifs supplémentaires pour l’évaluation.</li></ul></td></tr>
</table>

### <a name="define-and-document-phone-system-with-calling-plans-test-cases"></a>Définir et documenter un système téléphonique avec des cas de test de plans d’appel

Après avoir défini le système téléphonique avec les fonctionnalités de plans d’appel, le déploiement de clients et les scénarios côte à côte avec Skype entreprise (le cas échéant), l’étape suivante consiste à formuler les cas de test requis pour évaluer le système téléphonique avec les fonctionnalités d’appel d’appels dans hors. À un niveau élevé, les cas de test sont généralement groupés par zone de focalisation et incluent les éléments suivants:

-   **Titre du cas de test:** Zone focalisée de la fonctionnalité que le test évalue (par exemple, un système téléphonique avec des plans d’appel)

-   **Description de cas de test:** Récapitulatif des buts des fonctions de test évaluées

-   **Instructions de cas de test:** Étapes à suivre pour exécuter correctement le cas de test exécuté

-   **Environnement requis (prérequis):** Instructions de configuration nécessaires à l’exécution correcte du test

-   **Ressource requise:** Ressources humaines requises pour l’évaluation et l’exécution appropriées du test

-   **Résultats attendus:** Résultat attendu après le test réussi

> [!NOTE]
>   Dans la mesure où l’approche et le niveau de détail requis pour la création de cas de test peuvent varier au sein de votre organisation, il est recommandé de suivre une approche permettant d’obtenir un niveau de détail approprié pour la prise en charge des tests généraux. facilité.

> [!TIP]
>   Pour vous aider à effectuer des tests de création de cas de test en tant que point de départ, consultez la liste des recommandations en matière d’utilisation du système téléphonique disponibles aux [réunions et aux appels d’équipe](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8).

#### <a name="phone-system-with-calling-plans-test-case"></a>Système téléphonique avec un cas de test de plans d’appel

> [!TIP]
>   Vous trouverez ci-dessous un exemple de modèle de cas de test que vous pouvez utiliser pour documenter le système téléphonique avec les fonctionnalités d’administration de plans d’appel et de groupe d’utilisateurs à évaluer.

Système téléphonique avec validation de plans d’appel

| ID de cas de test | Titre du cas de test               | Description de cas de test                                                  | Environnement requis pour l’exécution de cas de test                                               | Étapes requises pour l’exécution de cas de test                                                                                                                                                          | Ressource de test requise              |
|--------------|-------------------------------|------------------------------------------------------------------------|--------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------|
| 1            | Placement d’un appel RTC sortant | Vérifiez que vous pouvez passer un appel vocal externe à un numéro à 10 chiffres. |<ul><li>Client teams installé.</li><li>Utilisateur activé avec les licences Office 365 suivantes attribuées:<ul><li>Office Enterprise E5 avec le système téléphonique, Microsoft teams et les offres d’appels nationaux et internationaux</li><li>Office entreprise E3 avec le système téléphonique, Microsoft teams et les offres d’appels nationaux et internationaux</li></ul></li></ul> | <ol><li>Connectez-vous au client Teams.</li><li>Sélectionnez le pavé de numérotation, puis entrez le numéro à 10 chiffres à composer.</li><li>Vérifiez que le numéro de numérotation est correctement normalisé et que l’appel RTC externe est établi.</li></ol>    | Système téléphonique avec testeur d’offres d’appels |


> [!TIP]
>   Pour obtenir des recommandations supplémentaires sur la création d’un cas de test individuel et sur la création d’un plan global pour l’évaluation du système téléphonique avec les fonctionnalités d’appels de votre organisation, consultez le [plan de test du système téléphonique](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_21) fourni par [MyAdvisor](https://myadvisor.fasttrack.microsoft.com/).


<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/> <br/>Points de décision</td><td><ul><li>Déterminez le système téléphonique avec les fonctionnalités d’administration et d’utilisation des plans d’appel.</li><li>Déterminez quel environnement de test est requis pour prendre en charge l’exécution de cas de test.</li><li>Déterminez les étapes nécessaires à l’évaluation de cas de test.</li><li>Déterminez les ressources nécessaires à l’exécution correcte du test.</li></ul></td></tr>
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
>   Vous trouverez ci-dessous un exemple de test de modèle de demande de ressources que vous pouvez utiliser pour documenter les différents types de ressources nécessaires à la prise en charge de la phase de test.


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
>   Vous trouverez ci-dessous un exemple de modèle de critères de chronologie des tests que vous pouvez utiliser pour documenter les dates prévues lors du déroulement d’activités de test spécifiques ou des jalons remis par.

| Tâche                                                 | Consultation       | Date de début                                                             | Date d’achèvement | Propriétaire | Ressources affectées | Coût |
|------------------------------------------------------|-----------------|------------------------------------------------------------------------|-----------------|-------|--------------------|------------|
| Rapport de test                                          | DÉFINIR             | DÉFINIR                                                                    | DÉFINIR             | DÉFINIR   | DÉFINIR                | Heures de TBD  |
| Exécution de cas de test: système téléphonique avec des plans d’appels | DÉFINIR             | DÉFINIR                                                                    | DÉFINIR             | DÉFINIR   | DÉFINIR                | Heures de TBD  |
| Exécution du cas de test: disponibilité du réseau               | DÉFINIR             | DÉFINIR                                                                    | DÉFINIR             | DÉFINIR   | DÉFINIR                | Heures de TBD  |


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
>   Vous trouverez ci-dessous un exemple de rapport sur les défauts et de modèle de plan de correction que vous pouvez utiliser pour documenter des problèmes détectés lors de la phase de test.

| ID de défaut                                | ID de cas de test affecté | Description de l’erreur                                                                                 | /Steps environnement pour reproduire                                                                                                | Minimal | État | Envoyé par | Propriétaire affecté | Informations de support (journaux, captures d’écran, etc.) |
|------------------------------------------|-----------------------|----------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------|----------|--------|--------------|----------------|---------------------------------------------------|
| 1                                        | 1                     | Lorsque l’utilisateur entre une extension à quatre chiffres, en essayant de passer un appel sortant, l’appel échoue. | Dans le client Microsoft Teams, sélectionnez le pavé de numérotation, entrez une extension à quatre chiffres et sélectionnez l’icône de téléphone pour essayer de passer l’appel. | Moyen   | Été | Louis Lahr   | Isabelle gris      | Journal côté client teams<br/> Capture d’écran du client teams     |


<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/> <br/>Points de décision</td><td><ul><li>Déterminez les niveaux de gravité du critère de défaut que vous attribuez à l’effort de test.</li><li>Déterminez les critères de signalement de problèmes que vous souhaitez utiliser pour le test.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Étapes suivantes</td><td><ul><li>Documentez les critères de signalement de défaut de test requis dans le modèle fourni.</li><li>Incluez le modèle complet dans le cadre de votre plan de test global.</li></ul></td></tr>
</table>


### <a name="define-and-document-exit-and-suspension-criteria"></a>Définir et définir les critères de sortie et de suspension d’un document

Dans le cadre de la procédure globale d’exécution d’un plan de test, vous devez définir des critères pour indiquer le point où vous devez suspendre les efforts de test et les exigences qui doivent être satisfaites pour obtenir une connexion et sortir de la phase de test.

#### <a name="test-plan-exit-and-suspension-criteria"></a>Critères de sortie et de suspension du plan de test

> [!TIP]
>   Vous trouverez ci-dessous un exemple de modèle de critères de Exit et de suspension que vous pouvez utiliser dans votre plan de test pour vous permettre de vous connecter, de quitter la phase de test ou de suspendre des activités de test.

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
>   Vous trouverez ci-dessous un exemple de modèle de réaffectation de défaut que vous pouvez utiliser dans le cadre de votre plan de test pour documenter le processus d’escalade requis pour la définition de priorités et la résolution des erreurs de test.

| ID de défaut                                | Description de l’erreur                                                                                 | Évaluation de priorité de défaut                                           | Propriétaire de défaut affecté | Point de réaffectation de défaut affecté | Méthode de réaffectation de défaut                                          | État d’erreur | Résolution requise par date | Date d’État |
|------------------------------------------|----------------------------------------------------------------------------------------------------|----------------------------------------------------------------------|-----------------------|----------------------------------|-------------------------------------------------------------------|---------------|-----------------------------|-------------|
| 1                                        | Lorsque l’utilisateur entre une extension à quatre chiffres, en essayant de passer un appel sortant, l’appel échoue. | Moyen                                                               | Isabelle gris             | Louis Lahr                       | Tri hebdomadaire-examen de la messagerie à haute priorité aux parties prenantes touchées | Ouvre          | DQP                        | 1/12/2018   |



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
>   Vous trouverez ci-dessous un exemple de matrice de livrables d’un plan de test que vous pouvez utiliser pour documenter les livrables à créer, ainsi que les ressources nécessaires pour la révision, l’approbation et la connexion.

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
----------------------------

En tant qu’élément critique prenant en charge votre déploiement d’équipe, la disponibilité du réseau est une partie essentielle des tests qui permettent de garantir l’optimisation du réseau pour la prise en charge des communications de l’équipe. Pour vous assurer que votre réseau est prêt pour les sites concernés, incluez les zones principales répertoriées ci-dessous dans votre stratégie de test générale:

-   Estimation de la bande passante et planification avec le planificateur réseau (via MyAdvisor)

-   Validation de la configuration de qualité de service (QoS)

-   Vérification de connectivité et de performance réseau via la simulation du trafic

-   Validation par tunneling fractionné

### <a name="execute-network-planner-through-myadvisor-for-sites-and-personas-in-scope"></a>Exécuter le planificateur de réseau (via MyAdvisor) pour les sites et les personnes dans l’étendue

Avant l’introduction de services de communication en temps réel tels que teams dans votre environnement, il est important de s’assurer que le réseau a été correctement optimisé et ajusté à partir d’une connexion Azure ExpressRoute (le cas échéant), d’Internet et de la bande passante WAN.

Pour vous aider à déterminer la quantité de bande passante et le niveau d’optimisation du réseau requis pour les sites de l’étendue prenant en charge votre déploiement, vous pouvez exécuter l’outil [Network Planner](https://myadvisor.fasttrack.microsoft.com/CloudVoice/NetworkPlanner/Help?sectionName=DashboardHelp) (via MyAdvisor) pour vérifier la disponibilité du réseau de votre organisation. Pour plus d’informations sur la façon de déterminer la configuration requise pour les équipes via le planificateur de réseaux, voir MyAdvisor: Network Planner.

> [!TIP]
>   Pour plus d’informations sur l’onglet **recommandations** , avec des exemples sur la façon de configurer et d’interpréter les résultats, voir [vue d’ensemble des recommandations](https://myadvisor.fasttrack.microsoft.com/CloudVoice/NetworkPlanner/Help?sectionName=RecommendationHelp)du planificateur réseau.



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
>   Vous trouverez ci-dessous un exemple de modèle de rapport de synthèse de tests que vous pouvez consulter lors de la réunion du Comité de direction suivant lorsque vous décidez de l’intégration d’un système téléphonique aux services de plans d’appel dans le cadre de la phase pilote.


**Validation de la configuration QoS via un objet de stratégie de groupe ou un analyseur de message**

**Résumé**des résultats&nbsp; &nbsp; &nbsp; :&#9744;&nbsp; &nbsp; &nbsp; passe &#9744;&nbsp; &nbsp; partielle&nbsp; &#9744;Fail

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
>   Outre le volume de solutions d’accès à distance disponibles sur Marketplace, ce document ne permet pas de fournir des informations spécifiques aux fournisseurs et seules les recommandations générales relatives aux solutions d’accès à distance.


<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/><br/>Points de décision</td><td><ul><li>Déterminez la configuration de tunneling fractionné à implémenter.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Étapes suivantes</td><td><ul><li>Mettre en œuvre une configuration de tunneling fractionné.</li><li>Testez et validez la configuration de tunneling fractionné.</li></ul></td></tr>
</table>


### <a name="document-split-tunnel-configuration-validation-test-results"></a>Résultats du test de vérification de la configuration du tunnel

Une fois que vous avez terminé de tester la configuration de tunneling fractionné pour les sites de l’application, créez un rapport qui résume les résultats des tests et présentez-le au cours de la révision du Comité de direction suivant.

#### <a name="site-a-split-tunnel-configuration-validation-testing-summary-report"></a>Site A: rapport de synthèse de vérification de la configuration du tunnel de fractionnement

> [!TIP]
>   Vous trouverez ci-dessous un exemple de modèle de rapport de synthèse de tests que vous pouvez consulter lors de la réunion du Comité de direction suivant lorsque vous décidez de l’intégration d’un système téléphonique aux services de plans d’appel dans le cadre de la phase pilote.

**Validation de la configuration du tunnel scindé**

**Résumé**des résultats&nbsp; &nbsp; &nbsp; :&#9744;&nbsp; &nbsp; &nbsp; passe &#9744;&nbsp; &nbsp; partielle&nbsp; &#9744;Fail

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
>   Pour effectuer une analyse de la disponibilité du réseau et un niveau d’exhaustivité pour les sites dans le cadre de l’objet, indiquez un lead pour chaque site qui peut vous aider à améliorer les efforts d’évaluation de la disponibilité du réseau.



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

**Résumé**des résultats&nbsp; &nbsp; &nbsp; :&#9744;&nbsp; &nbsp; &nbsp; passe &#9744;&nbsp; &nbsp; partielle&nbsp; &#9744;Fail 



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
<tr><th colspan="2">Test de lowlights  </th></tr> 
<tr><td><strong>Problème</strong>: latence élevée</td><td><strong>Correction:</strong> Recherchez le routage de paquets et implémentez l’itinéraire idéal.</td></tr>
<tr><td><strong>Problème</strong>: la durée de l’aller-retour n’est pas&#39;t doublement la latence</td><td><strong>Correction:</strong> Recherchez un problème de configuration de routeur ou de pare-feu. Examen des chemins de trafic.</td></tr>
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


<a name="execute-subscriber-number-port-validation"></a>Exécuter une validation de port du numéro d’abonné
-----------------------------------------

Si vous avez besoin de transférer des numéros dans le cadre de la fourniture de fonctionnalités d’appels entrants/sortants dans le système téléphonique avec les services de plans d’appel pris en charge par Teams, vous devez utiliser un port partiel pour un numéro de service. Cela vous permettra de valider les attentes, les exigences et les délais raisonnables lorsque vous avez fini de préparer votre déploiement de système téléphonique avec les services d’appels de plan dans votre environnement de production.

Pour effectuer un portage partiel du numéro d’abonné de votre fournisseur de services RTC actuel vers Teams, suivez les étapes décrites ci-dessous.

#### <a name="step-1"></a>Étape 1

Identifiez le numéro que vous voulez utiliser pour le portage d’Office 365 en tant que numéro d’utilisateur attribuable (numéro de l’abonné) pour être desservi par le biais du système téléphonique avec le Service plans d’appel dans Teams.

> [!IMPORTANT]
>Lorsque vous planifiez votre test de transfert de numéro, veillez à consulter les dernières recommandations en matière de demandes de transfert de numéros dans les questions fréquentes sur le [port de numéro](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/transferring-phone-numbers-common-questions).

#### <a name="step-2"></a>Étape 2

Identifiez et documentez toutes les informations sur le compte (y compris le nom utilisé pour le compte en particulier) pour le transporteur actuel du numéro de test que vous allez transférer.
En règle générale, vous trouverez les informations dont vous avez besoin dans la dernière facture de votre fournisseur de services actuel.

> [!TIP]
>   Vous pouvez porter ou transférer des numéros de téléphone dans les pays/régions actuellement pris en charge. Toutefois, le mode de soumission d’une demande de transfert peut varier en fonction du pays ou de la région à partir duquel les numéros de téléphone sont sources. Pour obtenir la liste actualisée des pays/régions actuellement pris en charge, consultez la rubrique [disponibilité des pays et de la région pour les conférences audio et les offres d’appels](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).
> 
>   Pour plus d’informations sur le transfert de numéros de téléphone vers le système téléphonique avec les offres d’appels, ainsi que les restrictions potentielles, voir [transférer des numéros de téléphone vers office 365](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365) et [restrictions de numérotation gratuites dans Office 365](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/toll-free-dialing-limitations-and-restrictions.).

#### <a name="step-3"></a>Étape 3

Téléchargez et créez une lettre d’autorisation (LOA) pour votre pays/région, en fonction du numéro de service, comme type de transfert de numéro.

>[!NOTE]
>   Dans la mesure où les formats LOA peuvent être différents selon le pays, la région ou le type de numéro (c’est-à-dire géographique ou non géographique ou numéro de téléphone ou numéro gratuit), vérifiez que vous utilisez le modèle LOA approprié pour votre type de scénario spécifique. Pour plus d’informations sur le choix de l’LOA, voir [Télécharger une lettre d’autorisation (LOA)](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/download-a-letter-of-authorization-loa) , ou accéder directement à la [page de téléchargement](https://www.microsoft.com/download/details.aspx?id=49167).

>[!NOTE]
> **États-Unis uniquement**<br/>
>   Étant donné que nous ne transférons qu’un numéro de service pour ce test, veillez à sélectionner les champs appropriés dans le LOA, comme illustré ci-dessous:

Combien de ![numéros de téléphone transférerez-vous? Réponse: je ne transfère que certains de mes numéros de mon opérateur actuel.] Combien de (media/onboarding-test-plan-image1.png "numéros de téléphone transférerez-vous? Réponse: je ne transfère que certains de mes numéros de mon opérateur actuel.")

![Quels types de numéros de téléphone allez-vous transférer? Réponse: je transfère des numéros de téléphone de service vocal comme pour les standards automatiques ou les ponts de conférence.] (media/onboarding-test-plan-image2.png "Quels types de numéros de téléphone allez-vous transférer? Réponse: je transfère des numéros de téléphone de service vocal comme pour les standards automatiques ou les ponts de conférence.")

>[!IMPORTANT]
>   Lorsque vous transférez manuellement des numéros de téléphone à l’aide d’un LOA, veillez à sélectionner le type de numéro de téléphone correct. Vous devez soumettre des demandes de transfert distinctes pour chaque type de numéro de téléphone que vous voulez transférer.<br/><br/>
>   Comme nous voulons tester le processus de transfert de numéro à l’aide d’un numéro de téléphone associé au même numéro de téléphone de facturation (BTN), vous devez vous assurer que le numéro de téléphone de facturation ne correspond *pas* au numéro de téléphone à transférer.

#### <a name="step-4"></a>Étape 4

Dans le portail d’administration du client, accédez à l’onglet **support** , puis créez et envoyez une demande de service. Joignez le fichier LOA Completed pour planifier le numéro de téléphone associé à votre fournisseur de services actuel pour la migration. Pour choisir la méthode de demande de service la plus appropriée à la taille de votre client, reportez-vous à la rubrique [envoi manuel d’une demande de service personnalisée](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/manually-submit-a-custom-service-request).

Après la réception de la demande d’assistance, le support Microsoft assurera le suivi en fonction de la méthode de communication que vous avez choisie et vous avertit de votre statut et des étapes suivantes pour terminer le processus de transfert de numéro.

#### <a name="step-5"></a>Étape 5

Une fois que le numéro a été transféré en tant que nouveau numéro d’abonné dans Office 365, attribuez-lui le numéro à l’aide du service de plan d’appel dans le portail \> d’administration du client dans le **Centre** \> **d’administration Skype entreprise. Voix**. Dans l’onglet **numéros de téléphone** , attribuez le nouveau numéro de service au système téléphonique grâce au service forfaits d’appels.

> [!TIP]
>   Même si cette tâche attribue un nouveau numéro de service au système téléphonique avec des plans d’appels, au moment de la rédaction de ce code, l’administration de cette tâche est effectuée à l’aide du centre d’administration Skype entreprise.

#### <a name="step-6"></a>Étape 6

À présent que vous avez attribué le numéro de l’abonné à une équipe, connectez-vous à un client teams en tant qu’utilisateur et composez un numéro à 10 chiffres externe via PSTN. Une fois l’appel terminé, confirmez que l’appel a été connecté et que l’ID d’appelant affiché correspond au numéro d’abonné que vous avez porté.

#### <a name="step-7"></a>Étape 7

À partir d’un numéro RTC externe, vous devez effectuer un appel vers le numéro de l’abonné que vous avez porté à Office 365 et vérifier que l’appel est reçu entrant et connecté via le client Teams.



<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/><br/>Points de décision</td><td><ul><li>Déterminez les numéros d’abonnés nationaux que vous devez porter, par pays/région.</li><li>Déterminez le modèle LOA que vous utiliserez.</li><li>Déterminez si votre opérateur actuel (opérateur de perte) permet de défragmenter le numéro de téléphone (c’est-à-dire autorisant les commandes de transfert partiel).</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Étapes suivantes</td><td><ul><li>Rassemblez les informations requises et préparez le LOAs.</li><li>Téléchargez et remplissez les modèles LOA dont vous avez besoin.</li><li>Envoyez une demande de transfert de numéro d’abonné.</li><li>Exécutez une validation de test pour les numéros portés en les affectant au système téléphonique avec service d’appels d’offre pour l’accès rendez-vous et confirmez qu’ils fonctionnent, comme indiqué dans les étapes 6 et 7 plus haut dans cette section.</li></ul></td></tr>
</table>


### <a name="document-service-number-porting-test-results"></a>Résultats du test de Portage du numéro de service de document

Une fois que vous avez terminé de tester le numéro de l’abonné, créez un rapport qui résume les résultats du test à présenter lors de la révision du Comité de direction suivant.

#### <a name="site-a-number-porting-test-summary-report"></a>Site A: rapport de synthèse des tests de transfert de numéros

> [!TIP]
>   Vous trouverez ci-dessous un exemple de modèle de rapport de synthèse de test que vous pouvez utiliser pour passer en revue lors de la réunion du Comité de direction suivant lorsque vous décidez de l’intégration d’un système téléphonique aux services de plans d’appel dans le cadre de la phase pilote.

**Transfert de numéro de service**

**Résumé**des résultats&nbsp; &nbsp; &nbsp; :&#9744;&nbsp; &nbsp; &nbsp; passe &#9744;&nbsp; &nbsp; partielle&nbsp; &#9744;Fail 

<table>
<tr><th colspan="2">Recommandations en matière de tests </th></tr>
<tr><td>DÉFINIR</td><td>DÉFINIR</td></tr>
<tr><th colspan="2">Test de lowlights  </th></tr><br/><tr><td><strong>Problème</strong>: TBD</td><td><strong>Correction:</strong> DÉFINIR</td></tr>
<tr><th colspan="2">Bloqueurs identifiés </td></tr>
<tr><td><strong>Bloqueur</strong>: TBD</td><td><strong>Correction</strong>: TBD</td></tr>
</table>


> [!TIP]
>   Pour faciliter la discussion supplémentaire au cours de l’évaluation du Comité d’orientation final, vous pouvez utiliser la [matrice de résultats de test](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_21) mise à jour fournie par [MyAdvisor](https://myadvisor.fasttrack.microsoft.com/) pour documenter et mettre en évidence des zones de test supplémentaires qui nécessitent une correction.


<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/><br/>Points de décision</td><td><ul><li>Déterminez si les numéros d’abonnés envoyés pour la migration ont été portés au système téléphonique avec le service de plans d’appel.</li><li>Évaluez si vous avez été en mesure d’affecter le numéro de service sur le système téléphonique avec le service des plans d’appels.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Étapes suivantes</td><td><ul><li>Documentez les résultats des tests de portage de votre numéro.</li><li>Exécutez les plans de remontée et de mise à jour pour résoudre les problèmes rencontrés avec le processus de transfert de numéro, le cas échéant.</li><li>Planifiez une réunion de Comité d’orientation pour passer en revue les résultats de synthèse des tests.</li><li>Présenter les résultats du test de synthèse au Comité d’orientation pour identifier les domaines qui nécessitent une correction.</li></ul></td></tr>
</table>


<a name="execute-your-test-plan-for-phone-system-with-calling-plans"></a>Exécuter votre plan de test pour le système téléphonique avec les offres d’appels
----------------------------------------------------------

Maintenant que vous avez défini votre plan de test, l’étape suivante consiste à parcourir les cas de test, en insistant sur l’évaluation du système téléphonique avec les fonctionnalités d’administration des plans d’appel et de l’utilisation de l’application. Avant le début du test, vérifiez que les conditions de test répertoriées ci-dessous sont en place.

### <a name="phone-system-with-calling-plans-testing-prerequisites"></a>Système téléphonique avec la configuration requise pour les tests d’offres

-   Des cas d’utilisation peuvent avoir été définis pour le système téléphonique avec le service forfaits d’appels.

-   Les principales parties prenantes ont été identifiées.

-   Le contrat de licence requis pour le système téléphonique avec les services de plans d’appel est disponible et attribué au groupe d’utilisateurs dans l’ensemble de l’application.

-   La liste des sites d’entreprise et des groupes d’utilisateurs de l’étendue a été identifiée.

-   [Crédits de communication](what-are-communications-credits.md) (si nécessaire) ont été configurés pour votre organisation.

-   Le système téléphonique avec des paramètres de plans d’appel a été identifié et configuré.

-   Les paramètres du plan de numérotation client prenant en charge le système téléphonique avec des plans d’appel ont été identifiés, configurés et appliqués pour le groupe d’utilisateurs dans l’étendue.

-   Le système téléphonique avec des plans d’appel a été identifié et configuré pour ce groupe d’utilisateurs.

-   Système téléphonique avec des plans d’appels le respect des exigences de conformité a été identifié et configuré pour le groupe d’utilisateurs dans l’étendue.

### <a name="document-phone-system-with-calling-plans-test-case-passfail-status"></a>Système téléphonique de documents avec l’état de réussite ou d’échec du test de plans d’appel

Dans la mesure où les cas de test sont évalués pour les fonctionnalités d’administration et de système téléphonique utilisateur de teams dans l’objectif, effectuez le suivi des résultats de chaque cas de test pour refléter le statut de réussite/partielle/échec, ainsi que l’ID attribué au cas où un problème imprévu se produisait.

#### <a name="phone-system-with-calling-plans-test-case-status"></a>Système téléphonique avec état du cas de test plans d’appel

> [!TIP]
>   Vous trouverez ci-dessous un exemple de modèle d’état de cas de test que vous pouvez utiliser pour documenter des résultats de test pour révision lors de la prochaine réunion du Comité de direction lorsque vous décidez de l’intégration du système téléphonique aux services d’appels de plan dans le cadre de la phase pilote.

| Système téléphonique avec forfaits d’appels          |                              |                                                                                            |                           |                                                                            |
|------------------------------------------|------------------------------|--------------------------------------------------------------------------------------------|---------------------------|----------------------------------------------------------------------------|
| ID de cas de test                             | Titre du cas de test              | Description de cas de test                                                                      | Résumé des résultats de cas de test | ID de défaut affecté (le cas échéant)                                         |
| 1                                        | Placement d’appels RTC sortants. | Passez un appel sortant en composant un numéro national à 10 chiffres.                              |    &#9744;passe<br/>&#9744;partielle<br/> &#9744;Fail                   | Lorsqu’un utilisateur entre un numéro à quatre chiffres, l’appel passé au RTC échoue. |



<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/><br/>Points de décision</td><td><ul><li>Évaluez l’état de réussite et d’échec du test de haut niveau par site pour le système téléphonique avec les fonctionnalités d’appels de plan dans l’étendue.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Étapes suivantes</td><td><ul><li>Documentez les résultats de l’état de cas de test pour tous les cas de test remplis dans l’étendue.</li><li>Planifiez une réunion de Comité d’orientation pour passer en revue les résultats de synthèse des tests.</li><li>Présenter les résultats de l’état de cas de test au Comité d’orientation pour identifier les domaines qui nécessitent une correction.</li></ul></td></tr>
</table>


### <a name="document-phone-system-with-calling-plans-testing-result-summary"></a>Système téléphonique de documents avec les résultats du test plans d’appel

Après que tous les cas de test prenant en charge le système téléphonique avec les fonctionnalités de plans d’appel dans le champ d’application ont été remplis par site, documentez les résultats à réviser au cours d’une réunion de Comité d’orientation lorsque vous décidez de l’activation de votre système téléphonique avec les services de plans d’appel au pilote. polyphasé.

#### <a name="site-a-phone-system-with-calling-plans-test-case-summary-report"></a>Site A: système téléphonique avec le rapport de synthèse de cas de test de plans d’appel:

> [!TIP]
>   Vous trouverez ci-dessous un exemple de modèle de rapport de synthèse de test que vous pouvez consulter lors de la réunion du Comité de direction suivant lorsque vous décidez de l’intégration de votre système téléphonique aux services de plans d’appel dans le cadre de la phase pilote.


**Système téléphonique d’équipe avec des plans d’appels**

**Résumé**des résultats&nbsp; &nbsp; &nbsp; :&#9744;&nbsp; &nbsp; &nbsp; passe &#9744;&nbsp; &nbsp; partielle&nbsp; &#9744;Fail 

<table>
<tr><th colspan="2">Recommandations en matière de tests </th></tr>
<tr><td>DÉFINIR</td><td>DÉFINIR</td></tr>
<tr><th colspan="2">Test de lowlights  </th></tr><br/><tr><td><strong>Problème</strong>: TBD</td><td><strong>Correction:</strong> DÉFINIR</td></tr>
<tr><th colspan="2">Bloqueurs identifiés </td></tr>
<tr><td><strong>Bloqueur</strong>: TBD</td><td><strong>Correction</strong>: TBD</td></tr>
</table>


> [!TIP]
>   Pour faciliter les discussions ultérieures au cours de l’évaluation du Comité d’orientation final, vous pouvez utiliser la [matrice de résultats de test](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_21) mise à jour fournie par [MyAdvisor](https://myadvisor.fasttrack.microsoft.com/) pour documenter et mettre en évidence des zones supplémentaires qui nécessitent une correction.



<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/><br/>Points de décision</td><td><ul><li>Évaluez les résultats de synthèse de test de haut niveau par site pour le système téléphonique avec les fonctionnalités d’appels de plan dans l’étendue.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Étapes suivantes</td><td><ul><li>Documentez le rapport de synthèse de cas de test une fois tous les résultats de cas de test remplis.</li><li>Planifiez une réunion de Comité d’orientation pour passer en revue les résultats de synthèse des tests.</li><li>Présenter des résultats de synthèse de test au Comité de direction pour identifier les domaines qui nécessitent une correction.</li></ul></td></tr>
</table>



<a name="present-and-report-phone-system-with-calling-plans-test-findings"></a>Présenter et signaler un système téléphonique avec les résultats des tests d’appels
----------------------------------------------------------------

Une fois toutes les activités de test effectuées et les éventuels défauts ayant un impact sur le niveau faible, planifiez une réunion définitive de clôture avec les parties prenantes en matière de tests désignés. Dans la réunion, adresse:

-   Résumé de l’État

-   Mise en surbrillance/lowlights

-   Leçons apprises

-   Recommandation globale: passez à la phase pilote ou réévaluez les résultats des tests.

-   Résultats de matrice de test (ces valeurs doivent être entièrement documentées dans une annexe)

#### <a name="test-plan-deliverables"></a>Livrables du plan de test:

> [!TIP]
>   Vous trouverez ci-dessous un exemple de modèle de livrable de plan de test que vous pouvez utiliser pour documenter les critères requis pour la connexion et la sortie de la phase de test, ou pour suspendre les tests jusqu’à ce que tous les problèmes identifiés soient entièrement résolus.

| Résumé de l’État               | Recommandations/lowlights | Leçons apprises | Recommandations en matière de conclusion |
|------------------------------|----------------------|-----------------|------------------------|
| <ul><li>Taux de tests de cas de test de% TBD</li><li>Tous les tests réussis</li></ul> | DÉFINIR                  | DÉFINIR             | Passer au programme pilote       |

-   Tous les tests réussis


<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/><br/>Points de décision</td><td><ul><li>Déterminez le résumé de l’état des tests.</li><li>Identifiez les tests de mise en surbrillance et lowlights.</li><li>Identifiez les leçons tirées.</li><li>Déterminez les actions de correction qui resteront, le cas échéant.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Étapes suivantes</td><td><ul><li>Vous pouvez inclure les résultats de synthèse du test de document comme suit:<ul><li>Résumé de l’État</li><li>Recommandations/lowlights</li><li>Leçons apprises</li></ul></li><li>Planifiez une réunion finale de Commission pour examiner les résultats des tests.</li><li>Présenter des résultats de synthèse lors d’une étude du Comité d’orientation afin d’obtenir une signature finale permettant de sortir de la phase de test.</li></ul></td></tr>
</table>
