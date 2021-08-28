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
description: Lisez cet article pour en savoir plus sur le déploiement Salles Microsoft Teams, y compris les phases de déploiement.
ms.openlocfilehash: 51a30137a2164651fe17f3910b17312fd6d45d6b
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58627166"
---
# <a name="deployment-overview"></a>Vue d’ensemble du déploiement

Le déploiement d Salles Microsoft Teams se décompose essentiellement en phases :

- Confirmation que vos emplacements de déploiement (salles) répondent aux dépendances de déploiement
- Création Microsoft Teams comptes Skype Entreprise et Exchange et leur attribution sur les appareils de la console (voir Configurer des comptes [Salles Microsoft Teams)](rooms-configure-accounts.md)
- Réimagie des tablettes Microsoft Surface pour les Salles Microsoft Teams consoles numériques (voir Configurer une console de Salles Microsoft Teams [ou](console.md) déployer Salles Microsoft Teams guide de [déploiement en masse)](rooms-scale.md)
- (Facultatif) Configuration de la suite Microsoft Operations Management suite pour vos systèmes (voir Déployer la gestion des Salles Microsoft Teams [avec le moniteur Azure](azure-monitor-deploy.md)
- Configuration de consoles dans les salles de réunion et connexion des périphériques dont vous avez besoin (voir la documentation OEM pour votre ensemble d’appareils)

Les techniciens av peuvent être utilisés pour la dernière tâche, mais le service informatique de votre organisation doit accomplir les autres parties du processus. 


## <a name="site-readiness"></a>État de préparation du site 

Pendant la livraison des appareils commandés à votre organisation, travaillez avec votre réseau, vos installations et vos équipes AV pour vous assurer que les dépendances de déploiement sont remplies et que chaque site et salle est prêt en termes de puissance, de mise en réseau et d’affichage. De plus, assurez-vous que les conditions d’installation physique sont respectées. Pour des raisons d’installation physique, rendez-vous sur le site du fournisseur et tirez parti de l’expérience de votre équipe AV lors de l’installation et de l’installation d’écrans et de l’exécution du cablage.

Pour plus d’informations sur ces dépendances, voir les liens d’aide à la planification ci-dessous :

-   [Vérification de la disponibilité du réseau](rooms-prep.md#check-network-availability)
-   [Certificats](rooms-prep.md#certificates)
-   [Proxy](rooms-prep.md#proxy)

**Pro conseil** : si vous avez l’intention d’utiliser des serveurs proxy pour fournir l’accès à Teams ou Skype Entreprise Online, examinez tout d’abord [cet article.](../proxy-servers-for-skype-for-business-online.md) En ce qui concerne le trafic Skype Entreprise serveur proxy, nous vous recommandons de contourner complètement les serveurs proxy. Skype Entreprise trafic est déjà chiffré, les serveurs proxy ne le rendent donc pas plus sécurisé. Dans le cadre de votre déploiement à plus grande échelle, nous vous recommandons de suivre les instructions de la guide Préparer votre réseau pour [Teams](../prepare-network.md) à des fin de planification de la bande passante et d’évaluation de l’adapter à votre réseau en cas de trafic en temps réel.

|  &nbsp;  | &nbsp;    |
|-----------|------------|
| ![confirmer les sites](../media/audio_conferencing_image7.png) <br/>Points de décision|<ul><li>Confirmez que vos sites répondent aux exigences essentielles pour Salles Microsoft Teams.</li><li>Confirmez que vous avez fourni suffisamment de bande passante pour chaque site.</li></ul>| 
| ![planifier le déploiement d’appareils](../media/audio_conferencing_image9.png)<br/>Étapes suivantes|<ul><li>Commencez à planifier le déploiement et la configuration de votre appareil.</li></ul>| 

## <a name="service-readiness"></a>Préparation du service

Pour préparer votre déploiement Salles Microsoft Teams, vous pouvez effectuer les tâches principales suivantes :

-   Définissez Salles Microsoft Teams fonctionnalités de compte de service.
-   Préparez un unité d’organisation et un groupe Active Directory pour conserver vos comptes de machine et de service Salles Microsoft Teams et éventuellement préparer les objets de stratégie de groupe pour activer la remotation PowerShell.

### <a name="define-microsoft-teams-rooms-service-account-features"></a>Définir Salles Microsoft Teams fonctionnalités de compte de service 

Selon les scénarios de collaboration que vous avez décidé d’activer avec votre déploiement Salles Microsoft Teams, vous devrez déterminer les fonctionnalités que vous affectez à chaque compte de service Salles Microsoft Teams que vous activez.

| **Scénario** | **Description** | **Salles Microsoft Teams fonctionnalité de compte de service** |
|---------- |------------- | --- |
| Réunions interactives            | utilisation de la voix, de la vidéo et du partage d’écran ; faire de l’Salles Microsoft Teams ressource bookable                     | Activé pour les Skype Entreprise, activé pour l’Exchange (boîte aux lettres de ressources) |
| Conférence rendez-vous            | Activer les réunions *démarrées directement à partir* de la console Salles Microsoft Teams avec les coordonnées de conférence rendez-vous | Activé pour l’audioconférence                                          |
| Appels PSTN sortants/entrants | Activer la console Salles Microsoft Teams pour effectuer et recevoir des appels PSTN                                         | Activé pour les Système téléphonique                                                |

Pour plus d’informations sur Salles Microsoft Teams comptes, voir Configurer [des comptes pour Salles Microsoft Teams.](rooms-configure-accounts.md)


|  &nbsp;  |  &nbsp;   |
|-----------|------------|
| ![prise en charge des scénarios](../media/audio_conferencing_image7.png) <br/>Points de décision|<ul><li>Déterminez les scénarios que vous prendrez en charge et identifiez les conditions de licence pour Salles Microsoft Teams comptes de service.</li></ul>| 
| ![préparer l’ordinateur hôte](../media/audio_conferencing_image9.png)<br/>Étapes suivantes|<ul><li>Préparez-vous à héberger des comptes d’ordinateurs et de services.</li></ul>| 


_Exemple de Salles Microsoft Teams table de planification d’un compte de service_

| **Site**  | **Nom de la salle** | **Type de salle** | **Capacités des salles à venir**                                                 | **Salles Microsoft Teams fonctionnalités de compte**                                                                                         |
|-----------|---------------|---------------|------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------|
| London HQ | Desso         | Moyen        | 1 écran, audio et vidéo plus présentation <br>Accès aux conférences téléphoniques<br> Accès PSTN  | Activé pour les Skype Entreprise, activé pour l’Exchange (boîte aux lettres de ressources) <br>Activé pour l’audioconférence <br>Activé pour les Système téléphonique |
| Sydney HQ | Hill          | Grande         | 2 écrans, audio et vidéo plus présentation<br>Accès aux conférences téléphoniques<br> Accès PSTN  | Activé pour les Skype Entreprise, activé pour l’Exchange (boîte aux lettres de ressources)<br> Activé pour l’audioconférence <br>Activé pour les Système téléphonique |


### <a name="prepare-to-host-microsoft-teams-rooms-machine-and-service-accounts-optional"></a>Préparer l’Salles Microsoft Teams comptes de machine et de service (facultatif)

Pour vous permettre de gérer vos comptes de machine et de service Salles Microsoft Teams et de les signaler, préparez votre annuaire Active Directory ou votre compte de Azure Active Directory (Azure AD). 

Définissez un groupe Active Directory ou Azure AD local pour ajouter tous les comptes de service Salles Microsoft Teams (utilisateurs), puis créez des rapports d’utilisation à l’aide de l’cmdlet PowerShell Get-CSUserSession dans votre déploiement Salles Microsoft Teams. Par exemple, créez un groupe nommé SkypeRoomSystemsv2-Service-Accounts. 


Définissez une unité d’organisation dans votre hiérarchie Active Directory ou Azure AD pour conserver tous les comptes d’ordinateur Salles Microsoft Teams (s’ils sont membres du domaine) et une unité organisationnelle pour conserver tous les comptes d’utilisateurs Salles Microsoft Teams. Si vous créez une unité d’organisation pour les comptes d’ordinateur Salles Microsoft Teams, désactivez l’héritage pour vous assurer que vous appliquez uniquement les stratégies que vous souhaitez appliquer aux utilisateurs dont le domaine est joint Salles Microsoft Teams. 

Créez un objet de stratégie de groupe affecté à l’unité de l’organisation qui Salles Microsoft Teams comptes informatiques. Utilisez-la pour : 

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

Chaque Salles Microsoft Teams nécessite un compte de ressource dédié et unique qui doit être activé pour les appareils Microsoft Teams,Skype Entreprise et Exchange. Ce compte doit avoir une boîte aux lettres de salle hébergée sur Exchange et être activé en tant que salle de réunion dans le déploiement Teams ou Skype Entreprise personnel. Sur le Exchange, le traitement du calendrier doit être configuré pour que l’appareil puisse accepter automatiquement les demandes de réunion entrantes. Pour plus d’informations sur la création de ces comptes, voir Configurer [des comptes pour Salles Microsoft Teams.](rooms-configure-accounts.md) 

**Pro conseil :** rendre les noms d’affichage de ces comptes descriptifs et faciles à comprendre. Voici les noms que les utilisateurs voient lors de la recherche et de l’ajout Salles Microsoft Teams systèmes à des réunions. Certaines organisations utilisent le nom de salle de *site* de la convention (Capacité maximale de salle )-RS, par exemple Domaine (salle de conférence de 12 personnes à Londres) qui peut avoir le nom complet - LON-X(12)-RS. 

|  &nbsp;  | &nbsp;    |
|-----------|------------|
| ![Décider d’une convention d’attribution de noms](../media/audio_conferencing_image7.png) <br/>Points de décision|<ul><li>Décidez de la convention d’Salles Microsoft Teams comptes.</li><li>Décidez si vous devez créer des comptes individuels ou utiliser des scripts d’approvisionnement en bloc.</li></ul>| 
| ![étapes suivantes](../media/audio_conferencing_image9.png)<br/>Étapes suivantes|<ul><li>Commencez à planifier le déploiement de votre appareil.</li></ul>| 


### <a name="device-software-installation"></a>Installation de logiciels d’appareil 

Lorsque vous planifiez le déploiement Salles Microsoft Teams, vous pouvez envisager d’installer les logiciels requis. Les scénarios et approches courants sont décrits dans le tableau suivant. 

| **Scénario**            | **Approche**         |
|-------------------------|-----------------------|   
|Déploiement de quelques appareils Salles Microsoft Teams (<10). | Si vous utilisez Surface Pro de données Salles Microsoft Teams, suivez les [instructions d’installation](console.md)pour une installation par appareil. [Cette vidéo pratique vous guide tout au long du processus.](https://content.cloudguides.com/guides/Configure%20the%20Skype%20Room%20Systems%20console) Si vous utilisez une solution intégrée, déployez le déploiement à l’aide de l’image du fournisseur et configurez les paramètres selon les besoins. |
| Déploiement de 10 à 50 appareils à partir d’un fournisseur unique.     | Créez une image basée sur WIM, marquez une pause après l’étape [6](console.md)dans les conseils et capturez une image de distribution à utiliser avec votre technologie de distribution de clonement.    |
| Déploiement de plus de 50 Salles Microsoft Teams, déploiement d’appareils de plusieurs fournisseurs ou resserrement d’agents spécifiques de l’organisation dans le cadre du déploiement. | Utilisez une plateforme de distribution et de build de logiciels basée sur un séquenceur de tâches, telle que [Microsoft Endpoint Configuration Manager.](rooms-scale.md)  |


**Pro conseil** : chaque Salles Microsoft Teams doit avoir un nom d’ordinateur valide et unique sur votre réseau. De nombreux systèmes de surveillance et d’alerte affichent le nom de l’ordinateur en tant qu’identificateur clé. Il est donc important de développer une convention d’affectation de noms pour les déploiements Salles Microsoft Teams qui permet au personnel de support de localiser facilement l’Salles Microsoft Teams pour qui une action a été signalée. Par exemple, vous pouvez utiliser un modèle MTR-*Nom* de la salle de -  site (MTR-LON-S). 

Dans le cadre du déploiement, vous devez également envisager votre stratégie de gestion et de configuration des comptes [locaux créés](/skypeforbusiness/plan-your-deployment/clients-and-devices/skype-room-systems-v2-0#local-accounts) par le programme d’installation Salles Microsoft Teams’application installer.

Nous fournissons des instructions sur l’utilisation du moniteur [Microsoft Azure](/skypeforbusiness/plan-your-deployment/clients-and-devices/azure-monitor) pour surveiller le déploiement d’Salles Microsoft Teams et signaler les erreurs de disponibilité, les erreurs matérielles/logicielles et la version Salles Microsoft Teams’application. Si vous décidez d’utiliser la suite Microsoft Operations Management, vous devez installer l’agent de la suite Operations Management suite dans le cadre du processus d’installation du logiciel et configurer les informations de connexion à l’espace de travail de votre espace de travail. 

Vous de même déterminer si l’Salles Microsoft Teams sera joint au domaine. Des informations sur les avantages de l’adhésion à un domaine sont disponibles dans les Skype domaines [de Room System qui rejoignent la réunion.](domain-joining-considerations.md) 

| &nbsp;   |  &nbsp;   |
|-----------|------------|
| ![Attribution d’un nom de périphérique à des points de décision](../media/audio_conferencing_image7.png) <br/>Points de décision|<ul><li>Décidez Salles Microsoft Teams convention d’affectation de noms d’appareils à utiliser lors de votre déploiement.</li><li>Décidez si vous devez rejoindre Salles Microsoft Teams votre domaine et comment gérer et configurer les comptes locaux. </li><li>Décidez si vous allez utiliser la suite Gestion des opérations pour surveiller le Salles Microsoft Teams déploiement.</li><li>Déterminez la méthode que vous utiliserez pour déployer le logiciel et les agents sur le Salles Microsoft Teams en vue du déploiement de l’appareil. </li></ul>| 
| ![Étapes suivantes pour planifier un appareil](../media/audio_conferencing_image9.png)<br/>Étapes suivantes|<ul><li>Commencez à planifier l’approche de déploiement de votre appareil.</li></ul>| 


### <a name="device-deployment"></a>Déploiement d’appareils

Après avoir déployé votre logiciel sur les unités de Salles Microsoft Teams, créez votre plan pour expédier les appareils et les périphériques affectés à vos salles, puis procédez à l’installation et à la configuration. 


|  &nbsp;  |   &nbsp;  |
|-----------|------------|
| ![gérer le déploiement site par site](../media/audio_conferencing_image7.png) <br/>Points de décision|<ul><li>Décidez qui gérera le déploiement site par site.</li><li> Identifiez les ressources qui seront en mesure d’installer les Salles Microsoft Teams sur site et entreprenons la configuration et le test.</li></ul>| 
| ![Démarrer le test de l’appareil](../media/audio_conferencing_image9.png)<br/>Étapes suivantes|<ul><li>Démarrez le test de l’appareil.</li></ul>| 

_Exemple de tableau de déploiement_

| **Site**  | **Nom de la salle** | **Type de salle** | **Salles Microsoft Teams système informatique**  | **Périphériques**  | **Salles Microsoft Teams nom de l’ordinateur**  | **Salles Microsoft Teams de ressources**  |
|-----------|---------------|---------------|-----------------------------------|------------------|------------------------------------------|---------------------------------------------|
| London HQ | Sy         | Moyen        |                                   |                  |                                          |                                             |
| Sydney HQ | Hill          | Grande         |                                   |                  |                                          |                                             |

### <a name="microsoft-teams-rooms-application-and-peripheral-device-configuration"></a>Salles Microsoft Teams configuration des applications et périphériques 

Une fois que chaque système Salles Microsoft Teams a été déployé physiquement et que les périphériques pris en charge se sont connectés, vous devez configurer l’application Salles Microsoft Teams pour affecter le compte de ressource et le mot de passe Salles Microsoft Teams créés précédemment, pour permettre au système Salles Microsoft Teams de se connecter à Microsoft Teams ou Skype Entreprise et Exchange. Il est important de tirer parti des périphériques audio et vidéo USB certifiés liés ailleurs dans le document. Ne pas le faire peut entraîner un comportement imprévisible. 

Vous pouvez configurer manuellement chaque Salles Microsoft Teams système informatique. Vous pouvez également utiliser un fichier de configuration XML stocké de façon centralisée et par-Salles Microsoft Teams pour gérer les paramètres des applications et tirer parti d’un script DPO de démarrage pour réappliquer la configuration de votre choix, chaque fois que le système Salles Microsoft Teams démarre. 

Pour plus d’informations sur l’utilisation du fichier de configuration XML, voir Gérer un fichier de configuration XML pour gérer Salles Microsoft Teams à distance avec un [fichier de configuration XML.](xml-config-file.md) 

Vous pouvez utiliser [PowerShell à distance pour](rooms-operations.md#remote-management-using-powershell) tirer le Salles Microsoft Teams aux besoins en matière de rapport. 

| &nbsp;   |  &nbsp;   |
|-----------|------------|
| ![configuration du point de décision](../media/audio_conferencing_image7.png) <br/>Points de décision|<ul><li>Décidez si vous devez configurer manuellement chaque Salles Microsoft Teams système informatique ou utiliser un fichier XML central (un par Salles Microsoft Teams appareil).</li></ul>| 
| ![Approche à distance des étapes suivantes](../media/audio_conferencing_image9.png)<br/>Étapes suivantes|<ul><li>Définissez votre approche de la gestion à distance.</li></ul>| 

### <a name="testing"></a> Tests

Une fois que Salles Microsoft Teams système d’exploitation a été déployé, vous devez le tester. Vérifiez que les fonctionnalités répertoriées dans [Salles Microsoft Teams’aide](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) fonctionnent sur l’appareil déployé. Nous recommandons vivement à l’équipe de déploiement de vérifier que Salles Microsoft Teams l’équipe se connecte à la suite Microsoft Operations Management Suite (le caser). Il est également important de tester la qualité des appels et des réunions. Pour plus d’informations, consultez cette [liste de contrôle utile pour le déploiement.](console.md#microsoft-teams-rooms-deployment-checklist)

Dans le cadre du déploiement général de la Teams ou de la Skype Entreprise, nous vous recommandons de configurer la création de fichiers pour le tableau de bord de qualité des appels, de surveiller les tendances en matière de qualité et de vous impliquer dans le processus de révision de la qualité de l’expérience. Pour plus d’informations, voir [Améliorer et surveiller la qualité des appels pour Teams.](../monitor-call-quality-qos.md) 

### <a name="asset-management"></a>Gestion des biens

Dans le cadre du déploiement, vous pouvez mettre à jour votre registre de biens avec le nom de la salle, le nom de l’appareil Salles Microsoft Teams, le compte de ressource connecté à Salles Microsoft Teams et les périphériques périphériques affectés (et les ports USB qu’ils utilisent). 

_Exemple de table des biens_

| **Site**  | **Nom de la salle** | **Type de salle** | **Salles Microsoft Teams non en série.**  | **Périphériques/ Numéros de série./ Ports**  | **Salles Microsoft Teams nom de l’ordinateur**  | **Salles Microsoft Teams service client**  | **Date de déploiement** |
|-----------|---------------|---------------|------------------------------------------|------------------------------------------|------------------------------------------|--------------------------------------------|-------------------|
| London HQ | Sy         | Moyen        |                                          |                                          |                                          |                                            |                   |
| Sydney HQ | Hill          | Grande         |                                          |                                          |                                          |                                            |                   |