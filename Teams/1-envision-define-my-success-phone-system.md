---
title: Définir la réussite dans le système téléphonique avec des Plans d’appel - Teams Microsoft
author: rmw2890
ms.author: MyAdvisor
manager: lehewe
ms.date: 03/13/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: Mesurer les résultats de votre système téléphonique avec appel de Plans de déploiement et vérifiez que vous avez obtenu les résultats escomptés.
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9883fb04c70d07a0249d2390b894bba3d491ec04
ms.sourcegitcommit: b985035b91ebd7ceff8d50e9e0fa9aa6ff971f3a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/15/2018
---
# <a name="define-my-success"></a>Définir ma réussite

## <a name="introduction"></a>Introduction

Ce contenu fournit une vue d’ensemble de la configuration requise pour la définition correcte de la réussite du déploiement du système téléphonique avec appel de Plans pour votre organisation. En définissant correctement votre réussite, vous pouvez mesurer les résultats de la mesure que vous avancez dans votre déploiement et vérifier que les résultats que vous obtenez sont les résultats que vous souhaitez.

<!--ENDOFSECTION-->

## <a name="define-business-use-cases-for-phone-system-with-calling-plans"></a>Définir les cas d'utilisation des systèmes téléphoniques avec forfaits d'appels

Organisations peuvent utiliser le système téléphonique avec des Plans d’appel pour moderniser leur environnement de travail en permettant aux utilisateurs de faire professionnelles des appels téléphoniques à partir de leurs ordinateurs et les périphériques mobiles.

Modernisation de l’espace de travail peut être la partie de n’importe quel nombre de scénarios, une implémentation basée sur l’activité de travail, déplacez un bureau principal, un ajustement à la sortie mise à jour office, déclassement d’une solutions d’exchange (PBX) hérités branche privé, la conclusion d’une public commuté contrat de fournisseur de service de réseau (RTPC) et ainsi de suite.

Dans un premier temps, les parties prenantes du projet de base est nécessaire définir des cas d’usage professionnel qui prennent en charge de la mise en oeuvre du système de téléphone avec des Plans d’appel.

Exemples d’utilisation sont destinés à définir et documenter les résultats attendus et mesurables et incluent les éléments suivants :

-   Description du processus professionnel en cours

-   Défis posés par le processus de gestion existant

-   Comment la technologie peut aider à surmonter ces difficultés

-   Les résultats pour l'entreprise attendus et mesurables si ces difficultés sont surmontées.

> [!TIP]
> Voici un exemple d'une étude de cas d'entreprise réalisée :
>|         |
>|---------|
>|**Description du processus d’entreprise actuel**<br>La configuration standard des espaces de travail Contoso inclut un numéro de téléphone pour chaque bureau. Chaque employé a reçu un intérieur directe (DID) numéro de téléphone. Les téléphones de bureau sont connectés à un système PBX et connectées au RTC via un tronc de session initiation protocol (SIP). Les employés peuvent uniquement passer et recevoir des appels sur le téléphone de bureau qui leur a été attribué.|
>|**Difficultés par rapport au processus d’entreprise existant**<br>Analyse de l’utilisation des téléphones de bureau montre que 10 % seulement des téléphones de bureau sont activement utilisé, avec les autres configurés pour transférer les appels à des téléphones portables ou à anneau simultanément à des téléphones mobiles. La maintenance système PBX existant et des téléphones de bureau associés contribue à 20 % du coût de service de téléphonie mensuel de Contoso.|
>|**Comment la technologie peut surmonter ces difficultés**<br>Système de téléphone avec des Plans d’appel permettra ordinateur personnel de l’utilisateur recevoir et effectuer des appels téléphoniques via le réseau de données grâce à l’application native Teams de Microsoft. Cela supprime la nécessité de déployer et de gérer des téléphones de bureau et ouvre la possibilité de retirer du système PBX existant, car le service de téléphone peut être remis via le nuage sur le réseau avec aucune dépendance sur un système téléphonique traditionnel.|
>|**Résultats de l’entreprise attendus et mesurables**<br>Suppression des besoins de maintenance et de mise hors service de PBX hérité et des téléphones de bureau fournira une réduction de 20 % de téléphonie mensuel des frais de service. Les systèmes téléphoniques avec forfaits d'appels simplifient les espaces de travail de bureau et permettent à Contoso de développer ses opérations, en établissant de nouveaux bureaux avec des coûts de téléphonie initiaux minimes.|

En plus de définir votre entreprise permet de cas, pour définir les limites du projet que vous devez viser clarté lecteur autour de :

