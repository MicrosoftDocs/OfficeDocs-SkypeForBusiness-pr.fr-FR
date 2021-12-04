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
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-apr2020
ms.assetid: 678689e4-d547-499b-be64-7d8f16dd8668
description: Lisez cet article pour en savoir plus sur le déploiement d Salles Microsoft Teams, y compris les phases de déploiement.
ms.openlocfilehash: 6a47ebd523e7b4806b3bc28251435942e9778844
ms.sourcegitcommit: 7eb66cb2955b17e89e1c162b6ca1b9bdb18189b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/04/2021
ms.locfileid: "61306179"
---
# <a name="deployment-overview"></a>Vue d’ensemble du déploiement

Le déploiement d Salles Microsoft Teams se décompose essentiellement en phases :

- Confirmation que vos emplacements de déploiement (espaces) répondent aux dépendances de déploiement
- Création Microsoft Teams comptes Skype Entreprise et Exchange et leur attribution sur les appareils de la console (voir Configurer des comptes [Salles Microsoft Teams)](rooms-configure-accounts.md)
- (Facultatif) Configuration d’Azure Monitor pour vos systèmes (voir Déployer la gestion des Salles Microsoft Teams [avec Azure Monitor](azure-monitor-deploy.md)
- Configuration salles Teams espaces de réunion et connexion des périphériques dont vous avez besoin (voir la documentation OEM de votre ensemble d’appareils)

## <a name="site-readiness"></a>État de préparation du site 

Pendant la livraison des appareils commandés à votre organisation, travaillez avec vos équipes de mise en réseau, de sites et d’av pour vous assurer que les dépendances de déploiement sont remplies et que chaque site et espace est prêt en termes d’alimentation, de mise en réseau et d’affichage. De plus, assurez-vous que les conditions d’installation physique sont respectées. Pour des raisons d’installation physique, consultez votre fournisseur et tirez parti de l’expérience de votre équipe AV lors de l’installation et de l’installation d’écrans et de l’exécution du cablage.

Pour plus d’informations sur ces dépendances, voir les liens d’aide à la planification ci-dessous :

-   [Vérification de la disponibilité du réseau](rooms-prep.md#check-network-availability)
-   [Certificats](rooms-prep.md#certificates)
-   [Proxy](rooms-prep.md#proxy)

**Pro conseil :** si vous devez utiliser des serveurs proxy pour fournir l’accès à Teams, [examinez cet article.](../proxy-servers-for-skype-for-business-online.md) En ce qui Microsoft Teams trafic de médias en temps réel sur des serveurs proxy, nous vous recommandons de contourner les serveurs proxy. Microsoft Teams trafic est déjà chiffré, les serveurs proxy ne le rendent donc pas plus sécurisé. Dans le cadre de votre déploiement à plus grande échelle, nous vous recommandons de suivre les instructions de la guide Préparer votre réseau pour [Teams](../prepare-network.md) à des fin de planification de la bande passante et d’évaluation de l’adapter à votre réseau en cas de trafic en temps réel.

|  &nbsp;  | &nbsp;    |
|-----------|------------|
| ![confirmez les sites.](../media/audio_conferencing_image7.png) <br/>Points de décision|<ul><li>Confirmez que vos sites répondent aux exigences essentielles pour Salles Microsoft Teams.</li><li>Confirmez que vous avez fourni suffisamment de bande passante pour chaque site.</li></ul>| 
| ![planifier le déploiement d’appareils.](../media/audio_conferencing_image9.png)<br/>Étapes suivantes|<ul><li>Commencez à planifier le déploiement et la configuration de votre appareil.</li></ul>| 

## <a name="service-readiness"></a>Préparation du service

Pour préparer votre déploiement Salles Microsoft Teams, vous pouvez effectuer les tâches clés suivantes :

-   Définissez Salles Microsoft Teams comptes de ressources.
-   Si vous rejoignez Teams Room to Azure Active Directory, préparez un groupe Azure AD dynamique de manière à conserver tous les salles Teams ressources de l’équipe. Cela simplifiera la gestion future, telle que l’application de stratégies d’accès conditionnel.
-   Si vous rejoignez Teams Room à Active Directory, préparez une unité d’organisation et un groupe Active Directory pour conserver vos comptes de machine et de service Salles Microsoft Teams et éventuellement préparer les objets de stratégie de groupe pour activer la remotation PowerShell.

### <a name="define-microsoft-teams-rooms-resource-account-features"></a>Définir Salles Microsoft Teams fonctionnalités de compte de ressource 

Selon les scénarios de collaboration que vous avez décidé d’activer avec votre déploiement Salles Microsoft Teams, vous devez déterminer les fonctionnalités que vous affectez à chaque salle Microsoft Teams que vous activez.

| **Scénario** | **Description** | **Salles Microsoft Teams fonctionnalité de compte de service** |
|---------- |------------- | --- |
| Réunions interactives            | utilisation de la voix, de la vidéo et du partage d’écran ; faire de l’Salles Microsoft Teams ressource bookable                     | Activé pour les Microsoft Teams ou les Skype Entreprise; activé pour les Exchange ressources (boîte aux lettres de ressources) |
| Conférence rendez-vous            | Avoir un numéro de téléphone de conférence audio lorsque vous appuyez sur « Nouvelle réunion » sur la console | Activé pour l’audioconférence                                          |
| Appels PSTN sortants/entrants | Activer la console Salles Microsoft Teams pour effectuer et recevoir des appels PSTN                                         | Activé pour les Système téléphonique                                                |

Pour plus d’informations sur Salles Microsoft Teams comptes, voir Configurer [des comptes pour Salles Microsoft Teams.](rooms-configure-accounts.md)


|  &nbsp;  |  &nbsp;   |
|-----------|------------|
| ![prise en charge des scénarios.](../media/audio_conferencing_image7.png) <br/>Points de décision|<ul><li>Déterminez les scénarios que vous prendrez en charge et identifiez les conditions de licence requises Salles Microsoft Teams comptes de service.</li></ul>| 
| ![préparez l’ordinateur hôte.](../media/audio_conferencing_image9.png)<br/>Étapes suivantes|<ul><li>Préparez-vous à héberger des comptes d’ordinateur et de service.</li></ul>| 


_Exemple de Salles Microsoft Teams table de planification d’un compte de service_

| **Site**  | **Nom de la salle** | **Type de salle** | **Capacités des salles à venir**                                                 | **Salles Microsoft Teams fonctionnalités de compte**                                                                                         |
|-----------|---------------|---------------|------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------|
| London HQ | Desso         | Moyen        | 1 écran, audio et vidéo plus présentation <br>Accès aux conférences téléphoniques<br> Accès PSTN  | Activé pour les Exchange (boîte aux lettres de ressources) <br>Activé pour l’audioconférence <br>Activé pour les Système téléphonique |
| Sydney HQ | Hill          | Grande         | 2 écrans, audio et vidéo plus présentation<br>Accès aux conférences téléphoniques<br> Accès PSTN  | Activé pour les Skype Entreprise <br>Activé pour les Exchange (boîte aux lettres de ressources)<br> Activé pour l’audioconférence <br>Activé pour les Système téléphonique |


### <a name="prepare-to-host-microsoft-teams-rooms-and-resource-accounts-optional"></a>Se préparer à héberger des Salles Microsoft Teams ressources et des comptes de ressources (facultatif)

Pour vous permettre de gérer vos comptes de ressources et de les Salles Microsoft Teams et de les signaler, préparez votre annuaire Active Directory ou votre compte de ressources Azure Active Directory (Azure AD). 

Définir un groupe d’utilisateurs ou Active Directory local à Azure Active Directory ajouter tous les comptes de service Salles Microsoft Teams (utilisateurs). Si vous utilisez Azure Active Directory, envisagez d’utiliser un groupe dynamique pour ajouter et supprimer automatiquement des comptes de ressources du groupe.

Définissez une unité d’organisation dans votre hiérarchie Active Directory en local pour conserver tous les comptes d’ordinateur Salles Microsoft Teams (s’ils sont joints au domaine) et une unité organisationnelle pour conserver tous les comptes d’Salles Microsoft Teams utilisateurs locaux. Désactivez l’héritage des stratégies de groupe pour vous assurer que vous appliquez uniquement les stratégies que vous souhaitez appliquer aux stratégies Salles Microsoft Teams.

Créez un objet de stratégie de groupe affecté à l’unité d’organisation qui Salles Microsoft Teams comptes informatiques. Utilisez-la pour : 

-   [Définissez les paramètres d’alimentation et de compte local.](rooms-operations.md#configuring-group-policy-for-microsoft-teams-rooms)
-   Activer Windows mise à jour.
-   Activez la remotation PowerShell. Vous pouvez configurer un script de démarrage pour exécuter un script : Enable-PSRemoting -Force

Vous pouvez utiliser PowerShell pour effectuer plusieurs activités de gestion à distance, notamment obtenir et définir des informations de configuration. La remotation PowerShell  doit être activée avant toute gestion à distance de PowerShell et doit être prise en considération dans le cadre de vos processus de déploiement ou configurée via une stratégie de groupe. Pour plus d’informations sur ces fonctionnalités et leur activation, voir [Maintenance et opérations.](rooms-operations.md#remote-management-using-powershell) 


## <a name="configuration-and-deployment"></a>Configuration et déploiement 

La planification de la configuration et du déploiement couvre les aspects clés suivants :

-   Provisionnage de compte
-   Installation de logiciels d’appareil
-   Déploiement d’appareils
-   Salles Microsoft Teams configuration des applications et périphériques
-    Tests
-   Gestion des biens

### <a name="account-provisioning"></a>Provisionnage de compte 

Chaque Salles Microsoft Teams nécessite un compte de ressource dédié et unique qui doit être activé pour les appareils Microsoft Teams ou Skype Entreprise, et Exchange. Une boîte aux lettres de salle doit être hébergée sur Exchange. Le traitement du calendrier doit être configuré pour que l’appareil puisse accepter automatiquement les demandes de réunion entrantes. Pour plus d’informations sur la création de ces comptes, voir Configurer [des comptes pour Salles Microsoft Teams.](rooms-configure-accounts.md) 

**Pro conseil** : chaque Salles Microsoft Teams doit avoir un nom d’ordinateur valide et unique sur votre réseau. De nombreux systèmes de surveillance et d’alerte affichent le nom de l’ordinateur en tant qu’identificateur clé. Il est donc important de développer une convention d’affectation de noms pour les déploiements Salles Microsoft Teams qui permet au personnel de support de localiser facilement l’Salles Microsoft Teams pour qui une action a été signalée. Par exemple, vous pouvez utiliser un modèle MTR-*Nom* de la salle de -  site (MTR-LON-S). 

|  &nbsp;  | &nbsp;    |
|-----------|------------|
| ![convention d’attribution de noms.](../media/audio_conferencing_image7.png) <br/>Points de décision|<ul><li>Décidez de la convention d’affectation de noms pour Salles Microsoft Teams de ressources.</li><li>Décidez si vous devez créer des comptes individuels ou utiliser des scripts d’approvisionnement en bloc.</li></ul>| 
| ![étapes suivantes.](../media/audio_conferencing_image9.png)<br/>Étapes suivantes|<ul><li>Commencez à planifier le déploiement de votre appareil.</li></ul>| 


### <a name="device-software-installation"></a>Installation de logiciels d’appareil 

salles Teams est préinstallé par le OEM.

Nous fournissons des instructions sur l’utilisation du moniteur [Microsoft Azure](/skypeforbusiness/plan-your-deployment/clients-and-devices/azure-monitor) pour surveiller le déploiement d’Salles Microsoft Teams ainsi que des rapports sur la disponibilité, les erreurs matérielles/logicielles et la version Salles Microsoft Teams’application. Si vous décidez d’utiliser la suite Microsoft Operations Management, vous devez installer l’agent de la suite Operations Management dans le cadre du processus d’installation du logiciel et configurer les informations de connexion à l’espace de travail de votre espace de travail. 

Vous de même déterminer si l’Salles Microsoft Teams sera joint au domaine. Vous pouvez trouver des informations sur les avantages de la jointation d’un domaine dans la configuration d’une stratégie de [groupe Salles Microsoft Teams.](rooms-operations.md#configuring-group-policy-for-microsoft-teams-rooms) 

| &nbsp;   |  &nbsp;   |
|-----------|------------|
| ![d’attribution des noms de périphériques à des points de décision.](../media/audio_conferencing_image7.png) <br/>Points de décision|<ul><li>Décidez Salles Microsoft Teams convention d’affectation de noms de comptes de ressources à utiliser lors de votre déploiement.</li><li>Décidez si vous devez rejoindre Salles Microsoft Teams votre domaine. </li><li>Décidez si vous allez utiliser le moniteur Azure pour surveiller le déploiement Salles Microsoft Teams déploiement.</li> 
| ![étapes suivantes du plan d’appareil.](../media/audio_conferencing_image9.png)<br/>Étapes suivantes|<ul><li>Commencez à planifier l’approche de déploiement de votre appareil.</li></ul>| 


### <a name="device-deployment"></a>Déploiement d’appareils

Après avoir décidé comment créer et responsable vos comptes de ressources Salles Microsoft Teams, créez votre plan pour expédier les appareils et les périphériques affectés à vos salles, puis procédez à l’installation et à la configuration. 


|  &nbsp;  |   &nbsp;  |
|-----------|------------|
| ![gérer le déploiement site par site.](../media/audio_conferencing_image7.png) <br/>Points de décision|<ul><li>Décidez qui gérera le déploiement site par site.</li><li> Identifiez les ressources qui seront en mesure d’installer Salles Microsoft Teams site et entreprenons la configuration et les tests.</li></ul>| 
| ![démarrer le test de l’appareil.](../media/audio_conferencing_image9.png)<br/>Étapes suivantes|<ul><li>Démarrez le test de l’appareil.</li></ul>| 

_Exemple de table de déploiement_

| **Site**  | **Nom de la salle** | **Type de salle** | **Salles Microsoft Teams système informatique**  | **Périphériques**  | **Salles Microsoft Teams nom de l’ordinateur**  | **Salles Microsoft Teams de ressources**  |
|-----------|---------------|---------------|-----------------------------------|------------------|------------------------------------------|---------------------------------------------|
| London HQ | Desso         | Moyen        |                                   |                  |                                          |                                             |
| Sydney HQ | Hill          | Grande         |                                   |                  |                                          |                                             |

### <a name="microsoft-teams-rooms-application-and-peripheral-device-configuration"></a>Salles Microsoft Teams configuration des applications et périphériques 

Une fois que chaque système Salles Microsoft Teams a été déployé physiquement et que les périphériques pris en charge se sont connectés, vous devez configurer l’application Salles Microsoft Teams pour affecter le compte de ressource et le mot de passe Salles Microsoft Teams pour activer l’salles Teams  pour vous y Microsoft Teams ou Skype Entreprise, puis Exchange.

Vous pouvez configurer manuellement chaque Salles Microsoft Teams système informatique. Vous pouvez également utiliser un fichier de configuration XML stocké de façon centralisée Salles Microsoft Teams XML pour gérer les paramètres de l’application.

Pour plus d’informations sur l’utilisation du fichier de configuration XML, voir Gérer un fichier de configuration XML pour gérer Salles Microsoft Teams à distance avec un [fichier de configuration XML.](xml-config-file.md) 

Vous pouvez utiliser [PowerShell à distance pour](rooms-operations.md#remote-management-using-powershell) tirer le Salles Microsoft Teams configuration nécessaire pour la déclaration des besoins. 

| &nbsp;   |  &nbsp;   |
|-----------|------------|
| ![configurez le point de décision.](../media/audio_conferencing_image7.png) <br/>Points de décision|<ul><li>Décidez si vous devez configurer manuellement chaque Salles Microsoft Teams système informatique ou utiliser un fichier XML central (un par Salles Microsoft Teams appareil).</li></ul>| 
| ![approche à distance des étapes suivantes.](../media/audio_conferencing_image9.png)<br/>Étapes suivantes|<ul><li>Définissez votre approche de la gestion à distance.</li></ul>| 

### <a name="testing"></a> Tests

Une salles Teams que vous avez été déployé, vous devez la tester. Vérifiez que les fonctionnalités répertoriées dans [Salles Microsoft Teams’aide](https://support.microsoft.com/en-us/office/microsoft-teams-rooms-help-e667f40e-5aab-40c1-bd68-611fe0002ba2?ui=en-us&rs=en-us&ad=us) fonctionnent sur l’appareil déployé. Nous recommandons vivement à l’équipe de déploiement de vérifier que Salles Microsoft Teams apparaît dans Teams centre d’administration. Il est également important de tester la qualité des appels et des réunions. Pour plus d’informations, consultez cette [liste de contrôle utile pour le déploiement.](console.md#microsoft-teams-rooms-deployment-checklist)

Dans le cadre du déploiement général de la Teams ou de la Skype Entreprise, nous vous recommandons de configurer la création de fichiers pour le tableau de bord de qualité des appels, de surveiller les tendances en matière de qualité et de vous impliquer dans le processus de révision de la qualité de l’expérience. Pour plus d’informations, voir [Améliorer et surveiller la qualité des appels pour Teams.](../monitor-call-quality-qos.md) 

### <a name="asset-management"></a>Gestion des biens

Dans le cadre du déploiement, vous pouvez mettre à jour votre registre de biens avec le nom de la salle, le nom de Salles Microsoft Teams, le compte de ressource connecté Salles Microsoft Teams et les périphériques affectés. 

_Exemple de table des biens_

| **Site**  | **Nom de la salle** | **Type de salle** | **Salles Microsoft Teams non en série.**  | **Périphériques/ Numéros de série./ Ports**  | **Salles Microsoft Teams nom de l’ordinateur**  | **Salles Microsoft Teams service client**  | **Date de déploiement** |
|-----------|---------------|---------------|------------------------------------------|------------------------------------------|------------------------------------------|--------------------------------------------|-------------------|
| London HQ | Desso         | Moyen        |                                          |                                          |                                          |                                            |                   |
| Sydney HQ | Hill          | Grande         |                                          |                                          |                                          |                                            |                   |