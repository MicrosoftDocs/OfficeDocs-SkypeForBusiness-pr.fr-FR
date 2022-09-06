---
title: Déployer Salles Microsoft Teams surveillance avec Azure Monitor
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
- Teams_ITAdmin_Rooms
ms.assetid: d86ff657-ee92-4b06-aee3-d4c43090bdcb
description: Cet article explique comment déployer la surveillance des Salles Microsoft Teams de manière intégrée de bout en bout à l’aide d’Azure Monitor.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 5dbea45008024762f30d9555f4762c4377d2ed1f
ms.sourcegitcommit: 75dfc3cd9b59282d68e35e4d7185da572eb3795c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/06/2022
ms.locfileid: "67606413"
---
# <a name="deploy-no-loc-textmicrosoft-teams-rooms-monitoring-with-no-loc-textazure-monitor"></a>Déployer :::no-loc text="Microsoft Teams Rooms"::: la surveillance avec :::no-loc text="Azure Monitor":::

Cet article explique comment configurer et déployer une surveillance intégrée de bout en bout des appareils à l’aide :::no-loc text="Azure Monitor":::de :::no-loc text="Microsoft Teams Rooms"::: .

[!INCLUDE [teams-pro-license-requirement](../includes/teams-pro-license-requirement.md)]

Vous pouvez configurer :::no-loc text="Log Analytics"::: à l’intérieur :::no-loc text="Azure Monitor"::: pour fournir des données de télémétrie de base et des alertes qui vous aideront à gérer :::no-loc text="Microsoft Teams Rooms":::. À mesure que votre solution de gestion évolue, vous pouvez décider de déployer des données et des fonctionnalités de gestion supplémentaires pour créer une vue plus détaillée de la disponibilité et des performances des appareils.

En suivant ce guide, vous pouvez utiliser un tableau de bord comme l’exemple suivant pour obtenir des rapports d’état détaillés sur la disponibilité des appareils, l’intégrité des applications et du matériel, ainsi que :::no-loc text="Microsoft Teams Rooms"::: la distribution des versions des applications et du système d’exploitation.

![Capture d’écran de l’exemple de vue Log Analytics pour Salles Microsoft Teams.](../media/Deploy-Azure-Monitor-1.png "Exemple de vue Log Analytics pour Salles Microsoft Teams")

À haut niveau, vous devez effectuer les tâches suivantes :


