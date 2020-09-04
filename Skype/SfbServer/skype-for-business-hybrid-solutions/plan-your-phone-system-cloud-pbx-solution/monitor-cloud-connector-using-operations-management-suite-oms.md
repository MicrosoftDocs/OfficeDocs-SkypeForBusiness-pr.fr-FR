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
description: Consultez cette rubrique pour découvrir comment surveiller votre déploiement de Cloud Connector version 2,1 et versions ultérieures à l’aide de Microsoft Operations Management Suite (OMS).
ms.openlocfilehash: eca2f56bf564e376717a42bd8d297710905f8dc6
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359090"
---
# <a name="monitor-cloud-connector-using-operations-management-suite-oms"></a>Surveiller Cloud Connector avec Operations Management Suite (OMS)

> [!Important]
> La version Cloud Connector sera déconnectée le 31 juillet 2021 avec Skype entreprise online. Une fois que votre organisation a effectué la mise à niveau vers Teams, Découvrez comment connecter votre réseau téléphonique local à teams à l’aide du [routage direct](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).

Consultez cette rubrique pour découvrir comment surveiller votre déploiement de Cloud Connector version 2,1 et versions ultérieures à l’aide de Microsoft Operations Management Suite (OMS).

Vous pouvez maintenant surveiller votre déploiement de Cloud Connector version 2,1 et versions ultérieures à l’aide d’Operations Management Suite (OMS), une solution de gestion informatique en nuage Microsoft. L’analyse des journaux OMS vous permet de surveiller et d’analyser la disponibilité et les performances des ressources, y compris les machines physiques et virtuelles. Pour plus d’informations sur OMS et sur l’analyse des journaux, voir [qu’est-ce que Operations Management Suite (OMS) ?](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview)

Cette rubrique comprend les sections suivantes :

- Conditions préalables

- Configurer Cloud Connector pour utiliser OMS

- Configurer OMS

- Analyser les alertes dans votre référentiel d’analyse des journaux

- Ensemble de surveillance recommandé

## <a name="prerequisites"></a>Conditions préalables

Avant de pouvoir utiliser OMS pour surveiller votre déploiement de Cloud Connector, vous aurez besoin des éléments suivants :

