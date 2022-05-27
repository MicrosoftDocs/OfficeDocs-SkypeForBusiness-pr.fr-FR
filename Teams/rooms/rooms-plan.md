---
title: Planifier les Salles Microsoft Teams
ms.author: czawideh
author: cazawideh
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
description: Cet article explique les considérations de planification pertinentes pour le déploiement de Salles Microsoft Teams, la prochaine génération de Skype Room Systems.
ms.openlocfilehash: 5dea2485221fa2755c567fd3ce619c232b4bb6a9
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65676136"
---
# <a name="plan-microsoft-teams-rooms"></a>Planifier Salles Microsoft Teams

Cet article présente une approche de bout en bout de la planification, de la prestation et du fonctionnement des Salles Microsoft Teams dans le cadre de votre stratégie globale de réunion et de salle de conférence.

Vous trouverez ci-dessous des informations de planification couvrant l’approche recommandée et les décisions clés que vous devez prendre, ainsi que des liens vers des informations techniques de prise en charge. Nous vous recommandons de consulter les sections Plan, Deploy et Manage, même si vous êtes déjà entièrement déployé.

## <a name="overview-of-microsoft-teams-rooms"></a>Vue d’ensemble de Salles Microsoft Teams

Salles Microsoft Teams offre une expérience de réunion complète qui offre un partage vidéo, audio et de contenu HD à des réunions de toutes tailles, des petites zones blotties aux grandes salles de conférence.

![Un utilisateur appuie sur une console salles Teams, avec un affichage en arrière-plan.](../media/room-systems-image1.jpg "Un utilisateur appuie sur une console salles Teams, avec un affichage en arrière-plan")
 [Salles Microsoft Teams aide](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) est une excellente ressource pour en savoir plus sur Salles Microsoft Teams et la façon dont elle peut ajouter de la valeur dans le cadre de votre déploiement.

## <a name="microsoft-teams-rooms-components"></a>composants Salles Microsoft Teams

Salles Microsoft Teams inclut les composants clés suivants pour offrir une expérience utilisateur optimale :

- Console à écran tactile
- Module de calcul
- application Salles Microsoft Teams
- Périphériques (caméra, microphone, haut-parleur)
- Écrans externes (maximum de deux)
- Entrée HDMI

Vous pouvez acheter ces composants en tant que bundles préinstallés auprès d’un certain nombre de fournisseurs, ou vous pouvez acheter les composants pris en charge individuellement en suivant les [exigences décrites dans cet article](requirements.md).

Vous pouvez déployer Salles Microsoft Teams avec des déploiements locaux Microsoft Teams ou Skype Entreprise.  Pour plus d’informations sur les licences nécessaires, consultez la [Teams Salle de réunion Mise à jour](rooms-licensing.md) des licences.

| &nbsp;   |  &nbsp;   |
|-----------|------------|
|![décider du déploiement.](../media/audio_conferencing_image7.png) <br/>Points de décision|<ul><li>Allez-vous déployer Salles Microsoft Teams dans votre organisation ? </li><li>Comment allez-vous acheter vos systèmes Salles Microsoft Teams ?</li></ul> |
| ![identifier les activités.](../media/audio_conferencing_image9.png)<br/>Étapes suivantes | <ul><li>Identifiez les personnes qui entreprendront les activités clés tout au long de votre déploiement.</li><li>Passez en revue les salles de réunion que vous avez (et prévoyez de configurer) pour comprendre où vous souhaitez déployer Salles Microsoft Teams et les périphériques appropriés pour la taille de la salle.</li></ul> |
| | |

## <a name="identify-who-will-undertake-the-key-activities-throughout-your-deployment"></a>Identifier les personnes qui entreprendront les activités clés tout au long de votre déploiement

Utilisez l’approche illustrée ci-dessous pour vous guider tout au long de votre déploiement et personnaliser les exemples de sorties fournis en fonction des besoins de votre organisation.

