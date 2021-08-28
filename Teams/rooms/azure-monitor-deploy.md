---
title: Déployer la Salles Microsoft Teams gestion des ordinateurs avec Azure Monitor
ms.author: dstrome
author: dstrome
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
description: Cet article décrit comment déployer la gestion des appareils Salles Microsoft Teams de bout en bout à l’aide d’Azure Monitor.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 77b1e18e9f30e13cc209040ab876324afa232766
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58613023"
---
# <a name="deploy-no-loc-textmicrosoft-teams-rooms-management-with-no-loc-textazure-monitor"></a>Gestion :::no-loc text="Microsoft Teams Rooms"::: du déploiement avec :::no-loc text="Azure Monitor":::

Cet article décrit la mise en place et le déploiement intégrés de la gestion de bout en bout :::no-loc text="Microsoft Teams Rooms"::: des appareils à l’aide. :::no-loc text="Azure Monitor":::

Vous pouvez configurer l’intérieur pour fournir des alertes et des données de télémétrie de base qui vous aideront à :::no-loc text="Log Analytics"::: :::no-loc text="Azure Monitor"::: gérer les périphériques des :::no-loc text="Microsoft Teams Rooms"::: salles de réunion. À mesure que votre solution de gestion mature, vous pouvez décider de déployer des données et des fonctionnalités de gestion supplémentaires afin de créer une vue plus détaillée de la disponibilité et des performances de l’appareil.

En suivant ce guide, vous pouvez utiliser un tableau de bord comme celui-ci pour obtenir des rapports d’état détaillés sur la disponibilité des appareils, l’état des applications et du matériel, ainsi que la distribution des versions des applications et des systèmes :::no-loc text="Microsoft Teams Rooms"::: d’exploitation.

![Capture d’écran de l’affichage Analyse des journaux d’Salles Microsoft Teams](../media/Deploy-Azure-Monitor-1.png "Exemple d’affichage Analyse des journaux pour Salles Microsoft Teams")

À haut niveau, vous devez effectuer les tâches suivantes :


