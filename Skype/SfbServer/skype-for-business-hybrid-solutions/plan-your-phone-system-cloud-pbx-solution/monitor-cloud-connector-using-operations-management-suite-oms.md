---
title: Surveiller Cloud Connector à l’aide d’Operations Management Suite (OMS)
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
ms.localizationpriority: medium
ms.assetid: edf4a04c-d4c9-4c05-aacc-9e084618bb55
description: Lisez cette rubrique pour découvrir comment surveiller votre déploiement de Cloud Connector version 2.1 et ultérieure à l’aide de Microsoft Operations Management Suite (OMS).
ms.openlocfilehash: 0589df251fedb8d60ba115920e76b3aa1b327334
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58729023"
---
# <a name="monitor-cloud-connector-using-operations-management-suite-oms"></a>Surveiller Cloud Connector à l’aide d’Operations Management Suite (OMS)

> [!Important]
> Cloud Connector Edition sera retirer le 31 juillet 2021 avec Skype Entreprise Online. Une fois votre organisation mise à niveau vers Teams, découvrez comment connecter votre réseau téléphonique local à Teams l’aide du [routage direct.](/MicrosoftTeams/direct-routing-landing-page)

Lisez cette rubrique pour découvrir comment surveiller votre déploiement de Cloud Connector version 2.1 et ultérieure à l’aide de Microsoft Operations Management Suite (OMS).

Vous pouvez désormais surveiller votre déploiement de Cloud Connector version 2.1 et ultérieure à l’aide d’Operations Management Suite (OMS), une solution de gestion informatique du cloud Microsoft. OMS Log Analytics vous permet de surveiller et d’analyser la disponibilité et les performances des ressources, y compris des ordinateurs physiques et virtuels. Pour plus d’informations sur OMS et Log Analytics, voir [Qu’est-ce que Operations Management Suite (OMS) ?](/azure/operations-management-suite/operations-management-suite-overview)

Cette rubrique comprend les sections suivantes :

- Configuration requise

- Configurer Cloud Connector pour utiliser OMS

- Configurer OMS

- Analyser les alertes dans votre référentiel Log Analytics

- Jeu d’analyse recommandé

## <a name="prerequisites"></a>Configuration requise

Avant de pouvoir utiliser OMS pour surveiller le déploiement de Cloud Connector, vous aurez besoin des informations suivantes :

- **Un compte Azure et un espace de travail OMS.** Si vous n’avez pas encore de compte Azure, vous devez en créer un pour utiliser OMS Log Analytics. Pour plus d’informations sur la création d’un compte Azure et la mise en place d’un espace de travail OMS, voir La mise en route d’un espace de travail [Log Analytics.](/azure/log-analytics/log-analytics-get-started)

- **Cloud Connector version 2.1 ou ultérieure**

- **Log Analytics new log search** is required for Cloud Connector monitoring. Pour plus d’informations, voir Mettre à niveau votre espace de travail [Azure Log Analytics vers une nouvelle recherche de journal.](/azure/log-analytics/log-analytics-log-search-upgrade)

## <a name="configure-cloud-connector-to-use-oms"></a>Configurer Cloud Connector pour utiliser OMS

Vous devez configurer votre environnement local Cloud Connector pour utiliser OMS. Pour ce faire, vous aurez besoin de votre ID d’espace de travail OMS et de votre clé, que vous pouvez trouver à l’aide du portail OMS comme suit : Paramètres -- Sources connectées \> -- \> Windows serveurs :

![Capture d’écran de Cloud Connector OMS.](../../media/a4bb0a96-c940-435e-a3f5-5ef3062dea83.png)

La configuration de Cloud Connector pour utiliser OMS dépend de votre scénario :

- **Si vous installez une** nouvelle appliance Cloud Connector ou que vous souhaitez déployer à nouveau une appliance, suivez les étapes suivantes avant d’exécuter Install-CcAppliance :

    1. Dans la section CloudConnector.ini fichier [Common], définissez le paramètre OMSEnabled sur True.

        Chaque fois que Cloud Connector est déployé ou mis à niveau, il essaie d’installer l’agent OMS automatiquement sur les VM. Activez cette fonctionnalité pour que l’agent OMS puisse résister à la mise à jour automatique de Cloud Connector.

    2. Pour configurer l’ID OMS et la clé, exécutez Set-CcCredential -AccountType OMSWorkspace. 