Commencez par comprendre les salles de conférence dont vous disposez et envisagez ce qui vous convient le mieux à l’avenir, puis passez à la sélection et à l’acquisition de l’équipement dont vous avez besoin, à la préparation de vos sites, à la configuration et au déploiement de votre service, à la gestion du changement et de l’adoption par l’utilisateur, et au développement d’opérations et de procédures de maintenance.

![Commencez par comprendre ce que vous avez et envisagez ce qui vous convient le mieux, puis passez à la sélection et à l’acquisition de l’équipement dont vous avez besoin, à la préparation de vos sites, à la configuration et au déploiement de votre service, à la gestion des modifications et de l’adoption des utilisateurs, au développement d’opérations et de procédures de maintenance.](../media/room-systems-image2.png "Commencez par comprendre ce que vous avez et envisagez ce qui vous convient le mieux, puis passez à la sélection et à l’acquisition de l’équipement dont vous avez besoin, à la préparation de vos sites, à la configuration et au déploiement de votre service, à la gestion des modifications et de l’adoption des utilisateurs, au développement d’opérations et de procédures de maintenance.")

Vous devrez peut-être coordonner ces activités entre plusieurs équipes. Nous fournissons une vue générale des principales activités que vous devez couvrir, ainsi que des suggestions pour les équipes qui sont généralement impliquées dans le déploiement et la gestion des systèmes de salle de conférence, pour vous aider à déterminer avec qui vous devez travailler.

