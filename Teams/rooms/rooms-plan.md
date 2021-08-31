---
title: Planifier les Salles Microsoft Teams
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: b4e0ad1e-12e5-4130-aec1-d8c9cd3a5965
ms.collection:
- M365-collaboration
- m365initiative-meetings
description: Cet article décrit les considérations pertinentes en rapport avec la planification du déploiement d Salles Microsoft Teams, de la prochaine génération de systèmes Skype de salle.
ms.openlocfilehash: 70fd1fabd416628fac4b934c2db5700f4e0f36c0
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58727803"
---
# <a name="plan-microsoft-teams-rooms"></a>Planifier Salles Microsoft Teams

Cet article propose une approche de bout en bout de la planification, de la livraison et de l’exploitation des Salles Microsoft Teams dans le cadre de votre stratégie globale de réunion et de salle de conférence.

Vous trouverez ci-dessous des informations de planification sur l’approche recommandée et les principales décisions à prendre, ainsi que des liens vers des informations techniques à l’appui. Nous vous recommandons de passer en revue les sections Plan, Déployer et Gérer, même si vous êtes déjà entièrement déployé.

## <a name="overview-of-microsoft-teams-rooms"></a>Vue d’ensemble des Salles Microsoft Teams

Salles Microsoft Teams fournit une expérience de réunion complète qui apporte de la vidéo HD, de l’audio et du partage de contenu aux réunions de toutes tailles, des petites salles de réunion jusqu’aux grandes salles de conférence.

![Une console, un microphone et un grand écran sont installés sur un mur de salle de conférence pour illustrer les éléments d’un exemple Salles Microsoft Teams configuration.](../media/room-systems-image1.png "Une console, un microphone et un grand écran sont installés sur un mur de salle de conférence pour illustrer les éléments d’un exemple Salles Microsoft Teams configuration.")