1. [Valider la :::no-loc text="Log Analytics"::: configuration](azure-monitor-deploy.md#validate_LogAnalytics)
2. [Configurer des périphériques de test pour la :::no-loc text="Log Analytics"::: configuration de la gestion](azure-monitor-deploy.md#configure_test_devices)
3. [Mapper les champs personnalisés](azure-monitor-deploy.md#Custom_fields)
4. [Définir les :::no-loc text="Microsoft Teams Rooms"::: affichages dans :::no-loc text="Log Analytics":::](azure-monitor-deploy.md#Define_Views)
5. [Définir des alertes](azure-monitor-deploy.md#Alerts)
6. [Configurer tous les appareils pour la surveillance](azure-monitor-deploy.md#configure_all_devices)
7. [Configurer des :::no-loc text="Azure Monitor"::: solutions supplémentaires](azure-monitor-deploy.md#Solutions)

> [!IMPORTANT]
> Bien qu’avec une configuration minimale, vous pouvez surveiller un ordinateur exécutant un système d’exploitation, il reste encore quelques étapes –spécifiques à suivre avant de commencer à déployer des agents sur :::no-loc text="Azure Monitor"::: :::no-loc text="Log Analytics"::: tous les :::no-loc text="Windows"::: :::no-loc text="Microsoft Teams Rooms"::: :::no-loc text="Microsoft Teams Rooms"::: appareils.
> Par conséquent, nous vous recommandons vivement d’effectuer toutes les étapes de configuration dans le bon ordre pour une configuration et une configuration contrôlées. La qualité du résultat final dépend beaucoup de la qualité de la configuration initiale.

## <a name="validate-no-loc-textlog-analytics-configuration"></a>Valider la :::no-loc text="Log Analytics"::: configuration
<a name="validate_LogAnalytics"> </a>

Vous devez avoir un espace :::no-loc text="Log Analytics"::: de travail pour commencer à collecter les journaux à partir d’appareils. :::no-loc text="Microsoft Teams Rooms"::: Un espace de travail est un environnement unique avec son propre référentiel :::no-loc text="Log Analytics"::: de données, ses sources de données et ses solutions. Si vous avez déjà un espace de travail existant, vous pouvez l’utiliser pour surveiller votre déploiement ou créer un espace de travail dédié spécifique à vos besoins :::no-loc text="Log Analytics"::: :::no-loc text="Microsoft Teams Rooms"::: de :::no-loc text="Log Analytics"::: :::no-loc text="Microsoft Teams Rooms"::: surveillance.

Si vous avez besoin de créer un espace de travail, suivez les instructions de l’article Créer :::no-loc text="Log Analytics"::: un espace de travail dans le [ :::no-loc text="Log Analytics"::: :::no-loc text="Azure"::: portail](/azure/azure-monitor/learn/quick-create-workspace)

> [!NOTE]
> Pour :::no-loc text="Log Analytics"::: l’utiliser, :::no-loc text="Azure Monitor"::: vous devez avoir un abonnement :::no-loc text="Azure"::: actif. Si vous n’avez pas d’abonnement, vous pouvez créer un abonnement d’essai :::no-loc text="Azure"::: gratuit comme point de départ. [](https://azure.microsoft.com/free)

### <a name="configure-no-loc-textlog-analytics-to-collect-no-loc-textmicrosoft-teams-rooms-event-logs"></a>Configurer la :::no-loc text="Log Analytics"::: collecte des :::no-loc text="Microsoft Teams Rooms"::: journaux d’événements

:::no-loc text="Log Analytics"::: collecte uniquement les événements à partir des journaux des :::no-loc text="Windows"::: événements spécifiés dans les paramètres. Pour chaque journal, seuls les événements dont la gravité est sélectionnée sont collectés.

Vous devez configurer pour collecter les journaux requis pour surveiller l’état de l’appareil :::no-loc text="Log Analytics"::: :::no-loc text="Microsoft Teams Rooms"::: et de l’application. :::no-loc text="Microsoft Teams Rooms"::: les appareils utilisent le **:::no-loc text="Skype Room System":::** journal des événements.

Pour configurer la :::no-loc text="Log Analytics"::: collecte des événements, consultez les sources de données du :::no-loc text="Microsoft Teams Rooms"::: journal des [ :::no-loc text="Windows"::: événements dans :::no-loc text="Azure Monitor"::: ](/azure/azure-monitor/platform/data-sources-windows-events)

![Capture d’écran des paramètres du journal des événements](../media/Deploy-Azure-Monitor-2.png "Paramètres du journal des événements")

> [!IMPORTANT]
> Configurez les paramètres du journal des événements et entrez le nom du journal des événements, puis cochez les cases Erreur, Avertissement et :::no-loc text="Windows"::: **:::no-loc text="Skype Room System":::** Informations.   

## <a name="configure-test-devices-for-azure-monitoring"></a>Configurer des périphériques de test pour Azure Monitoring
<a name="configure_test_devices"> </a>

Vous devez vous préparer :::no-loc text="Log Analytics"::: à être en mesure de surveiller les :::no-loc text="Microsoft Teams Rooms"::: événements –associés. Pour commencer, vous devez déployer des agents sur un ou deux appareils à qui vous avez accès physique, et faire en sorte que ces périphériques de test génèrent des données et les envoient à l’espace :::no-loc text="Microsoft Monitoring"::: :::no-loc text="Microsoft Teams Rooms"::: de :::no-loc text="Log Analytics"::: travail.

### <a name="install-no-loc-textmicrosoft-monitoring-agents-to-test-devices"></a>Installer des :::no-loc text="Microsoft Monitoring"::: agents pour tester les appareils

Déployez l’agent sur les périphériques de test en utilisant les instructions fournies :::no-loc text="Microsoft Monitoring"::: Connecter sur le service [ :::no-loc text="Windows"::: :::no-loc text="Log Analytics"::: dans :::no-loc text="Azure"::: ](/azure/azure-monitor/platform/agent-windows). Cet article fournit des informations détaillées sur les étapes à suivre pour le déploiement de l’Agent, des instructions pour obtenir l’ID d’espace de travail _ et la clé primaire _ pour connecter les appareils à votre déploiement, ainsi que des instructions pour vérifier la connectivité de l’agent à :::no-loc text="Microsoft Monitoring"::: :::no-loc text="Windows"::: :::no-loc text="Log Analytics":::  * ** :::no-loc text="Microsoft Teams Rooms"::: :::no-loc text="Azure Monitor"::: :::no-loc text="Log Analytics"::: l’instance.

### <a name="generate-sample-no-loc-textmicrosoft-teams-rooms-events"></a>Générer des exemples :::no-loc text="Microsoft Teams Rooms"::: d’événements

Une fois l’agent déployé sur les appareils de test, vérifiez que les données requises du journal des :::no-loc text="Microsoft Monitoring"::: événements sont collectées :::no-loc text="Azure Monitor"::: par.

> [!NOTE]
> Redémarrez l’appareil après l’installation de l’agent et assurez-vous que l’application Réunion est démarrée afin qu’elle puisse générer de nouveaux événements dans le :::no-loc text="Microsoft Monitoring"::: :::no-loc text="Microsoft Teams Rooms"::: journal des événements.

1.  Connectez-vous au [ :::no-loc text="Microsoft Azure"::: portail,](https://portal.azure.com) puis sélectionnez :::no-loc text="Log Analytics"::: votre espace de travail.

2.  Énumérer les événements de pulsation générés par un :::no-loc text="Microsoft Teams Rooms"::: appareil :
    1.  Sélectionnez votre espace de travail, puis allez **dans Journaux** et utilisez une requête pour extraire les enregistrements de pulsation qui auront les champs personnalisés pour :::no-loc text="Microsoft Teams Rooms"::: .
    2.  Exemple de requête : `Event | where Source == "SRS-App" and EventID == 2000`

3.  Assurez-vous que la requête renvoie des enregistrements journaux qui incluent des :::no-loc text="Microsoft Teams Rooms"::: événements générés par l’application Réunions.

4.  Générer un problème matériel et vérifier que les événements requis sont :::no-loc text="Azure Log Analytics"::: connectés.
    1.  Débranchez l’un des périphériques sur le système de :::no-loc text="Microsoft Teams Rooms"::: test. Cela peut être l’appareil photo, le téléphone haut-parleur, le microphone ou l’affichage de la salle avant
    2.  Attendez 10 minutes que le journal des événements soit :::no-loc text="Azure Log Analytics"::: rempli.
    3.  Utilisez une requête pour lister les événements d’erreurs matérielles : `Event | where Source == "SRS-App" and EventID == 3001`

5.  Générez un problème d’application et validez que les événements requis sont enregistrés.
    1.  Modifiez :::no-loc text="Microsoft Teams Rooms"::: la configuration de l’application et tapez une paire d’adresse/mot de passe SIP incorrecte.
    2.  Attendez 10 minutes que le journal des événements soit :::no-loc text="Azure Log Analytics"::: rempli.
    3.  Utilisez une requête pour lister les événements d’erreur d’application : `Event | where Source == "SRS-App" and EventID == 2001 and EventLevel == 1`

> [!IMPORTANT]
> Ces exemples de journaux d’événements sont requis pour que les champs personnalisés soient configurés. Ne pas passer à l’étape suivante tant que vous n’avez pas collecté les journaux des événements requis.

## <a name="map-custom-fields"></a>Mapper les champs personnalisés
<a name="Custom_fields"> </a>

Les champs personnalisés vous sont utilisés pour extraire des données spécifiques des journaux des événements. Vous devez définir des champs personnalisés qui seront utilisés ultérieurement avec vos vignettes, vues de tableau de bord et alertes. Consultez [les :::no-loc text="Log Analytics"::: champs personnalisés](/azure/azure-monitor/platform/custom-fields) et familiarisez-vous avec les concepts avant de commencer à créer vos champs personnalisés.

Pour extraire vos champs personnalisés des journaux des événements capturés, suivez ces étapes :

1.  Connectez-vous au [ :::no-loc text="Microsoft Azure"::: portail,](https://portal.azure.com) puis sélectionnez :::no-loc text="Log Analytics"::: votre espace de travail.

2. Listez les événements générés par un :::no-loc text="Microsoft Teams Rooms"::: appareil :
   1.  Allez dans **Journaux** et utilisez une requête pour récupérer les enregistrements qui auront le champ personnalisé.
   2.  Exemple de requête : `Event | where Source == "SRS-App" and EventID == 2000`

3. Sélectionnez l’un des enregistrements, sélectionnez le bouton à gauche et démarrez l’Assistant Extraction de champ.
4. Mettez en surbrillation les données que vous voulez extraire de la description RenderedDescription et indiquez un titre de champ. Les noms des champs que vous devez utiliser sont indiqués dans la Table 1.
5. Utilisez les mappages indiqués dans *le tableau 1.* :::no-loc text="Log Analytics":::automatiquement la chaîne **\_** CF lorsque vous définissez le nouveau champ.

> [!IMPORTANT]
> N’oubliez pas que tous les champs et JSON :::no-loc text="Log Analytics"::: sont sensibles à la cas.
> 
> Faites attention aux requêtes requises pour chaque champ personnalisé dans la table ci-dessous. Vous devez utiliser les requêtes correctes pour extraire correctement des :::no-loc text="Log Analytics"::: valeurs de champ personnalisé.
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
| État de l’affichage avant de la salle     | SRSFORDStatus               | **3001**     | Événement \| dans lequel Source == « SRS-App » et EventID == 3001 |
| État du capteur de mouvement             | SRSMotionSensorStatus       | **3001**     | Événement \| dans lequel Source == « SRS-App » et EventID == 3001 |
| État HDMI Ingest               | SRSHDMIIngestStatus         | **3001**     | Événement \| dans lequel Source == « SRS-App » et EventID == 3001 |


## <a name="define-the-no-loc-textmicrosoft-teams-rooms-views-in-no-loc-textlog-analytics"></a>Définir les :::no-loc text="Microsoft Teams Rooms"::: affichages dans :::no-loc text="Log Analytics":::
<a name="Define_Views"> </a>

Une fois les données collectées et les champs personnalisés mappés, vous pouvez utiliser le Concepteur de vues pour développer un tableau de bord contenant différentes vignettes pour surveiller les :::no-loc text="Microsoft Teams Rooms"::: événements. Utilisez le concepteur de vues pour créer les mosaïques suivantes. Pour plus d’informations, voir [Créer :::no-loc text="Log Analytics"::: des affichages personnalisés à l’aide du Concepteur de vues dans](/azure/azure-monitor/platform/view-designer)

> [!NOTE]
> Les étapes précédentes de ce guide doivent avoir été effectuées pour que les vignettes du tableau de bord fonctionnent correctement.
>
> [!IMPORTANT]
> Le Concepteur d’affichage dans l’écran Azure a été mis hors cours le [31 août 2023](https://azure.microsoft.com/updates/view-designer-in-azure-monitor-is-retiring-on-31-august-2023/) et les fonctionnalités de création et d’cloner ont été désactivées le 30 novembre 2020. Il est possible d’utiliser des manuels à la place. Pour plus d’informations sur le guide de transition du Concepteur de vues vers les manuels, voir Démarrage rapide avec des modèles de concepteur [de vues prédéfinfins.](/azure/azure-monitor/visualize/view-designer-conversion-tasks#quickstart-with-preset-view-designer-templates)

### <a name="create-a-microsoft-teams-rooms-dashboard-manually"></a>Créer un tableau Salles Microsoft Teams de bord manuellement

Vous pouvez également créer votre propre tableau de bord et ajouter uniquement les vignettes que vous souhaitez contrôler.

#### <a name="configure-the-overview-tile"></a>Configurer la vignette Vue d’ensemble

1.  Ouvrir **le Concepteur d’affichage.**
2.  Sélectionnez **Vignette vue d’ensemble,** puis deux numéros **dans** la galerie.
3.  Nommez la **:::no-loc text="Microsoft Teams Rooms":::** vignette.
4.  Définir la **première vignette**:<br>
    **Légende :** Appareils qui ont envoyé une pulsation au moins une fois au cours du mois précédent<br>
    **Requête :**```Event | where EventLog == "Skype Room System" and TimeGenerated > ago(30d) | summarize TotalSRSDevices = dcount(Computer)```
5.  Définir la **deuxième vignette**:<br>
    **Légende :** Appareils actifs qui ont envoyé une pulsation au cours de la dernière heure<br>
    **Requête :**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(1h) | summarize TotalSRSDevices = dcount(Computer)```
6.  Sélectionnez **Appliquer.**

### <a name="create-a-tile-that-displays-active-devices"></a>Créer une vignette qui affiche les appareils actifs

1.  Sélectionnez **Afficher le tableau de** bord pour commencer à ajouter vos vignettes.
2.  Sélectionner **l'& numéro dans** la galerie
3.  Définir les **propriétés Général** :<br>
    **Titre du groupe :** État de pulsation<br>
    **Nouveau groupe :** Sélectionné
4.  Définissez les **propriétés du** mosaïque :<br>
    **Légende :** Appareils actifs (pulsations envoyées au cours des 20 dernières minutes)<br>
    **Requête de mosaïque :** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize AggregatedValue = count() by Computer | count```
5.  Définir les **propriétés de la** liste :<br>
    **Requête de liste :**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
6.  Définir **les titres des colonnes**:<br>
    **Nom :** Nom de l’ordinateur<br>
    **Valeur :** Dernière pulsation
7.  Définir **la requête de navigation.**<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  Sélectionnez **Appliquer,** puis **Fermer.**

### <a name="create-a-tile-that-displays-devices-that-have-connectivity-issues"></a>Créer une vignette qui affiche les appareils qui ont des problèmes de connectivité

1.  Sélectionnez **Numéro & numéro dans** la galerie, puis ajoutez une nouvelle vignette.
2.  Définir les **propriétés Général** :<br>
    **Titre du groupe :** Laisser vide<br>
    **Nouveau groupe :** Non sélectionné
3.  Définissez les **propriétés du** mosaïque :<br>
    **Légende :** Appareils inactifs (aucun message de pulsation envoyé au cours des 20 dernières minutes)<br>
    **Requête de mosaïque :** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize LastHB = max(TimeGenerated) by Computer | where LastHB < ago(20m) | count```
4.  Définir les **propriétés de la** liste :<br>
    **Requête de liste :**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize TimeGenerated = max(TimeGenerated) by Computer | where TimeGenerated < ago(20m) | order by TimeGenerated```
5.  Définir **les titres des colonnes**:<br>
    **Nom :** Nom de l’ordinateur<br>
    **Valeur :** Dernière pulsation
6.  Définir **la requête de navigation**:<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
7.  Sélectionnez **Appliquer,** puis **Fermer.**

### <a name="create-a-tile-that-displays-devices-that-have-a-hardware-error"></a>Créer une vignette qui affiche les appareils qui ont une erreur matérielle

1.  Sélectionnez **Numéro & numéro dans** la galerie, puis ajoutez une nouvelle vignette.
2.  Définir les **propriétés Général** :<br>
    **Titre du groupe :** État du matériel<br>
    **Nouveau groupe :** Sélectionné
3.  Définissez les **propriétés du** mosaïque :<br>
    **Légende :** Appareils qui ont connu une erreur matérielle au cours de la dernière heure<br>
    **Requête de mosaïque :** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```
4.  Définir les **propriétés de la** liste :<br>
    **Requête de liste :**```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
5.  Définir **les titres des colonnes**:<br>
    **Nom :** Nom de l’ordinateur<br>
    **Valeur :** Dernière erreur
6.  Définir **la requête de navigation**:<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == 3001 and EventLevelName == "Error" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSConfMicrophoneStatus_CF, SRSConfSpeakerStatus_CF, SRSDefaultSpeakerStatus_CF, SRSCameraStatus_CF, SRSFORDStatus_CF, SRSMotionSensorStatus_CF, SRSHDMIIngestStatus_CF, SRSEventDescription_CF | sort by TimeGenerated desc```
7.  Sélectionnez **Appliquer,** puis **Fermer.**

### <a name="create-a-tile-that-displays-no-loc-textmicrosoft-teams-rooms-operating-system-versions"></a>Créer une vignette affichant les :::no-loc text="Microsoft Teams Rooms"::: versions du système d’exploitation

1.  Sélectionnez **Ajouter & liste** dans la galerie, puis ajoutez une nouvelle vignette.
2.  Définir les **propriétés Général** :<br>
    **Titre du groupe :** Détails sur le système d’exploitation<br>
    **Nouveau groupe :** Sélectionné
3.  Définir les **propriétés d’en-tête** :<br>
    **Titre :** Versions du système d’exploitation<br>
    **Sous-titre :** Appareils exécutant des versions de système d’exploitation spécifiques
4.  Définissez les **propriétés de la propriété Donut** :<br>
    **Requête :**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize OS_Version = max(SRSOSLongVersion_CF) by Computer | summarize AggregatedValue = count() by OS_Version | sort by OS_Version asc```<br>
    **Centrer le texte :** Appareils<br>
    **Opération :** Somme
5.  Définissez les **propriétés de** la liste.<br>
    **Requête de liste :**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSOSLongVersion_CF = max(SRSOSLongVersion_CF) by Computer | sort by Computer asc```<br>
    **Masquer les Graph :** Sélectionné<br>
    **Activer lesine sparkline :** Non sélectionné
6.  Définir les **titres des colonnes.**<br>
    **Nom :** Nom de l’ordinateur<br>
    **Valeur :** Laisser vide
7.  Définir **la requête de navigation.**<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSDisplayName_CF, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  Sélectionnez **Appliquer,** puis **Fermer.**

### <a name="create-a-tile-that-displays-no-loc-textmicrosoft-teams-rooms-application-versions"></a>Créer une vignette qui affiche les :::no-loc text="Microsoft Teams Rooms"::: versions des applications

1.  Sélectionnez **Ajouter & liste** dans la galerie, puis ajoutez une nouvelle vignette.
2.  Définir les **propriétés Général** :<br>
    **Titre du groupe :** :::no-loc text="Microsoft Teams Rooms"::: détails de l’application<br>
    **Nouveau groupe :** Sélectionné
3.  Définir les **propriétés d’en-tête** :<br>
    **Titre :** Versions des applications<br>
    **Sous-titre :** Appareils exécutant des versions d’application spécifiques
4.  Définissez les **propriétés de la propriété Donut** :<br>
    **Requête :**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize App_Version = max(SRSAppVersion_CF) by Computer | summarize AggregatedValue = count() by App_Version | sort by App_Version asc```<br>
    **Centrer le texte :** Appareils<br>
    **Opération :** Somme
5.  Définissez les **propriétés de** la liste.<br>
    **Requête de liste :**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSAppVersion_CF = max(SRSAppVersion_CF) by Computer | sort by Computer asc```<br>
    **Masquer les Graph :** Sélectionné<br>
    **Activer lesine sparkline :** Non sélectionné
6.  Définir les **titres des colonnes.**<br>
    **Nom :** Nom de l’ordinateur<br>
    **Valeur :** Laisser vide
7.  Définir **la requête de navigation.**<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  Sélectionnez **Appliquer,** puis **Fermer.**

### <a name="create-a-tile-that-displays-devices-that-have-an-application-error"></a>Créer une vignette qui affiche les appareils affichant une erreur d’application

1.  Sélectionnez **Numéro & numéro dans** la galerie, puis ajoutez une nouvelle vignette.
2.  Définissez **les propriétés** Général.<br>
    **Titre du groupe :** Laisser vide<br>
    **Nouveau groupe :** Non sélectionné
3.  Définissez les **propriétés du** mosaïque.<br>
    **Légende :** Appareils qui ont connu une erreur d’application au cours de la dernière heure<br>
    **Requête de mosaïque :** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```
4.  Définissez les **propriétés de** la liste.<br>
    **Requête de liste :**```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
5.  Définir les **titres des colonnes.**<br>
    **Nom :** Nom de l’ordinateur<br>
    **Valeur :** Dernière erreur
6.  Définir **la requête de navigation.**<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == 2001 and EventLevelName == "Error" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF | sort by TimeGenerated desc```
7.  Sélectionnez **Appliquer,** puis **Fermer.**

### <a name="create-a-tile-that-displays-devices-that-have-been-restarted"></a>Créer une vignette qui affiche les appareils qui ont été redémarrés

1.  Sélectionnez **Numéro & numéro dans** la galerie, puis ajoutez une nouvelle vignette.
2.  Définissez **les propriétés** Général.<br>
    **Titre du groupe :** Laisser vide<br>
    **Nouveau groupe :** Non sélectionné
3.  Définissez les **propriétés du** mosaïque.<br>
    **Légende :** Appareils sur lequel l’application a été redémarré au cours des dernières 24 heures et nombre de redémarrages<br>
    **Requête de mosaïque :** ```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | summarize AggregatedValue = count() by Computer | count```
4.  Définissez les **propriétés de** la liste.<br>
    **Requête de liste :**```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | order by TimeGenerated | summarize AggregatedValue = count(EventID) by Computer```
5.  Définir les **titres des colonnes.**<br>
    **Nom :** Nom de l’ordinateur<br>
    **Valeur :** Nombre de redémarrages
6.  Définir **la requête de navigation.**<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
7.  Sélectionnez **Appliquer,** puis **Fermer.**
8.  Sélectionnez **Enregistrer** pour enregistrer votre tableau de bord.

Vous avez à présent fini de créer vos affichages.

## <a name="configure-alerts-in-no-loc-textazure-monitor"></a>Configurer les alertes dans :::no-loc text="Azure Monitor":::
<a name="Alerts"> </a>

:::no-loc text="Azure Monitor"::: peut lever des alertes pour avertir les administrateurs lorsqu’une :::no-loc text="Microsoft Teams Rooms"::: console rencontre un problème.

:::no-loc text="Azure Monitor"::: inclut un mécanisme d’alerte intégré qui permet de passer par des recherches dans les journaux programmés à intervalles réguliers. Si les résultats de la recherche dans le journal correspondent à certains critères particuliers, un enregistrement d’alerte est créé.

La règle peut ensuite exécuter automatiquement une ou plusieurs actions pour vous avertir de l’alerte ou appeler un autre processus de manière proactive. Les options possibles avec des alertes sont les autres :
-   Envoi d’un e-mail
-   Appel d’un processus externe via une demande HTTP POST
-   Démarrage d’un runbook en :::no-loc text="Azure Automation"::: service

Consultez [les :::no-loc text="Azure Monitor"::: alertes de journal](/azure/azure-monitor/platform/alerts-unified-log) pour en savoir plus sur les alertes dans :::no-loc text="Azure Monitor"::: .

> [!NOTE]
> Les exemples suivants envoient des alertes par courrier électronique lorsqu’un appareil génère une erreur matérielle ou :::no-loc text="Microsoft Teams Rooms"::: d’application.

### <a name="configure-an-email-alert-for-no-loc-textmicrosoft-teams-rooms-hardware-issues"></a>Configurer une alerte par courrier électronique en cas :::no-loc text="Microsoft Teams Rooms"::: de problèmes matériels

Configurez une règle d’alerte qui vérifie les appareils qui ont rencontré des problèmes :::no-loc text="Microsoft Teams Rooms"::: matériels au cours de la dernière heure.
1.  Connectez-vous au [ :::no-loc text="Microsoft Azure"::: portail,](https://portal.azure.com) puis sélectionnez :::no-loc text="Log Analytics"::: votre espace de travail.

2. Accédez à votre :::no-loc text="Log Analytics"::: espace de travail, sélectionnez **Alertes,** puis **sélectionnez Nouvelle règle d’alerte**

3. Sélectionnez **Ajouter une condition,** puis **Recherche dans le journal personnalisé**

4.  Entrez la requête suivante dans la zone de texte de la requête de recherche.<br>
    ```
    Event
    | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h)
    | summarize arg_max(TimeGenerated, *) by Computer
    | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSConfMicrophoneStatus_CF, SRSConfSpeakerStatus_CF, SRSDefaultSpeakerStatus_CF, SRSCameraStatus_CF, SRSFORDStatus_CF, SRSMotionSensorStatus_CF, SRSHDMIIngestStatus_CF, SRSEventDescription_CF
    |sort by TimeGenerated desc
    ```

5.  Configurez les paramètres de la logique Alerte :<br>
    **Sur la base des données :** Nombre de résultats<br>
    **Condition :** Greater then<br>
    **Seuil :** 0<br>

6. Configurez les paramètres d’évaluation, puis sélectionnez **Terminé**: <br>
    **Période (en minutes) :** 60<br>
    **Fréquence (en minutes) :** 60<br>

7. Configurer des groupes d’actions :
    1.  Sélectionnez **Créer nouveau**
    2.  Fournissez des noms appropriés *pour les champs Nom du groupe d’actions* et Nom *court.*
    3.  Spécifiez un nom *d’action unique,* **sélectionnez E-mail/SMS/Push/Voix,** puis **sélectionnez Modifier les détails.**
    4.  Cochez **la case** Par e-mail et fournissez l’adresse e-mail de la personne ou du groupe qui recevra les alertes.
    5.  Vous pouvez également fournir votre numéro de téléphone pour être averti par SMS, par appel vocal ou les deux.
    6. Sélectionnez **OK.**

8. **Personnalisez les actions** si vous souhaitez remplacer la ligne d’objet des courriers électroniques d’alerte.

9. Spécifiez un nom de règle et une description.<br>
    **Nom de la règle :** :::no-loc text="Microsoft Teams Rooms"::: Alerte d’échec matériel<br>
    **Description :** Liste des appareils qui ont rencontré un problème matériel au cours de la dernière heure<br>

10. Sélectionnez la gravité prévue et assurez-vous que la règle est activée.

11. Sélectionnez **Créer une règle d’alerte.**

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

! [Exemple :::no-loc text="Azure Monitor"::: d’e-mail d’alerte](.. /media/Deploy-Azure-Monitor-6.png « Exemple de :::no-loc text="Azure Monitor"::: message d’alerte »)

## <a name="configure-all-devices-for-no-loc-textazure-monitoring"></a>Configurer tous les appareils pour :::no-loc text="Azure Monitoring":::
<a name="configure_all_devices"></a> Une fois les tableaux de bord et alertes configurés, vous pouvez configurer et configurer l’agent sur tous les appareils pour :::no-loc text="Microsoft Monitoring"::: terminer votre déploiement de :::no-loc text="Microsoft Teams Rooms"::: surveillance.

Bien que vous pouvez installer et configurer l’agent manuellement sur chaque appareil, nous vous recommandons vivement de tirer parti des méthodes et outils de déploiement de :::no-loc text="Microsoft Monitoring"::: logiciels existants.

Si vous créez vos appareils pour la première fois, vous souhaitez peut-être inclure les étapes de configuration de l’agent dans le cadre de :::no-loc text="Microsoft Teams Rooms"::: :::no-loc text="Microsoft Monitoring"::: votre processus de création. Pour plus d’informations, voir [Installer l’agent à l’aide de la ligne de commande.](/azure/azure-monitor/platform/agent-windows#install-the-agent-using-the-command-line)

### <a name="deploying-no-loc-textmicrosoft-monitoring-agent-by-using-a-group-policy-object-gpo"></a>Déploiement :::no-loc text="Microsoft Monitoring"::: d’un agent à l’aide d’un objet de stratégie de groupe

Si vous avez déjà déployé vos appareils avant de les implémenter, vous pouvez utiliser le script fourni pour configurer les agents à l’aide d’objets de stratégie :::no-loc text="Microsoft Teams Rooms"::: :::no-loc text="Azure Monitoring"::: de :::no-loc text="Active Directory"::: groupe.

1.  Créez un chemin réseau partagé et accordez l’accès en lecture au groupe **Ordinateurs de** domaine.

2.  Télécharger la version 64 bits de :::no-loc text="Microsoft Monitoring"::: l’Agent pour :::no-loc text="Windows":::<https://go.microsoft.com/fwlink/?LinkID=517476>

3.  Extraire le contenu du package d’installation dans le partage réseau.
    1.  Ouvrez une fenêtre d’invite de commandes, puis exécutez **MMASetup-AMD64.exe /c**
    2.  Spécifiez le partage que vous avez créé, puis extrayez le contenu.

4.  Créez un objet de stratégie de groupe et affectez-le à l’unité organisationnelle où se trouvent :::no-loc text="Microsoft Teams Rooms"::: les comptes d’ordinateurs.

5.  Configurer une stratégie d’exécution PowerShell :
    1.  Modifier l’objet de stratégie de groupe nouvellement créé et accéder aux composants de \\ \\ modèles d’administration Stratégies \\ :::no-loc text="Windows"::: \\ de configuration ordinateur :::no-loc text="Windows PowerShell":::
    2.  Activez **l’activer l’exécution de script** et définissez la stratégie **d’exécution** pour autoriser **les scripts locaux.**

6.  Configurez le script de démarrage :
    1.  Copiez le script suivant et enregistrez-le sous Install-MMAgent.ps1.
    2.  Modifiez les paramètres WorkspaceId, WorkspaceKey et SetupPath pour qu’ils correspondent à votre configuration.
    3.  Modifier le même objet de stratégie de groupe et accéder aux stratégies de configuration \\ \\ :::no-loc text="Windows"::: Paramètres \\ scripts (démarrage/arrêt)
    4.  Double-cliquez pour sélectionner **Démarrage,** puis **sélectionnez Scripts PowerShell.**
    5.  Sélectionnez **Afficher les** fichiers, puis copiez **leInstall-MMAgent.ps1** dans ce dossier.
    6.  Sélectionnez **Ajouter,** puis **Parcourir.**
    7.  Sélectionnez le script ps1 que vous viennent de copier.

7.  :::no-loc text="Microsoft Teams Rooms"::: les appareils doivent installer et configurer :::no-loc text="Microsoft Monitoring"::: l’agent avec le deuxième redémarrage.

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
> Vous pouvez consulter l’article Gérer et gérer l’agent lorsque vous avez besoin de reconfigurer un [ :::no-loc text="Log Analytics"::: agent,](/azure/azure-monitor/platform/agent-manage) de le déplacer vers un autre espace de travail ou de modifier les paramètres proxy après l’installation initiale.

## <a name="additional-solutions"></a>Autres solutions
<a name="Solutions"> </a>

:::no-loc text="Azure Monitor"::: fournit des solutions de gestion intégrées via sa [galerie](/azure/azure-monitor/insights/solutions) de solutions pour vous aider à surveiller votre environnement. Nous vous recommandons également d’ajouter des solutions [de](/azure/azure-monitor/platform/alert-management-solution) gestion des alertes et de santé de [ :::no-loc text="Azure Log Analytics"::: l’agent](/azure/azure-monitor/insights/solution-agenthealth) à votre espace de travail.

> [!NOTE]
> La solution d’état de l’agent peut vous aider à identifier les agents obsolètes ou rompus au sein de votre environnement, et la solution de gestion des alertes fournit des détails sur les alertes qui ont été élevées au cours d’une :::no-loc text="Microsoft Monitoring"::: période donnée.

## <a name="see-also"></a>Voir aussi

[Planifier :::no-loc text="Microsoft Teams Rooms"::: la gestion avec :::no-loc text="Azure Monitor":::](azure-monitor-plan.md)

[Gérer les :::no-loc text="Microsoft Teams Rooms"::: appareils avec :::no-loc text="Azure Monitor":::](azure-monitor-manage.md)