| Tâche                       | Qui peut entreprendre la tâche           | Affecté à | Liens vers ce contenu |
|----------------------------|----------------------------------------|-------------|-----------------------|
| Salles d’inventaire            | Facilities / AV team / IT Project Team |             | [Inventaire des salles et planification des fonctionnalités](#room-inventory-and-capability-planning) |
| Fonctionnalités de planification          | Équipe de Project informatique                        |             | [Inventaire des salles et planification des fonctionnalités](#room-inventory-and-capability-planning) |
| Sélection de l’appareil           | Équipe it Project / AV              |             | [Sélection de l’appareil](#device-selection) |
| Marchés publics                | Équipe it Project / AV              |             | [Marchés publics](#procurement) |
| Préparation du site             | Facilities / AV team / IT Project Team |             | [Préparation du site](rooms-deploy.md#site-readiness) |
| Préparation du service          | Équipe de Project informatique                        |             | [Préparation du service](rooms-deploy.md#service-readiness) |
| Configuration              | Équipe de Project informatique                        |             | [Configuration et déploiement](rooms-deploy.md#configuration-and-deployment) |
| Déploiement                 | Facilities / AV team / IT Project Team |             | [Liste de vérification du déploiement](console.md#microsoft-teams-rooms-deployment-checklist) |
| Adoption                   | Facilities / AV team / IT Project Team |             | [Adoption](#plan-for-adoption-and-change-management) |
| Maintenance et opérations | Équipe AV / Équipe de Project informatique              |             | [Vue d’ensemble de la gestion](rooms-manage.md) |

## <a name="room-inventory-and-capability-planning"></a>Inventaire des salles et planification des fonctionnalités

La première étape consiste à inventorier les espaces de réunion et les salles de conférence existants de votre organisation pour comprendre leur environnement, leur taille, leur disposition et leur objectif. Vous pouvez ensuite identifier les fonctionnalités que vous souhaitez que chaque pièce ait, telles que les caméras intelligentes, le tableau blanc, la caméra de contenu, etc.

Après avoir créé un inventaire de l’équipement et des fonctionnalités dans chaque salle existante, vos besoins pour cette salle alimentent la planification de la sélection de votre appareil afin de créer une solution de conférence enrichie. Les modalités (audio, vidéo) nécessaires pour chaque salle, en plus de la taille et de l’objectif de la salle, jouent un rôle important dans la décision de la solution la plus appropriée pour chaque salle.

Dans le cadre de votre découverte, il est essentiel de prendre en compte l’acoustique et la disposition de la pièce. Par exemple, vérifiez que les chaises de la salle ne bloquent pas l’affichage de la caméra. Vérifiez que la salle n’a pas d’écho excessif ou de climatisation bruyante, et qu’elle a suffisamment de puissance pour les écrans et Salles Microsoft Teams. Il existe de nombreux facteurs à prendre en compte pour que votre équipe ou partenaire audio-visuel (AV) soit en mesure de vous conseiller.

| &nbsp;   | &nbsp;    |
|-----------|------------|
| ![salles de déplysation.](../media/audio_conferencing_image9.png)<br/>Étapes suivantes|<ul><li>Passez en revue les salles dans l’étendue et définissez Salles Microsoft Teams configurations pour celles-ci.</li></ul>|

_Exemple d’inventaire des réunions/salles de conférence_

| Site      | Nom de la salle | Type de salle | Nombre de personnes | Dans l’étendue ? | Fonctionnalités actuelles de la salle           | Fonctionnalités de salle futures |
|-----------|-----------|-----------|------------------|-----------|-------------------------------------|--------------------------|
| Siège social de Londres | Curie     | Moyen    | 6&ndash;12       | Oui       | Haut-parleur                        | 1 écran, audio et vidéo plus présentation<br>Accès RTC |
| Siège social de Sydney | Hill      | Grande     | 12&ndash;16      | Oui       | Unité AV héritée, 1 écran et appareil photo | 2 écrans, audio et vidéo, plus une présentation<br>Accès RTC |

## <a name="device-selection"></a>Sélection de l’appareil

Évaluez la solution Salles Microsoft Teams la plus adaptée à chaque salle en fonction des fonctionnalités futures de la salle. Déterminez les périphériques AV qui conviennent le mieux, en fonction de la taille et de la disposition de la pièce.

Pour obtenir des conseils sur le type d’appareils système et périphériques par type de pièce et par taille, consultez l’article [sur les exigences Salles Microsoft Teams](requirements.md).

En fonction du fournisseur que vous préférez, utilisez les informations fournies dans l’article de configuration requise pour définir votre Salles Microsoft Teams et la configuration d’appareil périphérique prise en charge par type de salle, et utilisez-la comme modèle pour votre déploiement.

**Pro Conseil** : certains types de salles peuvent ne pas être applicables pour votre déploiement.

| &nbsp; | &nbsp; |
|---|---|
| ![dans l’étendue.](../media/audio_conferencing_image7.png) <br/>Points de décision | <ul><li>À partir de votre inventaire, quels types de salles sont concernés par votre déploiement ?</li><li>Quels systèmes allez-vous déployer pour chaque type de salle ?</li></ul> |
| ![recueillir du matériel.](../media/audio_conferencing_image9.png)<br/>Étapes suivantes | <ul><li>Commencez à rassembler des documents opérationnels clés pour les systèmes que vous avez choisis et engagez votre équipe d’approvisionnement.</li></ul> |

_Exemple de modèle de déploiement Salles Microsoft Teams pour votre organisation_

| Type/taille de la salle     | Nombre de personnes | système Salles Microsoft Teams | Périphériques | Affichage(s)      |
|--------------------|------------------|------------------------------|--------------------|-----------------|
| Focus 10' par 9'    | 2&ndash;4        |                              |                    |                 |
| Petit 16' par 16'   | 4&ndash;6        |                              |                    |                 |
| Moyenne 18' par 20'  | 6&ndash;12       |                              |                    |                 |
| Grand 15' par 32'   | 12&ndash;16      |                              |                    |                 |

**Pro Conseil :** c’est le moment idéal pour commencer à collecter des informations sur la solution Salles Microsoft Teams que vous avez choisie.

## <a name="procurement"></a>Marchés publics

Vous pouvez vous procurer le système que vous avez choisi en tant que bundle ou solution intégrée via des partenaires d’appareil.

Vous pouvez acquérir Salles Microsoft Teams auprès d’un certain nombre de partenaires répertoriés dans [l’article sur les exigences](requirements.md). Visitez les sites web des partenaires pour en savoir plus sur ces solutions et options d’approvisionnement.

En fonction de l’échelle et de l’approche de votre déploiement, vous pouvez décider d’envoyer les périphériques Salles Microsoft Teams et pris en charge à un emplacement central pour la configuration et l’affectation initiales. Il peut s’agir d’une bonne approche pour un déploiement intermédiaire sur de nombreux sites. Vous pouvez également choisir d’expédier les offres groupées directement à vos sites.

| &nbsp; | &nbsp; |
|---|---|
| ![composants d’expédition.](../media/audio_conferencing_image7.png) <br/>Points de décision|<ul><li>Allez-vous expédier les composants directement à un site ou à une installation de préproduction ?</li><li>Qui gérerez-vous l’installation intermédiaire (si vous décidez d’en utiliser une) ?</li></ul> |
| ![planifier les opérations.](../media/audio_conferencing_image9.png)<br/>Étapes suivantes|<ul><li>Planifier les opérations.</li><li>Planifier l’adoption et la gestion des changements.</li></ul> |

## <a name="plan-for-operations"></a>Planifier les opérations

Votre organisation doit exécuter des tâches de surveillance, d’administration et de gestion de façon continue, et il est essentiel de savoir qui effectuera ces tâches au début de votre déploiement.

De nombreuses organisations disposent d’une équipe av ou d’un partenaire qui gère leurs salles de conférence et leurs appareils. Vous pouvez également disposer de l’aide de Microsoft pour gérer les salles Teams en tirant parti de Salles Microsoft Teams Premium. Déterminez qui gérera les appareils Salles Microsoft Teams à l’avenir pour surveiller les performances et déployer des mises à jour logicielles et des correctifs logiciels.

Réfléchissez à la file d’attente du support technique vers laquelle vous allez acheminer Salles Microsoft Teams appels et fournissez une FAQ à l’équipe du support technique afin qu’elle puisse mieux comprendre comment utiliser Salles Microsoft Teams et les étapes de dépannage clés qu’elle peut effectuer. Un bon point de départ pour ce FAQ est [l’aide de l’utilisateur](https://support.microsoft.com/office/microsoft-teams-rooms-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) et [les problèmes connus](known-issues.md).

| &nbsp; | &nbsp; |
|---|---|
| ![choisir le responsable.](../media/audio_conferencing_image7.png) <br/>Points de décision|<ul><li>Déterminez qui gérera Salles Microsoft Teams.</li><li>Déterminez la file d’attente du support technique vers laquelle acheminer les appels liés à Salles Microsoft Teams.</li></ul> |
| ![préparer des comptes hôtes.](../media/audio_conferencing_image9.png)<br/>Étapes suivantes |<ul><li>Préparez-vous à héberger des comptes.</li></ul> |

## <a name="plan-for-adoption-and-change-management"></a>Planifier l’adoption et la gestion des changements

Salles Microsoft Teams systèmes introduisent de nouvelles fonctionnalités pour vos utilisateurs. Il est important que vous reconnaissiez qu’il s’agit d’un changement pour vos utilisateurs, et vous devez vous assurer que votre campagne marketing interne identifie les avantages que le nouveau système aura pour vos utilisateurs et les principaux points de discussion que les prospects peuvent utiliser pour discuter avec leurs équipes.

Envisagez de planifier des événements de présentation et des chutes d’affiches sur chaque site pour informer vos utilisateurs des nouvelles fonctionnalités. Vous pouvez également créer des « guides de démarrage rapide » dans la salle. Envisagez de trouver un champion de réunions sur chaque site qui peut aider d’autres personnes à se mettre à la vitesse et à commencer à utiliser les appareils.