1. [Valider la :::no-loc text="Log Analytics"::: configuration](azure-monitor-deploy.md#validate_LogAnalytics)
2. [Configurer des appareils de test pour :::no-loc text="Log Analytics"::: la configuration de la gestion](azure-monitor-deploy.md#configure_test_devices)
3. [Mapper les champs personnalisés](azure-monitor-deploy.md#Custom_fields)
4. [Définir les :::no-loc text="Microsoft Teams Rooms"::: vues dans :::no-loc text="Log Analytics":::](azure-monitor-deploy.md#Define_Views)
5. [Définir des alertes](azure-monitor-deploy.md#Alerts)
6. [Configurer tous les appareils pour la surveillance](azure-monitor-deploy.md#configure_all_devices)
7. [Configurer des solutions supplémentaires :::no-loc text="Azure Monitor":::](azure-monitor-deploy.md#Solutions)

> [!IMPORTANT]
> Bien qu’avec une configuration minimale, :::no-loc text="Azure Monitor"::: :::no-loc text="Log Analytics"::: vous puissiez surveiller un ordinateur exécutant un :::no-loc text="Windows"::: système d’exploitation, vous devez effectuer certaines :::no-loc text="Microsoft Teams Rooms":::étapes spécifiques avant de commencer à déployer des agents sur tous les :::no-loc text="Microsoft Teams Rooms"::: appareils.
> Par conséquent, nous vous recommandons vivement d’effectuer toutes les étapes de configuration dans le bon ordre pour une configuration et une configuration contrôlées. La qualité du résultat final dépend beaucoup de la qualité de la configuration initiale.

## <a name="validate-no-loc-textlog-analytics-configuration"></a>Valider la :::no-loc text="Log Analytics"::: configuration
<a name="validate_LogAnalytics"> </a>

Vous devez disposer d’un :::no-loc text="Log Analytics"::: espace de travail pour commencer à collecter les journaux à partir de :::no-loc text="Microsoft Teams Rooms":::. Un espace de travail est un environnement unique :::no-loc text="Log Analytics"::: avec son propre référentiel de données, ses sources de données et ses propres solutions. Si vous disposez déjà d’un espace de travail existant :::no-loc text="Log Analytics"::: , vous pouvez l’utiliser pour surveiller votre :::no-loc text="Microsoft Teams Rooms"::: déploiement ou vous pouvez également créer un espace de travail dédié :::no-loc text="Log Analytics"::: spécifique à vos :::no-loc text="Microsoft Teams Rooms"::: besoins de supervision.

Si vous devez créer un espace :::no-loc text="Log Analytics"::: de travail, suivez les instructions de l’article [Créer un :::no-loc text="Log Analytics"::: espace de travail dans le :::no-loc text="Azure"::: portail](/azure/azure-monitor/learn/quick-create-workspace)

> [!NOTE]
> Pour l’utiliser :::no-loc text="Log Analytics"::: , :::no-loc text="Azure Monitor":::vous devez disposer d’un abonnement actif :::no-loc text="Azure"::: . Si vous n’avez pas d’abonnement :::no-loc text="Azure"::: , vous pouvez créer [un abonnement d’essai gratuit](https://azure.microsoft.com/free) comme point de départ.

### <a name="configure-no-loc-textlog-analytics-to-collect-no-loc-textmicrosoft-teams-rooms-event-logs"></a>Configurer :::no-loc text="Log Analytics"::: pour collecter les journaux des :::no-loc text="Microsoft Teams Rooms"::: événements

:::no-loc text="Log Analytics"::: collecte uniquement les événements des :::no-loc text="Windows"::: journaux des événements spécifiés dans les paramètres. Pour chaque journal, seuls les événements avec les gravités sélectionnées sont collectés.

Vous devez configurer :::no-loc text="Log Analytics"::: pour collecter les journaux nécessaires pour surveiller :::no-loc text="Microsoft Teams Rooms"::: l’état de l’appareil et de l’application. :::no-loc text="Microsoft Teams Rooms"::: utiliser le journal des **:::no-loc text="Skype Room System":::** événements.

Pour configurer :::no-loc text="Log Analytics"::: la collecte des événements, consultez [:::no-loc text="Windows"::: les sources de données du journal des événements dans :::no-loc text="Azure Monitor":::](/azure/azure-monitor/platform/data-sources-windows-events) :::no-loc text="Microsoft Teams Rooms":::

![Capture d’écran des paramètres du journal des événements.](../media/Deploy-Azure-Monitor-2.png "Paramètres du journal des événements")

> [!IMPORTANT]
> :::no-loc text="Windows"::: Configurez les paramètres du journal des événements et entrez **:::no-loc text="Skype Room System":::** le nom du journal des événements, puis activez les cases **à** cocher Erreur, **Avertissement** et **Informations**.

## <a name="configure-test-devices-for-azure-monitoring"></a>Configurer des appareils de test pour Azure Monitoring
<a name="configure_test_devices"> </a>

Vous devez vous préparer :::no-loc text="Log Analytics"::: pour pouvoir surveiller les :::no-loc text="Microsoft Teams Rooms":::événements liés à –. Pour commencer, vous devez déployer :::no-loc text="Microsoft Monitoring"::: des agents sur un ou deux :::no-loc text="Microsoft Teams Rooms"::: appareils auxquels vous avez accès physiquement, et obtenir ces appareils de test pour générer des données et les envoyer à l’espace :::no-loc text="Log Analytics"::: de travail.

### <a name="install-no-loc-textmicrosoft-monitoring-agents-to-test-devices"></a>Installer des :::no-loc text="Microsoft Monitoring"::: agents pour tester des appareils

Déployez l’agent :::no-loc text="Microsoft Monitoring"::: sur les appareils de test en suivant les instructions [fournies dans Connecter :::no-loc text="Windows"::: des ordinateurs au :::no-loc text="Log Analytics"::: service dans :::no-loc text="Azure":::](/azure/azure-monitor/platform/agent-windows). Cet article fournit des informations détaillées sur les étapes de déploiement :::no-loc text="Microsoft Monitoring"::: de l’Agent, :::no-loc text="Windows":::des instructions pour obtenir **l’ID** _ de l’espace :::no-loc text="Log Analytics"::: * de travail et la _ *_clé primaire_** pour connecter :::no-loc text="Microsoft Teams Rooms"::: les appareils à votre :::no-loc text="Azure Monitor"::: déploiement, ainsi que des étapes pour vérifier la connectivité de l’agent à :::no-loc text="Log Analytics"::: l’instance.

### <a name="generate-sample-no-loc-textmicrosoft-teams-rooms-events"></a>Générer des exemples d’événements :::no-loc text="Microsoft Teams Rooms":::

Une fois l’agent :::no-loc text="Microsoft Monitoring"::: déployé sur les appareils de test, vérifiez que les données de journal des événements requises sont collectées par :::no-loc text="Azure Monitor":::.

> [!NOTE]
> Redémarrez l’appareil après l’installation de l’agent et assurez-vous que :::no-loc text="Microsoft Teams Rooms"::: l’application :::no-loc text="Microsoft Monitoring"::: réunion est démarrée afin qu’elle puisse générer de nouveaux événements dans le journal des événements.

1.  Connectez-vous au [:::no-loc text="Microsoft Azure"::: portail](https://portal.azure.com) et sélectionnez :::no-loc text="Log Analytics"::: votre espace de travail.

2.  Répertoriez les événements de pulsation générés par un :::no-loc text="Microsoft Teams Rooms"::: appareil :
    1.  Sélectionnez votre espace de travail, accédez aux journaux et utilisez une requête pour récupérer les enregistrements de pulsation qui auront les champs **personnalisés** pour :::no-loc text="Microsoft Teams Rooms":::.
    2.  Exemple de requête : `Event | where Source == "SRS-App" and EventID == 2000`

3.  Assurez-vous que la requête retourne des enregistrements de journal qui incluent des événements générés par l’application :::no-loc text="Microsoft Teams Rooms"::: réunions.

4.  Générez un problème matériel et vérifiez que les événements requis sont connectés :::no-loc text="Azure Log Analytics":::.
    1.  Débranchez l’un des périphériques sur le système de test :::no-loc text="Microsoft Teams Rooms"::: . Il peut s’agir de l’appareil photo, du haut-parleur, du microphone ou de l’affichage de la salle d’entrée
    2.  Attendez 10 minutes que le journal des événements soit renseigné.:::no-loc text="Azure Log Analytics":::
    3.  Utilisez une requête pour répertorier les événements d’erreur matérielle : `Event | where Source == "SRS-App" and EventID == 3001`

5.  Générez un problème d’application et vérifiez que les événements requis sont enregistrés.
    1.  Modifiez :::no-loc text="Microsoft Teams Rooms"::: la configuration du compte et tapez une paire Email/mot de passe incorrecte.
    2.  Attendez 10 minutes que le journal des événements soit renseigné.:::no-loc text="Azure Log Analytics":::
    3.  Utilisez une requête pour répertorier les événements d’erreur d’application : `Event | where Source == "SRS-App" and EventID == 2001 and EventLevel == 1`

> [!IMPORTANT]
> Ces exemples de journaux des événements sont requis avant que les champs personnalisés puissent être configurés. Ne passez pas à l’étape suivante tant que vous n’avez pas collecté les journaux des événements requis.

## <a name="map-custom-fields"></a>Mapper les champs personnalisés
<a name="Custom_fields"> </a>

Vous utilisez des champs personnalisés pour extraire des données spécifiques des journaux des événements. Vous devez définir des champs personnalisés qui seront utilisés ultérieurement avec vos vignettes, vues de tableau de bord et alertes. Consultez [les champs personnalisés et :::no-loc text="Log Analytics":::](/azure/azure-monitor/platform/custom-fields) familiarisez-vous avec les concepts avant de commencer à créer vos champs personnalisés.

Pour extraire vos champs personnalisés des journaux des événements capturés, procédez comme suit :

1.  Connectez-vous au [:::no-loc text="Microsoft Azure"::: portail](https://portal.azure.com) et sélectionnez :::no-loc text="Log Analytics"::: votre espace de travail.

2. Répertoriez les événements générés par un :::no-loc text="Microsoft Teams Rooms"::: appareil :
   1.  Accédez aux **journaux** et utilisez une requête pour récupérer les enregistrements qui auront le champ personnalisé.
   2.  Exemple de requête : `Event | where Source == "SRS-App" and EventID == 2000`

3. Sélectionnez l’un des enregistrements, sélectionnez le bouton à gauche, puis démarrez l’Assistant Extraction de champ.
4. Mettez en surbrillance les données que vous souhaitez extraire de RenderedDescription et fournissez un titre de champ. Les noms de champs que vous devez utiliser sont fournis dans le tableau 1.
5. Utilisez les mappages indiqués dans le *tableau 1*. :::no-loc text="Log Analytics"::: ajoute automatiquement la **\_chaîne CF** lorsque vous définissez le nouveau champ.

> [!IMPORTANT]
> N’oubliez pas que tous les champs et :::no-loc text="Log Analytics"::: JSON respectent la casse.
> 
> Faites attention aux requêtes requises pour chaque champ personnalisé dans le tableau ci-dessous. Vous devez utiliser les requêtes appropriées pour :::no-loc text="Log Analytics"::: extraire correctement des valeurs de champ personnalisées.
> 
**Tableau 1**

| **Champ JSON**                   | **:::no-loc text="Log Analytics"::: champ personnalisé** | **ID d’événement** | **Requête à utiliser avec l’extraction**                   |
|:---------------------------------|:-------------------------------|:-------------|:-------------------------------------------------------|
| Description                      | SRSEventDescription         | **2000**     | Événement \| où Source == « SRS-App » et EventID == 2000 |
| ResourceState                    | SRSResourceState            | **2000**     | Événement \| où Source == « SRS-App » et EventID == 2000 |
| OperationName                    | SRSOperationName            | **2000**     | Événement \| où Source == « SRS-App » et EventID == 2000 |
| OperationResult                  | SRSOperationResult          | **2000**     | Événement \| où Source == « SRS-App » et EventID == 2000 |
| OS                               | SRSOSVersion                | **2000**     | Événement \| où Source == « SRS-App » et EventID == 2000 |
| OSVersion                        | SRSOSLongVersion            | **2000**     | Événement \| où Source == « SRS-App » et EventID == 2000 |
| Alias                            | SRSAlias                    | **2000**     | Événement \| où Source == « SRS-App » et EventID == 2000 |
| DisplayName                      | SRSDisplayName              | **2000**     | Événement \| où Source == « SRS-App » et EventID == 2000 |
| AppVersion                       | SRSAppVersion               | **2000**     | Événement \| où Source == « SRS-App » et EventID == 2000 |
| IPv4Address                      | SRSIPv4Address              | **2000**     | Événement \| où Source == « SRS-App » et EventID == 2000 |
| IPv6Address                      | SRSIPv6Address              | **2000**     | Événement \| où Source == « SRS-App » et EventID == 2000 |
| État du microphone de conférence     | SRSConfMicrophoneStatus     | **3001**     | Événement \| où Source == « SRS-App » et EventID == 3001 |
| Statut de l’orateur de conférence        | SRSConfSpeakerStatus        | **3001**     | Événement \| où Source == « SRS-App » et EventID == 3001 |
| État de l’orateur par défaut           | SRSDefaultSpeakerStatus     | **3001**     | Événement \| où Source == « SRS-App » et EventID == 3001 |
| État de l’appareil photo                    | SRSCameraStatus             | **3001**     | Événement \| où Source == « SRS-App » et EventID == 3001 |
| État de l’affichage de l’avant de la salle     | SRSFORDStatus               | **3001**     | Événement \| où Source == « SRS-App » et EventID == 3001 |
| État du capteur de mouvement             | SRSMotionSensorStatus       | **3001**     | Événement \| où Source == « SRS-App » et EventID == 3001 |
| État d’ingestion HDMI               | SRSHDMIIngestStatus         | **3001**     | Événement \| où Source == « SRS-App » et EventID == 3001 |


## <a name="define-the-no-loc-textmicrosoft-teams-rooms-views-in-no-loc-textlog-analytics"></a>Définir les :::no-loc text="Microsoft Teams Rooms"::: vues dans :::no-loc text="Log Analytics":::
<a name="Define_Views"> </a>

Une fois les données collectées et les champs personnalisés mappés, vous pouvez utiliser le Concepteur de vues pour développer un tableau de bord contenant différentes vignettes pour surveiller :::no-loc text="Microsoft Teams Rooms"::: les événements. Utilisez le concepteur de vues pour créer les mosaïques suivantes. Pour plus d’informations, consultez [Créer des vues personnalisées à l’aide du Concepteur de vues dans :::no-loc text="Log Analytics":::](/azure/azure-monitor/platform/view-designer)

> [!NOTE]
> Les étapes précédentes de ce guide doivent avoir été effectuées pour que les vignettes du tableau de bord fonctionnent correctement.
>
> [!IMPORTANT]
> [Le Concepteur de vues dans Azure Monitor prend sa retraite le 31 août 2023](https://azure.microsoft.com/updates/view-designer-in-azure-monitor-is-retiring-on-31-august-2023/) et les fonctionnalités de création et de clonage ont été désactivées le 30 novembre 2020. Les classeurs peuvent être utilisés à la place. Pour plus d’informations sur le guide de transition du concepteur de vues vers des classeurs, consultez [démarrage rapide avec des modèles de concepteur de vues prédéfinis](/azure/azure-monitor/visualize/view-designer-conversion-tasks#quickstart-with-preset-view-designer-templates).

### <a name="create-a-microsoft-teams-rooms-dashboard-manually"></a>Créer un tableau de bord Salles Microsoft Teams manuellement

Vous pouvez également créer votre propre tableau de bord et ajouter uniquement les vignettes que vous souhaitez surveiller.

#### <a name="configure-the-overview-tile"></a>Configurer la vignette Vue d’ensemble

1.  Ouvrez **le Concepteur de vues**.
2.  Sélectionnez **Vignette Vue d’ensemble**, puis **deux nombres** dans la galerie.
3.  Nommez la vignette **:::no-loc text="Microsoft Teams Rooms":::**.
4.  Définissez la **première vignette** :<br>
    **Légende:** Appareils qui ont envoyé une pulsation au moins une fois au cours du dernier mois<br>
    **Requête:** ```Event | where EventLog == "Skype Room System" and TimeGenerated > ago(30d) | summarize TotalSRSDevices = dcount(Computer)```
5.  Définissez la **deuxième vignette** :<br>
    **Légende:** Appareils actifs qui ont envoyé une pulsation au cours de la dernière heure<br>
    **Requête:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(1h) | summarize TotalSRSDevices = dcount(Computer)```
6.  Sélectionnez **Appliquer**.

### <a name="create-a-tile-that-displays-active-devices"></a>Créer une vignette qui affiche les appareils actifs

1.  Sélectionnez **Afficher le tableau de bord** pour commencer à ajouter vos vignettes.
2.  Sélectionnez **Nombre & liste** dans la galerie
3.  Définissez les propriétés **générales** :<br>
    **Titre du groupe :** État des pulsations<br>
    **Nouveau groupe :** Sélectionné
4.  Définissez les propriétés de la **vignette** :<br>
    **Légende:** Appareils actifs (pulsation envoyée au cours des 20 dernières minutes)<br>
    **Requête de mosaïque :** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize AggregatedValue = count() by Computer | count```
5.  Définissez les propriétés **de liste** :<br>
    **Requête de liste :** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
6.  Définir les **titres des colonnes** :<br>
    **Nom:** Nom de l’ordinateur<br>
    **Valeur:** Dernière pulsation
7.  Définir une **requête de navigation**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  Sélectionnez **Appliquer**, puis **Fermez**.

### <a name="create-a-tile-that-displays-devices-that-have-connectivity-issues"></a>Créer une vignette qui affiche les appareils qui présentent des problèmes de connectivité

1.  Sélectionnez **Nombre & liste** dans la galerie, puis ajoutez une nouvelle vignette.
2.  Définissez les propriétés **générales** :<br>
    **Titre du groupe :** Laisser vide<br>
    **Nouveau groupe :** Non sélectionné
3.  Définissez les propriétés de la **vignette** :<br>
    **Légende:** Appareils inactifs (aucun message de pulsation envoyé au cours des 20 dernières minutes)<br>
    **Requête de mosaïque :** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize LastHB = max(TimeGenerated) by Computer | where LastHB < ago(20m) | count```
4.  Définissez les propriétés **de liste** :<br>
    **Requête de liste :** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize TimeGenerated = max(TimeGenerated) by Computer | where TimeGenerated < ago(20m) | order by TimeGenerated```
5.  Définir les **titres des colonnes** :<br>
    **Nom:** Nom de l’ordinateur<br>
    **Valeur:** Dernière pulsation
6.  Définir une **requête de navigation** :<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
7.  Sélectionnez **Appliquer**, puis **Fermez**.

### <a name="create-a-tile-that-displays-devices-that-have-a-hardware-error"></a>Créer une vignette qui affiche les appareils qui présentent une erreur matérielle

1.  Sélectionnez **Nombre & liste** dans la galerie, puis ajoutez une nouvelle vignette.
2.  Définissez les propriétés **générales** :<br>
    **Titre du groupe :** État du matériel<br>
    **Nouveau groupe :** Sélectionné
3.  Définissez les propriétés de la **vignette** :<br>
    **Légende:** Appareils qui ont rencontré une erreur matérielle au cours de la dernière heure<br>
    **Requête de mosaïque :** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```
4.  Définissez les propriétés **de liste** :<br>
    **Requête de liste :** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
5.  Définir les **titres des colonnes** :<br>
    **Nom:** Nom de l’ordinateur<br>
    **Valeur:** Dernière erreur
6.  Définir une **requête de navigation** :<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == 3001 and EventLevelName == "Error" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSConfMicrophoneStatus_CF, SRSConfSpeakerStatus_CF, SRSDefaultSpeakerStatus_CF, SRSCameraStatus_CF, SRSFORDStatus_CF, SRSMotionSensorStatus_CF, SRSHDMIIngestStatus_CF, SRSEventDescription_CF | sort by TimeGenerated desc```
7.  Sélectionnez **Appliquer**, puis **Fermez**.

### <a name="create-a-tile-that-displays-no-loc-textmicrosoft-teams-rooms-operating-system-versions"></a>Créer une vignette qui affiche :::no-loc text="Microsoft Teams Rooms"::: les versions du système d’exploitation

1.  Sélectionnez **Donut & liste** dans la galerie, puis ajoutez une nouvelle vignette.
2.  Définissez les propriétés **générales** :<br>
    **Titre du groupe :** Détails du système d’exploitation<br>
    **Nouveau groupe :** Sélectionné
3.  Définissez les propriétés **d’en-tête** :<br>
    **Titre:** Versions du système d’exploitation<br>
    **Sous-titre:** Appareils exécutant des versions de système d’exploitation spécifiques
4.  Définissez les propriétés **donut** :<br>
    **Requête:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize OS_Version = max(SRSOSLongVersion_CF) by Computer | summarize AggregatedValue = count() by OS_Version | sort by OS_Version asc```<br>
    **Texte central :** Dispositifs<br>
    **Opération:** Somme
5.  Définissez les propriétés **de liste** .<br>
    **Requête de liste :** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSOSLongVersion_CF = max(SRSOSLongVersion_CF) by Computer | sort by Computer asc```<br>
    **Masquer le graphique :** Sélectionné<br>
    **Activez sparklines :** Non sélectionné
6.  Définir les **titres des colonnes**.<br>
    **Nom:** Nom de l’ordinateur<br>
    **Valeur:** Laisser vide
7.  Définir une **requête de navigation**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSDisplayName_CF, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  Sélectionnez **Appliquer** , puis **Fermez**.

### <a name="create-a-tile-that-displays-no-loc-textmicrosoft-teams-rooms-application-versions"></a>Créer une vignette qui affiche les :::no-loc text="Microsoft Teams Rooms"::: versions d’application

1.  Sélectionnez **Donut & liste** dans la galerie, puis ajoutez une nouvelle vignette.
2.  Définissez les propriétés **générales** :<br>
    **Titre du groupe :** :::no-loc text="Microsoft Teams Rooms"::: détails de l’application<br>
    **Nouveau groupe :** Sélectionné
3.  Définissez les propriétés **d’en-tête** :<br>
    **Titre:** Versions d’application<br>
    **Sous-titre:** Appareils exécutant des versions d’application spécifiques
4.  Définissez les propriétés **donut** :<br>
    **Requête:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize App_Version = max(SRSAppVersion_CF) by Computer | summarize AggregatedValue = count() by App_Version | sort by App_Version asc```<br>
    **Texte central :** Dispositifs<br>
    **Opération:** Somme
5.  Définissez les propriétés **de liste** .<br>
    **Requête de liste :** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSAppVersion_CF = max(SRSAppVersion_CF) by Computer | sort by Computer asc```<br>
    **Masquer le graphique :** Sélectionné<br>
    **Activez sparklines :** Non sélectionné
6.  Définir les **titres des colonnes**.<br>
    **Nom:** Nom de l’ordinateur<br>
    **Valeur:** Laisser vide
7.  Définir une **requête de navigation**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  Sélectionnez **Appliquer** , puis **Fermez**.

### <a name="create-a-tile-that-displays-devices-that-have-an-application-error"></a>Créer une vignette qui affiche les appareils qui présentent une erreur d’application

1.  Sélectionnez **Nombre & liste** dans la galerie, puis ajoutez une nouvelle vignette.
2.  Définissez les propriétés **générales** .<br>
    **Titre du groupe :** Laisser vide<br>
    **Nouveau groupe :** Non sélectionné
3.  Définissez les propriétés de la **vignette** .<br>
    **Légende:** Appareils qui ont rencontré une erreur d’application au cours de la dernière heure<br>
    **Requête de mosaïque :** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```
4.  Définissez les propriétés **de liste** .<br>
    **Requête de liste :** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
5.  Définir les **titres des colonnes**.<br>
    **Nom:** Nom de l’ordinateur<br>
    **Valeur:** Dernière erreur
6.  Définir une **requête de navigation**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == 2001 and EventLevelName == "Error" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF | sort by TimeGenerated desc```
7.  Sélectionnez **Appliquer** , puis **Fermez**.

### <a name="create-a-tile-that-displays-devices-that-have-been-restarted"></a>Créer une vignette qui affiche les appareils qui ont été redémarrés

1.  Sélectionnez **Nombre & liste** dans la galerie, puis ajoutez une nouvelle vignette.
2.  Définissez les propriétés **générales** .<br>
    **Titre du groupe :** Laisser vide<br>
    **Nouveau groupe :** Non sélectionné
3.  Définissez les propriétés de la **vignette** .<br>
    **Légende:** Appareils sur lesquels l’application a été redémarrée au cours des dernières 24 heures et nombre de redémarrages<br>
    **Requête de mosaïque :** ```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | summarize AggregatedValue = count() by Computer | count```
4.  Définissez les propriétés **de liste** .<br>
    **Requête de liste :** ```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | order by TimeGenerated | summarize AggregatedValue = count(EventID) by Computer```
5.  Définir les **titres des colonnes**.<br>
    **Nom:** Nom de l’ordinateur<br>
    **Valeur:** Nombre de redémarrages
6.  Définir une **requête de navigation**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
7.  Sélectionnez **Appliquer** , puis **Fermez**.
8.  Sélectionnez **Enregistrer** pour enregistrer votre tableau de bord.

Vous avez maintenant terminé la création de vos vues.

## <a name="configure-alerts-in-no-loc-textazure-monitor"></a>Configurer des alertes dans :::no-loc text="Azure Monitor":::
<a name="Alerts"> </a>

:::no-loc text="Azure Monitor"::: peut déclencher des alertes pour avertir les administrateurs lorsqu’une :::no-loc text="Microsoft Teams Rooms"::: console rencontre un problème.

:::no-loc text="Azure Monitor"::: inclut un mécanisme d’alerte intégré qui s’exécute via des recherches de journal planifiées à intervalles réguliers. Si les résultats de la recherche dans les journaux correspondent à certains critères particuliers, un enregistrement d’alerte est créé.

La règle peut ensuite exécuter automatiquement une ou plusieurs actions pour vous avertir de manière proactive de l’alerte ou appeler un autre processus. Les options possibles avec les alertes sont les suivantes :
-   Envoi d’un e-mail
-   Appel d’un processus externe via une requête HTTP POST
-   Démarrage d’un runbook en :::no-loc text="Azure Automation"::: service

Consultez [les alertes de journal pour en :::no-loc text="Azure Monitor":::](/azure/azure-monitor/platform/alerts-unified-log) savoir plus sur les alertes dans :::no-loc text="Azure Monitor":::.

> [!NOTE]
> Les exemples suivants envoient des alertes par e-mail lorsqu’un :::no-loc text="Microsoft Teams Rooms"::: appareil génère un matériel ou une erreur d’application.

### <a name="configure-an-email-alert-for-no-loc-textmicrosoft-teams-rooms-hardware-issues"></a>Configurer une alerte par e-mail pour :::no-loc text="Microsoft Teams Rooms"::: les problèmes matériels

Configurez une règle d’alerte qui recherche les :::no-loc text="Microsoft Teams Rooms"::: appareils qui ont rencontré des problèmes matériels au cours de la dernière heure.
1.  Connectez-vous au [:::no-loc text="Microsoft Azure"::: portail](https://portal.azure.com) et sélectionnez :::no-loc text="Log Analytics"::: votre espace de travail.

2. Accédez à votre :::no-loc text="Log Analytics"::: espace de travail, sélectionnez **Alertes** , puis sélectionnez **Nouvelle règle d’alerte**

3. Sélectionnez **Ajouter une condition** , puis **Recherche dans les journaux personnalisés**

4.  Entrez la requête suivante dans la zone de texte De la requête de recherche.<br>
    ```
    Event
    | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h)
    | summarize arg_max(TimeGenerated, *) by Computer
    | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSConfMicrophoneStatus_CF, SRSConfSpeakerStatus_CF, SRSDefaultSpeakerStatus_CF, SRSCameraStatus_CF, SRSFORDStatus_CF, SRSMotionSensorStatus_CF, SRSHDMIIngestStatus_CF, SRSEventDescription_CF
    |sort by TimeGenerated desc
    ```

5.  Configurez les paramètres de logique d’alerte :<br>
    **Sur la base de :** Nombre de résultats<br>
    **Condition:** Supérieur à<br>
    **Seuil :** 0<br>

6. Configurez les paramètres d’évaluation et sélectionnez **Terminé** : <br>
    **Période (en minutes) :** 60<br>
    **Fréquence (en minutes) :** 60<br>

7. Configurer des groupes d’actions :
    1.  Sélectionnez **Créer nouveau**
    2.  Fournissez des noms appropriés pour le *nom du groupe d’actions* et les champs *Nom court* .
    3.  Spécifiez un *nom d’action* unique, sélectionnez **Email/SMS/Push/Voice**, puis **sélectionnez Modifier les détails**.
    4.  Cochez la **case Email** et indiquez l’adresse e-mail de la personne ou du groupe qui recevra les alertes.
    5.  Vous pouvez également fournir votre numéro de téléphone pour recevoir une notification par SMS, un appel vocal ou les deux.
    6. Sélectionnez **OK**.

8. **Personnalisez les actions** si vous souhaitez remplacer la ligne d’objet des e-mails d’alerte.

9. Spécifiez un nom de règle et une description.<br>
    **Nom de la règle :** :::no-loc text="Microsoft Teams Rooms"::: Alerte de défaillance matérielle<br>
    **Description:** Liste des appareils qui ont rencontré un problème matériel au cours de la dernière heure<br>

10. Sélectionnez la gravité prévue et vérifiez que la règle est activée.

11. Sélectionnez **Créer une règle d’alerte**.

### <a name="configure-an-email-alert-for-no-loc-textmicrosoft-teams-rooms-application-issues"></a>Configurer une alerte par e-mail pour :::no-loc text="Microsoft Teams Rooms"::: les problèmes d’application

Répétez la même procédure, mais utilisez la requête suivante pour répertorier les appareils qui ont rencontré des problèmes d’application au cours de la dernière heure.

 ```
 Event
 | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h)
 | summarize arg_max(TimeGenerated, *) by Computer
 | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF
 | sort by TimeGenerated desc
 ```

Vous avez maintenant terminé la définition des alertes. Vous pouvez définir des alertes supplémentaires à l’aide des exemples ci-dessus.

Lorsqu’une alerte est générée, vous recevez un e-mail qui répertorie les appareils qui ont rencontré un problème au cours de la dernière heure.

! [Exemple d’e-mail :::no-loc text="Azure Monitor"::: d’alerte](.. /media/Deploy-Azure-Monitor-6.png « Exemple d’e-mail :::no-loc text="Azure Monitor"::: d’alerte »)

## <a name="configure-all-devices-for-no-loc-textazure-monitoring"></a>Configurer tous les appareils pour :::no-loc text="Azure Monitoring":::
<a name="configure_all_devices"> </a> Une fois les tableaux de bord et les alertes configurés, vous pouvez configurer et configurer :::no-loc text="Microsoft Monitoring"::: l’agent sur tous les :::no-loc text="Microsoft Teams Rooms"::: appareils pour terminer votre déploiement de supervision.

Bien que vous puissiez installer et configurer l’agent :::no-loc text="Microsoft Monitoring"::: manuellement sur chaque appareil, nous vous recommandons vivement de tirer parti des méthodes et outils de déploiement de logiciels existants.

Si vous créez vos :::no-loc text="Microsoft Teams Rooms"::: appareils pour la première fois, vous souhaiterez peut-être inclure les étapes de configuration et de configuration de l’agent :::no-loc text="Microsoft Monitoring"::: dans le cadre de votre processus de génération. Pour plus d’informations, consultez [Installer l’agent à l’aide de la ligne de commande](/azure/azure-monitor/platform/agent-windows#install-the-agent-using-the-command-line).

### <a name="deploying-no-loc-textmicrosoft-monitoring-agent-by-using-a-group-policy-object-gpo"></a>Déploiement de l’agent à :::no-loc text="Microsoft Monitoring"::: l’aide d’un objet stratégie de groupe (GPO)

Si vous avez déjà déployé vos :::no-loc text="Microsoft Teams Rooms"::: appareils avant d’implémenter :::no-loc text="Azure Monitoring":::, vous pouvez utiliser le script fourni pour configurer et configurer les agents à l’aide d’objets :::no-loc text="Active Directory"::: de stratégie de groupe.

1.  Créez un chemin d’accès réseau partagé et accordez un accès en lecture au groupe **Ordinateurs de domaine** .

2.  Téléchargez la version 64 bits de l’Agent :::no-loc text="Microsoft Monitoring"::: à :::no-loc text="Windows"::: partir de <https://go.microsoft.com/fwlink/?LinkID=517476>

3.  Extrayez le contenu du package d’installation dans le partage réseau.
    1.  Ouvrez une fenêtre d’invite de commandes, puis exécutez **MMASetup-AMD64.exe /c**
    2.  Spécifiez le partage que vous venez de créer et extrayez le contenu.

4.  Créez un objet stratégie de groupe et attribuez-le à l’unité organisationnelle où :::no-loc text="Microsoft Teams Rooms"::: se trouvent les comptes de machine.

5.  Configurer la stratégie d’exécution PowerShell :
    1.  Modifier l’objet stratégie de groupe nouvellement créé et accéder aux composants des modèles d’administration des :::no-loc text="Windows"::: \\ stratégies de configuration \\ \\ de \\ l’ordinateur :::no-loc text="Windows PowerShell":::
    2.  Activez **l’exécution du script** et définissez la stratégie **d’exécution** pour **autoriser les scripts locaux**.

6.  Configurez le script de démarrage :
    1.  Copiez le script suivant et enregistrez-le en tant que Install-MMAgent.ps1.
    2.  Modifiez les paramètres WorkspaceId, WorkspaceKey et SetupPath pour qu’ils correspondent à votre configuration.
    3.  Modifiez le même objet stratégie de groupe et accédez aux scripts de paramètres des \\ stratégies de configuration \\ \\ :::no-loc text="Windows"::: de l’ordinateur (démarrage/arrêt)
    4.  Double-cliquez pour sélectionner **Démarrage**, puis sélectionnez **Scripts PowerShell**.
    5.  Sélectionnez **Afficher les fichiers**, puis copiez le fichier **Install-MMAgent.ps1** dans ce dossier.
    6.  Sélectionnez **Ajouter**, puis **Parcourir**.
    7.  Sélectionnez le script ps1 que vous venez de copier.

7.  :::no-loc text="Microsoft Teams Rooms"::: doit installer et configurer l’agent :::no-loc text="Microsoft Monitoring"::: avec le deuxième redémarrage.

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
> Vous pouvez consulter l’article [Gestion et maintenance de l’agent :::no-loc text="Log Analytics":::](/azure/azure-monitor/platform/agent-manage) lorsque vous devez reconfigurer un agent, le déplacer vers un autre espace de travail ou modifier les paramètres de proxy après l’installation initiale.

## <a name="additional-solutions"></a>Solutions supplémentaires
<a name="Solutions"> </a>

:::no-loc text="Azure Monitor"::: fournit des solutions de gestion intégrées par le biais de sa [galerie de solutions](/azure/azure-monitor/insights/solutions) pour vous aider à surveiller votre environnement. Nous vous recommandons vivement d’ajouter des solutions [de gestion des alertes](/azure/azure-monitor/platform/alert-management-solution) et [:::no-loc text="Azure Log Analytics"::: d’intégrité de l’agent](/azure/azure-monitor/insights/solution-agenthealth) à votre espace de travail.

> [!NOTE]
> La solution Agent Health peut vous aider à identifier les agents obsolètes ou rompus :::no-loc text="Microsoft Monitoring"::: au sein de votre environnement, et la solution Gestion des alertes fournit des détails sur les alertes qui ont été déclenchées au cours d’une période donnée.

## <a name="see-also"></a>Voir aussi

[Gestion des plans :::no-loc text="Microsoft Teams Rooms"::: avec :::no-loc text="Azure Monitor":::](azure-monitor-plan.md)

[Gérer les :::no-loc text="Microsoft Teams Rooms"::: appareils avec :::no-loc text="Azure Monitor":::](azure-monitor-manage.md)
