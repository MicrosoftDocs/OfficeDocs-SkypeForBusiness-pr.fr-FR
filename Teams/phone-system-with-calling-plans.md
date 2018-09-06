---
title: Guide pratique des systèmes téléphoniques avec forfaits d'appels dans Microsoft Teams
author: arachmanGitHub
ms.author: MyAdvisor
manager: serdars
ms.date: 08/21/2018
ms.topic: article
ms.service: msteams
ms.reviewer: MyAdvisor
description: Guide pratique pour la planification, le déploiement et la gestion des systèmes téléphoniques avec forfaits d'appels dans Microsoft Teams avec l'infrastructure Planifier (Programmer), Intégrer (Fournir), Générer une valeur ajoutée (Utiliser).
localization_priority: Priority
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
redirect_url: https://docs.microsoft.com/en-us/MicrosoftTeams/cloud-voice-deployment
ms.openlocfilehash: c697da99ab2ca96794448dca93f45ae29efa103d
ms.sourcegitcommit: cbb4738e119cf366c3aad9aad7f7b369bcd86c19
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/30/2018
ms.locfileid: "23779891"
---
<a name="practical-guidance-for-phone-system-with-calling-plans-in-microsoft-teams"></a>Guide pratique des systèmes téléphoniques avec forfaits d'appels dans Microsoft Teams
=========================================================================

La fonctionnalité de système téléphonique d'Office 365 permet de gérer le routage des appels, les stratégies et l'affectation d'utilisateurs. Cela inclut le système de gestion des appels téléphoniques, le routage des appels et le contrôle des appels.

Les forfaits d'appels Office 365 constituent un service complémentaire de la fonctionnalité de système téléphonique fournie via Teams et Skype Entreprise Online. Les forfaits d'appels confèrent à vos employés un numéro de téléphone principal leur permettant de passer et de recevoir des appels téléphoniques à l'extérieur de votre organisation via le réseau téléphonique commuté (RTC).

