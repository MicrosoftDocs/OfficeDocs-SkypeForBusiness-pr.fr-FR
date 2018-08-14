---
title: Déploiement de Skype Room System v2
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 678689e4-d547-499b-be64-7d8f16dd8668
description: Lisez cet article pour en savoir plus sur le déploiement de systèmes de salle Skype v2.
ms.openlocfilehash: 08d7444eea06eae3de2970b368eb1201828c8a07
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "21019455"
---
# <a name="deployment-overview"></a>Vue d’ensemble du déploiement

Déploiement de systèmes de salle Skype v2 essentiellement divise en phases :

- Vous demandant de confirmer que les emplacements de déploiement (salles) satisfont les dépendances de déploiement
- Création de Skype pour les comptes d’entreprise et Exchange et en leur attribuant sur les périphériques de la console (voir [configurer les comptes pour les systèmes de salle Skype v2](room-systems-v2-configure-accounts.md))
- Créer de nouvelles images Microsoft Surface tablettes pour fonctionner en tant que consoles v2 de systèmes de salle Skype (voir [configurer une console v2 de systèmes de salle Skype](console.md) ou [guide de déploiement en masse déployer Skype salle systèmes v2](room-systems-scale.md))
- (Facultatif) Configuration de Microsoft Operations Management Suite pour vos systèmes (voir [gestion v2 de déploiement de systèmes de salle Skype avec OMS](with-oms.md))
- Configuration de consoles dans les salles de réunion et connexion des périphériques vous devez (voir la documentation du fabricant de votre jeu de périphériques)

Techniciens AV peuvent être utilisées pour la dernière tâche, mais que votre organisation informatique doit être effectuée les autres parties du processus. 


## <a name="site-readiness"></a>Préparation du site 

Alors que les périphériques commandés sont remis à votre organisation, travailler avec votre mise en réseau et les installations et les équipes d’a/v pour vous assurer que les dépendances de déploiement sont remplies et chaque site et la salle sont prêt en termes d’alimentation, réseau et les afficher. En outre, assurez-vous que les conditions d’installation physique sont remplies. Pour des considérations relatives à l’installation physique, visitez le site du fournisseur et tirer parti de l’expérience de votre équipe AV lors de l’installation et écrans de montage et câblage en cours d’exécution.

Vous pouvez trouver plus d’informations sur ces dépendances dans les liens du Guide de planification ci-dessous :

