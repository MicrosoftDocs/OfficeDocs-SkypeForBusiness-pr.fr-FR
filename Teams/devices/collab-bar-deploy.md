---
title: Déployer Salles Microsoft Teams sur Android
ms.author: czawideh
author: cazawideh
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
ms.custom: ''
ms.assetid: 678689e4-d547-499b-be64-7d8f16dd8668
description: Lisez cet article pour en savoir plus sur le déploiement d Salles Microsoft Teams sur Android.
ms.openlocfilehash: 55e410b1863effd671f08cba663211b78f76e30f
ms.sourcegitcommit: a894e9397050e09bfaab02e700e943a3bbeb1302
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/15/2022
ms.locfileid: "63503541"
---
# <a name="deploy-microsoft-teams-rooms-on-android"></a>Déployer Salles Microsoft Teams sur Android

Le déploiement d Salles Microsoft Teams sur Android peut être ventilé selon les phases suivantes :

- **État de préparation du site** Confirmez que vos emplacements de déploiement (salles) répondent aux exigences de déploiement.
- **Disponibilité du service** Créez des comptes de ressources et attribuez-les aux appareils ([voir Créer un compte de ressource à l’aide du Centre d'administration Microsoft 365](resource-account-ui.md)). Bien que nous vous recommandons d’utiliser une licence de salle dédiée, un compte d’utilisateur final titulaire d’une licence appropriée peut également vous salles Teams sur Android.
- **Configuration et déploiement** Configurer et salles Teams connecter les périphériques dont vous avez besoin (pour plus d’informations, consultez la documentation du fabricant).

Pour gérer salles Teams, vous devez être administrateur global, administrateur de Teams service ou administrateur de Teams périphériques. Pour plus d’informations sur les rôles d’administrateur, voir [Utiliser Microsoft Teams rôles d’administrateur pour gérer Teams](../using-admin-roles.md).

## <a name="site-readiness"></a>État de préparation du site

Pendant la livraison des appareils commandés à votre organisation, travaillez avec votre réseau, vos installations et vos équipes audio-visuelles pour vous assurer que les exigences de déploiement sont respectées et que chaque site et salle est prêt en termes d’alimentation, de mise en réseau et d’affichage.

Nos recommandations pour les sites de barre de collaboration sont les suivantes :

- Salles dont la taille peut aller jusqu’à 5 personnes
- Comptes de ressources dédiés
- Écrans tactiles
- Cabling Ethernet
- Qualité de service (QoS) activée sur le réseau pour les Microsoft Teams multimédia

Pour des raisons d’installation physique, consultez la documentation du fabricant et, si vous en avez une, tirez parti de l’expérience de votre équipe audio-visuelle avant d’installer et d’installer les écrans et d’exécuter le cablage.

> [!TIP]
> Assurez-vous de préparer votre réseau [pour](../prepare-network.md) la Teams de planification de la bande passante et d’évaluation de l’pertinence de votre réseau pour le trafic en temps réel.
>
> Nous vous déconseillons de placer des serveurs proxy entre Teams appareils et Internet. Pour plus d’informations sur les serveurs proxy et Teams serveurs proxy, consultez [les serveurs proxy pour Teams](../proxy-servers-for-skype-for-business-online.md).

|&nbsp;|&nbsp;|
|-----------|------------|
| ![Icône montrant les points de décision.](../media/audio_conferencing_image7.png) <br/>Points de décision|<ul><li>Confirmez que vos sites répondent aux exigences de disponibilité du site pour les barres de collaboration pour Microsoft Teams.</li><li>Confirmez que vous avez fourni suffisamment de bande passante pour chaque site.</li></ul>|
| ![Icône illustrant les étapes suivantes.](../media/audio_conferencing_image9.png)<br/>Étapes suivantes|<ul><li>Commencez à planifier le déploiement et la configuration de votre barre de collaboration.</li></ul>|

## <a name="service-readiness"></a>Préparation du service

Avant de déployer salles Teams, vous devez décider s’ils utiliseront des comptes de ressources Microsoft 365, des comptes d’utilisateur final, ou un mélange des deux. Microsoft 365 de ressources sont des comptes de boîtes aux lettres et de Teams qui sont dédiés à des ressources spécifiques, telles qu’une salle, un projecteur, etc. Ces comptes de ressources peuvent répondre automatiquement aux invitations aux réunions à l’aide de règles que vous définissez lors de leur création. Sauf si salles Teams est dédié à une personne spécifique pour son utilisation privée, nous vous recommandons de Microsoft 365 un compte de ressource pour ce compte.

### <a name="using-a-resource-account"></a>Utilisation d’un compte de ressource

Si vous décidez de configurer un Microsoft 365 de ressources, vous devez acheter une licence Salle de réunion de ressources pour ce compte. La licence Salle de réunion inclut une boîte aux lettres de ressources qui permet aux membres de votre organisation de réserver la salle de réunion par le biais d Outlook réunion ou Teams. La licence permet également aux participants de la réunion de partager des vidéos et des audioconférences et des écrans.

Si vous devez recevoir ou appeler un numéro de téléphone externe, vous avez peut-être besoin d’un plan d’appels ou d Microsoft 365 Business Voice [licence de module logiciel.](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md?tabs=small-business) Si vous avez activé le routage direct dans votre organisation, vous n’avez besoin que de la référence Salle de réunion SKU.

Lorsque vous créez un compte de ressource, vous pouvez choisir d’autoriser ou non le compte à accepter ou refuser automatiquement les demandes de réunion, d’autoriser les réunions récurrentes, de spécifier à l’avance les informations sur la ressource, etc.

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

Pour plus d’informations sur Microsoft 365 comptes de ressources, voir [Créer un compte de ressource à l’aide de la Centre d'administration Microsoft 365](resource-account-ui.md).

|&nbsp;|&nbsp;|
|-----------|------------|
| ![Icône montrant les points de décision.](../media/audio_conferencing_image7.png) <br/>Points de décision|<ul><li>Décidez si vous souhaitez effectuer ou recevoir des appels téléphoniques externes et identifier les exigences en matière de licences pour vos comptes de ressources.</li></ul>|
| ![Icône illustrant les étapes suivantes.](../media/audio_conferencing_image9.png)<br/>Étapes suivantes|<ul><li>Préparer les comptes des ressources.</li></ul>|

## <a name="configuration-and-deployment"></a>Configuration et déploiement

La planification de la configuration et du déploiement couvre les aspects clés suivants :

- Mise en service de compte de ressource
- Déploiement d’appareils
- salles Teams configuration des applications et périphériques
-  Tests
- Gestion des biens

### <a name="account-provisioning"></a>Provisionnage de compte

Si vous envisagez d’utiliser des comptes de ressources Microsoft 365 pour laisser les utilisateurs réserver des barres de collaboration, suivez les instructions dans Créer un compte de ressource à l’aide du [Centre d'administration Microsoft 365](resource-account-ui.md) pour créer un compte de ressource Microsoft 365 pour chaque barre de collaboration qui en a besoin. C’est également ici que vous devrez ajouter une licence Salle de réunion au compte de ressource et, si vous voulez effectuer ou recevoir des appels vers ou depuis des numéros de téléphone externes, une licence Plan d’appel ou Voix Entreprise si votre organisation n’utilise pas le routage direct.

Si vous souhaitez affecter des salles Teams à des utilisateurs individuels pour leur utilisation privée, vous n’avez pas besoin de configurer de comptes supplémentaires. Les utilisateurs peuvent se connecter à des barres de collaboration à l’aide de leur compte personnel.

> [!TIP]
> Rendez les noms d’affichage de vos Microsoft 365 ressources descriptifs et faciles à comprendre. Voici les noms que les utilisateurs voient lorsqu’ils recherchent et ajoutent des salles Teams aux réunions. Vous pourriez utiliser une convention - telle que Le nom de la salle de *site(**Capacité* maximale de la salle), par exemple Tyz, une salle de réunion de 4 personnes à Londres, qui peut avoir le nom complet LON-X(4).

|&nbsp;|&nbsp;|
|-----------|------------|
| ![Icône montrant les points de décision.](../media/audio_conferencing_image7.png) <br/>Points de décision|<ul><li>Décidez de la convention d’affectation de noms pour vos comptes de ressources dédiés.</li><li>Décidez si vous devez créer des comptes individuels ou utiliser des scripts d’approvisionnement en bloc.</li></ul>|
| ![Icône illustrant les étapes suivantes.](../media/audio_conferencing_image9.png)<br/>Étapes suivantes|<ul><li>Commencez à planifier le déploiement de votre appareil.</li></ul>|

### <a name="device-deployment"></a>Déploiement d’appareils

Ensuite, vous devez créer votre plan pour remettre les appareils et leurs périphériques affectés à vos salles, puis procéder à l’installation et à la configuration.

|&nbsp;|&nbsp;|
|-----------|------------|
| ![Icône montrant les points de décision.](../media/audio_conferencing_image7.png) <br/>Points de décision|<ul><li>Décidez qui gérera le déploiement site par site.</li><li> Identifiez les ressources qui seront en mesure d’installer salles Teams site et entreprenons la configuration et les tests.</li></ul>|
| ![Icône illustrant les étapes suivantes.](../media/audio_conferencing_image9.png)<br/>Étapes suivantes|<ul><li>Démarrez le test de l’appareil.</li></ul>|

### <a name="testing"></a> Tests

Une fois que vous avez salles Teams, vous devez les tester. Connectez-vous salles Teams vérifier que les fonctionnalités attendues fonctionnent. Il est vivement recommandé de vérifier qu’elles apparaissent dans la section **Barres de collaboration** sous **l’onglet Teams Appareils** du Microsoft Teams d’administration. Il est également important de tester plusieurs appels et réunions afin de vérifier la qualité et les performances.

Dans le cadre du déploiement général de la Microsoft Teams, nous vous recommandons de configurer la création de fichiers pour le tableau de bord de qualité des appels, de surveiller les tendances de la qualité et de vous impliquer dans le processus de révision de la qualité de l’expérience. Pour plus d’informations, voir le [Guide de révision de la qualité de l’expérience](../quality-of-experience-review-guide.md).

### <a name="asset-management"></a>Gestion des biens

Dans le cadre du déploiement, vous pouvez mettre à jour votre registre de biens avec le nom de la salle, le compte de ressource connecté et les périphériques affectés.

## <a name="related-topics"></a>Sujets associés

[Configurer des comptes pour des utilisateurs Salles Microsoft Teams’aide Microsoft Teams centre d’administration](resource-account-ui.md)

<!-- [Configure accounts for collaboration bars for Microsoft Teams using PowerShell](resource-account-ps.md) -->