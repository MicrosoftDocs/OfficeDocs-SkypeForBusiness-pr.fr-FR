---
title: Déployer les Salles Microsoft Teams
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-apr2020
ms.assetid: 678689e4-d547-499b-be64-7d8f16dd8668
description: Lisez cet article pour en savoir plus sur le déploiement de salles Microsoft Teams, y compris les phases de déploiement.
ms.openlocfilehash: 3ac6ceabd1d421551ab3b9404688bd4a9302e3d6
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117462"
---
# <a name="deployment-overview"></a>Vue d’ensemble du déploiement

Le déploiement de salles Microsoft Teams se décompose essentiellement en phases :

- Confirmation que vos emplacements de déploiement (salles) répondent aux dépendances de déploiement
- Création de comptes Microsoft Teams ou Skype Entreprise et Exchange et affectation de ces derniers aux appareils de la console (voir Configurer des comptes pour les [salles Microsoft Teams)](rooms-configure-accounts.md)
- Réimagie des tablettes Microsoft Surface pour les faire fonctionner comme consoles de salles [Microsoft Teams](console.md) (voir Configurer une console Salles Microsoft Teams ou le guide de déploiement de masse de Salles Microsoft [Teams)](rooms-scale.md)
- (Facultatif) Configuration de la suite Microsoft Operations Management suite pour vos systèmes (voir Déployer la gestion des salles [Microsoft Teams avec Azure Monitor)](azure-monitor-deploy.md)
- Configuration de consoles dans les salles de réunion et connexion des périphériques dont vous avez besoin (voir la documentation OEM pour votre ensemble d’appareils)

Les techniciens av peuvent être utilisés pour la dernière tâche, mais le service informatique de votre organisation doit accomplir les autres parties du processus. 


## <a name="site-readiness"></a>État de préparation du site 

Pendant la livraison des appareils commandés à votre organisation, travaillez avec votre réseau, vos installations et vos équipes AV pour vous assurer que les dépendances de déploiement sont remplies et que chaque site et salle est prêt en termes de puissance, de mise en réseau et d’affichage. De plus, assurez-vous que les conditions d’installation physique sont respectées. Pour des raisons d’installation physique, rendez-vous sur le site du fournisseur et tirez parti de l’expérience de votre équipe AV lors de l’installation et de l’installation d’écrans et de l’exécution du cablage.

Pour plus d’informations sur ces dépendances, voir les liens d’aide à la planification ci-dessous :

