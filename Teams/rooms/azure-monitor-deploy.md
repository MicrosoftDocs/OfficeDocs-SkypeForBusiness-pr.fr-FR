---
title: Déployer l Salles Microsoft Teams de surveillance des données à l’Salles Microsoft Teams Azure Monitor
ms.author: czawideh
author: cazawideh
ms.reviewer: Turgayo
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
ms.assetid: d86ff657-ee92-4b06-aee3-d4c43090bdcb
description: Cet article décrit le déploiement de la surveillance des Salles Microsoft Teams de bout en bout à l’aide d’Azure Monitor.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: b991465bfff8f67fdbd3bdc9c03eba485690d5fb
ms.sourcegitcommit: a894e9397050e09bfaab02e700e943a3bbeb1302
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/15/2022
ms.locfileid: "63503871"
---
# <a name="deploy-no-loc-textmicrosoft-teams-rooms-monitoring-with-no-loc-textazure-monitor"></a>Surveillance du :::no-loc text="Microsoft Teams Rooms"::: déploiement avec :::no-loc text="Azure Monitor":::

Cet article décrit la mise en place et le déploiement intégrés d’une surveillance de bout en bout :::no-loc text="Microsoft Teams Rooms"::: des appareils à l’aide :::no-loc text="Azure Monitor":::.

Vous pouvez configurer dans afin :::no-loc text="Log Analytics"::: de fournir :::no-loc text="Azure Monitor"::: des alertes et des données de télémétrie de base qui vous aideront à gérer :::no-loc text="Microsoft Teams Rooms":::. À mesure que votre solution de gestion mature, vous pouvez décider de déployer des données et des fonctionnalités de gestion supplémentaires afin de créer une vue plus détaillée de la disponibilité et des performances de l’appareil.

En suivant ce guide, vous pouvez utiliser un tableau de bord comme celui-ci pour obtenir des rapports d’état détaillés sur la disponibilité des appareils, l’état des applications et du matériel, :::no-loc text="Microsoft Teams Rooms"::: ainsi que la distribution des versions des applications et des systèmes d’exploitation.

![Capture d’écran de l’affichage Analyse des journaux d Salles Microsoft Teams.](../media/Deploy-Azure-Monitor-1.png "Exemple d’affichage Analyse des journaux pour Salles Microsoft Teams")

À haut niveau, vous devez effectuer les tâches suivantes :


