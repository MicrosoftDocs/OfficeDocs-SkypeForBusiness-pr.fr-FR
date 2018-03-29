---
title: Déploiement de la gestion de Skype Room Systems v2 avec OMS
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/20/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: d86ff657-ee92-4b06-aee3-d4c43090bdcb
description: Cet article explique comment déployer la gestion des systèmes de salle Skype v2 périphériques d’une manière intégrée, de bout en bout à l’aide de Microsoft Operations Management Suite.
ms.openlocfilehash: 0d0490d92a5513dad38a9ff6348a957204274878
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-skype-room-systems-v2-management-with-oms"></a>Déploiement de la gestion de Skype Room Systems v2 avec OMS
 
Cet article explique comment déployer la gestion des systèmes de salle Skype v2 périphériques d’une manière intégrée, de bout en bout à l’aide de Microsoft Operations Management Suite. 
  
Vous pouvez configurer Microsoft Operations Management Suite (OMS) pour fournir des données télémétriques de base qui facilitent la gestion des dispositifs de salle de réunion Skype. Une fois que votre solution de gestion acquiert sa maturité, vous pouvez acheter des capacités de données et de gestion supplémentaires pour créer des vues plus précises des performances des appareils.
  
À haut niveau, vous devez effectuer les tâches suivantes :
  
