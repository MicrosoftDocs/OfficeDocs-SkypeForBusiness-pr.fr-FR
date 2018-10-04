---
title: Déploiement de la gestion de Skype Room Systems v2 avec OMS
ms.author: jambirk
author: Turgayo
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d86ff657-ee92-4b06-aee3-d4c43090bdcb
description: Cet article explique comment déployer la gestion des systèmes de salle Skype v2 périphériques d’une manière intégrée, de bout en bout à l’aide de Microsoft Operations Management Suite.
ms.openlocfilehash: 5ef935f30bfdb5036c87fe24d9456af1b52925e5
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/04/2018
ms.locfileid: "25371379"
---
# <a name="deploy-skype-room-systems-v2-management-with-oms"></a>Déploiement de la gestion de Skype Room Systems v2 avec OMS

Cet article explique comment configurer et déployer une gestion intégrée, de bout en bout des périphériques v2 de systèmes de salle Skype à l’aide de Microsoft Operations Management Suite.

Vous pouvez configurer Microsoft Operations Management Suite pour fournir la télémétrie de base et les alertes qui vous aideront à gérer Skype équipements de salle de réunion. Comme votre solution de gestion ailleurs, vous pouvez décider de déployer des données supplémentaires et les fonctionnalités de gestion pour créer une vue plus détaillée de performances et la disponibilité des périphériques.

En suivant ce guide, vous pouvez utiliser un tableau de bord à l’exemple suivant pour obtenir le statut détaillé, création de rapports pour la disponibilité des périphériques, application et d’intégrité du matériel et la distribution de systèmes de salle Skype v2 application version.

![Affichage d’exemple OMS pour SRS v2] (../../media/Deploy_OMS_1.png "Affichage d’exemple OMS pour SRS v2")

À haut niveau, vous devez effectuer les tâches suivantes :


