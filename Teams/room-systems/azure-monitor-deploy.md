---
title: Déployer la gestion des salles d’équipes Microsoft Azure moniteur
ms.author: jambirk
author: jambirk
ms.reviewer: Turgayo
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
- M365-voice
ms.custom: ''
ms.assetid: d86ff657-ee92-4b06-aee3-d4c43090bdcb
description: Cet article explique comment déployer la gestion des périphériques Microsoft équipes salles d’une manière intégrée, de bout en bout pour l’utilisation du moniteur Azure.
ms.openlocfilehash: c9808e03a9f72ce016e4e16b06a277377832122b
ms.sourcegitcommit: 79ec789a22acf1686c33a5cc8ba3bd50049f94b8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/26/2019
ms.locfileid: "33362784"
---
# <a name="deploy-microsoft-teams-rooms-management-with-azure-monitor"></a>Déployer la gestion des salles d’équipes Microsoft Azure moniteur

Cet article explique comment configurer et déployer gestion intégrée, de bout en bout des périphériques de salles d’équipes Microsoft Azure le moniteur.

Vous pouvez configurer les journaux Analytique moniteur Azure pour fournir la télémétrie base et alertes qui vous aideront à gérer les salles d’équipes Microsoft équipements de salle de réunion. Comme votre solution de gestion ailleurs, vous pouvez décider de déployer des données supplémentaires et les fonctionnalités de gestion pour créer une vue plus détaillée de performances et la disponibilité des périphériques.

En suivant ce guide, vous pouvez utiliser un tableau de bord à l’exemple suivant pour obtenir le statut détaillé, création de rapports pour la disponibilité des périphériques, application et d’intégrité, de matériel et application salles d’équipes Microsoft et distribution de version de système d’exploitation.

![Exemple de journal Analytique afficher pour les salles d’équipes Microsoft] (../media/Deploy-Azure-Monitor-1.png "Exemple de journal Analytique afficher pour les salles d’équipes Microsoft")

À haut niveau, vous devez effectuer les tâches suivantes :


