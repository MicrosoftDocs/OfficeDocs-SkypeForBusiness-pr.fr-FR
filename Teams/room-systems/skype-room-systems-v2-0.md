---
title: Plan pour les salles de Microsoft teams
ms.author: v-lanac
author: lanachin
ms.reviewer: sohailta
manager: serdars
ms.date: 5/10/2018
audience: ITPro
ms.topic: conceptual
ms.service: msteams
localization_priority: Normal
ms.assetid: b4e0ad1e-12e5-4130-aec1-d8c9cd3a5965
ms.collection:
- M365-collaboration
description: Cet article décrit les considérations relatives à la planification pour le déploiement de Microsoft Teams, la nouvelle génération de systèmes de salle Skype.
ms.openlocfilehash: 7225635e1069b880dd78d4d32060f1beb6e7b389
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2019
ms.locfileid: "37573582"
---
# <a name="plan-microsoft-teams-rooms"></a>Planifier les salles de Microsoft teams

Cet article présente une approche complète de la planification, de la distribution et de l’exploitation des salles Microsoft teams dans le cadre de la stratégie globale de réunion et de salle de conférence.

Vous trouverez ci-dessous des informations sur la planification de l’approche et des principales décisions que vous devez prendre en compte, ainsi que des liens vers des informations techniques. Nous vous recommandons de passer en revue le plan, de déployer et de gérer des sections même si vous êtes déjà entièrement déployé.

## <a name="overview-of-microsoft-teams-rooms"></a>Vue d’ensemble des salles Microsoft teams

Microsoft teams Room fournit une interface de réunion complète qui permet d’offrir une vidéo HD, du contenu audio et du partage de contenu à des réunions de toutes tailles, de petites zones de Huddle à des salles de conférence de grande taille.

![Une console, un microphone et un grand écran montés sur le mur d’une salle de conférence montrent les éléments d’un exemple de configuration des salles de Microsoft Teams.](../media/room-systems-image1.png "Une console, un microphone et un grand écran montés sur le mur d’une salle de conférence montrent les éléments d’un exemple de configuration des salles de Microsoft Teams.")

