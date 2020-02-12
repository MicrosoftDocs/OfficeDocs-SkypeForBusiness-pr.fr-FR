---
title: Surveiller Cloud Connector avec Operations Management Suite (OMS)
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: edf4a04c-d4c9-4c05-aacc-9e084618bb55
description: Pour plus d’informations sur la façon de surveiller la version 2,1 du Cloud Connector et le déploiement ultérieur à l’aide de Microsoft Operations Management Suite (OMS), consultez cette rubrique.
ms.openlocfilehash: 6c63baf078dc865a4e3aef574cff30bedabf3819
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888633"
---
# <a name="monitor-cloud-connector-using-operations-management-suite-oms"></a>Surveiller Cloud Connector avec Operations Management Suite (OMS)

Pour plus d’informations sur la façon de surveiller la version 2,1 du Cloud Connector et le déploiement ultérieur à l’aide de Microsoft Operations Management Suite (OMS), consultez cette rubrique.

Vous pouvez désormais surveiller la version 2,1 du Cloud Connector et le déploiement ultérieur à l’aide de Operations Management Suite (OMS), une solution de gestion informatique du Cloud Microsoft. L’analyse du journal OMS vous permet de surveiller et d’analyser la disponibilité et les performances des ressources, notamment les machines physiques et virtuelles. Pour plus d’informations sur OMS et sur l’analyse du journal, voir [qu’est-ce que la suite de gestion des opérations ?](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview)

Cette rubrique contient les sections suivantes :

- Conditions requises

- Configurer le Cloud Connector pour utiliser OMS

- Configurer OMS

- Analyser les alertes dans votre référentiel d’analyse du journal

- Ensemble de contrôles recommandés

## <a name="prerequisites"></a>Conditions requises

Pour que vous puissiez utiliser OMS pour surveiller le déploiement de votre Cloud Connector, vous devez disposer des éléments suivants :

