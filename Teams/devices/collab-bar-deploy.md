---
title: Déployer Salles Microsoft Teams sur Android
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
ms.reviewer: payurevi
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Devices
ms.custom: ''
ms.assetid: 678689e4-d547-499b-be64-7d8f16dd8668
description: Lisez cet article pour en savoir plus sur le déploiement de Salles Microsoft Teams sur Android.
ms.openlocfilehash: f5f49a7e461153d24837d28d7160a475e4992eba
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2022
ms.locfileid: "67267809"
---
# <a name="deploy-microsoft-teams-rooms-on-android"></a>Déployer Salles Microsoft Teams sur Android

Le déploiement de Salles Microsoft Teams sur Android peut être divisé en phases suivantes :

- **Préparation du site** Vérifiez que vos emplacements de déploiement (salles) répondent aux exigences de déploiement.
- **Préparation du service** Créez des comptes de ressources et attribuez-les aux appareils ([voir Créer un compte de ressource à l’aide du Centre d'administration Microsoft 365](resource-account-ui.md)). Bien que nous vous recommandons d’utiliser une licence de salle dédiée, un compte d’utilisateur final disposant d’une licence appropriée peut également se connecter à salles Teams sur Android.
- **Configuration et déploiement** Configurez salles Teams et connectez les périphériques dont vous avez besoin (consultez la documentation du fabricant pour plus d’informations).

Pour gérer salles Teams, vous devez être administrateur général, administrateur du service Teams ou administrateur d’appareil Teams. Pour plus d’informations sur les rôles d’administrateur, consultez [Utiliser les rôles d’administrateur Microsoft Teams pour gérer Teams](../using-admin-roles.md).

## <a name="site-readiness"></a>Préparation du site

Pendant que les appareils commandés sont remis à votre organisation, collaborez avec vos équipes réseau, installations et audio-visuels pour vous assurer que les exigences de déploiement sont remplies et que chaque site et salle est prêt en termes d’alimentation, de mise en réseau et d’affichage.

Nos recommandations pour les sites de barre de collaboration sont les suivantes :

- Chambres d’une taille maximale de 5 personnes
- Comptes de ressources dédiés
- Affichages tactiles
- Câblage Ethernet
- Qualité de service (QoS) activée sur le réseau pour les médias Microsoft Teams

Pour des considérations relatives à l’installation physique, consultez la documentation du fabricant et, si vous en avez une, tirez parti de l’expérience de votre équipe audio-visuelle avant d’installer et de monter des écrans et d’exécuter le câblage.

> [!TIP]
> Veillez à vérifier [la préparation de votre réseau pour Teams pour](../prepare-network.md) la planification de la bande passante et l’évaluation de l’adéquation de votre réseau pour le trafic en temps réel.
>
> Nous vous déconseillons de placer des serveurs proxy entre les appareils Teams et Internet. Pour plus d’informations sur les serveurs proxy et Teams, consultez [Serveurs proxy pour Teams](../proxy-servers-for-skype-for-business-online.md).

|&nbsp;|&nbsp;|
|-----------|------------|
| ![Icône montrant les points de décision.](../media/audio_conferencing_image7.png) <br/>Points de décision|<ul><li>Vérifiez que vos sites répondent aux exigences de préparation des sites pour les barres de collaboration pour Microsoft Teams.</li><li>Vérifiez que vous avez fourni une bande passante suffisante pour chaque site.</li></ul>|
| ![Icône représentant les étapes suivantes.](../media/audio_conferencing_image9.png)<br/>Étapes suivantes|<ul><li>Commencez à planifier le déploiement et la configuration de votre barre de collaboration.</li></ul>|

## <a name="service-readiness"></a>Préparation du service

Avant de déployer salles Teams, vous devez décider s’il utilisera des comptes de ressources Microsoft 365, des comptes d’utilisateur final ou un mélange des deux. Les comptes de ressources Microsoft 365 sont des comptes de boîte aux lettres et teams dédiés à des ressources spécifiques, telles qu’une salle, un projecteur, etc. Ces comptes de ressources peuvent répondre automatiquement aux invitations aux réunions à l’aide de règles que vous définissez lors de leur création. Sauf si salles Teams est dédié à une personne spécifique pour son utilisation privée, nous vous recommandons de configurer un compte de ressource Microsoft 365 pour celui-ci.

### <a name="using-a-resource-account"></a>Utilisation d’un compte de ressource

Si vous décidez de configurer un compte de ressource Microsoft 365, vous devez acheter une licence salle de réunion pour celui-ci. La licence salle de réunion inclut une boîte aux lettres de ressources qui permet aux membres de votre organisation de réserver la salle de réunion via Outlook ou Teams. La licence permet également la vidéo et l’audioconférence et le partage d’écran entre les participants à la réunion.

Si vous devez recevoir ou passer des appels vers ou depuis un numéro de téléphone externe, vous aurez [peut-être](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md?tabs=small-business) besoin d’un forfait d’appels ou d’une licence de module complémentaire Microsoft 365 Business Voice. Si le routage direct est activé dans votre organisation, vous n’avez besoin que de la référence SKU de salle de réunion.

Lorsque vous créez un compte de ressource, vous pouvez choisir de laisser le compte accepter ou refuser automatiquement les demandes de réunion, d’autoriser les réunions périodiques, de spécifier jusqu’à quel moment les utilisateurs peuvent réserver la ressource, et ainsi de suite.

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

Pour plus d’informations sur les comptes de ressources Microsoft 365, consultez [Créer un compte de ressources à l’aide de la Centre d'administration Microsoft 365](resource-account-ui.md).

|&nbsp;|&nbsp;|
|-----------|------------|
| ![Icône montrant les points de décision.](../media/audio_conferencing_image7.png) <br/>Points de décision|<ul><li>Déterminez si vous souhaitez passer ou recevoir des appels téléphoniques externes et identifier les exigences de licence pour vos comptes de ressources.</li></ul>|
| ![Icône représentant les étapes suivantes.](../media/audio_conferencing_image9.png)<br/>Étapes suivantes|<ul><li>Préparez des comptes de ressources.</li></ul>|

## <a name="configuration-and-deployment"></a>Configuration et déploiement

La planification de la configuration et du déploiement couvre les domaines clés suivants :

- Provisionnement de comptes de ressources
- Déploiement d’appareils
- salles Teams configuration de l’application et de l’appareil périphérique
-  Tests
- Gestion des ressources

### <a name="account-provisioning"></a>Provisionnement de comptes

Si vous envisagez d’utiliser des comptes de ressources Microsoft 365 pour permettre aux utilisateurs de réserver des barres de collaboration, suivez les instructions de [créer un compte de ressource à l’aide de la Centre d'administration Microsoft 365](resource-account-ui.md) pour créer un compte de ressource Microsoft 365 pour chaque barre de collaboration qui en a besoin. C’est également là que vous devez ajouter une licence salle de réunion au compte de ressource et, si vous souhaitez passer ou recevoir des appels vers ou depuis des numéros de téléphone externes, une licence Forfait d’appels ou Voix entreprise si votre organisation n’utilise pas le routage direct.

Si vous souhaitez affecter salles Teams à des utilisateurs individuels pour leur utilisation privée, vous n’avez pas besoin de configurer de comptes supplémentaires. Les utilisateurs peuvent se connecter aux barres de collaboration à l’aide de leur compte personnel.

> [!TIP]
> Rendez les noms d’affichage de vos comptes de ressources Microsoft 365 descriptifs et faciles à comprendre. Il s’agit des noms que les utilisateurs verront lors de la recherche et de l’ajout de salles Teams aux réunions. Vous pouvez utiliser une convention comme *Site*-*Room Name* (*Max Room Capacity*), par exemple Curie, une salle de réunion à 4 personnes à Londres, peut avoir le nom complet LON-CURIE(4).

|&nbsp;|&nbsp;|
|-----------|------------|
| ![Icône montrant les points de décision.](../media/audio_conferencing_image7.png) <br/>Points de décision|<ul><li>Décidez de la convention d’affectation de noms pour vos comptes de ressources dédiés.</li><li>Déterminez si vous allez créer des comptes individuels ou utiliser des scripts de provisionnement en bloc.</li></ul>|
| ![Icône représentant les étapes suivantes.](../media/audio_conferencing_image9.png)<br/>Étapes suivantes|<ul><li>Commencez à planifier le déploiement de votre appareil.</li></ul>|

### <a name="device-deployment"></a>Déploiement d’appareils

Ensuite, vous devez créer votre plan pour remettre les appareils et leurs périphériques affectés à vos salles, puis poursuivre l’installation et la configuration.

|&nbsp;|&nbsp;|
|-----------|------------|
| ![Icône montrant les points de décision.](../media/audio_conferencing_image7.png) <br/>Points de décision|<ul><li>Déterminez qui gérera le déploiement site par site.</li><li> Identifiez les ressources qui installeront salles Teams sur le site et effectuez la configuration et les tests.</li></ul>|
| ![Icône représentant les étapes suivantes.](../media/audio_conferencing_image9.png)<br/>Étapes suivantes|<ul><li>Démarrez le test de l’appareil.</li></ul>|

### <a name="testing"></a> Tests

Une fois que vous avez déployé salles Teams, vous devez les tester. Connectez-vous à salles Teams et vérifiez que les fonctionnalités attendues fonctionnent. Nous vous recommandons vivement de vérifier qu’elles apparaissent dans la section **Barres de collaboration** sous l’onglet **Appareils Teams** du Centre d’administration Microsoft Teams. Il est également important d’effectuer un certain nombre d’appels de test et de réunions pour vérifier la qualité et les performances.

Dans le cadre du déploiement général de Microsoft Teams, nous vous recommandons de configurer des fichiers de création pour le tableau de bord de qualité des appels (CQD), de surveiller les tendances de qualité et de participer au processus de révision de la qualité de l’expérience. Pour plus d’informations, consultez le [Guide de révision de la qualité de l’expérience](../quality-of-experience-review-guide.md).

### <a name="asset-management"></a>Gestion des ressources

Dans le cadre du déploiement, vous devez mettre à jour votre registre de ressources avec le nom de la salle, le compte de ressource connecté et les périphériques affectés.

## <a name="related-topics"></a>Voir aussi

[Créer des comptes de ressources pour les salles et les appareils Teams partagés](../rooms/with-office-365.md)