---
title: Surveiller le connecteur Cloud à l’aide de la Suite de gestion des opérations (OMS)
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: edf4a04c-d4c9-4c05-aacc-9e084618bb55
description: Lisez cette rubrique pour savoir comment surveiller votre version de connecteur de nuage 2.1 et d’un déploiement ultérieur à l’aide de Microsoft Operations Management Suite (OMS).
ms.openlocfilehash: 8cb454cfcb61bb11e0545ab5ff7dd45d1403ce55
ms.sourcegitcommit: ffca287cf70db2cab14cc1a6cb7cea68317bedd1
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/05/2018
---
# <a name="monitor-cloud-connector-using-operations-management-suite-oms"></a>Surveiller le connecteur Cloud à l’aide de la Suite de gestion des opérations (OMS)
 
Lisez cette rubrique pour savoir comment surveiller votre version de connecteur de nuage 2.1 et d’un déploiement ultérieur à l’aide de Microsoft Operations Management Suite (OMS).
  
Vous pouvez maintenant surveiller votre version de connecteur de nuage 2.1 et d’un déploiement ultérieur en utilisant la Suite de gestion des opérations (OMS), un solution de gestion informatique de Microsoft cloud. OMS journal Analytique vous permet de surveiller et d’analyser la disponibilité et les performances des ressources, y compris physiques et les machines virtuelles. Pour plus d’informations sur l’OMS et Analytique du journal, reportez-vous à la section [Quelle est la Suite de gestion des opérations (OMS) ?](https://docs.microsoft.com/en-us/azure/operations-management-suite/operations-management-suite-overview).
  
Cette rubrique contient les sections suivantes :
  
- Conditions requises
    
- Configuration du connecteur de nuage pour utiliser OMS
    
- Configurer l’OMS
    
- Analyser les alertes dans votre référentiel Analytique du journal
    
- Jeu de surveillance recommandé
    
## <a name="prerequisites"></a>Conditions requises

Avant de pouvoir utiliser OMS de déploiement de Cloud connecteur, vous devez les éléments suivants :
  
- **Un compte Azure et un espace de travail de l’OMS.** Si vous ne disposez pas d’un compte Azure, vous devez en créer un pour utiliser OMS journal Analytique. Pour plus d’informations sur la façon de créer un compte Azure et de configurer un espace de travail de l’OMS, consultez [mise en route de journal Analytique d’un espace de travail](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-get-started).
    
- **Connecteur de nuage version 2.1 ou ultérieure**
    
- **Nouvelle recherche de journal de journal Analytique** est nécessaire pour la surveillance de connecteur de nuage. Pour plus d’informations, consultez [mise à niveau de votre espace de travail Azure journal Analytique à la recherche des journaux de nouveau](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-log-search-upgrade).
    
## <a name="configure-cloud-connector-to-use-oms"></a>Configuration du connecteur de nuage pour utiliser OMS

Vous devez configurer votre environnement local de connecteur de nuage pour utiliser OMS. Pour ce faire, vous aurez besoin de votre ID d’espace de travail OMS et de la clé, que vous pouvez trouver en utilisant le portail OMS comme suit : paramètres--\>Sources connectées--\> serveurs Windows :
  
![Capture d'écran pour Cloud Connector OMS](../../media/a4bb0a96-c940-435e-a3f5-5ef3062dea83.png)
  
La configuration de connecteur de nuage pour utiliser OMS dépend de votre scénario :
  
- **Si vous installez un nouveau matériel de connecteur de nuage ou vous souhaitez redéployer une solution matérielle-logicielle**, procédez comme suit avant d’exécuter Install-CcAppliance :
    
1. Dans le section [Common] du fichier CloudConnector.ini, définissez le paramètre OMSEnabled sur True.
    
    Chaque fois que connecteur de nuage est déployé ou mis à niveau, il va tenter d’installer l’agent OMS automatiquement sur les ordinateurs virtuels. Activez cette fonction afin que l’agent de l’OMS peut survivre à la mise à jour automatique de connecteur de nuage.
    
2. Pour configurer l’ID de l’OMS et la clé, exécutez Set-CcCredential - AccountType OMSWorkspace. 
    
- **Si vous installez un agent de l’OMS sur une appliance de connecteur de nuage existante**, procédez comme suit :
    
1. Dans le fichier CloudConnector.ini de section [Common], définissez OMSEnabled = true. 
    
2. Exécutez CcConfiguration à l’importation. 
    
3. Exécutez CcOMSAgent à l’installation. 
    
    > [!NOTE]
    > Si les informations d’identification de OMSWorkspace n’a jamais été définie, vous êtes invité pour les informations d’identification lorsque vous exécutez l’installation-CcOMSAgent. 
  
- **Si vous souhaitez mettre à jour de l’ID d’espace de travail OMS ou clé dans un appareil de connecteur de nuage qui a déjà installé un agent d’OMS :**
    
1. Pour configurer l’ID de l’OMS et la clé, exécutez Set-CcCredential - AccountType OMSWorkspace. 
    
2. Pour appliquer les mises à jour, exécutez Install-CcOMSAgent. 
    
- **Pour tous les scénarios, vérifiez que les agents sont connectés comme suit :**
    
    Dans le portail de l’OMS, cliquez sur paramètres -\> Sources connectées -\> serveurs de Windows. Vous verrez une liste d’ordinateurs connectés. 
    
## <a name="configure-oms"></a>Configurer l’OMS

Ensuite, vous devez spécifier votre configuration OMS via le portail de l’OMS. Plus précisément, vous devez :
  
- Permet de spécifier des informations sur les journaux des événements et des compteurs de performance.
    
- Créer des alertes. 
    
### <a name="specify-information-about-event-logs-and-performance-counters"></a>Spécifier des informations sur les journaux des événements et des compteurs de performance

Dans le portail de l’OMS, vous devez spécifier des informations sur les journaux des événements et des compteurs de performance comme suit :
  
1. Accédez à paramètres -\>de données -\>les journaux d’événements Windows et ajoutez des journaux d’événements : 
    
  - Lync Server
    
  - Application
    
    > [!NOTE]
    > Vous devez entrer manuellement Lync Server dans la zone de texte. Il n’apparaît pas comme option dans la liste déroulante. 
  
    Pour plus d’informations, consultez [les sources de données de journal des événements Windows dans le journal Analytique](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-data-sources-windows-events)
    
2. Accédez à paramètres -\>de données -\> les compteurs de performances de Windows, et ajoutez des compteurs de performances pour : 
    
  - **Compteurs de niveau système d’exploitation**. Vous pouvez ajouter des compteurs au niveau du système d’exploitation, telles que l’utilisation du processeur, utilisation de la mémoire, l’utilisation du réseau, ou vous pouvez utiliser des solutions existantes telles que la capacité et de performances, sans ajouter explicitement les compteurs de l’Analyseur de performances réseau. Peu importe comment vous décidez de les contrôler, Microsoft recommande que vous surveillez ces compteurs du système d’exploitation.
    
  - **Skype pour les compteurs de l’entreprise**. Il existe de nombreux compteurs fournis par Skype pour les entreprises. Vous trouverez ces compteurs en vous connectant à n’importe quel serveur de médiation et d’ouverture de l’Analyseur de performances. Ces compteurs commencent par « LS : ». Microsoft vous recommande de commencer par les compteurs suivants de capacité au minimum et ajouter d’autres qui sont d’intérêt :
    
    Nombre total d’appels actif :
    
  - LS:MediationServer - entrant Calls(_Total)\- en cours 
    
  - LS:MediationServer - Calls(_Total) sortants\- en cours 
    
    Support active totale de contourner les appels :
    
  - LS:MediationServer - entrant Calls(_Total)\- support Active ignore les appels 
    
  - LS:MediationServer - Calls(_Total) sortants\- media Active ignore les appels 
    
    > [!NOTE]
    > Vous devez entrer manuellement les compteurs de performance dans la zone de texte. Ils n’apparaissent pas en tant qu’options dans la liste déroulante. 
  
    Pour plus d’informations, voir les [sources de données de performance Windows et Linux dans journal Analytique](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-data-sources-performance-counters)
    
### <a name="create-alerts"></a>Créer des alertes

Il existe deux types d’alertes dans OMS : nombre de résultats alertes et mesure métrique. Pour plus d’informations sur la création d’alertes, reportez-vous à la section [utilisation des règles d’alerte dans le journal Analytique](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-alerts-creating).
  
Lors de la création d’alertes, tenez compte des éléments suivants :
  
- Vérifiez que l’alerte est une alerte nombre de résultats, qui est la sélection par défaut. 
    
- Les requêtes de démonstration nécessitent que « Nombre de résultats » est définie à « supérieur à 0 ». 
    
- Il est recommandé de définir la fenêtre de temps et de fréquence de l’alerte à 5 minutes. 
    
- Il est recommandé de ne pas activer « Supprimer des alertes » pour les alertes de démonstration. 
    
- Pour les scénarios d’alerte par défaut, Microsoft recommande la création d’une paire d’alertes : d’une erreur et la réinitialisation d’une alerte. Pour le message d’erreur, sélectionnez le niveau de gravité critique ; l’alerte de réinitialisation, sélectionnez le niveau de gravité information.
    
Les sections suivantes décrivent comment créer des alertes de l’échantillon.
  
 **Créer une paire d’alerte : « RTCMEDSRV ne fonctionne pas dans les serveurs de médiation » et « RTCMEDSRV est en cours d’exécution sur les serveurs de médiation dans »**
  
Pour créer cette paire d’alerte :
  
- La requête pour le message d’erreur est :
    
  ```
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003)
 | summarize arg_max(TimeGenerated, EventID) by Computer | where EventID == 25003
  ```

    La requête utilise le filtre d’ordinateur *où ordinateur contient « MediationServer »* . Le filtre sélectionne uniquement l’ordinateur dont le nom contient la chaîne « MediationServer ».
    
     Vous souhaitez remplacer le filtre par le filtre de votre propre ordinateur ou simplement le supprimer. Vous pouvez créer des filtres de chaîne complexe sans les expressions régulières. Pour plus d’informations, consultez [opérateurs de type chaîne](https://docs.loganalytics.io/docs/Language-Reference/Scalar-operators/String-operators). Vous pouvez également choisir d’utiliser des expressions régulières. En outre, vous pouvez créer un groupe d’ordinateurs en enregistrant une requête de recherche à l’aide de ce groupe comme filtre de votre ordinateur dans votre requête d’alerte. Pour plus d’informations, consultez [groupes d’ordinateurs dans le journal Analytique journal des recherches](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-computer-groups).
    
    Pour chaque ordinateur, l’erreur de la requête obtient le dernier journal des événements pour les deux le démarrage du service RTCMEDSRV et arrêt de service. Il retournera un journal si le dernier événement est l’événement d’arrêt de service ; Il ne renvoie rien si le dernier événement est l’événement de démarrage du service. En bref, la requête renvoie une liste de serveurs dont RTCMEDSRV est arrêté dans la fenêtre de temps. 
    
- La requête de l’alerte de réinitialisation est :
    
  ```
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003)
 | summarize arg_max(TimeGenerated, EventID) by Computer  | where EventID == 2500
  ```

    La requête de réinitialisation ne la chose opposée de la requête de l’erreur. Pour chaque ordinateur, il retournera un si le dernier événement est que le service démarre l’événement ; Il ne renvoie rien si le dernier événement est l’événement d’arrêt de service.
    
 **Créer une paire d’alerte : "trop grand nombre d’appels simultané dans les serveurs de médiation » et « appels simultanés retomber à une charge normale »**
  
Pour créer cette alerte :
  
- La requête pour le message d’erreur est :
    
  ```
  Perf | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName 
== "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize
 TotalCalls = sum(CounterValue) by Computer| where TotalCalls >= 500
  ```

    Pour chaque ordinateur, la requête obtiendra les dernières compteurs pour les appels entrants et les appels sortants et somme des deux valeurs. Il retournera une session si la valeur de la somme est supérieure à 500 ; Il ne renvoie rien si elle n’est pas. En bref, la requête renvoie une liste de serveurs dont les appels simultanés sont trop nombreux dans la fenêtre de temps.
    
- La requête de l’alerte de réinitialisation est :
    
  ```
  Perf  | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName ==
 "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize
 TotalCalls = sum(CounterValue) by Computer| where TotalCalls < 500

  ```

    La requête de réinitialisation ne la chose opposée de la requête de l’erreur. Pour chaque ordinateur, la requête obtiendra les dernières compteurs pour les appels entrants et les appels sortants et somme des deux valeurs. Il retournera un journal si la valeur de la somme est inférieure à 500 ; elle retourne nothing dans le cas contraire.
    
 **Créer une alerte : « utilisation de l’UC \> 90 ou RTCMEDIARELAY s’est arrêté dans les serveurs « alerte**
  
Pour créer cette alerte, la requête est la suivante :
  
```
search *| where Computer contains "MediationServer" | where (Type == "Perf" or Type == "Event") | where ((ObjectName ==
 "Processor" and CounterName == "% Processor Time") or EventLog == "Lync Server") | where (CounterValue > 90 or EventID == 22003)
```

La requête obtiendra tous les compteurs d’utilisation de processeur et événement d’arrêt de service à partir de tous les ordinateurs et retour un journal si l’utilisation du processeur dépasse 90 % ou un service est déjà arrêté. 
  
## <a name="analyze-the-alerts-in-your-log-analytics-repository"></a>Analyser les alertes dans votre référentiel Analytique du journal

Pour analyser les alertes dans votre référentiel, utiliser la solution de gestion des alertes. Pour plus d’informations, consultez la [solution de gestion des alertes dans la Suite Gestion des opérations (OMS)](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-solution-alert-management)
  
## <a name="recommended-minimal-monitoring-set"></a>Ensemble de surveillance minimal recommandé

Pour identifier les problèmes avec les journaux des événements et des compteurs de performance : 
  
- **Journaux des événements.** Pour tout problème, il doit être une paire d’événements, avec un ensemble d’événements pour indiquer que quelque chose est incorrect, tandis que l’autre indique que tout est bien. Pour une période donnée, il est le dernier événement enregistré qui indique si un élément est explosion pour cette période.
    
- **Compteurs de performance.** Il doit exister un seuil pour les compteurs surveillés.
    
Le tableau suivant répertorie les services que Microsoft vous recommande de surveillance en répertoriant les ID d’événement arrêter et démarrer :
  
|Nom du service  <br/> |Rôle du serveur cible  <br/> |Arrêter l’ID d’événement  <br/> |ID de l’événement de début  <br/> |
|:-----|:-----|:-----|:-----|
|RTCMEDSRV  <br/> |Serveur de médiation  <br/> |25003  <br/> |25002  <br/> |
|RTCSRV  <br/> |Serveur Edge  <br/> |12289  <br/> |12288  <br/> |
|RTCMRAUTH  <br/> |Serveur Edge  <br/> |19003  <br/> |19002  <br/> |
|RTCMEDIARELAY  <br/> |Serveur Edge  <br/> |22003  <br/> |22002  <br/> |
   
Le tableau suivant répertorie les problèmes de réseau, Microsoft vous recommande de surveillance :
  
|Nom du moniteur  <br/> |Rôle du serveur cible  <br/> |Expression de l’ID d’événement de réussite  <br/> |Expression de l’ID d’événement d’erreur  <br/> |Exemple de défaillance  <br/> |
|:-----|:-----|:-----|:-----|:-----|
|Serveur de médiation pour Échec de connectivité de passerelle  <br/> |Serveur de médiation  <br/> |25062 || 25002  <br/> |25061  <br/> |Échec de MS PING (option) passerelle  <br/> |
|Serveur de médiation pour passerelle appeler Échec d’achèvement  <br/> |Serveur de médiation  <br/> |25064 || 25002  <br/> |25063  <br/> |Échec de MS, essayez de faire appel à la passerelle  <br/> |
|Problèmes réseau critiques.  <br/> |Serveur Edge  <br/> |14353 || 12288  <br/> |14624  <br/> |Le transport TLS n’a pas pu démarrer sur l’adresse IP locale 192.168.231.14 sur le port 5061  <br/> |
   
Voici les compteurs de capacité d’appel qui doivent être contrôlés. Ces numéros doivent être moins que 500 pour l’édition standard de nuage connecteur ; moins de 50 pour édition minimale de connecteur de nuage.
  
- LS:MediationServer - entrant Calls(_Total)\- en cours 
    
- LS:MediationServer - Calls(_Total) sortants\- en cours 
    
- LS:MediationServer - entrant Calls(_Total)\- support Active ignore les appels
    
- LS:MediationServer - Calls(_Total) sortants\- media Active ignore les appels
    
## <a name="see-also"></a>Voir aussi

Pour plus d’informations sur l’utilisation de l’OMS, consultez les rubriques suivantes :
  
- [Rechercher des données à l’aide de la recherche de journal de journal Analytique](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-log-searches)
    
- [Journal Azure Analytique de référence du langage](https://docs.loganalytics.io/docs/Language-Reference)
    
- [Présentation des alertes dans le journal Analytique](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-alerts)
    
- [Connecter des ordinateurs Windows au service journal Analytique dans Azure](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-windows-agents)
    