En plus de définir votre entreprise permet de cas, pour définir les limites du projet que vous devez viser clarté lecteur autour de :

-   **D’organisation étendue :** La mise en oeuvre du système de téléphone avec des Plans d’appel peut englober l’ensemble de l’organisation ou des divisions spécifiques.

-   **Chronologie du projet :** Le scénario spécifique, que le projet s’exécute.

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Points de décision|<ul><li>Quels sont les exemples d’utilisation de l’activité pour système de téléphone avec l’appel de Plans vous pouvez identifier dans votre organisation ?</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Étapes suivantes|<ul><li>Documenter tous les exemples d’utilisation pour système de téléphone avec l’appel de Plans pour votre organisation.</li></ul>|

<!--ENDOFSECTION-->

## <a name="identify-key-stakeholders"></a>Identifier les parties prenantes clés

Les cas d’usage professionnel définis à l’étape précédente incluent une portée organisationnelle pour le système de téléphone avec la mise en oeuvre des Plans d’appel. Sur cette base, vous pouvez terminer la matrice complète avec les parties intéressées pour inclure les bonnes personnes impliquer dans le projet.

> [!TIP]
> Voici un exemple de modèle de matrice des parties prenantes que vous pouvez utiliser pour documenter les parties prenantes intégrées dans le projet :
>|Rôle  |Description  |Nom, informations de contact, emplacement  |
>|---------|---------|---------|
>|Sponsor exécutif du projet|<ul><li>Prendre l’autorité ultime et les responsabilités du projet et la livraison sur les objectifs du projet.</li><li>Aider à résoudre les problèmes transmis par le responsable de projet.</li><li>Parrainent des communications au sein de la société sur les objectifs du projet.</li><li>Prendre des décisions stratégiques clées.</li><li>Garantir la disponibilité des ressources nécessaires et de budget.</li><li>Conduire tous les trimestres des analyses d’activité (QBRs).</li><li>Le lecteur dans l’achat et la prise en charge de la prise de conscience de la campagne.</li><li>Servir le commanditaire du projet pour le déploiement de programme.</li></ul>|TBA|
>|Chef de projet|<ul><li>Gérer et responsable de l’équipe de projet.</li><li>Coordonnées des partenaires et des équipes de travail dans le projet.</li><li>Être responsable de la création et des plans de gestion de projet afin de répondre aux résultats clés trimestriels.</li><li>Résoudre les problèmes de fonctionnel.</li><li>Fournir des mises à jour régulières pour les sponsors du projet.</li><li>Incorporer des aspects d’adoption dans le plan de projet de tous les accès.</li><li>Prospect Business mensuels et les revues opérationnelles (MBR), contribuent à QBRs.</li></ul>|TBA|
>|Chef/architecte de la collaboration|<ul><li>Exécution de la stratégie de collaboration définie par les dirigeants de l’entreprise.</li><li>Analyser et choisir les produits de collaboration qui répondent aux objectifs commerciaux de la société.</li><li>Concevoir des opérations pour les produits de collaboration.</li><li>Définir l’opération et prend en charge les modèles.</li><li>Contribuer à des analyses d’activité mensuels et trimestriels.</li></ul>|TBA|
>|Consultant|<ul><li>Responsable des services de configuration</li><li>Contribuer à l’architecture globale de la solution.</li></ul>|TBA|
>|Gestionnaire de projets|<ul><li>Développer et gérer le plan de projet.</li><li>Gérer les livrables dans le plan de projet et le budget du projet.</li><li>Enregistrer et de gérer les problèmes du projet, y compris les procédures d’escalade.</li><li>Effectuer des appels quotidienne hebdomadaires.</li><li>Assurer la liaison avec et fournissent des mises à jour aux sponsors exécutifs de projet.</li><li>Travailler avec l’architecte pour définir l’approche et la communication des plans de gestion modification.</li></ul>|TBA|
>|Spécialiste en gestion des changements/adoption|<ul><li>Fournir l’entrée lors de la phase de découverte à l’adoption et le processus de formation.</li><li>Participer à l’atelier de stratégie d’adoption.</li><li>Développer et prendre la responsabilité de la stratégie d’adoption.</li><li>Développer et exécuter le plan de communication.</li><li>Proposer des formations pour les utilisateurs.</li><li>Recueillir les commentaires et mener les enquêtes.</li></ul>|TBA|
>|Directeur de réseau|<ul><li>Fournir l’entrée lors de la phase de découverte dans la conception du réseau.</li><li>Participer à la planification au cours de l’atelier de phase Envision.</li><li>Coordonner le travail de l’équipe de mise en réseau au cours de l’exécution du projet.</li></ul>|TBA|
>|Directeur de la sécurité|<ul><li>Fournir l’entrée lors de la phase de découverte dans le processus et la conception de la sécurité.</li><li>Participer à la planification au cours de l’atelier de phase Envision.</li><li>Coordonner le travail de l’équipe de sécurité pendant l’exécution du projet.</li></ul>|TBA|
>|Directeur de la téléphonie|<ul><li>Fournir l’entrée lors de la phase de découverte dans la conception de la téléphonie.</li><li>Participer à la planification au cours de l’atelier de phase Envision.</li><li>Coordonner le travail de l’équipe de téléphonie lors de l’exécution du projet.</li></ul>|TBA|
>|Directeur de bureau|<ul><li>Fournir une entrée pendant la phase de découverte dans les clients et des mises à jour.</li><li>Participer à la planification au cours de l’atelier Envision.</li><li>Coordonner le travail de l’équipe de bureau lors de l’exécution du projet.</li></ul>|TBA|
>|Responsable du support|<ul><li>Fournir une entrée pendant la phase de découverte dans l’exploitation et la prise en charge des modèles.</li><li>Participer à la planification au cours de l’atelier de phase Envision.</li><li>Participer au modèle de prise en charge de planification.</li><li>Coordonnez le travail des équipes de support et des ressources au cours de l’exécution du projet.</li></ul>|TBA|
>|Représentants d'unité commerciale|<ul><li>Contribuer aux guides de l’utilisateur l’adoption et de matériaux.</li><li>Contribuent à et consulter des exemples d’utilisation.</li></ul>|TBA|
>|Directeur du déploiement|<ul><li>Assurez-vous que les conditions préalables au déploiement sont remplies.</li><li>Engager les ressources d’être impliqués dans les activités de la phase intégré.</li><li>Participer aux réunions pour examiner et établir des rapports sur l’état du déploiement.</li></ul>|TBA|
>|Administrateurs informatiques|<ul><li>Aider à la planification de test et l’exécution. Ce rôle est pour les professionnels de l’informatique.</li></ul>|TBA|
>|Propriétaire de service|<ul><li>Être responsable du fonctionnement du système téléphonique avec les Plans d’appel de service, tout.</li><li>Propriétaire du système téléphonique avec les Plans d’appel de service.</li></ul>|TBA|
>|Ambassadeurs de la qualité|<ul><li>Commentaires sur la qualité, la fiabilité et les utilisateurs du lecteur.</li><li>Identifier les tendances de qualité et disque correctives avec les équipes respectives.</li><li>Rapport par le comité de direction sur le marché.</li><li>Rapport sur la qualité, la fiabilité et utilisateur sentiment et taux de mes appels Net promoteur Score.</li></ul>|TBA|

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Points de décision|<ul><li>Qui remplit chaque rôle des parties prenantes clés de votre organisation ?</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Étapes suivantes|<ul><li>Documenter toutes les parties prenantes et communiquer les responsabilités et les attentes du rôle à chaque personne assignée.</li></ul>|

