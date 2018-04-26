---
title: Déploiement de la gestion de Skype Room Systems v2 avec OMS
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 4/20/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: d86ff657-ee92-4b06-aee3-d4c43090bdcb
description: Cet article explique comment déployer la gestion des systèmes de salle Skype v2 périphériques d’une manière intégrée, de bout en bout à l’aide de Microsoft Operations Management Suite.
ms.openlocfilehash: 3d42f0777059870872e871c25591f16c103b5939
ms.sourcegitcommit: f942232d43fc4ad56b34dd400fdb4bca39013f5f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/26/2018
---
# <a name="deploy-skype-room-systems-v2-management-with-oms"></a>Déploiement de la gestion de Skype Room Systems v2 avec OMS
 
Cet article explique comment configurer et déployer la gestion intégrée, de bout en bout pour des dispositifs de v2 Skype salle systèmes à l’aide de Microsoft Operations Management Suite.
  
Vous pouvez configurer Microsoft Operations Management Suite pour fournir de télémétrie de base et les alertes qui vous permettra de gérer Skype, équipements de salle de réunion. Que l’évolution de votre solution de gestion, vous pouvez décider de déployer des données supplémentaires et des fonctions de gestion pour créer un affichage plus détaillé de la disponibilité des périphériques et des performances.

En suivant ce guide, vous pouvez utiliser un tableau de bord comme dans l’exemple suivant pour obtenir le statut détaillé pour la disponibilité des périphériques, application et état du matériel et la distribution de systèmes de salle Skype v2 application version.

![Affichage d’exemple OMS SRS v2] (../../media/Deploy_OMS_1.png "Affichage d’exemple OMS SRS v2")
  
À haut niveau, vous devez effectuer les tâches suivantes :


