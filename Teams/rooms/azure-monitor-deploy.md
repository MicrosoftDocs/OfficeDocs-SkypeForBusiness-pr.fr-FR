---
title: Déploiement de la gestion de salles de Microsoft teams avec Azure Monitor
ms.author: v-lanac
author: lanachin
ms.reviewer: Turgayo
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.assetid: d86ff657-ee92-4b06-aee3-d4c43090bdcb
description: Cet article décrit le déploiement de la gestion des appareils Microsoft teams salles de manière intégrée et complète grâce à l’utilisation de moniteur Azure.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 3c1ecb3906eec551ddaed9a2c748a66c9da7ac9a
ms.sourcegitcommit: 67c686810d37bffda72a6e92155d9c8ec86bfae6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/15/2020
ms.locfileid: "47766878"
---
# <a name="deploy-no-loc-textmicrosoft-teams-rooms-management-with-no-loc-textazure-monitor"></a>Déploiement :::no-loc text="Microsoft Teams Rooms"::: de la gestion avec :::no-loc text="Azure Monitor":::

Cet article décrit la configuration et le déploiement de la gestion intégrée et complète des :::no-loc text="Microsoft Teams Rooms"::: appareils à l’aide de :::no-loc text="Azure Monitor"::: .

Vous pouvez configurer :::no-loc text="Log Analytics"::: dans :::no-loc text="Azure Monitor"::: pour fournir des alertes de télémétrie et des alertes de base qui vous aideront à gérer les :::no-loc text="Microsoft Teams Rooms"::: appareils de salle de réunion. Comme votre solution de gestion est mature, vous pouvez choisir de déployer des données supplémentaires et des fonctionnalités de gestion pour créer une vue plus détaillée de la disponibilité et des performances de l’appareil.

En suivant ce guide, vous pouvez utiliser un tableau de bord tel que l’exemple ci-dessous pour obtenir des rapports d’État détaillés pour la disponibilité des appareils, l’état des applications et du matériel, ainsi que l' :::no-loc text="Microsoft Teams Rooms"::: application et la distribution de la version du système d’exploitation.

![Capture d’écran de l’exemple d’affichage analyse du journal pour les salles de Microsoft teams](../media/Deploy-Azure-Monitor-1.png "Exemple d’affichage d’analyse du journal des salles de Microsoft teams")

À haut niveau, vous devez effectuer les tâches suivantes :