<!--ENDOFSECTION-->

## <a name="define-okrs-ksis-and-risks"></a>Définition des risques, des KSIs et des OKRs

Avec les parties prenantes du projet assemblés, vous pouvez traduire des exemples d’utilisation, la portée d’organisation et des chronologies de projet dans les objectifs et les résultats clés (OKRs) et les mesures de réussite du projet peuvent être définis comme une liste d’indicateurs de réussite clés (KSIs).

Pleine participation des parties prenantes du projet dans la définition de OKRs et KSIs est essentielle pour garantir leur donne un sentiment d’appartenance et alignement ces mesures de réussite aux exigences de l’entreprise.

OKRs contiennent les objectifs que vous définissez au début du projet, et que vous définissez des résultats mesurables clés sur une base trimestrielle. Vous examinez des résultats clés tous les mois pour effectuer le suivi de l’état de l’ensemble du projet, et, en fonction de la progression — vous ajustez les plans trimestrielles en fonction des besoins.

> [!TIP]
> Un exemple d'objectifs et résultats clés appropriés à l'implémentation d'un système téléphonique avec forfaits d'appels peut être référencé ci-après :
><br>
>
>**Vision : augmenter la productivité an optimisant les investissements dans Office 365**
>|Objectifs  |Résultats clés  |Action  |
>|---------|---------|---------|
>|Déployer les systèmes téléphoniques avec forfaits d'appels dans les filiales européennes d'ici la fin de l'exercice fiscal 2018|T3, 2018 : Déployer les systèmes téléphoniques avec forfaits d'appels dans les bureaux londoniens|Planifier<ul><li>Créer un plan de réussite</li><li>Créer un plan d’implémentation technique détaillé</li></ul><p>Intégrer<ul><li>Exécuter le plan de réussite</li><li>Exécuter le plan d’implémentation technique</li></ul>|
>|Désactiver le système PBX hérité dans les bureaux londoniens d'ici la fin de l'exercice fiscal 2018|T4, 2018 : Désactiver le système PBX hérité dans les bureaux londoniens|Générer une valeur ajoutée<ul><li>Favoriser l’implication des utilisateurs et encourager l'adoption</li><li>Gérer et préparer le changement</li><li>Mesurer, partager la réussite et retravailler</li>|