1.  [Valider la configuration de la Suite de gestion des opérations](with-oms.md#validate_OMS)
2.  [Configurer les périphériques de test pour les paramètres de gestion des opérations Management Suite](with-oms.md#configure_test_devices)
3.  [Mapper les champs personnalisés](with-oms.md#Custom_fields)
4.  [Définir les affichages v2 de systèmes de salle Skype dans la Suite de gestion des opérations](with-oms.md#Define_Views)
5.  [Définir des alertes](with-oms.md#Alerts)
6.  [Configurer tous les périphériques pour la Suite de gestion des opérations](with-oms.md#configure_all_devices)
7.  [Configurer d’autres solutions de la Suite de gestion des opérations](with-oms.md#Solutions)

> [!IMPORTANT]
> Bien que la configuration minimale, la Suite de gestion des opérations permet de surveiller un ordinateur exécutant un système d’exploitation Windows, il y a encore certaines étapes Skype salle systèmes v2 spécifiques que vous devez prendre avant de commencer le déploiement des agents à toutes les salles de Skype Périphériques de systèmes.
> Par conséquent, nous vous recommandons vivement de que procéder à toutes les étapes de configuration dans le bon ordre pour un contrôle du programme d’installation et la configuration. La qualité du résultat final dépend beaucoup de la qualité de la configuration initiale.

## <a name="validate-operations-management-suite-configuration"></a>Valider la configuration de la Suite de gestion des opérations
<a name="validate_OMS"> </a>

Vous devez disposer d’un espace de travail Suite de gestion des opérations pour démarrer la collecte de journaux à partir des périphériques v2 de systèmes de salle Skype. Un espace de travail est un environnement de journal Analytique unique avec son propre référentiel de données, les sources de données et les solutions. Si vous disposez déjà d’un espace de travail Analytique de journal existante, vous pouvez l’utiliser pour analyser votre déploiement de v2 Skype salle systèmes ou vous pouvez créer un espace de travail journal Analytique dédié spécifique à votre contrôle de systèmes de salle Skype v2 a besoin.

Si vous avez besoin créer un nouvel espace de travail de journal Analytique, suivez les instructions de l’article [créer un espace de travail Analytique journal dans le portail Azure](https://docs.microsoft.com/azure/log-analytics/log-analytics-quick-create-workspace)

> [!NOTE]
> Pour utiliser journal Analytique avec la Suite de gestion des opérations, vous devez posséder un abonnement Azure actif. Si vous ne disposez d’un abonnement Azure, vous pouvez créer [un abonnement d’évaluation gratuit](https://azure.microsoft.com/free) comme point de départ.


### <a name="configure-operations-management-suite-to-collect-skype-room-systems-v2-event-logs"></a>Configurer la Suite de gestion des opérations pour collecter des journaux des événements Skype salle systèmes v2

Journal Analytique collecte uniquement les événements dans les journaux des événements Windows qui sont spécifiés dans les paramètres. Pour chaque journal, seuls les événements avec les niveaux de gravité sélectionnés sont collectés.

Vous devez configurer la Suite de gestion des opérations pour collecter les journaux requis pour surveiller l’état des périphériques et d’applications v2 Skype salle systèmes. Les appareils v2 Skype salle systèmes utilisent le journal des événements **Système de salle Skype** .

Pour configurer la Suite de gestion des opérations pour collecter les événements de v2 Skype salle systèmes, voir [les sources de données de journal des événements Windows dans le journal Analytique](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-windows-events)

![Paramètres du journal des événements] (../../media/Deploy_OMS_2.png "Paramètres du journal des événements")


> [!IMPORTANT]
> Sélectionnez le journal des événements **Système de salle Skype** , puis activez les cases à cocher **erreur**, **Avertissement**et **informations** .

## <a name="configure-test-devices-for-operations-management-suite-setup"></a>Configurer les périphériques de test du programme d’installation de la Suite de gestion des opérations
<a name="configure_test_devices"> </a>

Vous devez préparer la Suite de gestion des opérations pour être en mesure de surveiller les événements Skype salle systèmes v2. Vous devez déployer les agents Operations Management Suite à une ou deux périphériques v2 de systèmes de salle Skype que vous avez accès physique à et ces derniers sont les périphériques de test générer des données et l’envoyer à l’espace de travail journal Analytique.

### <a name="install-operations-management-suite-agents-to-test-devices"></a>Installer des agents Operations Management Suite pour tester les périphériques

Déployer l’agent de la Suite de gestion des opérations sur les périphériques de test en suivant les instructions fournies dans [les ordinateurs Windows de se connecter au service journal Analytique dans Azure](https://docs.microsoft.com/azure/log-analytics/log-analytics-agent-windows). Cet article donne des informations détaillées sur les étapes de déploiement de Microsoft surveillance Agent pour Windows, des instructions permettant d’obtenir *l’ID de l’espace de travail* Suite de gestion des opérations et la *clé primaire* pour obtenir des périphériques v2 de systèmes de salle de Skype connecté à votre déploiement de la Suite de gestion des opérations et étapes permettant de vérifier la connectivité de l’agent au journal Analytique.

### <a name="generate-sample-skype-room-systems-events"></a>Générer des exemples d’événements systèmes de salle Skype

Une fois que l’agent Operations Management Suite est déployé sur les périphériques de test, vérifiez que les données du journal des événements requis sont rassemblées par journal Analytique.

1.  Connectez-vous au [portail Microsoft Operations Management Suite](https://aka.ms/omsportal).

2.  Répertorie les événements générés par un appareil v2 de systèmes de salle de Skype :
    1.  Accédez à la **Recherche des journaux** et utiliser une requête pour récupérer les enregistrements dont le champ personnalisé.
    2.  Exemple de requête :`Event | where Source == "SRS-App"`

3.  Assurez-vous que la requête renvoie les enregistrements du journal qui incluent des événements de pulsation correcte.

4.  Générer un problème de configuration matérielle et valider que les événements requis sont enregistrés dans la Suite de gestion des opérations.
    1.  Déconnectez un des périphériques sur le système de v2 Skype salle systèmes de test. Cela peut être la caméra, téléphone mains libres, microphone ou affichage de la salle de premier plan
    2.  Attendez 10 minutes pour le journal des événements doivent être renseignés dans la Suite de gestion des opérations.
    3.  Utiliser une requête d’événements d’erreur de matériel de liste :`Event | where EventID == 3001`

5.  Générer un problème d’application et valider que les événements requis sont enregistrés.
    1.  Modifier la configuration de l’application Skype salle systèmes v2, puis tapez une paire adresse/mot de passe de protocole SIP (Session Initiation) incorrect.
    2.  Attendez 10 minutes pour le journal des événements doivent être renseignés dans la Suite de gestion des opérations.
    3.  Utiliser une requête d’événements d’erreur liste application :`Event | where EventID == 2001`

> [!IMPORTANT]
> Ces exemples les journaux des événements sont requis avant de pouvoir configurer des champs personnalisés. Ne pas passer à l’étape suivante jusqu'à ce que vous avez collecté les journaux d’événements.

## <a name="map-custom-fields"></a>Mapper les champs personnalisés
<a name="Custom_fields"> </a>

Vous utilisez des champs personnalisés pour extraire des données spécifiques dans les journaux des événements. Vous devez définir des champs personnalisés qui seront utilisés ultérieurement des mosaïques, les tableaux de bord et des alertes. Voir [les champs personnalisés dans le journal Analytique](https://docs.microsoft.com/azure/log-analytics/log-analytics-custom-fields) et de vous familiariser avec les concepts avant de commencer la création de vos champs personnalisés.

Pour extraire vos champs personnalisés hors les journaux des événements capturés, procédez comme suit :

1. Connectez-vous au [portail Microsoft Operations Management Suite](https://aka.ms/omsportal).

2. Répertorie les événements générés par un appareil v2 de systèmes de salle de Skype :
   1.  Accédez à la **Recherche des journaux** et utiliser une requête pour récupérer les enregistrements dont le champ personnalisé.
   2.  Exemple de requête :`Event | where Source == "SRS-App"`

3. Sélectionnez une des enregistrements, sélectionnez le bouton situé à gauche et démarrer l’Assistant d’extraction de champ.

   ![Assistant d’extraction de champ] (../../media/Deploy_OMS_3.png "Assistant d’extraction de champ")

4. Mettez en surbrillance les données que vous souhaitez extraire la RenderedDescription et fournir un champ de titre. Les noms de champ que vous devez utiliser sont fournies dans le tableau 1.

   ![Définition de champ personnalisé] (../../media/Deploy_OMS_4.png "Définition de champ personnalisé")

5. Utilisez les mappages indiqués dans le *tableau 1*. Opérations Management Suite ajoute automatiquement le ** \_trésorerie** lorsque vous définissez le nouveau champ de chaîne.

> [!IMPORTANT]
> N’oubliez pas que tous les champs JSON et opérations Management Suite respectent la casse.
> 
> Prêtez attention à l’état de la case à cocher EventID dans le tableau ci-dessous. Assurez-vous que vous vérifiez l’état de cette case à cocher pour la Suite de gestion des opérations extraire des valeurs de champ personnalisé avec succès.
> 
> ![Définition de champ personnalisé] (../../media/Deploy_OMS_5.png "Définition de champ personnalisé")

**Le tableau 1**

| Champ JSON                   | Champ OMS personnalisé           | ID d’événement        |
|:-----------------------------|:---------------------------|:----------------|
| Description                  | SRSEventDescription_CF     | Non sélectionnée    |
| ResourceState                | SRSResourceState_CF        | Non sélectionnée    |
| NomOpération                | SRSOperationName_CF        | Non sélectionnée    |
| OperationResult              | SRSOperationResult_CF      | Non sélectionnée    |
| OS                           | SRSOSVersion_CF            | Non sélectionnée    |
| OSVersion                    | SRSOSLongVersion_CF        | Non sélectionnée    |
| Alias                        | SRSAlias_CF                | Non sélectionnée    |
| DisplayName                  | SRSDisplayName_CF          | Non sélectionnée    |
| AppVersion                   | SRSAppVersion_CF           | Non sélectionnée    |
| IPv4Address                  | SRSIPv4Address_CF          | Non sélectionnée    |
| IPv6Address                  | SRSIPv6Address_CF          | Non sélectionnée    |
| Avant de l’état d’affichage de la salle | SRSFORDStatus_CF           | 3001            |
| État de l’appareil photo                | SRSCameraStatus_CF         | 3001            |
| État de Microphone de conférence | SRSConfMicrophoneStatus_CF | 3001            |
| État de haut-parleur de conférence    | SRSConfSpeakerStatus_CF    | 3001            |
| Haut-parleur statut par défaut       | SRSDefaultSpeakerStatus_CF | 3001            |
| État de détecteur de mouvement         | SRSMotionSensorStatus_CF   | 3001            |
| État d’acquisition HDMI           | SRSHDMIIngestStatus_CF     | 3001            |


## <a name="define-the-skype-room-systems-v2-views-in-operations-management-suite"></a>Définir les affichages v2 de systèmes de salle Skype dans la Suite de gestion des opérations
<a name="Define_Views"> </a>

Une fois que la collecte des données et des champs personnalisés sont mappées, vous pouvez utiliser Concepteur de vues de Suite de gestion des opérations pour développer un tableau de bord contenant des mosaïques différentes pour surveiller les systèmes de salle Skype v2 événements. Utilisez le concepteur de vues pour créer les mosaïques suivantes. Pour plus d’informations, consultez [Concepteur de vues utilisées pour créer des vues personnalisées dans le journal Analytique](https://docs.microsoft.com/azure/log-analytics/log-analytics-view-designer)

> [!NOTE]
> Les étapes précédentes dans ce guide doivent être effectuées pour les mosaïques de tableau de bord fonctionnent correctement.


### <a name="create-a-skype-room-systems-v2-dashboard-by-using-the-import-method"></a>Créer un tableau de bord v2 Skype salle systèmes à l’aide de la méthode d’importation

Vous pouvez importer un tableau de bord Suite de gestion des opérations et démarrer l’analyse de vos périphériques immédiatement. Procédez comme suit pour importer le tableau de bord :

1.  Obtenez le fichier de tableau de bord [SkypeRoomSystems_v2.omsview](https://download.microsoft.com/download/9/0/D/90D4826A-9FD2-47D2-B911-97BF1737F4F7/SkypeRoomSystems_v2.omsview) .
2.  Connectez-vous au [portail Microsoft Operations Management Suite](https://aka.ms/omsportal).
3.  Ouvrez le **Concepteur de vues**.
4.  Sélectionnez **Importer**, puis sélectionnez le fichier **SkypeRoomSystems_v2.omsview** .
5.  Cliquez sur **Enregistrer**.

### <a name="create-a-skype-room-systems-v2-dashboard-manually"></a>Créer un tableau de bord v2 Skype salle systèmes manuellement

Vous pouvez également créer votre propre tableau de bord et ajouter uniquement les mosaïques que vous souhaitez analyser.

#### <a name="configure-the-overview-tile"></a>Configurer la vignette de vue d’ensemble
1.  Ouvrez le **Concepteur de vues**.
2.  Sélectionnez la **Vignette de vue d’ensemble**et sélectionnez à partir de la galerie de **deux nombres** .
3.  Nom de la mosaïque **Skype salle systèmes v2**.
4.  Définir la **première mosaïque**:<br>
    **Légende :** Périphériques qui a envoyé une pulsation au moins une fois depuis le mois dernier<br>
    **Requête :**```Event | where EventLog == "Skype Room System" and TimeGenerated > ago(30d) | summarize TotalSRSDevices = dcount(Computer)```
5.  Définir la **deuxième mosaïque**:<br>
    **Légende :** Dispositifs actifs qui a envoyé une pulsation au sein de la dernière heure<br>
    **Requête :**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(1h) | summarize TotalSRSDevices = dcount(Computer)```
6.  Sélectionnez **Appliquer**.

### <a name="create-a-tile-that-displays-active-devices"></a>Créer une mosaïque qui affiche les périphériques actives
1.  Sélectionnez **Afficher le tableau de bord** à ajouter votre mosaïques.
2.  Sélectionnez le **nombre et la liste** dans la galerie
3.  Définir les propriétés **générales** :<br>
    **Titre de groupe :** État de pulsation<br>
    **Nouveau groupe :** Sélectionné
4.  Définissez les propriétés de **Mosaïque** :<br>
    **Légende :** Dispositifs actifs (pulsation envoyée dans les 20 dernières minutes)<br>
    **Requête de mosaïque : ** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize AggregatedValue = count() by Computer | count```
5.  Définissez les propriétés de **liste** :<br>
    **Requête de liste :**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
6.  Définir les **titres des colonnes**:<br>
    **Nom :** Nom d’affichage<br>
    **Valeur :** Dernière pulsation
7.  Définir la **requête de Navigation**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  Sélectionnez **Appliquer**, puis sur **Fermer**.

### <a name="create-a-tile-that-displays-devices-that-have-connectivity-issues"></a>Créer une mosaïque qui affiche les périphériques qui ont des problèmes de connectivité
1.  Sélectionnez le **nombre et la liste** dans la galerie, puis ajoutez une nouvelle mosaïque.
2.  Définir les propriétés **générales** :<br>
    **Titre de groupe :** Laissez vide<br>
    **Nouveau groupe :** Non sélectionnée
3.  Définissez les propriétés de **Mosaïque** :<br>
    **Légende :** Périphériques inactifs (aucun message heartbeat envoyé dans les 20 dernières minutes)<br>
    **Requête de mosaïque : ** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize LastHB = max(TimeGenerated) by Computer | where LastHB < ago(20m) | count```
4.  Définissez les propriétés de **liste** :<br>
    **Requête de liste :**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize TimeGenerated = max(TimeGenerated) by Computer | where TimeGenerated < ago(20m) | order by TimeGenerated```
5.  Définir les **titres des colonnes**:<br>
    **Nom :** Nom d’affichage<br>
    **Valeur :** Dernière pulsation
6.  Définir la **requête de Navigation**:<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
7.  Sélectionnez **Appliquer**, puis sur **Fermer**.

### <a name="create-a-tile-that-displays-devices-that-have-a-hardware-error"></a>Créer une mosaïque qui affiche les périphériques qui ont une erreur matérielle

1.  Sélectionnez le **nombre et la liste** dans la galerie, puis ajoutez une nouvelle mosaïque.
2.  Définir les propriétés **générales** :<br>
    **Titre de groupe :** État du matériel<br>
    **Nouveau groupe :** Sélectionné
3.  Définissez les propriétés de **Mosaïque** :<br>
    **Légende :** Périphériques qui a rencontré une erreur matérielle dans la dernière heure <br>
    **Requête de mosaïque : ** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```
4.  Définissez les propriétés de **liste** :<br>
    **Requête de liste :**```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer```
5.  Définir les **titres des colonnes**:<br>
    **Nom :** Nom d’affichage<br>
    **Valeur :** Dernière erreur
6.  Définir la **requête de Navigation**:<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == 3001 and EventLevelName == "Error" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSConfMicrophoneStatus_CF, SRSConfSpeakerStatus_CF, SRSDefaultSpeakerStatus_CF, SRSCameraStatus_CF, SRSFORDStatus_CF, SRSMotionSensorStatus_CF, SRSHDMIIngestStatus_CF, SRSEventDescription_CF | sort by TimeGenerated desc```
7.  Sélectionnez **Appliquer**, puis sur **Fermer**.

### <a name="create-a-tile-that-displays-skype-room-systems-v2-operating-system-versions"></a>Créer une mosaïque qui affiche les versions de système d’exploitation de systèmes de salle Skype v2

1.  Sélectionnez **café et la liste** de la galerie, puis ajoutez une nouvelle mosaïque.
2.  Définir les propriétés **générales** :<br>
    **Titre de groupe :** Détails de Syetem d’exploitation <br>
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
    **Nom :** Nom d’affichage<br>
    **Valeur :** Laissez vide
7.  Définir la **requête de Navigation**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSDisplayName_CF, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  Sélectionnez **Appliquer** , puis sur **Fermer**.

### <a name="create-a-tile-that-displays-skype-room-systems-v2-application-versions"></a>Créer une mosaïque qui affiche les versions de l’application v2 systèmes de salle de Skype

1.  Sélectionnez **café et la liste** de la galerie, puis ajoutez une nouvelle mosaïque.
2.  Définir les propriétés **générales** :<br>
    **Titre de groupe :** Détails de l’application v2 systèmes de salle de Skype <br>
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
    **Nom :** Nom d’affichage<br>
    **Valeur :** Laissez vide
7.  Définir la **requête de Navigation**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  Sélectionnez **Appliquer** , puis sur **Fermer**.

### <a name="create-a-tile-that-displays-devices-that-have-an-application-error"></a>Créer une mosaïque qui affiche les périphériques qui ont une erreur d’application

1.  Sélectionnez le **nombre et la liste** dans la galerie, puis ajoutez une nouvelle mosaïque.
2.  Définir les propriétés **générales** .<br>
    **Titre de groupe :** Laissez vide<br>
    **Nouveau groupe :** Non sélectionnée
3.  Définir les propriétés de **Mosaïque** .<br>
    **Légende :** Périphériques qui a rencontré une erreur d’application dans la dernière heure<br>
    **Requête de mosaïque : ** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```
4.  Définir les propriétés de la **liste** .<br>
    **Requête de liste :**```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
5.  Définir les **titres des colonnes**.<br>
    **Nom :** Nom d’affichage<br>
    **Valeur :** Dernière erreur
6.  Définir la **requête de Navigation**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == 2001 and EventLevelName == "Error" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF | sort by TimeGenerated desc```
7.  Sélectionnez **Appliquer** , puis sur **Fermer**.

### <a name="create-a-tile-that-displays-devices-that-have-been-restarted"></a>Créer une mosaïque qui affiche les périphériques qui ont été redémarrés.

1.  Sélectionnez le **nombre et la liste** dans la galerie, puis ajoutez une nouvelle mosaïque.
2.  Définir les propriétés **générales** .<br>
    **Titre de groupe :** Laissez vide<br>
    **Nouveau groupe :** Non sélectionnée
3.  Définir les propriétés de **Mosaïque** .<br>
    **Légende :** Périphériques où l’application a été redémarrée dans la dernière 24 heures, nombre de redémarrages<br>
    **Requête de mosaïque : ** ```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | summarize AggregatedValue = count() by Computer | count```
4.  Définir les propriétés de la **liste** .<br>
    **Requête de liste :**```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | order by TimeGenerated | summarize AggregatedValue = count(EventID) by Computer```
5.  Définir les **titres des colonnes**.<br>
    **Nom :** Nom d’affichage<br>
    **Valeur :** Nombre de redémarrages
6.  Définir la **requête de Navigation**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
7.  Sélectionnez **Appliquer** , puis sur **Fermer**.
8.  Sélectionnez **Enregistrer** pour enregistrer votre tableau de bord.

Maintenant, vous avez terminé la création de votre vues.

Vous pouvez utiliser le portail Microsoft Operations Management Suite ou les clients mobiles Suite de gestion des opérations pour [Windows Phone](https://www.microsoft.com/en-us/store/p/microsoft-operations-management-suite/9wzdncrfjz2r), [iOS](https://itunes.apple.com/us/app/microsoft-operations-management-suite/id1042424859)ou [Android](https://play.google.com/store/apps/details?id=com.microsoft.operations.AndroidPhone) pour accéder à vos vues.

## <a name="configure-alerts-in-operations-management-suite"></a>Configurer les alertes dans la Suite de gestion des opérations
<a name="Alerts"></a> Dispositif de v2 lorsqu’un Skype salle systèmes rencontre un problème, Microsoft Operations Management Suite peut générer des alertes pour avertir les administrateurs avec les détails du problème.

Opérations Suite comprend un mécanisme d’alerte qui s’exécute par le biais de recherches de journal planifiées à intervalles réguliers. Si les résultats de la recherche du journal correspond à certains critères particuliers, un enregistrement de l’alerte est créé.

![Mécanisme d’alerte OMS] (../../media/Deploy_OMS_6.png "Mécanisme d’alerte OMS")

La règle peut exécuter automatiquement une ou plusieurs actions pour vous informer de l’alerte proactive ou d’appeler un autre processus. Les options des alertes de la Suite de gestion des opérations possibles sont les suivants :
-   Envoyer un message électronique
-   Appel d’un processus externe via une demande HTTP POST
-   Une procédure opérationnelle à compter d’Azure Automation Services

Consultez la rubrique [Présentation des alertes dans le journal Analytique](https://docs.microsoft.com/azure/log-analytics/log-analytics-alerts) en savoir plus sur les alertes dans la Suite de gestion des opérations.

> [!NOTE]
> Les exemples suivants envoient des alertes par courrier électronique lorsqu’un périphérique de v2 Skype salle systèmes génère un matériel ou une erreur d’application.


### <a name="configure-an-email-alert-for-skype-room-systems-v2-hardware-issues"></a>Configurer un message d’alerte pour les problèmes matériels Skype salle systèmes v2

Configurer une règle qui vérifie les périphériques v2 Skype salle systèmes qui ont des problèmes liés au matériel au sein de la dernière heure d’alerte.
1.  Connectez-vous au [portail Microsoft Operations Management Suite](https://aka.ms/omsportal).

2.  Sélectionnez la **recherche de journal**.

3.  Entrez la requête suivante, puis sélectionnez **exécuter**.<br>
    ```
    Event
    | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h)
    | summarize arg_max(TimeGenerated, *) by Computer
    | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSConfMicrophoneStatus_CF, SRSConfSpeakerStatus_CF, SRSDefaultSpeakerStatus_CF, SRSCameraStatus_CF, SRSFORDStatus_CF, SRSMotionSensorStatus_CF, SRSHDMIIngestStatus_CF, SRSEventDescription_CF
    |sort by TimeGenerated desc
    ```

4.  Une fois que la requête est exécutée, sélectionnez **l’alerte**. La page **Ajouter une règle de l’alerte** s’ouvre.

5.  Configurer les paramètres d’alerte en utilisant les informations ci-dessous :<br>
    **Nom de règle :** Alerte d’échec de matériel Skype salle systèmes v2<br>
    **Description :** Liste des périphériques qui a rencontré un problème de matériel au sein de la dernière heure<br>
    **Gravité :** Critique<br>
    **Requête :** Utiliser la requête de recherche rempli<br>
    **Fenêtre de temps :** 1 heure<br>
    **Fréquence de l’alerte :** 1 heure<br>
    **Nombre de résultats :** Supérieur à 0<br>
    **Objet de l’e-mail :** Alerte d’échec de matériel Skype salle systèmes v2<br>
    **Destinataires :** Inclure les adresses de messagerie, des points-virgules<br>

6.  Cliquez sur **Enregistrer**.

### <a name="configure-an-email-alert-for-skype-room-systems-v2-application-issues"></a>Configurer un message d’alerte pour les problèmes d’application Skype salle systèmes v2

Configurer une règle d’alerte qui vérifie les périphériques v2 qui ont des problèmes des applications au sein de la dernière heure pour les systèmes de salle Skype.
1.  Sélectionnez la **recherche de journal**.

2.  Entrez la requête suivante, puis sélectionnez **exécuter**.<br>
    ```
    Event
    | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(10h)
    | summarize arg_max(TimeGenerated, *) by Computer
    | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF
    | sort by TimeGenerated desc
    ```

3.  Une fois que la requête est exécutée, sélectionnez **l’alerte**. La page **Ajouter une règle de l’alerte** s’ouvre.

4.  Configurer les paramètres d’alerte en utilisant les informations ci-dessous :<br>
    **Nom de règle :** Alerte d’échec de salle Skype systèmes v2 Application<br>
    **Description :** Liste des périphériques qui a rencontré un problème d’application au sein de la dernière heure<br>
    **Gravité :** Critique<br>
    **Requête :** Utiliser la requête de recherche rempli<br>
    **Fenêtre de temps :** 1 heure<br>
    **Fréquence de l’alerte :** 1 heure<br>
    **Nombre de résultats :** Supérieur à 0<br>
    **Objet de l’e-mail :** Alerte d’échec de salle Skype systèmes v2 Application<br>
    **Destinataires :** Inclure les adresses de messagerie, des points-virgules

5.  Cliquez sur **Enregistrer**.

Maintenant vous avez terminé la définition des alertes. Vous pouvez définir des alertes supplémentaires à l’aide de l’exemple ci-dessus.

Lorsqu’une alerte est générée, vous obtiendrez un message électronique qui répertorie les périphériques qui a rencontré un problème au sein de la dernière heure.

![Courrier électronique d’alerte exemple OMS] (../../media/Deploy_OMS_7.png "Courrier électronique d’alerte exemple OMS")

Vous utilisez une page de paramètres d’alerte pour modifier la configuration d’une alerte existante, ou pour désactiver ou supprimer une alerte.

![Paramètres d’alerte OMS] (../../media/Deploy_OMS_8.png "Paramètres d’alerte OMS")

> [!NOTE]
> Vous devrez peut-être utiliser le portail Azure pour ajouter ou modifier des alertes Operations Management Suite si votre espace de travail Suite de gestion des opérations est configuré pour étendre les alertes de la Suite de gestion des opérations dans Azure. Pour plus d’informations, voir [Extend alertes à partir du portail OMS dans Azure](https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-alerts-extend).

## <a name="configure-all-devices-for-operations-management-suite"></a>Configurer tous les périphériques pour la Suite de gestion des opérations
<a name="configure_all_devices"></a> Après les tableaux de bord et les alertes sont configurés, vous pouvez installer et configurer agents Suite de gestion des opérations sur tous les périphériques v2 de systèmes de salle Skype pour effectuer votre déploiement de surveillance.

Bien que vous pouvez installer et configurer manuellement des agents de la Suite de gestion des opérations sur chaque périphérique, nous vous recommandons vivement de que vous tirer parti des méthodes et des outils de déploiement de logiciels existants.

Si vous créez vos périphériques v2 de systèmes de salle Skype pour la première fois, vous souhaitez inclure les étapes du programme d’installation et configuration de l’agent Suite de gestion des opérations dans le cadre de votre processus de génération. Pour plus d’informations, consultez [installation de l’agent à l’aide de la ligne de commande](https://docs.microsoft.com/azure/log-analytics/log-analytics-agent-windows#install-the-agent-using-the-command-line).

### <a name="deploying-operations-management-suite-agents-by-using-a-group-policy-object"></a>Déploiement d’agents Operations Management Suite à l’aide d’un objet de stratégie de groupe

Si vous déjà déployé vos périphériques v2 de systèmes de salle Skype avant d’implémenter des opérations de gestion Suite, vous pouvez utiliser le script fourni pour installer et configurer les agents à l’aide de stratégies de groupe Active Directory.

1.  Créer un chemin d’accès réseau partagé et accorder un accès en lecture au groupe **d’Ordinateurs du domaine** .

2.  Télécharger la version 64 bits de l’Agent Windows pour les opérations gestion Suite à partir de<https://go.microsoft.com/fwlink/?LinkID=517476>

3.  Extrayez le contenu du package du programme d’installation dans le partage réseau.
    1.  Ouvrez une fenêtre d’invite de commandes et l’exécuter **/c MMASetup-AMD64.exe**
    2.  Spécifiez le partage que vous venez de créer et extraire le contenu.

4.  Créer un nouvel objet de stratégie de groupe et l’affecter à l’unité d’organisation où se trouvent les comptes d’ordinateur Skype salle systèmes v2.

5.  Configurer la stratégie d’exécution PowerShell :
    1.  Modifier l’objet de stratégie de groupe nouvellement créé et accédez à Configuration de l’ordinateur \\ stratégies \\ modèles d’administration \\ composants Windows \\ Windows PowerShell
    2.  Activer l' **Activer l’exécution du Script** et définir la **Stratégie d’exécution** pour **Autoriser les Scripts locaux**.

6.  Configurer le script de démarrage :
    1.  Copiez le script suivant et enregistrez-le sous OMSAgent.ps1-Install.
    2.  Modifier les paramètres WorkspaceId, WorkspaceKey et SetupPath correspondant à votre configuration.
    3.  Modifier le même objet de stratégie de groupe et accédez à Configuration de l’ordinateur \\ stratégies \\ paramètres Windows \\ Scripts (démarrage/arrêt)
    4.  Cliquez deux fois sur **démarrage**, puis sélectionnez **Scripts PowerShell**.
    5.  Sélectionnez **Afficher les fichiers**, puis copiez le fichier **Install-OMSAgent.ps1** à ce dossier.
    6.  Sélectionnez **Ajouter**, puis **Parcourir**.
    7.  Sélectionnez le script ps1 que vous venez de copier.

7.  Les appareils v2 Skype salle systèmes doivent installer et configurer l’agent Microsoft Monitoring du deuxième redémarrage.


~~~
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
~~~

> [!NOTE]
> Vous pouvez faire référence à l’article [gestion et maintenance de l’agent de journal Analytique](https://docs.microsoft.com/azure/log-analytics/log-analytics-agent-manage) lorsque vous devez reconfigurer un agent, déplacer vers un autre espace de travail ou modifier les paramètres de proxy après l’installation initiale.

## <a name="additional-solutions"></a>Autres Solutions
<a name="Solutions"> </a>

Opérations Management Suite fournit des solutions intégrées par le biais de son [Galerie de solutions](https://docs.microsoft.com/azure/log-analytics/log-analytics-add-solutions) pour vous aider analyser votre environnement. Il est vivement recommandé d’ajouter des solutions de [Gestion des alertes](https://docs.microsoft.com/azure/log-analytics/log-analytics-solution-alert-management) et [D’intégrité de l’Agent](https://docs.microsoft.com/azure/operations-management-suite/oms-solution-agenthealth) à votre espace de travail Suite de gestion des opérations.

![Affichages OMS] (../../media/Deploy_OMS_9.png "Affichages OMS")

> [!NOTE]
> La solution d’intégrité de l’Agent peut vous aider à identifier des agents Operations Management Suite obsolètes ou interrompus au sein de votre environnement, et la solution de gestion de l’alerte fournit plus d’informations sur les alertes qui ont été déclenchés dans une période donnée.

## <a name="see-also"></a>Voir aussi

[Planification de la gestion de Skype Room Systems v2 avec OMS](../../plan-your-deployment/clients-and-devices/oms-management.md)

[Gestion des appareils Skype Room Systems v2 avec OMS](../../manage/skype-room-systems-v2/oms.md)