-   [Vérification de la disponibilité du réseau](rooms-prep.md#check-network-availability)
-   [Certificats](rooms-prep.md#certificates)
-   [Proxy](rooms-prep.md#proxy)

**Conseil professionnel** : si vous avez l’intention d’utiliser des serveurs proxy pour fournir l’accès à Teams ou à Skype Entreprise Online, examinez tout d’abord [cet article.](../proxy-servers-for-skype-for-business-online.md) En ce qui concerne le trafic Skype Entreprise via des serveurs proxy, nous vous recommandons de contourner complètement les serveurs proxy. Le trafic de Skype Entreprise étant déjà chiffré, les serveurs proxy ne le rendent pas plus sécurisé. Dans le cadre de votre déploiement à plus grande échelle, nous vous recommandons de suivre les recommandations de La préparation de votre réseau pour la planification de la bande passante de [Teams](../prepare-network.md) et d’évaluation de l’adapter à votre réseau pour le trafic en temps réel.

|    |     |
|-----------|------------|
| ![confirmer les sites](../media/audio_conferencing_image7.png) <br/>Points de décision|<ul><li>Confirmez que vos sites répondent aux exigences essentielles pour les salles Microsoft Teams.</li><li>Confirmez que vous avez fourni suffisamment de bande passante pour chaque site.</li></ul>| 
| ![planifier le déploiement d’appareils](../media/audio_conferencing_image9.png)<br/>Étapes suivantes|<ul><li>Commencez à planifier le déploiement et la configuration de votre appareil.</li></ul>| 

## <a name="service-readiness"></a>Préparation du service

Pour préparer le déploiement de salles Microsoft Teams, vous pouvez effectuer les tâches clés suivantes :

-   Définissez les fonctionnalités du compte de service Salles Microsoft Teams.
-   Préparez une unité d’organisation et un groupe Active Directory pour conserver vos comptes d’ordinateur et de service Microsoft Teams Rooms, et éventuellement préparer les objets de stratégie de groupe pour activer la remotation PowerShell.

### <a name="define-microsoft-teams-rooms-service-account-features"></a>Définir les fonctionnalités de compte du service Salles Microsoft Teams 

Selon les scénarios de collaboration que vous avez décidé d’activer avec votre déploiement de salles Microsoft Teams, vous devrez déterminer les fonctionnalités que vous affectez à chaque compte de service Salles Microsoft Teams que vous activez.

| **Scénario** | **Description** | **Fonctionnalité de compte de service Salles Microsoft Teams** |
|---------- |------------- | --- |
| Réunions interactives            | utilisation de la voix, de la vidéo et du partage d’écran ; faire des salles Microsoft Teams une ressource bookable                     | Activé pour Skype Entreprise, activé pour Exchange (boîte aux lettres de ressources) |
| Conférence rendez-vous            | Activer les réunions *démarrées directement à partir* de la console Salles de Microsoft Teams avec les coordonnées de conférence rendez-vous | Activé pour l’audioconférence                                          |
| Appels PSTN sortants/entrants | Activer la console Salles Microsoft Teams pour effectuer et recevoir des appels PSTN                                         | Activé pour le système téléphonique                                                |

Pour plus d’informations sur les comptes salles Microsoft Teams, voir Configurer des comptes pour [les salles Microsoft Teams.](rooms-configure-accounts.md)


|    |     |
|-----------|------------|
| ![prise en charge des scénarios](../media/audio_conferencing_image7.png) <br/>Points de décision|<ul><li>Déterminez les scénarios que vous prendrez en charge et identifiez les conditions de licence requises pour vos comptes de service Salles Microsoft Teams.</li></ul>| 
| ![préparer l’ordinateur hôte](../media/audio_conferencing_image9.png)<br/>Étapes suivantes|<ul><li>Préparez-vous à héberger des comptes d’ordinateurs et de services.</li></ul>| 


_Exemple de table de planification de compte du service Salles Microsoft Teams_

| **Site**  | **Nom de la salle** | **Type de salle** | **Capacités des salles à venir**                                                 | **Fonctionnalités du compte Salles Microsoft Teams**                                                                                         |
|-----------|---------------|---------------|------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------|
| London HQ | Sy         | Moyen        | 1 écran, audio et vidéo plus présentation <br>Accès aux conférences téléphoniques<br> Accès PSTN  | Activé pour Skype Entreprise, activé pour Exchange (boîte aux lettres de ressources) <br>Activé pour l’audioconférence <br>Activé pour le système téléphonique |
| Sydney HQ | Hill          | Grande         | 2 écrans, audio et vidéo plus présentation<br>Accès aux conférences téléphoniques<br> Accès PSTN  | Activé pour Skype Entreprise, activé pour Exchange (boîte aux lettres de ressources)<br> Activé pour l’audioconférence <br>Activé pour le système téléphonique |


### <a name="prepare-to-host-microsoft-teams-rooms-machine-and-service-accounts-optional"></a>Préparer l’hôte des comptes de machine et de service Salles Microsoft Teams (facultatif)

Pour vous permettre de gérer et de rapporter sur votre ordinateur et vos comptes de service Microsoft Teams Rooms, préparez votre annuaire Active Directory ou Azure Active Directory (Azure AD) local. 

Définissez un groupe Active Directory ou Azure AD local pour ajouter tous les comptes de service microsoft Teams Rooms (utilisateur), puis créez des rapports d’utilisation à l’aide de l’cmdlet PowerShell Get-CSUserSession dans le déploiement de salles Microsoft Teams. Par exemple, créez un groupe nommé SkypeRoomSystemsv2-Service-Accounts. 


Définissez une unité d’organisation dans votre hiérarchie Active Directory ou Azure AD pour conserver tous les comptes d’ordinateurs (s’ils sont membres du domaine) et une unité organisationnelle pour conserver tous les comptes d’utilisateurs des salles Microsoft Teams. Si vous créez une unité d’organisation pour les comptes d’ordinateurs Microsoft Teams Rooms, vous pouvez désactiver l’héritage pour vous assurer que vous appliquez uniquement les stratégies que vous souhaitez appliquer aux salles Microsoft Teams jointes à un domaine. 

Créez un objet de stratégie de groupe affecté à l’unité de l’organisation qui contient vos comptes d’ordinateurs Salle Microsoft Teams. Utilisez-la pour : 

-   [Définissez les paramètres d’alimentation et de compte local.](rooms-operations.md#configuring-group-policy-for-microsoft-teams-rooms)
-   Activer Windows Update.
-   Activer la remotation PowerShell. Vous pouvez configurer un script de démarrage pour exécuter un script : Enable-PSRemoting -Force

Vous pouvez utiliser PowerShell pour effectuer plusieurs activités de gestion à distance, notamment obtenir et définir des informations de configuration. La remotation PowerShell  doit être activée avant toute gestion à distance de PowerShell et doit être prise en considération dans le cadre de vos processus de déploiement ou configurée via une stratégie de groupe. Pour plus d’informations sur ces fonctionnalités et leur activation, voir [Maintenance et opérations.](rooms-operations.md#remote-management-using-powershell) 


## <a name="configuration-and-deployment"></a>Configuration et déploiement 

La planification de la configuration et du déploiement couvre les aspects clés suivants :

-   Provisionnage de compte
-   Installation de logiciels d’appareil
-   Déploiement d’appareils
-   Configuration de l’application Salles Microsoft Teams et de l’appareil périphérique
-    Tests
-   Gestion des biens

### <a name="account-provisioning"></a>Provisionnage de compte 

Chaque appareil Salle Microsoft Teams nécessite un compte de ressource dédié et unique qui doit être activé pour Microsoft Teams, Skype Entreprise et Exchange. Ce compte doit avoir une boîte aux lettres de salle hébergée sur Exchange et être activé en tant que salle de réunion dans le déploiement teams ou Skype Entreprise. Sur le côté Exchange, le traitement du calendrier doit être configuré pour que l’appareil puisse accepter automatiquement les demandes de réunion entrantes. Pour plus d’informations sur la création de ces comptes, voir Configurer des comptes pour les [salles Microsoft Teams.](rooms-configure-accounts.md) 

**Conseil professionnel** : assurez-vous que les noms d’affichage de ces comptes sont descriptifs et faciles à comprendre. Voici les noms que les utilisateurs voient lors de la recherche et de l’ajout de systèmes salles Microsoft Teams aux réunions. Certaines organisations utilisent le nom de salle de *site* de la convention (Capacité maximale de salle )-RS, par exemple Domaine (salle de conférence de 12 personnes à Londres) qui peut avoir le nom complet - LON-X(12)-RS. 

|    |     |
|-----------|------------|
| ![Décider d’une convention d’attribution de noms](../media/audio_conferencing_image7.png) <br/>Points de décision|<ul><li>Déterminez la convention d’attribution de noms de vos comptes Salles Microsoft Teams.</li><li>Décidez si vous devez créer des comptes individuels ou utiliser des scripts d’approvisionnement en bloc.</li></ul>| 
| ![étapes suivantes](../media/audio_conferencing_image9.png)<br/>Étapes suivantes|<ul><li>Commencez à planifier le déploiement de votre appareil.</li></ul>| 


### <a name="device-software-installation"></a>Installation de logiciels d’appareil 

Lorsque vous planifiez le déploiement de Salles Microsoft Teams, vous pouvez envisager d’installer le logiciel requis. Les scénarios et approches courants sont décrits dans le tableau suivant. 

| **Scénario**            | **Approche**         |
|-------------------------|-----------------------|   
|Déploiement de quelques appareils De salle Microsoft Teams (<10). | Si vous utilisez des salles Microsoft Teams basées sur Surface Pro, suivez les [instructions d’installation](console.md)pour une installation par appareil. [Cette vidéo pratique vous guide tout au long du processus.](https://content.cloudguides.com/guides/Configure%20the%20Skype%20Room%20Systems%20console) Si vous utilisez une solution intégrée, déployez le déploiement à l’aide de l’image du fournisseur et configurez les paramètres selon vos besoins. |
| Déploiement de 10 à 50 appareils à partir d’un fournisseur unique.     | Créez une image basée sur WIM, marquez une pause après l’étape [6](console.md)dans les conseils et capturez une image de distribution à utiliser avec votre technologie de distribution de clonement.    |
| Déploiement de plus de 50 appareils de salles Microsoft Teams, déploiement d’appareils de plusieurs fournisseurs ou resserrement d’agents spécifiques de l’organisation dans le cadre du déploiement. | Utilisez une plateforme de distribution et de build logicielle basée sur un séquenceur de tâches, telle que [Microsoft Endpoint Configuration Manager.](rooms-scale.md)  |


**Conseil professionnel** : chaque salle Microsoft Teams doit avoir un nom d’ordinateur valide et unique sur votre réseau. De nombreux systèmes de surveillance et d’alerte affichent le nom de l’ordinateur comme identificateur clé. Il est donc important de développer une convention d’affectation de noms pour les déploiements de salles Microsoft Teams, ce qui permet au personnel de support technique de localiser facilement les salles Microsoft Teams signalées comme nécessitant une action. Par exemple, vous pouvez utiliser un modèle MTR-*Nom* de la salle de -  site (MTR-LON-S). 

Dans le cadre du déploiement, vous devez également envisager votre stratégie de gestion et de configuration des comptes [locaux créés](/skypeforbusiness/plan-your-deployment/clients-and-devices/skype-room-systems-v2-0#local-accounts) par le programme d’installation de l’application Salles Microsoft Teams.

Nous fournissons des instructions sur l’utilisation du moniteur [Microsoft Azure](/skypeforbusiness/plan-your-deployment/clients-and-devices/azure-monitor) pour surveiller le déploiement de Salles Microsoft Teams et signaler les erreurs de disponibilité, les erreurs matérielles/logicielles et la version de l’application Salles Microsoft Teams. Si vous décidez d’utiliser la suite Microsoft Operations Management, vous devez installer l’agent de la suite Operations Management dans le cadre du processus d’installation du logiciel et configurer les informations de connexion à l’espace de travail de votre espace de travail. 

Vous de même déterminer si les salles Microsoft Teams seront jointes au domaine. Des informations sur les avantages de l’adhésion à un domaine sont disponibles dans le domaine [Skype Room System qui joint les considérations.](domain-joining-considerations.md) 

|    |     |
|-----------|------------|
| ![Attribution d’un nom de périphérique à des points de décision](../media/audio_conferencing_image7.png) <br/>Points de décision|<ul><li>Décidez de la convention d’affectation de noms d’appareils de Microsoft Teams Rooms à utiliser lors de votre déploiement.</li><li>Décidez si vous devez joindre des appareils Microsoft Teams Rooms à votre domaine et comment gérer et configurer des comptes locaux. </li><li>Décidez si vous allez utiliser la suite Operations Management Suite pour surveiller le déploiement des salles Microsoft Teams.</li><li>Déterminez la méthode que vous utiliserez pour déployer le logiciel et les agents dans le système Salles Microsoft Teams en vue du déploiement de l’appareil. </li></ul>| 
| ![Étapes suivantes pour planifier un appareil](../media/audio_conferencing_image9.png)<br/>Étapes suivantes|<ul><li>Commencez à planifier l’approche de déploiement de votre appareil.</li></ul>| 


### <a name="device-deployment"></a>Déploiement d’appareils

Après avoir déployé votre logiciel dans les unités Salles Microsoft Teams, créez votre offre pour expédier les appareils et les périphériques affectés à vos salles, puis procédez à l’installation et à la configuration. 


|    |     |
|-----------|------------|
| ![gérer le déploiement site par site](../media/audio_conferencing_image7.png) <br/>Points de décision|<ul><li>Décidez qui gérera le déploiement site par site.</li><li> Identifiez les ressources qui installeront les appareils salles Microsoft Teams sur site et entreprenons la configuration et les tests.</li></ul>| 
| ![Démarrer le test de l’appareil](../media/audio_conferencing_image9.png)<br/>Étapes suivantes|<ul><li>Démarrez le test de l’appareil.</li></ul>| 

_Exemple de table de déploiement_

| **Site**  | **Nom de la salle** | **Type de salle** | **Système de salles Microsoft Teams**  | **Périphériques**  | **Nom de l’ordinateur salles Microsoft Teams**  | **Compte de ressource Salles Microsoft Teams**  |
|-----------|---------------|---------------|-----------------------------------|------------------|------------------------------------------|---------------------------------------------|
| London HQ | Sy         | Moyen        |                                   |                  |                                          |                                             |
| Sydney HQ | Hill          | Grande         |                                   |                  |                                          |                                             |

### <a name="microsoft-teams-rooms-application-and-peripheral-device-configuration"></a>Configuration de l’application Salles Microsoft Teams et de l’appareil périphérique 

Une fois que chaque système Salles Microsoft Teams a été déployé physiquement et que les périphériques pris en charge sont connectés, vous devez configurer l’application Salles Microsoft Teams pour affecter le compte de ressource et le mot de passe créés précédemment pour que le système Salles Microsoft Teams se connecte à Microsoft Teams ou à Skype Entreprise et Exchange. Il est important de tirer parti des périphériques audio et vidéo USB certifiés liés ailleurs dans le document. Ne pas le faire peut entraîner un comportement imprévisible. 

Vous pouvez configurer manuellement chaque système de salles Microsoft Teams. Vous pouvez également utiliser un fichier de configuration XML stocké de façon centralisée par-Microsoft Teams Rooms pour gérer les paramètres de l’application et tirer parti d’un script d’po de démarrage pour réappliquer la configuration de votre choix, chaque fois que le système des salles Microsoft Teams démarre. 

Pour plus d’informations sur l’utilisation du fichier de configuration XML, voir Gérer les paramètres d’une console de salles Microsoft Teams à distance avec un [fichier de configuration XML.](xml-config-file.md) 

Vous pouvez utiliser [PowerShell à distance pour](rooms-operations.md#remote-management-using-powershell) tirer profit de la configuration des salles Microsoft Teams pour répondre aux besoins en matière de rapport. 

|    |     |
|-----------|------------|
| ![configuration du point de décision](../media/audio_conferencing_image7.png) <br/>Points de décision|<ul><li>Décidez si vous devez configurer manuellement chaque système salles Microsoft Teams ou utiliser un fichier XML central (un par appareil Salles Microsoft Teams).</li></ul>| 
| ![Approche à distance des étapes suivantes](../media/audio_conferencing_image9.png)<br/>Étapes suivantes|<ul><li>Définissez votre approche de la gestion à distance.</li></ul>| 

### <a name="testing"></a> Tests

Une fois le système salles Microsoft Teams déployé, vous devez le tester. Vérifiez que les fonctionnalités répertoriées dans l’aide [de Salles Microsoft Teams](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) fonctionnent sur l’appareil déployé. Nous recommandons vivement à l’équipe de déploiement de vérifier que Salles Microsoft Teams se connecte à la suite Microsoft Operations Management Suite (si elle est utilisée). Il est également important de tester la qualité des appels et des réunions. Pour plus d’informations, consultez cette [liste de contrôle utile pour le déploiement.](console.md#microsoft-teams-rooms-deployment-checklist)

Dans le cadre du déploiement général de Teams ou de Skype Entreprise, nous vous recommandons de configurer la création de fichiers pour le tableau de bord de qualité des appels, de surveiller les tendances de qualité et de vous impliquer dans le processus de révision de la qualité de l’expérience. Pour plus d’informations, voir [Améliorer et surveiller la qualité des appels pour Teams.](../monitor-call-quality-qos.md) 

### <a name="asset-management"></a>Gestion des biens

Dans le cadre du déploiement, vous pouvez mettre à jour votre registre de biens avec le nom de la salle, le nom de l’appareil Salles Microsoft Teams, le compte de ressource connecté aux salles Microsoft Teams et les périphériques affectés (et les ports USB qu’ils utilisent). 

_Exemple de table des biens_

| **Site**  | **Nom de la salle** | **Type de salle** | **Numéro de série des Salles Microsoft Teams.**  | **Périphériques/ Numéros de série./ Ports**  | **Nom de l’ordinateur salles Microsoft Teams**  | **Compte de service Salles Microsoft Teams**  | **Date de déploiement** |
|-----------|---------------|---------------|------------------------------------------|------------------------------------------|------------------------------------------|--------------------------------------------|-------------------|
| London HQ | Sy         | Moyen        |                                          |                                          |                                          |                                            |                   |
| Sydney HQ | Hill          | Grande         |                                          |                                          |                                          |                                            |                   |