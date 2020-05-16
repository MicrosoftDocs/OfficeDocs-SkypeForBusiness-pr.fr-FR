---
title: Déploiement de barres de collaboration pour Microsoft teams
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
description: Lisez cet article pour en savoir plus sur le déploiement de barres de collaboration pour Microsoft Teams.
ms.openlocfilehash: 4593d6b42e61efbd7d57f27fd0a10ed8f97b82f5
ms.sourcegitcommit: f0ccafb7e9c2d382ab4545e085657e8129024f1d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/16/2020
ms.locfileid: "44268031"
---
# <a name="deploy-collaboration-bars-for-microsoft-teams"></a>Déploiement de barres de collaboration pour Microsoft teams

Le déploiement des barres de collaboration de Microsoft teams peut être subdivisé selon les phases suivantes :

- **Disponibilité du site** Vérifiez que vos emplacements de déploiement (salles) répondent aux exigences de déploiement.
- **Disponibilité du service** Créez des comptes de ressources et affectez-les aux appareils ([voir créer un compte de ressources à l’aide du centre d’administration 365 Microsoft](resource-account-ui.md)). Bien que nous vous recommandons d’utiliser une licence de salle dédiée, un compte d’utilisateur final sous licence peut également se connecter aux barres de collaboration.
- **Configuration et déploiement** Configurez les barres de collaboration dans les salles et reliez les périphériques dont vous avez besoin (voir la documentation du fabricant pour vos barres de collaboration).

## <a name="site-readiness"></a>Disponibilité du site

Lorsque les périphériques commandés sont remis à votre organisation, collaborez avec votre réseau, vos installations et vos équipes audiovisuelles pour vous assurer que les exigences de déploiement sont satisfaites et que chaque site et salle est prêt en termes d’alimentation, de réseau et d’affichage.

Nos recommandations en matière de sites de barre de collaboration sont les suivantes :

- Salles d’une taille maximale de 4 personnes
- Comptes de ressources dédiés
- Affichages tactiles
- Câble Ethernet
- Activation de la qualité de service (QoS) sur le réseau pour les médias Microsoft teams

Pour plus d’informations sur les aspects physiques de l’installation, consultez la documentation du fabricant et, le cas échéant, tirez parti de l’aide de votre équipe audio et vidéo avant d’installer et de monter des écrans et de lancer le câblage.

> [!TIP]
> N’hésitez pas à consulter [préparer votre réseau pour](../prepare-network.md) la planification de la bande passante et à évaluer la pertinence de votre réseau pour le trafic en temps réel.
>
> Nous déconseillons de placer des serveurs proxy entre les appareils teams et Internet. Pour plus d’informations sur les serveurs proxy et les équipes, voir [serveurs proxy pour teams](../proxy-servers-for-skype-for-business-online.md).

|    |     |
|-----------|------------|
| ![Icône montrant les points de décision](../media/audio_conferencing_image7.png) <br/>Points de décision|<ul><li>Vérifiez que vos sites répondent à la configuration requise du site pour les barres de collaboration de Microsoft Teams.</li><li>Vérifiez que vous avez fourni suffisamment de bande passante pour chaque site.</li></ul>|
| ![Icône illustrant les étapes suivantes](../media/audio_conferencing_image9.png)<br/>Étapes suivantes|<ul><li>Commencez à planifier le déploiement et la configuration de la barre de collaboration.</li></ul>|

## <a name="service-readiness"></a>Préparation du service

Avant de déployer vos barres de collaboration, vous devez décider s’ils utiliseront les comptes de ressources Microsoft 365, les comptes d’utilisateurs finaux ou une combinaison des deux. Le compte de ressources Microsoft 365 est un compte de boîte aux lettres et d’équipe dédié à des ressources spécifiques, telles qu’une salle, un projecteur, etc. Ces comptes de ressources peuvent automatiquement répondre aux invitations aux réunions à l’aide de règles que vous définissez lors de leur création. Si une barre de collaboration est réservée à une personne spécifique à des fins d’utilisation privée, nous vous recommandons de configurer un compte de ressources Microsoft 365 pour celle-ci.

### <a name="using-a-resource-account"></a>Utilisation d’un compte de ressources

Si vous décidez de configurer un compte de ressources Microsoft 365, vous devez acheter une licence de salle de réunion. La licence de salle de réunion inclut une boîte aux lettres de ressources permettant aux personnes de votre organisation de réserver la salle de réunion via Outlook ou Teams. Cette licence autorise également les conférences vidéo et audio et le partage d’écran entre les participants à la réunion.

Si vous avez besoin de recevoir ou de passer des appels vers ou à partir d’un numéro de téléphone externe, vous aurez également besoin d’un système téléphonique Microsoft 365 ou d’une licence Microsoft 365 Business Voice.

Lorsque vous créez un compte de ressources, vous pouvez choisir de laisser le compte accepter ou refuser les demandes de réunion automatiquement, et autoriser les réunions récurrentes, spécifier combien de temps les utilisateurs peuvent la réserver, et ainsi de suite.

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

Pour plus d’informations sur les barres de collaboration pour les comptes de ressources Microsoft 365, voir [créer un compte de ressource à l’aide du centre d’administration microsoft 365](resource-account-ui.md).