1. [Valider la :::no-loc text="Log Analytics"::: Configuration](azure-monitor-deploy.md#validate_LogAnalytics)
2. [Configurer des périphériques de test pour la configuration de la :::no-loc text="Log Analytics"::: gestion](azure-monitor-deploy.md#configure_test_devices)
3. [Mapper les champs personnalisés](azure-monitor-deploy.md#Custom_fields)
4. [Définir les :::no-loc text="Microsoft Teams Rooms"::: affichages dans :::no-loc text="Log Analytics":::](azure-monitor-deploy.md#Define_Views)
5. [Définir des alertes](azure-monitor-deploy.md#Alerts)
6. [Configurer tous les appareils pour le contrôle](azure-monitor-deploy.md#configure_all_devices)
7. [Configurer des :::no-loc text="Azure Monitor"::: solutions supplémentaires](azure-monitor-deploy.md#Solutions)

> [!IMPORTANT]
> Bien que la configuration minimale :::no-loc text="Azure Monitor"::: :::no-loc text="Log Analytics"::: puisse surveiller un ordinateur exécutant un :::no-loc text="Windows"::: système d’exploitation, il existe toujours certaines :::no-loc text="Microsoft Teams Rooms"::: étapes spécifiques que vous devez effectuer avant de commencer à déployer les agents sur tous les :::no-loc text="Microsoft Teams Rooms"::: appareils.
> Par conséquent, nous vous conseillons vivement d’effectuer toutes les étapes de configuration dans l’ordre approprié pour une configuration et une configuration contrôlées. La qualité du résultat final dépend considérablement de la qualité de la configuration initiale.

## <a name="validate-no-loc-textlog-analytics-configuration"></a>Valider la :::no-loc text="Log Analytics"::: Configuration
<a name="validate_LogAnalytics"> </a>

Vous devez disposer d’un :::no-loc text="Log Analytics"::: espace de travail pour commencer à collecter des journaux sur les :::no-loc text="Microsoft Teams Rooms"::: appareils. Un espace de travail est un :::no-loc text="Log Analytics"::: environnement unique doté de son propre référentiel de données, de sources de données et de solutions. Si vous disposez déjà d’un :::no-loc text="Log Analytics"::: espace de travail existant, vous pouvez l’utiliser pour contrôler votre :::no-loc text="Microsoft Teams Rooms"::: déploiement ou vous pouvez créer un :::no-loc text="Log Analytics"::: espace de travail dédié spécifique à vos :::no-loc text="Microsoft Teams Rooms"::: besoins en matière de surveillance.

Si vous avez besoin de créer un nouvel :::no-loc text="Log Analytics"::: espace de travail, suivez les instructions de l’article [créer un :::no-loc text="Log Analytics"::: espace de travail dans le :::no-loc text="Azure"::: portail](https://docs.microsoft.com/azure/azure-monitor/learn/quick-create-workspace) .

> [!NOTE]
> Pour utiliser :::no-loc text="Log Analytics"::: with :::no-loc text="Azure Monitor"::: , vous devez disposer d’un :::no-loc text="Azure"::: abonnement actif. Si vous n’avez pas d' :::no-loc text="Azure"::: abonnement, vous pouvez créer [un abonnement d’essai gratuit](https://azure.microsoft.com/free) comme point de départ.

### <a name="configure-no-loc-textlog-analytics-to-collect-no-loc-textmicrosoft-teams-rooms-event-logs"></a>Configurer :::no-loc text="Log Analytics"::: pour collecter les :::no-loc text="Microsoft Teams Rooms"::: journaux des événements

:::no-loc text="Log Analytics"::: recueille uniquement les événements provenant des :::no-loc text="Windows"::: journaux d’événements spécifiés dans les paramètres. Pour chaque journal, seuls les événements associés aux gravités sélectionnées sont collectés.

Vous devez configurer :::no-loc text="Log Analytics"::: pour recueillir les journaux requis pour contrôler l' :::no-loc text="Microsoft Teams Rooms"::: État de l’appareil et de l’application. :::no-loc text="Microsoft Teams Rooms"::: les appareils utilisent le **:::no-loc text="Skype Room System":::** Journal des événements.

Pour configurer :::no-loc text="Log Analytics"::: la collecte des :::no-loc text="Microsoft Teams Rooms"::: événements, voir [ :::no-loc text="Windows"::: sources de données du journal :::no-loc text="Azure Monitor"::: des événements dans](https://docs.microsoft.com/azure/azure-monitor/platform/data-sources-windows-events)

![Capture d’écran des paramètres du journal des événements](../media/Deploy-Azure-Monitor-2.png "Paramètres du journal des événements")

> [!IMPORTANT]
> Configurez :::no-loc text="Windows"::: les paramètres du journal des événements **:::no-loc text="Skype Room System":::** , entrez comme nom du journal des événements, puis activez les cases à cocher **erreur**, **Avertissement**et **informations** .

## <a name="configure-test-devices-for-azure-monitoring"></a>Configurer des appareils de test pour la surveillance d’Azure
<a name="configure_test_devices"> </a>

Vous devez vous préparer :::no-loc text="Log Analytics"::: à pouvoir surveiller les :::no-loc text="Microsoft Teams Rooms"::: événements liés. Pour commencer, vous devez déployer des :::no-loc text="Microsoft Monitoring"::: agents sur un ou deux :::no-loc text="Microsoft Teams Rooms"::: appareils pour lesquels vous disposez d’un accès physique, et faire en sorte que ces derniers puissent générer des données et les pousser dans l' :::no-loc text="Log Analytics"::: espace de travail.

### <a name="install-no-loc-textmicrosoft-monitoring-agents-to-test-devices"></a>Installer des :::no-loc text="Microsoft Monitoring"::: agents sur les appareils de test

Déployez l' :::no-loc text="Microsoft Monitoring"::: agent sur les appareils de test en suivant les instructions fournies dans la rubrique [connecter des :::no-loc text="Windows"::: ordinateurs au :::no-loc text="Log Analytics"::: service :::no-loc text="Azure"::: ](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows). Cet article fournit des informations détaillées sur les étapes nécessaires au déploiement :::no-loc text="Microsoft Monitoring"::: de l’agent :::no-loc text="Windows"::: , des instructions pour l’obtention de l' :::no-loc text="Log Analytics"::: ***ID d’espace de travail*** et de la ***clé primaire*** pour l’obtention de :::no-loc text="Microsoft Teams Rooms"::: périphériques connectés à votre :::no-loc text="Azure Monitor"::: déploiement, ainsi que la procédure de vérification de la connectivité de l’agent à l' :::no-loc text="Log Analytics"::: instance.

### <a name="generate-sample-no-loc-textmicrosoft-teams-rooms-events"></a>Générer des exemples d' :::no-loc text="Microsoft Teams Rooms"::: événements

Une fois l' :::no-loc text="Microsoft Monitoring"::: agent déployé sur les appareils de test, vérifiez que les données du journal d’événements requises sont collectées par :::no-loc text="Azure Monitor"::: .

> [!NOTE]
> Redémarrez l’appareil après l’installation de l' :::no-loc text="Microsoft Monitoring"::: agent et assurez-vous que l' :::no-loc text="Microsoft Teams Rooms"::: application de réunion est démarrée pour pouvoir générer de nouveaux événements dans le journal des événements.

1.  Connectez-vous au [ :::no-loc text="Microsoft Azure"::: portail](https://portal.azure.com) et :::no-loc text="Log Analytics"::: Sélectionnez votre espace de travail.

2.  Répertorier les événements de pulsation générés par un :::no-loc text="Microsoft Teams Rooms"::: appareil :
    1.  Sélectionnez votre espace de travail, accédez aux **journaux** , puis utilisez une requête pour récupérer les enregistrements de pulsation pour lesquels les champs personnalisés seront disponibles :::no-loc text="Microsoft Teams Rooms"::: .
    2.  Exemple de requête : `Event | where Source == "SRS-App" and EventID == 2000`

3.  Assurez-vous que la requête renvoie les enregistrements du journal qui incluent les événements générés par l' :::no-loc text="Microsoft Teams Rooms"::: application réunions.

4.  Générez un problème de matériel et confirmez que les événements requis sont connectés :::no-loc text="Azure Log Analytics"::: .
    1.  Débranchez l’un des périphériques sur le système de test :::no-loc text="Microsoft Teams Rooms"::: . Il peut s’agir de l’écran de l’appareil photo, de l’écoute amplifiée, du microphone ou de la salle de façade
    2.  Attendez 10 minutes pour le remplissage du journal des événements :::no-loc text="Azure Log Analytics"::: .
    3.  Utiliser une requête pour répertorier les événements d’erreur matérielle : `Event | where Source == "SRS-App" and EventID == 3001`

5.  Génère un problème d’application et validez le journal des événements requis.
    1.  Modifiez la :::no-loc text="Microsoft Teams Rooms"::: configuration de l’application et tapez une adresse SIP (Session Initiation Protocol) incorrecte.
    2.  Attendez 10 minutes pour le remplissage du journal des événements :::no-loc text="Azure Log Analytics"::: .
    3.  Utiliser une requête pour répertorier les événements d’erreur d’application : `Event | where Source == "SRS-App" and EventID == 2001 and EventLevel == 1`

> [!IMPORTANT]
> Ces exemples de journaux d’événements sont requis pour pouvoir configurer les champs personnalisés. Ne passez pas à l’étape suivante tant que vous n’avez pas collecté les journaux des événements requis.

## <a name="map-custom-fields"></a>Mapper les champs personnalisés
<a name="Custom_fields"> </a>

Vous utilisez des champs personnalisés pour extraire des données spécifiques des journaux d’événements. Vous devez définir des champs personnalisés qui seront utilisés plus tard avec vos vignettes, affichages de tableau de bord et alertes. Affichez les [champs :::no-loc text="Log Analytics"::: personnalisés](https://docs.microsoft.com/azure/azure-monitor/platform/custom-fields) et familiarisez-vous avec les concepts avant de commencer à créer vos champs personnalisés.

Pour extraire vos champs personnalisés des journaux des événements capturés, procédez comme suit :

1.  Connectez-vous au [ :::no-loc text="Microsoft Azure"::: portail](https://portal.azure.com) et :::no-loc text="Log Analytics"::: Sélectionnez votre espace de travail.

2. Répertorier les événements générés par un :::no-loc text="Microsoft Teams Rooms"::: appareil :
   1.  Accédez aux **journaux** et utilisez une requête pour récupérer les enregistrements qui auront le champ personnalisé.
   2.  Exemple de requête : `Event | where Source == "SRS-App" and EventID == 2000`

3. Sélectionnez l’un des enregistrements, cliquez sur le bouton situé à gauche, puis démarrez l’Assistant extraction de champ.
4. Mettez en surbrillance les données que vous souhaitez extraire du RenderedDescription et indiquez un titre de champ. Les noms des champs que vous devez utiliser sont indiqués dans le tableau 1.
5. Utilisez les mappages indiqués dans le *tableau 1*. :::no-loc text="Log Analytics":::ajoute automatiquement la chaîne ** \_ CF** lorsque vous définissez le nouveau champ.

> [!IMPORTANT]
> Gardez à l’esprit que tous les champs JSON et respectent la :::no-loc text="Log Analytics"::: casse.
> 
> Soyez attentif aux requêtes requises pour chaque champ personnalisé dans le tableau ci-dessous. Vous devez utiliser les requêtes appropriées pour :::no-loc text="Log Analytics"::: extraire les valeurs de champs personnalisés.
> 
**Tableau 1**

| **Champ JSON**                   | **:::no-loc text="Log Analytics"::: champ personnalisé** | **ID d’événement** | **Requête à utiliser avec l’extraction**                   |
|:---------------------------------|:-------------------------------|:-------------|:-------------------------------------------------------|
| Description                      | SRSEventDescription         | **2000**     | Événement \| où source = = "SRS-App" et EventID = = 2000 |
| ResourceState                    | SRSResourceState            | **2000**     | Événement \| où source = = "SRS-App" et EventID = = 2000 |
| OperationName                    | SRSOperationName            | **2000**     | Événement \| où source = = "SRS-App" et EventID = = 2000 |
| OperationResult                  | SRSOperationResult          | **2000**     | Événement \| où source = = "SRS-App" et EventID = = 2000 |
| OS                               | SRSOSVersion                | **2000**     | Événement \| où source = = "SRS-App" et EventID = = 2000 |
| OSVersion                        | SRSOSLongVersion            | **2000**     | Événement \| où source = = "SRS-App" et EventID = = 2000 |
| Alias                            | SRSAlias                    | **2000**     | Événement \| où source = = "SRS-App" et EventID = = 2000 |
| DisplayName                      | SRSDisplayName              | **2000**     | Événement \| où source = = "SRS-App" et EventID = = 2000 |
| AppVersion                       | SRSAppVersion               | **2000**     | Événement \| où source = = "SRS-App" et EventID = = 2000 |
| IPv4Address                      | SRSIPv4Address              | **2000**     | Événement \| où source = = "SRS-App" et EventID = = 2000 |
| IPv6Address                      | SRSIPv6Address              | **2000**     | Événement \| où source = = "SRS-App" et EventID = = 2000 |
| État du micro de la Conférence     | SRSConfMicrophoneStatus     | **3001**     | Événement \| où source = = "SRS-App" et EventID = = 3001 |
| État du intervenant de la Conférence        | SRSConfSpeakerStatus        | **3001**     | Événement \| où source = = "SRS-App" et EventID = = 3001 |
| Statut de haut-parleur par défaut           | SRSDefaultSpeakerStatus     | **3001**     | Événement \| où source = = "SRS-App" et EventID = = 3001 |
| État de l’appareil photo                    | SRSCameraStatus             | **3001**     | Événement \| où source = = "SRS-App" et EventID = = 3001 |
| État d’affichage avant de la salle     | SRSFORDStatus               | **3001**     | Événement \| où source = = "SRS-App" et EventID = = 3001 |
| État du capteur de mouvement             | SRSMotionSensorStatus       | **3001**     | Événement \| où source = = "SRS-App" et EventID = = 3001 |
| État d’intégration HDMI               | SRSHDMIIngestStatus         | **3001**     | Événement \| où source = = "SRS-App" et EventID = = 3001 |


## <a name="define-the-no-loc-textmicrosoft-teams-rooms-views-in-no-loc-textlog-analytics"></a>Définir les :::no-loc text="Microsoft Teams Rooms"::: affichages dans :::no-loc text="Log Analytics":::
<a name="Define_Views"> </a>

Une fois que les données sont collectées et que les champs personnalisés sont mappés, vous pouvez utiliser le concepteur de vues pour développer un tableau de bord contenant différentes mosaïques pour surveiller les :::no-loc text="Microsoft Teams Rooms"::: événements. Utilisez le concepteur de vues pour créer les mosaïques suivantes. Pour plus d’informations, voir [créer des affichages personnalisés à l' :::no-loc text="Log Analytics"::: aide du concepteur de vues dans](https://docs.microsoft.com/azure/azure-monitor/platform/view-designer)

> [!NOTE]
> Les étapes précédentes de ce guide doivent avoir été effectuées pour que les vignettes du tableau de bord fonctionnent correctement.

### <a name="create-a-microsoft-teams-rooms-dashboard-by-using-the-import-method"></a>Créer un tableau de bord de Microsoft teams à l’aide de la méthode d’importation

Vous pouvez importer un :::no-loc text="Microsoft Teams Rooms"::: tableau de bord et commencer à surveiller vos appareils rapidement. Pour importer le tableau de bord, procédez comme suit :

1.  Obtenez le fichier de tableau de bord [SkypeRoomSystems_v2. omsview](https://go.microsoft.com/fwlink/?linkid=835675) .
2.  Connectez-vous au [ :::no-loc text="Microsoft Azure"::: portail](https://portal.azure.com) et :::no-loc text="Log Analytics"::: Sélectionnez votre espace de travail.
3.  Ouvrez le **Concepteur de vues**.
4.  Cliquez sur **Importer**, puis sélectionnez le fichier **SkypeRoomSystems_v2. omsview** .
5.  Sélectionnez **Save (enregistrer**).

### <a name="create-a-microsoft-teams-rooms-dashboard-manually"></a>Créer un tableau de bord de salles Microsoft teams manuellement

Vous pouvez également créer votre propre tableau de bord et ajouter uniquement les vignettes que vous souhaitez surveiller.

#### <a name="configure-the-overview-tile"></a>Configurer la vignette de vue d’ensemble

1.  Ouvrez le **Concepteur de vues**.
2.  Sélectionnez **vignette de vue d’ensemble**, puis sélectionnez **deux numéros** dans la Galerie.
3.  Nommez la vignette **:::no-loc text="Microsoft Teams Rooms":::** .
4.  Définissez la **première vignette**:<br>
    **Légende :** Appareils ayant envoyé un Heartbeat au moins une fois au cours du mois dernier<br>
    **Requête :**```Event | where EventLog == "Skype Room System" and TimeGenerated > ago(30d) | summarize TotalSRSDevices = dcount(Computer)```
5.  Définissez la **deuxième vignette**:<br>
    **Légende :** Appareils actifs ayant envoyé un Heartbeat au cours de la dernière heure<br>
    **Requête :**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(1h) | summarize TotalSRSDevices = dcount(Computer)```
6.  Sélectionnez **appliquer**.

### <a name="create-a-tile-that-displays-active-devices"></a>Créer une vignette qui affiche les appareils actifs

1.  Pour commencer à ajouter vos vignettes, sélectionnez **afficher le tableau de bord** .
2.  Sélectionner le **numéro & liste** dans la Galerie
3.  Définissez les propriétés **générales** :<br>
    **Titre du groupe :** État de la pulsation<br>
    **Nouveau groupe :** Sélectionné
4.  Définissez les propriétés de la **vignette** :<br>
    **Légende :** Appareils actifs (pulsation envoyés au cours des dernières 20 minutes)<br>
    **Requête de mosaïque : ** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize AggregatedValue = count() by Computer | count```
5.  Définissez les propriétés de la **liste** :<br>
    **Requête de liste :**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
6.  Définir les **titres des colonnes**:<br>
    **Nom :** Nom de l’ordinateur<br>
    **Valeur :** Dernière pulsation
7.  Définissez une **requête de navigation**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  Sélectionnez **appliquer**, puis **Fermer**.

### <a name="create-a-tile-that-displays-devices-that-have-connectivity-issues"></a>Créer une vignette qui affiche les appareils présentant des problèmes de connectivité

1.  Sélectionnez **numéro & liste** dans la Galerie, puis ajoutez une nouvelle vignette.
2.  Définissez les propriétés **générales** :<br>
    **Titre du groupe :** Laisser vide<br>
    **Nouveau groupe :** Non sélectionnée
3.  Définissez les propriétés de la **vignette** :<br>
    **Légende :** Appareils inactifs (aucun message Heartbeat envoyé au cours des dernières 20 minutes)<br>
    **Requête de mosaïque : ** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize LastHB = max(TimeGenerated) by Computer | where LastHB < ago(20m) | count```
4.  Définissez les propriétés de la **liste** :<br>
    **Requête de liste :**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize TimeGenerated = max(TimeGenerated) by Computer | where TimeGenerated < ago(20m) | order by TimeGenerated```
5.  Définir les **titres des colonnes**:<br>
    **Nom :** Nom de l’ordinateur<br>
    **Valeur :** Dernière pulsation
6.  Définir la **requête de navigation**:<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
7.  Sélectionnez **appliquer**, puis **Fermer**.

### <a name="create-a-tile-that-displays-devices-that-have-a-hardware-error"></a>Créer une vignette qui affiche les appareils présentant une erreur matérielle

1.  Sélectionnez **numéro & liste** dans la Galerie, puis ajoutez une nouvelle vignette.
2.  Définissez les propriétés **générales** :<br>
    **Titre du groupe :** État du matériel<br>
    **Nouveau groupe :** Sélectionné
3.  Définissez les propriétés de la **vignette** :<br>
    **Légende :** Appareils ayant rencontré une erreur matérielle lors de la dernière heure<br>
    **Requête de mosaïque : ** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```
4.  Définissez les propriétés de la **liste** :<br>
    **Requête de liste :**```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
5.  Définir les **titres des colonnes**:<br>
    **Nom :** Nom de l’ordinateur<br>
    **Valeur :** Dernière erreur
6.  Définir la **requête de navigation**:<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == 3001 and EventLevelName == "Error" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSConfMicrophoneStatus_CF, SRSConfSpeakerStatus_CF, SRSDefaultSpeakerStatus_CF, SRSCameraStatus_CF, SRSFORDStatus_CF, SRSMotionSensorStatus_CF, SRSHDMIIngestStatus_CF, SRSEventDescription_CF | sort by TimeGenerated desc```
7.  Sélectionnez **appliquer**, puis **Fermer**.

### <a name="create-a-tile-that-displays-no-loc-textmicrosoft-teams-rooms-operating-system-versions"></a>Créer une vignette qui affiche les :::no-loc text="Microsoft Teams Rooms"::: versions du système d’exploitation

1.  Sélectionnez **bouée & liste** dans la Galerie, puis ajoutez une nouvelle vignette.
2.  Définissez les propriétés **générales** :<br>
    **Titre du groupe :** Détails du système d’exploitation<br>
    **Nouveau groupe :** Sélectionné
3.  Définissez les propriétés d' **en-tête** :<br>
    **Titre :** Versions de système d’exploitation<br>
    **Sous-titre :** Appareils exécutant des versions spécifiques du système d’exploitation
4.  Définissez les propriétés **bouée** :<br>
    **Requête :**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize OS_Version = max(SRSOSLongVersion_CF) by Computer | summarize AggregatedValue = count() by OS_Version | sort by OS_Version asc```<br>
    **Centrer le texte :** Appareils<br>
    **Opération :** Somme
5.  Définissez les propriétés de **liste** .<br>
    **Requête de liste :**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSOSLongVersion_CF = max(SRSOSLongVersion_CF) by Computer | sort by Computer asc```<br>
    **Masquer le graphique :** Sélectionné<br>
    **Activer les graphiques sparkline :** Non sélectionnée
6.  Définissez des **titres de colonnes**.<br>
    **Nom :** Nom de l’ordinateur<br>
    **Valeur :** Laisser vide
7.  Définissez une **requête de navigation**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSDisplayName_CF, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  Sélectionnez **appliquer** , puis **Fermer**.

### <a name="create-a-tile-that-displays-no-loc-textmicrosoft-teams-rooms-application-versions"></a>Créer une vignette qui affiche les :::no-loc text="Microsoft Teams Rooms"::: versions d’applications

1.  Sélectionnez **bouée & liste** dans la Galerie, puis ajoutez une nouvelle vignette.
2.  Définissez les propriétés **générales** :<br>
    **Titre du groupe :** :::no-loc text="Microsoft Teams Rooms"::: Détails de l’application<br>
    **Nouveau groupe :** Sélectionné
3.  Définissez les propriétés d' **en-tête** :<br>
    **Titre :** Versions de l’application<br>
    **Sous-titre :** Appareils exécutant des versions d’application spécifiques
4.  Définissez les propriétés **bouée** :<br>
    **Requête :**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize App_Version = max(SRSAppVersion_CF) by Computer | summarize AggregatedValue = count() by App_Version | sort by App_Version asc```<br>
    **Centrer le texte :** Appareils<br>
    **Opération :** Somme
5.  Définissez les propriétés de **liste** .<br>
    **Requête de liste :**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSAppVersion_CF = max(SRSAppVersion_CF) by Computer | sort by Computer asc```<br>
    **Masquer le graphique :** Sélectionné<br>
    **Activer les graphiques sparkline :** Non sélectionnée
6.  Définissez des **titres de colonnes**.<br>
    **Nom :** Nom de l’ordinateur<br>
    **Valeur :** Laisser vide
7.  Définissez une **requête de navigation**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  Sélectionnez **appliquer** , puis **Fermer**.

### <a name="create-a-tile-that-displays-devices-that-have-an-application-error"></a>Créer une vignette qui affiche les appareils présentant une erreur d’application

1.  Sélectionnez **numéro & liste** dans la Galerie, puis ajoutez une nouvelle vignette.
2.  Définissez les propriétés **générales** .<br>
    **Titre du groupe :** Laisser vide<br>
    **Nouveau groupe :** Non sélectionnée
3.  Définissez les propriétés de la **vignette** .<br>
    **Légende :** Appareils ayant rencontré une erreur d’application au cours de la dernière heure<br>
    **Requête de mosaïque : ** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```
4.  Définissez les propriétés de **liste** .<br>
    **Requête de liste :**```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
5.  Définissez des **titres de colonnes**.<br>
    **Nom :** Nom de l’ordinateur<br>
    **Valeur :** Dernière erreur
6.  Définissez une **requête de navigation**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == 2001 and EventLevelName == "Error" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF | sort by TimeGenerated desc```
7.  Sélectionnez **appliquer** , puis **Fermer**.

### <a name="create-a-tile-that-displays-devices-that-have-been-restarted"></a>Créer une vignette qui affiche les appareils qui ont été redémarrés

1.  Sélectionnez **numéro & liste** dans la Galerie, puis ajoutez une nouvelle vignette.
2.  Définissez les propriétés **générales** .<br>
    **Titre du groupe :** Laisser vide<br>
    **Nouveau groupe :** Non sélectionnée
3.  Définissez les propriétés de la **vignette** .<br>
    **Légende :** Appareils dans lesquels l’application a été redémarrée au cours des dernières 24 heures et nombre de redémarrages<br>
    **Requête de mosaïque : ** ```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | summarize AggregatedValue = count() by Computer | count```
4.  Définissez les propriétés de **liste** .<br>
    **Requête de liste :**```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | order by TimeGenerated | summarize AggregatedValue = count(EventID) by Computer```
5.  Définissez des **titres de colonnes**.<br>
    **Nom :** Nom de l’ordinateur<br>
    **Valeur :** Nombre de redémarrages
6.  Définissez une **requête de navigation**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
7.  Sélectionnez **appliquer** , puis **Fermer**.
8.  Cliquez sur **Enregistrer** pour enregistrer votre tableau de bord.

Maintenant que vous avez terminé de créer vos vues.

## <a name="configure-alerts-in-no-loc-textazure-monitor"></a>Configurer les alertes en :::no-loc text="Azure Monitor":::
<a name="Alerts"> </a>

:::no-loc text="Azure Monitor"::: peut déclencher des alertes pour signaler aux administrateurs que le :::no-loc text="Microsoft Teams Rooms"::: problème est rencontré.

:::no-loc text="Azure Monitor"::: inclut un mécanisme d’alerte intégré qui s’exécute via les recherches du journal planifié à intervalles réguliers. Si les résultats de la recherche dans le journal répondent à certains critères, un enregistrement d’alerte est créé.

La règle peut alors automatiquement exécuter une ou plusieurs actions pour vous signaler de manière proactive de l’alerte ou appeler un autre processus. Les options possibles des alertes sont les suivantes :
-   Envoi d’un message électronique
-   Appel d’un processus externe via une requête HTTP POST
-   Démarrage d’une runbook en :::no-loc text="Azure Automation"::: service

Pour en savoir plus sur [les alertes de. :::no-loc text="Azure Monitor"::: ](https://docs.microsoft.com/azure/azure-monitor/platform/alerts-unified-log) :::no-loc text="Azure Monitor":::

> [!NOTE]
> Les exemples suivants envoient des alertes par courrier électronique lorsqu’un :::no-loc text="Microsoft Teams Rooms"::: appareil génère une erreur matérielle ou d’application.

### <a name="configure-an-email-alert-for-no-loc-textmicrosoft-teams-rooms-hardware-issues"></a>Configurer une alerte par courrier électronique pour les :::no-loc text="Microsoft Teams Rooms"::: problèmes matériels

Configurez une règle d’alerte qui recherche les :::no-loc text="Microsoft Teams Rooms"::: appareils qui ont rencontré des problèmes matériels au cours de la dernière heure.
1.  Connectez-vous au [ :::no-loc text="Microsoft Azure"::: portail](https://portal.azure.com) et :::no-loc text="Log Analytics"::: Sélectionnez votre espace de travail.

2. Accédez à votre :::no-loc text="Log Analytics"::: espace de travail, sélectionnez **alertes** , puis sélectionnez **nouvelle règle d’alerte** .

3. Sélectionnez **Ajouter une condition** , puis **recherche de journaux personnalisés**

4.  Entrez la requête suivante dans la zone de texte requête de recherche.<br>
    ```
    Event
    | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h)
    | summarize arg_max(TimeGenerated, *) by Computer
    | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSConfMicrophoneStatus_CF, SRSConfSpeakerStatus_CF, SRSDefaultSpeakerStatus_CF, SRSCameraStatus_CF, SRSFORDStatus_CF, SRSMotionSensorStatus_CF, SRSHDMIIngestStatus_CF, SRSEventDescription_CF
    |sort by TimeGenerated desc
    ```

5.  Configurez les paramètres de logique d’alerte :<br>
    **Basé sur :** Nombre de résultats<br>
    **État :** Plus, puis<br>
    **Seuil :** 0<br>

6. Configurez les paramètres d’évaluation et sélectionnez **Terminer**: <br>
    **Période (en minutes) :** 60<br>
    **Fréquence (en minutes) :** 60<br>

7. Configurer les groupes d’action :
    1.  Sélectionner **créer**
    2.  Donnez des noms appropriés aux champs *nom du groupe d’action* et *nom court* .
    3.  Spécifiez un *nom d’action* unique et sélectionnez **email/SMS/émission/voix**, puis sélectionnez **modifier les détails**.
    4.  Cochez la case **message électronique** et indiquez l’adresse de messagerie de la personne ou du groupe qui recevra les alertes.
    5.  Vous pouvez également fournir votre numéro de téléphone pour être informé des SMS, un appel audio ou les deux.
    6. Sélectionnez **OK**.

8. **Personnalisez les actions** si vous souhaitez remplacer la ligne d’objet des alertes par courrier électronique.

9. Spécifiez le nom et la description de la règle.<br>
    **Nom de la règle :** :::no-loc text="Microsoft Teams Rooms"::: Alerte de défaillance matérielle<br>
    **Description :** Liste des périphériques ayant rencontré un problème de matériel au cours de la dernière heure<br>

10. Sélectionnez la gravité prévue, puis vérifiez que la règle est activée.

11. Sélectionnez **créer une règle d’alerte**.

### <a name="configure-an-email-alert-for-no-loc-textmicrosoft-teams-rooms-application-issues"></a>Configurer une alerte par courrier électronique pour les :::no-loc text="Microsoft Teams Rooms"::: problèmes liés à l’application

Répétez la même procédure, mais utilisez la requête suivante pour répertorier les appareils qui ont rencontré des problèmes d’application au cours de la dernière heure.

    ```
    Event
    | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h)
    | summarize arg_max(TimeGenerated, *) by Computer
    | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF
    | sort by TimeGenerated desc
    ```

Maintenant que vous avez terminé de définir des alertes. Vous pouvez définir des alertes supplémentaires à l’aide des exemples ci-dessus.

Lors de la génération d’une alerte, vous recevez un courrier électronique qui recense les appareils qui ont rencontré un problème au cours de la dernière heure.

! [Message d’exemple d' :::no-loc text="Azure Monitor"::: alerte] (... /Media/Deploy-Azure-Monitor-6.png "exemple de :::no-loc text="Azure Monitor"::: message d’alerte")

## <a name="configure-all-devices-for-no-loc-textazure-monitoring"></a>Configurer tous les appareils pour :::no-loc text="Azure Monitoring":::
<a name="configure_all_devices"> </a> Une fois les tableaux de bord et les alertes configurés, vous pouvez configurer et configurer :::no-loc text="Microsoft Monitoring"::: l’agent sur tous les :::no-loc text="Microsoft Teams Rooms"::: appareils pour terminer le déploiement de votre analyse.

Même si vous pouvez installer et configurer l' :::no-loc text="Microsoft Monitoring"::: agent manuellement sur chaque appareil, nous vous conseillons vivement d’utiliser les outils et méthodes de déploiement de logiciels existants.

Si vous créez vos :::no-loc text="Microsoft Teams Rooms"::: appareils pour la première fois, vous souhaiterez peut-être inclure les :::no-loc text="Microsoft Monitoring"::: étapes de configuration et de configuration de l’agent dans le cadre de votre processus de génération. Pour plus d’informations, voir [installer l’agent à l’aide de la ligne de commande](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows#install-the-agent-using-the-command-line).

### <a name="deploying-no-loc-textmicrosoft-monitoring-agent-by-using-a-group-policy-object-gpo"></a>Déploiement :::no-loc text="Microsoft Monitoring"::: d’agent à l’aide d’un objet de stratégie de groupe (GPO)

Si vous avez déjà déployé vos appareils avant de procéder à la :::no-loc text="Microsoft Teams Rooms"::: mise en œuvre :::no-loc text="Azure Monitoring"::: , vous pouvez utiliser le script fourni pour configurer et configurer les agents à l’aide d' :::no-loc text="Active Directory"::: objets de stratégie de groupe.

1.  Créez un chemin réseau partagé et octroyez l’accès en lecture au groupe **ordinateurs du domaine** .

2.  Télécharger la version 64 bits de l' :::no-loc text="Microsoft Monitoring"::: agent pour :::no-loc text="Windows"::: à partir de <https://go.microsoft.com/fwlink/?LinkID=517476>

3.  Extrayez le contenu du package d’installation vers le partage réseau.
    1.  Ouvrez une fenêtre d’invite de commandes, puis exécutez **MMASetup-AMD64.exe/c** .
    2.  Spécifiez le partage que vous venez de créer, puis extrayez le contenu.

4.  Créez un nouvel objet de stratégie de groupe et attribuez-le à l’unité d’organisation où se :::no-loc text="Microsoft Teams Rooms"::: trouvent les comptes d’ordinateur.

5.  Configurer une stratégie d’exécution PowerShell :
    1.  Modifier l’objet de stratégie de groupe que vous venez de créer et accéder aux stratégies de configuration de l’ordinateur \\ \\ \\ :::no-loc text="Windows"::: composants \\ modèles d’administration :::no-loc text="Windows PowerShell":::
    2.  Activez l' **exécution du script** et la **stratégie d’exécution** définies pour autoriser les **scripts locaux**.

6.  Configurez le script de démarrage :
    1.  Copiez le script suivant et enregistrez-le en tant que Install-MMAgent.ps1.
    2.  Modifiez les paramètres WorkspaceId, WorkspaceKey et SetupPath en fonction de votre configuration.
    3.  Modifiez le même objet de stratégie de groupe et naviguez jusqu’à scripts de configuration de l’ordinateur \\ \\ :::no-loc text="Windows"::: \\ (démarrage/arrêt).
    4.  Double-cliquez pour sélectionner **démarrage**, puis sélectionnez **scripts PowerShell**.
    5.  Sélectionnez **afficher les fichiers**, puis copiez le fichier **Install-MMAgent.ps1** dans ce dossier.
    6.  Cliquez sur **Ajouter**, puis sur **Parcourir**.
    7.  Sélectionnez le script PS1 que vous venez de copier.

7.  :::no-loc text="Microsoft Teams Rooms"::: les appareils doivent installer et configurer l' :::no-loc text="Microsoft Monitoring"::: agent avec le second redémarrage.

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
> Vous pouvez vous référer à l’article [gestion et maintenance de l' :::no-loc text="Log Analytics"::: agent](https://docs.microsoft.com/azure/azure-monitor/platform/agent-manage) lorsque vous avez besoin de reconfigurer un agent, de le déplacer vers un autre espace de travail ou de modifier les paramètres de proxy après l’installation initiale.

## <a name="additional-solutions"></a>Solutions supplémentaires
<a name="Solutions"> </a>

:::no-loc text="Azure Monitor"::: fournit des solutions de gestion intégrées par le biais de la [Galerie de solutions](https://docs.microsoft.com/azure/azure-monitor/insights/solutions) pour vous aider à surveiller votre environnement. Nous vous recommandons vivement d’ajouter également la [gestion des alertes](https://docs.microsoft.com/azure/azure-monitor/platform/alert-management-solution) et les solutions d' [ :::no-loc text="Azure Log Analytics"::: intégrité des agents](https://docs.microsoft.com/azure/azure-monitor/insights/solution-agenthealth) à votre espace de travail.

> [!NOTE]
> La solution d’intégrité des agents peut vous aider à identifier les agents obsolètes ou défectueux :::no-loc text="Microsoft Monitoring"::: au sein de votre environnement, et la solution de gestion des alertes fournit des détails sur les alertes déclenchées au cours d’une période donnée.

## <a name="see-also"></a>Voir aussi

[:::no-loc text="Microsoft Teams Rooms":::Gestion des plans avec:::no-loc text="Azure Monitor":::](azure-monitor-plan.md)

[Gérer :::no-loc text="Microsoft Teams Rooms"::: les appareils avec :::no-loc text="Azure Monitor":::](azure-monitor-manage.md)