KSIs mesurer la qualité et la réussite des résultats et de compléter la nature binaire de OKRs (réalisés ou pas) en détaillant les résultats de la bonne ou mauvaises.

Lors de la définition de KSIs, nous vous conseillons d’utiliser des critères (SMART) « spécifiques, mesurables, être assignés, réalistes, liées au temps » :

-   Spécifiques : cibler une zone spécifique d’amélioration

-   Quantifier mesurable : ou suggestions d’au moins un indicateur de progression

-   Être assigné : spécifier qui fera

-   Realistic : les résultats peuvent réaliste l’état atteindre, compte tenu des ressources disponibles

-   Temporelle : spécifiez si les résultats peuvent être obtenus

> [!TIP]
> Voici un exemple d'indicateur de succès clé approprié à ce projet :
>|Type  |Questions sur l'indicateur de succès clé et critères  |Comment les mesurer  |Critères de réussite  |Mesurés  |Responsable  |
>|---------|---------|---------|---------|---------|---------|
>|Utilisation/adoption|La qualité des appels est égale ou meilleure qu’avec la solution précédente|Enquête|80 % des utilisateurs sont d’accord ou tout à fait d’accord|Après activation et chaque trimestre|Équipe responsable des technologies de l’information|
>|Utilisation/adoption|Microsoft Teams a facilité le processus de communication|Enquête|80 % des utilisateurs sont d’accord ou tout à fait d’accord|Après activation et chaque trimestre|Équipe responsable de la gestion des changements|
>|Utilisation/adoption|Les utilisateurs utilisent activement la solution|Rapports Office 365, tableau de bord de la qualité des appels|80 % des utilisateurs l’utilisent quotidiennement|Chaque jour|Équipe responsable de la gestion des changements|
>|Utilisation/qualité|Le pourcentage d’appels/conférences médiocres doit être minimal|Tableau de bord de la qualité des appels|< 5 % d'appels médiocres par mois|Chaque jour|Équipe responsable des technologies de l’information|
>|Utilisation/support|Je sais comment obtenir le support technique|Enquête|90% des utilisateurs sont d’accord ou tout à fait d’accord|Après activation et chaque trimestre|Équipe responsable de la gestion des changements|
>|Utilisation/support|Je suis satisfait de la qualité du support technique|Enquête|80 % des utilisateurs sont d’accord ou tout à fait d’accord|Après chaque incident|Équipe responsable des technologies de l’information|
>|Financier|Réduction du nombre de minutes de conférence héritée|Système financier|Atteindre le retour sur investissement défini|Basé sur le retour sur investissement|Équipe responsable de la gestion des changements|

Vous devez identifier les risques d’entreprise dans le cadre de cette activité et définir un plan d’atténuation pour chaque risque identifié. Capturer ces informations dans un registre des risques.

> [!TIP]
> Votre Registre des risques peut être documentée dans l’exemple ci-dessous :
>|Risque  |Probabilité  |Impact  |Global  |Plan d’atténuation  |
>|---------|---------|---------|---------|---------|
>|Une fusion prochaine ajoutera jusqu’à 1000 personnes|Élevée|Haut|Haut|<ul><li>Pour les sociétés fusionnées, créer un OKR distincte qui s’appliquent à leurs propres phases du projet (Envision, Onboard, valeur de lecteur)</li><li>N’incluez pas ces OKRs dans OKRs existants</li></ul>|
>|Le transfert des numéros de téléphone retardera la réalisation du projet|Élevée|Haut|Haut|<ul><li>Préparer toutes les informations nécessaires pour prendre en charge le numéro de téléphone du portage à l’avance (service enregistrement de client, détails de la lettre d’autorisation de facturation)</li><li>Ajuster la chronologie du projet pour tenir compte de la fréquence d’exécution de portage numérique de téléphone</li><li>Utiliser les numéros de téléphone provisoires avec la manipulation de l'ID de l'appelant</li></ul>|
>|Reconception du réseau planifiée|Élevée|Moyen|Moyen|<ul><li>Avant d’implémenter des équipes comme une plate-forme de collaboration et de communications modernes, procéder à une évaluation de la disponibilité du réseau pour les sites dans la portée du projet</li></ul>|

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Points de décision|<ul><li>Quels sont les OKRs et les KSIs de votre organisation ?</li><li>Quels risques vous ont identifié un approprié à l’implémentation des services de conférence Audio de votre organisation ? Quels sont les plans d’atténuation des risques identifiés ?</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Étapes suivantes|<ul><li>Les OKRs, KSIs, de documents et établir le casier de risques.</li></ul>|

