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
ms.openlocfilehash: 52b865879db3941b5631d7b22c25bd8f6e4d3ce6
ms.sourcegitcommit: b710fc61558a0e031d4e3e4000f234c495e2c4c6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/17/2022
ms.locfileid: "69438412"
---
# <a name="deploy-microsoft-teams-rooms-on-android"></a>Déployer Salles Microsoft Teams sur Android

Le déploiement de Salles Microsoft Teams sur Android peut être divisé en phases suivantes :

- **Préparation du site** Vérifiez que vos emplacements de déploiement (salles) répondent aux exigences de déploiement.
- **Préparation du service** Créez des comptes de ressources et affectez-les aux appareils ([consultez Créer un compte de ressource à l’aide de la Centre d'administration Microsoft 365](resource-account-ui.md)). Bien que nous vous recommandons d’utiliser une licence de salle dédiée, un compte d’utilisateur final sous licence appropriée peut également se connecter à salles Teams sur Android.
- **Configuration et déploiement** Configurez salles Teams et connectez les périphériques dont vous avez besoin (pour plus d’informations, consultez la documentation du fabricant).

Pour gérer salles Teams, vous devez être administrateur général, administrateur de service Teams ou administrateur d’appareils Teams. Pour plus d’informations sur les rôles d’administrateur, consultez [Utiliser Microsoft rôles d’administrateur Teams pour gérer Teams](../using-admin-roles.md).

## <a name="site-readiness"></a>Préparation du site

Pendant que les appareils commandés sont livrés à votre organisation, collaborez avec vos équipes de mise en réseau, d’installations et d’audio-visuels pour vous assurer que les exigences de déploiement sont remplies et que chaque site et salle est prêt en termes d’alimentation, de mise en réseau et d’affichage.

Nos recommandations pour salles Teams sur les sites Android sont les suivantes :

- Chambres jusqu’à 5 personnes
- Comptes de ressources dédiés
- Écrans tactiles
- Câblage Ethernet
- Qualité de service (QoS) activée sur le réseau pour les médias Microsoft Teams

Pour les considérations relatives à l’installation physique, consultez la documentation du fabricant et, le cas échéant, tirez parti de l’expérience de votre équipe audio-visuelle avant d’installer et de monter des écrans et d’exécuter le câblage.

> [!TIP]
> Veillez à consulter [Préparer votre réseau pour Teams](../prepare-network.md) pour la planification de la bande passante et l’évaluation de l’adéquation de votre réseau au trafic en temps réel.
>
> Nous vous déconseillons de placer des serveurs proxy entre les appareils Teams et Internet. Pour plus d’informations sur les serveurs proxy et Teams, consultez [Serveurs proxy pour Teams](../proxy-servers-for-skype-for-business-online.md).

|&nbsp;|&nbsp;|
|-----------|------------|
| ![Icône montrant les points de décision.](../media/audio_conferencing_image7.png) <br/>Points de décision|<ul><li>Vérifiez que vos sites répondent aux exigences de préparation du site pour salles Teams sur Android.</li><li>Vérifiez que vous avez fourni une bande passante suffisante pour chaque site.</li></ul>|
| ![Icône représentant les étapes suivantes.](../media/audio_conferencing_image9.png)<br/>Étapes suivantes|<ul><li>Commencez à planifier votre salles Teams sur le déploiement et la configuration Android.</li></ul>|

## <a name="service-readiness"></a>Préparation du service

Avant de déployer salles Teams, vous devez décider s’ils utiliseront Microsoft comptes de ressources 365, des comptes d’utilisateur final ou une combinaison des deux. Microsoft 365 comptes de ressources sont des comptes de boîte aux lettres et Teams dédiés à des ressources spécifiques, telles qu’une salle, un projecteur, etc. Ces comptes de ressources peuvent répondre automatiquement aux invitations à une réunion à l’aide de règles que vous définissez lors de leur création. À moins que salles Teams ne soit dédié à une personne spécifique pour son utilisation privée, nous vous recommandons de configurer un compte de ressource Microsoft 365 pour celle-ci.

### <a name="using-a-resource-account"></a>Utilisation d’un compte de ressource

Si vous décidez de configurer un compte de ressource Microsoft 365, vous devez acheter une licence salle de réunion pour celui-ci. La licence salle de réunion inclut une boîte aux lettres de ressources qui permet aux membres de votre organisation de réserver la salle de réunion via Outlook ou Teams. La licence permet également la visioconférence et l’audioconférence et le partage d’écran entre les participants à la réunion.

Si vous devez recevoir ou passer des appels vers ou depuis un numéro de téléphone externe, vous aurez peut-être besoin d’un forfait d’appels ou d’Microsoft 365 Business Voice [licence d’extension](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md?tabs=small-business). Si le routage direct est activé dans votre organisation, vous avez uniquement besoin de la référence SKU salle de réunion.

Lorsque vous créez un compte de ressource, vous pouvez choisir de laisser le compte accepter ou refuser automatiquement les demandes de réunion, d’autoriser les réunions périodiques, de spécifier à l’avance combien les utilisateurs peuvent réserver la ressource, etc.

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

Pour plus d’informations sur Microsoft 365 comptes de ressources, consultez [Créer un compte de ressource à l’aide du Centre d'administration Microsoft 365](resource-account-ui.md).

|&nbsp;|&nbsp;|
|-----------|------------|
| ![Icône montrant les points de décision.](../media/audio_conferencing_image7.png) <br/>Points de décision|<ul><li>Déterminez si vous souhaitez passer ou recevoir des appels téléphoniques externes et identifiez les exigences de licence pour vos comptes de ressources.</li></ul>|
| ![Icône représentant les étapes suivantes.](../media/audio_conferencing_image9.png)<br/>Étapes suivantes|<ul><li>Préparez les comptes de ressources.</li></ul>|

## <a name="configuration-and-deployment"></a>Configuration et déploiement

La planification de la configuration et du déploiement couvre les domaines clés suivants :

- Provisionnement de comptes de ressources
- Déploiement d’appareils
- salles Teams configuration de l’application et de l’appareil périphérique
-  Tests
- Gestion des ressources

### <a name="account-provisioning"></a>Provisionnement de compte

Si vous envisagez d’utiliser Microsoft comptes de ressources 365 pour permettre aux utilisateurs de réserver des salles Teams sur des appareils Android, suivez les instructions dans [Créer un compte de ressource à l’aide de la Centre d'administration Microsoft 365](resource-account-ui.md) pour créer un compte de ressource Microsoft 365 pour chaque compte de ressources salles Teams sur un appareil Android qui en a besoin. C’est également là que vous devez ajouter une licence salle de réunion au compte de ressource et, si vous souhaitez passer ou recevoir des appels vers ou à partir de numéros de téléphone externes, une offre d’appels ou une licence Business Voice si votre organisation n’utilise pas le routage direct.

Si vous souhaitez attribuer des salles Teams à des utilisateurs individuels pour leur utilisation privée, vous n’avez pas besoin de configurer de comptes supplémentaires. Les utilisateurs peuvent se connecter à salles Teams sur des appareils Android à l’aide de leur compte personnel.

> [!TIP]
> Rendez les noms complets de vos comptes de ressources Microsoft 365 descriptifs et faciles à comprendre. Il s’agit des noms que les utilisateurs verront lors de la recherche et de l’ajout de salles Teams aux réunions. Vous pouvez utiliser une convention telle que Nom de la *salle* de *site*- (*Capacité maximale* de salle), par exemple Curie, une salle de réunion de 4 personnes à Londres, peut avoir le nom d’affichage LON-CURIE(4).

|&nbsp;|&nbsp;|
|-----------|------------|
| ![Icône montrant les points de décision.](../media/audio_conferencing_image7.png) <br/>Points de décision|<ul><li>Déterminez la convention de nommage de vos comptes de ressources dédiés.</li><li>Déterminez si vous allez créer des comptes individuels ou utiliser des scripts d’approvisionnement en bloc.</li></ul>|
| ![Icône représentant les étapes suivantes.](../media/audio_conferencing_image9.png)<br/>Étapes suivantes|<ul><li>Commencez à planifier le déploiement de votre appareil.</li></ul>|

### <a name="device-deployment"></a>Déploiement d’appareils

Ensuite, vous devez créer votre plan pour remettre les appareils et les périphériques qui leur sont attribués à vos salles, puis procéder à l’installation et à la configuration.

|&nbsp;|&nbsp;|
|-----------|------------|
| ![Icône montrant les points de décision.](../media/audio_conferencing_image7.png) <br/>Points de décision|<ul><li>Déterminez qui gérera le déploiement site par site.</li><li> Identifiez les ressources qui installeront salles Teams sur site et effectuez la configuration et les tests.</li></ul>|
| ![Icône représentant les étapes suivantes.](../media/audio_conferencing_image9.png)<br/>Étapes suivantes|<ul><li>Démarrez le test de l’appareil.</li></ul>|

### <a name="testing"></a> Tests

Une fois que vous avez déployé salles Teams, vous devez les tester. Connectez-vous à salles Teams et vérifiez que les fonctionnalités attendues fonctionnent. Nous vous recommandons vivement de vérifier qu’ils apparaissent dans la section **salles Teams sur Android** sous l’onglet **Appareils Teams** de Microsoft Centre d’administration Teams. Il est également important d’effectuer un certain nombre d’appels de test et de réunions pour vérifier la qualité et les performances.

Dans le cadre du déploiement général de Teams Microsoft, nous vous recommandons de configurer des fichiers de génération pour le tableau de bord de qualité des appels (CQD), de surveiller les tendances en matière de qualité et de participer au processus de révision de la qualité de l’expérience. Pour plus d’informations, consultez le [Guide de révision de la qualité de l’expérience](../quality-of-experience-review-guide.md).

### <a name="asset-management"></a>Gestion des ressources

Dans le cadre du déploiement, vous souhaiterez mettre à jour votre registre de ressources avec le nom de la salle, le compte de ressource connecté et les appareils périphériques affectés.

## <a name="related-topics"></a>Rubriques connexes

[Créer des comptes de ressources pour les salles et les appareils Teams partagés](../rooms/with-office-365.md)