1.  [Valider la configuration du journal Analytique](azure-monitor-deploy.md#validate_LogAnalytics)
2.  [Configurer les périphériques de test pour l’installation de gestion de journal Analytique](azure-monitor-deploy.md#configure_test_devices)
3.  [Mapper les champs personnalisés](azure-monitor-deploy.md#Custom_fields)
4.  [Définir les affichages de salles d’équipes Microsoft dans le journal Analytique](azure-monitor-deploy.md#Define_Views)
5.  [Définir des alertes](azure-monitor-deploy.md#Alerts)
6.  [Configurer tous les périphériques pour la surveillance](azure-monitor-deploy.md#configure_all_devices)
7.  [Configurer des solutions Azure moniteur supplémentaires](azure-monitor-deploy.md#Solutions)

> [!IMPORTANT]
> Bien que la configuration minimale Azure moniteur journal Analytique permet de surveiller un ordinateur exécutant un système d’exploitation Windows, il y a encore quelques étapes Microsoft Teams salles spécifiques que vous devez prendre avant de commencer le déploiement des agents sur tous les Teams Microsoft Périphériques de salles.
> Par conséquent, nous vous recommandons vivement de que procéder à toutes les étapes de configuration dans le bon ordre pour un contrôle du programme d’installation et la configuration. La qualité du résultat final dépend beaucoup de la qualité de la configuration initiale.

## <a name="validate-log-analytics-configuration"></a>Valider la configuration du journal Analytique
<a name="validate_LogAnalytics"> </a>

Vous devez disposer d’un espace de travail journal Analytique pour démarrer la collecte de journaux à partir des périphériques Microsoft équipes salles. Un espace de travail est un environnement de journal Analytique unique avec son propre référentiel de données, les sources de données et les solutions. Si vous disposez déjà d’un espace de travail Analytique de journal existante, vous pouvez l’utiliser pour analyser votre déploiement de Microsoft équipes salles ou sinon, vous pouvez créer un espace de travail journal Analytique dédié spécifique à vos salles d’équipes Microsoft surveillance.

Si vous avez besoin créer un nouvel espace de travail de journal Analytique, suivez les instructions de l’article [créer un espace de travail Analytique journal dans le portail Azure](https://docs.microsoft.com/azure/azure-monitor/learn/quick-create-workspace)

> [!NOTE]
> Pour utiliser le journal Analytique avec Azure moniteur, vous devez disposez d’un abonnement Azure actif. Si vous ne disposez d’un abonnement Azure, vous pouvez créer [un abonnement d’évaluation gratuit](https://azure.microsoft.com/free) comme point de départ.

### <a name="configure-log-analytics-to-collect-microsoft-teams-rooms-event-logs"></a>Configurer le journal Analytique pour collecter des journaux des événements Microsoft équipes salles

Journal Analytique collecte uniquement les événements dans les journaux des événements Windows qui sont spécifiés dans les paramètres. Pour chaque journal, seuls les événements avec les niveaux de gravité sélectionnés sont collectés.

Vous devez configurer le journal Analytique pour collecter les journaux requis pour surveiller l’état de périphériques et d’applications Microsoft équipes salles. Les appareils de salles d’équipes Microsoft utilisent le journal des événements **Système de salle Skype** .

Pour configurer le journal Analytique pour collecter les événements de salles d’équipes Microsoft, voir [les sources de données de journal des événements Windows Azure moniteur](https://docs.microsoft.com/azure/azure-monitor/platform/data-sources-windows-events)

![Paramètres du journal des événements] (../media/Deploy-Azure-Monitor-2.png "Paramètres du journal des événements")

> [!IMPORTANT]
> Configurer les paramètres du journal des événements Windows et entrez **Skype salle système** en tant que nom du journal des événements, puis activez les cases à cocher **erreur**, **Avertissement**et **informations** .

## <a name="configure-test-devices-for-azure-monitoring"></a>Configurer les périphériques de test pour la surveillance d’Azure
<a name="configure_test_devices"> </a>

Vous devez préparer Analytique journal pour être en mesure de surveiller les événements relatifs aux salles d’équipes Microsoft. Vous devez déployer les agents de Monitoring Microsoft sur une ou deux périphériques salles d’équipes Microsoft que vous avez accès physique à et obtenir les périphériques de test générer des données et l’envoyer à l’espace de travail journal Analytique.

### <a name="install-microsoft-monitoring-agents-to-test-devices"></a>Installer des agents Monitoring Microsoft pour tester les périphériques

Déployer l’agent Microsoft Monitoring sur les périphériques de test en suivant les instructions fournies dans [les ordinateurs Windows de se connecter au service journal Analytique dans Azure](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows). Cet article fournit des informations détaillées sur les étapes de déploiement de Microsoft surveillance Agent pour Windows, des instructions permettant d’obtenir journal Analytique ***ID de l’espace de travail*** et la ***clé primaire*** pour obtenir les appareils Microsoft équipes salles connectée à votre déploiement de moniteur Azure et les étapes permettant de vérifier la connectivité de l’agent à l’instance de journal Analytique.

### <a name="generate-sample-microsoft-teams-rooms-events"></a>Générer des exemples d’événements Microsoft équipes salles

Une fois que l’agent Microsoft Monitoring est déployé sur les périphériques de test, vérifiez que les données du journal des événements requis sont collectées par l’analyseur Azure.

> [!NOTE]
> Redémarrer le périphérique après l’installation de l’agent Microsoft Monitoring et vérifiez que cette application de réunion de salles d’équipes Microsoft est démarrée, afin qu’il peut générer des nouveaux événements dans le journal des événements.

1.  Connectez-vous au [portail Microsoft Azure](https://portal.azure.com) et accédez au journal Analytique et sélectionnez votre espace de travail.

2.  Répertorie les événements de pulsation générés par un périphérique Microsoft équipes salles :
    1.  Sélectionnez votre espace de travail et accédez à **journaux** et utiliser une requête pour récupérer les enregistrements de pulsation dont les champs personnalisés pour les salles d’équipes Microsoft.
    2.  Exemple de requête :`Event | where Source == "SRS-App" and EventID == 2000`

3.  Assurez-vous que la requête renvoie les enregistrements du journal qui incluent les événements générés par l’application de réunions salles d’équipes Microsoft.

4.  Générer un problème de configuration matérielle et valider que les événements requis sont enregistrés dans Azure journal Analytique.
    1.  Déconnectez un des périphériques sur le système Microsoft équipes salles de test. Cela peut être la caméra, téléphone mains libres, microphone ou affichage de la salle de premier plan
    2.  Attendez 10 minutes pour le journal des événements doivent être renseignés dans Azure journal Analytique.
    3.  Utiliser une requête d’événements d’erreur de matériel de liste :`Event | where Source == "SRS-App" and EventID == 3001`

5.  Générer un problème d’application et valider que les événements requis sont enregistrés.
    1.  Modifier la configuration de l’application Microsoft équipes salles, puis tapez une paire adresse/mot de passe de protocole SIP (Session Initiation) incorrect.
    2.  Attendez 10 minutes pour le journal des événements doivent être renseignés dans Azure journal Analytique.
    3.  Utiliser une requête d’événements d’erreur liste application :`Event | where Source == "SRS-App" and EventID == 2001 and EventLevel == 1`

> [!IMPORTANT]
> Ces exemples les journaux des événements sont requis avant de pouvoir configurer des champs personnalisés. Ne pas passer à l’étape suivante jusqu'à ce que vous avez collecté les journaux d’événements.

## <a name="map-custom-fields"></a>Mapper les champs personnalisés
<a name="Custom_fields"> </a>

Vous utilisez des champs personnalisés pour extraire des données spécifiques dans les journaux des événements. Vous devez définir des champs personnalisés qui seront utilisés ultérieurement des mosaïques, les tableaux de bord et des alertes. Voir [les champs personnalisés dans le journal Analytique](https://docs.microsoft.com/azure/azure-monitor/platform/custom-fields) et de vous familiariser avec les concepts avant de commencer la création de vos champs personnalisés.

Pour extraire vos champs personnalisés hors les journaux des événements capturés, procédez comme suit :

1.  Connectez-vous au [portail Microsoft Azure](https://portal.azure.com) et accédez au journal Analytique et sélectionnez votre espace de travail.

2. Répertorie les événements générés par un appareil Microsoft équipes salles :
   1.  Accédez à **journaux** et utiliser une requête pour récupérer les enregistrements dont le champ personnalisé.
   2.  Exemple de requête :`Event | where Source == "SRS-App" and EventID == 2000`

3. Sélectionnez une des enregistrements, sélectionnez le bouton situé à gauche et démarrer l’Assistant d’extraction de champ.
4. Mettez en surbrillance les données que vous souhaitez extraire la RenderedDescription et fournir un champ de titre. Les noms de champ que vous devez utiliser sont fournies dans le tableau 1.

   ![Définition de champ personnalisé] (../media/Deploy-Azure-Monitor-4.png "Définition de champ personnalisé")

5. Utilisez les mappages indiqués dans le *tableau 1*. Journal Analytique ajoutera automatiquement le ** \_trésorerie** lorsque vous définissez le nouveau champ de chaîne.

> [!IMPORTANT]
> N’oubliez pas que tous les champs JSON et journal Analytique respectent la casse.
> 
> Attention aux requêtes requis pour chaque champ personnalisé dans le tableau ci-dessous. Vous devez utiliser les requêtes corrects de journal Analytique pour extraire des valeurs de champ personnalisé avec succès.
> 
 ![Définition de champ personnalisé] (../media/Deploy-Azure-Monitor-5.png "Définition de champ personnalisé")

**Le tableau 1**

| **Champ JSON**                   | **Ouvrez une session de champ personnalisé Analytique** | **ID d’événement** | **Requête à utiliser par l’extraction**                   |
|:---------------------------------|:-------------------------------|:-------------|:-------------------------------------------------------|
| Description                      | SRSEventDescription         | **2000**     | Événement \| Source où == « SRS-App » et ID d’événement == 2000 |
| ResourceState                    | SRSResourceState            | **2000**     | Événement \| Source où == « SRS-App » et ID d’événement == 2000 |
| OperationName                    | SRSOperationName            | **2000**     | Événement \| Source où == « SRS-App » et ID d’événement == 2000 |
| OperationResult                  | SRSOperationResult          | **2000**     | Événement \| Source où == « SRS-App » et ID d’événement == 2000 |
| OS                               | SRSOSVersion                | **2000**     | Événement \| Source où == « SRS-App » et ID d’événement == 2000 |
| OSVersion                        | SRSOSLongVersion            | **2000**     | Événement \| Source où == « SRS-App » et ID d’événement == 2000 |
| Alias                            | SRSAlias                    | **2000**     | Événement \| Source où == « SRS-App » et ID d’événement == 2000 |
| DisplayName                      | SRSDisplayName              | **2000**     | Événement \| Source où == « SRS-App » et ID d’événement == 2000 |
| AppVersion                       | SRSAppVersion               | **2000**     | Événement \| Source où == « SRS-App » et ID d’événement == 2000 |
| IPv4Address                      | SRSIPv4Address              | **2000**     | Événement \| Source où == « SRS-App » et ID d’événement == 2000 |
| IPv6Address                      | SRSIPv6Address              | **2000**     | Événement \| Source où == « SRS-App » et ID d’événement == 2000 |
| État de Microphone de conférence     | SRSConfMicrophoneStatus     | **3001**     | Événement \| Source où == « SRS-App » et ID d’événement == 3001 |
| État de haut-parleur de conférence        | SRSConfSpeakerStatus        | **3001**     | Événement \| Source où == « SRS-App » et ID d’événement == 3001 |
| Haut-parleur statut par défaut           | SRSDefaultSpeakerStatus     | **3001**     | Événement \| Source où == « SRS-App » et ID d’événement == 3001 |
| État de l’appareil photo                    | SRSCameraStatus             | **3001**     | Événement \| Source où == « SRS-App » et ID d’événement == 3001 |
| Avant de l’état d’affichage de la salle     | SRSFORDStatus               | **3001**     | Événement \| Source où == « SRS-App » et ID d’événement == 3001 |
| État de détecteur de mouvement             | SRSMotionSensorStatus       | **3001**     | Événement \| Source où == « SRS-App » et ID d’événement == 3001 |
| État d’acquisition HDMI               | SRSHDMIIngestStatus         | **3001**     | Événement \| Source où == « SRS-App » et ID d’événement == 3001 |


## <a name="define-the-microsoft-teams-rooms-views-in-log-analytics"></a>Définir les affichages de salles d’équipes Microsoft dans le journal Analytique
<a name="Define_Views"> </a>

Une fois la collecte des données et des champs personnalisés sont mappées, vous pouvez utiliser le Concepteur de vues pour développer un tableau de bord contenant des mosaïques différentes pour surveiller les événements de salles d’équipes Microsoft. Utilisez le concepteur de vues pour créer les mosaïques suivantes. Pour plus d’informations, voir [créer des affichages personnalisés à l’aide du Concepteur de vues dans le journal Analytique](https://docs.microsoft.com/azure/azure-monitor/platform/view-designer)

> [!NOTE]
> Les étapes précédentes dans ce guide doivent être effectuées pour les mosaïques de tableau de bord fonctionnent correctement.

### <a name="create-a-microsoft-teams-rooms-dashboard-by-using-the-import-method"></a>Créer un tableau de bord Microsoft équipes salles à l’aide de la méthode d’importation

Vous pouvez importer un tableau de bord Microsoft équipes salles et démarrer l’analyse de vos périphériques rapidement. Procédez comme suit pour importer le tableau de bord :

1.  Obtenez le fichier de tableau de bord [SkypeRoomSystems_v2.omsview](https://go.microsoft.com/fwlink/?linkid=835675) .
2.  Connectez-vous au [portail Microsoft Azure](https://portal.azure.com) et accédez au journal Analytique et sélectionnez votre espace de travail.
3.  Ouvrez le **Concepteur de vues**.
4.  Sélectionnez **Importer**, puis sélectionnez le fichier **SkypeRoomSystems_v2.omsview** .
5.  Cliquez sur **Enregistrer**.

### <a name="create-a-microsoft-teams-rooms-dashboard-manually"></a>Créer un tableau de bord Microsoft équipes salles manuellement

Vous pouvez également créer votre propre tableau de bord et ajouter uniquement les mosaïques que vous souhaitez analyser.

#### <a name="configure-the-overview-tile"></a>Configurer la vignette de vue d’ensemble

1.  Ouvrez le **Concepteur de vues**.
2.  Sélectionnez la **Vignette de vue d’ensemble**et sélectionnez à partir de la galerie de **deux nombres** .
3.  Nom de la mosaïque **Salles d’équipes Microsoft**.
4.  Définir la **première mosaïque**:<br>
    **Légende :** Périphériques qui a envoyé une pulsation au moins une fois depuis le mois dernier<br>
    **Requête :**```Event | where EventLog == "Skype Room System" and TimeGenerated > ago(30d) | summarize TotalSRSDevices = dcount(Computer)```
5.  Définir la **deuxième mosaïque**:<br>
    **Légende :** Dispositifs actifs qui a envoyé une pulsation au sein de la dernière heure<br>
    **Requête :**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(1h) | summarize TotalSRSDevices = dcount(Computer)```
6.  Sélectionnez **Appliquer**.

### <a name="create-a-tile-that-displays-active-devices"></a>Créer une mosaïque qui affiche les périphériques actives

1.  Sélectionnez **Afficher le tableau de bord** à ajouter votre mosaïques.
2.  Sélectionnez **numéro & liste** dans la galerie
3.  Définir les propriétés **générales** :<br>
    **Titre de groupe :** État de pulsation<br>
    **Nouveau groupe :** Sélectionné
4.  Définissez les propriétés de **Mosaïque** :<br>
    **Légende :** Dispositifs actifs (pulsation envoyée dans les 20 dernières minutes)<br>
    **Requête de mosaïque : ** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize AggregatedValue = count() by Computer | count```
5.  Définissez les propriétés de **liste** :<br>
    **Requête de liste :**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
6.  Définir les **titres des colonnes**:<br>
    **Nom :** Nom de l’ordinateur<br>
    **Valeur :** Dernière pulsation
7.  Définir la **requête de Navigation**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  Sélectionnez **Appliquer**, puis sur **Fermer**.

### <a name="create-a-tile-that-displays-devices-that-have-connectivity-issues"></a>Créer une mosaïque qui affiche les périphériques qui ont des problèmes de connectivité

1.  Sélectionnez **numéro & liste** dans la galerie, puis ajoutez une nouvelle mosaïque.
2.  Définir les propriétés **générales** :<br>
    **Titre de groupe :** Laissez vide<br>
    **Nouveau groupe :** Non sélectionnée
3.  Définissez les propriétés de **Mosaïque** :<br>
    **Légende :** Périphériques inactifs (aucun message heartbeat envoyé dans les 20 dernières minutes)<br>
    **Requête de mosaïque : ** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize LastHB = max(TimeGenerated) by Computer | where LastHB < ago(20m) | count```
4.  Définissez les propriétés de **liste** :<br>
    **Requête de liste :**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize TimeGenerated = max(TimeGenerated) by Computer | where TimeGenerated < ago(20m) | order by TimeGenerated```
5.  Définir les **titres des colonnes**:<br>
    **Nom :** Nom de l’ordinateur<br>
    **Valeur :** Dernière pulsation
6.  Définir la **requête de Navigation**:<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
7.  Sélectionnez **Appliquer**, puis sur **Fermer**.

### <a name="create-a-tile-that-displays-devices-that-have-a-hardware-error"></a>Créer une mosaïque qui affiche les périphériques qui ont une erreur matérielle

1.  Sélectionnez **numéro & liste** dans la galerie, puis ajoutez une nouvelle mosaïque.
2.  Définir les propriétés **générales** :<br>
    **Titre de groupe :** État du matériel<br>
    **Nouveau groupe :** Sélectionné
3.  Définissez les propriétés de **Mosaïque** :<br>
    **Légende :** Périphériques qui a rencontré une erreur matérielle dans la dernière heure<br>
    **Requête de mosaïque : ** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```
4.  Définissez les propriétés de **liste** :<br>
    **Requête de liste :**```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
5.  Définir les **titres des colonnes**:<br>
    **Nom :** Nom de l’ordinateur<br>
    **Valeur :** Dernière erreur
6.  Définir la **requête de Navigation**:<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == 3001 and EventLevelName == "Error" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSConfMicrophoneStatus_CF, SRSConfSpeakerStatus_CF, SRSDefaultSpeakerStatus_CF, SRSCameraStatus_CF, SRSFORDStatus_CF, SRSMotionSensorStatus_CF, SRSHDMIIngestStatus_CF, SRSEventDescription_CF | sort by TimeGenerated desc```
7.  Sélectionnez **Appliquer**, puis sur **Fermer**.

### <a name="create-a-tile-that-displays-microsoft-teams-rooms-operating-system-versions"></a>Créer une mosaïque qui affiche les versions du système d’exploitation de Microsoft équipes salles

1.  Sélectionnez **liste de & café** à partir de la galerie, puis ajoutez une nouvelle mosaïque.
2.  Définir les propriétés **générales** :<br>
    **Titre de groupe :** Détails du système d’exploitation<br>
    **Nouveau groupe :** Sélectionné
3.  Définir les propriétés **d’en-tête** :<br>
    **Titre :** Versions de système d’exploitation<br>
    **Sous-titre :** Appareils exécutant des versions spécifiques du système d’exploitation
4.  Définissez les propriétés de **l’anneau** :<br>
    **Requête :**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize OS_Version = max(SRSOSLongVersion_CF) by Computer | summarize AggregatedValue = count() by OS_Version | sort by OS_Version asc```<br>
    **Centre le texte :** Périphériques<br>
    **Opération :** Somme
5.  Définir les propriétés de la **liste** .<br>
    **Requête de liste :**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSOSLongVersion_CF = max(SRSOSLongVersion_CF) by Computer | sort by Computer asc```<br>
    **Masquer graphique :** Sélectionné<br>
    **Activer les graphiques sparkline :** Non sélectionnée
6.  Définir les **titres des colonnes**.<br>
    **Nom :** Nom de l’ordinateur<br>
    **Valeur :** Laissez vide
7.  Définir la **requête de Navigation**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSDisplayName_CF, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  Sélectionnez **Appliquer** , puis sur **Fermer**.

### <a name="create-a-tile-that-displays-microsoft-teams-rooms-application-versions"></a>Créer une mosaïque qui affiche les versions de l’application Microsoft équipes salles

1.  Sélectionnez **liste de & café** à partir de la galerie, puis ajoutez une nouvelle mosaïque.
2.  Définir les propriétés **générales** :<br>
    **Titre de groupe :** Détails de l’application Microsoft équipes salles<br>
    **Nouveau groupe :** Sélectionné
3.  Définir les propriétés **d’en-tête** :<br>
    **Titre :** Versions de l’application<br>
    **Sous-titre :** Appareils exécutant des versions des applications spécifiques
4.  Définissez les propriétés de **l’anneau** :<br>
    **Requête :**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize App_Version = max(SRSAppVersion_CF) by Computer | summarize AggregatedValue = count() by App_Version | sort by App_Version asc```<br>
    **Centre le texte :** Périphériques<br>
    **Opération :** Somme
5.  Définir les propriétés de la **liste** .<br>
    **Requête de liste :**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSAppVersion_CF = max(SRSAppVersion_CF) by Computer | sort by Computer asc```<br>
    **Masquer graphique :** Sélectionné<br>
    **Activer les graphiques sparkline :** Non sélectionnée
6.  Définir les **titres des colonnes**.<br>
    **Nom :** Nom de l’ordinateur<br>
    **Valeur :** Laissez vide
7.  Définir la **requête de Navigation**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  Sélectionnez **Appliquer** , puis sur **Fermer**.

### <a name="create-a-tile-that-displays-devices-that-have-an-application-error"></a>Créer une mosaïque qui affiche les périphériques qui ont une erreur d’application

1.  Sélectionnez **numéro & liste** dans la galerie, puis ajoutez une nouvelle mosaïque.
2.  Définir les propriétés **générales** .<br>
    **Titre de groupe :** Laissez vide<br>
    **Nouveau groupe :** Non sélectionnée
3.  Définir les propriétés de **Mosaïque** .<br>
    **Légende :** Périphériques qui a rencontré une erreur d’application dans la dernière heure<br>
    **Requête de mosaïque : ** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```
4.  Définir les propriétés de la **liste** .<br>
    **Requête de liste :**```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
5.  Définir les **titres des colonnes**.<br>
    **Nom :** Nom de l’ordinateur<br>
    **Valeur :** Dernière erreur
6.  Définir la **requête de Navigation**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == 2001 and EventLevelName == "Error" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF | sort by TimeGenerated desc```
7.  Sélectionnez **Appliquer** , puis sur **Fermer**.

### <a name="create-a-tile-that-displays-devices-that-have-been-restarted"></a>Créer une mosaïque qui affiche les périphériques qui ont été redémarrés.

1.  Sélectionnez **numéro & liste** dans la galerie, puis ajoutez une nouvelle mosaïque.
2.  Définir les propriétés **générales** .<br>
    **Titre de groupe :** Laissez vide<br>
    **Nouveau groupe :** Non sélectionnée
3.  Définir les propriétés de **Mosaïque** .<br>
    **Légende :** Périphériques où l’application a été redémarrée dans la dernière 24 heures, nombre de redémarrages<br>
    **Requête de mosaïque : ** ```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | summarize AggregatedValue = count() by Computer | count```
4.  Définir les propriétés de la **liste** .<br>
    **Requête de liste :**```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | order by TimeGenerated | summarize AggregatedValue = count(EventID) by Computer```
5.  Définir les **titres des colonnes**.<br>
    **Nom :** Nom de l’ordinateur<br>
    **Valeur :** Nombre de redémarrages
6.  Définir la **requête de Navigation**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
7.  Sélectionnez **Appliquer** , puis sur **Fermer**.
8.  Sélectionnez **Enregistrer** pour enregistrer votre tableau de bord.

Maintenant, vous avez terminé la création de votre vues.

## <a name="configure-alerts-in-azure-monitor"></a>Configurer les alertes dans le moniteur Azure
<a name="Alerts"> </a>

Moniteur Azure peut générer des alertes pour avertir les administrateurs lorsqu’une console Microsoft équipes salles rencontre un problème.

Moniteur Azure inclut un mécanisme d’alerte qui s’exécute par le biais de recherches de journal planifiées à intervalles réguliers. Si les résultats de la recherche du journal correspond à certains critères particuliers, un enregistrement de l’alerte est créé.

La règle peut exécuter automatiquement une ou plusieurs actions pour vous informer de l’alerte proactive ou d’appeler un autre processus. Les options des alertes possibles sont les suivants :
-   Envoyer un message électronique
-   Appel d’un processus externe via une demande HTTP POST
-   Une procédure opérationnelle à compter d’Azure Automation Services

Consultez [consignent les alertes dans le moniteur Azure](https://docs.microsoft.com/azure/azure-monitor/platform/alerts-unified-log) pour en savoir plus sur les alertes dans le moniteur Azure.

> [!NOTE]
> Les exemples suivants envoient des alertes par courrier électronique lorsqu’un périphérique Microsoft équipes salles génère un matériel ou une erreur d’application.

### <a name="configure-an-email-alert-for-microsoft-teams-rooms-hardware-issues"></a>Configurer un message d’alerte pour les problèmes matériels de salles d’équipes Microsoft

Configurer une règle qui vérifie les appareils Microsoft équipes salles qui ont rencontré des problèmes liés au matériel au sein de la dernière heure d’alerte.
1.  Connectez-vous au [portail Microsoft Azure](https://portal.azure.com) et accédez au journal Analytique et sélectionnez votre espace de travail.

2. Accédez à votre espace de travail de journal Analytique puis sélectionnez **alertes** et sélectionnez **nouvelle règle d’alerte**

3. Sélectionnez **Ajouter une condition** , puis **recherche dans un journal personnalisé**

4.  Entrez la requête suivante pour la zone de texte de requête de recherche.<br>
    ```
    Event
    | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h)
    | summarize arg_max(TimeGenerated, *) by Computer
    | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSConfMicrophoneStatus_CF, SRSConfSpeakerStatus_CF, SRSDefaultSpeakerStatus_CF, SRSCameraStatus_CF, SRSFORDStatus_CF, SRSMotionSensorStatus_CF, SRSHDMIIngestStatus_CF, SRSEventDescription_CF
    |sort by TimeGenerated desc
    ```

5.  Configurer les paramètres de la logique de l’alerte :<br>
    **Selon :** Nombre de résultats<br>
    **Condition :** Supérieure<br>
    **Seuil :** 0<br>

6. Configurer les paramètres d’évaluation, puis sélectionnez **terminé**: <br>
    **Période (en minutes) :** 60<br>
    **Fréquence (en minutes) :** 60<br>

7. Configurer des groupes d’actions :
    1.  Sélectionnez **créer une nouvelle**
    2.  Fournir des noms appropriés pour les champs *nom de groupe l’Action* et le *Nom court* .
    3.  Spécifiez un *Nom de l’Action* unique et sélectionnez **E-mail/SMS/Push/voix**, puis sélectionnez **Modifier les détails**.
    4.  Activez la case à cocher courrier électronique et fournir l’adresse de messagerie de la personne ou du groupe qui recevra les alertes.
    5.  Vous pouvez également indiquer votre numéro de téléphone pour recevoir un avertissement avec SMS, un appel vocal ou les deux.
    6. Sélectionnez **OK**.

8. **Personnaliser les Actions** si vous souhaitez remplacer la ligne d’objet des e-mails de l’alerte.

9. Spécifiez un nom de la règle et une description.<br>
    **Nom de règle :** Les équipes Microsoft salles d’alerte de défaillance matérielle<br>
    **Description :** Liste des périphériques qui a rencontré un problème de matériel au sein de la dernière heure<br>

10. Sélectionnez la gravité concernée et assurez-vous que la règle est activée.

11. Sélectionnez **créer une règle d’alerte**.

### <a name="configure-an-email-alert-for-microsoft-teams-rooms-application-issues"></a>Configurer un message d’alerte pour les problèmes des applications Microsoft équipes salles

Répétez la même procédure, mais utilisez la requête suivante pour les périphériques qui ont rencontré des problèmes des applications au sein de la dernière heure.

    ```
    Event
    | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h)
    | summarize arg_max(TimeGenerated, *) by Computer
    | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF
    | sort by TimeGenerated desc
    ```

Maintenant vous avez terminé la définition des alertes. Vous pouvez définir des alertes supplémentaires à l’aide de l’exemple ci-dessus.

Lorsqu’une alerte est générée, vous obtiendrez un message électronique qui répertorie les périphériques qui a rencontré un problème au sein de la dernière heure.

![Moniteur d’Azure exemple de courrier électronique d’alerte] (../media/Deploy-Azure-Monitor-6.png "Moniteur d’Azure exemple de courrier électronique d’alerte")

## <a name="configure-all-devices-for-azure-monitoring"></a>Configurer tous les périphériques pour la surveillance d’Azure
<a name="configure_all_devices"></a> Après les tableaux de bord et les alertes sont configurés, vous pouvez installer et configurer Monitoring Microsoft agent sur tous les périphériques de salles d’équipes Microsoft pour effectuer votre déploiement de surveillance.

Bien que vous pouvez installer et configurer l’agent Microsoft Monitoring manuellement sur chaque périphérique, nous vous recommandons vivement de que vous tirer parti des méthodes et des outils de déploiement de logiciels existants.

Si vous créez vos périphériques salles d’équipes Microsoft pour la première fois, vous souhaitez inclure les étapes du programme d’installation et configuration de l’agent Microsoft Monitoring dans le cadre de votre processus de génération. Pour plus d’informations, consultez [installation de l’agent à l’aide de la ligne de commande](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows#install-the-agent-using-the-command-line).

### <a name="deploying-microsoft-monitoring-agent-by-using-a-group-policy-object-gpo"></a>Déploiement de l’agent Monitoring Microsoft à l’aide d’un objet de stratégie de groupe (GPO)

Si vous déjà déployé vos périphériques Microsoft équipes salles avant d’implémenter Azure surveillance, vous pouvez utiliser le script fourni pour installer et configurer les agents à l’aide des objets de stratégie de groupe Active Directory.

1.  Créer un chemin d’accès réseau partagé et accorder un accès en lecture au groupe **d’Ordinateurs du domaine** .

2.  Télécharger la version 64 bits de Microsoft surveillance Agent pour Windows à partir de<https://go.microsoft.com/fwlink/?LinkID=517476>

3.  Extrayez le contenu du package du programme d’installation dans le partage réseau.
    1.  Ouvrez une fenêtre d’invite de commandes et l’exécuter **/c MMASetup-AMD64.exe**
    2.  Spécifiez le partage que vous venez de créer et extraire le contenu.

4.  Créer un nouvel objet de stratégie de groupe et l’affecter à l’unité d’organisation où se trouvent les comptes d’ordinateur salles d’équipes Microsoft.

5.  Configurer la stratégie d’exécution PowerShell :
    1.  Modifier l’objet de stratégie de groupe nouvellement créé et accédez à Configuration de l’ordinateur \\ stratégies \\ modèles d’administration \\ composants Windows \\ Windows PowerShell
    2.  Activer l' **Activer l’exécution du Script** et définir la **Stratégie d’exécution** pour **Autoriser les Scripts locaux**.

6.  Configurer le script de démarrage :
    1.  Copiez le script suivant et enregistrez-le sous MMAgent.ps1-Install.
    2.  Modifier les paramètres WorkspaceId, WorkspaceKey et SetupPath correspondant à votre configuration.
    3.  Modifier le même objet de stratégie de groupe et accédez à Configuration de l’ordinateur \\ stratégies \\ paramètres Windows \\ Scripts (démarrage/arrêt)
    4.  Cliquez deux fois sur **démarrage**, puis sélectionnez **Scripts PowerShell**.
    5.  Sélectionnez **Afficher les fichiers**, puis copiez le fichier **Install-MMAgent.ps1** à ce dossier.
    6.  Sélectionnez **Ajouter**, puis **Parcourir**.
    7.  Sélectionnez le script ps1 que vous venez de copier.

7.  Périphériques de salles d’équipes Microsoft doivent installer et configurer l’agent Microsoft Monitoring du deuxième redémarrage.

```
# Install-MMAgent.ps1
<#
Date:        04/20/2018
Script:      Install-MMAgent.ps1
Version:     1.0
#>

# Set the parameters
$WorkspaceId = "<your workspace id>"
$WorkspaceKey = "<your workspace key>"
$SetupPath = "\\Server\Share"

$SetupParameters = "/qn NOAPM=1 ADD_OPINSIGHTS_WORKSPACE=1 OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE=0 OPINSIGHTS_WORKSPACE_ID=$WorkspaceId OPINSIGHTS_WORKSPACE_KEY=$WorkspaceKey AcceptEndUserLicenseAgreement=1"

# $SetupParameters = $SetupParameters + " OPINSIGHTS_PROXY_URL=<Proxy server URL> OPINSIGHTS_PROXY_USERNAME=<Proxy server username> OPINSIGHTS_PROXY_PASSWORD=<Proxy server password>"

# Start PowerShell logging
Start-Transcript -Path C:\Temp\MMA-Install.Log

# Check if the Microsoft Monitoring Agent is installed
$mma = New-Object -ComObject 'AgentConfigManager.MgmtSvcCfg'

# Check if the Microsoft Monitoring agent is installed
if (!$mma)
{
    #Install agent
    Start-Process -FilePath "$SetupPath\Setup.exe" -ArgumentList $SetupParameters -ErrorAction Stop -Wait
}

# Check if the agent has a valid configuration
$CheckMMA = $mma.GetCloudWorkspace($WorkspaceId).AgentId
if (!$CheckMMA)
{
    # Apply new configuration
    $mma.AddCloudWorkspace($WorkspaceId, $WorkspaceKey)
    $mma.ReloadConfiguration()
}

Stop-Transcript
```

> [!NOTE]
> Vous pouvez faire référence à l’article [gestion et maintenance de l’agent de journal Analytique](https://docs.microsoft.com/azure/azure-monitor/platform/agent-manage) lorsque vous devez reconfigurer un agent, déplacer vers un autre espace de travail ou modifier les paramètres de proxy après l’installation initiale.

## <a name="additional-solutions"></a>Autres Solutions
<a name="Solutions"> </a>

Moniteur Azure fournit des solutions de gestion intégrés par le biais de son [Galerie de solutions](https://docs.microsoft.com/azure/azure-monitor/insights/solutions) pour vous aider analyser votre environnement. Il est vivement recommandé d’ajouter des solutions de [Gestion des alertes](https://docs.microsoft.com/azure/azure-monitor/platform/alert-management-solution) et [L’intégrité des agents Azure journal Analytique](https://docs.microsoft.com/azure/azure-monitor/insights/solution-agenthealth) à votre espace de travail.

> [!NOTE]
> La solution de l’intégrité des agents peut vous aider à identifier des agents de Microsoft Monitoring obsolètes ou interrompus dans votre environnement, et la solution de gestion de l’alerte fournit plus d’informations sur les alertes qui ont été déclenchés dans une période donnée.

## <a name="see-also"></a>Voir aussi

[Planifier la gestion des salles d’équipes Microsoft Azure moniteur](azure-monitor-plan.md)

[Gérer les périphériques de salles d’équipes Microsoft Azure moniteur](azure-monitor-manage.md)