- **Un compte Azure et un espace de travail OMS.** Si vous n’avez pas encore de compte Azure, vous devez en créer un pour utiliser l’analyse de journal OMS. Pour plus d’informations sur la création d’un compte Azure et la configuration d’un espace de travail OMS, voir [Get Started with a log Analytics Workspace](https://docs.microsoft.com/azure/log-analytics/log-analytics-get-started).

- **Cloud Connector version 2,1 ou ultérieure**

- **Log Analytics New log Search** est nécessaire pour la surveillance de Cloud Connector. Pour plus d’informations, consultez [la rubrique mettre à niveau votre espace de travail d’analyse Azure log Analytics vers une nouvelle recherche de journal](https://docs.microsoft.com/azure/log-analytics/log-analytics-log-search-upgrade).

## <a name="configure-cloud-connector-to-use-oms"></a>Configurer Cloud Connector pour utiliser OMS

Vous devez configurer votre environnement Cloud Connector sur site pour qu’il utilise OMS. Pour ce faire, vous aurez besoin de votre ID d’espace de travail OMS et de votre clé, que vous pouvez trouver à l’aide du portail OMS comme suit : Settings-- \> sources connectées-- \> serveurs Windows :

![Capture d’écran pour le Cloud Connector OMS](../../media/a4bb0a96-c940-435e-a3f5-5ef3062dea83.png)

La configuration de Cloud Connector pour l’utilisation d’OMS dépend de votre scénario :

- **Si vous installez une nouvelle appliance Cloud Connector ou si vous souhaitez redéployer une appliance**, procédez comme suit avant d’exécuter Install-applet ccappliance :

    1. Dans la section fichier de CloudConnector.ini [Common], définissez le paramètre OMSEnabled sur true.

        Chaque fois que Cloud Connector est déployé ou mis à niveau, il essaiera d’installer l’agent OMS automatiquement sur les machines virtuelles. Activez cette fonctionnalité afin que l’agent OMS puisse survivre à la mise à jour automatique de Cloud Connector.

    2. Pour configurer l’ID et la clé OMS, exécutez Set-applet cccredential-AccountType OMSWorkspace. 

- **Si vous installez un agent OMS sur une appliance Cloud Connector existante**, procédez comme suit :

    1. Dans la section fichier de CloudConnector.ini [Common], définissez OMSEnabled = true. 

    2. Exécutez Import-CcConfiguration. 

    3. Exécutez Install-CcOMSAgent. 

        > [!NOTE]
        > Si les informations d’identification OMSWorkspace n’ont jamais été définies, vous êtes invité à entrer les informations d’identification lorsque vous exécutez Install-CcOMSAgent. 

- **Si vous souhaitez mettre à jour l’ID ou la clé d’espace de travail OMS dans une appliance Cloud Connector qui a déjà installé un agent OMS :**

    1. Pour configurer l’ID et la clé OMS, exécutez Set-applet cccredential-AccountType OMSWorkspace. 

    2. Pour appliquer les mises à jour, exécutez Install-CcOMSAgent. 

- **Pour tous les scénarios, vérifiez que les agents sont connectés comme suit :**

    Dans le portail OMS, accédez à paramètres- \> sources connectées- \> serveurs Windows. La liste des ordinateurs connectés s’affiche. 

## <a name="configure-oms"></a>Configurer OMS

Ensuite, vous devrez spécifier votre configuration OMS à l’aide du portail OMS. Plus précisément, vous devez :

- Spécifiez des informations sur les journaux des événements et les compteurs de performance.

- Créer des alertes 

### <a name="specify-information-about-event-logs-and-performance-counters"></a>Spécifier des informations sur les journaux des événements et les compteurs de performance

Dans le portail OMS, vous devez spécifier des informations sur les journaux d’événements et les compteurs de performance comme suit :

1. Accédez à paramètres- \> données-données- \> journaux des événements Windows et ajoutez des journaux d’événements pour : 

   - Lync Server

   - Application

     > [!NOTE]
     > Vous devez entrer manuellement Lync Server dans la zone de texte. Elle n’apparaît pas sous la forme d’une option dans la liste déroulante. 

     Pour plus d’informations, consultez la rubrique [sources de données du journal des événements Windows dans analyse des journaux](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-windows-events)

2. Accédez à paramètres- \> données-données- \> compteurs de performances Windows et ajoutez des compteurs de performance pour : 

   - **Compteurs de niveau de système d’exploitation**. Vous pouvez ajouter des compteurs au niveau du système d’exploitation, tels que l’utilisation du processeur, l’utilisation de la mémoire, l’utilisation du réseau, ou vous pouvez utiliser des solutions existantes comme la capacité et les performances, l’analyseur de performances réseau sans ajouter de compteurs de manière explicite. Quelle que soit la façon dont vous décidez de les surveiller, Microsoft vous recommande de surveiller ces compteurs de système d’exploitation.

   - **Compteurs Skype entreprise**. Il existe de nombreux compteurs fournis par Skype entreprise. Vous pouvez trouver ces compteurs en vous connectant à un serveur de médiation et en ouvrant l’analyseur de performances. Ces compteurs commencent par « LS : ». Microsoft vous recommande de commencer avec les compteurs de capacité suivants au minimum et d’ajouter d’autres personnes intéressantes :

     Nombre total d’appels actifs :

       - LS : MediationServer-appels entrants (_Total) \- en cours 

       - LS : MediationServer-appels sortants (_Total) \- en cours 

     Nombre total d’appels de déviation du trafic multimédia actif :

       - LS : MediationServer-appels entrants (_Total) appels de déviation du trafic \- multimédia actifs 

       - LS : MediationServer-appels sortants (_Total) \- appels de contournement de média actifs 

     > [!NOTE]
     > Vous devez entrer manuellement les compteurs de performance dans la zone de texte. Elles n’apparaissent pas sous forme d’options dans la liste déroulante. 

     Pour plus d’informations, consultez la rubrique [sources de données de performances Windows et Linux dans analyse des journaux](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-performance-counters)

### <a name="create-alerts"></a>Créer des alertes

Il existe deux types d’alertes dans OMS : nombre d’alertes de résultats et alertes de mesure métrique. Pour plus d’informations sur la création d’alertes, voir [Working with Alert Rules in log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-alerts-creating).

Vous devez tenir compte des éléments suivants lors de la création d’alertes :

- Assurez-vous que l’alerte est une alerte de nombre de résultats, qui est la sélection par défaut. 

- Les requêtes de démonstration exigent que le paramètre « nombre de résultats » soit défini sur « supérieur à 0 ». 

- Il est recommandé de définir la fréquence des alertes et de la fenêtre de temps sur 5 minutes. 

- Il est recommandé de ne pas activer la suppression des alertes pour les alertes de démonstration. 

- Pour les scénarios d’alerte classiques, Microsoft recommande de créer une paire d’alertes : une alerte d’erreur et une alerte de réinitialisation. Pour l’alerte d’erreur, sélectionnez niveau de gravité critique ; pour l’alerte réinitialiser, sélectionnez niveau de gravité information.

Les sections suivantes décrivent comment créer des alertes exemples.

 **Créer une paire d’alertes : « RTCMEDSRV ne s’exécute pas dans les serveurs de médiation » et « RTCMEDSRV revient en cours d’exécution dans les serveurs de médiation »**

Pour créer cette paire d’alertes :

- La requête de l’alerte d’erreur est la suivante :

  ```Kusto
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003)  | summarize arg_max(TimeGenerated, EventID) by Computer | where EventID == 25003
  ```

    La requête utilise le filtre de l’ordinateur  *où l’ordinateur contient « MediationServer »*  . Le filtre sélectionne uniquement l’ordinateur dont le nom contient la chaîne « MediationServer ».

     Vous devez remplacer le filtre par votre propre filtre d’ordinateur ou simplement le supprimer. Vous pouvez créer des filtres de chaîne complexes sans expressions régulières. Pour plus d’informations, consultez la rubrique [opérateurs de chaîne](https://docs.loganalytics.io/docs/Language-Reference/Scalar-operators/String-operators). Vous pouvez également choisir d’utiliser des expressions régulières. Par ailleurs, vous pouvez créer un groupe d’ordinateurs en enregistrant une requête de recherche et en utilisant ce groupe comme filtre de votre ordinateur dans votre requête d’alerte. Pour plus d’informations, consultez la rubrique [groupes d’ordinateurs dans les recherches du journal d’analyse des journaux](https://docs.microsoft.com/azure/log-analytics/log-analytics-computer-groups).

    Pour chaque ordinateur, la requête d’erreur obtiendra le dernier journal des événements pour le démarrage du service RTCMEDSRV et l’arrêt du service. Elle renverra un journal si le dernier événement est l’événement d’arrêt de service ; elle renvoie la valeur Nothing si le dernier événement est l’événement de démarrage du service. En bref, la requête renvoie une liste des serveurs dont la RTCMEDSRV est arrêtée dans la fenêtre de temps. 

- La requête pour l’alerte de réinitialisation est la suivante :

  ```Kusto
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003) | summarize arg_max(TimeGenerated, EventID) by Computer  | where EventID == 2500
  ```

    La requête de réinitialisation effectue exactement l’autre chose de la requête d’erreur. Pour chaque ordinateur, il renvoie un si le dernier événement est l’événement de démarrage du service ; elle renvoie la valeur Nothing si le dernier événement est l’événement d’arrêt de service.

**Créer une paire d’alertes : « trop d’appels simultanés dans les serveurs de médiation » et « appels simultanés vers une charge normale »**

Pour créer cette alerte :

- La requête de l’alerte d’erreur est la suivante :

  ```Kusto
  Perf | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName == "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls >= 500
  ```

    Pour chaque ordinateur, la requête obtiendra les derniers compteurs pour les appels entrants et sortants et totalisez ces deux valeurs. Elle renverra un journal si la valeur de la somme dépasse 500 ; elle renvoie la valeur Nothing si ce n’est pas le cas. En bref, la requête renvoie une liste des serveurs dont les appels simultanés sont trop nombreux dans la fenêtre de temps.

- La requête pour l’alerte de réinitialisation est la suivante :

  ```Kusto
  Perf  | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName ==  "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls < 500
  ```

    La requête de réinitialisation effectue exactement l’autre chose de la requête d’erreur. Pour chaque ordinateur, la requête obtiendra les derniers compteurs pour les appels entrants et sortants et totalisez ces deux valeurs. Elle renverra un journal si la valeur de la somme est inférieure à 500 ; il ne renvoie rien sinon.

**Créer une alerte : alerte utilisation de l’UC \> 90 ou RTCMEDIARELAY arrêtée dans les serveurs**

Pour créer cette alerte, la requête est la suivante :

```Kusto
search *| where Computer contains "MediationServer" | where (Type == "Perf" or Type == "Event") | where ((ObjectName ==  "Processor" and CounterName == "% Processor Time") or EventLog == "Lync Server") | where (CounterValue > 90 or EventID == 22003)
```

La requête obtiendra tous les compteurs d’utilisation du processeur et l’événement d’arrêt de service à partir de tous les ordinateurs et renverra un journal si l’utilisation du processeur dépasse 90% ou que le service est toujours arrêté. 

## <a name="analyze-the-alerts-in-your-log-analytics-repository"></a>Analyser les alertes dans votre référentiel d’analyse des journaux

Pour analyser les alertes dans votre référentiel, utilisez la solution de gestion des alertes. Pour plus d’informations, consultez la rubrique [Alert Management solution in Operations Management Suite (OMS)](https://docs.microsoft.com/azure/log-analytics/log-analytics-solution-alert-management) .

## <a name="recommended-minimal-monitoring-set"></a>Ensemble de surveillance minimal recommandé

Pour identifier les problèmes liés aux journaux des événements et aux compteurs de performance : 

- **Journaux des événements.** Pour tout problème, il doit y avoir une paire Events, avec un ensemble d’événements pour indiquer un élément incorrect, tandis que l’autre indique que tout est bien. Pour une période donnée, c’est le dernier événement enregistré qui indique si un point est amiss pendant cette période.

- **Compteurs de performance.** Il doit y avoir un seuil pour les compteurs surveillés.

Le tableau suivant répertorie les services que Microsoft recommande de surveiller en indiquant les ID d’événement stop et Start :

|Nom du service  <br/> |Rôle de serveur cible  <br/> |Arrêter l’ID d’événement  <br/> |ID d’événement de début  <br/> |
|:-----|:-----|:-----|:-----|
|RTCMEDSRV  <br/> |Serveur de médiation  <br/> |25003  <br/> |25002  <br/> |
|RTCSRV  <br/> |Serveur Edge  <br/> |12289  <br/> |12288  <br/> |
|RTCMRAUTH  <br/> |Serveur Edge  <br/> |19003  <br/> |19002  <br/> |
|RTCMEDIARELAY  <br/> |Serveur Edge  <br/> |22003  <br/> |22002  <br/> |

Le tableau suivant répertorie les problèmes réseau que Microsoft recommande de surveiller :


| Nom du moniteur  <br/>                                        | Rôle de serveur cible  <br/> | Expression d’ID d’événement de réussite  <br/> | Expression d’ID d’événement d’erreur  <br/> | Exemple d’échec  <br/> |
|:-----------------------------------------------------------|:--------------------------|:-----------------------------------|:---------------------------------|:-----------------------|
| Échec de la connectivité du serveur de médiation à la passerelle  <br/>    | Serveur de médiation  <br/>   | 25062                              |                                  | 25002  <br/>           |
| Échec de la fin de l’appel de passerelle de serveur de médiation  <br/> | Serveur de médiation  <br/>   | 25064                              |                                  | 25002  <br/>           |
| Problèmes réseau critiques  <br/>                           | Serveur Edge  <br/>        | 14353                              |                                  | 12288  <br/>           |

La liste suivante répertorie les compteurs de capacité d’appel qui doivent être surveillés. Ces chiffres doivent être inférieurs à 500 pour Cloud Connector Standard Edition ; inférieur à 50 pour la version minimale de Cloud Connector.

- LS : MediationServer-appels entrants (_Total) \- en cours 

- LS : MediationServer-appels sortants (_Total) \- en cours 

- LS : MediationServer-appels entrants (_Total) appels de déviation du trafic \- multimédia actifs

- LS : MediationServer-appels sortants (_Total) \- appels de contournement de média actifs

## <a name="see-also"></a>Voir aussi

Pour plus d’informations sur l’utilisation d’OMS, consultez les rubriques suivantes :

- [Rechercher des données à l’aide de recherches de journal dans l’analyse de journal](https://docs.microsoft.com/azure/log-analytics/log-analytics-log-searches)

- [Référence du langage d’analyse de journalisation Azure](https://docs.loganalytics.io/docs/Language-Reference)

- [Présentation des alertes dans les analyses de journal](https://docs.microsoft.com/azure/log-analytics/log-analytics-alerts)

- [Connecter des ordinateurs Windows au service Journal Analytics dans Azure](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents)