- **Un compte Azure et un espace de travail OMS.** Si vous n’avez pas encore de compte Azure, vous devez en créer un pour utiliser l’analyse du journal OMS. Pour plus d’informations sur la création d’un compte Azure et la configuration d’un espace de travail OMS, voir [commencer à utiliser un espace de travail d’analyse du journal](https://docs.microsoft.com/azure/log-analytics/log-analytics-get-started).

- **Cloud Connector version 2,1 ou ultérieure**

- Le **nouveau journal de recherche du journal d’analyse** est requis pour la surveillance du connecteur Cloud. Pour plus d’informations, reportez-vous à [mettre à niveau votre espace de travail analyse du journal Azure vers une nouvelle recherche de journaux](https://docs.microsoft.com/azure/log-analytics/log-analytics-log-search-upgrade).

## <a name="configure-cloud-connector-to-use-oms"></a>Configurer le Cloud Connector pour utiliser OMS

Vous devez configurer votre environnement sur site Cloud Connector pour qu’il utilise OMS. Pour ce faire, vous avez besoin de votre ID d’espace de travail OMS et de votre clé, que vous pouvez trouver en utilisant le portail OMS\>comme suit : Settings--sources connectées-serveurs\> Windows :

![Capture d'écran pour Cloud Connector OMS](../../media/a4bb0a96-c940-435e-a3f5-5ef3062dea83.png)

La configuration de Cloud Connector pour utiliser OMS dépend de votre scénario :

- **Si vous installez un nouveau matériel de connecteur Cloud ou que vous voulez redéployer un appareil**, procédez comme suit avant d’exécuter l’installation-CcAppliance :

    1. Dans la section [Common] du fichier CloudConnector. ini, définissez le paramètre OMSEnabled sur true.

        Chaque fois que le Cloud Connector est déployé ou mis à niveau, il essaiera d’installer automatiquement l’agent OMS sur les ordinateurs virtuels. Activez cette fonctionnalité pour que l’agent OMS puisse survivre à la mise à jour automatique du Cloud Cloud.

    2. Pour configurer l’ID et la clé OMS, exécutez Set-CcCredential-AccountType OMSWorkspace. 

- **Si vous installez un agent OMS sur un appareil de connecteur Cloud existant**, procédez comme suit :

    1. Dans la section [Common] du fichier CloudConnector. ini, définissez OMSEnabled = true. 

    2. Exécutez Import-CcConfiguration. 

    3. Exécutez Install-CcOMSAgent. 

        > [!NOTE]
        > Si les informations d’identification OMSWorkspace n’ont jamais été définies, vous êtes invité à entrer les informations d’identification lorsque vous exécutez Install-CcOMSAgent. 

- **Si vous voulez mettre à jour l’ID d’espace de travail OMS ou la clé dans un appareil Cloud sur lequel est déjà installé un agent OMS :**

    1. Pour configurer l’ID et la clé OMS, exécutez Set-CcCredential-AccountType OMSWorkspace. 

    2. Pour appliquer les mises à jour, exécutez Install-CcOMSAgent. 

- **Dans tous les cas, vérifiez que les agents sont connectés comme suit :**

    Dans le portail OMS, accédez à paramètres-\> sources connectées\> -serveurs Windows. Une liste des ordinateurs connectés s’affiche. 

## <a name="configure-oms"></a>Configurer OMS

Vous devrez ensuite spécifier votre configuration OMS à l’aide du portail OMS. En particulier, vous devez effectuer les opérations suivantes :

- Spécifiez les informations relatives aux journaux des événements et aux compteurs de performance.

- Créer des alertes. 

### <a name="specify-information-about-event-logs-and-performance-counters"></a>Spécifier des informations sur les journaux d’événements et les compteurs de performance

Dans le portail OMS, vous devez spécifier les informations relatives aux journaux d’événements et aux compteurs de performance comme suit :

1. Accédez à paramètres-\>données-\>journaux des événements Windows et ajoutez les journaux des événements pour : 

   - Lync Server

   - Application

     > [!NOTE]
     > Vous devez entrer manuellement Lync Server dans la zone de texte. Il n’apparaît pas sous la forme d’une option dans la liste déroulante. 

     Pour plus d’informations, voir [sources de données du journal des événements Windows dans analyse du journal](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-windows-events)

2. Accédez à paramètres-\>données-\> compteurs de performance Windows et ajouter des compteurs de performance pour : 

   - **Compteurs de niveau de système d’exploitation**. Vous pouvez ajouter des compteurs de niveau de système d’exploitation, par exemple une utilisation du processeur, de la mémoire, une utilisation du réseau, ou vous pouvez utiliser des solutions existantes comme la capacité et les performances, le moniteur des performances du réseau sans ajouter de compteurs explicitement. Quelle que soit la façon dont vous décidez de les surveiller, Microsoft vous recommande de surveiller ces compteurs du système d’exploitation.

   - **Des compteurs Skype entreprise**. Il existe de nombreux compteurs proposés par Skype entreprise. Vous pouvez trouver ces compteurs en vous connectant à un serveur de médiation et en ouvrant le moniteur de performance. Ces compteurs commencent par « LS : ». Microsoft vous recommande de commencer avec les compteurs de capacité suivants au minimum et d’ajouter d’autres personnes qui vous intéressent :

     Nombre total d’appels actifs :

       - LS : MediationServer-appels entrants (_Total)\- actuels 

       - LS : MediationServer-les appels sortants (_Total\- ) actuels 

     Nombre total d’appels multimédias actifs :

       - LS : appels entrants et MediationServer (_Total)\- 

       - LS : MediationServer-appels sortants (_Total)\- appels multimédias actifs 

     > [!NOTE]
     > Vous devez entrer manuellement les compteurs de performance dans la zone de texte. Elles n’apparaissent pas sous la forme d’options dans la liste déroulante. 

     Pour plus d’informations, voir [sources de données de performances Windows et Linux dans l’analyse du journal](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-performance-counters)

### <a name="create-alerts"></a>Créer des alertes

Il existe deux types d’alertes dans OMS : le nombre d’alertes de résultats et d’alertes de mesure métrique. Pour plus d’informations sur la création d’alertes, voir [utilisation des règles d’alerte dans l’analyse du journal](https://docs.microsoft.com/azure/log-analytics/log-analytics-alerts-creating).

Lorsque vous créez des alertes, vous devez tenir compte des éléments suivants :

- Assurez-vous que l’alerte est une alerte de type nombre de résultats (sélection par défaut). 

- Les requêtes de démonstration requièrent que « nombre de résultats » soit défini sur « supérieur à 0 ». 

- Nous vous conseillons de définir la fenêtre temps et la fréquence d’alerte sur 5 minutes. 

- Nous vous recommandons de ne pas activer « supprimer les alertes » pour les alertes de démonstration. 

- Pour des scénarios d’alerte standard, Microsoft recommande la création d’une paire d’alertes : une alerte d’erreur et une alerte de réinitialisation unique. Pour l’alerte d’erreur, sélectionnez niveau de gravité critique ; pour l’alerte de réinitialisation, sélectionnez information sur le niveau de gravité.

Les sections suivantes décrivent comment créer des exemples d’alertes.

 **Créer une paire d’alertes : « RTCMEDSRV ne s’exécute pas sur les serveurs de médiation » et « RTCMEDSRV fonctionne de nouveau sur les serveurs de médiation »**

Pour créer cette paire d’alertes :

- La requête d’erreur est la suivante :

  ```Kusto
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003)  | summarize arg_max(TimeGenerated, EventID) by Computer | where EventID == 25003
  ```

    La requête utilise le filtre d’ordinateur sur *lequel ordinateur contient « MediationServer »* . Le filtre sélectionne uniquement l’ordinateur dont le nom contient la chaîne « MediationServer ».

     Vous devez remplacer le filtre par votre propre filtre d’ordinateur ou simplement le supprimer. Vous pouvez créer des filtres de chaîne complexes sans expression régulière. Pour plus d’informations, consultez la section [opérateurs de chaîne](https://docs.loganalytics.io/docs/Language-Reference/Scalar-operators/String-operators). Vous pouvez également choisir d’utiliser des expressions régulières. Par ailleurs, vous pouvez créer un groupe d’ordinateurs en enregistrant une requête de recherche et en utilisant ce groupe comme filtre d’ordinateur dans votre requête d’alerte. Pour plus d’informations, voir [groupes d’ordinateurs dans les recherches dans le journal d’analyse du journal](https://docs.microsoft.com/azure/log-analytics/log-analytics-computer-groups).

    Pour chaque ordinateur, la requête d’erreur reçoit le dernier journal des événements pour le démarrage et le service du service RTCMEDSRV. Il renverra un journal si le dernier événement est l’événement d’arrêt du service ; elle ne renvoie aucune valeur si le dernier événement est l’événement de début de service. En résumé, la requête renvoie une liste de serveurs pour lesquels RTCMEDSRV est arrêté dans la fenêtre délai. 

- La requête de réinitialisation est la suivante :

  ```Kusto
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003) | summarize arg_max(TimeGenerated, EventID) by Computer  | where EventID == 2500
  ```

    La requête Reset effectue exactement l’opération inverse de la requête d’erreur. S’il s’agit d’un ordinateur, l’événement de début de service sera renvoyé. elle ne renvoie aucune valeur si le dernier événement est l’événement d’arrêt de service.

**Créer une paire d’alertes : « un trop grand nombre d’appels simultanés dans les serveurs de médiation » et « les appels simultanés sont ramenés au chargement normal »**

Pour créer cette alerte :

- La requête d’erreur est la suivante :

  ```Kusto
  Perf | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName == "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls >= 500
  ```

    Pour chaque ordinateur, la requête obtiendra les derniers compteurs pour les appels entrants et sortants et additionner ces deux valeurs. Il renverra un journal si la valeur de somme dépasse 500 ; Si ce n’est pas le cas, elle renvoie la valeur Nothing. En résumé, la requête renvoie une liste de serveurs dont les appels simultanés sont trop nombreux dans la fenêtre délai.

- La requête de réinitialisation est la suivante :

  ```Kusto
  Perf  | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName ==  "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls < 500
  ```

    La requête Reset effectue exactement l’opération inverse de la requête d’erreur. Pour chaque ordinateur, la requête obtiendra les derniers compteurs pour les appels entrants et sortants et additionner ces deux valeurs. Il renverra un journal si la valeur somme est inférieure à 500 ; elle ne renvoie aucun résultat.

**Créer une alerte : « utilisation \> processeur 90 ou RTCMEDIARELAY arrêtées dans les serveurs »**

Pour créer cette alerte, la requête est la suivante :

```Kusto
search *| where Computer contains "MediationServer" | where (Type == "Perf" or Type == "Event") | where ((ObjectName ==  "Processor" and CounterName == "% Processor Time") or EventLog == "Lync Server") | where (CounterValue > 90 or EventID == 22003)
```

La requête obtiendra tous les compteurs d’utilisation du processeur et un événement d’arrêt de service de tous les ordinateurs et renverra un journal si l’utilisation du processeur dépasse 90% ou si le service est arrêté. 

## <a name="analyze-the-alerts-in-your-log-analytics-repository"></a>Analyser les alertes dans votre référentiel d’analyse du journal

Pour analyser les alertes dans votre référentiel, utilisez la solution de gestion des alertes. Pour plus d’informations, reportez-vous [à solution de gestion des alertes dans Operations Management Suite (OMS)](https://docs.microsoft.com/azure/log-analytics/log-analytics-solution-alert-management)

## <a name="recommended-minimal-monitoring-set"></a>Ensemble de contrôles minimaux recommandés

Pour identifier les problèmes liés aux journaux d’événements et aux compteurs de performance : 

- **Journaux des événements.** En cas de problème, il devrait y avoir une paire d’événements, avec un ensemble d’événements indiquant qu’un problème survient, tandis que l’autre indique que tout est bien. Pour une période donnée, il s’agit du dernier événement enregistré qui indique s’il s’agit d’amiss pour cette période.

- **Compteurs de performance.** Le seuil doit être défini pour les compteurs surveillés.

Le tableau suivant répertorie les services que Microsoft recommande de surveiller en répertoriant les ID d’événement stop et Start :

|Nom du service  <br/> |Rôle du serveur cible  <br/> |Arrêter l’ID d’événement  <br/> |ID d’événement de début  <br/> |
|:-----|:-----|:-----|:-----|
|RTCMEDSRV  <br/> |serveur de médiation  <br/> |25003  <br/> |25002  <br/> |
|RTCSRV  <br/> |serveur Edge  <br/> |12289  <br/> |12288  <br/> |
|RTCMRAUTH  <br/> |serveur Edge  <br/> |19003  <br/> |19002  <br/> |
|RTCMEDIARELAY  <br/> |serveur Edge  <br/> |22003  <br/> |22002  <br/> |

Le tableau suivant répertorie les problèmes de réseau que Microsoft recommande de surveiller :


| Nom du moniteur  <br/>                                        | Rôle du serveur cible  <br/> | Expression d’ID d’événement Success  <br/> | Expression d’ID d’événement d’erreur  <br/> | Exemple d’échec  <br/> |
|:-----------------------------------------------------------|:--------------------------|:-----------------------------------|:---------------------------------|:-----------------------|
| Échec de la connectivité du serveur de médiation  <br/>    | serveur de médiation  <br/>   | 25062                              |                                  | 25002  <br/>           |
| Serveur de médiation-échec de la fin de l’appel de la passerelle  <br/> | serveur de médiation  <br/>   | 25064                              |                                  | 25002  <br/>           |
| Problèmes réseau critiques  <br/>                           | serveur Edge  <br/>        | 14353                              |                                  | 12288  <br/>           |

La liste suivante répertorie les compteurs de capacités d’appel qui doivent être analysés. Ces nombres doivent avoir moins de 500 pour le Cloud Connector Standard Edition ; inférieur à 50 pour le Cloud Connector édition minimum.

- LS : MediationServer-appels entrants (_Total)\- actuels 

- LS : MediationServer-les appels sortants (_Total\- ) actuels 

- LS : appels entrants et MediationServer (_Total)\-

- LS : MediationServer-appels sortants (_Total)\- appels multimédias actifs

## <a name="see-also"></a>Voir aussi

Pour plus d’informations sur l’utilisation d’OMS, voir les rubriques suivantes :

- [Rechercher des données à l’aide de recherches de journaux dans l’analyse du journal](https://docs.microsoft.com/azure/log-analytics/log-analytics-log-searches)

- [Informations de référence sur le langage d’analyse du journal Azure](https://docs.loganalytics.io/docs/Language-Reference)

- [Présentation des alertes dans l’analyse du journal](https://docs.microsoft.com/azure/log-analytics/log-analytics-alerts)

- [Connecter des ordinateurs Windows au service d’analyse du journal dans Azure](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents)