[Salles Microsoft Teams’aide](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) est une ressource très utile pour en savoir plus sur Salles Microsoft Teams et la manière dont elle peut ajouter de la valeur dans le cadre de votre déploiement. Par ailleurs, nous vous recommandons de regarder cette [vidéo de présentation.](https://youtu.be/tNey5KZVCl0) 

## <a name="microsoft-teams-rooms-components"></a>Salles Microsoft Teams composants

Salles Microsoft Teams comprend les composants clés suivants pour offrir une expérience utilisateur excellente :

- Panneau de contrôle de l’écran tactile
- Compute
- Salles Microsoft Teams application
- Station d’accueil/extension
- Périphériques (caméra, microphone, haut-parleur)
- Écrans externes (maximum deux)
- Entrée HDMI

Vous pouvez obtenir ces composants en tant qu’offres groupées préinstallées auprès d’un certain nombre de fournisseurs, ou acheter les composants pris en charge individuellement en suivant les exigences de cet [article.](requirements.md)

Outre la combinaison Surface Pro/station d’accueil, vous pouvez également acheter des Salles Microsoft Teams avec le panneau de contrôle à écran tactile, le calcul, l’ancre et les principaux périphériques intégrés. 

En règle générale, les offres groupées et les unités intégrées incluent les logiciels préinstallés, tandis que si vous achetez des composants pris en charge individuellement pour les systèmes Surface Pro, vous devez installer le logiciel. Pour obtenir des instructions sur [l’installation des logiciels sur les appareils, consultez cet article.](rooms-scale.md) 

Vous pouvez déployer des déploiements Salles Microsoft Teams avec Microsoft Teams, Skype Entreprise Online ou Skype Entreprise déploiements hybrides ou locaux.  Consultez la [Teams Salle de réunion mise à jour des](rooms-licensing.md) licences pour plus d’informations sur les licences nécessaires.

| &nbsp;   |  &nbsp;   |
|-----------|------------|
|![décider du déploiement.](../media/audio_conferencing_image7.png) <br/>Points de décision|<ul><li>Allez-vous déployer Salles Microsoft Teams dans votre organisation ? </li><li>Comment allez-vous obtenir vos systèmes Salles Microsoft Teams-groupés, comme des composants distincts ou en tant qu’unité intégrée ?</li></ul> |
| ![identifiez les activités.](../media/audio_conferencing_image9.png)<br/>Étapes suivantes | <ul><li>Identifiez qui entreprendrea les activités clés tout au long de votre déploiement.</li><li>Examinez les salles de réunion dont vous disposez (et prévoyez de les configurer) pour comprendre où vous voulez déployer Salles Microsoft Teams et les périphériques appropriés à la taille de la salle.</li></ul> |
| | |

## <a name="identify-who-will-undertake-the-key-activities-throughout-your-deployment"></a>Identifier qui entreprendrea les activités clés tout au long de votre déploiement

Utilisez l’approche illustrée ci-dessous pour vous guider tout au long de votre déploiement et personnaliser les exemples de sorties fournis dans ces articles au besoin pour votre organisation.

Commencez par comprendre les salles de conférence dont vous disposez et souhaitez savoir ce qui pourrait vous être le plus approprié à l’avenir, puis passer par la sélection et la mise en service de l’équipement dont vous avez besoin, la préparation de vos sites, la configuration et le déploiement de votre service, la gestion des changements et l’adoption par les utilisateurs, et le développement d’opérations et de procédures de maintenance.

![Commencez par comprendre ce que vous avez et élaborez ce qui pourrait vous être le plus approprié, puis avancez dans la sélection et la mise en service de l’équipement dont vous avez besoin, préparez vos sites, configurez et déployez votre service, gérez les changements et l’adoption par les utilisateurs, et développez des opérations et des procédures de maintenance.](../media/room-systems-image2.png "Commencez par comprendre ce que vous avez et élaborez ce qui pourrait vous être le plus approprié, puis avancez dans la sélection et la mise en service de l’équipement dont vous avez besoin, préparez vos sites, configurez et déployez votre service, gérez les changements et l’adoption par les utilisateurs, et développez des opérations et des procédures de maintenance.")

Vous devrez peut-être coordonner ces activités au sein de plusieurs équipes. Nous fournissons une vue d’ensemble des principales activités que vous devez couvrir, ainsi que des suggestions pour les équipes qui sont généralement impliquées dans le déploiement et la gestion des systèmes de salle de conférence, pour vous aider à déterminer les personnes avec qui vous devez travailler.

| Tâche                       | Qui pouvez entreprendre la tâche           | Affecté à | Liens vers ce contenu |
|----------------------------|----------------------------------------|-------------|-----------------------|
| Salles d’inventaire            | Installations / équipe AV / Équipe Project services Project’équipe |             | [Planification de l’inventaire des salles et des fonctionnalités](#room-inventory-and-capability-planning)        |
| Planifier les fonctionnalités          | Équipe Project des Project l’it                        |             | [Planification de l’inventaire des salles et des fonctionnalités](#room-inventory-and-capability-planning)                       |
| Sélection de l’appareil           | Équipe Project it/AV              |             | [Sélection de l’appareil](#device-selection)                      |
| Approvisionnement                | Équipe Project it/AV              |             | [Approvisionnement](#procurement)                      |
| État de préparation du site             | Installations / équipe AV / Équipe Project services Project’équipe |             | [État de préparation du site](rooms-deploy.md#site-readiness)                      |
| Préparation du service          | Équipe Project des Project l’it                        |             | [Préparation du service](rooms-deploy.md#service-readiness)                      |
| Configuration              | Équipe Project des Project l’it                        |             | [Configuration et déploiement](rooms-deploy.md#configuration-and-deployment)                      |
| Déploiement                 | Installations / équipe AV / Équipe Project services Project’équipe |             | [Liste de contrôle du déploiement](console.md#microsoft-teams-rooms-deployment-checklist)                      |
| Adoption                   | Installations / équipe AV / Équipe Project services Project’équipe |             | [Adoption](#plan-for-adoption-and-change-management)                      |
| Maintenance et opérations | Équipe AV / Équipe de Project de l’it              |             | [Vue d’ensemble de la gestion](rooms-manage.md)                      |


## <a name="room-inventory-and-capability-planning"></a>Planification de l’inventaire des salles et des fonctionnalités

La première étape consiste à inventorier les salles de réunion et de conférence existantes de votre organisation afin de comprendre leur environnement, leur taille, leur disposition et leur objet, et d’identifier les fonctionnalités dont vous souhaitez que chaque salle dans l’étendue soit à l’avenir, telles que les fonctionnalités de collaboration enrichies qui seront activées dans la salle. 

Après avoir créé l’inventaire de l’équipement et des fonctionnalités de chaque salle existante, les exigences relatives à cette salle s’inséront dans la planification de la sélection de votre appareil pour créer une solution de conférence enrichie. Les qualités (audio et vidéo) nécessaires pour chaque salle, en plus de la taille et de l’objectif de la salle, jouent un rôle important dans la décision de la solution la plus appropriée pour chaque salle. 

Dans le cadre de votre découverte, il est important de tenir compte de l’acoustique et de la disposition de la pièce. Par exemple, vérifiez que les chaises dans la salle ne bloquent pas la vue de la caméra. Vérifiez que la pièce n’a pas d’écho excessif ni de panne de l’air bruyant, et qu’elle est suffisamment puissant pour les écrans et les Salles Microsoft Teams. Il existe de nombreux facteurs à prendre en compte pour que votre équipe ou partenaire audio-visuel (AV) soit en mesure de vous en conseiller. 

| &nbsp;   | &nbsp;    |
|-----------|------------|
| ![deplyment rooms.](../media/audio_conferencing_image9.png)<br/>Étapes suivantes|<ul><li>Examinez les salles dans l’étendue et définissez Salles Microsoft Teams configuration pour elles.</li></ul>|

_Exemple d’inventaire des salles de réunion/conférence_

| Site  | Nom de la salle | Type de salle | Nombre de personnes  | Dans l’étendue ? | Fonctionnalités actuelles des salles       | Capacités des salles à venir     |
|-----------|---------------|---------------|-----------------------|--------------|-------------------------------------|----------------------------------------------------------|
| London HQ | Sy         | Moyen        | 6 &ndash; 12                  | Oui          | Haut-parleur                        | 1 écran, audio et vidéo plus présentation<br>Accès PSTN |
| Sydney HQ | Hill          | Grande         | 12 &ndash; 16                 | Oui          | Unité AV héritée, 1 écran et appareil photo | 2 écrans, audio et vidéo plus présentation<br>Accès PSTN |

## <a name="device-selection"></a>Sélection de l’appareil 

Évaluez Salles Microsoft Teams solution la plus adaptée à chaque salle en fonction des capacités futures que vous souhaitez pour la salle. Déterminez les périphériques AV qui s’adaptent le mieux, selon la taille de la pièce et la disposition. 

Pour obtenir des instructions sur le type d’appareils système et périphériques par type et taille de salle, voir l’article [Salles Microsoft Teams la demande de](requirements.md) salle. 

En fonction du fournisseur que vous préférez, utilisez les informations fournies dans l’article sur la configuration requise pour définir votre Salles Microsoft Teams et la configuration des périphériques par type de salle, et utilisez-la comme modèle pour votre déploiement. 

**Pro conseil : certains** types de salle peuvent ne pas être applicables à votre déploiement.

| &nbsp;   |  &nbsp;   |
|-----------|------------|
| ![salles dans l’étendue.](../media/audio_conferencing_image7.png) <br/>Points de décision|<ul><li>À partir de votre inventaire, quels types de salles sont dans l’étendue de votre déploiement ?</li><li>Quels systèmes allez-vous déployer pour chaque type de salle ?</li></ul>|
| ![rassembler du matériel.](../media/audio_conferencing_image9.png)<br/>Étapes suivantes|<ul><li>Commencez à rassembler les ressources opérationnelles clés pour les systèmes que vous avez choisis, et impliquez votre équipe d’approvisionnement.</li></ul>|

_Exemple Salles Microsoft Teams modèle de déploiement pour votre organisation_

| **Type/taille de salle** | **Nombre de personnes**  | **Salles Microsoft Teams système informatique** | **Périphériques**  | **Affichage(s)** |
|----------------------|-----------------------|----------------------------------|-------------------------|-----------------|
| Focus 10' par 9'      | 2 &ndash; 4                   |                                  |                         |                 |
| Petite taille : 16' par 16'     | 4 &ndash; 6                   |                                  |                         |                 |
| Moyen 18' par 20'    | 6 &ndash; 12                  |                                  |                         |                 |
| Grand 15' par 32'     | 12 &ndash; 16                 |                                  |                         |                 |

**Pro conseil –** C’est le moment idéal pour commencer à collecter des informations sur Salles Microsoft Teams solution que vous avez choisie.

## <a name="procurement"></a>Approvisionnement 

Vous pouvez obtenir le système que vous avez choisi en tant qu’offre groupée ou solution intégrée via des partenaires d’appareils. Vous pouvez également acquérir une station d’accueil d’appareil partenaire et préparer votre propre solution Salles Microsoft Teams à l’aide d’un appareil Surface Pro et de périphériques _AV_ existants pris en charge. 

Vous pouvez faire l Salles Microsoft Teams de nombreux partenaires répertoriés dans [l’article requis.](requirements.md) Visitez les sites web des partenaires pour en savoir plus sur ces solutions et les options d’approvisionnement. 

En fonction de l’échelle et de l’approche de déploiement, vous pouvez décider d’expédier les périphériques Salles Microsoft Teams pris en charge vers un emplacement central pour la configuration initiale et l’affectation. Il peut s’agit d’une bonne approche pour un déploiement par étape sur de nombreux sites. Vous pouvez également décider d’expédier les offres groupées directement sur vos sites. 

|   &nbsp; |  &nbsp;   |
|-----------|------------|
| ![composants d’expédition.](../media/audio_conferencing_image7.png) <br/>Points de décision|<ul><li>Allez-vous expédier les composants directement à un site ou à une installation intermédiaire ?</li><li>Qui gérera l’installation intermédiaire (si vous décidez d’en utiliser une) ?</li></ul>|
| ![d’entreprise.](../media/audio_conferencing_image9.png)<br/>Étapes suivantes|<ul><li>Planifiez les opérations.</li><li>Planifier l’adoption et la gestion des changements.</li></ul>|

## <a name="plan-for-operations"></a>Planifier les opérations 

Votre organisation doit effectuer régulièrement la surveillance, l’administration et la gestion, et il est essentiel d’accepter qui entreprendrea ces tâches au tout début de votre déploiement. 

De nombreuses organisations ont une équipe av ou un partenaire qui gère leurs salles de conférence et leurs appareils. Cette équipe doit être impliquée afin d’accepter qui gérera les appareils Salles Microsoft Teams à l’avenir afin de surveiller les performances et de déployer les mises à jour logicielles et les correctifs logiciels. 

Pensez à la file d’attente de l’aide que vous allez router Salles Microsoft Teams Microsoft Teams Rooms</DICT__Salles⚐Microsoft⚐Teams> et les principales étapes de résolution des problèmes qu’elles peuvent suivre. L’aide de l’utilisateur [](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) et les problèmes connus constitue un bon point de départ pour cette [FAQ.](known-issues.md)

|  &nbsp;  |  &nbsp;   |
|-----------|------------|
| ![sélectionnez le responsable.](../media/audio_conferencing_image7.png) <br/>Points de décision|<ul><li>Décidez qui gérera Salles Microsoft Teams.</li><li>Déterminez la file d’attente du Salles Microsoft Teams vers laquelle router les appels associés.</li></ul>|
| ![préparer des comptes d’hôtes.](../media/audio_conferencing_image9.png)<br/>Étapes suivantes|<ul><li>Préparez les comptes d’hôtes. </li></ul>|


## <a name="plan-for-adoption-and-change-management"></a>Planifier l’adoption et la gestion des changements

Salles Microsoft Teams de nouveaux systèmes présentent de nouvelles fonctionnalités à vos utilisateurs. Il est important de reconnaître qu’il s’agit d’un changement pour vos utilisateurs, et vous devez vous assurer que votre campagne identifie les avantages que le nouveau système aura pour vos utilisateurs, et que les principaux points de discussion pourront les utiliser pour discuter avec leurs équipes. 

Envisagez de planifier des événements d’affichage et d’affiche sur chaque site pour informer vos utilisateurs des nouvelles fonctionnalités. Vous pouvez également créer des « guides de démarrage rapide » dans la salle. Songez à trouver un champion des réunions sur chaque site qui peut aider d’autres personnes à se mettre à niveau et à commencer à utiliser les appareils.