1. [Valider la :::no-loc text="Log Analytics"::: configuration](azure-monitor-deploy.md#validate_LogAnalytics)
2. [Configurer des périphériques de test pour la configuration :::no-loc text="Log Analytics"::: de la gestion](azure-monitor-deploy.md#configure_test_devices)
3. [Mapper les champs personnalisés](azure-monitor-deploy.md#Custom_fields)
4. [Définir les affichages :::no-loc text="Microsoft Teams Rooms"::: dans :::no-loc text="Log Analytics":::](azure-monitor-deploy.md#Define_Views)
5. [Définir des alertes](azure-monitor-deploy.md#Alerts)
6. [Configurer tous les appareils pour la surveillance](azure-monitor-deploy.md#configure_all_devices)
7. [Configurer des solutions supplémentaires :::no-loc text="Azure Monitor":::](azure-monitor-deploy.md#Solutions)

> [!IMPORTANT]
> Bien qu’avec une configuration minimale, :::no-loc text="Azure Monitor"::: :::no-loc text="Log Analytics"::: :::no-loc text="Windows"::: vous pouvez surveiller un ordinateur exécutant un système d’exploitation, :::no-loc text="Microsoft Teams Rooms":::il reste encore quelques étapes –spécifiques à suivre avant de commencer à déployer des agents sur tous les :::no-loc text="Microsoft Teams Rooms"::: appareils.
> Par conséquent, nous vous recommandons vivement d’effectuer toutes les étapes de configuration dans le bon ordre pour une configuration et une configuration contrôlées. La qualité du résultat final dépend beaucoup de la qualité de la configuration initiale.

## <a name="validate-no-loc-textlog-analytics-configuration"></a>Valider la :::no-loc text="Log Analytics"::: configuration
<a name="validate_LogAnalytics"> </a>

Vous devez avoir un espace de :::no-loc text="Log Analytics"::: travail à partir d’où commencer la collecte des journaux :::no-loc text="Microsoft Teams Rooms":::. Un espace de travail est un environnement unique :::no-loc text="Log Analytics"::: avec son propre référentiel de données, ses sources de données et ses solutions. Si vous avez déjà :::no-loc text="Log Analytics"::: un espace de travail existant, :::no-loc text="Microsoft Teams Rooms"::: :::no-loc text="Log Analytics"::: :::no-loc text="Microsoft Teams Rooms"::: vous pouvez l’utiliser pour surveiller votre déploiement ou créer un espace de travail dédié spécifique à vos besoins de surveillance.

Si vous avez besoin de créer un espace :::no-loc text="Log Analytics"::: de travail, suivez les instructions de l’article Créer [un :::no-loc text="Log Analytics"::: espace de travail dans le :::no-loc text="Azure"::: portail](/azure/azure-monitor/learn/quick-create-workspace)

> [!NOTE]
> Pour l’utiliser :::no-loc text="Log Analytics"::: :::no-loc text="Azure Monitor":::, vous devez avoir un abonnement :::no-loc text="Azure"::: actif. Si vous n’avez pas d’abonnement :::no-loc text="Azure"::: , vous pouvez créer un [abonnement](https://azure.microsoft.com/free) d’essai gratuit comme point de départ.

### <a name="configure-no-loc-textlog-analytics-to-collect-no-loc-textmicrosoft-teams-rooms-event-logs"></a>Configurer la collecte :::no-loc text="Log Analytics"::: des journaux :::no-loc text="Microsoft Teams Rooms"::: d’événements

:::no-loc text="Log Analytics"::: collecte uniquement les événements à partir des :::no-loc text="Windows"::: journaux des événements spécifiés dans les paramètres. Pour chaque journal, seuls les événements dont la gravité est sélectionnée sont collectés.

Vous devez configurer pour collecter les :::no-loc text="Log Analytics"::: journaux requis pour surveiller :::no-loc text="Microsoft Teams Rooms"::: l’état de l’appareil et de l’application. :::no-loc text="Microsoft Teams Rooms"::: utilisez le journal des **:::no-loc text="Skype Room System":::** événements.

Pour configurer la collecte :::no-loc text="Log Analytics"::: des événements :::no-loc text="Microsoft Teams Rooms"::: , consultez les [:::no-loc text="Windows"::: sources de données du journal des événements dans :::no-loc text="Azure Monitor":::](/azure/azure-monitor/platform/data-sources-windows-events)

![Capture d’écran des paramètres du journal des événements.](../media/Deploy-Azure-Monitor-2.png "Paramètres du journal des événements")

> [!IMPORTANT]
> Configurez les paramètres :::no-loc text="Windows"::: du journal des événements et entrez le nom du journal des événements **:::no-loc text="Skype Room System":::**, puis cochez les cases **Erreur, Avertissement** et Informations.

## <a name="configure-test-devices-for-azure-monitoring"></a>Configurer des périphériques de test pour Azure Monitoring
<a name="configure_test_devices"> </a>

Vous devez vous préparer à :::no-loc text="Log Analytics"::: être en mesure de surveiller les événements :::no-loc text="Microsoft Teams Rooms":::–associés. Pour commencer, vous :::no-loc text="Microsoft Monitoring"::: devez déployer des agents :::no-loc text="Microsoft Teams Rooms"::: sur un ou deux appareils à qui vous avez accès physique, et obtenir ces périphériques de test :::no-loc text="Log Analytics"::: pour générer des données et les pousser vers l’espace de travail.

### <a name="install-no-loc-textmicrosoft-monitoring-agents-to-test-devices"></a>Installer des :::no-loc text="Microsoft Monitoring"::: agents sur les appareils de test

Déployez l’agent :::no-loc text="Microsoft Monitoring"::: sur les périphériques de test en utilisant les instructions fournies [Connecter :::no-loc text="Windows"::: des ordinateurs sur le :::no-loc text="Log Analytics"::: service dans :::no-loc text="Azure":::](/azure/azure-monitor/platform/agent-windows). Cet article :::no-loc text="Microsoft Monitoring"::: fournit des informations détaillées sur les étapes à suivre pour déployer l’Agent:::no-loc text="Windows":::, des instructions pour obtenir **l’ID** de l’espace de travail et la _ *_primary key_** :::no-loc text="Microsoft Teams Rooms"::: :::no-loc text="Azure Monitor"::: pour connecter les appareils à votre déploiement, et des instructions :::no-loc text="Log Analytics"::: * pour vérifier la connectivité de l’agent :::no-loc text="Log Analytics"::: à une instance.

### <a name="generate-sample-no-loc-textmicrosoft-teams-rooms-events"></a>Générer des exemples d’événements :::no-loc text="Microsoft Teams Rooms":::

Une fois :::no-loc text="Microsoft Monitoring"::: l’agent déployé sur les appareils de test, vérifiez que les données requises du journal des événements sont collectées par :::no-loc text="Azure Monitor":::.

> [!NOTE]
> Redémarrez l’appareil après l’installation :::no-loc text="Microsoft Monitoring"::: de l’agent et :::no-loc text="Microsoft Teams Rooms"::: assurez-vous que l’application Réunion est démarrée afin qu’elle puisse générer de nouveaux événements dans le journal des événements.

1.  Connectez-vous au [portail:::no-loc text="Microsoft Azure":::,](https://portal.azure.com) puis sélectionnez :::no-loc text="Log Analytics"::: votre espace de travail.

2.  Énumérer les événements de pulsation générés par un :::no-loc text="Microsoft Teams Rooms"::: appareil :
    1.  Sélectionnez votre espace de travail, puis allez dans Journaux et utilisez une requête pour extraire les enregistrements de pulsation qui auront les champs **personnalisés** pour :::no-loc text="Microsoft Teams Rooms":::.
    2.  Exemple de requête : `Event | where Source == "SRS-App" and EventID == 2000`

3.  Assurez-vous que la requête renvoie des enregistrements journaux qui incluent des événements générés par l’application :::no-loc text="Microsoft Teams Rooms"::: Réunions.

4.  Générer un problème matériel et vérifier que les événements requis sont connectés :::no-loc text="Azure Log Analytics":::.
    1.  Débranchez l’un des périphériques sur le système de test :::no-loc text="Microsoft Teams Rooms"::: . Cela peut être l’affichage de la caméra, du haut-parleur, du microphone ou de la salle avant
    2.  Attendez 10 minutes que le journal des événements soit rempli :::no-loc text="Azure Log Analytics":::.
    3.  Utilisez une requête pour lister les événements d’erreurs matérielles : `Event | where Source == "SRS-App" and EventID == 3001`

5.  Générez un problème d’application et validez que les événements requis sont enregistrés.
    1.  Modifiez :::no-loc text="Microsoft Teams Rooms"::: la configuration du compte et tapez une paire e-mail/mot de passe incorrecte.
    2.  Attendez 10 minutes que le journal des événements soit rempli :::no-loc text="Azure Log Analytics":::.
    3.  Utilisez une requête pour lister les événements d’erreur d’application : `Event | where Source == "SRS-App" and EventID == 2001 and EventLevel == 1`

> [!IMPORTANT]
> Ces exemples de journaux d’événements sont requis pour que les champs personnalisés soient configurés. Ne pas passer à l’étape suivante tant que vous n’avez pas collecté les journaux des événements requis.

## <a name="map-custom-fields"></a>Mapper les champs personnalisés
<a name="Custom_fields"> </a>

Les champs personnalisés vous sont utilisés pour extraire des données spécifiques des journaux des événements. Vous devez définir des champs personnalisés qui seront utilisés ultérieurement avec vos vignettes, vues de tableau de bord et alertes. [Consultez les champs personnalisés :::no-loc text="Log Analytics":::](/azure/azure-monitor/platform/custom-fields) et familiarisez-vous avec les concepts avant de commencer à créer vos champs personnalisés.

Pour extraire vos champs personnalisés des journaux des événements capturés, suivez ces étapes :

1.  Connectez-vous au [portail:::no-loc text="Microsoft Azure":::,](https://portal.azure.com) puis sélectionnez :::no-loc text="Log Analytics"::: votre espace de travail.

2. Listez les événements générés par un :::no-loc text="Microsoft Teams Rooms"::: appareil :
   1.  Allez dans **Journaux** et utilisez une requête pour récupérer les enregistrements qui auront le champ personnalisé.
   2.  Exemple de requête : `Event | where Source == "SRS-App" and EventID == 2000`

3. Sélectionnez l’un des enregistrements, sélectionnez le bouton à gauche et démarrez l’Assistant Extraction de champ.
4. Mettez en surbrillation les données que vous voulez extraire de la description RenderedDescription et indiquez un titre de champ. Les noms de champs que vous devez utiliser sont indiqués dans la Table 1.
5. Utilisez les mappages indiqués dans *le tableau 1*. :::no-loc text="Log Analytics":::automatiquement la chaîne CF lorsque **\_** vous définissez le nouveau champ.

> [!IMPORTANT]
> N’oubliez pas que tous les champs et :::no-loc text="Log Analytics"::: JSON sont sensibles à la cas.
> 
> Faites attention aux requêtes requises pour chaque champ personnalisé dans la table ci-dessous. Vous devez utiliser les requêtes correctes pour :::no-loc text="Log Analytics"::: extraire correctement des valeurs de champ personnalisé.
> 
**Tableau 1**

| **Champ JSON**                   | **:::no-loc text="Log Analytics"::: champ personnalisé** | **ID d’événement** | **Requête à utiliser avec l’extraction**                   |
|:---------------------------------|:-------------------------------|:-------------|:-------------------------------------------------------|
| Description                      | SRSEventDescription         | **2000**     | Événement \| dans lequel Source == « SRS-App » et EventID == 2000 |
| ResourceState                    | SRSResourceState            | **2000**     | Événement \| dans lequel Source == « SRS-App » et EventID == 2000 |
| OperationName                    | SRSOperationName            | **2000**     | Événement \| dans lequel Source == « SRS-App » et EventID == 2000 |
| OperationResult                  | SRSOperationResult          | **2000**     | Événement \| dans lequel Source == « SRS-App » et EventID == 2000 |
| OS                               | SRSOSVersion                | **2000**     | Événement \| dans lequel Source == « SRS-App » et EventID == 2000 |
| OSVersion                        | SRSOSLongVersion            | **2000**     | Événement \| dans lequel Source == « SRS-App » et EventID == 2000 |
| Alias                            | SRSAlias                    | **2000**     | Événement \| dans lequel Source == « SRS-App » et EventID == 2000 |
| DisplayName                      | SRSDisplayName              | **2000**     | Événement \| dans lequel Source == « SRS-App » et EventID == 2000 |
| AppVersion                       | SRSAppVersion               | **2000**     | Événement \| dans lequel Source == « SRS-App » et EventID == 2000 |
| IPv4Address                      | SRSIPv4Address              | **2000**     | Événement \| dans lequel Source == « SRS-App » et EventID == 2000 |
| IPv6Address                      | SRSIPv6Address              | **2000**     | Événement \| dans lequel Source == « SRS-App » et EventID == 2000 |
| État du microphone de conférence     | SRSConfMicrophoneStatus     | **3001**     | Événement \| dans lequel Source == « SRS-App » et EventID == 3001 |
| Statut du haut-parleur de conférence        | SRSConfSpeakerStatus        | **3001**     | Événement \| dans lequel Source == « SRS-App » et EventID == 3001 |
| Statut du haut-parleur par défaut           | SRSDefaultSpeakerStatus     | **3001**     | Événement \| dans lequel Source == « SRS-App » et EventID == 3001 |
| État de la caméra                    | SRSCameraStatus             | **3001**     | Événement \| dans lequel Source == « SRS-App » et EventID == 3001 |
| État d’affichage avant de la salle     | SRSFORDStatus               | **3001**     | Événement \| dans lequel Source == « SRS-App » et EventID == 3001 |
| État du capteur de mouvement             | SRSMotionSensorStatus       | **3001**     | Événement \| dans lequel Source == « SRS-App » et EventID == 3001 |
| État HDMI Ingest               | SRSHDMIIngestStatus         | **3001**     | Événement \| dans lequel Source == « SRS-App » et EventID == 3001 |


## <a name="define-the-no-loc-textmicrosoft-teams-rooms-views-in-no-loc-textlog-analytics"></a>Définir les affichages :::no-loc text="Microsoft Teams Rooms"::: dans :::no-loc text="Log Analytics":::
<a name="Define_Views"> </a>

Une fois les données collectées et les champs personnalisés mappés, vous pouvez utiliser le Concepteur de vues pour développer un tableau de bord contenant différentes vignettes pour surveiller les événements :::no-loc text="Microsoft Teams Rooms"::: . Utilisez le concepteur de vues pour créer les mosaïques suivantes. Pour plus d’informations, voir [Créer des affichages personnalisés à l’aide du Concepteur de vues dans :::no-loc text="Log Analytics":::](/azure/azure-monitor/platform/view-designer)

> [!NOTE]
> Les étapes précédentes de ce guide doivent avoir été effectuées pour que les mosaïques du tableau de bord fonctionnent correctement.
>
> [!IMPORTANT]
> Le Concepteur de vues sur l’écran Azure a été mis hors place le [31 août 2023](https://azure.microsoft.com/updates/view-designer-in-azure-monitor-is-retiring-on-31-august-2023/) et les fonctionnalités de création et d’clone ont été désactivées le 30 novembre 2020. Lesbooks peuvent être utilisés à la place. Pour plus d’informations sur le guide de transition du concepteur de vues vers les manuels, voir Démarrage rapide avec [des modèles de concepteur de vues prédéfinfins](/azure/azure-monitor/visualize/view-designer-conversion-tasks#quickstart-with-preset-view-designer-templates).

### <a name="create-a-microsoft-teams-rooms-dashboard-manually"></a>Créer un tableau Salles Microsoft Teams de bord manuellement

Vous pouvez également créer votre propre tableau de bord et ajouter uniquement les vignettes que vous souhaitez contrôler.

#### <a name="configure-the-overview-tile"></a>Configurer la vignette Vue d’ensemble

1.  **Ouvrez le Concepteur d’affichage**.
2.  **Sélectionnez Vignette vue d’ensemble**, puis **deux numéros dans** la galerie.
3.  Nommez la vignette **:::no-loc text="Microsoft Teams Rooms":::**.
4.  Définir la **première vignette** :<br>
    **Légende :** Appareils qui ont envoyé une pulsation au moins une fois au cours du mois dernier<br>
    **Requête :** ```Event | where EventLog == "Skype Room System" and TimeGenerated > ago(30d) | summarize TotalSRSDevices = dcount(Computer)```
5.  Définir la **deuxième vignette** :<br>
    **Légende :** Appareils actifs qui ont envoyé une pulsation au cours de la dernière heure<br>
    **Requête :** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(1h) | summarize TotalSRSDevices = dcount(Computer)```
6.  **Sélectionnez Appliquer**.

### <a name="create-a-tile-that-displays-active-devices"></a>Créer une vignette qui affiche les appareils actifs

1.  Sélectionnez **Afficher le tableau de** bord pour commencer à ajouter vos vignettes.
2.  Sélectionner **numéro & liste dans** la galerie
3.  Définir les **propriétés Général** :<br>
    **Titre du groupe :** État heartbeat<br>
    **Nouveau groupe :** Sélectionné
4.  Définissez les **propriétés du** mosaïque :<br>
    **Légende :** Appareils actifs (pulsations envoyées au cours des 20 dernières minutes)<br>
    **Requête de mosaïque :** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize AggregatedValue = count() by Computer | count```
5.  Définir les **propriétés de la** liste :<br>
    **Requête de liste :** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
6.  Définir les **titres des colonnes** :<br>
    **Nom :** Nom de l’ordinateur<br>
    **Valeur :** Dernière pulsation
7.  Définir **la requête de navigation**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  **Sélectionnez Appliquer**, puis **Fermer**.

### <a name="create-a-tile-that-displays-devices-that-have-connectivity-issues"></a>Créer une vignette qui affiche les appareils qui ont des problèmes de connectivité

1.  **Sélectionnez Numéro & numéro dans** la galerie, puis ajoutez une nouvelle vignette.
2.  Définir les **propriétés Général** :<br>
    **Titre du groupe :** Laisser vide<br>
    **Nouveau groupe :** Non sélectionné
3.  Définissez les **propriétés du** mosaïque :<br>
    **Légende :** Appareils inactifs (aucun message de pulsation envoyé au cours des 20 dernières minutes)<br>
    **Requête de mosaïque :** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize LastHB = max(TimeGenerated) by Computer | where LastHB < ago(20m) | count```
4.  Définir les **propriétés de la** liste :<br>
    **Requête de liste :** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize TimeGenerated = max(TimeGenerated) by Computer | where TimeGenerated < ago(20m) | order by TimeGenerated```
5.  Définir les **titres des colonnes** :<br>
    **Nom :** Nom de l’ordinateur<br>
    **Valeur :** Dernière pulsation
6.  Définir **la requête de navigation** :<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
7.  **Sélectionnez Appliquer**, puis **Fermer**.

### <a name="create-a-tile-that-displays-devices-that-have-a-hardware-error"></a>Créer une vignette qui affiche les appareils qui ont une erreur matérielle

1.  **Sélectionnez Numéro & numéro dans** la galerie, puis ajoutez une nouvelle vignette.
2.  Définir les **propriétés Général** :<br>
    **Titre du groupe :** État du matériel<br>
    **Nouveau groupe :** Sélectionné
3.  Définissez les **propriétés du** mosaïque :<br>
    **Légende :** Appareils qui ont connu une erreur matérielle au cours de la dernière heure<br>
    **Requête de mosaïque :** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```
4.  Définir les **propriétés de la** liste :<br>
    **Requête de liste :** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
5.  Définir les **titres des colonnes** :<br>
    **Nom :** Nom de l’ordinateur<br>
    **Valeur :** Dernière erreur
6.  Définir **la requête de navigation** :<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == 3001 and EventLevelName == "Error" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSConfMicrophoneStatus_CF, SRSConfSpeakerStatus_CF, SRSDefaultSpeakerStatus_CF, SRSCameraStatus_CF, SRSFORDStatus_CF, SRSMotionSensorStatus_CF, SRSHDMIIngestStatus_CF, SRSEventDescription_CF | sort by TimeGenerated desc```
7.  **Sélectionnez Appliquer**, puis **Fermer**.

### <a name="create-a-tile-that-displays-no-loc-textmicrosoft-teams-rooms-operating-system-versions"></a>Créer une vignette affichant les versions du :::no-loc text="Microsoft Teams Rooms"::: système d’exploitation

1.  **Sélectionnez Donut & liste** dans la galerie, puis ajoutez une nouvelle vignette.
2.  Définir les **propriétés Général** :<br>
    **Titre du groupe :** Détails sur le système d’exploitation<br>
    **Nouveau groupe :** Sélectionné
3.  Définir les **propriétés d’en-tête** :<br>
    **Titre :** Versions du système d’exploitation<br>
    **Sous-titre :** Appareils exécutant des versions de système d’exploitation spécifiques
4.  Définissez les **propriétés de la propriété Donut** :<br>
    **Requête :** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize OS_Version = max(SRSOSLongVersion_CF) by Computer | summarize AggregatedValue = count() by OS_Version | sort by OS_Version asc```<br>
    **Centrer le texte :** Appareils<br>
    **Opération :** Somme
5.  Définissez les **propriétés de** la liste.<br>
    **Requête de liste :** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSOSLongVersion_CF = max(SRSOSLongVersion_CF) by Computer | sort by Computer asc```<br>
    **Masquer Graph :** sélectionné<br>
    **Activer lesine sparkline :** Non sélectionné
6.  Définir les **titres des colonnes**<br>
    **Nom :** Nom de l’ordinateur<br>
    **Valeur :** Laisser vide
7.  Définir **la requête de navigation**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSDisplayName_CF, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  **Sélectionnez Appliquer**, puis **Fermer**.

### <a name="create-a-tile-that-displays-no-loc-textmicrosoft-teams-rooms-application-versions"></a>Créer une vignette qui affiche les versions des :::no-loc text="Microsoft Teams Rooms"::: applications

1.  **Sélectionnez Donut & liste** dans la galerie, puis ajoutez une nouvelle vignette.
2.  Définir les **propriétés Général** :<br>
    **Titre du groupe :** :::no-loc text="Microsoft Teams Rooms"::: détails de l’application<br>
    **Nouveau groupe :** Sélectionné
3.  Définir les **propriétés d’en-tête** :<br>
    **Titre :** Versions des applications<br>
    **Sous-titre :** Appareils exécutant des versions d’application spécifiques
4.  Définissez les **propriétés de la propriété Donut** :<br>
    **Requête :** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize App_Version = max(SRSAppVersion_CF) by Computer | summarize AggregatedValue = count() by App_Version | sort by App_Version asc```<br>
    **Centrer le texte :** Appareils<br>
    **Opération :** Somme
5.  Définissez les **propriétés de** la liste.<br>
    **Requête de liste :** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSAppVersion_CF = max(SRSAppVersion_CF) by Computer | sort by Computer asc```<br>
    **Masquer Graph :** sélectionné<br>
    **Activer lesine sparkline :** Non sélectionné
6.  Définir les **titres des colonnes**<br>
    **Nom :** Nom de l’ordinateur<br>
    **Valeur :** Laisser vide
7.  Définir **la requête de navigation**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  **Sélectionnez Appliquer**, puis **Fermer**.

### <a name="create-a-tile-that-displays-devices-that-have-an-application-error"></a>Créer une vignette affichant les appareils affichant une erreur d’application

1.  **Sélectionnez Numéro & numéro dans** la galerie, puis ajoutez une nouvelle vignette.
2.  Définissez les **propriétés** Général.<br>
    **Titre du groupe :** Laisser vide<br>
    **Nouveau groupe :** Non sélectionné
3.  Définissez les **propriétés du** mosaïque.<br>
    **Légende :** Appareils qui ont connu une erreur d’application au cours de la dernière heure<br>
    **Requête de mosaïque :** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```
4.  Définissez les **propriétés de** la liste.<br>
    **Requête de liste :** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
5.  Définir les **titres des colonnes**<br>
    **Nom :** Nom de l’ordinateur<br>
    **Valeur :** Dernière erreur
6.  Définir **la requête de navigation**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == 2001 and EventLevelName == "Error" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF | sort by TimeGenerated desc```
7.  **Sélectionnez Appliquer**, puis **Fermer**.

### <a name="create-a-tile-that-displays-devices-that-have-been-restarted"></a>Créer une vignette qui affiche les appareils qui ont été redémarrés

1.  **Sélectionnez Numéro & numéro dans** la galerie, puis ajoutez une nouvelle vignette.
2.  Définissez les **propriétés** Général.<br>
    **Titre du groupe :** Laisser vide<br>
    **Nouveau groupe :** Non sélectionné
3.  Définissez les **propriétés du** mosaïque.<br>
    **Légende :** Appareils sur lequel l’application a été redémarré au cours des dernières 24 heures et nombre de redémarrages<br>
    **Requête de mosaïque :** ```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | summarize AggregatedValue = count() by Computer | count```
4.  Définissez les **propriétés de** la liste.<br>
    **Requête de liste :** ```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | order by TimeGenerated | summarize AggregatedValue = count(EventID) by Computer```
5.  Définir les **titres des colonnes**<br>
    **Nom :** Nom de l’ordinateur<br>
    **Valeur :** Nombre de redémarrages
6.  Définir **la requête de navigation**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
7.  **Sélectionnez Appliquer**, puis **Fermer**.
8.  **Sélectionnez Enregistrer** pour enregistrer votre tableau de bord.

Vous avez à présent fini de créer vos affichages.

## <a name="configure-alerts-in-no-loc-textazure-monitor"></a>Configurer les alertes dans :::no-loc text="Azure Monitor":::
<a name="Alerts"> </a>

:::no-loc text="Azure Monitor"::: peut lever des alertes pour avertir les administrateurs lorsqu’une :::no-loc text="Microsoft Teams Rooms"::: console rencontre un problème.

:::no-loc text="Azure Monitor"::: inclut un mécanisme d’alerte intégré qui permet de passer par des recherches dans les journaux programmés à intervalles réguliers. Si les résultats de la recherche dans le journal correspondent à certains critères particuliers, un enregistrement d’alerte est créé.

La règle peut ensuite exécuter automatiquement une ou plusieurs actions pour vous avertir de l’alerte ou appeler un autre processus de manière proactive. Les options possibles avec des alertes sont les autres :
-   Envoi d’un e-mail
-   Appel d’un processus externe via une demande HTTP POST
-   Démarrage d’un runbook en :::no-loc text="Azure Automation"::: service

[Consultez les alertes de journal :::no-loc text="Azure Monitor":::](/azure/azure-monitor/platform/alerts-unified-log) pour en savoir plus sur les alertes dans :::no-loc text="Azure Monitor":::.

> [!NOTE]
> Les exemples suivants envoient des alertes par courrier électronique lorsqu’un :::no-loc text="Microsoft Teams Rooms"::: appareil génère une erreur matérielle ou d’application.

### <a name="configure-an-email-alert-for-no-loc-textmicrosoft-teams-rooms-hardware-issues"></a>Configurer une alerte par courrier électronique en cas de :::no-loc text="Microsoft Teams Rooms"::: problèmes matériels

Configurez une règle d’alerte qui vérifie les :::no-loc text="Microsoft Teams Rooms"::: appareils qui ont rencontré des problèmes matériels au cours de la dernière heure.
1.  Connectez-vous au [portail:::no-loc text="Microsoft Azure":::,](https://portal.azure.com) puis sélectionnez :::no-loc text="Log Analytics"::: votre espace de travail.

2. Accédez à votre espace :::no-loc text="Log Analytics"::: de travail, sélectionnez **Alertes** , puis **sélectionnez Nouvelle règle d’alerte**

3. **Sélectionnez Ajouter une condition**, puis **Recherche dans le journal personnalisé**

4.  Entrez la requête suivante dans la zone de texte requête de recherche.<br>
    ```
    Event
    | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h)
    | summarize arg_max(TimeGenerated, *) by Computer
    | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSConfMicrophoneStatus_CF, SRSConfSpeakerStatus_CF, SRSDefaultSpeakerStatus_CF, SRSCameraStatus_CF, SRSFORDStatus_CF, SRSMotionSensorStatus_CF, SRSHDMIIngestStatus_CF, SRSEventDescription_CF
    |sort by TimeGenerated desc
    ```

5.  Configurez les paramètres de la logique Alerte :<br>
    **Sur la base des données :** Nombre de résultats<br>
    **Condition :** Supérieur à<br>
    **Seuil :** 0<br>

6. Configurez les paramètres d’évaluation, puis sélectionnez **Terminé** : <br>
    **Période (en minutes) :** 60<br>
    **Fréquence (en minutes) :** 60<br>

7. Configurer des groupes d’actions :
    1.  **Sélectionnez Créer nouveau**
    2.  Fournissez des noms appropriés pour *les champs Nom du groupe d’actions* *et Nom court* .
    3.  Spécifiez un nom *d’action unique* , **sélectionnez E-mail/SMS/Push/Voice**, puis **sélectionnez Modifier les détails**.
    4.  Cochez **la case** par courrier électronique et fournissez l’adresse de courrier de la personne ou du groupe qui recevra les alertes.
    5.  Vous pouvez également fournir votre numéro de téléphone pour être averti par SMS, par appel vocal ou les deux.
    6. **Sélectionnez OK**.

8. **Personnalisez les Actions** si vous souhaitez remplacer la ligne d’objet des courriers électroniques d’alerte.

9. Spécifiez un nom de règle et une description.<br>
    **Nom de la règle :** :::no-loc text="Microsoft Teams Rooms"::: Alerte de défaillance matérielle<br>
    **Description :** Liste des appareils qui ont rencontré un problème matériel au cours de la dernière heure<br>

10. Sélectionnez la gravité prévue et assurez-vous que la règle est activée.

11. Sélectionnez **Créer une règle d’alerte**.

### <a name="configure-an-email-alert-for-no-loc-textmicrosoft-teams-rooms-application-issues"></a>Configurer une alerte par courrier électronique en cas de :::no-loc text="Microsoft Teams Rooms"::: problèmes d’application

Répétez la même procédure, mais utilisez la requête suivante pour ré lister les appareils qui ont rencontré des problèmes d’application au cours de la dernière heure.

 ```
 Event
 | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h)
 | summarize arg_max(TimeGenerated, *) by Computer
 | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF
 | sort by TimeGenerated desc
 ```

Vous avez à présent défini les alertes. Vous pouvez définir des alertes supplémentaires à l’aide des exemples ci-dessus.

Lorsqu’une alerte est générée, vous recevez un e-mail répertoriant les appareils qui ont rencontré un problème au cours de la dernière heure.

! [Exemple d’e-mail :::no-loc text="Azure Monitor"::: d’alerte](.. /media/Deploy-Azure-Monitor-6.png « Exemple de message d’alerte :::no-loc text="Azure Monitor"::: »)

## <a name="configure-all-devices-for-no-loc-textazure-monitoring"></a>Configurer tous les appareils pour :::no-loc text="Azure Monitoring":::
<a name="configure_all_devices"> </a> Une fois les tableaux de bord et alertes configurés, :::no-loc text="Microsoft Monitoring"::: vous pouvez configurer et configurer l’agent :::no-loc text="Microsoft Teams Rooms"::: sur tous les appareils pour terminer votre déploiement de surveillance.

Bien que vous pouvez installer :::no-loc text="Microsoft Monitoring"::: et configurer l’agent manuellement sur chaque appareil, nous vous recommandons vivement de tirer parti des méthodes et outils de déploiement de logiciels existants.

Si vous créez vos :::no-loc text="Microsoft Teams Rooms"::: appareils pour la première fois, :::no-loc text="Microsoft Monitoring"::: vous souhaitez peut-être inclure les étapes de configuration de l’agent dans le cadre du processus de création. Pour plus d’informations, voir [Installer l’agent à l’aide de la ligne de commande](/azure/azure-monitor/platform/agent-windows#install-the-agent-using-the-command-line).

### <a name="deploying-no-loc-textmicrosoft-monitoring-agent-by-using-a-group-policy-object-gpo"></a>Déploiement d’un :::no-loc text="Microsoft Monitoring"::: agent à l’aide d’un objet de stratégie de groupe

Si vous avez déjà déployé vos :::no-loc text="Microsoft Teams Rooms"::: :::no-loc text="Azure Monitoring":::appareils avant de les implémenter, vous pouvez utiliser le script fourni pour configurer les agents :::no-loc text="Active Directory"::: à l’aide d’objets de stratégie de groupe.

1.  Créez un chemin réseau partagé et accordez l’accès en lecture au groupe **Ordinateurs de** domaine.

2.  Télécharger la version 64 bits de l’Agent :::no-loc text="Microsoft Monitoring"::: pour :::no-loc text="Windows":::<https://go.microsoft.com/fwlink/?LinkID=517476>

3.  Extraire le contenu du package d’installation dans le partage réseau.
    1.  Ouvrez une fenêtre d’invite de commandes, puis exécutez **MMASetup-AMD64.exe /c**
    2.  Spécifiez le partage que vous avez créé, puis extrayez le contenu.

4.  Créez un objet de stratégie de groupe et affectez-le à l’unité :::no-loc text="Microsoft Teams Rooms"::: organisationnelle où se trouvent les comptes d’ordinateurs.

5.  Configurer une stratégie d’exécution PowerShell :
    1.  Modifier l’objet de stratégie de groupe nouvellement créé et accéder aux composants de modèles d’administration Stratégies \\ :::no-loc text="Windows"::: \\ de configuration ordinateur \\ \\ :::no-loc text="Windows PowerShell":::
    2.  Activez **l’exécution de script et** définissez la stratégie **d’exécution** pour **autoriser les scripts locaux**.

6.  Configurez le script de démarrage :
    1.  Copiez le script suivant et enregistrez-le Install-MMAgent.ps1.
    2.  Modifiez les paramètres WorkspaceId, WorkspaceKey et SetupPath pour qu’ils correspondent à votre configuration.
    3.  Modifier le même objet de stratégie de groupe et accéder aux stratégies de configuration \\ \\ :::no-loc text="Windows"::: Paramètres \\ scripts (démarrage/arrêt)
    4.  Double-cliquez pour sélectionner **Démarrage**, puis **sélectionnez Scripts PowerShell**.
    5.  **Sélectionnez Afficher les** fichiers, puis copiez **Install-MMAgent.ps1** fichier dans ce dossier.
    6.  **Sélectionnez Ajouter**, puis **Parcourir**.
    7.  Sélectionnez le script ps1 que vous viennent de copier.

7.  :::no-loc text="Microsoft Teams Rooms"::: devraient installer et configurer l’agent :::no-loc text="Microsoft Monitoring"::: avec le deuxième redémarrage.

```PowerShell
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
> Vous pouvez consulter l’article [:::no-loc text="Log Analytics":::](/azure/azure-monitor/platform/agent-manage) Gérer et gérer l’agent lorsque vous avez besoin de reconfigurer un agent, de le déplacer vers un autre espace de travail ou de modifier les paramètres proxy après l’installation initiale.

## <a name="additional-solutions"></a>Autres solutions
<a name="Solutions"> </a>

:::no-loc text="Azure Monitor"::: fournit des solutions de gestion intégrées par le biais de [sa](/azure/azure-monitor/insights/solutions) galerie de solutions pour vous aider à surveiller votre environnement. Nous vous recommandons également d’ajouter des solutions [de](/azure/azure-monitor/platform/alert-management-solution) [:::no-loc text="Azure Log Analytics":::](/azure/azure-monitor/insights/solution-agenthealth) gestion des alertes et d’état d’santé de l’agent à votre espace de travail.

> [!NOTE]
> La solution :::no-loc text="Microsoft Monitoring"::: Agent Health peut vous aider à identifier les agents obsolètes ou rompus au sein de votre environnement, et la solution de gestion des alertes fournit des détails sur les alertes qui ont été élevées au cours d’une période donnée.

## <a name="see-also"></a>Voir aussi

[Planifier la :::no-loc text="Microsoft Teams Rooms"::: gestion avec :::no-loc text="Azure Monitor":::](azure-monitor-plan.md)

[Gérer les :::no-loc text="Microsoft Teams Rooms"::: appareils avec :::no-loc text="Azure Monitor":::](azure-monitor-manage.md)