-   [Vérification de la disponibilité du réseau](../../plan-your-deployment/clients-and-devices/srs-v2-prep.md#check-network-availability) 
-   [Certificats](../../plan-your-deployment/clients-and-devices/srs-v2-prep.md#certificates)
-   [Proxy](../../plan-your-deployment/clients-and-devices/srs-v2-prep.md#proxy)

**Conseil pro** - si vous envisagez d’utiliser des serveurs proxy pour fournir l’accès à Skype pour Business en ligne, d’abord [Lisez cet article](https://docs.microsoft.com/skypeforbusiness/optimizing-your-network/proxy-servers-for-skype-for-business-online). Notez que lorsqu’il s’agit Skype pour le trafic métiers via des serveurs proxy, nous vous recommandons d’ignorer complètement les serveurs proxy. Skype pour le trafic d’entreprise est déjà chiffré, les serveurs proxy ne pas rendre plus sécurisé. Dans le cadre de votre plus large Skype pour le déploiement d’entreprise, nous vous conseillons de suivre les instructions de [évaluer mon environnement](https://docs.microsoft.com/MicrosoftTeams/3-envision-evaluate-my-environment#network-readiness) pour la bande passante de planification et d’évaluation de pertinence de votre réseau pour le trafic en temps réel. Pour toute la bande passante planification, utilisez le [Planificateur de réseau MyAdvisor](https://myadvisor.fasttrack.microsoft.com/CloudVoice/NetworkPlanner). (Nous vous conseillons de créer un personnage v2 de systèmes de salle Skype pour refléter l’utilisation v2 Skype salle systèmes prévue [vidéo, partage d’écran, audio] et affecter un nombre d’utilisateurs qui correspond au nombre d’unités de systèmes de salle Skype pour être déployés sur chaque site.) 

|    |     |
|-----------|------------|
| ![](../../media/audio_conferencing_image7.png) <br/>Points de décision|<ul><li>Vérifiez que vos sites remplissent les conditions clées pour les systèmes de salle Skype v2.</li><li>Vérifiez que vous avez fourni suffisamment de bande passante pour chaque site.</li></ul>| 
| ![](../../media/audio_conferencing_image9.png)<br/>Étapes suivantes|<ul><li>Commencer à planifier votre déploiement des périphériques et la configuration.</li></ul>| 

**Professionnels de l’info-bulle-** À partir d’un point de vue de planification de site par site, vous pourriez trouver utiles les ressources suivantes. Ils traitent plus que Skype salle systèmes v2 et peuvent être utilisées dans un déploiement complet de Skype pour Business Online :

-   [Déploiement de site/remise Guide de planification de Migration](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_24)

-   [Site de déploiement et de planification de la Migration - lecture](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_16)

    > [!NOTE]
    > Dans la lecture, effectuez les tâches dans la section « 4,3 – > salles de conférence » dans la feuille « 4-points de terminaison » pour chaque site où vous projetez de déployer des systèmes de salle Skype v2 périphériques. Cela vous permettra d’utiliser le compte en bloc script plus loin dans le processus de mise en service. 

## <a name="service-readiness"></a>Préparation du service

Pour préparer votre déploiement de systèmes de salle Skype, effectuez la clé suivante, les tâches centrale :

-   Définir les fonctionnalités de compte de service de systèmes de salle Skype.
-   Préparer une unité d’organisation et un groupe Active Directory pour maintenir votre ordinateur Skype salle systèmes et de comptes, de service et, éventuellement, préparer des objets de stratégie de groupe (GPO) pour activer l’accès à distance PowerShell.

### <a name="define-skype-room-systems-service-account-features"></a>Définir les fonctionnalités de compte de service de systèmes de salle de Skype 

Selon les scénarios de collaboration que vous avez décidé d’activer avec votre déploiement de v2 Skype salle systèmes, vous devez déterminer les fonctionnalités que vous assignez à chaque compte de service v2 Skype salle systèmes qui vous permettent.

| **Scénario** | **Description** | **Fonctionnalité de compte de service Skype salle systèmes v2** |
|---------- |------------- | --- |
| Réunions interactives            | À l’aide de la voix, vidéo et partage d’écran ; émission d’une ressource bookable le v2 de systèmes de salle de Skype                     | Activé pour Skype pour les entreprises, activé pour Exchange (boîtes aux lettres de ressources) |
| Conférence rendez-vous            | Activer le démarrage de réunions *directement* depuis la console de v2 de systèmes de salle Skype avec les coordonnées de conférence rendez-vous | Activé pour l’audioconférence                                          |
| Entrante/sortante l’appel PSTN | Activer la console v2 de systèmes de salle Skype émettre et recevoir des appels PSTN                                         | Activé pour le système téléphonique                                                |

Pour plus d’informations sur les comptes de systèmes de salle Skype, voir [configurer les comptes pour les systèmes de salle Skype v2](room-systems-v2-configure-accounts.md).


|    |     |
|-----------|------------|
| ![](../../media/audio_conferencing_image7.png) <br/>Points de décision|<ul><li>Décider quels scénarios vous allez prennent en charge et identifier les besoins de gestion des licences pour vos comptes de service de systèmes de salle Skype v2.</li></ul>| 
| ![](../../media/audio_conferencing_image9.png)<br/>Étapes suivantes|<ul><li>Préparer héberger des ordinateurs et comptes de service.</li></ul>| 


_Compte de service v2 Skype salle systèmes exemple planification de table_

| **Site**  | **Nom de la salle** | **Type de salle** | **Fonctionnalités futures de salle**                                                 | **Fonctionnalités de compte Skype salle systèmes v2**                                                                                         |
|-----------|---------------|---------------|------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------|
| Siège social Londres | Curie         | Moyen        | 1 écran, audio et vidéo plus présentation <br>Accès aux conférences rendez-vous<br> Accès RTC  | Activé pour Skype pour les entreprises, activé pour Exchange (boîtes aux lettres de ressources) <br>Activé pour l’audioconférence <br>Activé pour le système téléphonique |
| Siège Sydney | Hill          | Grande         | 2 écrans, audio et vidéos plus présentation<br>Accès aux conférences rendez-vous<br> Accès RTC  | Activé pour Skype pour les entreprises, activé pour Exchange (boîtes aux lettres de ressources)<br> Activé pour l’audioconférence <br>Activé pour le système téléphonique |


### <a name="prepare-to-host-skype-room-systems-v2-machine-and-service-accounts-optional"></a>Préparer la machine hôte v2 Skype salle systèmes et (facultatifs) de comptes de service

Pour pouvoir gérer et créer des rapports sur votre ordinateur de v2 Skype salle systèmes et comptes de service, préparer votre local Active Directory ou Azure Active Directory (AD Azure). 

Définir un groupe d’Active Directory ou Azure AD sur site pour ajouter tous les systèmes de salle Skype v2 (utilisateur) comptes de service, puis créez les rapports d’utilisation à l’aide de l’applet de commande Get-CSUserSession PowerShell dans votre déploiement de v2 Skype salle systèmes. Par exemple, créez un groupe nommé SkypeRoomSystemsv2 de comptes de Service. 


Définir une unité d’organisation dans votre hiérarchie d’Active Directory ou Azure AD sur site destiné à contenir tous les comptes d’ordinateur Skype salle systèmes v2 (s’ils sont joints au domaine) et une unité d’organisation pour contenir tous les comptes d’utilisateur Skype salle systèmes v2. Si vous créez une unité d’organisation pour les comptes d’ordinateur Skype salle systèmes v2, envisagez de désactiver l’héritage des autorisations pour vous assurer que vous appliquez uniquement les stratégies que à appliquer à la Systemsv2 à un domaine de salle Skype voulu. 

Créer un objet de stratégie de groupe affecté à l’unité d’organisation qui contient vos comptes d’ordinateur Skype salle systèmes. Utilisez cette option pour : 

-   [Définir la puissance et les paramètres du compte local](../../manage/skype-room-systems-v2/room-systems-v2-operations.md#configuring-group-policy-for-skype-room-systems-v2).
-   Activez Windows Update.
-   Activer l’accès à distance PowerShell. Vous pouvez configurer un script de démarrage pour exécuter un script simple : Enable-PSRemoting - Force

Vous pouvez utiliser PowerShell pour effectuer un certain nombre d’activités de gestion à distance, y compris l’obtention et définition des informations de configuration. Accès à distance PowerShell doit être activé *avant* toute PowerShell gestion à distance peut prendre place et doivent être considérés dans le cadre de votre processus de déploiement ou configurés via la stratégie de groupe. Pour plus d’informations sur ces fonctionnalités et de les activer, voir [Maintenance et opérations](../../manage/skype-room-systems-v2/room-systems-v2-operations.md#remote-management-using-powershell). 


## <a name="configuration-and-deployment"></a>Configuration et déploiement 

Planification de la configuration et de déploiement couvre les domaines clés suivants :

-   Mise en service de compte
-   Installation des logiciels de périphérique
-   Déploiement des périphériques
-   Application de systèmes de salle Skype v2 et configuration du périphérique
-   Test
-   Gestion des biens

### <a name="account-provisioning"></a>Mise en service de compte 

Chaque périphérique v2 de systèmes de salle Skype nécessite un compte dédié et uniques des ressources qui doit être activé pour les deux Skype pour les entreprises et Exchange. Ce compte doit avoir une boîte aux lettres de salle hébergée sur Exchange et être activé en tant qu’une salle de réunion dans le Skype pour le déploiement d’entreprise. Sur le côté Exchange, le traitement du calendrier doit être configuré afin que le périphérique peut accepter automatiquement les demandes de réunion entrantes. Pour plus d’informations sur la création de ces comptes, voir [configurer les comptes pour les systèmes de salle Skype v2](room-systems-v2-configure-accounts.md). 

**Conseil pro** – Assurez-vous l’affichage des noms pour ces comptes descriptif et facile à comprendre. Voici les noms qui s’affiche lors de la recherche et ajout de Skype salle systèmes v2 à des réunions. Certaines organisations utilisent la convention de *Site*-*Nom de la salle*(*Capacité maximale*)-RS, par exemple Curie — une salle de conférence 12-personne à Londres — peut avoir le nom d’affichage LON-CURIE (12)-RS. 

Si votre organisation possède plusieurs salles de conférence qui nécessitent plusieurs, les comptes approvisionnés, vous souhaiterez à utiliser des [Scripts de mise en service de comptes Skype salle de systèmes](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_2_0_4,5_2_0_5) à la disposition en bloc plusieurs comptes de service de manière automatique. 


|    |     |
|-----------|------------|
| ![](../../media/audio_conferencing_image7.png) <br/>Points de décision|<ul><li>Déterminez la convention d’affectation de noms pour vos comptes v2 de systèmes de salle Skype.</li><li>Décider si vous allez créer des comptes individuels ou utiliser des scripts de mise en service en bloc.</li></ul>| 
| ![](../../media/audio_conferencing_image9.png)<br/>Étapes suivantes|<ul><li>Commencer à planifier votre déploiement des périphériques.</li></ul>| 


### <a name="device-software-installation"></a>Installation des logiciels de périphérique 

Lorsque vous planifiez de déployer Skype salle Systemsv2, vous disposez d’un nombre d’options à prendre en compte pour installer les logiciels requis. Scénarios courants et approches sont décrits dans le tableau suivant. 

| **Scénario**            | **Approche**         |
|-------------------------|-----------------------|   
|Déploiement d’un petit nombre de périphériques de systèmes de salle Skype (< 10). | Si v2 Surface Pro Skype salle systèmes, procédez comme les [instructions d’installation pour un périphérique par installer](console.md). [Cette vidéo pratique vous guide tout au long du processus.](https://content.cloudguides.com/guides/Configure%20the%20Skype%20Room%20Systems%20console) Si vous utilisez une solution intégrée, déployer à l’aide de l’image de fournisseur et configurez les paramètres selon vos besoins. |
| Déploiement entre 10 et 50 les périphériques d’un seul fournisseur.     | Créer une image WIM et suspendre après [l’étape 6 dans le Guide de](console.md)capturer une image de distribution à utiliser avec la technologie de distribution clonage.    |
| Déploiement de plus de 50 périphériques Skype salle systèmes, le déploiement des périphériques à partir de plusieurs fournisseurs ou nécessitant des agents spécifiques d’une organisation dans le cadre du déploiement. | Utilisez une tâche basée sur Séquenceur génération et distribution plate-forme logicielle, tel que [System Center Configuration Manager](with-oms.md).  |

**Conseil pro** - v2 chaque Skype salle systèmes doit avoir un nom d’ordinateur valide et unique sur votre réseau. Nombre de surveillance et d’alerte systèmes affichent le nom de l’ordinateur comme identificateur de clé, il est important de développer une convention d’appellation pour les déploiements de systèmes de salle Skype v2 permettant de localiser aisément les systèmes de salle Skype v2 qui a été marqué comme personnel de support nécessitant une action. Un exemple peut utiliser un modèle de SRS -*Site*-*Nom de la salle* (SRS-LON-CURIE). 


Dans le cadre du déploiement, vous devez également prendre en compte votre stratégie pour la gestion et la configuration des [comptes locaux](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/skype-room-systems-v2-0#local-accounts) qui sont créés par le programme d’installation de systèmes de salle Skype application.

Nous fournissent des conseils sur l’utilisation de la [Suite de gestion des opérations Microsoft](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/oms-management) pour surveiller le déploiement de v2 Skype salle systèmes et créer des rapports sur la disponibilité, les erreurs matérielles et logicielles et version de l’application v2 Skype salle systèmes. Si vous décidez d’utiliser Microsoft Operations Management Suite, vous installez l’agent Operations Management Suite dans le cadre du processus d’installation logicielle et configurer les informations de connexion d’espace de travail pour votre espace de travail. 

Une considération supplémentaire est si les systèmes de salle Skype v2 doit être joint au domaine. Vous trouverez des informations sur les avantages de l’intégration de domaine considérations sur [rejoindre Skype salle système domaine](domain-joining-considerations.md). 

|    |     |
|-----------|------------|
| ![](../../media/audio_conferencing_image7.png) <br/>Points de décision|<ul><li>Déterminez la convention de dénomination des périphériques Skype salle systèmes à utiliser lors du déploiement.</li><li>Décider si vous rejoignez d’appareils v2 de systèmes de salle Skype pour votre domaine et comment gérer et configurer des comptes locaux. </li><li>Décider si vous allez utiliser la Suite de gestion des opérations pour surveiller le déploiement de v2 Skype salle systèmes.</li><li>Déterminer la méthode que vous allez utiliser pour déployer le logiciel et les agents sur le système v2 de systèmes de salle Skype en vue du déploiement des périphériques. </li></ul>| 
| ![](../../media/audio_conferencing_image9.png)<br/>Étapes suivantes|<ul><li>Commencer à planifier votre approche de déploiement des périphériques.</li></ul>| 


### <a name="device-deployment"></a>Déploiement des périphériques

Une fois que vous avez déployé vos logiciels unités Skype salle systèmes v2, créez votre plan pour livrer les périphériques et leurs périphériques affectées à vos salles, puis passez à l’installation et la configuration. 


|    |     |
|-----------|------------|
| ![](../../media/audio_conferencing_image7.png) <br/>Points de décision|<ul><li>Décidez qui va gérer le déploiement de site par site.</li><li> Identifier les ressources qui installera les périphériques v2 de systèmes de salle Skype sur site et procéder à la configuration et de test.</li></ul>| 
| ![](../../media/audio_conferencing_image9.png)<br/>Étapes suivantes|<ul><li>Commencer les tests de l’appareil.</li></ul>| 

_Exemple de tableau de déploiement_

| **Site**  | **Nom de la salle** | **Type de salle** | **Systèmes de salle de Skype v2 système**  | **Tous les périphériques**  | **Nom de l’ordinateur Skype salle systèmes v2**  | **Compte de la ressource Skype salle systèmes v2**  |
|-----------|---------------|---------------|-----------------------------------|------------------|------------------------------------------|---------------------------------------------|
| Siège social Londres | Curie         | Moyen        |                                   |                  |                                          |                                             |
| Siège Sydney | Hill          | Grande         |                                   |                  |                                          |                                             |

### <a name="skype-room-systems-v2-application-and-peripheral-device-configuration"></a>Application de systèmes de salle Skype v2 et configuration du périphérique 

Une fois que chaque système v2 de systèmes de salle Skype a été déployée physiquement et les périphériques pris en charge connectés, vous devez configurer l’application v2 de systèmes de salle Skype pour attribuer le compte de la ressource Skype salle systèmes v2 et le mot de passe créé précédemment, à Activer le système de v2 de systèmes de salle Skype pour vous connecter à Skype pour les entreprises et Exchange. Il s’agit de la clé à tirer parti de Skype pour les entreprises certifié périphériques audio et vidéos USB liées ailleurs dans le document. Sinon, peut entraîner un comportement imprévisible. 

Vous pouvez configurer manuellement chaque système v2 de systèmes de salle Skype. Vous pouvez également utiliser un stockée de manière centralisée, systèmes de salle par – Skype XML fichier de configuration pour gérer les paramètres d’application et de tirer parti d’un script de stratégie de groupe de démarrage afin de réappliquer la configuration souhaitée, chaque fois que le système de v2 Skype salle systèmes démarre. 

Pour plus d’informations sur la façon d’utiliser le fichier de configuration XML, voir [un v2 Skype salle de systèmes de gérer les paramètres de la console à distance avec un fichier de configuration XML](../../manage/skype-room-systems-v2/xml-config-file.md). 

Vous pouvez utiliser [PowerShell à distance](../../manage/skype-room-systems-v2/room-systems-v2-operations.md#remote-management-using-powershell) pour extraire la configuration v2 de systèmes de salle Skype pour les besoins de rapports. 

|    |     |
|-----------|------------|
| ![](../../media/audio_conferencing_image7.png) <br/>Points de décision|<ul><li>Décider si vous allez manuellement configurer chaque système v2 de systèmes de salle Skype ou utiliser un fichier XML central (une par appareil v2 de systèmes de salle Skype).</li></ul>| 
| ![](../../media/audio_conferencing_image9.png)<br/>Étapes suivantes|<ul><li>Définir votre approche de gestion à distance.</li></ul>| 

### <a name="testing"></a>Test

Une fois que le système v2 Skype salle systèmes a été déployé, vous devez le tester. Vérifiez que les fonctionnalités répertoriées dans [l’aide de systèmes de salle Skype v2](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) fonctionnent sur l’appareil déployé. Il est vivement recommandé que l’équipe de déploiement vérifie que les systèmes de salle Skype v2 se connecte à la Suite de gestion des opérations Microsoft (le cas échéant). Il est également important d’effectuer un nombre de réunions et appels de test pour vérifier la qualité. Pour plus d’informations, voir cette [liste de vérification du déploiement utiles](console.md#skype-room-systems-v2-deployment-checklist). 

Il est recommandé que dans le cadre de la Skype général pour le déploiement d’entreprise, vous configurez les fichiers de création de tableau de bord de qualité des appels (CQD), d’analyser les tendances de qualité et prendre part dans le processus d’examen de la qualité de l’expérience. Pour plus d’informations, consultez le [Guide Quality of Experience révision](https://aka.ms/qerguide). 

**Conseil pro** – la [Matrice de test](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_21) disponibles à partir de [MyAdvisor](https://myadvisor.fasttrack.microsoft.com/) contient un onglet avec un nombre de systèmes de salle Skype v2 tests que nous vous invitons à l’aide dans le cadre de vos tests. 

### <a name="asset-management"></a>Gestion des biens 

Dans le cadre du déploiement, vous souhaiterez mettre à jour votre Registre connecté le compte de ressource Skype salle systèmes v2, nom du périphérique Skype salle systèmes v2, nom de la salle et affecté des périphériques (et les ports USB utilisent). 

_Exemple de tableau actif_

| **Site**  | **Nom de la salle** | **Type de salle** | **Systèmes de salle Skype v2 numéro de série.**  | **Périphériques / série n° / Ports**  | **Nom de l’ordinateur Skype salle systèmes v2**  | **Compte de service de systèmes de salle Skype v2**  | **Date déployé** |
|-----------|---------------|---------------|------------------------------------------|------------------------------------------|------------------------------------------|--------------------------------------------|-------------------|
| Siège social Londres | Curie         | Moyen        |                                          |                                          |                                          |                                            |                   |
| Siège Sydney | Hill          | Grande         |                                          |                                          |                                          |                                            |                   |