1.  [Valider la configuration de la Suite de gestion des opérations](with-oms.md#validate_OMS)
2.  [Configurer les périphériques de test pour le programme d’installation de Microsoft Operations Management Suite Gestion](with-oms.md#configure_test_devices)
3.  [Mapper les champs personnalisés](with-oms.md#Custom_fields)
4.  [Définir les vues v2 de systèmes de salle Skype dans la Suite de gestion des opérations](with-oms.md#Define_Views)
5.  [Définir des alertes](with-oms.md#Alerts)
6.  [Configurer tous les périphériques pour la Suite de gestion des opérations](with-oms.md#configure_all_devices)
7.  [Configurer les autres solutions Operations Management Suite](with-oms.md#Solutions)

> [!IMPORTANT]
> Bien qu’avec une configuration minimale, la Suite de gestion des opérations peut surveiller un ordinateur exécutant un système d’exploitation de Windows, il existe toujours certaines étapes de la salle de Skype systèmes spécifiques que vous devez prendre avant de commencer le déploiement des agents sur tous les systèmes de salle de Skype périphériques.
> Par conséquent, nous vous recommandons vivement de que procéder à toutes les étapes de configuration dans le bon ordre pour une installation contrôlée et de la configuration. La qualité du résultat final dépend beaucoup de la qualité de la configuration initiale.

## <a name="validate-operations-management-suite-configuration"></a>Valider la configuration de la Suite de gestion des opérations
<a name="validate_OMS"> </a>

Vous devez disposer d’un espace de travail Microsoft Operations Management Suite pour commencer à collecter les journaux à partir de périphériques de systèmes de salle de Skype. Un espace de travail est un environnement de journal Analytique unique avec son propre référentiel de données, les sources de données et des solutions. Si vous disposez déjà d’un espace de travail Analytique de journal existant, vous pouvez l’utiliser pour surveiller le déploiement de systèmes de salle Skype, ou vous pouvez créer un espace de travail Analytique de journal dédié spécifique à votre surveillance de systèmes de salle Skype a besoin.

Si vous avez besoin créer un nouvel espace de travail du journal Analytique, suivez les instructions de l’article [créer un espace de travail du journal Analytique dans le portail Azure](https://docs.microsoft.com/azure/log-analytics/log-analytics-quick-create-workspace)

> [!NOTE]
> Pour utiliser le journal Analytique avec Operations Management Suite, vous avez besoin à un abonnement Azure actif. Si vous n’avez pas un abonnement Azure, vous pouvez créer [un abonnement d’essai gratuit](https://azure.microsoft.com/free) comme point de départ.


### <a name="configure-operations-management-suite-to-collect-skype-room-systems-event-logs"></a>Configurer les opérations Management Suite pour collecter des journaux d’événements systèmes de salle de Skype

Analytique de journal seulement collecte les événements dans les journaux des événements Windows qui sont spécifiés dans les paramètres. Pour chaque journal, seuls les événements possédant les niveaux de gravité sélectionnés sont collectés.

Vous devez configurer les opérations Management Suite pour collecter les journaux requis pour surveiller l’état de périphérique et d’application des systèmes de salle de Skype. Les périphériques de systèmes de salle Skype v2 utilisent le journal des événements système de salle de Skype.

Pour configurer les opérations Management Suite pour collecter les événements systèmes de salle Skype, consultez [les sources de données de journal des événements Windows dans le journal Analytique](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-windows-events)

![Paramètres du journal des événements] (../../media/Deploy_OMS_2.png "Paramètres du journal des événements")


> [!IMPORTANT]
> Sélectionnez le journal des événements système de salle de Skype et puis activez les cases à cocher **erreur**, **d’Avertissement**et **d’Information** .

## <a name="configure-test-devices-for-operations-management-suite-setup"></a>Configurer les périphériques de test pour le programme d’installation de Microsoft Operations Management Suite
<a name="configure_test_devices"> </a>

Vous devez préparer les opérations Management Suite pour être en mesure de surveiller les événements liés aux systèmes de salle de Skype. D’origine, vous avez besoin déployer les agents d’Operations Management Suite pour seulement une ou deux périphériques de systèmes de salle Skype que vous avez accès physique à et ces derniers sont des dispositifs de test génèrent des données et l’envoyer à l’espace de travail du journal Analytique.

### <a name="install-operations-management-suite-agents-to-test-devices"></a>Installez les agents d’Operations Management Suite pour tester les périphériques

Déployer l’agent de la Suite de gestion des opérations sur les périphériques de test en suivant les instructions fournies sur les [ordinateurs Windows de se connecter au service journal Analytique dans Azure](https://docs.microsoft.com/azure/log-analytics/log-analytics-agent-windows). Cet article donne des informations détaillées sur la procédure de déploiement de Microsoft contrôle l’Agent pour Windows, des instructions pour l’obtention de l’ID d’espace de travail Operations Management Suite et de la clé primaire afin d’obtenir des périphériques de systèmes de salle Skype connecté à votre Déploiement de Suite de gestion des opérations et étapes permettant de vérifier la connectivité de l’agent pour l’Analytique de journal.

### <a name="generate-sample-skype-room-systems-events"></a>Générer des exemples d’événements systèmes de salle de Skype

Une fois que l’agent Microsoft Operations Management Suite est déployée sur les périphériques de test, vérifiez que les données du journal d’événements requis sont collectées par journal Analytique.

1.  Ouvrez une session sur le [portail de Microsoft Operations Management Suite](http://aka.ms/omsportal).

2.  Liste les événements générés par un périphérique de système de salle de Skype :
    1.  Accédez au **Journal recherche** et utiliser une requête pour extraire les enregistrements dont le champ personnalisé.
    2.  Exemple de requête :`Event | where Source == "SRS-App"`

3.  Assurez-vous que la requête renvoie les enregistrements du journal qui incluent les événements de pulsation correcte.

4.  Générer un problème de matériel et de valider que les événements requis sont enregistrés dans la Suite de gestion des opérations.
    1.  Débranchez un périphérique sur le système de Skype salle systèmes de test. Cela peut être la caméra, haut-parleur, micro ou espace avant affichage
    2.  Attendez 10 minutes pour le journal des événements doivent être renseignés dans la Suite de gestion des opérations.
    3.  Utiliser une requête d’événements d’erreur de matériel de liste :`Event | where EventID == 3001`

5.  Générer un problème d’application et de valider que les événements requis sont enregistrés.
    1.  Modifier la configuration de l’application Skype salle systèmes et tapez une paire adresse/mot de passe de Session Initiation Protocol (SIP) incorrect.
    2.  Attendez 10 minutes pour le journal des événements doivent être renseignés dans la Suite de gestion des opérations.
    3.  Utiliser une requête d’événements d’erreur liste application :`Event | where EventID == 2001`

> [!IMPORTANT]
> Ces exemples de journaux d’événements sont nécessaires avant de pouvoir configurer des champs personnalisés. Ne passez à l’étape suivante jusqu'à ce que vous avez collecté les journaux d’événements.

## <a name="map-custom-fields"></a>Mapper les champs personnalisés
<a name="Custom_fields"> </a>

Champs personnalisés vous permet d’extraire des données spécifiques depuis les journaux d’événements. Vous devez définir des champs personnalisés qui seront utilisés ultérieurement des mosaïques, des tableaux de bord et des alertes. Reportez-vous à la section [champs personnalisés dans le journal Analytique](https://docs.microsoft.com/azure/log-analytics/log-analytics-custom-fields) et vous familiariser avec les concepts avant de créer vos champs personnalisés.

Pour extraire vos champs personnalisés sur les journaux d’événements capturés, procédez comme suit :

1.  Ouvrez une session sur le [portail de Microsoft Operations Management Suite](http://aka.ms/omsportal).

2.  Liste les événements générés par un périphérique de système de salle de Skype :
    1.  Accédez au **Journal recherche** et utiliser une requête pour extraire les enregistrements dont le champ personnalisé.
    2.  Exemple de requête :`Event | where Source == "SRS-App"`

3.  Sélectionnez un des enregistrements, cliquez sur le bouton à gauche et démarrez l’Assistant d’extraction de champ.

![Assistant d’extraction de champ] (../../media/Deploy_OMS_3.png "Assistant d’extraction de champ")

4.  Mettez en surbrillance les données que vous souhaitez extraire de la RenderedDescription et de fournir un titre de champ. Les noms de champ que vous devez utiliser sont fournis dans le tableau 1.

![Définition des champs personnalisés] (../../media/Deploy_OMS_4.png "Définition des champs personnalisés")

5.  Utilisez les mappages indiqués dans le tableau 1. Suite de gestion des opérations ajoute automatiquement le ** \_CF** lorsque vous définissez le nouveau champ de chaîne.

> [!IMPORTANT]
> N’oubliez pas que tous les champs JSON et Operations Management Suite respectent la casse.

> Faites attention à l’état de la case à cocher EventID dans le tableau ci-dessous. N’oubliez pas de que vous confirmez l’état de cette case à cocher pour Operations Management Suite à extraire correctement les valeurs de champ personnalisé.
> ![Définition des champs personnalisés] (../../media/Deploy_OMS_5.png "Définition des champs personnalisés") 

**Tableau 1**

| **Champ JSON**               | **Champ personnalisé d’OMS**       | **ID d’événement** |
|------------------------------|----------------------------|-----------------|
| Description                  | SRSEventDescription_CF     | Non sélectionné    |
| ResourceState                | SRSResourceState_CF        | Non sélectionné    |
| OperationName                | SRSOperationName_CF        | Non sélectionné    |
| OperationResult              | SRSOperationResult_CF      | Non sélectionné    |
| OS                           | SRSOSVersion_CF            | Non sélectionné    |
| OSVersion                    | SRSOSLongVersion_CF        | Non sélectionné    |
| Alias                        | SRSAlias_CF                | Non sélectionné    |
| DisplayName                  | SRSDisplayName_CF          | Non sélectionné    |
| AppVersion                   | SRSAppVersion_CF           | Non sélectionné    |
| IPv4Address                  | SRSIPv4Address_CF          | Non sélectionné    |
| IPv6Address                  | SRSIPv6Address_CF          | Non sélectionné    |
| Avant de l’état d’affichage de la salle | SRSFORDStatus_CF           | 3001            |
| État de l’appareil photo                | SRSCameraStatus_CF         | 3001            |
| État de Microphone de conférence | SRSConfMicrophoneStatus_CF | 3001            |
| État de haut-parleur de conférence    | SRSConfSpeakerStatus_CF    | 3001            |
| État par défaut du haut-parleur       | SRSDefaultSpeakerStatus_CF | 3001            |
| État de capteur de mouvement         | SRSMotionSensorStatus_CF   | 3001            |
| Statut de l’acquisition de HDMI           | SRSHDMIIngestStatus_CF     | 3001            |


## <a name="define-the-skype-room-systems-v2-views-in-operations-management-suite"></a>Définir les vues v2 de systèmes de salle Skype dans la Suite de gestion des opérations
<a name="Define_Views"> </a>

Une fois que les données sont collectées et mappage des champs personnalisés, vous pouvez utiliser le Concepteur de vues de Suite de gestion des opérations pour développer un tableau de bord contenant plusieurs mosaïques pour surveiller les systèmes de salle Skype v2 événements. Utilisez le concepteur de vues pour créer les mosaïques suivantes. Pour plus d’informations, consultez [Concepteur de vue utilisé pour créer des vues personnalisées dans le journal Analytique](https://docs.microsoft.com/azure/log-analytics/log-analytics-view-designer)

> [!NOTE]
> Les étapes précédentes de ce guide doivent être effectuées pour des dalles de tableau de bord fonctionnent correctement.


### <a name="create-a-skype-room-systems-v2-dashboard-by-using-the-import-method"></a>Créer un tableau de bord v2 Skype salle systèmes à l’aide de la méthode d’importation

Vous pouvez importer un tableau de bord Operations Management Suite et commencer à analyser vos périphériques immédiatement. Procédez comme suit pour importer le tableau de bord :

1.  Télécharger le [tableau de bord](http://download.microsoft.com/download/9/0/D/90D4826A-9FD2-47D2-B911-97BF1737F4F7/SkypeRoomSystems_v2.omsview).
2.  Ouvrez une session sur le [portail de Microsoft Operations Management Suite](http://aka.ms/omsportal).
3.  Ouvrez le **Concepteur de vues**.
4.  Sélectionnez **Importer**et sélectionnez le fichier **SkypeRoomSystems_v2.omsview** .
5.  Cliquez sur **Enregistrer**.

### <a name="create-a-skype-room-systems-v2-dashboard-manually"></a>Créer un tableau de bord v2 Skype salle systèmes manuellement

Sinon, vous pouvez créer votre propre tableau de bord et ajouter uniquement les morceaux que vous souhaitez surveiller.

#### <a name="configure-the-overview-tile"></a>Configurer la mosaïque de la vue d’ensemble
1.  Ouvrez le **Concepteur de vues**.
2.  Sélectionnez **Aperçu mosaïque**et sélectionnez **deux nombres** de la galerie.
3.  Nom de la mosaïque de **Systèmes de salle de Skype**.
4.  Définir la **première mosaïque**:<br>
    **Légende :** Périphériques envoyé de pulsations au moins une fois depuis le mois dernier<br>
    **Requête :**```Event | where EventLog == "Skype Room System" and TimeGenerated > ago(30d) | summarize TotalSRSDevices = dcount(Computer)```
5.  Définissez la **deuxième mosaïque**:<br>
    **Légende :** Dispositifs actifs envoyé de pulsations au sein de la dernière heure<br>
    **Requête :**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(1h) | summarize TotalSRSDevices = dcount(Computer)```
6.  Sélectionnez **Appliquer**.

### <a name="create-a-tile-that-displays-active-devices"></a>Créer une mosaïque qui affiche les périphériques actifs
1.  Sélectionnez un **Affichage tableau de bord** pour commencer à ajouter vos mosaïques.
2.  Sélectionnez le **numéro et la liste** dans la galerie
3.  Définir les propriétés **générales** :<br>
    **Titre de groupe :** État de pulsation<br>
    **Nouveau groupe :** Sélectionné
4.  Définissez les propriétés de **Mosaïque** :<br>
    **Légende :** Dispositifs actifs (pulsation envoyée dans les dernières minutes 20)<br>
    **Requête de mosaïque :**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize AggregatedValue = count() by Computer | count```
5.  Définissez les propriétés de la **liste** :<br>
    **Requête de liste :**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
6.  Définir les **titres des colonnes**:<br>
    **Nom :** Nom complet<br>
    **Valeur :** Dernière pulsation
7.  Définissez la **requête de Navigation**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  Sélectionnez **Appliquer**, puis sur **Fermer**.

### <a name="create-a-tile-that-displays-devices-that-have-connectivity-issues"></a>Créer une mosaïque qui affiche les périphériques qui ont des problèmes de connectivité
1.  Sélectionnez le **numéro et la liste** dans la galerie, puis ajoutez une nouvelle mosaïque.
2.  Définir les propriétés **générales** :<br>
    **Titre de groupe :** Laisser vide<br>
    **Nouveau groupe :** Non sélectionné
3.  Définissez les propriétés de **Mosaïque** :<br>
    **Légende :** Périphériques inactifs (aucun message de pulsation envoyé dans les dernières minutes 20)<br>
    **Requête de mosaïque :**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize LastHB = max(TimeGenerated) by Computer | where LastHB < ago(20m) | count```
4.  Définissez les propriétés de la **liste** :<br>
    **Requête de liste :**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize TimeGenerated = max(TimeGenerated) by Computer | where TimeGenerated < ago(20m) | order by TimeGenerated```
5.  Définir les **titres des colonnes**:<br>
    **Nom :** Nom complet<br>
    **Valeur :** Dernière pulsation
6.  Définissez la **requête de Navigation**:<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
7.  Sélectionnez **Appliquer**, puis sur **Fermer**.

### <a name="create-a-tile-that-displays-devices-that-have-a-hardware-error"></a>Créer une mosaïque qui affiche les périphériques qui ont une erreur matérielle

1.  Sélectionnez le **numéro et la liste** dans la galerie, puis ajoutez une nouvelle mosaïque.
2.  Définir les propriétés **générales** :<br>
    **Titre de groupe :** Matériel<br>
    **Nouveau groupe :** Sélectionné
3.  Définissez les propriétés de **Mosaïque** :<br>
    **Légende :** Périphériques qui a rencontré une erreur matérielle dans l’heure écoulée <br>
    **Requête de mosaïque :**```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```
4.  Définissez les propriétés de la **liste** :<br>
    **Requête de liste :**```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer```
5.  Définir les **titres des colonnes**:<br>
    **Nom :** Nom complet<br>
    **Valeur :** Dernière erreur
6.  Définissez la **requête de Navigation**:<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == 3001 and EventLevelName == "Error" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSConfMicrophoneStatus_CF, SRSConfSpeakerStatus_CF, SRSDefaultSpeakerStatus_CF, SRSCameraStatus_CF, SRSFORDStatus_CF, SRSMotionSensorStatus_CF, SRSHDMIIngestStatus_CF, SRSEventDescription_CF | sort by TimeGenerated desc```
7.  Sélectionnez **Appliquer**, puis sur **Fermer**.

### <a name="create-a-tile-that-displays-skype-room-systems-application-versions"></a>Créer une mosaïque qui affiche les versions des applications de systèmes de salle de Skype

1.  Sélectionnez **bouée & liste** dans la galerie, puis ajoutez une nouvelle mosaïque.
2.  Définir les propriétés **générales** :<br>
    **Titre de groupe :** Détails de l’application v2 systèmes de salle de Skype <br>
    **Nouveau groupe :** Sélectionné
3.  Définir les propriétés **d’en-tête** :<br>
    **Titre :** Versions d’application<br>
    **Sous-titre :** Périphériques qui exécutent des versions de l’application spécifique
4.  Définissez les propriétés de **l’anneau** :<br>
    **Requête :**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize App_Version = max(SRSAppVersion_CF) by Computer | summarize AggregatedValue = count() by App_Version | sort by App_Version asc```<br>
    **Centre le texte :** Périphériques<br>
    **Opération :** Somme
5.  Définir les propriétés de la **liste** .<br>
    **Requête de liste :**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSAppVersion_CF = max(SRSAppVersion_CF) by Computer | sort by Computer asc```<br>
    **Masquer graphique :** Sélectionné<br>
    **Activer les graphiques sparkline :** Non sélectionné
6.  Définir les **titres des colonnes**.<br>
    **Nom :** Nom complet<br>
    **Valeur :** Laisser vide
7.  Définissez la **requête de Navigation**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  Sélectionnez **Appliquer** , puis sur **Fermer**.

### <a name="create-a-tile-that-displays-devices-that-have-an-application-error"></a>Créer une mosaïque qui affiche les périphériques qui ont une erreur d’application

1.  Sélectionnez le **numéro et la liste** dans la galerie, puis ajoutez une nouvelle mosaïque.
2.  Définir les propriétés **générales** .<br>
    **Titre de groupe :** Laisser vide<br>
    **Nouveau groupe :** Non sélectionné
3.  Définir les propriétés de la **Mosaïque** .<br>
    **Légende :** Périphériques qui a rencontré une erreur d’application durant la dernière heure<br>
    **Requête de mosaïque :**```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```
4.  Définir les propriétés de la **liste** .<br>
    **Requête de liste :**```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
5.  Définir les **titres des colonnes**.<br>
    **Nom :** Nom complet<br>
    **Valeur :** Dernière erreur
6.  Définissez la **requête de Navigation**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == 2001 and EventLevelName == "Error" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF | sort by TimeGenerated desc```
7.  Sélectionnez **Appliquer** , puis sur **Fermer**.

### <a name="create-a-tile-that-displays-devices-that-have-been-restarted"></a>Créer une mosaïque qui affiche les périphériques qui ont été redémarrés.

1.  Sélectionnez le **numéro et la liste** dans la galerie, puis ajoutez une nouvelle mosaïque.
2.  Définir les propriétés **générales** .<br>
    **Titre de groupe :** Laisser vide<br>
    **Nouveau groupe :** Non sélectionné
3.  Définir les propriétés de la **Mosaïque** .<br>
    **Légende :** Périphériques où l’application a été redémarrée dans le dernier 24 heures et le nombre de redémarrages<br>
    **Requête de mosaïque :**```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | summarize AggregatedValue = count() by Computer | count```
4.  Définir les propriétés de la **liste** .<br>
    **Requête de liste :**```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | order by TimeGenerated | summarize AggregatedValue = count(EventID) by Computer```
5.  Définir les **titres des colonnes**.<br>
    **Nom :** Nom complet<br>
    **Valeur :** Nombre de redémarrages
6.  Définissez la **requête de Navigation**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
7.  Sélectionnez **Appliquer** , puis sur **Fermer**.
8.  Sélectionnez **Enregistrer** pour enregistrer votre tableau de bord.

Maintenant, vous avez terminé la création de vos vues.

Pour accéder à vos vues, vous pouvez utiliser le portail de Microsoft Operations Management Suite ou les clients mobiles de Microsoft Operations Management Suite pour [Windows Phone](https://www.microsoft.com/en-us/store/p/microsoft-operations-management-suite/9wzdncrfjz2r), [iOS](https://itunes.apple.com/us/app/microsoft-operations-management-suite/id1042424859)ou [Android](https://play.google.com/store/apps/details?id=com.microsoft.operations.AndroidPhone) .

## <a name="configure-alerts-in-operations-management-suite"></a>Configurer des alertes dans Microsoft Operations Management Suite
<a name="Alerts"></a> Les périphériques lorsqu’un Skype salle systèmes rencontre un problème, de Microsoft Operations Management Suite peuvent déclencher des alertes pour avertir les administrateurs avec les détails du problème.

Opérations Suite comprend un mécanisme d’alerte intégré qui s’exécute par le biais de recherches de journal planifiées à intervalles réguliers. Si les résultats de la recherche du journal correspondent à certains critères particuliers, un enregistrement d’alerte est créé.

![Mécanisme d’alerte OMS] (../../media/Deploy_OMS_6.png "Mécanisme d’alerte OMS")

La règle exécute alors automatiquement une ou plusieurs actions pour vous avertir de l’alerte proactive ou d’appeler un autre processus. Les options possibles avec les alertes de Microsoft Operations Management Suite sont :
-   Envoi d’un e-mail
-   L’appel à un processus externe via une demande HTTP POST
-   Démarrage d’une procédure opérationnelle dans le service d’Azure Automation

Reportez-vous à la section [Présentation des alertes dans le journal Analytique](https://docs.microsoft.com/azure/log-analytics/log-analytics-alerts) pour en savoir plus sur les alertes de Microsoft Operations Management Suite.

> [!NOTE]
> Les exemples suivants envoient des alertes par e-mail lorsqu’un périphérique de système de salle de Skype génère un matériel ou une erreur d’application. 


### <a name="configure-an-email-alert-for-skype-room-systems-hardware-issues"></a>Configurer un message d’alerte pour les problèmes matériels de systèmes de salle de Skype

Configurer une règle d’alerte qui vérifie pour les périphériques de systèmes de salle Skype qui ont eu des problèmes matériels dans la dernière heure.
1.  Ouvrez une session sur le [portail de Microsoft Operations Management Suite](http://aka.ms/omsportal).

2.  Sélectionnez la **recherche dans un journal**.

3.  Entrez la requête suivante, puis sélectionnez **exécuter**.<br>
    ```
    Event
    | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h)
    | summarize arg_max(TimeGenerated, *) by Computer
    | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSConfMicrophoneStatus_CF, SRSConfSpeakerStatus_CF, SRSDefaultSpeakerStatus_CF, SRSCameraStatus_CF, SRSFORDStatus_CF, SRSMotionSensorStatus_CF, SRSHDMIIngestStatus_CF, SRSEventDescription_CF 
    |sort by TimeGenerated desc
    ```

4.  Après l’exécution de la requête, sélectionnez **alerte**. Cela ouvre la page **Ajouter une règle d’alerte** .

5.  Configurer les paramètres d’alerte en utilisant les informations ci-dessous :<br>
    **Nom de règle :** Alerte d’échec de la salle de Skype systèmes matériels<br>
    **Description :** Liste des périphériques qui a rencontré un problème matériel au sein de la dernière heure<br>
    **Gravité :** Critique<br>
    **Requête :** Utilisez la requête de recherche préremplies<br>
    **Fenêtre de temps :** 1 heure<br>
    **Fréquence de l’alerte :** 1 heure<br>
    **Nombre de résultats :** Supérieur à 0<br>
    **Objet de l’e-mail :** Alerte d’échec de la salle de Skype systèmes matériels<br>
    **Destinataires :** Inclure les adresses de messagerie, en utilisant des points-virgules comme séparateurs<br>

6.  Cliquez sur **Enregistrer**.

### <a name="configure-an-email-alert-for-skype-room-systems-application-issues"></a>Configurer un message d’alerte pour les problèmes d’application de systèmes de salle de Skype

Configurer une règle d’alerte, qui vérifie pour les périphériques de systèmes de salle Skype qui ont eu des problèmes de l’application au sein de la dernière heure.
1.  Sélectionnez la **recherche dans un journal**.

2.  Entrez la requête suivante, puis sélectionnez **exécuter**.<br>
    ```
    Event
    | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(10h)
    | summarize arg_max(TimeGenerated, *) by Computer
    | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF
    | sort by TimeGenerated desc
    ```

3.  Après l’exécution de la requête, sélectionnez **alerte**. Cela ouvre la page **Ajouter une règle d’alerte** .

4.  Configurer les paramètres d’alerte en utilisant les informations ci-dessous :<br>
    **Nom de règle :** Alerte d’échec de la salle de Skype systèmes Application<br>
    **Description :** Liste des périphériques qui a rencontré un problème d’application au sein de la dernière heure<br>
    **Gravité :** Critique<br>
    **Requête :** Utilisez la requête de recherche préremplies<br>
    **Fenêtre de temps :** 1 heure<br>
    **Fréquence de l’alerte :** 1 heure<br>
    **Nombre de résultats :** Supérieur à 0<br>
    **Objet de l’e-mail :** Alerte d’échec de la salle de Skype systèmes Application<br>
    **Destinataires :** Inclure les adresses de messagerie, en utilisant des points-virgules comme séparateurs

5.  Cliquez sur **Enregistrer**.

Maintenant vous avez terminé la définition d’alertes. Vous pouvez définir des alertes supplémentaires en utilisant les exemples ci-dessus.

Lorsqu’une alerte est générée, vous obtiendrez un e-mail qui répertorie les périphériques a rencontré un problème au sein de la dernière heure.

![Exemple OMS d’alerte e-mail] (../../media/Deploy_OMS_7.png "Exemple OMS d’alerte e-mail")

Vous utilisez une page de paramètres d’alerte pour modifier la configuration d’une alerte existante, ou pour désactiver ou supprimer une alerte.

![Paramètres d’alerte OMS] (../../media/Deploy_OMS_8.png "Paramètres d’alerte OMS")

> [!NOTE]
> Vous devrez peut-être utiliser le portail Azure pour ajouter ou modifier les alertes de Microsoft Operations Management Suite si votre espace de travail de la Suite de gestion des opérations est configuré pour étendre les alertes Operations Management Suite dans Azure. Pour plus de détails, consultez [extension des alertes du portail OMS dans Azure](https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-alerts-extend).

## <a name="configure-all-devices-for-operations-management-suite"></a>Configurer tous les périphériques pour la Suite de gestion des opérations
<a name="configure_all_devices"></a> Après avoir configuré les tableaux de bord et les alertes, vous pouvez définir et configurer les agents de la Suite de gestion des opérations sur tous les périphériques de systèmes de salle Skype pour effectuer votre déploiement de surveillance.

Bien que vous pouvez installer et configurer les agents Microsoft Operations Management Suite manuellement sur chaque périphérique, nous vous recommandons vivement de que vous exploitez des méthodes et des outils de déploiement de logiciels existants.

Si vous créez vos périphériques de systèmes de salle Skype pour la première fois, vous pouvez souhaiter inclure les étapes d’installation et de configuration de l’agent Operations Management Suite dans le cadre de votre processus de génération. Pour plus d’informations, reportez-vous à la section [installation de l’agent à l’aide de la ligne de commande](https://docs.microsoft.com/azure/log-analytics/log-analytics-agent-windows#install-the-agent-using-the-command-line).

### <a name="deploying-operations-management-suite-agents-by-using-a-group-policy-object"></a>Déploiement d’agents Operations Management Suite à l’aide d’un objet de stratégie de groupe

Si vous déjà déployé vos périphériques de systèmes de salle Skype avant d’implémenter les opérations Management Suite, vous pouvez utiliser le script fourni pour installer et configurer les agents à l’aide de stratégies de groupe Active Directory.

1.  Créer un chemin d’accès de réseau partagé et accordez l’accès en lecture au groupe **Ordinateurs du domaine** .

2.  Télécharger la version 64 bits de l’Agent Windows pour opérations de gestion Suite à partir de<http://go.microsoft.com/fwlink/?LinkID=517476>

3.  Extrayez le contenu du package d’installation dans le partage réseau.
    1.  Ouvrez une fenêtre d’invite de commande et l’exécuter **MMASetup-AMD64.exe /c**
    2.  Spécifiez le partage que vous venez de créer et extraire le contenu.

4.  Créer un nouvel objet de stratégie de groupe et l’affecter à l’unité d’organisation où se trouvent les comptes d’ordinateur de systèmes de salle de Skype.

5.  Configurer la stratégie d’exécution PowerShell :
    1.  Modifier l’objet de stratégie de groupe nouvellement créé et accédez au dossier Configuration de l’ordinateur \\ stratégies \\ les modèles d’administration \\ composants Windows \\ de Windows PowerShell
    2.  Activer l' **activer sur l’exécution du Script** et de définir la **Stratégie d’exécution** pour **Autoriser les Scripts locaux**.

6.  Configurer le script de démarrage :
    1.  Copiez le script suivant et enregistrez-le en tant que OMSAgent.ps1 de l’installation.
    2.  Modifier les paramètres WorkspaceId, WorkspaceKey et SetupPath correspondant à votre configuration.
    3.  Modifier le même objet de stratégie de groupe et accédez au dossier Configuration de l’ordinateur \\ stratégies \\ paramètres Windows \\ Scripts (démarrage/arrêt)
    4.  Cliquez deux fois sur **démarrage**et sélectionnez **Scripts PowerShell**.
    5.  Sélectionnez **Afficher les fichiers**, puis copiez le fichier **OMSAgent.ps1 de l’installation** dans ce dossier.
    6.  Sélectionnez **Ajouter**, puis sur **Parcourir**.
    7.  Sélectionnez le script ps1 que vous venez de copier.

7.  Les périphériques de systèmes de salle Skype doivent installer et configurer l’agent Microsoft Monitoring du deuxième redémarrage.


    ```
    # Install-OMSAgent.ps1
    <# 
    Date:        04/20/2018 
    Script:      Install-OMSAgent.ps1 
    Version:     1.0
    #> 
    
    # Set the parameters
    $WorkspaceId = "<your workspace id>"
    $WorkspaceKey = "<your workspace key>"
    $SetupPath = "\\Server\Share"
    
    $SetupParameters = "/qn NOAPM=1 ADD_OPINSIGHTS_WORKSPACE=1 OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE=0 OPINSIGHTS_WORKSPACE_ID=$WorkspaceId OPINSIGHTS_WORKSPACE_KEY=$WorkspaceKey AcceptEndUserLicenseAgreement=1"
    
    # $SetupParameters = $SetupParameters + " OPINSIGHTS_PROXY_URL=<Proxy server URL> OPINSIGHTS_PROXY_USERNAME=<Proxy server username> OPINSIGHTS_PROXY_PASSWORD=<Proxy server password>"
    
    # Start PowerShell logging
    Start-Transcript -Path C:\OMSAgentInstall.Log  
    
    # Check if the Microsoft Monitoring Agent is installed
    $mma = New-Object -ComObject 'AgentConfigManager.MgmtSvcCfg'
    
    # Check if the Microsoft Monitoring agent is installed 
    if (!$mma)
    {
        #Install agent
        Start-Process -FilePath "$SetupPath\Setup.exe" -ArgumentList $SetupParameters -ErrorAction Stop -Wait
    }
    
    # Check if the agent has a valid configuration
    $CheckOMS = $mma.GetCloudWorkspace($WorkspaceId).AgentId
    if (!$CheckOMS)
    {
        # Apply new configuration
        $mma.AddCloudWorkspace($WorkspaceId, $WorkspaceKey)
        $mma.ReloadConfiguration()
    } 
    
    Stop-Transcript 
    
    ```
    
> [!NOTE]
> Vous pouvez faire référence à l’article de la [gestion et la maintenance de l’agent de journal Analytique](https://docs.microsoft.com/azure/log-analytics/log-analytics-agent-manage) lorsque vous devez reconfigurer un agent, le déplacer vers un autre espace de travail, ou de modifier les paramètres de proxy après l’installation initiale.

## <a name="additional-solutions"></a>Solutions supplémentaires
<a name="Solutions"> </a>

Operations Management Suite fournit des solutions intégrées par le biais de la [Galerie de solutions](https://docs.microsoft.com/azure/log-analytics/log-analytics-add-solutions) supplémentaires permettent de contrôler votre environnement. Il est vivement recommandé d’ajouter des solutions de [Gestion des alertes](https://docs.microsoft.com/azure/log-analytics/log-analytics-solution-alert-management) et de [La santé de l’Agent](https://docs.microsoft.com/azure/operations-management-suite/oms-solution-agenthealth) à votre espace de travail Suite de gestion des opérations.

![Vues de l’OMS] (../../media/Deploy_OMS_9.png "Vues de l’OMS")

> [!NOTE]
> La solution de santé des agents peut vous aider à identifier des agents d’Operations Management Suite obsolètes ou endommagés dans votre environnement, et la solution de gestion des alertes fournit des détails sur les alertes qui ont été déclenchés dans une période donnée.

## <a name="see-also"></a>Voir aussi

#### 
[Planification de la gestion de v2 Skype salle systèmes avec OMS](../../plan-your-deployment/clients-and-devices/oms-management.md)
  
[Gérer les périphériques de v2 Skype salle systèmes avec OMS](../../manage/skype-room-systems-v2/oms.md)