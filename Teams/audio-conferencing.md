---
title: Guide pratique pour l’audioconférence dans Microsoft Teams
author: arachmanGitHub
ms.author: MyAdvisor
manager: serdars
ms.date: 03/12/2018
ms.topic: article
ms.service: msteams
ms.reviewer: MyAdvisor, lolaj
description: Guide pratique pour la planification, le déploiement et la gestion de l’audioconférence dans Microsoft Teams avec l'infrastructure Planifier (Programmer), Intégrer (Fournir), Générer une valeur ajoutée (Utiliser).
localization_priority: Normal
search.appverid: MET150
appliesto:
- Microsoft Teams
redirect_url: https://docs.microsoft.com/MicrosoftTeams/cloud-voice-deployment
ms.openlocfilehash: a3ce04974eec062360bb6b0663255f079e097554
ms.sourcegitcommit: 8a6bf02958436fcdeed336f09079bd3827e2fccb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/12/2018
ms.locfileid: "26283065"
---
<a name="practical-guidance-for-audio-conferencing-in-microsoft-teams"></a>Guide pratique pour l’audioconférence dans Microsoft Teams
============================================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

L’audioconférence dans Office 365 permet aux participants de rejoindre vos réunions Teams depuis n’importe quel téléphone.

Voici les avantages de [l’audioconférence](https://go.microsoft.com/fwlink/?linkid=858992) dans Office 365.

Ce guide pratique vous accédez via le client Office 365 FastTrack framework voyage et ses trois phases, prévoir, intégrée et valeur lecteur, pour vous aider à planifier, fournir et utiliser une implémentation de conférence Audio vers fructueuse résultats commerciaux.

> [!TIP]
> Dans ce guide pratique, nous fournissons des exemples de résultats pour chaque activité et theme principal. Les exemples fournis tout au long de ce document sont intégrés aux légendes des astuces et peuvent être utilisés comme modèles. « TBA » (à ajouter) est affiché en regard des informations que vous devez remplir dans le cadre de votre processus de planification.

Concevoir <a name="Envision_AudioConferencing"> </a>
=========

La phase Planifier fournit les bases du parcours du client Office 365 et s’applique à toutes les charges de travail comme l’audioconférence.

Dans cette phase, les objectifs de l’entreprise sont déterminés, avec les parties prenantes impliquées dans le projet réunies, pour fournir par la suite :

-   Un plan de réussite général contenant des cas d'utilisation, des parties prenantes clés, des objectifs et des résultats clés, des indicateurs de succès clés, des risques, une évaluation de l'environnement, la préparation à l'adoption et un plan opérationnel

-  Un plan d’implémentation technique de l’audioconférence détaillé pour parvenir à l’état final souhaité.

<a name="define-business-use-cases-for-audio-conferencing"></a>Définir les cas d'utilisation professionnelle de l'audioconférence
------------------------------------------------

L’audioconférence fournit aux organisations des points d’entrée supplémentaires à toutes les réunions (ponctuelles et planifiées) en permettant aux participants de les rejoindre via PSTN (réseau téléphonique commuté public) en composant des numéros de téléphone de ligne fixe traditionnels, PBX ou de mobile.

Cela est utile lorsque la personne qui a organisé la réunion ou les participants ne se trouvent pas devant un ordinateur, ou lorsque les connexions de données sont indisponibles ou non fiables pour prendre en charge des communications vocales - par exemple lorsque les participants se trouvent dans une zone avec une couverture de données mobiles inégale, ou s’ils sont connectés à un service Wi-Fi gratuit public avec une bande passante limitée, ou lorsqu'ils préfèrent rejoindre la réunion à l’aide d'un point de terminaison de téléphonie qui leur est facilement accessible.

Dans cette étape, les principales parties prenantes impliquées dans le projet définiront des cas d’utilisation professionnelle qui prennent en charge l’implémentation de l’audioconférence.

Les cas d’utilisation professionnelle sont destinés à définir et documenter des résultats de l’entreprise attendus et mesurables, et incluent les éléments suivants :

-   Description du processus d’entreprise actuel
-   Difficultés par rapport au processus d'entreprise existant définies
-   Comment la technologie peut aider à surmonter ces difficultés
-   Les résultats pour l'entreprise attendus et mesurables si ces difficultés sont surmontées.

> [!TIP]
> Voici un exemple d'une étude de cas d'entreprise réalisée :
> 
> |         |
> |---------|
> |**Description du processus d’entreprise actuel**<br>Contoso fait actuellement appel à des services de conférence PSTN fournis par le fournisseur de téléphonie local titulaire facturés par minutes de réunion pour les réunions internes et celles impliquant des parties externes.|
> |**Difficultés par rapport au processus d’entreprise existant**<br>Contoso dépense environ 1 million de dollars par an pour le service de conférence PSTN actuel, les réunions internes représentant 75 % du coût.<br>L’utilisation de points de terminaison de téléphonie traditionnels pour participer aux réunions hébergées par le service de conférence PSTN ne correspond pas au plan pour que l’organisation adopte Teams comme plate-forme de communication et de collaboration moderne.|
> |**Comment la technologie peut surmonter ces difficultés**<br>Avec l’adoption de Microsoft Teams comme plate-forme de communication et de collaboration moderne, les utilisateurs internes devraient principalement rejoindre les réunions en utilisant leurs PC équipés de casques optimisés et de dispositifs de salle de réunion. Le service d’audioconférence sera disponible pour prendre en charge les participants externes ou les situations où l’utilisation de l’audio sur PC n’est pas avantageuse pour les participants internes.|
> |**Résultats de l’entreprise attendus et mesurables**<br>Le passage à Teams comme plate-forme de communication et de collaboration moderne, combinée au service d’audioconférence, réduira considérablement le coût de la prestation du service de conférence PSTN, Contoso devant dépenser seulement 20 % environ du coût annuel du service de conférence PSTN existant.|

En plus de définir vos cas d'utilisation, lorsque vous passez à l’étape suivante de la phase Planifier, vous devez également clarifier les éléments suivants :
- portée organisationnelle et
- planning de projet

<a name="identify-key-stakeholders"></a>Identifier les parties prenantes clés
-------------------------

Les cas d’utilisation professionnelle définis à l’étape précédente incluront la portée organisationnelle de l’implémentation de l’audioconférence et, de ce fait, la matrice complète des parties prenantes peut être complétée pour inclure les personnes adéquates à inclure dans le projet.

> [!TIP]
> Voici un exemple de modèle de matrice des parties prenantes que vous pouvez utiliser pour documenter les parties prenantes intégrées dans le projet :
> 
> |                 Rôle                  |                                                                                                                                                                                                                                                                Description                                                                                                                                                                                                                                                                 | Nom, informations de contact, emplacement |
> |---------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------|
> |       Sponsor exécutif du projet       | <ul><li>Autorité et responsabilité ultimes du projet et réalisation des objectifs du projet</li><li>Aide à résoudre les problèmes transmis par le chef de projet</li><li>Organise la communication au sein de l’entreprise au sujet des objectifs du projet</li><li>Chargé de prendre les décisions stratégiques clés</li><li>Chargé de la disponibilité des ressources nécessaires et du budget</li><li>Principale évaluation trimestrielle des activités</li><li>Adhésion et appui à la campagne de sensibilisation</li><li>Est le sponsor du projet pour le lancement du programme</li></ul> |                 TBA                 |
> |             Chef de projet              |                   <ul><li>Gestion et direction de l’équipe du projet</li><li>Coordonne les partenaires et les équipes qui participent au projet</li><li>Responsable de la création et de la gestion des plans du projet pour obtenir les principaux résultats trimestriels</li><li>Résoudre les problèmes fonctionnels croisés</li><li>Fournir des informations actualisées périodiques aux sponsors du projet</li><li>Incorporer les aspects relatifs à l’adoption dans l’ensemble du plan du projet</li><li>Diriger les évaluations mensuelles des activités et opérationnelles, contribuer aux évaluations trimestrielles des activités</li></ul>                   |                 TBA                 |
> |     Chef/architecte de la collaboration      |                                                                       <ul><li>Chargé de l’exécution de la stratégie de collaboration définie par la direction de l’entreprise</li><li>Analyse et choisit les produits de collaboration pour l’entreprise permettant d’atteindre les objectifs professionnels</li><li>Chargé de la conception des opérations des produits de collaboration</li><li>Définit un modèle d'opération et de prise en charge</li><li>Contribue aux évaluations mensuelles et trimestrielles des activités</li><ul>                                                                        |                 TBA                 |
> |              Consultant               |                                                                                                                                                                                                               <ul><li>Chargé des services de configuration</li><li>Contribue à l'architecture de solutions globale</li></ul>                                                                                                                                                                                                                |                 TBA                 |
> |            Gestionnaire de projets            |                                                      <ul><li>Élaborer et tenir à jour les plans de projet</li><li>Gérer les livrables du projet conformément au plan et au budget du projet</li><li>Noter et gérer les problèmes liés au projet, y compris les remontées</li><li>Effectuer des appels d'intervention hebdomadaires</li><li>Assurer la liaison avec, et fournir des informations actualisées aux sponsors exécutifs du projet</li><li>Collaborer avec l’architecte pour définir le mode de gestion des changements et les plans de communication</li></ul>                                                       |                 TBA                 |
> | Spécialiste en gestion des changements/adoption |                                                                                       <ul><li>Formuler des recommandations lors de la phase de découverte sur les processus d’adoption et de formation</li><li>Participer à l’atelier sur la stratégie d’adoption</li><li>Développer et être responsable de la stratégie d’adoption</li><li>Développer et exécuter le plan de communication</li><li>Chargé de dispenser des formations aux utilisateurs finaux</li><li>Recueillir les commentaires et réaliser des enquêtes</li></ul>                                                                                        |                 TBA                 |
> |             Directeur de réseau              |                                                                                                                                                              <ul><li>Formuler des recommandations lors de la phase de découverte sur la conception du réseau</li><li>Participer à la planification lors de l’atelier sur la planification</li><li>Coordonner le travail de l’équipe de mise en réseau lors de l’exécution du projet</li></ul>                                                                                                                                                               |                 TBA                 |
> |             Directeur de la sécurité             |                                                                                                                                                        <ul><li>Formuler des recommandations lors de la phase de découverte sur les processus et la conception de la sécurité</li><li>Participer à la planification lors de l’atelier sur la planification</li><li>Coordonner le travail de l’équipe chargée de la sécurité lors de l’exécution du projet</li></ul>                                                                                                                                                        |                 TBA                 |
> |            Directeur de la téléphonie             |                                                                                                                                                              <ul><li>Formuler des recommandations lors de la phase de découverte sur la conception de la téléphonie</li><li>Participer à la planification lors de l’atelier sur la planification</li><li>Coordonner le travail de l’équipe chargée de la téléphonie lors de l’exécution du projet</li></ul>                                                                                                                                                              |                 TBA                 |
> |             Directeur de bureau              |                                                                                                                                                          <ul><li>Formuler des recommandations lors de la phase de découverte sur les clients et le processus de mise à jour</li><li>Participer à la planification lors de l’atelier sur la planification</li><li>Coordonner le travail de l’équipe chargée des bureaux lors de l’exécution du projet</li></ul>                                                                                                                                                          |                 TBA                 |
> |        Responsable du support         |                                                                                                                          <ul><li>Formuler des recommandations lors de la phase de découverte sur le modèle opérationnel et de prise en charge</li><li>Participer à la planification lors de l’atelier sur la planification</li><li>Participer à la planification du modèle de prise en charge</li><li>Coordonner le travail de l’équipe chargée de la prise en charge/des ressources lors de l’exécution du projet</li></ul>                                                                                                                          |                 TBA                 |
> |     Représentants d'unité commerciale     |                                                                                                                                                                                                      <ul><li>Contribuer aux guides et supports d’adoption basés sur les utilisateurs finaux</li><li>Évaluer et contribuer aux cas d’utilisation professionnelle</li></ul>                                                                                                                                                                                                      |                 TBA                 |
> |            Directeur du déploiement            |                                                                                                                                                           <ul><li>S’assurer que les conditions préalables au déploiement sont remplies</li><li>Impliquer des ressources des clients dans l’affectation, la préparation et le déploiement des activités de l’étape</li><li>Participer à des réunions pour évaluer l’état de préparation et du déploiement</li></ul>                                                                                                                                                            |                 TBA                 |
> |               Administrateurs informatiques               |                                                                                                                                                                                                                           <ul><li>Spécialistes des technologies de l'information pour aider à la planification et l’exécution des tests</li></ul>                                                                                                                                                                                                                            |                 TBA                 |
> |             Propriétaire de service             |                                                                                                                                                                                                  <ul><li>Responsable du fonctionnement de l’ensemble du service d’audioconférence</li><li>Propriétaire du service d’audioconférence</li></ul>                                                                                                                                                                                                   |                 TBA                 |
> |           Ambassadeurs de la qualité           |                                                                                                      <ul><li>Génère des commentaires sur la qualité, la fiabilité et des utilisateurs</li><li>Identifie les tendances en matière de qualité et génère les corrections avec les équipes respectives</li><li>Fait des rapports par le biais du comité de pilotage à la direction</li><li>Fait des rapports sur la qualité, la fiabilité et l’opinion des utilisateurs par l’intermédiaire de Rate My Call et de Net Promoter Score</li></ul>                                                                                                       |                 TBA                 |

<a name="define-objectives-and-key-results-key-success-indicators-and-risks"></a>Définir les objectifs et les résultats clés, les indicateurs de succès clés et les risques
--------------------------------------------------------------------

Avec les parties prenantes impliquées dans le projet réunies, les cas d’utilisation professionnelle, la portée organisationnelle et le planning du projet peuvent être transposés en objectifs et résultats clés et les mesures de réussite du projet peuvent être définies dans une liste d’indicateurs de succès clés.

L’entière participation des parties prenantes impliquées dans le projet lors de la définition des objectifs et résultats clés et des indicateurs de succès clés garantira le sentiment d’appartenance et qu'ils correspondent aux besoins de l’entreprise en matière d’organisation.

Les objectifs et résultats clés contiennent la liste des objectifs définis au début du projet, les résultats clés mesurables étant définis chaque trimestre. Les résultats clés sont vérifiés chaque mois pour effectuer le suivi du projet global et, en fonction de l’évolution, les plans trimestriels peuvent être adaptés lorsque cela est nécessaire.

> [!TIP]
> Un exemple d'objectifs et résultats clés appropriés à l'implémentation de l’audioconférence peut être référencé ci-après :
> <br>
> 
> **Vision : augmenter la productivité an optimisant les investissements dans Office 365**
> 
> |Objectifs  |Résultats clés  |Action  |
> |---------|---------|---------|
> |Déployer l’audioconférence dans Teams d’ici la fin de l’exercice fiscal 2018|T1 de l’exercice 2018 : déployer l’audioconférence dans Teams globalement|Concevoir<ul><li>Créer un plan de réussite</li><li>Créer un plan d’implémentation technique détaillé</li></ul><p>Intégrer<ul><li>Exécuter le plan de réussite</li><li>Exécuter le plan d’implémentation technique</li></ul>|
> |Désactiver l’ancien service de conférence PSTN à l’échelle globale d'ici la fin de l’exercice fiscal 2018|T2 de l’exercice 2018 : désactiver l’ancien service de conférence PSTN à l’échelle globale|Générer une valeur ajoutée<ul><li>Favoriser l’implication des utilisateurs et encourager l'adoption</li><li>Gérer et préparer le changement</li><li>Mesurer, partager la réussite et retravailler</li>|

Les indicateurs de succès clés mesurent la qualité et la réussite des résultats clés et complètent la nature binaire des objectifs et résultats clés (obtenus ou non), en détaillant les bons et les mauvais résultats. Lors de la définition des indicateurs de réussite clés, nous recommandons d’utiliser les critères « spécifique, mesurable, attribuable, réaliste, temporel » ou SMART.

> [!TIP]
> Voici un exemple d'indicateur de succès clé approprié à ce projet :
> 
> |Type  |Questions sur l'indicateur de succès clé et critères  |Comment les mesurer  |Critères de réussite  |Mesurés  |Responsable  |
> |---------|---------|---------|---------|---------|---------|
> |Utilisation/adoption|La qualité des appels est égale ou meilleure qu’avec la solution précédente|Enquête|80 % des utilisateurs sont d’accord ou tout à fait d’accord|Après activation et chaque trimestre|Équipe responsable des technologies de l’information|
> |Utilisation/adoption|Microsoft Teams a facilité le processus de communication|Enquête|80 % des utilisateurs sont d’accord ou tout à fait d’accord|Après activation et chaque trimestre|Équipe responsable de la gestion des changements|
> |Utilisation/adoption|Les utilisateurs utilisent activement la solution|Rapports Office 365, tableau de bord de la qualité des appels|80 % des utilisateurs l’utilisent quotidiennement|Chaque jour|Équipe responsable de la gestion des changements|
> |Utilisation/qualité|Le pourcentage d’appels/conférences médiocres doit être minimal|Tableau de bord de la qualité des appels|< 5 % d'appels médiocres par mois|Chaque jour|Équipe responsable des technologies de l’information|
> |Utilisation/support|Je sais comment obtenir le support technique|Enquête|90% des utilisateurs sont d’accord ou tout à fait d’accord|Après activation et chaque trimestre|Équipe responsable de la gestion des changements|
> |Utilisation/support|Je suis satisfait de la qualité du support technique|Enquête|80 % des utilisateurs sont d’accord ou tout à fait d’accord|Après chaque incident|Équipe responsable des technologies de l’information|
> |Financier|Réduction du nombre de minutes de conférence héritée|Système financier|Atteindre le retour sur investissement défini|Basé sur le retour sur investissement|Équipe responsable de la gestion des changements|

Vous devez identifier les risques d’entreprise dans le cadre de cette activité et définir un plan d’atténuation pour chaque risque identifié. Ces informations peuvent être consignées dans un plan de gestion des risques

> [!TIP]
> Votre plan de gestion des risques peut être documenté comme l'exemple ci-après :
> 
> |Risque  |Probabilité  |Impact  |Global  |Plan d’atténuation  |
> |---------|---------|---------|---------|---------|
> |Une fusion prochaine ajoutera jusqu’à 1000 personnes|Élevée|Élevée|Élevée|<ul><li>Pour les entreprises ayant fusionné, différenciez l’objectif et résultat clé avec le processus propre (Planifier, Intégrer, Générer une valeur ajoutée)</li><li>Ne les incluez pas dans les objectifs et résultats clés existants</li></ul>|
> |Le transfert des numéros de téléphone retardera la réalisation du projet|Élevée|Élevée|Élevée|<ul><li>Préparer toutes les informations nécessaires pour prendre en charge le transfert des numéros de téléphone au préalable (enregistrement de service client, informations de facturation, courrier d’autorisation)</li><li>Ajuster le planning du projet pour concilier la durée de bouclage de l’exécution du transfert des numéros de téléphone</li><li>Communiquer l’utilisation de nouveaux numéros de conférence rendez-vous aux participants externes</li></ul>|
> |Reconception du réseau planifiée|Élevée|Moyenne|Moyenne|<ul><li>Avant d’implémenter Teams comme plate-forme de communication et de collaboration moderne, exécuter l’évaluation de la préparation du réseau pour les sites dans le champ du projet</li></ul>|

<a name="assess-environment-and-evaluate-adoption-readiness"></a>Évaluer l'environnement et la préparation à l'adoption
--------------------------------------------------

Pour atteindre les objectifs et résultats clés, vous devez définir l’architecture globale de la solution. Évaluer tous les aspects relatifs à l’infrastructure informatique et de téléphonie, à la mise en réseau et aux opérations nécessite une découverte de l’environnement.

Toutes les questions liées à l’environnement informatique des utilisateurs finaux, tels que l’évaluation de la préparation des ordinateurs personnels et appareils mobiles pour prendre en charge les cas d’utilisation professionnelle de l’audioconférence, de la configuration matérielle requise à la configuration logicielle requise, seront incluses dans le cadre de la découverte de l’environnement.

La découverte de l’environnement peut également révéler s’il existe des exigences relatives au [transfert des numéros de téléphone à Microsoft](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365). Cela permettra à votre organisation d’ajuster le plan du projet en conséquence et de préparer les infirmations nécessaires pour le transfert des numéros. Vous pouvez effectuer la découverte de l’environnement en utilisant le [questionnaire](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=4_1_0_3) suivant.

La découverte de l’environnement doit inclure l’évaluation de la préparation du réseau pour s’assurer que celui-ci est prêt à prendre en charge l’implémentation du service d’audioconférence.

La préparation du réseau pour prendre en charge l’audioconférence peut être déterminée en utilisant les informations capturées par le biais de la découverte de l’environnement (comme les informations sur la connectivité Internet et la topologie du réseau étendu, les liens de sites et la bande passante disponible) et les données d’analyse des personnes (qui peuvent être converties en utilisation prévue de chaque charge de travail) dans l’outil [My Advisor Network Planning](https://myadvisor.fasttrack.microsoft.com/CloudVoice/NetworkPlanner). Pour confirmer la préparation du réseau, une simulation du trafic en temps réel peut être effectuée à l’aide des solutions fournies par [Microsoft](https://www.microsoft.com/download/details.aspx?id=53885) ou par les [partenaires d'outils d’évaluation de la préparation du réseau](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Partners?ToolPartners).

Les résultats de l’évaluation de la préparation du réseau donneront une image plus claire de l’optimisation du réseau nécessaire ou de la correction requise pour réussir l’implémentation de l’audioconférence.

La préparation à l’adoption peut être évaluée en exécutant une analyse des personnes qui établira une liste des personnes dans l'organisation qui peuvent être ciblées pour l’implémentation du service d’audioconférence. L’analyse des personnes inclut l’identification des périphériques ou dispositifs requis pour aboutir aux résultats de l’entreprise attendus.

Pour effectuer une analyse des personnes, vous pouvez organiser un atelier en impliquant les parties prenantes impliquées dans le projet, à l’aide du support d’atelier [Alignement des personnes](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=4_2_0_7) et de la [Matrice des fonctionnalités des personnes](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=4_2_0_8). Le résultat de l’atelier d’analyse des personnes peut être résumé dans un rapport à l’aide du modèle [Rapport d’analyse des personnes](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=4_2_0_9).

> [!NOTE]
> Les exemples de questionnaire de découverte et d’analyse des personnes ont été rédigés initialement pour Skype Entreprise Online, mais la plus grande partie du contenu s’applique à Teams. N'hésitez pas à modifier ou supprimer les éléments non pertinents par rapport aux objectifs de votre projet.

Vous pouvez identifier les risques techniques dans le cadre de l’évaluation de l’environnement et de la préparation à l’adoption et élaborer un plan d’atténuation pour chaque risque identifié. Ces informations doivent être incorporées dans le plan de gestion des risques.

<a name="map-operational-roles"></a>Mapper les rôles opérationnels
---------------------

La planification des opérations et l identification des équipes qui utiliseront le service d’audioconférence sont une étape importante, les opérations devant commencer lorsque les premiers utilisateurs pilotes sont activés. Chaque équipe identifiée doit vérifier et contenir des tâches et responsabilités identifiées et commencer la préparation pour utiliser le service d’audioconférence. La préparation doit inclure la formation et la préparation, le personnel supplémentaire ou s’assurer que les fournisseurs externes sont configurés pour fournir le service.

> [!TIP]
> Voici un exemple de modèle de documentation du résultat de l'activité de mappage des rôles opérationnels que vous avez réalisée pour prendre en charge ce projet :
> 
> |Rôle opérationnel  |Description  |Équipe  |Détails du contact  |
> |---------|---------|---------|---------|
> |Propriétaire de service|Propriétaire de service, interface avec les divisions de l’entreprise, stratégie|TBA|TBA|
> |Opérations d’audioconférence|Opérations quotidiennes, déplacement/ajout/modification des comptes d’utilisateurs et d’appareils, supervision|TBA|TBA|
> |Administration des clients|Modifier les paramètres à l'échelle du client, activer les nouvelles fonctions|TBA|TBA|
> |Support technique|Interface permettant aux utilisateurs finaux d’obtenir un support|TBA|TBA|
> |Opérations réseau|Exécution du réseau local, étendu, Wi-Fi et accès à Internet|TBA|TBA|
> |Équipe responsable des points de terminaison de client|Gérer les déploiements de bureau|TBA|TBA|
> |Opérations d’identité|Gérer l’infrastructure d’identité (AD, ADFS, Azure AD)|TBA|TBA|
> |Adoption/gestion des changements|Gérer la sensibilisation, la formation et l’adoption de la solution|TBA|TBA|
> |Opérations Exchange|Gère l’environnement Exchange|TBA|TBA|

Pour permettre un mappage des rôles opérationnels plus détaillé, incluant les tâches associées à chaque rôle opérationnel, vous pouvez utiliser le [Classeur de mappage des rôles opérationnels](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=4_4_0_16) pour capturer les détails qui permettront d’avoir une vision claire des rôles et responsabilités pour la prise en charge du service d’audioconférence.

<a name="document-success-plan"></a>Documenter le plan de réussite
---------------------

Un plan de réussite est une documentation créée dans la phase Planifier constituée d'un script commercial, de la préparation du service, d'un plan d’adoption et d’un plan opérationnel.

Le plan de réussite fournira l’équipe du projet, qui peut inclure FastTrack ou un partenaire de déploiement, avec des informations suffisantes pour réaliser les objectifs de l’organisation avec le service d’audioconférence.

Généralement, un plan de réussite contiendra les sections principales suivantes :

-   Script commercial
-   Préparation du service
-   Plan d’adoption
-   Plan opérationnel

### <a name="business-case"></a>Script commercial

Les cas d’utilisation professionnelle, les parties prenantes, les objectifs et résultats clés et les indicateurs de réussite clés, les risques et le planning du projet constituent généralement l’essentiel des informations nécessaires pour un script commercial. Vous devez les documenter dans le cadre du plan de réussite.

### <a name="service-readiness"></a>Préparation du service

L’évaluation de l’environnement fournit les informations initiales nécessaires pour déterminer la préparation technique de l’organisation pour implémenter l’audioconférence.

Le plan pour régler les éléments nécessitant une correction découverts par le biais de l’évaluation de l’environnement est inclus ici. Vous devez inclure l’évaluation de la préparation du service et le plan de correction au plan de réussite.

### <a name="adoption-plan"></a>Plan d’adoption

Après l’évaluation de la préparation à l’adoption, une planification plus détaillée doit être fournie pour que l’équipe du projet puisse générer un ensemble complet de plans de communication, un plan de formation et des activités d’adoption avant, pendant et après le lancement.

Les ressources permettant d’appuyer les activités liées à l’adoption sont des prospectus, des courriers électroniques de bienvenue et les supports de formation identifiés dans cette étape, ainsi que les personnalisations nécessaires pour répondre aux besoins de l'organisation.

Les modèles d’activités d’adoption sont disponibles [ici](https://www.microsoft.com/download/details.aspx?id=54244).

### <a name="operational-plan"></a>Plan opérationnel

L’activité de mappage des rôles opérationnels établira les rôles et les responsabilités, ainsi que les équipes affectées à chaque rôle opérationnel pour prendre en charge l’implémentation de l’audioconférence.

Vous devez effectuer cette étape et inclure le plan opérationnel dans le plan de réussite pour garantir la préparation opérationnelle de la solution.

<br>
Planification technique de l’audioconférence
-----------------------------------------
<a name="technical-planning-for-audio-conferencing"></a> Pour planifier l’implémentation technique de conférence Audio, une série de décisions doit être effectuée à l’avance pour mieux préparer votre organisation pour implémenter une solution qui répond aux besoins de l’entreprise. Ces décisions seront documentées dans un plan d’implémentation technique.

## <a name="availability-of-audio-conferencing"></a>Disponibilité de l’audioconférence

L’audioconférence est disponible dans les [pays et régions suivants :](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).

> [!IMPORTANT]
> En raison de contraintes juridiques, pour rendre l’audioconférence disponible dans les organisations multinationales, le contrat des abonnements Office 365 doit être souscrit dans les pays et régions couverts par le service d’audioconférence ou dans lesquels il est disponible dans le commerce.

Après avoir vérifié l’admissibilité de votre organisation à obtenir le service d’audioconférence, établissez la liste des emplacements des utilisateurs ou des bureaux où le service d’audioconférence sera implémenté en vous basant sur la liste des pays et régions disponibles.

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Points de décision|<ul><li>Déterminer les emplacements des utilisateurs ou les bureaux qui implémenteront le service d’audioconférence</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Étapes suivantes|<ul><li>Consigner les emplacements des utilisateurs ou les bureaux qui seront habilités pour le service d’audioconférence</li></ul>|

> [!TIP]
> Voici un exemple de modèle de liste d'habilitation des sites pour les systèmes téléphoniques avec forfaits d'appels :
> 
> |Bureau   |Emplacement |Service de conférence PSTN  |
> |---------|---------|---------|
> |1 Eppîng Road|Australie|Audioconférence|
> |100 Cyberport Road|Hong Kong R.A.S.|Conférence PSTN héritée|
> |1 Marina Boulevard|Singapour|Audioconférence|
> |32 London Bridge Street|Royaume-Uni|Audioconférence|
> |39 quai du Président Roosevelt|France|Audioconférence|

## <a name="licensing-for-audio-conferencing"></a>Licences pour l’audioconférence

[La licence pour l’audioconférence](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing) est disponible dans le cadre des plans d'abonnement Office 365 E5, ou en tant que complément des plans d'abonnement Office 365 E1 ou Office 365 E3.

> [!NOTE]
> La conférence PSTN ou rendez-vous dans Teams ne prend pas en charge les<sup></sup>-fournisseurs de service d’audioconférence tiers (ACP). <br>Si vous utilisez déjà la conférence PSTN Skype Entreprise Online, vous pouvez bénéficier immédiatement de l’audioconférence dans Teams.

Pour fournir des numéros gratuits de pont de téléconférence et pour prendre en charge les appels de téléconférence vers des numéros internationaux, vous devez configurer des [crédits de communication](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits) pour votre organisation.

> [!IMPORTANT]
> Certains pays sont desservis uniquement par des numéros gratuits de téléconférence et, dans ce cas, l’utilisation de crédits de communication est obligatoire pour prendre en charge la composition de numéros pour ces pays.

Le premier élément à prendre en compte lors de l’implémentation de crédits de communication est de décider du montant initial des fonds à acheter. Les montants de financement recommandés peuvent être obtenus dans l'article sur les [crédits de communication](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits).

Si votre organisation choisit d'utiliser la recharge automatique, une recommandation sur le déclencheur (montant des fonds le moins élevé) est également incluse dans l'article sur les [crédits de communication](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits). Le montant de la recharge automatique doit être déterminé par l’utilisation réelle. L'utilisation des crédits de communication doit être régulièrement contrôlée et le montant de la recharge doit être ajusté en fonction des besoins.

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Points de décision|<ul><li>Si votre organisation n’a pas déjà acheté les licences requises pour l’audioconférence, déterminez si les licences seront acquises en passant à des niveaux d’abonnement Office 365 supérieurs ou en achetant des compléments pour l’audioconférence.</li><li>Déterminez si des crédits de communication sont requis pour l’implémentation de l’audioconférence. Si c’est le cas, déterminez le montant initial des fonds qui doit être acheté. Le cas échéant, déterminez le montant déclencheur et celui de la recharge automatique.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Étapes suivantes|<ul><li>Consigner les utilisateurs à qui une licence d’audioconférence sera attribuée</li><li>Documentez le plan de crédits de communication (montant initial, montant déclencheur, montant de la recharge automatique).</li></ul>|

> [!TIP]
> Vous pouvez documenter la liste d'attribution des licences pour les utilisateurs du service d’audioconférence à l'aide de l'exemple suivant :
> 
> |Utilisateur  |Bureau  |Licence Office 365  |
> |---------|---------|---------|
> |Adele Vance|1 Eppîng Road|Office 365 E5|
> |Alex Wilber|1 Eppîng Road|Office 365 E3, complément pour l’audioconférence|
> |Ben Walters|1 Eppîng Road|Office 365 E3, complément pour l’audioconférence|
> |Christie Cline|1 Marina Boulevard|Office 365 E3, complément pour l’audioconférence|
> |Debra Berger|1 Marina Boulevard|Office 365 E5|
> |Lee Gu|1 Marina Boulevard|Office 365 E5|
> |Emily Braun|32 London Bridge Street|Office 365 E5|
> |Lidia Holloway|32 London Bridge Street|Office 365 E5|
> |Pradeep Gupta|32 London Bridge Street|Office 365 E5|
> |Marcel Beauchamp|39 quai du Président Roosevelt|Office 365 E3, complément pour l’audioconférence|
> |Rachelle Cormier|39 quai du Président Roosevelt|Office 365 E5|
> |Isabell Potvin|39 quai du Président Roosevelt|Office 365 E3, complément pour l’audioconférence|

<br>
> [!TIP]
> Vous pouvez documenter les numéros de planification de vos crédits de communication comme suit :
> |         |         |
> |---------|---------|
> |Montant initial|1 000 $|
> |Montant déclencheur|400 $|
> |Montant de la recharge automatique|TBA|
> 

## <a name="conference-bridge-phone-numbers"></a>Numéros de pont de téléconférence

Le service d’audioconférence dans Office 365 inclut les éléments suivants :

-   plusieurs types de numéros de pont de téléconférence (payants et gratuits) ;
-   plusieurs catégories de numéros de téléphone (dédiés et partagés) ;
-   prise en charge de plusieurs langues pour le pont de téléconférence (principale et secondaire) ;
-   numéro de téléphone par défaut du client.

Vous trouverez une description complète des fonctionnalités incluses dans les rubriques [Configurer l’audioconférence pour Skype Entreprise et Microsoft Teams](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/set-up-audio-conferencing) et [Numéros de téléphone pour l’audioconférence](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/phone-numbers-for-audio-conferencing).

> [!NOTE]
> Les numéros de pont de téléconférence dédiés sont inclus dans le calcul de la limite du nombre de numéros de téléphone qui peuvent être achetés par client, en fonction du nombre de licences applicables comme il est décrit dans la rubrique [Obtenir des numéros de téléphone du service pour Skype Entreprise et Microsoft Teams](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers). Les numéros de pont de téléconférence gratuits requièrent des crédits de communication.

Si des numéros de pont de téléconférence existants doivent être transférés vers le service d’audioconférence, en partant du principe qu'ils répondent aux exigences spécifiques au pays, ils peuvent être transférés vers Microsoft.

> [!NOTE]
> Le transfert de numéros de téléphone vers Microsoft est plus ou moins complexe selon les pays ou régions, les opérateurs, le nombre de circuits concernés et de nombreux autres facteurs. Pour planifier un transfert de numéros de téléphone, consultez le [Guide de transfert de numéros](https://go.microsoft.com/fwlink/?linkid=859011).

Vous trouverez des informations complémentaires sur le transfert de numéros de téléphone vers le service d’audioconférence dans la rubrique [Transférer des numéros de téléphone vers Office 365](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365).

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Points de décision|<ul><li>Déterminer si l’organisation a besoin de numéros de pont de téléconférence dédiés</li><li>Déterminer comment les numéros de pont de téléconférence dédiés seront obtenus pour les emplacements des utilisateurs ou les bureaux concernés par l’implémentation de l’audioconférence (les obtenir auprès de Microsoft ou transférer des numéros de téléphone existants)</li><li>Si vous choisissez de les obtenir auprès de Microsoft, décider de la méthode pour les obtenir (envoi de formulaire ou automatisé) pour les emplacements des utilisateurs ou les bureaux concernés par l’implémentation de l’audioconférence</li><li>Déterminer les préférences de langue à configurer pour chaque numéro de pont de téléconférence dédié</li><li>Décider du numéro de pont de téléconférence par défaut du client</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Étapes suivantes|<ul><li>Documentez le plan général d’acquisition de numéros de téléphone, en détaillant comment les numéros de téléphone seront obtenus pour chaque emplacement d’utilisateur ou bureau concernés par l’implémentation de l’audioconférence.</li><li>Le cas échéant, remplir <a href="https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization">le formulaire de demande de nouveau numéro de téléphone</a> (un formulaire par emplacement ou bureau)</li><li>Si vous choisissez de transférer des numéros de téléphone existants, consultez le <a href="https://go.microsoft.com/fwlink/?linkid=859011">Guide de transfert de numéros</a> pour le planifier et ajuster le planning d’implémentation de l’audioconférence en conséquence.</li><li>Documenter les configurations détaillées des numéros de pont de téléconférence (numéros de pont de téléconférence partagés et dédiés, préférences de langue pour chaque numéro de pont de téléconférence dédié, numéro de pont de téléconférence par défaut du client)</li></ul>|

> [!TIP]
> Voici un exemple de modèle pour capturer les détails du pont de téléconférence :
> 
> |Bureau   |Acquisition de numéro de pont de téléconférence et type de pont |Numéro du pont  |Langue du pont|
> |---------|---------|---------|---------|
> |1 Eppîng Road|Acquisition d'un nouveau numéro de pont dédié|TBA|Anglais (Australie)|
> |1 Marina Boulevard|Acquisition d'un nouveau numéro de pont partagé|TBA|Anglais (États-Unis), Chinois (simplifié, RPC)|
> |32 London Bridge Street|Port existant, dédié|+44 20 7946 0001|Anglais (Royaume-Uni)|
> |39 quai du Président Roosevelt|Acquisition d'un nouveau numéro de pont dédié|TBA|Français (France), Anglais (Royaume-Uni)|

## <a name="conference-bridge-settings"></a>Paramètres du pont de téléconférence

Des options de configuration à l’échelle de l’organisation relatives à l’expérience de participation aux réunions en audioconférence (notification d’accès et de sortie de réunion et enregistrement du numéro de l’appelant), à la longueur du code PIN des organisateurs de réunion et à la notification par courrier électronique sont disponibles afin de personnaliser davantage l’expérience des utilisateurs finaux.

-   Les notifications d’accès et de sortie de réunion sont disponibles sous la forme de nom enregistré, de numéro de téléphone et de tonalités.
-   La longueur du code PIN peut être configurée entre 4 et 12 chiffres, un code PIN de 5 chiffres étant configuré par défaut.
-   Les notifications par courrier électronique lors de l’activation d'une licence d’audioconférence ou d’autres modifications effectuées par un administrateur sont activées par défaut. Vous pouvez désactiver cette fonction et contrôler les communications des utilisateurs finaux de votre organisation.

Pour les utilisateurs à qui une licence d’audioconférence a été attribuée, les numéros payants/gratuits, présentés dans les coordonnées d’audioconférence, peuvent être configurés pour utiliser :

-   le numéro par défaut au niveau du client, ou
-   les numéros de pont de téléconférence attribués automatiquement, ou
-   des numéros de pont de téléconférence définis manuellement pour chaque utilisateur.

Des numéros de pont de téléconférence spécifiques aux utilisateurs sont généralement utiles dans les organisations mondiales ou à l'échelle du pays ou de la région où les utilisateurs sont distribués et doivent fournir des numéros locaux comme numéros de pont de téléconférence par défaut dans les invitations aux réunions.

Les participants qui rejoignent les réunions depuis des villes ou pays différents peuvent rechercher les numéros supplémentaires configurés au niveau du client, mais ces numéros n’apparaissent pas dans les invitations aux réunions. Les invitations aux réunions fournissent un lien qui dirige les participants vers la page des numéros à composer pour la conférence Teams afin qui leur permet de rechercher les numéros de pont de téléconférence les plus proches disponibles pour leur emplacement.

Vous pouvez également configurer comment les utilisateurs non authentifiés sont gérés par chaque organisateur de réunion individuel : exiger que l’organisateur de la réunion commence la réunion avant que les appelants non authentifiés soient admis ou autoriser les appelants non authentifiés à démarrer une réunion.

Des configurations supplémentaires pouvant être appliquées pour chaque utilisateur sont disponibles pour contrôler l’utilisation de numéros de pont de téléconférence gratuits et les appels depuis une conférence.

> [!NOTE]
> Ces contrôles liés au coût ne sont disponibles actuellement que pour les utilisateurs précoces. Vous pouvez inscrire votre organisation dans le programme Aperçu à partir de [https://www.skypepreview.com](https://go.microsoft.com/fwlink/?linkid=859013).

Ces contrôles vous permettent de déterminer si les organisateurs de réunions peuvent fournir des numéros de pont de téléconférence gratuits pour les réunions qu’ils organisent, et de contrôler si les participants peuvent composer des numéros depuis les réunions qu'ils ont organisées. Les niveaux de contrôle sont les suivants : ne pas autoriser la composition de numéros, autoriser uniquement la composition de numéros nationaux, autoriser la composition de numéros nationaux et internationaux.

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Points de décision|<ul><li>Déterminer si l’organisation requiert des notifications d’accès et de sortie de réunion et, le cas échéant, le type de notification à implémenter (tonalités, numéro de téléphone ou nom enregistré)</li><li>Déterminer la longueur du code PIN pour l’audioconférence qui correspond aux exigences de sécurité de l'organisation</li><li>Déterminer si l’organisation souhaite contrôler les communications des utilisateurs finaux liées au service d’audioconférence</li><li>Déterminer les numéros de pont de téléconférence à attribuer à chaque organisateur de réunions</li><li>Déterminer si certains organisateurs de réunions doivent pouvoir utiliser des numéros de pont de téléconférence gratuits pour leurs réunions</li><li>Déterminer si certains organisateurs de réunions doivent pouvoir autoriser les appelants non authentifiés à démarrer une réunion</li><li>Déterminer si la composition des numéros doit être contrôlée pour certains organisateurs de réunions</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Étapes suivantes|<ul><li>Consigner les paramètres détaillés de pont de téléconférence (notifications d’accès et de sortie de réunion, longueur du code PIN, notification par courrier électronique des modifications de configuration)</li><li>Consigner les numéros de pont de téléconférence qui seront attribués à chaque organisateur de réunions et le paramètre correspondant de la stratégie de contrôle des appelants non authentifiés et pour les numéros gratuits et les appels</li></ul>|

> [!TIP]
> Vous pouvez documenter les paramètres de pont de téléconférence comme suit :
> 
> |         |         |
> |---------|---------|
> |Activer les notifications d’accès et de sortie de réunion|Activé|
> |Type d’annonce d’accès/sortie|Tonalités|
> |Demander aux appelants d’enregistrer leur nom avant de rejoindre la réunion|Désactivé|
> |Longueur du code PIN|5|
> |Envoyer automatiquement des e-mails aux utilisateurs si leurs paramètres de numérotation changent|Désactivé|

<br>

> [!TIP]
> Vous pouvez documenter la liste d'attribution des paramètres de pont de téléconférence pour les utilisateurs du service d’audioconférence à l'aide de l'exemple suivant :
>
> |Utilisateur  |Bureau  |Numéro payant par défaut  |Numéro gratuit par défaut  |Autoriser le numéro gratuit  |Les appelants non authentifiés contournent la salle d’attente  |Composition de numéros depuis la conférence  |
> |---------|---------|---------|---------|---------|---------|---------|
> |Adele Vance|1 Eppîng Road|TBA|TBA|Oui|Activé|Internationaux et nationaux|
> |Alex Wilber|1 Eppîng Road|TBA|TBA|Non|Désactivé|Non autorisé|
> |Ben Walters|1 Eppîng Road|TBA|TBA|Non|Désactivé|Non autorisé|
> |Christie Cline|1 Marina Boulevard|TBA|TBA|Oui|Désactivé|Nationaux|
> |Debra Berger|1 Marina Boulevard|TBA|TBA|Oui|Activé|Nationaux|
> |Lee Gu|1 Marina Boulevard|TBA|TBA|Oui|Activé|Nationaux|
> |Emily Braun|32 London Bridge Street|+44 20 7946 0001|TBA|Oui|Activé|Non autorisé|
> |Lidia Holloway|32 London Bridge Street|+44 20 7946 0001|TBA|Oui|Désactivé|Non autorisé|
> |Pradeep Gupta|32 London Bridge Street|+44 20 7946 0001|TBA|Oui|Désactivé|Non autorisé|
> |Marcel Beauchamp|39 quai du Président Roosevelt|TBA|TBA|Non|Désactivé|Nationaux|
> |Rachelle Cormier|39 quai du Président Roosevelt|TBA|TBA|Oui|Activé|Internationaux et nationaux|
> |Isabell Potvin|39 quai du Président Roosevelt|TBA|TBA|Non|Désactivé|Nationaux|

## <a name="dial-plans"></a>Plan de numérotation

Un [Plan de numérotation](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-dial-plans), une fonctionnalité du système téléphonique d'Office 365, est un ensemble de règles de normalisation qui convertit les numéros de téléphone composés dans un autre format (généralement le format [E.164](https://go.microsoft.com/fwlink/?linkid=859014)) pour l'autorisation et le routage des appels. Le service d’audioconférence utilise les mêmes fonctionnalités que le système téléphonique pour convertir les numéros de téléphone en scénarios de numéros composés depuis la conférence.

Un plan de numérotation permet aux utilisateurs de composer des numéros de téléphone comme ils le font habituellement, par exemple en omettant l'indicatif régional pour les appels locaux, l'indicatif du pays ou de la région pour les appels nationaux ou même en composant un numéro court lorsqu'ils passent un appel depuis une conférence.

La fonctionnalité de système téléphonique d’Office 365 comporte deux types de plans de numérotation :

-   **Plan de numérotation de service**. Il s’agit du plan de numérotation par défaut, qui est appliqué aux utilisateurs selon l’emplacement d’utilisation d’Office 365, et il ne peut pas être modifié.
-   **Plan de numérotation de client**. Ce plan de numérotation peut être personnalisé au sein d'un client, et divisé en deux types :
    -   **Plan de numérotation de client global** : ce plan de numérotation s’applique à tous les utilisateurs au sein du client.
    -   **Plan de numérotation d’utilisateurs du client** : ce plan de numérotation s’applique uniquement à des utilisateurs spécifiques.

> [!NOTE]
> Consultez la rubrique [Que sont les plans de numérotation ?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-dial-plans) pour en savoir plus et obtenir des exemples.

Le plan de numérotation efficace affecté aux utilisateurs est la combinaison du plan de numérotation de service (basé sur l’emplacement d’utilisation d’Office 365 des utilisateurs) et du plan de numérotation de client (il peut s’agir d’un plan de numérotation de client.global ou d'un plan de numérotation d’utilisateurs du client).

![Le tableau présente trois combinaisons de plans de numérotation de client et de service.](media/audio_conferencing_image8.png)

Il existe 25 règles de normalisation au maximum dans chaque plan de numérotation de client, et le double emploi des règles de normalisation déjà disponibles dans le plan de numérotation de service doit donc être évité.

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Points de décision|<ul><li>Déterminer si votre organisation requiert des plans de numérotation personnalisés (besoins de l'organisation, exigences en matière d'adoption, etc.)</li><li>Le cas échéant, déterminer la portée du plan de numérotation de client (global au sein du client ou utilisateurs du client) pour prendre en charge les exigences des plans de numérotation personnalisés</li><li>Le cas échéant, déterminer les plans de numérotation de client qui seront créés pour prendre en charge les emplacements des utilisateurs ou les bureaux concernés par l’implémentation de l’audioconférence</li><li>Le cas échéant, déterminer le plan de numérotation personnalisé et le plan de numérotation de client qui doit être affecté à chaque utilisateur</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Étapes suivantes|<ul><li>Consigner les plans de numérotation personnalisés et les règles de normalisation associées à configurer dans le cadre de l’implémentation de l’audioconférence</li><li>Consigner les utilisateurs auxquels le plan de numérotation personnalisé sera affecté et le plan de numérotation de client qui doit être affecté à chaque utilisateur</li></ul>|

> [!TIP]
> Si cela est applicable à votre projet, vous pouvez utiliser les modèles suivants pour documenter les configurations de plans de numérotation de client :
> 
> |Nom du plan de numérotation de client<br>_Description_  |Nom des règles de normalisation<br>_Description_  |Modèle<br>Conversion<br>IsInternalExtension  |
> |---------|---------|---------|
> |**AU-NSW-NorthRyde-OER**<br>_1 Epping Road North Ryde, NSW, plan de numérotation AU_|**AU-NSW-NorthRyde-OER-Internal**<br>_Numéro interne (x7000 - x7999) du 1 Epping Road office, North Ryde, NSW, Australie_|^(7\d{3})$<br>+6125550$1<br>True|
> ||**AU-NSW-Local**<br>_Normalisation du numéro local pour NSW, Australie_|^ ([2-9] \d{7}) $<br>+612$1<br>False|
> ||**AU-TollFree**<br>_Normalisation du numéro gratuit pour l’Australie_|^ (1 [38] \d{4,8}) \d*$<br>+61$1<br>False|
> ||**AU-Service**<br>_Normalisation du numéro de service pour l’Australie_|^ (000\|1 [0125] \d{1,8}) $<br>$1<br>False|
> |**SG-Singapore-OMB**<br>_OMB Singapour, plan de numérotation SG_|**SG-OMB-Internal**<br>_Numéro interne (x8000 – x8999) du bureau OMB, Singapour_|^(8\d{3})$<br>+656888$1<br>True|
> ||**SG-TollFree**<br>_Normalisation du numéro gratuit pour Singapour_|^(1?800\d{7}) \d*$<br>+65$1<br>False|
> ||**SG-Service**<br>_Normalisation du numéro de service pour Singapour_|^ (1\d{3,4}\|9\d{2}) $<br>$1<br>False|
> |**FR-Paris-Issy-39qdPR**<br>_39 quai du Président Roosevelt Issy-les-Moulineaux, plan de numérotation France_|**FR-39qdPR-Internal**<br>_Numéro interne (x7000 – x7999) du bureau 39 quai du Président Roosevelt, Issy-les-Moulineaux, France_|^(7\d{3})$<br>+3319999$1<br>True|
> ||**FR-TollFree**<br>_Normalisation du numéro gratuit pour la France_|^ 0?(80\d{7}) \d*$<br>+33$1<br>False|
> ||**FR-Service**<br>_Normalisation du numéro de service pour la France_|^ (1\d{1,2}\|11 [68] \d{3}\|10\d{2}\|3\d{3}) $<br>$1<br>False|

<br>

> [!TIP]
> Le modèle d'exemple ci-après peut être utilisé pour documenter les attributions de plan de numérotation afin de prendre en charge votre projet :
>
> |Utilisateur  |Bureau  |Type de plan de numérotation  |Nom du plan de numérotation  |
> |---------|---------|---------|---------|
> |Adele Vance|1 Eppîng Road|Plan de numérotation de client|AU-NSW-NorthRyde-OER|
> |Alex Wilber|1 Eppîng Road|Plan de numérotation de client|AU-NSW-NorthRyde-OER|
> |Ben Walters|1 Eppîng Road|Plan de numérotation de client|AU-NSW-NorthRyde-OER|
> |Christie Cline|1 Marina Boulevard|Plan de numérotation de client|SG-Singapore-OMB|
> |Debra Berger|1 Marina Boulevard|Plan de numérotation de client|SG-Singapore-OMB|
> |Lee Gu|1 Marina Boulevard|Plan de numérotation de client|SG-Singapore-OMB|
> |Emily Braun|32 London Bridge Street|Plan de numérotation de service|N/A|
> |Lidia Holloway|32 London Bridge Street|Plan de numérotation de service|N/A|
> |Pradeep Gupta|32 London Bridge Street|Plan de numérotation de service|N/A|
> |Marcel Beauchamp|39 quai du Président Roosevelt|Plan de numérotation de client|FR-Paris-Issy-30qdPR|
> |Rachelle Cormier|39 quai du Président Roosevelt|Plan de numérotation de client|FR-Paris-Issy-30qdPR|
> |Isabell Potvin|39 quai du Président Roosevelt|Plan de numérotation de client|FR-Paris-Issy-30qdPR|

## <a name="microsoft-teams-configurations"></a>Configurations de Microsoft Teams

La prise en charge de l’audioconférence est disponible pour les réunions ponctuelles et planifiées. Pour les réunions planifiées, les configurations au niveau du client qui régissent la planification des réunions (réunions privées et de canal) doivent être activées.

> [!NOTE]
> Actuellement, si votre organisation a des exigences de conformité exigeant que toutes les discussions en réunion puissent être découvertes, vous devez désactiver les réunions privées si l’organisateur dispose d’une boîte aux lettres sur site Exchange.<br>
> Dans un autre cas d’utilisation, si toutes les réunions dans l’organisation doivent être visibles **pour les parties invitées** uniquement, afin d’empêcher que les informations sur les réunions soient divulguées aux parties non invitées, nous vous recommandons de désactiver la possibilité de planifier des réunions dans les **canaux**.

Les paramètres, disponibles en tant que configurations au niveau du client, s’appliquent à tous les utilisateurs dans l’organisation et auront une incidence sur toutes les planifications de réunions dans Teams, et non pas uniquement aux réunions Teams **avec** l’audioconférence.

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Points de décision|<ul><li>Déterminer si l’organisation requiert que la planification de réunions privées soit activée ou désactivée</li><li>Déterminer si l’organisation requiert que la planification de réunions de canal soit activée ou désactivée</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Étapes suivantes|<ul><li>Consigner les configurations de planification de réunions de Teams</li></ul>|

> [!TIP]
> Vous pouvez documenter les configurations des réunions comme suit :
> 
> |         |         |
> |---------|---------|
> |Autoriser la planification de réunions privées|Activé|
> |Autoriser la planification de réunions de canal|Désactivé|

## <a name="document-technical-implementation-plan"></a>Documenter le plan d’implémentation technique

Utilisez les points de décision ci-dessus pour documenter votre plan d’implémentation technique.
Ce plan d’implémentation technique fournira l’équipe du projet, qui peut inclure FastTrack ou un partenaire de déploiement, avec les informations nécessaires pour exécuter l’intégration technique pour l’implémentation de l’audioconférence.

Généralement, un plan d’implémentation technique contiendra les sections principales suivantes :

-   Liste d’habilitations de sites pour le service d’audioconférence

-   Liste d’attributions de licences pour les organisateurs de réunions en audioconférence

-   Numéros de planification de crédits de communication

-   Détails du pont de téléconférence

-   Paramètres du pont de téléconférence

-   Affectations de paramètres de pont de téléconférence

-   Plans de numérotation de client

-   Affectations du plan de numérotation

-   Configurations des réunions Microsoft Teams

<br>
Une fois les plans de réussite et d’implémentation technique établis, vous êtes prêt à faire franchir à votre organisation les étapes suivantes du parcours du client d’Office 365.

<br>
Intégrer =======

*Bientôt disponible.*

<br>
Générer une valeur ajoutée ===========

*Bientôt disponible.*

<br>
## <a name="see-also"></a>Voir aussi

[Configurer l’audioconférence pour Skype Entreprise et Microsoft Teams](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/set-up-audio-conferencing)