Pour en savoir plus, consultez [Voici les avantages du système téléphonique d'Office 365](https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/here-s-what-you-get-with-phone-system) et [En quoi consiste les forfaits d'appels dans Office 365 ?](https://docs.microsoft.com/en-us/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-calling-plans-in-office-365)

Ce guide pratique vous oriente dans la structure du client FastTrack d'Office 365 et ses trois phases, planifier, intégrer et générer une valeur ajoutée, pour vous aider à programmer, fournir et utiliser une implémentation réussie d'un système téléphonique avec forfaits d'appels.

> [!TIP]
> Dans ce guide pratique, nous fournissons des exemples de résultats pour chaque activité et theme principal. Les exemples fournis tout au long de ce document sont intégrés aux légendes des astuces et peuvent être utilisés comme modèles. « TBA » (à ajouter) est affiché en regard des informations que vous devez remplir dans le cadre de votre processus de planification.

Concevoir <a name="Envision_PhoneSystemWithCallingPlans"> </a>
========

La phase Planifier fournit les bases du parcours du client Office 365 et s'applique à toutes les charges de travail, y compris au système téléphonique avec forfaits d'appels.

Dans cette phase, les objectifs de l’entreprise sont déterminés, avec les parties prenantes impliquées dans le projet réunies, pour fournir par la suite :

-   Un plan de réussite général contenant des cas d'utilisation, des parties prenantes clés, des objectifs et des résultats clés, des indicateurs de succès clés, des risques, une évaluation de l'environnement, la préparation à l'adoption et un plan opérationnel

-   Un plan d'implémentation technique des systèmes téléphoniques avec forfaits d'appels pour parvenir à l'état final souhaité

<a name="define-business-use-cases-for-phone-system-with-calling-plans"></a>Définir les cas d'utilisation des systèmes téléphoniques avec forfaits d'appels
-------------------------------------------------------------

Les systèmes téléphoniques avec forfaits d'appels permettent aux organisations de moderniser leur espace de travail en permettant aux utilisateurs de passer des appels professionnels à partir de leur ordinateur et de leurs appareils mobiles.

La modernisation de l'espace de travail peut faire partie d'une implémentation  fonctionnelle reposant sur les activités, d'un déménagement de bureaux, d'un réaménagement des bureaux, du retrait des solutions PBX (autocommutateur privé) existantes, de la signature d'un contrat de fourniture de services PSTN, etc.

Dans cette étape, les principales parties prenantes impliquées dans le projet définiront des cas d'utilisation qui prennent en charge l'implémentation de systèmes téléphoniques avec forfaits d'appels.

Les cas d'utilisation sont destinés à documenter des résultats attendus et mesurables, et incluent les éléments suivants :

-   Description du processus d’entreprise actuel
-   Difficultés par rapport au processus d'entreprise existant définies
-   Comment la technologie peut aider à surmonter ces difficultés
-   Les résultats attendus et mesurables si ces difficultés sont surmontées

> [!TIP]
> Voici un exemple d'une étude de cas d'entreprise réalisée :
>|         |
>|---------|
>|**Description du processus d’entreprise actuel**<p>La configuration standard des espaces de travail Contoso inclut un numéro de téléphone pour chaque bureau. Chaque employé reçoit un numéro de téléphone de ligne entrante directe. Les téléphones de bureau sont connectés à un système PBX et connectés au PSTN via une jonction SIP. Les employés peuvent uniquement passer et recevoir des appels sur le téléphone de bureau qui leur a été attribué.|
>|**Difficultés par rapport au processus d’entreprise existant**<p>L'analyse de l'utilisation des téléphones de bureau indique que seulement 10 % des téléphones de bureau sont activement utilisés, le reste étant configuré soit pour transférer des appels vers des téléphones mobiles, soit pour faire sonner en même temps des téléphones mobiles. La maintenance du système PBX existant et des téléphones de bureau associés contribue aux 20 % des coûts de service téléphonique mensuels.|
>|**Comment la technologie peut surmonter ces difficultés**<p>Les systèmes téléphoniques avec forfaits d'appels permettent à l'ordinateur personnel de l'utilisateur final de recevoir et de passer des appels téléphoniques via le réseau de données en tirant profit de l'application Microsoft Teams native et en supprimant la nécessité de déployer et de maintenir des téléphones de bureau. Ils offrent également la possibilité de désactiver le système PBX existant, étant donné que le service téléphonique peut être fourni via le cloud sur le réseau sans dépendance sur le système téléphonique traditionnel.|
>|**Résultats de l’entreprise attendus et mesurables**<p>La suppression des besoins de maintenance et la mise hors service des téléphones PBX et de bureau existants entraînent une réduction de 20 % des dépenses de service téléphonique mensuelles. Les systèmes téléphoniques avec forfaits d'appels simplifient les espaces de travail de bureau et permettent à Contoso de développer ses opérations, en établissant de nouveaux bureaux avec des coûts de téléphonie initiaux minimes.|

Au cours de la phase Planifier, en plus de définir vos cas d'utilisation, vous devez également clarifier les éléments suivants :
- Portée organisationnelle
- Planning de projet

<a name="identify-key-stakeholders"></a>Identifier les parties prenantes clés
-------------------------

Les cas d'utilisation définis à l'étape précédente incluront la portée organisationnelle de l'implémentation des systèmes téléphoniques avec forfaits d'appels. De ce fait, vous pouvez compléter la matrice complète des parties prenantes pour inclure les personnes adéquates à intégrer au projet.

> [!TIP]
> Voici un exemple de modèle de matrice des parties prenantes que vous pouvez utiliser pour documenter les parties prenantes intégrées dans le projet :
>|Rôle  |Description  |Nom, informations de contact, emplacement  |
>|---------|---------|---------|
>|Sponsor exécutif du projet|<ul><li>Autorité et responsabilité ultimes du projet et réalisation des objectifs du projet</li><li>Aide à résoudre les problèmes transmis par le chef de projet</li><li>Organise la communication au sein de l’entreprise au sujet des objectifs du projet</li><li>Chargé de prendre les décisions stratégiques clés</li><li>Chargé de la disponibilité des ressources nécessaires et du budget</li><li>Principale évaluation trimestrielle des activités</li><li>Adhésion et appui à la campagne de sensibilisation</li><li>Est le sponsor du projet pour le lancement du programme</li></ul>|TBA|
>|Chef de projet|<ul><li>Gestion et direction de l’équipe du projet</li><li>Coordonne les partenaires et les équipes qui participent au projet</li><li>Responsable de la création et de la gestion des plans du projet pour obtenir les principaux résultats trimestriels</li><li>Résoudre les problèmes fonctionnels croisés</li><li>Fournir des informations actualisées périodiques aux sponsors du projet</li><li>Incorporer les aspects relatifs à l’adoption dans l’ensemble du plan du projet</li><li>Diriger les évaluations mensuelles des activités et opérationnelles, contribuer aux évaluations trimestrielles des activités</li></ul>|TBA|
>|Chef/architecte de la collaboration|<ul><li>Chargé de l’exécution de la stratégie de collaboration définie par la direction de l’entreprise</li><li>Analyse et choisit les produits de collaboration pour l’entreprise permettant d’atteindre les objectifs professionnels</li><li>Chargé de la conception des opérations des produits de collaboration</li><li>Définit un modèle d'opération et de prise en charge</li><li>Contribue aux évaluations mensuelles et trimestrielles des activités</li><ul>|TBA|
>|Consultant|<ul><li>Chargé des services de configuration</li><li>Contribue à l'architecture de solutions globale</li></ul>|TBA|
>|Gestionnaire de projets|<ul><li>Élaborer et tenir à jour les plans de projet</li><li>Gérer les livrables du projet conformément au plan et au budget du projet</li><li>Noter et gérer les problèmes liés au projet, y compris les remontées</li><li>Effectuer des appels d'intervention hebdomadaires</li><li>Assurer la liaison avec, et fournir des informations actualisées aux sponsors exécutifs du projet</li><li>Collaborer avec l’architecte pour définir le mode de gestion des changements et les plans de communication</li></ul>|TBA|
>|Spécialiste en gestion des changements/adoption|<ul><li>Formuler des recommandations lors de la phase de découverte sur les processus d’adoption et de formation</li><li>Participer à l’atelier sur la stratégie d’adoption</li><li>Développer et être responsable de la stratégie d’adoption</li><li>Développer et exécuter le plan de communication</li><li>Chargé de dispenser des formations aux utilisateurs finaux</li><li>Recueillir les commentaires et réaliser des enquêtes</li></ul>|TBA|
>|Directeur de réseau|<ul><li>Formuler des recommandations lors de la phase de découverte sur la conception du réseau</li><li>Participer à la planification lors de l’atelier sur la planification</li><li>Coordonner le travail de l’équipe de mise en réseau lors de l’exécution du projet</li></ul>|TBA|
>|Directeur de la sécurité|<ul><li>Formuler des recommandations lors de la phase de découverte sur les processus et la conception de la sécurité</li><li>Participer à la planification lors de l’atelier sur la planification</li><li>Coordonner le travail de l’équipe chargée de la sécurité lors de l’exécution du projet</li></ul>|TBA|
>|Directeur de la téléphonie|<ul><li>Formuler des recommandations lors de la phase de découverte sur la conception de la téléphonie</li><li>Participer à la planification lors de l’atelier sur la planification</li><li>Coordonner le travail de l’équipe chargée de la téléphonie lors de l’exécution du projet</li></ul>|TBA|
>|Directeur de bureau|<ul><li>Formuler des recommandations lors de la phase de découverte sur les clients et le processus de mise à jour</li><li>Participer à la planification lors de l’atelier sur la planification</li><li>Coordonner le travail de l’équipe chargée des bureaux lors de l’exécution du projet</li></ul>|TBA|
>|Responsable du support|<ul><li>Formuler des recommandations lors de la phase de découverte sur le modèle opérationnel et de prise en charge</li><li>Participer à la planification lors de l’atelier sur la planification</li><li>Participer à la planification du modèle de prise en charge</li><li>Coordonner le travail de l’équipe chargée de la prise en charge/des ressources lors de l’exécution du projet</li></ul>|TBA|
>|Représentants d'unité commerciale|<ul><li>Contribuer aux guides et supports d’adoption basés sur les utilisateurs finaux</li><li>Évaluer et contribuer aux cas d’utilisation professionnelle</li></ul>|TBA|
>|Directeur du déploiement|<ul><li>S’assurer que les conditions préalables au déploiement sont remplies</li><li>Impliquer des ressources des clients dans l’affectation, la préparation et le déploiement des activités de l’étape</li><li>Participer à des réunions pour évaluer l’état de préparation et du déploiement</li></ul>|TBA|
>|Administrateurs informatiques|<ul><li>Spécialistes des technologies de l'information pour aider à la planification et l’exécution des tests</li></ul>|TBA|
>|Propriétaire de service|<ul><li>Responsable du fonctionnement de l'ensemble du service de systèmes téléphoniques avec forfaits d'appels</li><li>Propriétaire du service de systèmes téléphoniques avec forfaits d'appels</li></ul>|TBA|
>|Ambassadeurs de la qualité|<ul><li>Génère des commentaires sur la qualité, la fiabilité et des utilisateurs</li><li>Identifie les tendances en matière de qualité et génère les corrections avec les équipes respectives</li><li>Fait des rapports par le biais du comité de pilotage à la direction</li><li>Fait des rapports sur la qualité, la fiabilité et l’opinion des utilisateurs par l’intermédiaire de Rate My Call et de Net Promoter Score</li></ul>|TBA|

<a name="define-objectives-and-key-results-key-success-indicators-and-risks"></a>Définir les objectifs et les résultats clés, les indicateurs de succès clés et les risques
--------------------------------------------------------------------

Avec les parties prenantes impliquées dans le projet réunies, les cas d'utilisation professionnelle, la portée organisationnelle et le planning du projet peuvent être transposés en objectifs et résultats clés et les mesures de réussite du projet peuvent être définies dans une liste d'indicateurs de succès clés.

L’entière participation des parties prenantes impliquées dans le projet lors de la définition des objectifs et résultats clés et des indicateurs de succès clés garantira le sentiment d’appartenance et qu'ils correspondent aux besoins de l’entreprise en matière d’organisation.

Les objectifs et résultats clés contiennent la liste des objectifs définis au début du projet, les résultats clés mesurables étant définis chaque trimestre. Les résultats clés sont vérifiés chaque mois pour effectuer le suivi du projet global et, en fonction de l’évolution, les plans trimestriels peuvent être adaptés lorsque cela est nécessaire.

> [!TIP]
> Un exemple d'objectifs et résultats clés appropriés à l'implémentation d'un système téléphonique avec forfaits d'appels peut être référencé ci-après :
><br>
>
>**Vision : augmenter la productivité an optimisant les investissements dans Office 365**
>|Objectifs  |Résultats clés  |Action  |
>|---------|---------|---------|
>|Déployer les systèmes téléphoniques avec forfaits d'appels dans les filiales européennes d'ici la fin de l'exercice fiscal 2018|T3, 2018 : Déployer les systèmes téléphoniques avec forfaits d'appels dans les bureaux londoniens|Planifier<ul><li>Créer un plan de réussite</li><li>Créer un plan d’implémentation technique détaillé</li></ul><p>Intégrer<ul><li>Exécuter le plan de réussite</li><li>Exécuter le plan d’implémentation technique</li></ul>|
>|Désactiver le système PBX hérité dans les bureaux londoniens d'ici la fin de l'exercice fiscal 2018|T4, 2018 : Désactiver le système PBX hérité dans les bureaux londoniens|Générer une valeur ajoutée<ul><li>Favoriser l’implication des utilisateurs et encourager l'adoption</li><li>Gérer et préparer le changement</li><li>Mesurer, partager la réussite et retravailler</li>|

Les indicateurs de succès clés mesurent la qualité et la réussite des résultats clés et complètent la nature binaire des objectifs et résultats clés (obtenus ou non), en détaillant les bons et les mauvais résultats. Lors de la définition des indicateurs de réussite clés, nous recommandons d’utiliser les critères « spécifique, mesurable, attribuable, réaliste, temporel » ou SMART.

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
>|Financier|Réduction des dépenses de service téléphonique mensuelles|Système financier|Atteindre le retour sur investissement défini|Basé sur le retour sur investissement|Équipe responsable de la gestion des changements|

Vous devez identifier les risques d’entreprise dans le cadre de cette activité et définir un plan d’atténuation pour chaque risque identifié. Capturez ces informations dans un plan de gestion des risques.

> [!TIP]
> Votre plan de gestion des risques peut être documenté comme l'exemple ci-après :
>|Risque  |Probabilité  |Impact  |Global  |Plan d’atténuation  |
>|---------|---------|---------|---------|---------|
>|Une fusion prochaine ajoutera jusqu’à 1000 personnes|Élevée|Élevée|Élevée|<ul><li>Pour les entreprises ayant fusionné, différenciez l’objectif et résultat clé avec le processus propre (Planifier, Intégrer, Générer une valeur ajoutée)</li><li>Ne les incluez pas dans les objectifs et résultats clés existants</li></ul>|
>|Le transfert des numéros de téléphone retardera la réalisation du projet|Élevée|Élevée|Élevée|<ul><li>Préparer toutes les informations nécessaires pour prendre en charge le transfert des numéros de téléphone au préalable (enregistrement de service client, informations de facturation, courrier d’autorisation)</li><li>Ajuster le planning du projet pour concilier la durée de bouclage de l’exécution du transfert des numéros de téléphone</li><li>Utiliser les numéros de téléphone provisoires avec la manipulation de l'ID de l'appelant</li></ul>|
>|Reconception du réseau planifiée|Élevée|Moyenne|Moyenne|<ul><li>Avant d’implémenter Teams comme plate-forme de communication et de collaboration moderne, exécuter l’évaluation de la préparation du réseau pour les sites dans le champ du projet</li></ul>|

<a name="assess-environment-and-evaluate-adoption-readiness"></a>Évaluer l'environnement et la préparation à l'adoption
--------------------------------------------------

Pour atteindre les objectifs et résultats clés, vous devez définir l’architecture globale de la solution. Évaluer tous les aspects relatifs à l’infrastructure informatique et de téléphonie, à la mise en réseau et aux opérations nécessite une découverte de l’environnement.

Toutes les questions liées à l'environnement informatique des utilisateurs finaux, tels que l'évaluation de la préparation des ordinateurs personnels et appareils mobiles pour prendre en charge les cas d'utilisation des systèmes téléphoniques avec forfaits d'appels, de la configuration matérielle requise à la configuration logicielle requise, seront incluses dans le cadre de la découverte de l'environnement.

La découverte de l'environnement peut également indiquer si vous devez [transférer des numéros de téléphone à Microsoft](https://docs.microsoft.com/en-us/skypeforbusiness/what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365). Cela permettra à votre organisation d'ajuster le plan du projet en conséquence et de préparer les informations nécessaires pour le transfert des numéros. Pour effectuer la découverte de l'environnement, utilisez le [questionnaire de découverte](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=4_1_0_3).

La découverte de l'environnement doit inclure l'évaluation de la préparation du réseau pour s'assurer que celui-ci est prêt à prendre en charge l'implémentation des systèmes téléphoniques avec forfaits d'appels.

La préparation du réseau pour prendre en charge les systèmes téléphoniques avec forfaits d'appels peut être déterminée en utilisant les informations capturées par le biais de la découverte de l'environnement (comme les informations sur la connectivité Internet et la topologie du réseau étendu, les liens de sites et la bande passante disponible) et les données d'analyse des personnes (qui peuvent être converties en utilisation prévue de chaque charge de travail) dans l'outil [My Advisor Network Planner](https://myadvisor.fasttrack.microsoft.com/CloudVoice/NetworkPlanner). Pour confirmer la préparation du réseau, effectuez une simulation du trafic en temps réel à l'aide des solutions suivantes :
- Microsoft : [Outil d'évaluation du réseau de Skype Entreprise](https://www.microsoft.com/download/details.aspx?id=53885)
- Partenaires : [Partenaires d'outils d'évaluation de la préparation du réseau](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Partners?ToolPartners)

Les résultats de l'évaluation de la préparation du réseau donneront une image plus claire de l'optimisation du réseau nécessaire ou de la correction requise pour réussir l'implémentation des systèmes téléphoniques avec forfaits d'appels.

La préparation à l'adoption peut être évaluée en exécutant une analyse des personnes pour établira une liste des utilisateurs dans l'organisation qui peuvent être ciblés pour l'implémentation des systèmes téléphoniques avec forfaits d'appels. L’analyse des personnes inclut l’identification des périphériques ou dispositifs requis pour aboutir aux résultats de l’entreprise attendus.

Pour effectuer une analyse des personnes, vous pouvez organiser un atelier en impliquant les parties prenantes impliquées dans le projet, à l’aide du support d’atelier [Alignement des personnes](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=4_2_0_7) et de la [Matrice des fonctionnalités des personnes](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=4_2_0_8). Le résultat de l’atelier d’analyse des personnes peut être résumé dans un rapport à l’aide du modèle [Rapport d’analyse des personnes](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=4_2_0_9).

> [!NOTE]
> Les exemples de questionnaire de découverte et d’analyse des personnes ont été rédigés initialement pour Skype Entreprise Online, mais la plus grande partie du contenu s’applique à Teams. N'hésitez pas à modifier ou supprimer les éléments non pertinents par rapport aux objectifs de votre projet.

Vous pouvez identifier les risques techniques dans le cadre de l’évaluation de l’environnement et de la préparation à l’adoption et élaborer un plan d’atténuation pour chaque risque identifié. Ces informations doivent être incorporées dans le plan de gestion des risques.

<a name="map-operational-roles"></a>Mapper les rôles opérationnels
---------------------

La planification des opérations et l'identification des équipes qui utiliseront le service de systèmes téléphoniques avec forfaits d'appels sont une étape importante, les opérations devant commencer lorsque les premiers utilisateurs pilotes sont activés. Chaque équipe identifiée doit vérifier et contenir des tâches et responsabilités identifiées et commencer la préparation pour utiliser le service de systèmes téléphoniques avec forfaits d'appels. La préparation doit inclure la formation et la préparation, le personnel supplémentaire ou s’assurer que les fournisseurs externes sont configurés pour fournir le service.

> [!TIP]
> Voici un exemple de modèle de documentation du résultat de l'activité de mappage des rôles opérationnels que vous avez réalisée pour prendre en charge ce projet :
>|Rôle opérationnel  |Description  |Équipe  |Détails du contact  |
>|---------|---------|---------|---------|
>|Propriétaire de service|Propriétaire de service, interface avec les divisions de l’entreprise, stratégie|TBA|TBA|
>|Fonctionnement des systèmes téléphoniques avec forfaits d'appels|Opérations quotidiennes, déplacement/ajout/modification des comptes d’utilisateurs et d’appareils, supervision|TBA|TBA|
>|Administration des clients|Modifier les paramètres à l'échelle du client, activer les nouvelles fonctions|TBA|TBA|
>|Support technique|Interface permettant aux utilisateurs finaux d’obtenir un support|TBA|TBA|
>|Opérations réseau|Exécution du réseau local, étendu, Wi-Fi et accès à Internet|TBA|TBA|
>|Équipe responsable des points de terminaison de client|Gérer les déploiements de bureau|TBA|TBA|
>|Opérations d’identité|Gérer l’infrastructure d’identité (AD, ADFS, Azure AD)|TBA|TBA|
>|Adoption/gestion des changements|Gérer la sensibilisation, la formation et l’adoption de la solution|TBA|TBA|
>|Opérations Exchange|Gère l’environnement Exchange|TBA|TBA|

Pour permettre un mappage des rôles opérationnels plus détaillé, incluant les tâches associées à chaque rôle opérationnel, vous pouvez utiliser le [Classeur de mappage des rôles opérationnels](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=4_4_0_16) pour capturer les détails qui permettront d'obtenir une vision claire des rôles et responsabilités pour la prise en charge du service de systèmes téléphoniques avec forfaits d'appels.

<a name="document-success-plan"></a>Documenter le plan de réussite
---------------------

Un plan de réussite est une documentation créée dans la phase Planifier constituée d'un script commercial, de la préparation du service, d'un plan d’adoption et d’un plan opérationnel.

Le plan de réussite fournira l'équipe du projet, qui peut inclure FastTrack ou un partenaire de déploiement, avec des informations suffisantes pour réaliser les objectifs de l'organisation à l'aide du système téléphonique avec forfaits d'appels.

Généralement, un plan de réussite contiendra les sections principales suivantes :

-   Script commercial
-   Préparation du service
-   Plan d’adoption
-   Plan opérationnel

### <a name="business-case"></a>Script commercial

Les cas d’utilisation professionnelle, les parties prenantes, les objectifs et résultats clés et les indicateurs de réussite clés, les risques et le planning du projet constituent généralement l’essentiel des informations nécessaires pour un script commercial. Vous devez les documenter dans le cadre du plan de réussite.

### <a name="service-readiness"></a>Préparation du service

L'évaluation de l'environnement fournit les informations initiales nécessaires pour déterminer la préparation technique de l'organisation pour implémenter les systèmes téléphoniques avec forfaits d'appels.

Le plan pour régler les éléments nécessitant une correction découverts par le biais de l’évaluation de l’environnement est inclus ici. Vous devez inclure l’évaluation de la préparation du service et le plan de correction au plan de réussite.

### <a name="adoption-plan"></a>Plan d’adoption

Après l’évaluation de la préparation à l’adoption, une planification plus détaillée doit être fournie pour que l’équipe du projet puisse générer un ensemble complet de plans de communication, un plan de formation et des activités d’adoption avant, pendant et après le lancement.

Les ressources permettant d’appuyer les activités liées à l’adoption sont des prospectus, des courriers électroniques de bienvenue et les supports de formation identifiés dans cette étape, ainsi que les personnalisations nécessaires pour répondre aux besoins de l'organisation.

Les modèles d’activités d’adoption sont disponibles [ici](https://www.microsoft.com/download/details.aspx?id=54244).

### <a name="operational-plan"></a>Plan opérationnel

L'activité de mappage des rôles opérationnels établira les rôles et les responsabilités, ainsi que les équipes affectées à chaque rôle opérationnel pour prendre en charge l'implémentation du système téléphonique avec forfaits d'appels.

Vous devez effectuer cette étape et inclure le plan opérationnel dans le plan de réussite pour garantir la préparation opérationnelle de la solution.

<br>
Planification technique du système téléphonique avec forfaits d'appels
------------------------------------------------------

Pour planifier l'implémentation technique du système téléphonique avec forfaits d'appels, plusieurs décisions doivent être prises au préalable afin de mieux préparer votre organisation à implémenter une solution qui répond aux besoins de votre organisation. Ces décisions seront documentées dans un plan d’implémentation technique.

## <a name="availability-of-calling-plans"></a>Disponibilité des forfaits d'appels

Pour connaître les pays et régions dans lesquels les services de forfaits d'appel sont disponibles, consultez [Pays et régions dans lesquels l'audioconférence et les forfaits d'appels sont disponibles](https://docs.microsoft.com/en-uscountry-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).

> [!IMPORTANT]
> En raison de contraintes juridiques, pour rendre les forfaits d'appels disponibles dans les organisations multinationales, le contrat des abonnements Office 365 doit être souscrit dans les pays et régions couverts par le service de forfaits d'appels où dans lesquels il est disponible dans le commerce.

Après avoir vérifié l'admissibilité de votre organisation à obtenir le service de forfaits d'appels, établissez la liste des emplacements des utilisateurs ou des bureaux où le service de forfaits d'appels sera implémenté en vous basant sur la liste des pays et régions disponibles.

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Points de décision|<ul><li>Choisissez les emplacements des utilisateurs ou les bureaux dans lesquels le service de forfaits d'appels sera implémenté.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Étapes suivantes|<ul><li>Documentez les emplacements des utilisateurs ou les bureaux qui seront habilités pour le service de forfaits d'appels.</li></ul>|

> [!TIP]
> Voici un exemple de modèle de liste d'habilitation des sites pour les systèmes téléphoniques avec forfaits d'appels :
>|Bureau   |Emplacement |Service de système téléphonique  |
>|---------|---------|---------|
>|1 Eppîng Road|Australie|Service PSTN hérité|
>|100 Cyberport Road|Hong Kong R.A.S.|Service PSTN hérité|
>|1 Marina Boulevard|Singapour|Service PSTN hérité|
>|32 London Bridge Street|Royaume-Uni|Système téléphonique avec forfaits d’appels|
>|39 quai du Président Roosevelt|France|Système téléphonique avec forfaits d’appels|

## <a name="licensing-for-calling-plans"></a>Licence de forfaits d'appels

Les forfaits d'appels Office 365 constituent un service complémentaire de la fonctionnalité de système téléphonique. Vous devez donc disposer d'une licence de système téléphonique active pour utiliser les forfaits d'appel.

[La licence de système téléphonique](https://docs.microsoft.com/en-us/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing) est disponible dans le cadre des plans d'abonnement Office 365 E5, ou en tant que complément des plans d'abonnement Office 365 E1 ou Office 365 E3.
Deux types de [licences de forfait d'appels](https://docs.microsoft.com/en-us/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-calling-plans-in-office-365) sont disponibles :

-   Forfait d'appels nationaux
-   Forfait d'appels nationaux et internationaux

> [!NOTE]
> Le caractère « national » inhérent à un utilisateur spécifique est déterminé par l'emplacement d'utilisation d'Office 365 attribué à cet utilisateur.

Chaque type de forfait d'appels attribue des minutes d'appels nationaux ou internationaux aux utilisateurs sur une base mensuelle. Le forfait d'appels nationaux est moins onéreux que le forfait d'appels nationaux et internationaux. Pour découvrir le nombre de minutes disponibles pour chaque pays/région, consultez la section Forfaits d'appels dans [Pays et régions dans lesquels l'audioconférence et les forfaits d'appels sont disponibles](https://docs.microsoft.com/en-uscountry-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).

En règle générale, tous les utilisateurs d'une organisation n'ont pas besoin de passer des appels internationaux. La flexibilité d'abonnement et d'attribution du type de forfait d'appels le plus approprié en fonction des exigences professionnelles de chaque employé permet à votre organisation de contrôler les coûts d'implémentation des forfaits d'appels.

Pour chaque client Office 365, le nombre de minutes d'appels combiné est regroupé par pays ou région et par type de forfait d'appels. Une fois que le client a atteint la limite de minutes d'appels mensuelles, le service de forfaits d'appels (à l'exception des appels d'urgence) est suspendu jusqu'à la fin du mois. Les services de forfaits d'appels sont automatiquement disponibles le premier jour du mois calendaire suivant.

Pour permettre aux utilisateurs de passer des appels extérieurs une fois les minutes d'appels écoulées sans devoir attendre le mois suivant (cycle de facturation suivant), vous pouvez configurer des crédits de communication pour votre organisation. Les [crédits de communication](https://docs.microsoft.com/en-us/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits) permettent également aux utilisateurs possédant un forfait d'appels nationaux de passer des appels internationaux sur le principe du paiement à la minute.

Le premier élément à prendre en compte lors de l’implémentation de crédits de communication est de décider du montant initial des fonds à acheter. Les montants de financement recommandés peuvent être obtenus dans l'article sur les [crédits de communication](https://docs.microsoft.com/en-us/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits).

Si votre organisation choisit d'utiliser la recharge automatique, une recommandation sur le déclencheur (montant des fonds le moins élevé) est également incluse dans l'article sur les [crédits de communication](https://docs.microsoft.com/en-us/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits). Le montant de la recharge automatique doit être déterminé par l’utilisation réelle. L'utilisation des crédits de communication doit être régulièrement contrôlée et le montant de la recharge doit être ajusté en fonction des besoins.

L'utilisation des crédits de communication est contrôlable au niveau de chaque utilisateur pour vous permettre de satisfaire les exigences professionnelles spécifiques à chaque employé de l'organisation.

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Points de décision|<ul><li>Si votre organisation ne dispose pas de la licence de système téléphonique requise, déterminez si la licence de système téléphonique sera acquise en passant à des niveaux d'abonnement Office 365 supérieurs ou en achetant des compléments pour le système téléphonique.</li><li>Déterminez les utilisateurs qui requièrent une licence de forfait d'appels nationaux et les utilisateurs nécessitant une licence de forfait d'appels nationaux et internationaux</li><li>Déterminez si des crédits de communication sont requis pour l'implémentation des forfaits d'appels. Si c’est le cas, déterminez le montant initial des fonds qui doit être acheté. Le cas échéant, déterminez le montant déclencheur et celui de la recharge automatique.</li><li>Déterminez les utilisateurs qui requièrent l'utilisation d'une licence de crédits de communication.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Étapes suivantes|<ul><li>Documentez les utilisateurs auxquels la licence de système téléphonique sera attribuée avec la licence de forfait d'appels nationaux, ainsi que les utilisateurs auxquels la licence de système téléphonique sera attribuée avec la licence de forfait d'appels nationaux et internationaux.</li><li>Documentez le plan de crédits de communication (montant initial, montant déclencheur, montant de la recharge automatique).</li><li>Consignez les utilisateurs pour lesquels la licence de crédits de communication doit être activée.</li></ul>|

> [!TIP]
> Vous pouvez documenter la liste d'attribution des licences du système téléphonique avec les utilisateurs des forfaits d'appels à l'aide de l'exemple suivant :
>|Utilisateur  |Bureau  |Licence Office 365  |Crédits de communication  |
>|---------|---------|---------|---------|
>|Emily Braun|32 London Bridge Street|Office 365 E5, forfait d'appels nationaux et internationaux|Activé|
>|Lidia Holloway|32 London Bridge Street|Office 365 E5, forfait d'appels nationaux|Désactivé|
>|Pradeep Gupta|32 London Bridge Street|Office 365 E5, forfait d'appels nationaux|Activé|
>|Marcel Beauchamp|39 quai du Président Roosevelt|Office 365 E3, compléments du système téléphonique, forfait d'appels nationaux|Désactivé|
>|Rachelle Cormier|39 quai du Président Roosevelt|Office 365 E5, forfait d'appels nationaux et internationaux|Activé|
>|Isabell Potvin|39 quai du Président Roosevelt|Office 365 E3, compléments du système téléphonique, forfait d'appels nationaux|Désactivé|

<br>
> [!TIP]
> Vous pouvez documenter les numéros de planification de vos crédits de communication comme suit :
>|         |         |
>|---------|---------|
>|Montant initial|1 000 $|
>|Montant déclencheur|400 $|
>|Montant de la recharge automatique|TBA|

## <a name="phone-numbers-and-emergency-locations"></a>Numéros de téléphone et emplacements d'urgence

Avec les forfaits d'appels dans Office 365, chaque utilisateur de votre organisation doit posséder un numéro de téléphonique DID (sélection directe à l'arrivée) unique et une [adresse d'urgence validée](https://docs.microsoft.com/en-us/skypeforbusiness/what-are-calling-plans-in-office-365/what-are-emergency-locations-addresses-and-call-routing) correspondante.

Il est possible d'obtenir les numéros de téléphone [directement auprès de Microsoft](https://docs.microsoft.com/en-us/SkypeForBusiness/what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization) ou de [transférer à Microsoft](https://docs.microsoft.com/en-us/SkypeForBusiness/what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365) des numéros existants.

> [!NOTE]
> Le transfert de numéros de téléphone vers Microsoft est plus ou moins complexe selon les pays ou régions, les opérateurs, le nombre de circuits concernés et de nombreux autres facteurs. Pour planifier un transfert de numéros de téléphone, consultez le [Guide de transfert de numéros](https://go.microsoft.com/fwlink/?linkid=859011) pour en savoir plus.

Pour obtenir des numéros de téléphone directement auprès de Microsoft, utilisez l'une des options suivantes :

- [Centre d'administration Skype Entreprise](https://docs.microsoft.com/en-us/SkypeForBusiness/what-are-calling-plans-in-office-365/getting-phone-numbers-for-your-users)
- [Applets de commande de Windows PowerShell à distance](https://docs.microsoft.com/powershell/module/skype/?view=skype-ps)
- [Envoyer un formulaire nouvelle demande de numéro de téléphone](https://docs.microsoft.com/en-us/SkypeForBusiness/what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization).

Le formulaire de demande de nouveau numéro de téléphone convient mieux à l'acquisition d'un numéro de téléphone planifié car vous pouvez demander un ensemble de numéros de téléphone consécutifs. L'obtention de numéros de téléphone à l'aide du centre d'administration Skype Entreprise ou de Windows PowerShell à distance n'est pas disponible dans tous les pays ou régions.

Les deux premières méthodes (centre d'administration Skype Entreprise ou Windows PowerShell à distance) ne fonctionneront pas pour l'acquisition instantanée et ponctuelle d'un numéro de téléphone et lorsqu'un ensemble de numéros de téléphone consécutifs n'est pas indispensable.

> [!NOTE]
> Le [nombre de numéros de téléphone](https://docs.microsoft.com/en-us/SkypeForBusiness/what-are-calling-plans-in-office-365/how-many-phone-numbers-can-you-get) pouvant être acquis auprès de Microsoft est limité en fonction du nombre de licences de forfait d'appels souscrites par votre organisation. Pour les numéros de téléphone utilisateur (abonné), la formule est (nombre de licences de forfait d'appels nationaux + de forfait d'appels nationaux et internationaux) x 1,1 +10. Par exemple, si vous comptez 50 utilisateurs avec licence de forfait d'appels, vous pouvez acquérir 65 numéros de téléphone ((50 x 1,1) + 10).

Lors de la configuration des numéros de téléphone pour les forfaits d'appels, une adresse d'urgence doit être affectée à chaque numéro de téléphone avant toute attribution à un utilisateur. Cela est obligatoire pour prendre en charge les appels d'urgence. L'adresse d'urgence doit être validée pour garantir la reconnaissance de l'adresse d'urgence et s'assurer que son format est approprié et compatible avec une utilisation par les services d'intervention d'urgence.

> [!IMPORTANT]
> Les appels des services d'urgence fonctionnent différemment avec le service de forfaits d'appels par rapport aux services téléphoniques traditionnels. Il est important que vous compreniez ces différences et que vous les communiquiez à tous les utilisateurs. Consultez [Conditions générales relatives aux appels d'urgence](https://docs.microsoft.com/en-us/SkypeForBusiness/legal-and-regulatory/emergency-calling-terms-and-conditions) pour en savoir plus.

En plus d'une adresse d'urgence validée, les emplacements d'urgence peuvent être définis et associés à une adresse d'urgence validée pour indiquer plus précisément l'emplacement d'une adresse. Un emplacement d'urgence correspond généralement à un numéro de bâtiment, un étage, une aile de bâtiment ou un numéro de bureau où se trouve l'utilisateur.

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Points de décision|<ul><li>Déterminez comment les numéros de téléphone seront obtenus pour les emplacements des utilisateurs ou les bureaux concernés par l'implémentation des forfaits d'appels (les obtenir auprès de Microsoft ou transférer des numéros de téléphone existants).</li><li>Si vous choisissez de les obtenir auprès de Microsoft, décidez de la méthode pour les obtenir (envoi de formulaire ou automatisé) pour les emplacements des utilisateurs ou les bureaux concernés par l'implémentation des forfaits d'appels.</li><li>Déterminez la granularité des informations sur les emplacements d'urgence à collecter relatifs aux emplacements des utilisateurs ou des bureaux concernés par l'implémentation des forfaits d'appels.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Étapes suivantes|<ul><li>Documentez le plan général d'acquisition de numéros de téléphone, en détaillant comment les numéros de téléphone seront obtenus pour chaque emplacement d'utilisateur ou bureau concerné par l'implémentation des forfaits d'appels.</li><li>Le cas échéant, remplir <a href="https://docs.microsoft.com/en-us/SkypeForBusiness/what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization">le formulaire de demande de nouveau numéro de téléphone</a> (un formulaire par emplacement ou bureau)</li><li>Si vous choisissez de transférer des numéros de téléphone existants, consultez le <a href="https://go.microsoft.com/fwlink/?linkid=859011">Guide de transfert de numéros</a> pour le planifier et ajuster le planning d'implémentation des forfaits d'appels en conséquence.</li><li>Documentez de manière détaillée l'adresse d'urgence et les emplacements d'urgence relatifs à l'emplacement de chaque utilisateur ou bureau concerné par l'implémentation des forfaits d'appels</li></ul>

> [!TIP]
> Les détails relatifs à l'acquisition des numéros de téléphone, aux numéros de téléphone et aux emplacements d'urgence sont documentables à l'aide du modèle suivant :
>|Utilisateur  |Adresse et emplacement d'urgence  |Acquisition du numéro de téléphone  |Numéro de téléphone  |
>|---------|---------|---------|---------|
>|Emily Braun|1034/32 London Bridge Street, Londres, SE1, Royaume-Uni|Port existant|+44 20 7946 0034|
>|Lidia Holloway|1023/32 London Bridge Street, Londres, SE1, Royaume-Uni|Port existant|+44 20 7946 0065|
>|Pradeep Gupta|1023/32 London Bridge Street, Londres, SE1, Royaume-Uni|Port existant|+44 20 7946 0023|
>|Marcel Beauchamp|07E15D/39 quai du Président Roosevelt, 92130 Issy-les-Moulineaux, France|Acquérir|TBA|
>|Rachelle Cormier|07E15D/39 quai du Président Roosevelt, 92130 Issy-les-Moulineaux, France|Acquérir|TBA|
>|Isabell Potvin|07E15D/39 quai du Président Roosevelt, 92130 Issy-les-Moulineaux, France|Acquérir|TBA|

## <a name="voicemail"></a>Messagerie vocale

La messagerie vocale du système téléphonique, avec le service de boîte vocale d'Azure, prend uniquement en charge le dépôt des messages vocaux dans la messagerie Exchange. Aucun système de messagerie électronique tiers n'est pris en charge.

La messagerie vocale du système téléphonique fonctionne par défaut avec Exchange Online. Elle prend toutefois en charge un [modèle de déploiement et une version Exchange locale minimum](https://support.microsoft.com/help/3195158/customer-issues-between-exum-and-azure-voicemail) pour garantir la livraison de messages vocaux aux messageries vocales des utilisateurs dans le déploiement local d'Exchange.

La messagerie vocale du système téléphonique intègre la transcription des messages vocaux. Elle est activée par défaut pour tous les utilisateurs de votre entreprise. Dans certains cas, votre entreprise peut exiger la désactivation de la transcription des messages vocaux pour des utilisateurs particuliers ou à l'échelle de l'organisation.

> [!NOTE]
> Un mécanisme de secours a été implémenté permettant à la messagerie vocale du système téléphonique de renvoyer des messages via SMTP. Ainsi les utilisateurs qui possèdent une messagerie électronique sur un système tiers recevront les messages vocaux. La disponibilité du service et d'autres fonctionnalités de la messagerie vocale, notamment la modification des messages d'accueil et d'autres paramètres, n'est pas garantie.

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Points de décision|<ul><li>Déterminez si la messagerie vocale du système téléphonique sera activée pour l'implémentation des forfaits d'appels.</li><li>Si vous utilisez Exchange sur site et que le déploiement existant n'est pas conforme aux exigences de prise en charge de la messagerie vocale du système téléphonique, déterminez les options disponibles (mise à niveau et configuration de l'assistance de la messagerie vocale du système téléphonique ou migration vers Exchange Online avec le recours à un mécanisme de secours).</li><li>Déterminez si la transcription des messages vocaux doit être activée/désactivée dans l'organisation ou pour des utilisateurs spécifiques.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Étapes suivantes|<ul><li>Le cas échéant, documentez les points de décision Exchange relatifs à la prise en charge de la messagerie vocale du système téléphonique.</li><li>Si la messagerie vocale et la transcription de la messagerie vocale ne doivent pas être activées pour tous les utilisateurs, documentez les utilisateurs pour lesquels la messagerie vocale et la transcription de la messagerie vocale doivent être activées.</li></ul>|

> [!TIP]
> Vous pouvez documenter les détails relatifs à la messagerie vocale du système téléphonique concernant l'implémentation d'un système téléphonique avec forfaits d'appels comme suit :
>|Utilisateur  |Boîte de messagerie Exchange  |Activer la messagerie vocale  |Transcription de la messagerie vocale  |
>|---------|---------|---------|---------|
>|Emily Braun|En ligne|Oui|Activé|
>|Lidia Holloway|En ligne|Oui|Activé|
>|Pradeep Gupta|Local|Oui|Activé|
>|Marcel Beauchamp|Local|Oui|Désactivé|
>|Rachelle Cormier|En ligne|Oui|Désactivé|
>|Isabell Potvin|Local|Oui|Désactivé|

## <a name="calling-identity"></a>Identité d'appel

Par défaut, tous les appels sortants utilisent le numéro de téléphone attribué en tant qu'identité d'appel (ID de l'appelant). Le destinataire de l'appel peut rapidement identifier l'appelant et décider d'accepter ou de refuser l'appel. Dans certains cas, des exigences professionnelles légitimes imposent de masquer l'ID de l'appelant pour protéger l'identité de l'appelant au moyen d'un numéro de ligne professionnelle principal (il s'agit généralement d'un numéro de service géré par la configuration d'un [standard automatique](https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants)) utilisé en tant qu'ID de l'appelant ou pour bloquer totalement la présentation de l'ID de l'appelant.

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Points de décision|<ul><li>Déterminez si la manipulation de l'ID de l'appelant est requise pour l'implémentation des forfaits d'appels.</li><li>Le cas échéant, déterminez les types de manipulations de l'ID de l'appelant (masquage avec numéro de service ou anonymisation) à implémenter.</li><li>Le cas échéant, déterminez l'utilisateur nécessitant une manipulation de l'ID de l'appelant et le type de cette dernière à attribuer à chaque utilisateur.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Étapes suivantes|<ul><li>Documentez les utilisateurs auxquels affecter une manipulation de l'ID de l'appelant et le type de manipulation applicable à chaque utilisateur.</li></ul>|

> [!TIP]
> Voici un exemple de modèle de documentation des détails de l'ID de l'appelant :
>|Utilisateur  |Activer le masquage de l'ID de l'appelant sortant  |Type de masquage de l'ID de l'appelant  |Autoriser le remplacement de l'utilisateur  | Activer le masquage de l'ID de l'appelant entrant  |
>|---------|---------|---------|---------|---------|
>|Emily Braun|Non|N/A|Oui|Non|
>|Lidia Holloway|Oui|Numéro de service (OrgAA, +44 20 7946 0000)|Non|Oui|
>|Pradeep Gupta|Non|N/A|Oui|Non|
>|Marcel Beauchamp|Oui|Numéro de service (OrgAA, TBA)|Non|Oui|
>|Rachelle Cormier|Oui|Anonymiser|Oui|Non|
>|Isabell Potvin|Oui|Numéro de service (OrgAA, TBA)|Non|Oui|

## <a name="dial-plans"></a>Plan de numérotation

Un [Plan de numérotation](https://docs.microsoft.com/en-us/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-dial-plans), une fonctionnalité du système téléphonique d'Office 365, est un ensemble de règles de normalisation qui convertit les numéros de téléphone composés dans un autre format (généralement le format [E.164](https://go.microsoft.com/fwlink/?linkid=859014)) pour l'autorisation et le routage des appels. 

Un plan de numérotation permet aux utilisateurs de composer des numéros de téléphone comme ils le font habituellement, par exemple en omettant l'indicatif régional pour les appels locaux, l'indicatif du pays ou de la région pour les appels nationaux ou même en composant un numéro court lorsqu'ils passent un appel.

La fonctionnalité de système téléphonique d’Office 365 comporte deux types de plans de numérotation :

-   **Plan de numérotation de service**. Il s’agit du plan de numérotation par défaut, qui est appliqué aux utilisateurs selon l’emplacement d’utilisation d’Office 365, et il ne peut pas être modifié.
-   **Plan de numérotation de client**. Ce plan de numérotation peut être personnalisé au sein d'un client, et divisé en deux types :
    -   **Plan de numérotation de client global** : ce plan de numérotation s’applique à tous les utilisateurs au sein du client.
    -   **Plan de numérotation d’utilisateurs du client** : ce plan de numérotation s’applique uniquement à des utilisateurs spécifiques.

> [!NOTE]
> Consultez [Que sont les plans de numérotation ?](https://docs.microsoft.com/en-us/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-dial-plans) pour en savoir plus et découvrir des exemples.

Le plan de numérotation efficace affecté aux utilisateurs est la combinaison du plan de numérotation de service (basé sur l’emplacement d’utilisation d’Office 365 des utilisateurs) et du plan de numérotation de client (il peut s’agir d’un plan de numérotation de client.global ou d'un plan de numérotation d’utilisateurs du client).

![Le tableau présente trois combinaisons de plans de numérotation de client et de service.](media/audio_conferencing_image8.png)

Il existe 25 règles de normalisation au maximum dans chaque plan de numérotation de client, et le double emploi des règles de normalisation déjà disponibles dans le plan de numérotation de service doit donc être évité.

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Points de décision|<ul><li>Déterminez si votre organisation requiert des plans de numérotation personnalisés (besoins de l'organisation, exigences en matière d'adoption, etc.).</li><li>Le cas échéant, déterminez la portée du plan de numérotation de client (global au sein du client ou utilisateurs du client) pour prendre en charge les exigences des plans de numérotation personnalisés.</li><li>Le cas échéant, déterminez les plans de numérotation de client qui seront créés pour prendre en charge les emplacements des utilisateurs ou les bureaux concernés par l'implémentation des forfaits d'appels.</li><li>Le cas échéant, déterminez le plan de numérotation personnalisé et le plan de numérotation de client qui doit être affecté à chaque utilisateur.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Étapes suivantes|<ul><li>Consignez les plans de numérotation personnalisés et les règles de normalisation associées à configurer dans le cadre de l'implémentation des forfaits d'appels.</li><li>Consignez les utilisateurs auxquels le plan de numérotation personnalisé sera affecté et le plan de numérotation de client qui doit être affecté à chaque utilisateur.</li></ul>|

> [!TIP]
> Si cela est applicable à votre projet, vous pouvez utiliser les modèles suivants pour documenter les configurations de plans de numérotation de client :
>|Nom du plan de numérotation de client<br>_Description  |Nom des règles de normalisation<br>_Description_  |Modèle<br>Conversion<br>IsInternalExtension  |
>|---------|---------|---------|
>|**FR-Paris-Issy-39qdPR**<br>_39 quai du Président Roosevelt Issy-les-Moulineaux, plan de numérotation France_|**FR-39qdPR-Internal**<br>_Numéro interne (x7000 – x7999) du bureau 39 quai du Président Roosevelt, Issy-les-Moulineaux, France_|^(7\d{3})$<br>+3319999$1<br>True|
>||**FR-TollFree**<br>_Normalisation du numéro gratuit pour la France_|^ 0?(80\d{7}) \d*$<br>+33$1<br>False|
>||**FR-Service**<br>_Normalisation du numéro de service pour la France_|^ (1\d{1,2}\|11 [68] \d{3}\|10\d{2}\|3\d{3}) $<br>$1<br>False|

<br>
> [!TIP]
> Le modèle d'exemple ci-après peut être utilisé pour documenter les attributions de plan de numérotation afin de prendre en charge votre projet :
>|Utilisateur  |Bureau  |Type de plan de numérotation  |Nom du plan de numérotation  |
>|---------|---------|---------|---------|
>|Emily Braun|32 London Bridge Street|Plan de numérotation de service|N/A|
>|Lidia Holloway|32 London Bridge Street|Plan de numérotation de service|N/A|
>|Pradeep Gupta|32 London Bridge Street|Plan de numérotation de service|N/A|
>|Marcel Beauchamp|39 quai du Président Roosevelt|Plan de numérotation de client|FR-Paris-Issy-39qdPR|
>|Rachelle Cormier|39 quai du Président Roosevelt|Plan de numérotation de client|FR-Paris-Issy-39qdPR|
>|Isabell Potvin|39 quai du Président Roosevelt|Plan de numérotation de client|FR-Paris-Issy-39qdPR|

## <a name="document-technical-implementation-plan"></a>Documenter le plan d’implémentation technique

Utilisez les points de décision ci-dessus pour documenter votre plan d’implémentation technique.
Ce plan d'implémentation technique fournira l'équipe du projet, qui peut inclure FastTrack ou un partenaire de déploiement, avec les informations nécessaires pour exécuter l'intégration technique pour l'implémentation des systèmes téléphoniques avec forfaits d'appels.

Généralement, un plan d’implémentation technique contiendra les sections principales suivantes :

-   Liste d'habilitation des sites pour les systèmes téléphoniques avec forfaits d'appels

-   Attribution d'une licence aux utilisateurs de système téléphonique avec forfaits d'appels

-   Numéros de planification de crédits de communication

-   Détails relatifs à l'acquisition des numéros de téléphone, aux numéros de téléphones et aux emplacements d'urgence

-   Détails sur la configuration de la messagerie vocale

-   Détails de la configuration du masquage de l'ID de l'appelant

-   Plans de numérotation de client

-   Affectations du plan de numérotation

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

[Configurer des forfaits d'appels](https://docs.microsoft.com/en-us/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

[Guide de démarrage rapide : Configuration des forfaits d'appels dans Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/configuring-teams-calling-quickstartguide)
