---
title: Déployer les équipes Microsoft salles
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
- M365-voice
ms.custom: ''
ms.assetid: 678689e4-d547-499b-be64-7d8f16dd8668
description: Lisez cet article pour en savoir plus sur le déploiement de salles d’équipes Microsoft.
ms.openlocfilehash: 26a8a15f678c57e9e2f27b4aacde1577176a3840
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33916550"
---
# <a name="deployment-overview"></a>Vue d’ensemble du déploiement

Déploiement de Microsoft équipes salles essentiellement divise en phases :

- Vous demandant de confirmer que les emplacements de déploiement (salles) satisfont les dépendances de déploiement
- Création de Microsoft Teams ou Skype pour les comptes d’entreprise et Exchange et en leur attribuant sur les périphériques de la console (voir [configurer les comptes pour les salles d’équipes Microsoft](room-systems-v2-configure-accounts.md))
- Créer de nouvelles images Microsoft Surface tablettes pour fonctionner en tant que consoles de salles d’équipes Microsoft (voir [configurer une console Microsoft équipes salles](console.md) ou [déployer Microsoft équipes salles guide de déploiement de masse](room-systems-scale.md))
- (Facultatif) Configuration de Microsoft Operations Management Suite pour vos systèmes (voir [Gestion des salles d’équipes Microsoft déployer avec Azure moniteur](azure-monitor-deploy.md)
- Configuration de consoles dans les salles de réunion et connexion des périphériques vous devez (voir la documentation du fabricant de votre jeu de périphériques)

Techniciens AV peuvent être utilisées pour la dernière tâche, mais que votre organisation informatique doit être effectuée les autres parties du processus. 


## <a name="site-readiness"></a>Préparation du site 

Alors que les périphériques commandés sont remis à votre organisation, travailler avec votre mise en réseau et les installations et les équipes d’a/v pour vous assurer que les dépendances de déploiement sont remplies et chaque site et la salle sont prêt en termes d’alimentation, réseau et les afficher. En outre, assurez-vous que les conditions d’installation physique sont remplies. Pour des considérations relatives à l’installation physique, visitez le site du fournisseur et tirer parti de l’expérience de votre équipe AV lors de l’installation et écrans de montage et câblage en cours d’exécution.

Vous pouvez trouver plus d’informations sur ces dépendances dans les liens du Guide de planification ci-dessous :

-   [Vérification de la disponibilité du réseau](srs-v2-prep.md#check-network-availability) 
-   [Certificats](srs-v2-prep.md#certificates)
-   [Proxy](srs-v2-prep.md#proxy)

**Conseil pro** - si vous envisagez d’utiliser des serveurs proxy pour fournir l’accès à Microsoft Teams ou Skype pour Business en ligne, d’abord [Lisez cet article](https://docs.microsoft.com/skypeforbusiness/optimizing-your-network/proxy-servers-for-skype-for-business-online). Notez que lorsqu’il s’agit Skype pour le trafic métiers via des serveurs proxy, nous vous recommandons d’ignorer complètement les serveurs proxy. Skype pour le trafic d’entreprise est déjà chiffré, les serveurs proxy ne pas rendre plus sécurisé. Dans le cadre de votre déploiement plus large, nous vous conseillons de suivre les instructions de [évaluer mon environnement](https://docs.microsoft.com/MicrosoftTeams/3-envision-evaluate-my-environment#network-readiness) pour la bande passante de planification et d’évaluation de pertinence de votre réseau pour le trafic en temps réel. Pour toute la bande passante planification, utilisez le [Planificateur de réseau MyAdvisor](https://myadvisor.fasttrack.microsoft.com/CloudVoice/NetworkPlanner). (Nous vous conseillons de créer un personnage salles d’équipes Microsoft pour refléter l’utilisation prévue de salles d’équipes Microsoft [vidéo, partage d’écran, audio] et affecter un nombre d’utilisateurs qui correspond au nombre d’unités de salles d’équipes Microsoft pour être déployés sur chaque site.) 

|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>Points de décision|<ul><li>Vérifiez que vos sites répondent aux exigences clés pour les salles d’équipes Microsoft.</li><li>Vérifiez que vous avez fourni suffisamment de bande passante pour chaque site.</li></ul>| 
| ![](../media/audio_conferencing_image9.png)<br/>Étapes suivantes|<ul><li>Commencer à planifier votre déploiement des périphériques et la configuration.</li></ul>| 

**Professionnels de l’info-bulle-** À partir d’un point de vue de planification de site par site, vous pourriez trouver utiles les ressources suivantes. Ils traitent plus que les salles d’équipes Microsoft et peuvent être utilisées dans un déploiement complet de Skype pour Business Online :

-   [Déploiement de site/remise Guide de planification de Migration](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_24)

-   [Site de déploiement et de planification de la Migration - lecture](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_16)

    > [!NOTE]
    > Dans la lecture, effectuez les tâches dans la section « 4,3 – > salles de conférence » dans la feuille « 4-points de terminaison » pour chaque site où vous projetez de déployer des périphériques Microsoft équipes salles. Cela vous permettra d’utiliser le compte en bloc script plus loin dans le processus de mise en service. 

## <a name="service-readiness"></a>Préparation du service

Pour préparer votre déploiement salles des équipes Microsoft, effectuez la clé suivante, les tâches centrale :

-   Définir les fonctionnalités de compte de service de salles d’équipes Microsoft.
-   Préparer une unité d’organisation et un groupe Active Directory pour maintenir votre ordinateur salles d’équipes Microsoft et de comptes, de service et, éventuellement, préparer des objets de stratégie de groupe (GPO) pour activer l’accès à distance PowerShell.

### <a name="define-microsoft-teams-rooms-service-account-features"></a>Définir les fonctionnalités de compte de service Microsoft équipes salles 

Selon les scénarios de collaboration que vous avez décidé d’activer avec votre déploiement de salles d’équipes Microsoft, vous devrez déterminer les fonctionnalités que vous assignez à chaque compte de service Microsoft équipes salles que vous activez.

| **Scénario** | **Description** | **Fonctionnalité de compte de service Microsoft équipes salles** |
|---------- |------------- | --- |
| Réunions interactives            | À l’aide de la voix, vidéo et partage d’écran ; rendre les salles d’équipes Microsoft une ressource bookable                     | Activé pour Skype pour les entreprises, activé pour Exchange (boîtes aux lettres de ressources) |
| Conférence rendez-vous            | Activer le démarrage de réunions *directement* depuis la console de salles d’équipes Microsoft avec des coordonnées de conférence rendez-vous | Activé pour l’audioconférence                                          |
| Entrante/sortante l’appel PSTN | Activer la console de salles d’équipes Microsoft émettre et recevoir des appels PSTN                                         | Activé pour le système téléphonique                                                |

Pour plus d’informations sur les comptes locaux des équipes Microsoft, voir [configurer les comptes pour les salles d’équipes Microsoft](room-systems-v2-configure-accounts.md).


|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>Points de décision|<ul><li>Décider quels scénarios vous allez prennent en charge et identifier les besoins de gestion des licences pour vos comptes de service Microsoft équipes salles.</li></ul>| 
| ![](../media/audio_conferencing_image9.png)<br/>Étapes suivantes|<ul><li>Préparer héberger des ordinateurs et comptes de service.</li></ul>| 


_Compte de service Microsoft équipes salles exemple planification de table_

| **Site**  | **Nom de la salle** | **Type de salle** | **Fonctionnalités futures de salle**                                                 | **Fonctionnalités de compte Microsoft équipes salles**                                                                                         |
|-----------|---------------|---------------|------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------|
| Siège social Londres | Curie         | Moyen        | 1 écran, audio et vidéo plus présentation <br>Accès aux conférences rendez-vous<br> Accès RTC  | Activé pour Skype pour les entreprises, activé pour Exchange (boîtes aux lettres de ressources) <br>Activé pour l’audioconférence <br>Activé pour le système téléphonique |
| Siège Sydney | Hill          | Grande         | 2 écrans, audio et vidéos plus présentation<br>Accès aux conférences rendez-vous<br> Accès RTC  | Activé pour Skype pour les entreprises, activé pour Exchange (boîtes aux lettres de ressources)<br> Activé pour l’audioconférence <br>Activé pour le système téléphonique |


### <a name="prepare-to-host-microsoft-teams-rooms-machine-and-service-accounts-optional"></a>Préparer héberger des ordinateurs locaux des équipes Microsoft et (facultatifs) de comptes de service

Pour vous permettre de gérer et de créer des rapports sur vos salles d’équipes Microsoft comptes d’ordinateur et de service, préparer votre local Active Directory ou Azure Active Directory (AD Azure). 

Définir un groupe d’Active Directory ou Azure AD sur site pour ajouter tous les comptes de service (utilisateur) Microsoft équipes salles à, puis créer les rapports d’utilisation à l’aide de l’applet de commande Get-CSUserSession PowerShell dans votre déploiement de salles d’équipes Microsoft. Par exemple, créez un groupe nommé SkypeRoomSystemsv2 de comptes de Service. 


Définir une unité d’organisation dans votre hiérarchie d’Active Directory ou Azure AD sur site destiné à contenir tous les comptes d’ordinateur salles d’équipes Microsoft (s’ils sont joints au domaine) et une unité d’organisation pour contenir tous les comptes d’utilisateur locaux des équipes Microsoft. Si vous créez une unité d’organisation pour les comptes d’ordinateurs locaux des équipes Microsoft, envisagez de désactiver l’héritage des autorisations pour vous assurer que vous appliquez uniquement les stratégies que vous destiné à appliquer dans les salles d’équipes Microsoft à un domaine. 

Créer un objet de stratégie de groupe affecté à l’unité d’organisation qui contient vos comptes d’ordinateurs locaux des équipes Microsoft. Utilisez cette option pour : 

-   [Définir la puissance et les paramètres du compte local](room-systems-v2-operations.md#configuring-group-policy-for-microsoft-teams-rooms).
-   Activez Windows Update.
-   Activer l’accès à distance PowerShell. Vous pouvez configurer un script de démarrage pour exécuter un script simple : Enable-PSRemoting - Force

Vous pouvez utiliser PowerShell pour effectuer un certain nombre d’activités de gestion à distance, y compris l’obtention et définition des informations de configuration. Accès à distance PowerShell doit être activé *avant* toute PowerShell gestion à distance peut prendre place et doivent être considérés dans le cadre de votre processus de déploiement ou configurés via la stratégie de groupe. Pour plus d’informations sur ces fonctionnalités et de les activer, voir [Maintenance et opérations](room-systems-v2-operations.md#remote-management-using-powershell). 


## <a name="configuration-and-deployment"></a>Configuration et déploiement 

Planification de la configuration et de déploiement couvre les domaines clés suivants :

-   Mise en service de compte
-   Installation des logiciels de périphérique
-   Déploiement des périphériques
-   Application de salles d’équipes Microsoft et la configuration de périphérique
-    Tests
-   Gestion des biens

### <a name="account-provisioning"></a>Mise en service de compte 

Chaque périphérique Microsoft équipes salles nécessite un compte dédié et uniques des ressources qui doit être activé pour Microsoft Teams ou de Skype pour les entreprises et Exchange. Ce compte doit avoir une boîte aux lettres de salle hébergée sur Exchange et être activé en tant qu’une salle de réunion dans les équipes ou Skype pour le déploiement d’entreprise. Sur le côté Exchange, le traitement du calendrier doit être configuré afin que le périphérique peut accepter automatiquement les demandes de réunion entrantes. Pour plus d’informations sur la création de ces comptes, voir [configurer les comptes pour les salles d’équipes Microsoft](room-systems-v2-configure-accounts.md). 

**Conseil pro** – Assurez-vous l’affichage des noms pour ces comptes descriptif et facile à comprendre. Voici les noms qui s’affiche lors de la recherche et ajout de systèmes de salles d’équipes Microsoft à des réunions. Certaines organisations utilisent la convention de *Site*-*Nom de la salle*(*Capacité maximale*)-RS, par exemple Curie — une salle de conférence 12-personne à Londres — peut avoir le nom d’affichage LON-CURIE (12)-RS. 

Si votre organisation possède plusieurs salles de conférence qui nécessitent plusieurs, les comptes approvisionnés, vous souhaiterez à utiliser des [Scripts de mise en service de comptes Skype salle de systèmes](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_2_0_4,5_2_0_5) à la disposition en bloc plusieurs comptes de service de manière automatique.


|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>Points de décision|<ul><li>Déterminez la convention d’affectation de noms pour vos comptes locaux des équipes Microsoft.</li><li>Décider si vous allez créer des comptes individuels ou utiliser des scripts de mise en service en bloc.</li></ul>| 
| ![](../media/audio_conferencing_image9.png)<br/>Étapes suivantes|<ul><li>Commencer à planifier votre déploiement des périphériques.</li></ul>| 


### <a name="device-software-installation"></a>Installation des logiciels de périphérique 

Lorsque vous planifiez de déployer Microsoft équipes salles, vous disposez d’un nombre d’options à prendre en compte pour installer les logiciels requis. Scénarios courants et approches sont décrits dans le tableau suivant. 

| **Scénario**            | **Approche**         |
|-------------------------|-----------------------|   
|Déploiement d’un petit nombre de périphériques de salles d’équipes Microsoft (<10). | Si Surface Pro basée sur Microsoft équipes salles, procédez comme les [instructions d’installation pour un périphérique par installer](console.md). [Cette vidéo pratique vous guide tout au long du processus.](https://content.cloudguides.com/guides/Configure%20the%20Skype%20Room%20Systems%20console) Si vous utilisez une solution intégrée, déployer à l’aide de l’image de fournisseur et configurez les paramètres selon vos besoins. |
| Déploiement entre 10 et 50 les périphériques d’un seul fournisseur.     | Créer une image WIM et suspendre après [l’étape 6 dans le Guide de](console.md)capturer une image de distribution à utiliser avec la technologie de distribution clonage.    |
| Déploiement de plus de 50 périphériques salles des équipes Microsoft, le déploiement des périphériques à partir de plusieurs fournisseurs ou nécessitant des agents spécifiques d’une organisation dans le cadre du déploiement. | Utilisez une tâche basée sur Séquenceur génération et distribution plate-forme logicielle, tel que [System Center Configuration Manager](room-systems-scale.md).  |

**Conseil pro** - chaque salles d’équipes Microsoft doit avoir un nom d’ordinateur valide et unique sur votre réseau. Nombre de surveillance et d’alerte systèmes affichent le nom de l’ordinateur comme identificateur de clé, il est important de développer une convention d’affectation de noms pour les déploiements de salles d’équipes Microsoft qui permet le personnel du support technique localiser aisément les salles d’équipes Microsoft qui a été marqué comme nécessitant une action. Un exemple peut utiliser un modèle de MTR -*Site*-*Nom de la salle* (MTR-LON-CURIE). 

Dans le cadre du déploiement, vous devez également prendre en compte votre stratégie pour la gestion et la configuration des [comptes locaux](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/skype-room-systems-v2-0#local-accounts) qui sont créés par le programme d’installation Microsoft équipes salles application.

Nous fournissent des conseils sur l’utilisation de l' [Analyseur de Microsoft Azure](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/azure-monitor) pour surveiller le déploiement de Microsoft équipes salles et créer des rapports sur la disponibilité, les erreurs matérielles et logicielles et version de l’application Microsoft équipes salles. Si vous décidez d’utiliser Microsoft Operations Management Suite, vous installez l’agent Operations Management Suite dans le cadre du processus d’installation logicielle et configurer les informations de connexion d’espace de travail pour votre espace de travail. 

Une considération supplémentaire est si les salles d’équipes Microsoft doit être joint au domaine. Vous trouverez des informations sur les avantages de l’intégration de domaine considérations sur [rejoindre Skype salle système domaine](domain-joining-considerations.md). 

|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>Points de décision|<ul><li>Déterminez la convention de dénomination des périphériques salles d’équipes Microsoft à utiliser lors du déploiement.</li><li>Décider si vous rejoignez d’appareils salles d’équipes Microsoft pour votre domaine et comment gérer et configurer des comptes locaux. </li><li>Décider si vous allez utiliser la Suite de gestion des opérations pour surveiller le déploiement de salles d’équipes Microsoft.</li><li>Déterminer la méthode que vous allez utiliser pour déployer le logiciel et les agents pour le système Microsoft équipes salles en vue du déploiement des périphériques. </li></ul>| 
| ![](../media/audio_conferencing_image9.png)<br/>Étapes suivantes|<ul><li>Commencer à planifier votre approche de déploiement des périphériques.</li></ul>| 


### <a name="device-deployment"></a>Déploiement des périphériques

Une fois que vous avez déployé le logiciel pour les unités de salles d’équipes Microsoft, créez votre plan pour livrer les périphériques et leurs périphériques affectées à vos salles, puis passez à l’installation et la configuration. 


|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>Points de décision|<ul><li>Décidez qui va gérer le déploiement de site par site.</li><li> Identifier les ressources qui installera les périphériques salles d’équipes Microsoft sur site et procéder à la configuration et de test.</li></ul>| 
| ![](../media/audio_conferencing_image9.png)<br/>Étapes suivantes|<ul><li>Commencer les tests de l’appareil.</li></ul>| 

_Exemple de tableau de déploiement_

| **Site**  | **Nom de la salle** | **Type de salle** | **Système de salles d’équipes Microsoft**  | **Tous les périphériques**  | **Nom de l’ordinateur Microsoft équipes salles**  | **Compte de ressource salles d’équipes Microsoft**  |
|-----------|---------------|---------------|-----------------------------------|------------------|------------------------------------------|---------------------------------------------|
| Siège social Londres | Curie         | Moyen        |                                   |                  |                                          |                                             |
| Siège Sydney | Hill          | Grande         |                                   |                  |                                          |                                             |

### <a name="microsoft-teams-rooms-application-and-peripheral-device-configuration"></a>Application de salles d’équipes Microsoft et la configuration de périphérique 

Après chaque salles d’équipes Microsoft système a été déployé physiquement et les périphériques pris en charge connectés, vous devez configurer l’application Microsoft équipes salles pour attribuer le compte de ressource salles d’équipes Microsoft et le mot de passe créé précédemment , pour permettre au système de salles d’équipes Microsoft pour vous connecter à Microsoft Teams ou Skype pour les entreprises et Exchange. Il est la clé pour mettre à profit certifié audio et vidéos les périphériques USB liées ailleurs dans le document. Sinon, peut entraîner un comportement imprévisible. 

Vous pouvez configurer manuellement chaque système salles d’équipes Microsoft. Vous pouvez également utiliser un stockée de manière centralisée, salles d’équipes Microsoft par le fichier de configuration XML pour gérer les paramètres d’application et de tirer parti d’un script de stratégie de groupe de démarrage afin de réappliquer la configuration souhaitée, chaque fois que le système de salles d’équipes Microsoft démarre. 

Pour plus d’informations sur la façon d’utiliser le fichier de configuration XML, voir [Gérer les paramètres de la console de salles d’équipes Microsoft à distance avec un fichier de configuration XML](xml-config-file.md). 

Vous pouvez utiliser [PowerShell à distance](room-systems-v2-operations.md#remote-management-using-powershell) pour extraire la configuration de salles d’équipes Microsoft pour les besoins de rapports. 

|    |     |
|-----------|------------|
| ![](../media/audio_conferencing_image7.png) <br/>Points de décision|<ul><li>Décider si vous allez manuellement configurer chaque système Microsoft équipes salles ou utiliser un fichier XML central (une par appareil salles d’équipes Microsoft).</li></ul>| 
| ![](../media/audio_conferencing_image9.png)<br/>Étapes suivantes|<ul><li>Définir votre approche de gestion à distance.</li></ul>| 

### <a name="testing"></a> Tests

Une fois que le système de salles d’équipes Microsoft a été déployé, vous devez le tester. Vérifiez que les fonctionnalités répertoriées dans les [salles d’équipes Microsoft aide](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) fonctionne sur les appareils mobiles déployés. Il est vivement recommandé que l’équipe de déploiement vérifie que les salles d’équipes Microsoft se connecte à la Suite de gestion des opérations Microsoft (le cas échéant). Il est également important d’effectuer un nombre de réunions et appels de test pour vérifier la qualité. Pour plus d’informations, voir cette [liste de vérification du déploiement utiles](console.md#microsoft-teams-rooms-deployment-checklist).

Il est recommandé que dans le cadre des équipes générales Skype pour le déploiement d’entreprise, vous configurez les fichiers de création de tableau de bord de qualité des appels (CQD), d’analyser les tendances de qualité et prendre part dans le processus d’examen de la qualité de l’expérience. Pour plus d’informations, consultez le [Guide Quality of Experience révision](https://aka.ms/qerguide). 

**Conseil pro** – la [Matrice de test](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_21) disponibles à partir de [MyAdvisor](https://myadvisor.fasttrack.microsoft.com/) contient un onglet avec un nombre de tests de salles d’équipes Microsoft vous invitons à lire à l’aide dans le cadre de vos tests. 

### <a name="asset-management"></a>Gestion des biens 

Dans le cadre du déploiement, vous souhaiterez mettre à jour votre Registre connecté le compte de ressource salles des équipes Microsoft, nom du périphérique salles des équipes Microsoft, nom de la salle et affecté des périphériques (et les ports USB utilisent). 

_Exemple de tableau actif_

| **Site**  | **Nom de la salle** | **Type de salle** | **Salles d’équipes Microsoft numéro de série.**  | **Périphériques / série n° / Ports**  | **Nom de l’ordinateur Microsoft équipes salles**  | **Compte de service Microsoft équipes salles**  | **Date déployé** |
|-----------|---------------|---------------|------------------------------------------|------------------------------------------|------------------------------------------|--------------------------------------------|-------------------|
| Siège social Londres | Curie         | Moyen        |                                          |                                          |                                          |                                            |                   |
| Siège Sydney | Hill          | Grande         |                                          |                                          |                                          |                                            |                   |