- **Si vous installez un agent OMS sur** une appliance Cloud Connector existante, suivez les étapes suivantes :

    1. Dans la section CloudConnector.ini fichier [Common], définissez OMSEnabled=true. 

    2. Exécutez Import-CcConfiguration. 

    3. Exécutez Install-CcOMSAgent. 

        > [!NOTE]
        > Si les informations d’identification OMSWorkspace n’ont jamais été définies, vous êtes invité à les obtenir lorsque vous exécutez install-CcOMSAgent. 

- **Si vous souhaitez mettre à jour l’ID ou la clé d’espace de travail OMS dans une appliance Cloud Connector qui a déjà installé un agent OMS :**

    1. Pour configurer l’ID OMS et la clé, exécutez Set-CcCredential -AccountType OMSWorkspace. 

    2. Pour appliquer les mises à jour, exécutez Install-CcOMSAgent. 

- **Pour tous les scénarios, vérifiez que les agents sont connectés comme suit :**

    Dans le portail OMS, go to Paramètres - \> Connected Sources - Windows \> Servers. Vous verrez une liste d’ordinateurs connectés. 

## <a name="configure-oms"></a>Configurer OMS

Ensuite, vous devez spécifier votre configuration OMS à l’aide du portail OMS. Plus précisément, vous devez :

- Spécifiez des informations sur les journaux des événements et les compteurs de performances.

- Créer des alertes 

### <a name="specify-information-about-event-logs-and-performance-counters"></a>Spécifier des informations sur les journaux des événements et les compteurs de performances

Dans le portail OMS, vous devez spécifier des informations sur les journaux des événements et les compteurs de performances comme suit :

1. Go to Paramètres- \> Data- \> Windows Event logs, and add event logs for: 

   - Lync Server

   - Application

     > [!NOTE]
     > Vous devez entrer manuellement Lync Server dans la zone de texte. Elle n’apparaît pas en tant qu’option dans la liste liste. 

     Pour plus d’informations, voir Windows sources de données du journal [des événements dans Log Analytics](/azure/log-analytics/log-analytics-data-sources-windows-events)

2. Go to Paramètres- \> Data- \> Windows Performance Counters, and add performance counters for: 

   - **Compteurs au niveau du système d’exploitation.** Vous pouvez ajouter des compteurs au niveau du système d’exploitation, tels que l’utilisation du processeur, l’utilisation de la mémoire, l’utilisation du réseau, ou vous pouvez utiliser des solutions existantes telles que Capacité et performances, Moniteur de performances réseau sans ajouter explicitement de compteurs. Quelle que soit la façon dont vous décidez de les surveiller, Microsoft vous recommande de surveiller ces compteurs de système d’exploitation.

   - **Skype Entreprise.** Il existe de nombreux compteurs fournis par Skype Entreprise. Vous pouvez trouver ces compteurs en vous connectant à n’importe quel serveur de médiation et en ouvrant l’Observateur de performances. Ces compteurs commencent par « LS: ». Microsoft vous recommande de commencer avec les compteurs de capacité suivants au minimum et d’ajouter d’autres qui vous intéressent :

     Nombre total d’appels actifs :

       - LS:MediationServer - Inbound Calls(_Total) \- Current 

       - LS:MediationServer - Outbound Calls(_Total) \- Current 

     Nombre total d’appels de contournement de média actifs :

       - LS:MediationServer - Appels entrants(_Total) appels de déviation \- du trafic multimédia actifs 

       - LS:MediationServer - Appels sortants(_Total) appels de déviation \- du trafic multimédia actifs 

     > [!NOTE]
     > Vous devez entrer manuellement les compteurs de performance dans la zone de texte. Elles n’apparaissent pas en tant qu’options dans la liste liste. 

     Pour plus d’informations, voir Windows sources de données de [performances Linux dans Log Analytics](/azure/log-analytics/log-analytics-data-sources-performance-counters)

### <a name="create-alerts"></a>Créer des alertes

Il existe deux types d’alertes dans OMS : nombre d’alertes de résultats et alertes de mesure métrique. Pour plus d’informations sur la création d’alertes, voir [Working with alert rules in Log Analytics](/azure/log-analytics/log-analytics-alerts-creating).

Vous devez tenir compte des considérations suivantes lors de la création d’alertes :

- Assurez-vous que l’alerte est une alerte nombre de résultats, qui est la sélection par défaut. 

