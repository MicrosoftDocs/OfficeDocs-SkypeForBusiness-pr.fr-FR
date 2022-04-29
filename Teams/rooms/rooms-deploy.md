---
title: Déployer les Salles Microsoft Teams
ms.author: czawideh
author: cazawideh
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
description: Lisez cet article pour en savoir plus sur le déploiement de Salles Microsoft Teams, y compris les phases de déploiement.
ms.openlocfilehash: 18a5d72fb9c11b34bb994734b8d064c3aaa2cdae
ms.sourcegitcommit: d16fb01f752d186445893ea8e3b0d4450a4a0e67
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/29/2022
ms.locfileid: "65125769"
---
# <a name="deployment-overview"></a>Vue d’ensemble du déploiement

Le déploiement de Salles Microsoft Teams se décompose essentiellement en phases :

- Confirmer que vos emplacements de déploiement (espaces) répondent aux dépendances de déploiement
- Création de comptes Microsoft Teams ou Skype Entreprise et Exchange et leur affectation à salles Teams (voir [Configurer des comptes pour Salles Microsoft Teams](rooms-configure-accounts.md))
- (Facultatif) Configuration d’Azure Monitor pour vos systèmes (voir [Déployer la gestion Salles Microsoft Teams avec Azure Monitor](azure-monitor-deploy.md)
- Configuration salles Teams dans les espaces de réunion et connexion des périphériques dont vous avez besoin (consultez la documentation OEM de votre ensemble d’appareils)

## <a name="site-readiness"></a>Préparation du site 

Pendant que les appareils commandés sont remis à votre organisation, collaborez avec vos équipes réseau, installations et av pour vous assurer que les dépendances de déploiement sont remplies et que chaque site et espace est prêt en termes de puissance, de mise en réseau et d’affichage. En outre, assurez-vous que les exigences d’installation physique sont remplies. Pour des considérations relatives à l’installation physique, consultez votre fournisseur et tirez parti de l’expérience de votre équipe av lors de l’installation et du montage d’écrans et de l’exécution du câblage.

Pour plus d’informations sur ces dépendances, consultez les liens d’aide à la planification ci-dessous :

-   [Vérification de la disponibilité du réseau](rooms-prep.md#check-network-availability)
-   [Certificats](rooms-prep.md#certificates)
-   [Proxy](rooms-prep.md#proxy)

**Pro Conseil** : si vous devez utiliser des serveurs proxy pour fournir l’accès à Teams, [commencez par consulter cet article](../proxy-servers-for-skype-for-business-online.md). Quand il s’agit de Microsoft Teams trafic multimédia en temps réel sur les serveurs proxy, nous vous recommandons de contourner complètement les serveurs proxy. Microsoft Teams trafic étant déjà chiffré, les serveurs proxy ne le rendent pas plus sécurisé et ajoutent de la latence au trafic en temps réel. Dans le cadre de votre déploiement plus large, nous vous recommandons de suivre les instructions fournies dans [Préparer votre réseau pour Teams pour](../prepare-network.md) la planification de la bande passante et l’évaluation de l’adéquation de votre réseau pour le trafic en temps réel.

|  &nbsp;  | &nbsp;    |
|-----------|------------|
| ![confirmer les sites.](../media/audio_conferencing_image7.png) <br/>Points de décision|<ul><li>Vérifiez que vos sites répondent aux exigences clés pour Salles Microsoft Teams.</li><li>Vérifiez que vous avez fourni une bande passante suffisante pour chaque site.</li></ul>| 
| ![planifier le déploiement de l’appareil.](../media/audio_conferencing_image9.png)<br/>Étapes suivantes|<ul><li>Commencez à planifier le déploiement et la configuration de votre appareil.</li></ul>| 

## <a name="service-readiness"></a>Préparation du service

Pour préparer votre déploiement Salles Microsoft Teams, effectuez les tâches centrales clés suivantes :

-   Définissez Salles Microsoft Teams comptes de ressources.
-   Si vous joignez salles Teams à Azure Active Directory, préparez un groupe Azure AD avec une appartenance dynamique pour contenir tous les comptes de ressources salles Teams. Cela simplifiera la gestion future, comme l’application de stratégies d’accès conditionnel. Pour tirer le meilleur parti de Azure AD groupes dynamiques, déterminez une convention d’affectation de noms qui identifiera de manière unique vos comptes de ressources salles Teams.
-   Si vous joignez salles Teams à Active Directory, préparez une unité d’organisation et un groupe Active Directory pour contenir vos comptes d’ordinateur et de ressources Salles Microsoft Teams et, éventuellement, préparez des objets stratégie de groupe (GPO) pour activer la communication à distance PowerShell.

### <a name="define-microsoft-teams-rooms-resource-account-features"></a>Définir Salles Microsoft Teams fonctionnalités du compte de ressource 

Selon les scénarios de collaboration que vous avez décidé d’activer avec votre déploiement Salles Microsoft Teams, vous devez déterminer les fonctionnalités et fonctionnalités que vous affectez à chaque Salles Microsoft Teams que vous activez.

| **Scénario** | **Description** | **fonctionnalité de compte de service Salles Microsoft Teams** |
|---------- |------------- | --- |
| Réunions interactives            | Utilisation de la voix, de la vidéo et du partage d’écran ; faire de l’Salles Microsoft Teams une ressource bookable                     | Activé pour Microsoft Teams ou Skype Entreprise ; activé pour Exchange (boîte aux lettres de ressources) |
| Conférence rendez-vous            | Disposer d’un numéro de téléphone d’audioconférence lors de l’appui sur « Nouvelle réunion » sur la console | Activé pour l’audioconférence                                          |
| Appels PSTN sortants/entrants | Activer la console Salles Microsoft Teams pour effectuer et recevoir des appels RTC                                         | Activé pour Système téléphonique                                                |

Pour plus d’informations sur Salles Microsoft Teams comptes, consultez [Configurer des comptes pour Salles Microsoft Teams](rooms-configure-accounts.md).


|  &nbsp;  |  &nbsp;   |
|-----------|------------|
| ![prise en charge du scénario.](../media/audio_conferencing_image7.png) <br/>Points de décision|<ul><li>Déterminez les scénarios que vous allez prendre en charge et identifiez les exigences de licence pour vos comptes de ressources Salles Microsoft Teams.</li></ul>| 
| ![préparer l’ordinateur hôte.](../media/audio_conferencing_image9.png)<br/>Étapes suivantes|<ul><li>Préparez-vous à héberger des comptes de machine et de ressources.</li></ul>| 


_Exemple de table de planification de compte de ressources Salles Microsoft Teams_

| **Site**  | **Nom de la salle** | **Type de salle** | **Fonctionnalités de salle futures**                                                 | **Salles Microsoft Teams fonctionnalités du compte**                                                                                         |
|-----------|---------------|---------------|------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------|
| Siège social de Londres | Curie         | Moyen        | 1 écran, audio et vidéo plus présentation <br>Accès aux conférences rendez-vous<br> Accès RTC  | Activé pour Exchange (boîte aux lettres de ressources) <br>Activé pour l’audioconférence <br>Activé pour Système téléphonique |
| Siège social de Sydney | Hill          | Grande         | 2 Écrans, audio et vidéo et présentation<br>Accès aux conférences rendez-vous<br> Accès RTC  | Activé pour Skype Entreprise <br>Activé pour Exchange (boîte aux lettres de ressources)<br> Activé pour l’audioconférence <br>Activé pour Système téléphonique |


### <a name="prepare-to-host-microsoft-teams-rooms-and-resource-accounts-optional"></a>Préparer l’hébergement des comptes de Salles Microsoft Teams et de ressources (facultatif)

Pour vous permettre de gérer et de créer des rapports sur vos comptes de Salles Microsoft Teams et de ressources, préparez votre Active Directory local ou Azure Active Directory (Azure AD). 

Définissez un groupe Active Directory local ou Azure Active Directory auquel ajouter tous les comptes de ressources Salles Microsoft Teams. Si vous utilisez Azure Active Directory, envisagez d’utiliser un groupe dynamique pour ajouter et supprimer automatiquement des comptes de ressources du groupe.

Définissez une unité organisationnelle dans votre hiérarchie Active Directory local pour contenir tous les comptes d’ordinateur Salles Microsoft Teams (s’ils sont joints au domaine) et une unité d’organisation pour contenir tous les comptes d’utilisateur Salles Microsoft Teams. Désactivez stratégie de groupe héritage pour vous assurer que vous appliquez uniquement les stratégies que vous avez l’intention d’appliquer au Salles Microsoft Teams joint au domaine.

Créez un objet stratégie de groupe affecté à l’unité d’organisation qui contient vos comptes d’ordinateur Salles Microsoft Teams. Utilisez cette option pour : 

-   [Définissez les paramètres d’alimentation et de compte local](rooms-operations.md#configuring-group-policy-for-microsoft-teams-rooms).
-   Activez Windows Update.
-   Activez la communication à distance PowerShell. Vous pouvez configurer un script de démarrage pour exécuter un script : Enable-PSRemoting -Force

Vous pouvez utiliser PowerShell pour effectuer plusieurs activités de gestion à distance, notamment l’obtention et la définition d’informations de configuration. La communication à distance PowerShell doit être activée *avant* qu’une gestion à distance PowerShell puisse avoir lieu et doit être prise en compte dans le cadre de vos processus de déploiement ou configurée via stratégie de groupe. Pour plus d’informations sur ces fonctionnalités et leur activation, consultez [Maintenance et opérations](rooms-operations.md#remote-management-using-powershell). 


## <a name="configuration-and-deployment"></a>Configuration et déploiement 

La planification de la configuration et du déploiement couvre les domaines clés suivants :

-   Provisionnement de comptes de ressources
-   Installation de logiciels d’appareil
-   Déploiement d’appareils
-   Salles Microsoft Teams configuration de l’application et de l’appareil périphérique
-    Tests
-   Gestion des ressources

### <a name="resource-account-provisioning"></a>Provisionnement de comptes de ressources 

Chaque appareil Salles Microsoft Teams nécessite un compte de ressource dédié et unique qui doit être activé pour les Microsoft Teams ou les Skype Entreprise, ainsi que pour les Exchange. Ce compte doit avoir une boîte aux lettres de salle hébergée sur Exchange. Le traitement du calendrier doit être configuré afin que l’appareil puisse accepter automatiquement les demandes de réunion entrantes. Pour plus d’informations sur la création de ces comptes, consultez [Configurer des comptes pour Salles Microsoft Teams](rooms-configure-accounts.md). 

**Pro Conseil** : chaque Salles Microsoft Teams doit avoir un nom de machine valide et unique sur votre réseau. De nombreux systèmes de surveillance et d’alerte affichent le nom de la machine en tant qu’identificateur de clé. Il est donc important de développer une convention d’affectation de noms pour Salles Microsoft Teams déploiements qui permet au personnel du support technique de localiser facilement les Salles Microsoft Teams signalés comme nécessitant une action. Par exemple, vous pouvez utiliser un modèle *MTR-SiteRoom*- *Name* (MTR-LON-CURIE). 

|  &nbsp;  | &nbsp;    |
|-----------|------------|
| ![décider de la convention d’affectation de noms.](../media/audio_conferencing_image7.png) <br/>Points de décision|<ul><li>Choisissez la convention d’affectation de noms pour vos comptes de ressources Salles Microsoft Teams.</li><li>Déterminez si vous allez créer des comptes individuels ou utiliser des scripts de provisionnement en bloc.</li></ul>| 
| ![étapes suivantes.](../media/audio_conferencing_image9.png)<br/>Étapes suivantes|<ul><li>Commencez à planifier le déploiement de votre appareil.</li></ul>| 


### <a name="device-software-installation"></a>Installation de logiciels d’appareil 

salles Teams est préinstallé par le fabricant d’équipement d’origine (OEM).

Nous fournissons des conseils sur l’utilisation [de Microsoft Azure Monitor](/skypeforbusiness/plan-your-deployment/clients-and-devices/azure-monitor) pour surveiller le déploiement Salles Microsoft Teams et signaler la disponibilité, les erreurs matérielles/logicielles et Salles Microsoft Teams version de l’application. Si vous décidez d’utiliser Microsoft Operations Management Suite, vous devez installer l’agent Operations Management Suite dans le cadre du processus d’installation du logiciel et configurer les informations de connexion de l’espace de travail pour votre espace de travail. 

Une autre considération est de savoir si le Salles Microsoft Teams sera joint à un domaine. Vous trouverez des informations sur les avantages de la jonction de domaine dans [La configuration de stratégie de groupe pour Salles Microsoft Teams](rooms-operations.md#configuring-group-policy-for-microsoft-teams-rooms). 

| &nbsp;   |  &nbsp;   |
|-----------|------------|
| ![les points de décision nommage de l’appareil.](../media/audio_conferencing_image7.png) <br/>Points de décision|<ul><li>Décidez de la convention d’affectation de noms de compte de ressource Salles Microsoft Teams à utiliser pendant votre déploiement.</li><li>Décidez si vous allez joindre Salles Microsoft Teams appareils à votre domaine. </li><li>Déterminez si vous allez utiliser Azure Monitor pour surveiller le déploiement Salles Microsoft Teams.</li> 
| ![étapes suivantes planifiez l’appareil.](../media/audio_conferencing_image9.png)<br/>Étapes suivantes|<ul><li>Commencez à planifier l’approche de déploiement de votre appareil.</li></ul>| 


### <a name="device-deployment"></a>Déploiement d’appareils

Une fois que vous avez décidé de créer et de gérer vos comptes de ressources Salles Microsoft Teams, créez votre plan pour expédier les appareils et leurs périphériques affectés à vos salles, puis passez à l’installation et à la configuration.


|  &nbsp;  |   &nbsp;  |
|-----------|------------|
| ![gérer le déploiement site par site.](../media/audio_conferencing_image7.png) <br/>Points de décision|<ul><li>Déterminez qui gérera le déploiement site par site.</li><li> Identifiez les ressources qui installeront Salles Microsoft Teams sur le site et effectuez la configuration et les tests.</li></ul>| 
| ![démarrer le test de l’appareil.](../media/audio_conferencing_image9.png)<br/>Étapes suivantes|<ul><li>Démarrez le test de l’appareil.</li></ul>| 

_Exemple de table de déploiement_

| **Site**  | **Nom de la salle** | **Type de salle** | **système Salles Microsoft Teams**  | **Périphériques**  | **Salles Microsoft Teams nom de l’ordinateur**  | **Salles Microsoft Teams compte de ressource**  |
|-----------|---------------|---------------|-----------------------------------|------------------|------------------------------------------|---------------------------------------------|
| Siège social de Londres | Curie         | Moyen        |                                   |                  |                                          |                                             |
| Siège social de Sydney | Hill          | Grande         |                                   |                  |                                          |                                             |

### <a name="microsoft-teams-rooms-application-and-peripheral-device-configuration"></a>Salles Microsoft Teams configuration de l’application et de l’appareil périphérique 

Une fois que chaque système Salles Microsoft Teams a été déployé physiquement et que les périphériques pris en charge sont connectés, vous devez configurer l’application Salles Microsoft Teams pour affecter le compte de ressource et le mot de passe Salles Microsoft Teams pour activer salles Teams  pour vous connecter à Microsoft Teams ou à Skype Entreprise, et Exchange.

Vous pouvez configurer manuellement chaque système Salles Microsoft Teams. Vous pouvez également utiliser un fichier de configuration XML stocké de manière centralisée, par salles Teams pour gérer les paramètres de l’application.

Pour plus d’informations sur l’utilisation du fichier de configuration XML, consultez [Gérer à distance les paramètres d’une console Salles Microsoft Teams avec un fichier de configuration XML](xml-config-file.md). 

Vous pouvez utiliser [PowerShell à distance](rooms-operations.md#remote-management-using-powershell) pour extraire la configuration Salles Microsoft Teams pour les besoins de création de rapports. 

| &nbsp;   |  &nbsp;   |
|-----------|------------|
| ![configuration du point de décision.](../media/audio_conferencing_image7.png) <br/>Points de décision|<ul><li>Déterminez si vous allez configurer manuellement chaque système Salles Microsoft Teams ou utiliser un fichier XML central (un par appareil Salles Microsoft Teams).</li></ul>| 
| ![étapes suivantes de l’approche à distance.](../media/audio_conferencing_image9.png)<br/>Étapes suivantes|<ul><li>Définissez votre approche de gestion à distance.</li></ul>| 

### <a name="testing"></a> Tests

Une fois que salles Teams a été déployé, vous devez le tester. Vérifiez que les fonctionnalités répertoriées dans [Salles Microsoft Teams aide](https://support.microsoft.com/en-us/office/microsoft-teams-rooms-help-e667f40e-5aab-40c1-bd68-611fe0002ba2?ui=en-us&rs=en-us&ad=us) fonctionnent sur l’appareil déployé. Nous recommandons vivement à l’équipe de déploiement de vérifier que Salles Microsoft Teams apparaît dans Teams centre d’administration. Il est également important d’effectuer un certain nombre d’appels de test et de réunions pour vérifier la qualité. Pour plus d’informations, consultez cette [liste de contrôle de déploiement utile](console.md#microsoft-teams-rooms-deployment-checklist).

Dans le cadre du déploiement général Teams ou Skype Entreprise, nous vous recommandons de configurer des fichiers de génération pour le tableau de bord de qualité des appels (CQD), de surveiller les tendances de qualité et de participer au processus de révision de la qualité de l’expérience. Pour plus d’informations, consultez [Améliorer et surveiller la qualité des appels pour Teams](../monitor-call-quality-qos.md). 

### <a name="asset-management"></a>Gestion des ressources

Dans le cadre du déploiement, vous devez mettre à jour votre registre de ressources avec le nom de la salle, le nom Salles Microsoft Teams, le compte de ressource Salles Microsoft Teams et les périphériques affectés. 

_Exemple de table des ressources_

| **Site**  | **Nom de la salle** | **Type de salle** | **Salles Microsoft Teams non série.**  | **Périphériques/ Nos séries./ Ports**  | **Salles Microsoft Teams nom de l’ordinateur**  | **compte de service Salles Microsoft Teams**  | **Date de déploiement** |
|-----------|---------------|---------------|------------------------------------------|------------------------------------------|------------------------------------------|--------------------------------------------|-------------------|
| Siège social de Londres | Curie         | Moyen        |                                          |                                          |                                          |                                            |                   |
| Siège social de Sydney | Hill          | Grande         |                                          |                                          |                                          |                                            |                   |
