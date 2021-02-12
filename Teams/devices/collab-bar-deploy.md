---
title: Déployer des barres de collaboration pour Microsoft Teams
ms.author: mitressl
author: flinchbot
manager: serdars
audience: ITPro
ms.reviewer: payurevi
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom: ''
ms.assetid: 678689e4-d547-499b-be64-7d8f16dd8668
description: Lisez cet article pour en savoir plus sur le déploiement des barres de collaboration pour Microsoft Teams.
ms.openlocfilehash: 41eb3335eef78f1da2c64b1df65443ba93d40159
ms.sourcegitcommit: b255db7ef816d1884c9c71af86a901bd83a1d9ab
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/18/2020
ms.locfileid: "47962905"
---
# <a name="deploy-collaboration-bars-for-microsoft-teams"></a>Déployer des barres de collaboration pour Microsoft Teams

Le déploiement de barres de collaboration pour Microsoft Teams peut être ventilé selon les phases suivantes :

- **État de préparation du site** Confirmez que vos emplacements de déploiement (salles) répondent aux exigences de déploiement.
- **Disponibilité du service** Créez des comptes de ressources et attribuez-les aux appareils (voir Créer un compte de ressource à l’aide du Centre d’administration [Microsoft 365).](resource-account-ui.md) Bien qu’il soit recommandé d’utiliser une licence de salle dédiée, un compte d’utilisateur final titulaire d’une licence appropriée peut également se connecter aux barres de collaboration.
- **Configuration et déploiement** Configurer les barres de collaboration dans des salles et connecter les périphériques dont vous avez besoin (consultez la documentation du fabricant pour vos barres de collaboration).

Pour gérer les barres de collaboration, vous devez être un administrateur global, un administrateur de service Teams ou un administrateur d’appareil Teams. Pour plus d’informations sur les rôles d’administrateur, voir [Utiliser les rôles d’administrateur Microsoft Teams pour gérer Teams.](../using-admin-roles.md)

## <a name="site-readiness"></a>État de préparation du site

Pendant la livraison des appareils commandés à votre organisation, travaillez avec votre réseau, vos installations et vos équipes audio-visuelles pour vous assurer que les exigences de déploiement sont respectées et que chaque site et salle est prêt en termes d’alimentation, de mise en réseau et d’affichage.

Nos recommandations pour les sites de barre de collaboration sont les suivantes :

- Salles dont la taille peut aller jusqu’à 4 personnes
- Comptes de ressources dédiés
- Affichages tactiles
- Cabling Ethernet
- Qualité de service (QoS) activée sur le réseau pour les médias Microsoft Teams

Pour des raisons d’installation physique, consultez la documentation du fabricant et, si vous en avez une, tirez parti de l’expérience de votre équipe audio-visuelle avant d’installer et d’installer les écrans et d’exécuter le cablage.

> [!TIP]
> Assurez-vous de consulter [la préparation](../prepare-network.md) de votre réseau pour Teams à des fin de planification de la bande passante et d’évaluation de l’pertinence de votre réseau pour le trafic en temps réel.
>
> Nous vous déconseillons de placer des serveurs proxy entre les appareils Teams et Internet. Pour plus d’informations sur les serveurs proxy et Teams, consultez [les serveurs proxy pour Teams.](../proxy-servers-for-skype-for-business-online.md)

|    |     |
|-----------|------------|
| ![Icône montrant les points de décision](../media/audio_conferencing_image7.png) <br/>Points de décision|<ul><li>Confirmez que vos sites répondent aux exigences de disponibilité du site pour les barres de collaboration pour Microsoft Teams.</li><li>Confirmez que vous avez fourni suffisamment de bande passante pour chaque site.</li></ul>|
| ![Icône illustrant les étapes suivantes](../media/audio_conferencing_image9.png)<br/>Étapes suivantes|<ul><li>Commencez à planifier le déploiement et la configuration de votre barre de collaboration.</li></ul>|

## <a name="service-readiness"></a>Préparation du service

Avant de déployer vos barres de collaboration, vous devez décider si elles utiliseront des comptes de ressources Microsoft 365, des comptes d’utilisateur final, ou un mélange des deux. Les comptes de ressources Microsoft 365 sont des comptes de boîte aux lettres et teams qui sont dédiés à des ressources spécifiques, telles qu’une salle, un projecteur, etc. Ces comptes de ressources peuvent répondre automatiquement aux invitations aux réunions à l’aide de règles que vous définissez lors de leur création. À moins qu’une barre de collaboration ne soit dédiée à un individu spécifique pour son utilisation privée, nous vous recommandons de créer un compte de ressource Microsoft 365 pour ce compte.

### <a name="using-a-resource-account"></a>Utilisation d’un compte de ressource

Si vous décidez de configurer un compte de ressource Microsoft 365, vous devez acheter une licence de salle de réunion pour cette salle. La licence Salle de réunion inclut une boîte aux lettres de ressource qui permet aux membres de votre organisation de réserver la salle de réunion via Outlook ou Teams. La licence permet également aux participants de la réunion de partager des vidéos, des audioconférences et des écrans.

Si vous devez recevoir ou appeler un numéro de téléphone externe, vous devrez peut-être bénéficier d’un plan d’appels ou d’une licence de module [add-on](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing?tabs=small-business)Microsoft 365 Business Voice. Si le routage direct est activé dans votre organisation, vous n’avez besoin que de la référence SKU de salle de réunion.

