---
title: Déploiement de salles de Microsoft teams
ms.author: v-lanac
author: lanachin
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
ms.custom: ''
ms.assetid: 678689e4-d547-499b-be64-7d8f16dd8668
description: Lisez cet article pour en savoir plus sur le déploiement de salles de Microsoft Teams.
ms.openlocfilehash: 650302d6d952a59c1cc460e2cdf8758cfb0fcd41
ms.sourcegitcommit: 2511cd95a186d95f4571afa4212f8e0fc207817d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/08/2020
ms.locfileid: "41863345"
---
# <a name="deployment-overview"></a>Vue d’ensemble du déploiement

Le déploiement de Microsoft teams salles s’arrête essentiellement par phases :

- Confirmation que vos emplacements de déploiement (salles) répondent aux dépendances de déploiement
- Créer des comptes Microsoft teams ou Skype entreprise et les affecter aux périphériques de la console (voir [configurer des comptes pour les salles de Microsoft teams](rooms-configure-accounts.md))
- Recréation d’images de Microsoft surface Tablet pour fonctionner en tant que consoles de salle Microsoft Teams (voir [configurer une console de salle Microsoft](console.md) teams ou [déployer le Guide de déploiement de Microsoft teams](rooms-scale.md))
- Facultatif Configuration de la suite Microsoft Operations Management pour vos systèmes (reportez-vous à la rubrique déploiement de la [gestion des salles Microsoft teams avec Azure Monitor](azure-monitor-deploy.md)
- Configuration de consoles dans les salles de réunion et connexion des périphériques nécessaires (voir la documentation OEM de votre ensemble d’appareils)

Les technologies AUDIOVISUELles peuvent être utilisées pour la dernière tâche, mais le service informatique de votre organisation devra effectuer les autres parties du processus. 


## <a name="site-readiness"></a>Disponibilité du site 

Lorsque les périphériques commandés sont remis à votre organisation, collaborez avec votre réseau et vos installations AV pour vous assurer que les dépendances de déploiement sont satisfaites et que chaque site et salle est prêt en termes d’alimentation, de réseau et d’affichage. Par ailleurs, assurez-vous que la configuration requise pour l’installation physique est satisfaite. Pour plus d’informations sur l’installation physique, consultez le site du fournisseur et profitez de l’utilisation de votre équipe AV lors de l’installation et du montage d’écrans et de l’utilisation de câbles.

Vous pouvez en savoir plus sur ces dépendances dans les liens d’instructions de planification ci-dessous :

-   [Vérification de la disponibilité du réseau](rooms-prep.md#check-network-availability)
-   [Certificats](rooms-prep.md#certificates)
-   [Proxy](rooms-prep.md#proxy)

**Conseil professionnel** : Si vous envisagez d’utiliser des serveurs proxy pour donner accès à teams ou à Skype entreprise Online, vous devez commencer par [consulter cet article](../proxy-servers-for-skype-for-business-online.md). Notez que lorsqu’il s’agit du trafic de Skype entreprise sur les serveurs proxy, nous vous recommandons de contourner entièrement les serveurs proxy. Le trafic Skype entreprise est déjà crypté, de sorte que les serveurs proxy ne le rendent pas plus sûr. Dans le cadre de votre déploiement plus large, nous vous conseillons de suivre les recommandations de la rubrique [préparer votre réseau pour les équipes](../prepare-network.md) pour la planification de la bande passante et évaluer la pertinence de votre réseau pour le trafic en temps réel.

|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>Points de décision|<ul><li>Confirmez que vos sites répondent à la configuration requise pour les salles Microsoft Teams.</li><li>Vérifiez que vous avez fourni suffisamment de bande passante pour chaque site.</li></ul>| 
| ![](../media/audio_conferencing_image9.png)<br/>Étapes suivantes|<ul><li>Commencez à planifier le déploiement et la configuration de votre appareil.</li></ul>| 

## <a name="service-readiness"></a>Préparation du service

Pour préparer le déploiement de Microsoft Teams, effectuez les tâches centrales suivantes :

-   Définissez les fonctionnalités de compte de service de Microsoft teams services.
-   Préparez une unité d’organisation et un groupe Active Directory pour contenir les comptes d’ordinateur et de service de Microsoft Teams, et, éventuellement, préparer des objets de stratégie de groupe pour activer l’accès distant PowerShell.

### <a name="define-microsoft-teams-rooms-service-account-features"></a>Définir les fonctionnalités de compte de service de Microsoft teams 

En fonction des scénarios de collaboration que vous avez décidé d’activer avec le déploiement de Microsoft Teams, vous devez déterminer les fonctionnalités et fonctionnalités que vous attribuez à chaque compte de service Microsoft Teams, que vous activez.

| **Scénario** | **Description** | **Fonctionnalité de compte de service de Microsoft teams** |
|---------- |------------- | --- |
| Réunions interactives            | Utilisation de la voix, de la vidéo et du partage d’écran ; création de la ressource bookable de Microsoft teams                     | Activé pour Skype entreprise, activé pour Exchange (boîte aux lettres de ressources) |
| Conférence rendez-vous            | Activer les réunions démarrées *directement* à partir de la console des salles de Microsoft teams avec les coordonnées de conférence rendez-vous | Activé pour les conférences audio                                          |
| Appel RTC entrant/sortant | Activer la console de salles de Microsoft teams pour passer et recevoir des appels RTC                                         | Activé pour le système téléphonique                                                |

Pour plus d’informations sur les comptes de Microsoft Teams, voir [configurer des comptes pour les salles Microsoft teams](rooms-configure-accounts.md).


|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>Points de décision|<ul><li>Déterminez les scénarios pris en charge et identifiez les exigences en matière de licences pour les comptes de service de Microsoft Teams.</li></ul>| 
| ![](../media/audio_conferencing_image9.png)<br/>Étapes suivantes|<ul><li>Préparez-vous à héberger les comptes d’ordinateur et de service.</li></ul>| 


_Exemple de tableau de planification de compte de service de Microsoft teams_

| **Site**  | **Nom de la salle** | **Type de salle** | **Nouvelles fonctionnalités de salle**                                                 | **Fonctionnalités de compte Microsoft teams**                                                                                         |
|-----------|---------------|---------------|------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------|
| HQ de Londres | Curie         | Moyen        | 1 écran, audio et vidéo plus présentation <br>Accès à une conférence rendez-vous<br> Accès RTC  | Activé pour Skype entreprise, activé pour Exchange (boîte aux lettres de ressources) <br>Activé pour les conférences audio <br>Activé pour le système téléphonique |
| HQ de Sydney | Hill          | Grande         | 2 écrans, audio et vidéo et présentation<br>Accès à une conférence rendez-vous<br> Accès RTC  | Activé pour Skype entreprise, activé pour Exchange (boîte aux lettres de ressources)<br> Activé pour les conférences audio <br>Activé pour le système téléphonique |


### <a name="prepare-to-host-microsoft-teams-rooms-machine-and-service-accounts-optional"></a>Préparez-vous à l’hébergement des comptes d’ordinateur et de service de Microsoft Teams (facultatif)

Pour vous permettre de gérer et de créer des rapports sur les comptes d’ordinateur et de service de Microsoft Teams, préparez votre Active Directory local ou Azure Active Directory (Azure AD). 

Définissez une communauté locale Active Directory ou Azure AD pour ajouter tous les comptes de service de Microsoft Teams (utilisateur), puis créez des rapports d’utilisation à l’aide de l’applet de commande PowerShell Get-CSUserSession sur votre déploiement de Microsoft Teams. Par exemple, créez un groupe intitulé SkypeRoomSystemsv2-Service-Accounts. 


Définissez une unité d’organisation dans votre hiérarchie locale Active Directory ou Azure AD pour contenir tous les comptes d’ordinateur de Microsoft Teams (s’ils sont joints au domaine) et une unité d’organisation pour contenir tous les comptes d’utilisateurs de Microsoft Teams. Si vous créez une unité d’organisation pour les comptes d’ordinateur de Microsoft Teams, envisagez de désactiver l’héritage de façon à ce que vous appliquiez uniquement les stratégies que vous souhaitez appliquer à l’équipe Microsoft teams dans le domaine. 

Création d’un objet de stratégie de groupe affecté à l’unité d’organisation qui contient les comptes d’ordinateur de votre équipe Microsoft teams ; Utilisez cette opération pour : 

-   [Définissez les paramètres de compte d’alimentation et de local](rooms-operations.md#configuring-group-policy-for-microsoft-teams-rooms).
-   Activez Windows Update.
-   Activez l’accès distant PowerShell. Vous pouvez configurer un script de démarrage de manière à exécuter un script simple : Enable-PSRemoting-force

Vous pouvez utiliser PowerShell pour effectuer un certain nombre d’activités de gestion à distance, y compris la création et la définition d’informations de configuration. L’accès distant PowerShell doit être activé *avant qu'* une gestion PowerShell à distance puisse avoir lieu et qu’il soit considéré comme faisant partie de vos processus de déploiement ou configurés via une stratégie de groupe. Pour plus d’informations sur ces fonctionnalités et leur activation, voir [maintenance et opérations](rooms-operations.md#remote-management-using-powershell). 


## <a name="configuration-and-deployment"></a>Configuration et déploiement 

La planification de la configuration et du déploiement englobe les principales zones suivantes :

-   Attribution de compte
-   Installation de logiciels de périphériques
-   Déploiement d’appareil
-   Configuration de l’application et de l’appareil périphériques de Microsoft teams
-    Tests
-   Gestion des ressources

### <a name="account-provisioning"></a>Attribution de compte 

Chaque appareil de salle Microsoft teams nécessite un compte de ressources dédié et unique qui doit être activé pour Microsoft teams ou Skype entreprise et Exchange. Ce compte doit avoir une boîte aux lettres de salle hébergée sur Exchange et être activé comme salle de réunion dans le déploiement teams ou Skype entreprise. Dans le cas d’Exchange, le traitement du calendrier doit être configuré de manière à ce que l’appareil puisse automatiquement accepter les demandes de réunion entrantes. Pour plus d’informations sur la création de comptes, reportez-vous à [configurer des comptes pour les salles Microsoft teams](rooms-configure-accounts.md). 

**Conseil Pro** : rendez les noms d’affichage de ces comptes descriptifs et faciles à comprendre. Il s’agit des noms que les utilisateurs verront lors de la recherche et de l’ajout de systèmes de salle Microsoft teams à des réunions. Certaines organisations utilisent le*nom*de la salle de *site*-(*capacité maximale*de la salle)-RS, par exemple Curie, une salle de conférence de 12 personnes à Londres, peut présenter le nom d’affichage lon-Curie (12)-RS. 

|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>Points de décision|<ul><li>Déterminez la Convention d’affectation de noms pour les comptes de vos salles Microsoft Teams.</li><li>Décidez si vous voulez créer des comptes individuels ou utiliser des scripts de provisionnement en bloc.</li></ul>| 
| ![](../media/audio_conferencing_image9.png)<br/>Étapes suivantes|<ul><li>Commencez à planifier le déploiement de votre appareil.</li></ul>| 


### <a name="device-software-installation"></a>Installation de logiciels de périphériques 

Lors de la planification du déploiement des salles de Microsoft Teams, vous avez le choix entre plusieurs options pour installer les logiciels requis. Le tableau suivant décrit les scénarios et approches courants. 

| **Scénario**            | **Accessible**         |
|-------------------------|-----------------------|   
|Déploiement d’un petit nombre d’appareils de salle Microsoft Teams (<10). | Si vous utilisez des salles de Microsoft teams sous la forme de surface Pro, suivez les [instructions d’installation d’une installation par appareil](console.md). [Cette vidéo pratique vous guide tout au long du processus.](https://content.cloudguides.com/guides/Configure%20the%20Skype%20Room%20Systems%20console) Si vous utilisez une solution intégrée, déployez en utilisant l’image du fournisseur et configurez les paramètres selon les besoins. |
| Déploiement entre 10 et 50 appareils à partir d’un seul fournisseur.     | Créez une image WIM, interrompez votre travail après [l’étape 6 dans les instructions](console.md), puis capturez une image de distribution à utiliser avec votre technologie de distribution de clonage.    |
| Déploiement de plus de 50 équipements de salles de Microsoft Teams, déploiement de périphériques auprès de plusieurs fournisseurs ou demandant des agents spécifiques à une organisation dans le cadre du déploiement. | Utilisez une plateforme de build et de distribution de logiciels basée sur une séquence de tâches, telle que [Microsoft Endpoint Configuration Manager](rooms-scale.md).  |


**Conseil professionnel** -chaque salle de Microsoft teams doit avoir un nom de machine valide et unique sur votre réseau. De nombreux systèmes de surveillance et d’alerte indiquent le nom de l’ordinateur comme identificateur de clé, il est donc important de mettre en place une convention d’affectation de noms pour les déploiements Microsoft teams comme nécessitant une action. Par exemple, il se peut que vous utilisiez un modèle de MTR-nom de la*salle* de*site*-(MTR-lon-Curie). 

Dans le cadre du déploiement, vous devez également prendre en considération votre stratégie de gestion et de configuration des [comptes locaux](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/skype-room-systems-v2-0#local-accounts) créés par le programme d’installation de l’application Microsoft Teams.

Nous fournissons des conseils sur l’utilisation de [Microsoft Azure Monitor](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/azure-monitor) pour contrôler le déploiement de Microsoft Teams, ainsi que le rapport sur la disponibilité, les erreurs matérielles/logicielles et la version de l’application Microsoft Teams. Si vous décidez d’utiliser Microsoft Operations Management suite, vous devez installer l’agent de la suite Operations Management dans le cadre du processus d’installation du logiciel et configurer les informations de connexion à l’espace de travail de votre espace de travail. 

Il est également possible de faire en sorte que les salles de Microsoft teams soient jointes au domaine. Pour plus d’informations sur les avantages de la participation au domaine, voir [considérations relatives aux domaines du système de salle Skype](domain-joining-considerations.md). 

|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>Points de décision|<ul><li>Déterminez la Convention d’affectation de noms de Microsoft teams sur les appareils à utiliser pendant votre déploiement.</li><li>Décidez si vous allez joindre des appareils Microsoft teams à votre domaine et comment gérer et configurer des comptes locaux. </li><li>Décidez si vous allez utiliser la suite gestion des opérations pour surveiller le déploiement de Microsoft Teams.</li><li>Déterminez la méthode à utiliser pour déployer le logiciel et les agents sur le système de Microsoft Teams, en préparation du déploiement de l’appareil. </li></ul>| 
| ![](../media/audio_conferencing_image9.png)<br/>Étapes suivantes|<ul><li>Commencez à planifier l’approche de déploiement de votre appareil.</li></ul>| 


### <a name="device-deployment"></a>Déploiement d’appareil

Après avoir déployé votre logiciel sur les unités de salles de Microsoft Teams, créez votre plan pour expédier les appareils et les périphériques qui leur sont attribués dans vos salles, puis procédez à l’installation et à la configuration. 


|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>Points de décision|<ul><li>Déterminez qui va gérer le déploiement d’un site par site.</li><li> Identifiez les ressources qui installent les appareils de salle de Microsoft teams sur le site et qui effectuent les opérations de configuration et de test.</li></ul>| 
| ![](../media/audio_conferencing_image9.png)<br/>Étapes suivantes|<ul><li>Démarrez les tests d’appareil.</li></ul>| 

_Exemple de tableau de déploiement_

| **Site**  | **Nom de la salle** | **Type de salle** | **Système de salle Microsoft teams**  | **Appareils périphériques**  | **Nom de l’ordinateur Microsoft teams**  | **Compte de ressources de Microsoft teams**  |
|-----------|---------------|---------------|-----------------------------------|------------------|------------------------------------------|---------------------------------------------|
| HQ de Londres | Curie         | Moyen        |                                   |                  |                                          |                                             |
| HQ de Sydney | Hill          | Grande         |                                   |                  |                                          |                                             |

### <a name="microsoft-teams-rooms-application-and-peripheral-device-configuration"></a>Configuration de l’application et de l’appareil périphériques de Microsoft teams 

Après le déploiement physique de chaque système de salle Microsoft teams et les périphériques pris en charge connectés, vous devez configurer l’application Microsoft teams pièces pour affecter le compte de ressources de Microsoft teams et le mot de passe créés précédemment. pour permettre au système de Microsoft teams de se connecter à Microsoft teams ou à Skype entreprise et Exchange. Il est essentiel de tirer parti des périphériques audio et vidéo USB certifiés liés à un autre emplacement dans le document. Ce n’est pas le cas, cela peut entraîner un comportement imprévisible. 

Vous pouvez configurer manuellement chaque système de salle Microsoft Teams. Par ailleurs, vous pouvez utiliser un fichier de configuration XML au format central de Microsoft teams pour gérer les paramètres de l’application et utiliser un script d’objet de stratégie de groupe pour réappliquer la configuration de votre choix, chaque fois que le système de Microsoft Teams. 

Pour plus d’informations sur l’utilisation du fichier de configuration XML, voir [gérer les paramètres de la console de Microsoft teams à distance à l’aide d’un fichier de configuration XML](xml-config-file.md). 

Vous pouvez utiliser [Remote PowerShell](rooms-operations.md#remote-management-using-powershell) pour extraire la configuration des salles de Microsoft teams pour la création de rapports. 

|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>Points de décision|<ul><li>Décidez si vous allez configurer manuellement chaque système de salle Microsoft teams ou utiliser un fichier XML central (un par périphérique Microsoft Teams).</li></ul>| 
| ![](../media/audio_conferencing_image9.png)<br/>Étapes suivantes|<ul><li>Définissez votre approche de gestion à distance.</li></ul>| 

### <a name="testing"></a> Tests

Une fois le système de salle Microsoft teams déployé, vous devez le tester. Vérifiez que les fonctionnalités répertoriées dans l' [aide de Microsoft teams](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) pour travailler sur l’appareil déployé. Nous recommandons fortement aux équipes de déploiement de vérifier que Microsoft teams se connecte à la suite Microsoft Operations Management (si utilisée). Il est également important de passer des appels et des réunions de test pour vérifier la qualité. Pour plus d’informations, consultez cette [liste de vérification de déploiement utile](console.md#microsoft-teams-rooms-deployment-checklist).

Nous vous recommandons de configurer les fichiers de construction pour le tableau de bord de qualité des appels dans le cadre d’équipes générales ou du lancement de Skype entreprise, ainsi que le processus de vérification de la qualité de l’expertise. Pour plus d’informations, reportez-vous au [Guide de vérification de la qualité de l’utilisation](https://aka.ms/qerguide). 

### <a name="asset-management"></a>Gestion des ressources

Dans le cadre du déploiement, vous pouvez mettre à jour votre registre de biens à l’aide du nom de la salle, du nom de l’appareil de Microsoft Teams, du compte de ressources connecté à Microsoft Teams, et des périphériques périphériques (et des ports USB qu’il utilise). 

_Exemple de table de biens_

| **Site**  | **Nom de la salle** | **Type de salle** | **Le numéro de série de l’équipe Microsoft teams**  | **Périphériques/numéros de série/ports**  | **Nom de l’ordinateur Microsoft teams**  | **Compte de service de Microsoft teams**  | **Date de déploiement** |
|-----------|---------------|---------------|------------------------------------------|------------------------------------------|------------------------------------------|--------------------------------------------|-------------------|
| HQ de Londres | Curie         | Moyen        |                                          |                                          |                                          |                                            |                   |
| HQ de Sydney | Hill          | Grande         |                                          |                                          |                                          |                                            |                   |