Le [Centre d’aide de Microsoft teams vous](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) permet d’en savoir plus sur Microsoft teams et de la manière dont il peut ajouter de la valeur dans le cadre de votre déploiement. Par ailleurs, nous vous recommandons de suivre cette [vidéo de présentation](https://youtu.be/tNey5KZVCl0). 

## <a name="microsoft-teams-rooms-components"></a>Composants de salles de Microsoft teams

Dans Microsoft Teams, les principaux composants suivants vous permettent d’offrir une formidable interface utilisateur :

- Panneau de configuration tactile
- Calculer
- Application Microsoft teams
- Dock/extension
- Périphériques (caméra, micro, haut-parleurs)
- Écrans externes (deux au maximum)
- Entrée HDMI

Vous pouvez acheter ces composants comme packages préinstallés auprès d’un certain nombre de fournisseurs ou vous pouvez acheter les composants pris en charge individuellement en suivant les [instructions décrites dans cet article](requirements.md).

Outre la combinaison surface Pro/Dock, vous pouvez également acheter des salles de Microsoft teams à l’aide du panneau de configuration de l’écran tactile, du calcul, du Dock et des périphériques clés intégrés. 

En règle générale, les forfaits et unités intégrées incluent les logiciels préinstallés, alors que si vous achetez individuellement des composants pris en charge pour les systèmes surface Pro, vous devez installer le logiciel. Pour obtenir des instructions, consultez [cet article sur l’installation de logiciels sur des appareils](room-systems-scale.md). 

Vous pouvez déployer des salles de Microsoft teams avec Microsoft Teams, Skype entreprise Online, ou des déploiements hybrides Skype entreprise ou locaux.  Pour plus d’informations sur les licences nécessaires, voir la [mise à jour des licences de salle de réunion teams](skype-room-systems-v2.md) .

|    |     |
|-----------|------------|
|![](../media/audio_conferencing_image7.png) <br/>Points de décision|<ul><li>Déploierez-vous des salles Microsoft teams au sein de votre organisation ? </li><li>Comment allez-vous utiliserez vos systèmes de salle Microsoft Teams, regroupés en tant que composants séparés ou en tant qu’unités intégrées ?</li></ul> |
| ![](../media/audio_conferencing_image9.png)<br/>Étapes suivantes | <ul><li>Identifiez les personnes qui utiliseront les principales activités dans votre déploiement.</li><li>Passez en revue les salles de réunion que vous avez (et prévoyez de configurer) pour comprendre l’endroit où vous voulez déployer les salles et les périphériques de Microsoft teams appropriés à la taille de la pièce.</li></ul> |
| | |

## <a name="identify-who-will-undertake-the-key-activities-throughout-your-deployment"></a>Identifier les personnes qui utiliseront les principales activités dans votre déploiement

Utilisez l’approche décrite ci-dessous pour vous guider dans votre déploiement et pour personnaliser les exemples de sorties proposés dans ces articles en fonction de votre organisation.

Commencez par comprendre les salles de conférence dont vous avez besoin et comment vous conformer ce qui vous convient le mieux, puis parcourez la sélection et la mise en œuvre de l’équipement dont vous avez besoin, la configuration et le déploiement de votre service, la gestion des modifications et adoption des utilisateurs et développement d’opérations et de procédures de maintenance.

![Commencez par comprendre ce dont vous avez besoin et votre vision qui vous convient, puis passez en revue la sélection et le déploiement de l’équipement dont vous avez besoin, la configuration et le déploiement de votre service, la gestion des modifications et de l’adoption des utilisateurs, et le développement procédures et opérations de maintenance.](../media/room-systems-image2.png "Commencez par comprendre ce dont vous avez besoin et votre vision qui vous convient, puis passez en revue la sélection et le déploiement de l’équipement dont vous avez besoin, la configuration et le déploiement de votre service, la gestion des modifications et de l’adoption des utilisateurs, et le développement procédures et opérations de maintenance.")

Vous devrez peut-être coordonner ces activités entre plusieurs équipes. Nous vous proposons une vue d’ensemble des principales activités que vous devez aborder, ainsi que des suggestions pour les équipes qui participent en général au déploiement et à la gestion des systèmes de salle de conférence, pour vous aider à déterminer les personnes avec lesquelles vous avez besoin de travailler.

| Tâche                       | Qui peut engager la tâche           | Affectée à | Liens vers ce contenu |
|----------------------------|----------------------------------------|-------------|-----------------------|
| Salles de stocks            | Installations/équipe AV/équipe de projet informatique |             | [Inventaire de la salle et planification des capacités](#room-inventory-and-capability-planning)        |
| Planifier les fonctionnalités          | Équipe de projet informatique                        |             | [Inventaire de la salle et planification des capacités](#room-inventory-and-capability-planning)                       |
| Sélection d’appareil           | Équipe de projet informatique/équipe AV              |             | [Sélection d’appareil](#device-selection)                      |
| Marchés                | Équipe de projet informatique/équipe AV              |             | [Marchés](#procurement)                      |
| Disponibilité du site             | Installations/équipe AV/équipe de projet informatique |             | [Disponibilité du site](room-systems-v2.md#site-readiness)                      |
| Préparation du service          | Équipe de projet informatique                        |             | [Préparation du service](room-systems-v2.md#service-readiness)                      |
| Configuration              | Équipe de projet informatique                        |             | [Configuration et déploiement](room-systems-v2.md#configuration-and-deployment)                      |
| Déploiement                 | Installations/équipe AV/équipe de projet informatique |             | [Liste de vérification de déploiement](console.md#microsoft-teams-rooms-deployment-checklist)                      |
| Croissante                   | Installations/équipe AV/équipe de projet informatique |             | [Croissante](#plan-for-adoption-and-change-management)                      |
| Maintenance et opérations | Équipe AV/équipe de projet informatique              |             | [Vue d’ensemble de la gestion](skype-room-systems-v2.md)                      |


## <a name="room-inventory-and-capability-planning"></a>Inventaire de la salle et planification des capacités

La première étape consiste à inventorier la réunion existante de votre organisation et les salles de conférence pour comprendre son environnement, sa taille, sa disposition et son objectif ainsi que les fonctionnalités que vous voulez que chaque salle de votre choix dispose à l’avenir, par exemple plus riche les fonctionnalités de collaboration seront activées dans la salle. 

Une fois que vous avez créé un inventaire de l’équipement et des capacités dans chaque salle existante, vous devez disposer de la configuration requise pour le flux de la salle dans la planification de votre appareil pour créer une solution de conférence complète. Les modalités (audio, vidéo) nécessaires pour chaque pièce, en plus de la taille et de l’objectif de la salle, jouent un rôle important dans le choix de la solution la plus appropriée pour chaque pièce. 

Dans le cadre de votre découverte, il est essentiel de prendre en compte l’acoustique et la disposition de la salle. Par exemple, assurez-vous que les chaises dans la salle ne bloquent pas la vue de la caméra. Vérifiez que la salle n’utilise pas un écho excessif ou un système de climatisation bruyant et qu’elle dispose d’une alimentation suffisante pour les écrans et les salles de Microsoft Teams. Il existe de nombreux facteurs à prendre en compte pour pouvoir conseiller votre équipe ou votre partenaire audiovisuel. 

|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>Points de décision|<ul><li>Quelles sont les salles de déploiement ?</li><li>Quels sites font l’objet de votre déploiement ?</li><li>Qui s’engage l’inventaire des salles de réunion ?</li></ul> |
| ![](../media/audio_conferencing_image9.png)<br/>Étapes suivantes|<ul><li>Révisez les salles de l’application, puis définissez les configurations des salles de Microsoft teams pour elles.</li></ul>|

_Exemple d’inventaire d’une salle de réunion/de conférence_

| Site  | Nom de la salle | Type de salle | Nombre de personnes  | Dans l’étendue ? | Fonctionnalités actuelles de la salle       | Nouvelles fonctionnalités de salle     |
|-----------|---------------|---------------|-----------------------|--------------|-------------------------------------|----------------------------------------------------------|
| HQ de Londres | Curie         | Moyen        | 6&ndash;12                  | Oui          | Mains                        | 1 écran, audio et vidéo plus présentation<br>Accès RTC |
| HQ de Sydney | Hill          | Grande         | 12&ndash;16                 | Oui          | Unité AV héritée, 1 écran et appareil photo | 2 écrans, audio et vidéo et présentation<br>Accès RTC |

## <a name="device-selection"></a>Sélection d’appareil 

Évaluez la solution Microsoft teams Room qui est la plus appropriée pour chaque salle en fonction des fonctionnalités que vous voulez utiliser pour la salle. Déterminez les périphériques AV qui conviennent le mieux, en fonction de la taille de la salle et de la disposition. 

Pour obtenir des instructions sur le type de périphériques système et périphériques par type et taille de pièce, voir l’article [Configuration requise pour Microsoft teams](requirements.md) . 

En fonction du fournisseur de votre choix, utilisez les informations fournies dans l’article sur la configuration requise pour définir les salles de votre équipe Microsoft teams et la configuration de votre appareil périphérique par type de pièce, et utilisez-la en tant que modèle pour votre déploiement. 

**Conseil Pro** : certains types de salle peuvent ne pas être applicables pour votre déploiement.

|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>Points de décision|<ul><li>Dans votre inventaire, quels types de salles font l’objet de votre déploiement ?</li><li>Quels sont les systèmes que vous déploierez pour chaque type de pièce ?</li></ul>|
| ![](../media/audio_conferencing_image9.png)<br/>Étapes suivantes|<ul><li>Commencez à collecter des documents opérationnels clés pour les systèmes que vous avez choisis et contactez votre équipe d’approvisionnement.</li></ul>|

_Exemple de modèle de déploiement de salles de Microsoft teams pour votre organisation_

| **Type/taille de pièce** | **Nombre de personnes**  | **Système de salle Microsoft teams** | **Appareils périphériques**  | **Affichage (s)** |
|----------------------|-----------------------|----------------------------------|-------------------------|-----------------|
| Mettre le focus sur 10 'par 9 '      | 2&ndash;4                   |                                  |                         |                 |
| Petites 16 'par 16 '     | 4&ndash;6                   |                                  |                         |                 |
| Moyenne 18 'par 20 '    | 6&ndash;12                  |                                  |                         |                 |
| Grande 15 'par 32 '     | 12&ndash;16                 |                                  |                         |                 |

**Conseil Pro :** C’est le moment idéal pour commencer à collecter des informations sur la solution de Microsoft teams que vous avez choisie.

## <a name="procurement"></a>Marchés 

Vous pouvez vous procurer votre système à votre choix en tant qu’offre groupée ou une solution intégrée via les partenaires de périphériques. Vous pouvez également acquérir un dock de dispositif de partenariat et préparer votre propre solution Microsoft teams à l’aide d’un appareil surface Pro et de périphériques AV _pris en charge_ existants. 

Vous pouvez acquérir des salles de Microsoft teams à partir d’un certain nombre de partenaires qui sont répertoriés dans l' [article Configuration requise](requirements.md). Rendez-vous sur le site Web des partenaires pour en savoir plus sur ces solutions et options d’approvisionnement. 

En fonction de l’échelle et de l’approche de votre déploiement, il est possible que vous souhaitiez que les salles de Microsoft teams et les périphériques pris en charge soient livrés à un emplacement central pour la configuration initiale et le devoir. Il peut s’agir d’une bonne approche pour un déploiement intermédiaire dans de nombreux sites. Vous pouvez également choisir d’expédier les offres directement sur vos sites. 

|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>Points de décision|<ul><li>Allez-vous livrer les composants directement à un site ou à une installation intermédiaire ?</li><li>Qui doit gérer la fonction de staging (si vous décidez d’en utiliser une) ?</li></ul>|
| ![](../media/audio_conferencing_image9.png)<br/>Étapes suivantes|<ul><li>Planifiez les opérations.</li><li>Planifier l’adoption et la gestion des modifications.</li></ul>|

## <a name="plan-for-operations"></a>Planifier les opérations 

Votre organisation doit exécuter les tâches de surveillance, d’administration et de gestion de façon continue, et il est essentiel d’accepter les tâches suivantes dans le cadre de votre déploiement. 

De nombreuses organisations disposent d’une équipe ou d’un partenaire AV qui gère leurs salles et périphériques de conférence. Cette équipe doit être chargée de l’acceptation des personnes qui géreront les périphériques de la salle de Microsoft teams pour contrôler les performances et déployer les mises à jour logicielles et les correctifs logiciels. 

Envisagez la file d’attente du support technique pour laquelle vous dirigez les appels liés à Microsoft teams rooms֪, puis fournissez une FAQ à l’équipe du support technique afin qu’elle puisse mieux comprendre l’utilisation des salles de Microsoft teams et les principales étapes de résolution des problèmes. Voici un bon point de départ pour cette FAQ : l’aide de l' [utilisateur](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) et la [liste des problèmes connus](known-issues.md).

|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>Points de décision|<ul><li>Décidez qui gérera les salles de Microsoft Teams.</li><li>Déterminez la file d’attente du support technique pour diriger les appels liés à Microsoft Teams.</li></ul>|
| ![](../media/audio_conferencing_image9.png)<br/>Étapes suivantes|<ul><li>Préparer l’hébergement des comptes. </li></ul>|


## <a name="plan-for-adoption-and-change-management"></a>Planifier l’adoption et la gestion des modifications

Les systèmes de salle Microsoft teams introduisent de nouvelles fonctionnalités pour vos utilisateurs. Il est important que vous reconnaissez qu’il s’agit d’une modification apportée aux utilisateurs et que vous devez vous assurer que votre campagne identifie les avantages dont dispose le nouveau système pour vos utilisateurs et que les principaux points de discussion peuvent utiliser pour discuter avec leurs équipes. 

Envisagez de planifier des événements d’affichage et de découpage d’affiches sur chaque site pour informer vos utilisateurs des nouvelles fonctionnalités. Vous pouvez également créer des guides de démarrage rapide dans la salle. Envisagez de rechercher un champion de réunions sur chaque site qui peut aider les autres à s’utiliser et commencer à utiliser les appareils.
