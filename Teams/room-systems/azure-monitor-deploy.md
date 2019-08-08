---
title: Déploiement de la gestion de salles de Microsoft teams avec Azure Monitor
ms.author: v-lanac
author: lanachin
ms.reviewer: Turgayo
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
- M365-voice
ms.custom: ''
ms.assetid: d86ff657-ee92-4b06-aee3-d4c43090bdcb
description: Cet article décrit le déploiement de la gestion des appareils Microsoft teams salles de manière intégrée et complète grâce à l’utilisation de moniteur Azure.
ms.openlocfilehash: 1f9a6e6ba4da22d8b14f4b1d545c0a6cfb16e14b
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36243618"
---
# <a name="deploy-microsoft-teams-rooms-management-with-azure-monitor"></a>Déploiement de la gestion de salles de Microsoft teams avec Azure Monitor

Cet article décrit la configuration et le déploiement de la gestion intégrée et complète des appareils de salle Microsoft teams à l’aide d’Azure Monitor.

Vous pouvez configurer l’analyse du journal dans Azure Monitor pour fournir une télémétrie de base et des alertes qui vous aideront à gérer les appareils de salle de réunion de Microsoft Teams. Comme votre solution de gestion est mature, vous pouvez choisir de déployer des données supplémentaires et des fonctionnalités de gestion pour créer une vue plus détaillée de la disponibilité et des performances de l’appareil.

En suivant ce guide, vous pouvez utiliser un tableau de bord tel que l’exemple ci-dessous pour obtenir des rapports d’État détaillés pour la disponibilité des appareils, l’état des applications et du matériel, et la distribution de la version de l’application Microsoft teams et du système d’exploitation.

![Capture d’écran de l’exemple d’affichage analyse du journal pour les salles de Microsoft teams] (../media/Deploy-Azure-Monitor-1.png "Exemple d’affichage d’analyse du journal des salles de Microsoft teams")

À haut niveau, vous devez effectuer les tâches suivantes :