Lorsque vous créez un compte de ressource, vous pouvez choisir d’autoriser ou non le compte à accepter ou refuser automatiquement les demandes de réunion, d’autoriser les réunions récurrentes, de spécifier à l’avance les informations sur la ressource, etc.

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

Pour plus d’informations sur les barres de collaboration pour les comptes de ressources Microsoft 365, voir Créer un compte de ressource à l’aide du Centre [d’administration Microsoft 365.](resource-account-ui.md)

|    |     |
|-----------|------------|
| ![Icône montrant les points de décision](../media/audio_conferencing_image7.png) <br/>Points de décision|<ul><li>Décidez si vous souhaitez effectuer ou recevoir des appels téléphoniques externes et identifier les exigences en matière de licences pour vos comptes de ressources.</li></ul>|
| ![Icône illustrant les étapes suivantes](../media/audio_conferencing_image9.png)<br/>Étapes suivantes|<ul><li>Préparer les comptes des ressources.</li></ul>|

## <a name="configuration-and-deployment"></a>Configuration et déploiement

La planification de la configuration et du déploiement couvre les aspects clés suivants :

- Mise en service de compte de ressource
- Déploiement d’appareils
- Barres de collaboration pour la configuration des applications et périphériques Microsoft Teams
-  Tests
- Gestion des biens

### <a name="account-provisioning"></a>Provisionnage de compte

Si vous envisagez d’utiliser des comptes de ressources Microsoft 365 pour laisser les utilisateurs réserver des barres de collaboration, suivez les instructions dans Créer un compte de ressource à l’aide du Centre d’administration [Microsoft 365](resource-account-ui.md) pour créer un compte de ressource Microsoft 365 pour chaque barre de collaboration qui en a besoin. C’est également ici que vous devrez ajouter une licence Salle de réunion au compte de ressource et, si vous souhaitez effectuer ou recevoir des appels vers ou depuis des numéros de téléphone externes, une licence Plan d’appels ou Voix Entreprise si votre organisation n’utilise pas le routage direct.

Si vous souhaitez attribuer des barres de collaboration à des utilisateurs individuels pour leur utilisation privée, vous n’avez pas besoin de configurer de comptes supplémentaires. Les utilisateurs peuvent se connecter à des barres de collaboration à l’aide de leur compte personnel.

> [!TIP]
> Rendez les noms d’affichage de vos comptes de ressources Microsoft 365 descriptifs et faciles à comprendre. Voici les noms que les utilisateurs voient lorsqu’ils recherchent et ajoutent des barres de collaboration pour Microsoft Teams à des réunions. Vous pourriez utiliser une convention telle que Le nom de la salle de site (Capacité maximale de la salle), par exemple Domaine, une salle de réunion de 4 personnes à Londres, avec le nom complet - LON-S(4).

|    |     |
|-----------|------------|
| ![Icône montrant les points de décision](../media/audio_conferencing_image7.png) <br/>Points de décision|<ul><li>Décidez de la convention d’affectation de noms pour vos comptes de ressources dédiés.</li><li>Décidez si vous devez créer des comptes individuels ou utiliser des scripts d’approvisionnement en bloc.</li></ul>|
| ![Icône illustrant les étapes suivantes](../media/audio_conferencing_image9.png)<br/>Étapes suivantes|<ul><li>Commencez à planifier le déploiement de votre appareil.</li></ul>|

### <a name="device-deployment"></a>Déploiement d’appareils

Ensuite, vous devez créer votre plan pour remettre les appareils et leurs périphériques affectés à vos salles, puis procéder à l’installation et à la configuration.

|    |     |
|-----------|------------|
| ![Icône montrant les points de décision](../media/audio_conferencing_image7.png) <br/>Points de décision|<ul><li>Décidez qui gérera le déploiement site par site.</li><li> Identifiez les ressources qui installeront les barres de collaboration pour Microsoft Teams sur site et entreprenons la configuration et les tests.</li></ul>|
| ![Icône illustrant les étapes suivantes](../media/audio_conferencing_image9.png)<br/>Étapes suivantes|<ul><li>Démarrez le test de l’appareil.</li></ul>|

### <a name="testing"></a> Tests

Une fois que les barres de collaboration de Microsoft Teams ont été déployées, vous devez les tester. Connectez-vous à l’appareil et vérifiez que les fonctionnalités attendues fonctionnent sur l’appareil déployé. Il est vivement recommandé de vérifier que les appareils  s’affichent dans la section **Barres de collaboration** sous l’onglet Appareils du Centre d’administration Microsoft Teams. Il est également important de tester plusieurs appels et réunions afin de vérifier la qualité et les performances.

Dans le cadre du déploiement général de Microsoft Teams, nous vous recommandons de configurer la création de fichiers pour le tableau de bord de qualité des appels, de surveiller les tendances de qualité et de vous impliquer dans le processus de révision de la qualité de l’expérience. Pour plus d’informations, voir le Guide de révision [de la qualité de l’expérience.](https://aka.ms/qerguide)

### <a name="asset-management"></a>Gestion des biens

Dans le cadre du déploiement, vous pouvez mettre à jour votre registre de biens avec le nom de la salle, le compte de ressource connecté et les périphériques affectés.

## <a name="related-topics"></a>Sujets associés

[Configurer des comptes pour les barres de collaboration pour Microsoft Teams à l’aide du Centre d’administration Microsoft Teams](resource-account-ui.md)

<!-- [Configure accounts for collaboration bars for Microsoft Teams using PowerShell](resource-account-ps.md) -->