- Les requêtes de démonstration nécessitent que « Nombre de résultats » soit définie sur « Supérieur à 0 ». 

- Il est recommandé de définir à la fois la fenêtre d’heure et la fréquence d’alerte sur 5 minutes. 

- Il est recommandé de ne pas activer « Supprimer les alertes » pour les alertes de démonstration. 

- Pour les scénarios d’alerte classiques, Microsoft recommande de créer une paire d’alertes : une alerte d’erreur et une alerte de réinitialisation. Pour l’alerte d’erreur, sélectionnez Niveau de gravité Critique ; pour l’alerte de réinitialisation, sélectionnez niveau de gravité Informations.

Les sections suivantes décrivent comment créer des exemples d’alertes.

 **Créez une paire d’alertes : « RTCMEDSRV n’est PAS en cours d’exécution dans les serveurs de médiation » et « RTCMEDSRV est de nouveau en cours d’exécution dans les serveurs de médiation »**

Pour créer cette paire d’alertes :

- La requête de l’alerte d’erreur est la :

  ```Kusto
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003)  | summarize arg_max(TimeGenerated, EventID) by Computer | where EventID == 25003
  ```

    La requête utilise le filtre d’ordinateur  *où l’ordinateur contient « MediationServer*  ». Le filtre sélectionne uniquement l’ordinateur dont le nom contient la chaîne « MediationServer ».

     Vous devez remplacer le filtre par votre propre filtre d’ordinateur ou simplement le supprimer. Vous pouvez créer des filtres de chaîne complexes sans expressions régulières. Pour plus d’informations, voir [Opérateurs de chaîne.](https://docs.loganalytics.io/docs/Language-Reference/Scalar-operators/String-operators) Vous pouvez également choisir d’utiliser des expressions régulières. En outre, vous pouvez créer un groupe d’ordinateurs en enregistrer une requête de recherche et en utilisant ce groupe comme filtre d’ordinateur dans votre requête d’alerte. Pour plus d’informations, voir [Groupes d’ordinateurs dans les](/azure/log-analytics/log-analytics-computer-groups)recherches du journal Log Analytics.

    Pour chaque ordinateur, la requête d’erreur reçoit le dernier journal des événements pour le démarrage et l’arrêt du service RTCMEDSRV. Elle retourne un journal si le dernier événement est l’événement d’arrêt de service ; Elle ne retourne rien si le dernier événement est l’événement de démarrage du service. En bref, la requête retourne une liste de serveurs dont la rtCMEDSRV est arrêtée dans la fenêtre de temps. 

- La requête pour l’alerte de réinitialisation est la :

  ```Kusto
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003) | summarize arg_max(TimeGenerated, EventID) by Computer  | where EventID == 2500
  ```

    La requête de réinitialisation fait exactement l’inverse de la requête d’erreur. Pour chaque ordinateur, il en retourne un si le dernier événement est l’événement de démarrage du service . Elle ne retourne rien si le dernier événement est l’événement d’arrêt de service.

**Créez une paire d’alertes : « Trop d’appels simultanés dans les serveurs de médiation » et « Les appels simultanés reviennent à la charge normale »**

Pour créer cette alerte :

- La requête de l’alerte d’erreur est la :

  ```Kusto
  Perf | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName == "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls >= 500
  ```

    Pour chaque ordinateur, la requête reçoit les derniers compteurs pour l’appel entrant et l’appel sortant et additione ces deux valeurs. Elle retourne un journal si la valeur de la somme dépasse 500 ; Si ce n’est pas le cas, elle ne retourne rien. En bref, la requête retourne une liste de serveurs dont les appels simultanés sont trop nombreux dans la fenêtre de temps.

- La requête pour l’alerte de réinitialisation est la :

  ```Kusto
  Perf  | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName ==  "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls < 500
  ```

    La requête de réinitialisation fait exactement l’inverse de la requête d’erreur. Pour chaque ordinateur, la requête reçoit les derniers compteurs pour l’appel entrant et l’appel sortant et additione ces deux valeurs. Elle retourne un journal si la valeur de somme est inférieure à 500 ; sinon, elle ne retourne rien.

**Créer une alerte : « Utilisation du processeur \> 90 ou RTCMEDIARELAY arrêté dans les serveurs »**

Pour créer cette alerte, la requête est :

```Kusto
search *| where Computer contains "MediationServer" | where (Type == "Perf" or Type == "Event") | where ((ObjectName ==  "Processor" and CounterName == "% Processor Time") or EventLog == "Lync Server") | where (CounterValue > 90 or EventID == 22003)
```

La requête reçoit tous les compteurs d’utilisation du processeur et tous les événements d’arrêt de service de tous les ordinateurs et retourne un journal si l’utilisation du processeur dépasse 90 % ou si le service est jamais arrêté. 

## <a name="analyze-the-alerts-in-your-log-analytics-repository"></a>Analyser les alertes dans votre référentiel Log Analytics

Pour analyser les alertes dans votre référentiel, utilisez la solution de gestion des alertes. Pour plus d’informations, [voir solution de gestion des alertes dans Operations Management Suite (OMS)](/azure/log-analytics/log-analytics-solution-alert-management)

## <a name="recommended-minimal-monitoring-set"></a>Jeu de surveillance minimal recommandé

Pour identifier les problèmes avec les journaux des événements et les compteurs de performances : 

- **Journaux des événements.** Pour tout problème, il doit y avoir une paire d’événements, avec un ensemble d’événements pour indiquer un problème, tandis que l’autre indique que tout va bien. Pour une période donnée, il s’agit du dernier événement enregistré qui indique si quelque chose ne va pas pour cette période.

- **Compteurs de performances.** Il doit y avoir un seuil pour les compteurs surveillés.

Le tableau suivant répertorie les services que Microsoft recommande d’surveiller en répertoriant les ID d’événement d’arrêt et de démarrage :

|Nom du service  <br/> |Rôle serveur cible  <br/> |ID d’événement d’arrêt  <br/> |ID d’événement de démarrage  <br/> |
|:-----|:-----|:-----|:-----|
|RTCMEDSRV  <br/> |Serveur de médiation  <br/> |25003  <br/> |25002  <br/> |
|RTCSRV  <br/> |Serveur Edge  <br/> |12289  <br/> |12288  <br/> |
|RTCMRAUTH  <br/> |Serveur Edge  <br/> |19003  <br/> |19002  <br/> |
|RTCMEDIARELAY  <br/> |Serveur Edge  <br/> |22003  <br/> |22002  <br/> |

Le tableau suivant répertorie les problèmes réseau que Microsoft recommande de surveiller :


| Nom du moniteur  <br/>                                        | Rôle serveur cible  <br/> | Expression d’ID d’événement de réussite  <br/> | Expression d’ID d’événement d’erreur  <br/> | Exemple d’échec  <br/> |
|:-----------------------------------------------------------|:--------------------------|:-----------------------------------|:---------------------------------|:-----------------------|
| Échec de la connectivité du serveur de médiation vers la passerelle  <br/>    | Serveur de médiation  <br/>   | 25062                              |                                  | 25002  <br/>           |
| Échec de la fin de l’appel du serveur de médiation vers la passerelle  <br/> | Serveur de médiation  <br/>   | 25064                              |                                  | 25002  <br/>           |
| Problèmes réseau critiques  <br/>                           | Serveur Edge  <br/>        | 14353                              |                                  | 12288  <br/>           |

Les listes suivantes répertorient les compteurs de capacité des appels qui doivent être surveillés. Ces numéros doivent être inférieurs à 500 pour l’édition standard de Cloud Connector ; inférieur à 50 pour l’édition minimale de Cloud Connector.

- LS:MediationServer - Inbound Calls(_Total) \- Current 

- LS:MediationServer - Outbound Calls(_Total) \- Current 

- LS:MediationServer - Appels entrants(_Total) appels de déviation \- du trafic multimédia actifs

- LS:MediationServer - Appels sortants(_Total) appels de déviation \- du trafic multimédia actifs

## <a name="see-also"></a>Voir aussi

Pour plus d’informations sur l’working with OMS, consultez les informations suivantes :

- [Rechercher des données à l’aide des recherches de journaux dans Log Analytics](/azure/log-analytics/log-analytics-log-searches)

- [Référence du langage Azure Log Analytics](https://docs.loganalytics.io/docs/Language-Reference)

- [Comprendre les alertes dans Log Analytics](/azure/log-analytics/log-analytics-alerts)

- [Connecter Windows au service Log Analytics dans Azure](/azure/log-analytics/log-analytics-windows-agents)