1. [Configurer les appareils pour la gestion OMS ](with-oms.md#config_devices)
    
2. [Mapper les champs personnalisés](with-oms.md#Custom_fields)
    
3. [Définir les vues SRS v2 dans OMS](with-oms.md#Views)
    
## <a name="find-and-record-device-locations-capabilities-and-configurations"></a>Rechercher et enregistrer l’emplacement des appareils, les fonctionnalités et les configurations
<a name="find_devices"> </a>

La première étape consiste à créer une base de données complète regroupant tout l’équipement du système, détaillant les fonctionnalités, la configuration et l’emplacement. Une feuille de calcul peut s’avérer adaptée pour cette tâche dans les petites et moyennes entreprises. Si vous travaillez dans une grande entreprise, vous devriez envisager de recourir à des outils et des services tiers de gestion des ressources. L’important, c’est que vous enregistriez l’emplacement et tous les détails appropriés sur chaque appareil.
  
Une fois cette tâche effectuée, vous pouvez utiliser ces informations pour déléguer des techniciens et gérer les correctifs et les mises à niveau.
  
## <a name="configure-devices-for-oms-management"></a>Configurer les appareils pour la gestion OMS 
<a name="config_devices"> </a>

Pour chaque périphérique SRS, suivez les instructions dans les [ordinateurs Windows de se connecter au service journal Analytique dans Azure](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-windows-agents).
  
## <a name="configure-oms-to-collect-device-event-logs"></a>Configurer OMS pour collecter le journal des événements des appareils
<a name="config_devices"> </a>

Vous devez configurer spécifiquement OMS pour collecter des journaux des événements à partir de périphériques SRS à l’aide de la procédure à [des sources de données de journal des événements Windows dans le journal Analytique](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-data-sources-windows-events). Le journal des événements pour sélectionner SRS est « Système de salle Skype » et vous devez vérifier les cases d’option pour tous les types : erreur, avertissement et informations.
  
## <a name="map-custom-fields"></a>Mapper les champs personnalisés
<a name="Custom_fields"> </a>

Avant de pouvoir utiliser les mosaïques créés dans les [vues de définir le v2 SRS de l’OMS](with-oms.md#Views) , vous devrez créer des champs personnalisés pour votre affichage. Pour plus d’informations sur la création de champs personnalisés, reportez-vous à la section [champs personnalisés dans le journal Analytique](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-custom-fields) .
  
Utiliser les mappages ci-dessous, OMS ajoute automatiquement le _CF lors de la définition du nouveau champ. 
  
> [!IMPORTANT]
> N’oubliez pas que tous les champs JSON et OMS sont sensibles à la casse. 
  
**Mappage des champs personnalisés**

|**Champ JSON**|**Champ personnalisé d’OMS**|
|:-----|:-----|
|Description  <br/> |SRSEventDescription_CF  <br/> |
|ResourceState  <br/> |SRSResourceState_CF  <br/> |
|OperationName  <br/> |SRSOperationName_CF  <br/> |
|OperationResult  <br/> |SRSOperationResult_CF  <br/> |
|OS  <br/> |SRSOSVersion_CF  <br/> |
|OSVersion  <br/> |SRSOSLongVersion_CF  <br/> |
|Alias  <br/> |SRSAlias_CF  <br/> |
|DisplayName  <br/> |SRSDisplayName_CF  <br/> |
|AppVersion  <br/> |SRSAppVersion_CF  <br/> |
|IPv4Address  <br/> |SRSIPv4Address_CF  <br/> |
|IPv6Address  <br/> |SRSIPv6Address_CF  <br/> |
   
## <a name="define-the-srs-v2-views-in-oms"></a>Définir les vues SRS v2 dans OMS
<a name="Views"> </a>

Une fois que les données sont collectées et mappage des champs personnalisés, vous pouvez utiliser le Concepteur de vues OMS pour développer un tableau de bord contenant des mosaïques pour surveiller les événements de v2 SRS. Concepteur de vues permet de créer des mosaïques suivantes, consultez [Concepteur de vue utilisé pour créer des vues personnalisées dans le journal Analytique](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-view-designer) si nécessaire.
  
### <a name="create-a-tile-that-shows-healthy-devices"></a>Créer une mosaïque qui indique les appareils sains

1. Définissez le cas :  
    
    Cette mosaïque affiche tous les appareils ayant envoyé un message de pulsations au cours des 10 dernières minutes.
    
2. Assigner une mosaïque de groupe  
    
   ```
   SRS v2
   ```

3. Case à cocher nouveau groupe
    
4. Ajouter le texte de légende de la mosaïque
    
   ```
   All healthy devices (Heartbeat sent in last 10 minutes)
   ```

5. Entrer la requête de mosaïque
    
   ```
   Type:Event EventLog:"Skype Room System" SRSOperationName_CF:"Heartbeat" TimeGenerated >NOW-10MINUTES|measure count() by SRSDisplayName_CF 
   ```

6. Entrer la requête de liste
    
   ```
   Type:Event EventLog:"Skype Room System" SRSOperationName_CF:"Heartbeat" |measure max(TimeGenerated) as LastHB by SRSDisplayName_CF |Where LastHB>NOW-10MINUTES
   ```

7. Définir le nom des titres de colonne
    
   ```
   Display Name
   ```

8. Définir la valeur des titres de colonne
    
   ```
   Last HB
   ```

9. Entrer la requête de navigation
    
   ```
   {selected item} EventLog:"Skype Room System" SRSOperationName_CF:"Heartbeat"|Dedup SRSDisplayName_CF|Select TimeGenerated, Computer, SRSOperationName_CF, SRSOperationResult_CF,SRSEventDescription_CF, SRSAppVersion_CF, SRSDisplayName_CF, SRSAlias_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF
   ```

### <a name="create-the-tile-that-shows-devices-with-connectivity-issues"></a>Créer la mosaïque qui montre les appareils présentant des problèmes de connectivité

1. Définissez le cas :  
    
    Cette mosaïque affiche tous les appareils qui ont envoyé un message de pulsations au cours des 10 dernières minutes. Ces appareils ont pu rencontrer des problèmes de connectivité avec le réseau, Exchange ou Skype Entreprise.
    
2. Assigner une mosaïque de groupe  
    
   ```
   SRS v2
   ```

3. Ne cochez pas la nouvelle zone de groupe. Vous l’avez déjà fait lors de la création de la mosaïque 1. Vous n’avez donc pas à le refaire.
    
4. Ajouter le texte de légende de la mosaïque
    
   ```
   Devices no longer sending Heartbeat messages
   ```

5. Entrer la requête de mosaïque
    
   ```
   Type:Event EventLog:"Skype Room System" SRSOperationName_CF:"Heartbeat" |measure max(TimeGenerated) as LastHB by Computer|Where LastHB<NOW-10MINUTES
   ```

6. Entrer la requête de liste
    
   ```
   Type:Event EventLog:"Skype Room System" SRSOperationName_CF:"Heartbeat" |measure max(TimeGenerated) as LastHB by Computer|Where LastHB<NOW-10MINUTES
   ```

7. Définir le nom des titres de colonne
    
   ```
   Device Name
   ```

8. Définir la valeur des titres de colonne  
    
   ```
   Last HB
   ```

9. Entrer la requête de navigation
    
   ```
   {selected item} EventLog:"Skype Room System" SRSOperationName_CF:"Heartbeat" |Dedup SRSDisplayName_CF|Select TimeGenerated, Computer, SRSDisplayName_CF, SRSAlias_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF
   ```

### <a name="list-devices-with-a-hardware-error"></a>Liste des appareils présentant une erreur matérielle 

1. Définissez le cas :  
    
   Cette mosaïque affiche tous les périphériques qui a envoyé un message indiquant un un ou plusieurs problèmes de composant matériel dans les dix dernières minutes. 
    
2. Assigner une mosaïque de groupe  
    
   ```
   SRS v2
   ```

3. Ne cochez pas la nouvelle zone de groupe. Vous l’avez déjà fait lors de la création de la mosaïque 1. Vous n’avez donc pas à le refaire.
    
4. Légende de la mosaïque :  
    
   ```
   Devices with a Hardware Error
   ```

5. Requête de mosaïque
    
   ```
   Type:Event EventLog:"Skype Room System" EventLevelName:Error EventID:3001 TimeGenerated>NOW-10MINUTES|measure count() by SRSDisplayName_CF
   ```

6. Requête de liste :
    
   ```
   Type:Event EventLog:"Skype Room System" EventLevelName:Error EventID:3001 TimeGenerated>NOW-10MINUTES|measure max(TimeGenerated) by SRSDisplayName_CF
   ```

7. Nom des titres de colonne :  
    
   ```
   Display Name
   ```

8. Valeur des titres de colonne :  
    
   ```
   Last Error
   ```

9. Requête de navigation :  
    
   ```
   {selected item}  EventLevelName:Error EventID:3001|Dedup SRSDisplayName_CF|Select TimeGenerated, Computer, SRSOperationName_CF, SRSOperationResult_CF,SRSEventDescription_CF, SRSAppVersion_CF, SRSDisplayName_CF, SRSAlias_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF
   ```

### <a name="list-devices-with-an-app-error"></a>Liste des appareils présentant une erreur d’application  

1. Définissez le cas : 
    
   Cette mosaïque affiche tous les appareils SRS qui signalent la survenue d’une ou de plusieurs erreurs au niveau des composants de l’application au cours des 10 dernières minutes.
    
2. Assigner une mosaïque de groupe  
    
   ```
   SRS v2
   ```

3. Ne cochez pas la nouvelle zone de groupe. Vous l’avez déjà fait lors de la création de la mosaïque 1. Vous n’avez donc pas à le refaire.
    
4. Légende de la mosaïque :  
   ``` 
    Device with App Errors (in prior 10 minutes)
   ``` 
5. Requête de mosaïque :  
    
   ```
   Type:Event EventLog:"Skype Room System" EventLevelName:Error EventID:2001 TimeGenerated>NOW-10MINUTES|measure count() by Computer
   ```

6. Requête de liste :  
    
   ```
   Type:Event EventLog:"Skype Room System" EventLevelName:Error EventID:2001 TimeGenerated>NOW-10MINUTES|measure max(TimeGenerated) by Computer
   ```

7. Nom des titres de colonne :  
    
   ```
   Device Name
   ```

8. Valeur des titres de colonne :  
    
   ```
   Last Error
   ```

9. Requête de navigation :
    
   ```
   {selected item} EventLevelName:Error|Dedup SRSDisplayName_CF|Select TimeGenerated, Computer, SRSOperationName_CF, SRSOperationResult_CF,SRSEventDescription_CF, SRSAppVersion_CF, SRSDisplayName_CF, SRSAlias_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF
   ```

### <a name="list-devices-requiring-a-restart"></a>Liste des appareils nécessitant un redémarrage

1. Définissez le cas : 
    
   Cette mosaïque affiche tous les appareils SRS qui ont été redémarrés au cours des 24 dernières heures et le nombre de redémarrages.
    
2. Assigner une mosaïque de groupe  
    
  ```
  SRS v2
  ```

3. Ne cochez pas la nouvelle zone de groupe. Vous l’avez déjà fait lors de la création de la mosaïque 1. Vous n’avez donc pas à le refaire.
    
4. Légende de la mosaïque :  
    
   ```
   Devices with App restarted (past 24 hours)
   ```

5. Requête de mosaïque :  
    
   ```
   Type:Event EventLog:"Skype Room System" EventID:4000 TimeGenerated>NOW-24HOURS|measure count() by Computer
   ```

6. Requête de liste :  
    
   ```
   Type:Event EventLog:"Skype Room System" EventID:4000 TimeGenerated>NOW-24HOURS|measure count(EventID) by SRSDisplayName_CF
   ```

7. Nom des titres de colonne :  
    
   ```
   Display Name
   ```

8. Valeur des titres de colonne :  
    
   ```
   Number of restarts
   ```

9. Requête de navigation :  
    
   ```
   {selected item} EventID:4000 TimeGenerated >NOW-24HOURS|Select TimeGenerated, Computer, SRSOperationName_CF, SRSOperationResult_CF,SRSEventDescription_CF, SRSAppVersion_CF, SRSDisplayName_CF, SRSAlias_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF
   ```

La création de vues est terminée. Les alertes disponibles sont toutes reflétées dans une ou plusieurs de ces mosaïques.
## <a name="see-also"></a>Voir aussi
<a name="Views"> </a>

#### 

[Planification de la gestion de v2 Skype salle systèmes avec OMS](../../plan-your-deployment/clients-and-devices/oms-management.md)
  
[Gérer les périphériques de v2 Skype salle systèmes avec OMS](../../manage/skype-room-systems-v2/oms.md)