<!--ENDOFSECTION-->

## <a name="establish-a-steering-committee"></a>Établir un comité de direction

Un comité de direction est un groupe régissant les principales parties prenantes et les chefs de projet qui ont été introduites pour guider un projet ou programme vers ses résultats métiers bien définis. Le comité de direction n’est pas directement responsable de *la* que livraison du projet, mais plutôt *le* que projet fournit à l’entreprise.

Chaque projet nécessite un accord sur la vision et la charte. La vision pour fournir les résultats de votre choix dans le projet, doit être clairement définie, et il doit être surveillés et mis à jour. Cela devient la responsabilité du comité directeur : lecteur des décisions, informer, fournir une supervision stratégique, comme les défenseurs de l’organisation pour les initiatives du projet, et, lorsque cela est nécessaire : supprimer les bloqueurs de fenêtres publicitaires.

Votre organisation doit mettre la pensée significative dans la constitution du comité directeur. Le comité doit s’assurer que le projet atteint les objectifs que vous avez définies pour la modification de l’organisation, répondre aux périodiquement pour discuter de l’impulsion en cours du projet, de conduite et aider à débloquer les obstacles rencontrés le long de la moyen.

Le comité doit définir sa charte pour inclure certains objectifs clés :

-   Conserver un alignement fort entre l’équipe de projet et le soutien de la direction ou le leadership exécutif.

-   Fournir un aperçu de l’état du projet pour le soutien de la direction ou la direction et leadership.

-   Autoriser le soutien de la direction ou de l’équipe de direction et leadership définir l’orientation et d’entrée pour le projet et vous assurer qu’il s’aligne avec commandes changent les objectifs de l’entreprise, en ajustant les plans de projet, les résultats de clé objectifs (OKRs) et autres activités de projet.

Le comité de direction répond à intervalles réguliers tout au long de la durée de vie d’un projet pour garantir l’alignement entre la position de leader d’organisation et l’équipe de projet. Cette réunion critique garantit que la direction du projet est la prise en charge complète du leadership et incorpore des commentaires fournis par la position de leader dans le projet à la réussite du lecteur. Le comité utilise ces réunions de dans l’état du projet et à comprendre :

-   Accord sur les résultats d’entreprise qui s’alignent sur l’étude de cas, et pour que le projet pilote vers la livraison de ces résultats.

-   Vérifier et approuver le projet pour l’exactitude et la conformité avec l’étude de cas.

-   Examinez et vérifiez les modifications apportées à l’étude de cas qui pourrait affecter les résultats définis.

-   Prendre des décisions stratégiques en ce qui concerne la définition de priorités des livrables du projet et d’approuver les livrables intermédiaires.

-   Identifier, gérer et atténuer les intervalles, les risques et les problèmes où influence supplémentaire est requise par le comité.

-   Recueillir la prise en charge à partir du soutien de la direction ou l’équipe de direction et leadership pour les problèmes nécessitant une escalade, définition des priorités et résoudre tous les conflits entre les centres de profit des parties prenantes. 

-   Fournir une évaluation formelle et des recommandations à la direction et leadership, le comité consultatif des modifications, ou autres business et informatique parties prenantes, le cas échéant.

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Points de décision|<ul><li>Décider si un comité de direction est nécessaire pour votre organisation.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Étapes suivantes|<ul><li>Identifier les membres du comité directeur.</li><li>Planifier des réunions du comité de direction.</li><li>Préparation des réunions du comité de direction.</li><li>Réunions du comité de direction.</li><li>Prendre des mesures en fonction de l’entrée de réunion du comité de direction.</li></ul>|

Vous trouverez des conseils supplémentaires sur l’utilisation d’un comité de direction approprié dans le comité de direction guide disponible [ici](https://docs.microsoft.com/MicrosoftTeams/envision-steering-committee-complete-guide).

<!--ENDOFSECTION-->