1.  [Valider la configuration d’analyse du journal](azure-monitor-deploy.md#validate_LogAnalytics)
2.  [Configurer des appareils de test pour la configuration de l’analyse du journal](azure-monitor-deploy.md#configure_test_devices)
3.  [Mapper les champs personnalisés](azure-monitor-deploy.md#Custom_fields)
4.  [Définir les affichages des salles de Microsoft teams dans l’analyse du journal](azure-monitor-deploy.md#Define_Views)
5.  [Définir des alertes](azure-monitor-deploy.md#Alerts)
6.  [Configurer tous les appareils pour le contrôle](azure-monitor-deploy.md#configure_all_devices)
7.  [Configurer des solutions supplémentaires pour moniteur Azure](azure-monitor-deploy.md#Solutions)

> [!IMPORTANT]
> Même si la configuration est minime, l’analyse du journal d’analyse Azure Monitor peut surveiller un ordinateur exécutant un système d’exploitation Windows, il existe toujours certaines étapes spécifiques de Microsoft Teams, dont vous devez disposer avant de commencer à déployer les agents sur toutes les équipes de Microsoft teams Appareils de salle.
> Par conséquent, nous vous conseillons vivement d’effectuer toutes les étapes de configuration dans l’ordre approprié pour une configuration et une configuration contrôlées. La qualité du résultat final dépend considérablement de la qualité de la configuration initiale.

## <a name="validate-log-analytics-configuration"></a>Valider la configuration d’analyse du journal
<a name="validate_LogAnalytics"> </a>

Vous devez disposer d’un espace de travail d’analyse du journal pour commencer à collecter des journaux sur les appareils Microsoft Teams. Un espace de travail est un environnement d’analyse du journal unique doté de son propre référentiel de données, de sources de données et de solutions. Si vous disposez déjà d’un espace de travail d’analyse du journal, vous pouvez l’utiliser pour surveiller votre déploiement de Microsoft Teams, ou vous pouvez créer un espace de travail d’analyse du journal dédié spécifique à votre analyse des salles de Microsoft Teams.

Si vous avez besoin de créer un nouvel espace de travail d’analyse du journal, suivez les instructions de l’article [créer un espace de travail d’analyse du journal sur le portail Azure](https://docs.microsoft.com/azure/azure-monitor/learn/quick-create-workspace) .

> [!NOTE]
> Pour utiliser l’analyse du journal avec Azure Monitor, vous devez disposer d’un abonnement Azure actif. Si vous n’avez pas d’abonnement Azure, vous pouvez créer [un abonnement d’essai gratuit](https://azure.microsoft.com/free) comme point de départ.

### <a name="configure-log-analytics-to-collect-microsoft-teams-rooms-event-logs"></a>Configurer l’analyse du journal pour recueillir les journaux d’événements de Microsoft teams

L’analyse du journal collecte uniquement les événements provenant des journaux d’événements Windows indiqués dans les paramètres. Pour chaque journal, seuls les événements associés aux gravités sélectionnées sont collectés.

Vous devez configurer l’analyse du journal pour recueillir les journaux requis pour contrôler l’état de l’appareil et de l’application Microsoft Teams. Les appareils Microsoft teams salles utilisent le journal des événements du **système de salle Skype** .

Pour configurer l’analyse du journal de sorte que les événements sur les salles de Microsoft teams soient collectés, voir [sources de données du journal des événements Windows dans Azure Monitor](https://docs.microsoft.com/azure/azure-monitor/platform/data-sources-windows-events)

![Capture d’écran des paramètres du journal des événements] (../media/Deploy-Azure-Monitor-2.png "Paramètres du journal des événements")

> [!IMPORTANT]
> Configurez les paramètres du journal des événements Windows et entrez le nom du journal des événements dans **Skype** , puis activez les cases à cocher **erreur**, **Avertissement**et **informations** .

## <a name="configure-test-devices-for-azure-monitoring"></a>Configurer des appareils de test pour la surveillance d’Azure
<a name="configure_test_devices"> </a>

Vous devez préparer l’analyse du journal pour pouvoir surveiller les événements liés aux salles de Microsoft Teams. Pour commencer, vous devez déployer les agents de surveillance Microsoft sur un ou deux appareils Microsoft teams uniquement pour lesquels vous disposez d’un accès physique, et faire en sorte que ces derniers puissent générer des données et les envoyer à l’espace de travail d’analyse du journal.

### <a name="install-microsoft-monitoring-agents-to-test-devices"></a>Installer les agents de surveillance Microsoft pour tester des appareils

Déployez l’agent de surveillance Microsoft sur les appareils de test en suivant les instructions fournies dans [connecter des ordinateurs Windows au service d’analyse du journal dans Azure](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows). Cet article fournit des informations détaillées sur les étapes nécessaires au déploiement de l’agent de surveillance Microsoft pour Windows, instructions pour l’obtention de l' ***ID de l’espace de travail*** d’analyse du journal et de la ***clé primaire*** pour obtenir la connexion des appareils Microsoft teams le déploiement de votre moniteur Azure et étapes de vérification de la connectivité de l’agent pour consigner l’instance d’analyse.

### <a name="generate-sample-microsoft-teams-rooms-events"></a>Générer des exemples d’événements de salle Microsoft teams

Après le déploiement de l’agent de surveillance Microsoft sur les appareils de test, vérifiez que les données du journal d’événements requises sont collectées par Azure Monitor.

> [!NOTE]
> Redémarrez l’appareil après l’installation de l’agent de surveillance Microsoft et assurez-vous que l’application réunion Microsoft teams est démarrée pour pouvoir générer de nouveaux événements dans le journal des événements.

1.  Connectez-vous au [portail Microsoft Azure](https://portal.azure.com) et accédez à analyse du journal et sélectionnez votre espace de travail.

2.  Répertorier les événements de pulsation générés par un appareil Microsoft teams:
    1.  Sélectionnez votre espace de travail, accédez aux **journaux** , puis utilisez une requête pour récupérer les enregistrements de pulsation qui disposeront des champs personnalisés pour les salles Microsoft Teams.
    2.  Exemple de requête:`Event | where Source == "SRS-App" and EventID == 2000`

3.  Assurez-vous que la requête renvoie les enregistrements du journal qui incluent les événements générés par l’application réunions de Microsoft Teams.

4.  Générez un problème de matériel et validez le journal des événements requis dans l’analyse du journal Azure.
    1.  Débranchez l’un des périphériques sur le système de test de Microsoft Teams. Il peut s’agir de l’écran de l’appareil photo, de l’écoute amplifiée, du microphone ou de la salle de façade
    2.  Attendez 10 minutes que le journal des événements soit rempli dans l’analyse du journal Azure.
    3.  Utiliser une requête pour répertorier les événements d’erreur matérielle:`Event | where Source == "SRS-App" and EventID == 3001`

5.  Génère un problème d’application et validez le journal des événements requis.
    1.  Modifiez la configuration de l’application Microsoft teams à partir de Microsoft Teams, puis tapez une paire adresse de mot de passe ou adresse SIP (Session Initiation Protocol) incorrecte.
    2.  Attendez 10 minutes que le journal des événements soit rempli dans l’analyse du journal Azure.
    3.  Utiliser une requête pour répertorier les événements d’erreur d’application:`Event | where Source == "SRS-App" and EventID == 2001 and EventLevel == 1`

> [!IMPORTANT]
> Ces exemples de journaux d’événements sont requis pour pouvoir configurer les champs personnalisés. Ne passez pas à l’étape suivante tant que vous n’avez pas collecté les journaux des événements requis.

## <a name="map-custom-fields"></a>Mapper les champs personnalisés
<a name="Custom_fields"> </a>

Vous utilisez des champs personnalisés pour extraire des données spécifiques des journaux d’événements. Vous devez définir des champs personnalisés qui seront utilisés plus tard avec vos vignettes, affichages de tableau de bord et alertes. Affichez les [champs personnalisés dans l’analyse du journal](https://docs.microsoft.com/azure/azure-monitor/platform/custom-fields) et familiarisez-vous avec les concepts avant de commencer à créer vos champs personnalisés.

Pour extraire vos champs personnalisés des journaux des événements capturés, procédez comme suit:

1.  Connectez-vous au [portail Microsoft Azure](https://portal.azure.com) et accédez à analyse du journal et sélectionnez votre espace de travail.

2. Répertorier les événements générés par un appareil Microsoft teams:
   1.  Accédez aux **journaux** et utilisez une requête pour récupérer les enregistrements qui auront le champ personnalisé.
   2.  Exemple de requête:`Event | where Source == "SRS-App" and EventID == 2000`

3. Sélectionnez l’un des enregistrements, cliquez sur le bouton situé à gauche, puis démarrez l’Assistant extraction de champ.
4. Mettez en surbrillance les données que vous souhaitez extraire du RenderedDescription et indiquez un titre de champ. Les noms des champs que vous devez utiliser sont indiqués dans le tableau 1.

   ![Définition de champ personnalisé] (../media/Deploy-Azure-Monitor-4.png "Définition de champ personnalisé")

5. Utilisez les mappages indiqués dans le *tableau 1*. L’analyse du journal ajoute automatiquement ** \_** la chaîne CF lorsque vous définissez le nouveau champ.

> [!IMPORTANT]
> Gardez à l’esprit que tous les champs d’analyse JSON et de journalisation sont sensibles à la casse.
> 
> Soyez attentif aux requêtes requises pour chaque champ personnalisé dans le tableau ci-dessous. Vous devez utiliser les requêtes appropriées pour l’analyse du journal pour extraire les valeurs de champs personnalisés.
> 
 ![Définition de champ personnalisé] (../media/Deploy-Azure-Monitor-5.png "Définition de champ personnalisé")

**Tableau 1**

| **Champ JSON**                   | **Champ personnalisé d’analyse du journal** | **ID d’événement** | **Requête à utiliser avec l’extraction**                   |
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


## <a name="define-the-microsoft-teams-rooms-views-in-log-analytics"></a>Définir les affichages des salles de Microsoft teams dans l’analyse du journal
<a name="Define_Views"> </a>

Une fois que les données sont collectées et que les champs personnalisés sont mappés, vous pouvez utiliser le concepteur de vues pour développer un tableau de bord contenant différentes mosaïques afin de surveiller les événements de salles de Microsoft Teams. Utilisez le concepteur de vues pour créer les mosaïques suivantes. Pour plus d’informations, consultez [créer des affichages personnalisés à l’aide du concepteur de vues dans analyse du journal](https://docs.microsoft.com/azure/azure-monitor/platform/view-designer)

> [!NOTE]
> Les étapes précédentes de ce guide doivent avoir été effectuées pour que les vignettes du tableau de bord fonctionnent correctement.

### <a name="create-a-microsoft-teams-rooms-dashboard-by-using-the-import-method"></a>Créer un tableau de bord de Microsoft teams à l’aide de la méthode d’importation

Vous pouvez importer un tableau de bord des salles de Microsoft teams et commencer à surveiller vos appareils rapidement. Pour importer le tableau de bord, procédez comme suit:

1.  Obtenez le fichier de tableau de bord [SkypeRoomSystems_v2. omsview](https://go.microsoft.com/fwlink/?linkid=835675) .
2.  Connectez-vous au [portail Microsoft Azure](https://portal.azure.com) et accédez à analyse du journal et sélectionnez votre espace de travail.
3.  Ouvrez le **Concepteur de vues**.
4.  Cliquez sur **Importer**, puis sélectionnez le fichier **SkypeRoomSystems_v2. omsview** .
5.  Sélectionnez **Save (enregistrer**).

### <a name="create-a-microsoft-teams-rooms-dashboard-manually"></a>Créer un tableau de bord de salles Microsoft teams manuellement

Vous pouvez également créer votre propre tableau de bord et ajouter uniquement les vignettes que vous souhaitez surveiller.

#### <a name="configure-the-overview-tile"></a>Configurer la vignette de vue d’ensemble

1.  Ouvrez le **Concepteur de vues**.
2.  Sélectionnez **vignette de vue d’ensemble**, puis sélectionnez **deux numéros** dans la Galerie.
3.  Nommez la vignette **salles Microsoft teams**.
4.  Définissez la **première vignette**:<br>
    **Légende:** Appareils ayant envoyé un Heartbeat au moins une fois au cours du mois dernier<br>
    **Requête:**```Event | where EventLog == "Skype Room System" and TimeGenerated > ago(30d) | summarize TotalSRSDevices = dcount(Computer)```
5.  Définissez la **deuxième vignette**:<br>
    **Légende:** Appareils actifs ayant envoyé un Heartbeat au cours de la dernière heure<br>
    **Requête:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(1h) | summarize TotalSRSDevices = dcount(Computer)```
6.  Sélectionnez **appliquer**.

### <a name="create-a-tile-that-displays-active-devices"></a>Créer une vignette qui affiche les appareils actifs

1.  Pour commencer à ajouter vos vignettes, sélectionnez **afficher le tableau de bord** .
2.  Sélectionner le **numéro & liste** dans la Galerie
3.  Définissez les propriétés **générales** :<br>
    **Titre du groupe:** État de la pulsation<br>
    **Nouveau groupe:** Sélectionné
4.  Définissez les propriétés de la **vignette** :<br>
    **Légende:** Appareils actifs (pulsation envoyés au cours des dernières 20 minutes)<br>
    **Requête de mosaïque : ** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize AggregatedValue = count() by Computer | count```
5.  Définissez les propriétés de la **liste** :<br>
    **Requête de liste:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
6.  Définir les **titres des colonnes**:<br>
    **Nom:** Nom de l’ordinateur<br>
    **Valeur:** Dernière pulsation
7.  Définissez une **requête de navigation**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  Sélectionnez **appliquer**, puis **Fermer**.

### <a name="create-a-tile-that-displays-devices-that-have-connectivity-issues"></a>Créer une vignette qui affiche les appareils présentant des problèmes de connectivité

1.  Sélectionnez **numéro & liste** dans la Galerie, puis ajoutez une nouvelle vignette.
2.  Définissez les propriétés **générales** :<br>
    **Titre du groupe:** Laisser vide<br>
    **Nouveau groupe:** Non sélectionnée
3.  Définissez les propriétés de la **vignette** :<br>
    **Légende:** Appareils inactifs (aucun message Heartbeat envoyé au cours des dernières 20 minutes)<br>
    **Requête de mosaïque : ** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize LastHB = max(TimeGenerated) by Computer | where LastHB < ago(20m) | count```
4.  Définissez les propriétés de la **liste** :<br>
    **Requête de liste:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize TimeGenerated = max(TimeGenerated) by Computer | where TimeGenerated < ago(20m) | order by TimeGenerated```
5.  Définir les **titres des colonnes**:<br>
    **Nom:** Nom de l’ordinateur<br>
    **Valeur:** Dernière pulsation
6.  Définir la **requête de navigation**:<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
7.  Sélectionnez **appliquer**, puis **Fermer**.

### <a name="create-a-tile-that-displays-devices-that-have-a-hardware-error"></a>Créer une vignette qui affiche les appareils présentant une erreur matérielle

1.  Sélectionnez **numéro & liste** dans la Galerie, puis ajoutez une nouvelle vignette.
2.  Définissez les propriétés **générales** :<br>
    **Titre du groupe:** État du matériel<br>
    **Nouveau groupe:** Sélectionné
3.  Définissez les propriétés de la **vignette** :<br>
    **Légende:** Appareils ayant rencontré une erreur matérielle lors de la dernière heure<br>
    **Requête de mosaïque : ** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```
4.  Définissez les propriétés de la **liste** :<br>
    **Requête de liste:**```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
5.  Définir les **titres des colonnes**:<br>
    **Nom:** Nom de l’ordinateur<br>
    **Valeur:** Dernière erreur
6.  Définir la **requête de navigation**:<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == 3001 and EventLevelName == "Error" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSConfMicrophoneStatus_CF, SRSConfSpeakerStatus_CF, SRSDefaultSpeakerStatus_CF, SRSCameraStatus_CF, SRSFORDStatus_CF, SRSMotionSensorStatus_CF, SRSHDMIIngestStatus_CF, SRSEventDescription_CF | sort by TimeGenerated desc```
7.  Sélectionnez **appliquer**, puis **Fermer**.

### <a name="create-a-tile-that-displays-microsoft-teams-rooms-operating-system-versions"></a>Créer une vignette qui affiche les versions du système d’exploitation Microsoft teams

1.  Sélectionnez **bouée & liste** dans la Galerie, puis ajoutez une nouvelle vignette.
2.  Définissez les propriétés **générales** :<br>
    **Titre du groupe:** Détails du système d’exploitation<br>
    **Nouveau groupe:** Sélectionné
3.  Définissez les propriétés d' **en-tête** :<br>
    **Titre:** Versions de système d’exploitation<br>
    **Sous-titre:** Appareils exécutant des versions spécifiques du système d’exploitation
4.  Définissez les propriétés **bouée** :<br>
    **Requête:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize OS_Version = max(SRSOSLongVersion_CF) by Computer | summarize AggregatedValue = count() by OS_Version | sort by OS_Version asc```<br>
    **Centrer le texte:** Appareils<br>
    **Opération:** Somme
5.  Définissez les propriétés de **liste** .<br>
    **Requête de liste:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSOSLongVersion_CF = max(SRSOSLongVersion_CF) by Computer | sort by Computer asc```<br>
    **Masquer le graphique:** Sélectionné<br>
    **Activer les graphiques sparkline:** Non sélectionnée
6.  Définissez des **titres de colonnes**.<br>
    **Nom:** Nom de l’ordinateur<br>
    **Valeur:** Laisser vide
7.  Définissez une **requête de navigation**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSDisplayName_CF, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  Sélectionnez **appliquer** , puis **Fermer**.

### <a name="create-a-tile-that-displays-microsoft-teams-rooms-application-versions"></a>Créer une vignette qui affiche les versions de l’application Microsoft teams

1.  Sélectionnez **bouée & liste** dans la Galerie, puis ajoutez une nouvelle vignette.
2.  Définissez les propriétés **générales** :<br>
    **Titre du groupe:** Détails de l’application Microsoft teams salles<br>
    **Nouveau groupe:** Sélectionné
3.  Définissez les propriétés d' **en-tête** :<br>
    **Titre:** Versions de l’application<br>
    **Sous-titre:** Appareils exécutant des versions d’application spécifiques
4.  Définissez les propriétés **bouée** :<br>
    **Requête:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize App_Version = max(SRSAppVersion_CF) by Computer | summarize AggregatedValue = count() by App_Version | sort by App_Version asc```<br>
    **Centrer le texte:** Appareils<br>
    **Opération:** Somme
5.  Définissez les propriétés de **liste** .<br>
    **Requête de liste:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSAppVersion_CF = max(SRSAppVersion_CF) by Computer | sort by Computer asc```<br>
    **Masquer le graphique:** Sélectionné<br>
    **Activer les graphiques sparkline:** Non sélectionnée
6.  Définissez des **titres de colonnes**.<br>
    **Nom:** Nom de l’ordinateur<br>
    **Valeur:** Laisser vide
7.  Définissez une **requête de navigation**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  Sélectionnez **appliquer** , puis **Fermer**.

### <a name="create-a-tile-that-displays-devices-that-have-an-application-error"></a>Créer une vignette qui affiche les appareils présentant une erreur d’application

1.  Sélectionnez **numéro & liste** dans la Galerie, puis ajoutez une nouvelle vignette.
2.  Définissez les propriétés **générales** .<br>
    **Titre du groupe:** Laisser vide<br>
    **Nouveau groupe:** Non sélectionnée
3.  Définissez les propriétés de la **vignette** .<br>
    **Légende:** Appareils ayant rencontré une erreur d’application au cours de la dernière heure<br>
    **Requête de mosaïque : ** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```
4.  Définissez les propriétés de **liste** .<br>
    **Requête de liste:**```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
5.  Définissez des **titres de colonnes**.<br>
    **Nom:** Nom de l’ordinateur<br>
    **Valeur:** Dernière erreur
6.  Définissez une **requête de navigation**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == 2001 and EventLevelName == "Error" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF | sort by TimeGenerated desc```
7.  Sélectionnez **appliquer** , puis **Fermer**.

### <a name="create-a-tile-that-displays-devices-that-have-been-restarted"></a>Créer une vignette qui affiche les appareils qui ont été redémarrés

1.  Sélectionnez **numéro & liste** dans la Galerie, puis ajoutez une nouvelle vignette.
2.  Définissez les propriétés **générales** .<br>
    **Titre du groupe:** Laisser vide<br>
    **Nouveau groupe:** Non sélectionnée
3.  Définissez les propriétés de la **vignette** .<br>
    **Légende:** Appareils dans lesquels l’application a été redémarrée au cours des dernières 24 heures et nombre de redémarrages<br>
    **Requête de mosaïque : ** ```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | summarize AggregatedValue = count() by Computer | count```
4.  Définissez les propriétés de **liste** .<br>
    **Requête de liste:**```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | order by TimeGenerated | summarize AggregatedValue = count(EventID) by Computer```
5.  Définissez des **titres de colonnes**.<br>
    **Nom:** Nom de l’ordinateur<br>
    **Valeur:** Nombre de redémarrages
6.  Définissez une **requête de navigation**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
7.  Sélectionnez **appliquer** , puis **Fermer**.
8.  Cliquez sur **Enregistrer** pour enregistrer votre tableau de bord.

Maintenant que vous avez terminé de créer vos vues.

## <a name="configure-alerts-in-azure-monitor"></a>Configurer les alertes dans Azure Monitor
<a name="Alerts"> </a>

Le moniteur Azure peut déclencher des alertes pour signaler aux administrateurs qu’une console Microsoft teams rencontre un problème.

Le moniteur Azure inclut un mécanisme d’alerte intégré qui s’exécute via les recherches dans le journal planifié à intervalles réguliers. Si les résultats de la recherche dans le journal répondent à certains critères, un enregistrement d’alerte est créé.

La règle peut alors automatiquement exécuter une ou plusieurs actions pour vous signaler de manière proactive de l’alerte ou appeler un autre processus. Les options possibles des alertes sont les suivantes:
-   Envoi d’un message électronique
-   Appel d’un processus externe via une requête HTTP POST
-   Démarrage d’un runbook dans Azure Automation service

Pour en savoir plus sur les alertes dans Azure Monitor, voir [alertes de journal dans Azure](https://docs.microsoft.com/azure/azure-monitor/platform/alerts-unified-log) .

> [!NOTE]
> Les exemples suivants envoient des alertes par courrier électronique lors de la génération d’une erreur matérielle ou d’une application par courrier électronique.

### <a name="configure-an-email-alert-for-microsoft-teams-rooms-hardware-issues"></a>Configurer une alerte par courrier électronique pour les problèmes matériels de Microsoft teams

Configurez une règle d’alerte qui recherche sur les appareils Microsoft teams pour lesquels il a rencontré des problèmes matériels au cours de la dernière heure.
1.  Connectez-vous au [portail Microsoft Azure](https://portal.azure.com) et accédez à analyse du journal et sélectionnez votre espace de travail.

2. Accédez à votre espace de travail analyse du journal et sélectionnez **alertes** , puis sélectionnez **nouvelle règle d’alerte** .

3. Sélectionnez **Ajouter une condition** , puis **recherche de journaux personnalisés**

4.  Entrez la requête suivante dans la zone de texte requête de recherche.<br>
    ```
    Event
    | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h)
    | summarize arg_max(TimeGenerated, *) by Computer
    | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSConfMicrophoneStatus_CF, SRSConfSpeakerStatus_CF, SRSDefaultSpeakerStatus_CF, SRSCameraStatus_CF, SRSFORDStatus_CF, SRSMotionSensorStatus_CF, SRSHDMIIngestStatus_CF, SRSEventDescription_CF
    |sort by TimeGenerated desc
    ```

5.  Configurez les paramètres de logique d’alerte:<br>
    **Basé sur:** Nombre de résultats<br>
    **État:** Plus, puis<br>
    **Treshold:** 0<br>

6. Configurez les paramètres d’évaluation et sélectionnez **Terminer**: <br>
    **Période (en minutes):** 60<br>
    **Fréquence (en minutes):** 60<br>

7. Configurer les groupes d’action:
    1.  Sélectionner **créer**
    2.  Donnez des noms appropriés aux champs *nom du groupe d’action* et *nom court* .
    3.  Spécifiez un *nom d’action* unique et sélectionnez **email/SMS/émission/voix**, puis sélectionnez **modifier les détails**.
    4.  Cochez la case message électronique et indiquez l’adresse de messagerie de la personne ou du groupe qui recevra les alertes.
    5.  Vous pouvez également fournir votre numéro de téléphone pour être informé des SMS, un appel audio ou les deux.
    6. Sélectionnez **OK**.

8. **Personnalisez les actions** si vous souhaitez remplacer la ligne d’objet des alertes par courrier électronique.

9. Spécifiez le nom et la description de la règle.<br>
    **Nom de la règle:** Alerte d’échec du matériel dans Microsoft teams<br>
    **Description:** Liste des périphériques ayant rencontré un problème de matériel au cours de la dernière heure<br>

10. Sélectionnez la gravité prévue, puis vérifiez que la règle est activée.

11. Sélectionnez **créer une règle d’alerte**.

### <a name="configure-an-email-alert-for-microsoft-teams-rooms-application-issues"></a>Configurer une alerte par courrier électronique pour les problèmes liés à l’application Microsoft teams

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

![Exemple de message d’alerte de moniteur Azure] (../media/Deploy-Azure-Monitor-6.png "Exemple de message d’alerte de moniteur Azure")

## <a name="configure-all-devices-for-azure-monitoring"></a>Configurer tous les appareils pour la surveillance Azure
<a name="configure_all_devices"></a> Après avoir configuré les tableaux de bord et les alertes, vous pouvez configurer et configurer l’agent de surveillance Microsoft sur tous les appareils Microsoft teams pour terminer le déploiement de votre analyse.

Même si vous pouvez installer et configurer l’agent de surveillance Microsoft manuellement sur chaque appareil, nous vous conseillons vivement d’utiliser les outils et méthodes de déploiement de logiciels existants.

Si vous créez vos appareils Microsoft teams pour la première fois, vous souhaiterez peut-être inclure les étapes de configuration et de configuration de l’agent de contrôle Microsoft dans le cadre de votre processus de génération. Pour plus d’informations, voir [installer l’agent à l’aide de la ligne de commande](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows#install-the-agent-using-the-command-line).

### <a name="deploying-microsoft-monitoring-agent-by-using-a-group-policy-object-gpo"></a>Déploiement de Microsoft Monitoring agent à l’aide d’un objet de stratégie de groupe (GPO)

Si vous avez déjà déployé les périphériques de votre équipe Microsoft teams avant d’implémenter l’analyse Azure, vous pouvez utiliser le script fourni pour configurer et configurer les agents à l’aide d’objets de stratégie de groupe Active Directory.

1.  Créez un chemin réseau partagé et octroyez l’accès en lecture au groupe **ordinateurs du domaine** .

2.  Télécharger la version 64 bits de l’agent de surveillance Microsoft pour Windows à partir de<https://go.microsoft.com/fwlink/?LinkID=517476>

3.  Extrayez le contenu du package d’installation vers le partage réseau.
    1.  Ouvrez une fenêtre d’invite de commandes, puis exécutez **MMASetup-amd64. exe/c.**
    2.  Spécifiez le partage que vous venez de créer, puis extrayez le contenu.

4.  Créez un nouvel objet de stratégie de groupe et attribuez-le à l’unité d’organisation où se trouvent les comptes d’ordinateur de Microsoft Teams.

5.  Configurer une stratégie d’exécution PowerShell:
    1.  Modifiez l’objet de stratégie de groupe que vous venez de créer \\ , \\ puis sélectionnez \\ stratégies de \\ configuration de l’ordinateur modèles d’administration Composants Windows PowerShell Windows PowerShell
    2.  Activez l' **exécution du script** et la **stratégie d’exécution** définies pour autoriser les **scripts locaux**.

6.  Configurez le script de démarrage:
    1.  Copiez le script suivant et enregistrez-le en tant que Install-MMAgent. ps1.
    2.  Modifiez les paramètres WorkspaceId, WorkspaceKey et SetupPath en fonction de votre configuration.
    3.  Modifiez le même objet de stratégie de groupe et sélectionnez stratégies \\ \\ de configuration de \\ l’ordinateur scripts de paramètres Windows (démarrage/arrêt).
    4.  Double-cliquez pour sélectionner **démarrage**, puis sélectionnez **scripts PowerShell**.
    5.  Sélectionnez **afficher les fichiers**, puis copiez le fichier **install-mmagent. ps1** dans ce dossier.
    6.  Cliquez sur **Ajouter**, puis sur **Parcourir**.
    7.  Sélectionnez le script PS1 que vous venez de copier.

7.  Les appareils Microsoft teams salles doivent installer et configurer l’agent de surveillance Microsoft avec le second redémarrage.

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
> Vous pouvez vous référer à l’article [gestion et maintenance de l’agent d’analyse du journal](https://docs.microsoft.com/azure/azure-monitor/platform/agent-manage) lorsque vous avez besoin de reconfigurer un agent, de le déplacer vers un autre espace de travail ou de modifier les paramètres de proxy après l’installation initiale.

## <a name="additional-solutions"></a>Solutions supplémentaires
<a name="Solutions"> </a>

Le moniteur Azure fournit des solutions de gestion intégrées par le biais de la [Galerie de solutions](https://docs.microsoft.com/azure/azure-monitor/insights/solutions) pour vous aider à surveiller votre environnement. Nous vous recommandons vivement d’ajouter également les solutions de [gestion des alertes](https://docs.microsoft.com/azure/azure-monitor/platform/alert-management-solution) et d’intégrité des agents d' [analyse du journal Azure](https://docs.microsoft.com/azure/azure-monitor/insights/solution-agenthealth) à votre espace de travail.

> [!NOTE]
> La solution d’intégrité des agents peut vous aider à identifier les agents de surveillance Microsoft obsolètes ou défectueux au sein de votre environnement, et la solution de gestion des alertes fournit des détails sur les alertes déclenchées au cours d’une période donnée.

## <a name="see-also"></a>Voir aussi

[Planifier la gestion des salles de Microsoft teams avec Azure Monitor](azure-monitor-plan.md)

[Gérer les appareils de salle Microsoft teams avec Azure Monitor](azure-monitor-manage.md)