|    |     |
|-----------|------------|
| ![Icône montrant les points de décision](../media/audio_conferencing_image7.png) <br/>Points de décision|<ul><li>Décidez si vous voulez passer et recevoir des appels téléphoniques externes et identifier les exigences en matière de licences pour vos comptes de ressources.</li></ul>|
| ![Icône illustrant les étapes suivantes](../media/audio_conferencing_image9.png)<br/>Étapes suivantes|<ul><li>Préparer les comptes de ressources</li></ul>|

## <a name="configuration-and-deployment"></a>Configuration et déploiement

La planification de la configuration et du déploiement englobe les principales zones suivantes :

- Attribution d’un compte de ressources
- Déploiement d’appareil
- Barres de collaboration pour l’application Microsoft teams et la configuration de périphériques périphériques
-  Tests
- Gestion des ressources

### <a name="account-provisioning"></a>Attribution de compte

Si vous envisagez d’utiliser des comptes de ressources Microsoft 365 pour permettre aux utilisateurs de coorganiser la collaboration, suivez les instructions de la procédure de [création d’un compte de ressources à l’aide du centre d’administration microsoft 365](resource-account-ui.md) pour créer un compte de ressource Microsoft 365 pour chaque barre de collaboration qui en a besoin. C’est également ici que vous devez ajouter une licence de salle de réunion au compte de ressources et, si vous voulez passer ou recevoir des appels vers des numéros de téléphone externes ou des numéros de téléphone externes, un système téléphonique ou une licence voix entreprise.

Si vous voulez attribuer des barres de collaboration à des utilisateurs individuels pour leur utilisation privée, vous n’avez pas besoin de configurer d’autres comptes. Les utilisateurs peuvent se connecter aux barres de collaboration à l’aide de leur compte personnel.

> [!TIP]
> Rendez les noms d’affichage pour les comptes de ressources Microsoft 365 descriptifs et faciles à comprendre. Il s’agit des noms que les utilisateurs verront lors de la recherche et de l’ajout de barres de collaboration de Microsoft teams à des réunions. Vous pouvez utiliser une convention comme le nom de la salle de *site* - *Room Name*(*capacité maximale*de la salle), par exemple Curie, une salle de réunion à quatre personnes à Londres peut avoir le nom d’affichage lon-Curie (4).

|    |     |
|-----------|------------|
| ![Icône montrant les points de décision](../media/audio_conferencing_image7.png) <br/>Points de décision|<ul><li>Déterminez la Convention d’affectation de noms pour vos comptes de ressources dédiés.</li><li>Décidez si vous voulez créer des comptes individuels ou utiliser des scripts de provisionnement en bloc.</li></ul>|
| ![Icône illustrant les étapes suivantes](../media/audio_conferencing_image9.png)<br/>Étapes suivantes|<ul><li>Commencez à planifier le déploiement de votre appareil.</li></ul>|

### <a name="device-deployment"></a>Déploiement d’appareil

Ensuite, vous devez créer votre plan pour découper les appareils et leurs périphériques de montage, puis procéder à l’installation et à la configuration.

|    |     |
|-----------|------------|
| ![Icône montrant les points de décision](../media/audio_conferencing_image7.png) <br/>Points de décision|<ul><li>Déterminez qui va gérer le déploiement d’un site par site.</li><li> Identifiez les ressources qui installent les barres de collaboration de Microsoft teams sur le site et qui effectuent les opérations de configuration et de test.</li></ul>|
| ![Icône illustrant les étapes suivantes](../media/audio_conferencing_image9.png)<br/>Étapes suivantes|<ul><li>Démarrez les tests d’appareil.</li></ul>|

### <a name="testing"></a> Tests

Après le déploiement des barres de collaboration de Microsoft Teams, vous devez les tester. Connectez-vous à l’appareil et assurez-vous que les fonctionnalités attendues fonctionnent sur l’appareil déployé. Nous vous recommandons vivement de vérifier que les périphériques apparaissent dans la section **barres de collaboration** sous l’onglet **périphériques** du centre d’administration Microsoft Teams. Il est également important de passer des appels et des réunions de test pour vérifier la qualité et les performances.

Nous vous recommandons de configurer les fichiers de construction pour le tableau de bord de qualité des appels (bord) dans le cadre de l’implémentation générale de Microsoft Teams, et de surveiller les tendances de qualité et de vous engager dans le processus de vérification de la qualité de l’appel. Pour plus d’informations, reportez-vous au [Guide de vérification de la qualité de l’utilisation](https://aka.ms/qerguide).

### <a name="asset-management"></a>Gestion des ressources

Dans le cadre du déploiement, vous pouvez mettre à jour votre registre de biens avec le nom de la salle, le compte de ressources connecté et les périphériques périphériques.

## <a name="related-topics"></a>Sujets associés

[Configurer les comptes pour les barres de collaboration de Microsoft teams à l’aide du centre d’administration Microsoft teams](resource-account-ui.md)

<!-- [Configure accounts for collaboration bars for Microsoft Teams using PowerShell](resource-account-ps.md) -->
