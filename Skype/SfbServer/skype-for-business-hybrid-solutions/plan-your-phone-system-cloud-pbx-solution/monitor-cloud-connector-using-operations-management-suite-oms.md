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
description: Lisez cette rubrique pour découvrir comment surveiller votre déploiement cloud connector version 2.1 et ultérieure à l’aide de Microsoft Operations Management Suite (OMS).
ms.openlocfilehash: c10eac34e065ab76cb570a21752838c308b6afd8
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65676506"
---
# <a name="monitor-cloud-connector-using-operations-management-suite-oms"></a>Surveiller Cloud Connector à l’aide d’Operations Management Suite (OMS)

> [!Important]
> Cloud Connector Edition prendra sa retraite le 31 juillet 2021 avec Skype Entreprise Online. Une fois votre organisation mise à niveau vers Teams, découvrez comment connecter votre réseau de téléphonie local à Teams à l’aide du [routage direct](/MicrosoftTeams/direct-routing-landing-page).

Lisez cette rubrique pour découvrir comment surveiller votre déploiement cloud connector version 2.1 et ultérieure à l’aide de Microsoft Operations Management Suite (OMS).

Vous pouvez désormais surveiller votre déploiement Cloud Connector version 2.1 et ultérieure à l’aide d’Operations Management Suite (OMS), une solution de gestion informatique cloud Microsoft. OMS Log Analytics vous permet de surveiller et d’analyser la disponibilité et les performances des ressources, notamment les machines physiques et virtuelles. Pour plus d’informations sur OMS et Log Analytics, consultez [Qu’est-ce qu’Operations Management Suite (OMS) ?](/azure/operations-management-suite/operations-management-suite-overview)

Cette rubrique comprend les sections suivantes :

- Conditions préalables

- Configurer Cloud Connector pour utiliser OMS

- Configurer OMS

- Analyser les alertes dans votre référentiel Log Analytics

- Ensemble de surveillance recommandé

## <a name="prerequisites"></a>Conditions préalables

Avant de pouvoir utiliser OMS pour surveiller votre déploiement Cloud Connector, vous aurez besoin des éléments suivants :

- **Un compte Azure et un espace de travail OMS.** Si vous n’avez pas encore de compte Azure, vous devez en créer un pour utiliser OMS Log Analytics. Pour plus d’informations sur la création d’un compte Azure et la configuration d’un espace de travail OMS, consultez [Démarrage avec un espace de travail Log Analytics](/azure/log-analytics/log-analytics-get-started).

- **Cloud Connector version 2.1 ou ultérieure**

- **Une nouvelle recherche dans les journaux Log Analytics** est requise pour la surveillance du connecteur cloud. Pour plus d’informations, consultez [Mettre à niveau votre espace de travail Azure Log Analytics vers une nouvelle recherche dans les journaux](/azure/log-analytics/log-analytics-log-search-upgrade).

## <a name="configure-cloud-connector-to-use-oms"></a>Configurer Cloud Connector pour utiliser OMS

Vous devez configurer votre environnement local Cloud Connector pour utiliser OMS. Pour ce faire, vous aurez besoin de votre ID et de votre clé d’espace de travail OMS, que vous pouvez trouver à l’aide du portail OMS comme suit : Paramètres --\>Sources connectées --\> serveurs Windows :

![Capture d’écran de Cloud Connector OMS.](../../media/a4bb0a96-c940-435e-a3f5-5ef3062dea83.png)

La façon dont vous configurez Cloud Connector pour utiliser OMS dépend de votre scénario :

- **Si vous installez une nouvelle appliance Cloud Connector ou si vous souhaitez redéployer une appliance**, procédez comme suit avant d’exécuter Install-CcAppliance :

  1. Dans la section CloudConnector.ini fichier [Commun], définissez le paramètre OMSEnabled sur True.

     Chaque fois que Cloud Connector est déployé ou mis à niveau, il tente d’installer automatiquement l’agent OMS sur les machines virtuelles. Activez cette fonctionnalité pour que l’agent OMS puisse survivre à la mise à jour automatique du connecteur cloud.

  2. Pour configurer l’ID et la clé OMS, exécutez Set-CcCredential -AccountType OMSWorkspace.

- **Si vous installez un agent OMS sur une appliance Cloud Connector existante**, procédez comme suit :

  1. Dans la section CloudConnector.ini fichier [Commun], définissez OMSEnabled=true.

  2. Exécutez Import-CcConfiguration.

  3. Exécutez Install-CcOMSAgent.

     > [!NOTE]
     > Si les informations d’identification OMSWorkspace n’ont jamais été définies, vous êtes invité à les entrer lorsque vous exécutez install-CcOMSAgent.

- **Si vous souhaitez mettre à jour l’ID ou la clé de l’espace de travail OMS dans une appliance Cloud Connector qui a déjà installé un agent OMS :**

  1. Pour configurer l’ID et la clé OMS, exécutez Set-CcCredential -AccountType OMSWorkspace.

  2. Pour appliquer les mises à jour, exécutez Install-CcOMSAgent.

- **Pour tous les scénarios, vérifiez que les agents sont connectés comme suit :**

    Dans le portail OMS, accédez à Paramètres -\> Sources connectées -\> serveurs Windows. Vous verrez une liste des machines connectées.

## <a name="configure-oms"></a>Configurer OMS

Ensuite, vous devez spécifier votre configuration OMS à l’aide du portail OMS. Plus précisément, vous devez :

- Spécifiez des informations sur les journaux des événements et les compteurs de performances.

- Créer des alertes

### <a name="specify-information-about-event-logs-and-performance-counters"></a>Spécifier des informations sur les journaux des événements et les compteurs de performances

Dans le portail OMS, vous devez spécifier des informations sur les journaux des événements et les compteurs de performances comme suit :

1. Accédez à Paramètres-Data-Windows\>\> Journaux des événements et ajoutez les journaux des événements pour :

   - Lync Server

   - Application

     > [!NOTE]
     > Vous devez entrer manuellement Lync Server dans la zone de texte. Il n’apparaît pas comme une option dans la liste déroulante.

     Pour plus d’informations, consultez [Windows sources de données du journal des événements dans Log Analytics](/azure/log-analytics/log-analytics-data-sources-windows-events)

2. Accédez à Paramètres-Data\>-\> Windows Compteurs de performances, puis ajoutez des compteurs de performances pour :

   - **Compteurs au niveau du système d’exploitation**. Vous pouvez ajouter des compteurs au niveau du système d’exploitation, tels que l’utilisation du processeur, l’utilisation de la mémoire, l’utilisation du réseau, ou vous pouvez utiliser des solutions existantes telles que la capacité et les performances, les Analyseur de performances réseau sans ajouter explicitement de compteurs. Quelle que soit la façon dont vous décidez de les surveiller, Microsoft vous recommande de surveiller ces compteurs de système d’exploitation.

   - **Skype Entreprise compteurs**. Il existe de nombreux compteurs fournis par Skype Entreprise. Vous pouvez trouver ces compteurs en vous connectant à n’importe quel serveur de médiation et en ouvrant le Analyseur de performances. Ces compteurs commencent par « LS: ». Microsoft vous recommande de commencer avec les compteurs de capacité suivants au minimum et d’ajouter d’autres compteurs intéressants :

     Nombre total d’appels actifs :

     - LS:MediationServer - Appels entrants (_Total)\- actuels

     - LS:MediationServer - Appels sortants (_Total)\- actuels

     Nombre total d’appels de contournement de média actifs :

     - LS:MediationServer - Appels entrants (_Total)\- Appels de contournement multimédia actifs

     - LS:MediationServer - Appels sortants (_Total)\- Appels de contournement de média actifs

     > [!NOTE]
     > Vous devez entrer manuellement les compteurs de performances dans la zone de texte. Elles n’apparaissent pas en tant qu’options dans la liste déroulante.

     Pour plus d’informations, consultez [les sources de données de performances Windows et Linux dans Log Analytics](/azure/log-analytics/log-analytics-data-sources-performance-counters)

### <a name="create-alerts"></a>Créer des alertes

Il existe deux types d’alertes dans OMS : le nombre d’alertes de résultats et les alertes de mesure de métrique. Pour plus d’informations sur la création d’alertes, consultez [Utilisation des règles d’alerte dans Log Analytics](/azure/log-analytics/log-analytics-alerts-creating).

Vous devez prendre en compte les éléments suivants lors de la création d’alertes :

- Assurez-vous que l’alerte est une alerte de nombre de résultats, qui est la sélection par défaut.

- Les requêtes de démonstration nécessitent que « Nombre de résultats » soit défini sur « Supérieur à 0 ».

- Il est recommandé de définir à la fois la fenêtre De temps et la fréquence des alertes sur 5 minutes.

- Il est recommandé de ne pas activer « Supprimer les alertes » pour les alertes de démonstration.

- Pour les scénarios d’alerte classiques, Microsoft recommande de créer une paire d’alertes : une alerte d’erreur et une alerte de réinitialisation. Pour l’alerte d’erreur, sélectionnez le niveau de gravité Critique ; pour l’alerte de réinitialisation, sélectionnez le niveau de gravité Informational .

Les sections suivantes décrivent comment créer des exemples d’alertes.

#### <a name="create-an-alert-pair-rtcmedsrv-is-not-running-in-mediation-servers-and-rtcmedsrv-is-back-in-running-in-mediation-servers"></a>Créez une paire d’alertes : « RTCMEDSRV n’est PAS en cours d’exécution dans les serveurs de médiation » et « RTCMEDSRV est de nouveau en cours d’exécution dans les serveurs de médiation »

Pour créer cette paire d’alertes :

- La requête pour l’alerte d’erreur est la suivante :

  ```Kusto
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003)  | summarize arg_max(TimeGenerated, EventID) by Computer | where EventID == 25003
  ```

    La requête utilise le filtre d’ordinateur *où l’ordinateur contient « MediationServer ».* Le filtre sélectionne uniquement l’ordinateur dont le nom contient la chaîne « MediationServer ».

     Vous devez remplacer le filtre par votre propre filtre d’ordinateur ou simplement le supprimer. Vous pouvez créer des filtres de chaînes complexes sans expressions régulières. Vous pouvez également choisir d’utiliser des expressions régulières. En outre, vous pouvez créer un groupe d’ordinateurs en enregistrant une requête de recherche et en utilisant ce groupe comme filtre d’ordinateur dans votre requête d’alerte. Pour plus d’informations, consultez [Groupes d’ordinateurs dans les recherches dans les journaux Log Analytics](/azure/log-analytics/log-analytics-computer-groups).

    Pour chaque ordinateur, la requête d’erreur obtient le dernier journal des événements pour le démarrage du service RTCMEDSRV et l’arrêt du service. Il retourne un journal si le dernier événement est l’événement d’arrêt de service ; il ne retourne rien si le dernier événement est l’événement de démarrage du service. En bref, la requête retourne une liste de serveurs dont RTCMEDSRV est arrêté dans la fenêtre de temps.

- La requête pour l’alerte de réinitialisation est la suivante :

  ```Kusto
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003) | summarize arg_max(TimeGenerated, EventID) by Computer  | where EventID == 2500
  ```

    La requête de réinitialisation effectue exactement l’inverse de la requête d’erreur. Pour chaque ordinateur, il en retourne un si le dernier événement est l’événement de démarrage du service ; il ne retourne rien si le dernier événement est l’événement d’arrêt de service.

#### <a name="create-an-alert-pair--too-many-concurrent-calls-in-mediation-servers-and-concurrent-calls-fall-back-to-normal-load"></a>Créez une paire d’alertes : « Trop d’appels simultanés dans les serveurs de médiation » et « Les appels simultanés retombent à une charge normale »

Pour créer cette alerte :

- La requête pour l’alerte d’erreur est la suivante :

  ```Kusto
  Perf | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName == "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls >= 500
  ```

    Pour chaque ordinateur, la requête obtient les derniers compteurs pour l’appel entrant et l’appel sortant, puis additionner ces deux valeurs. Elle retourne un journal si la valeur de somme dépasse 500 ; elle ne retournera rien si ce n’est pas le cas. En bref, la requête retourne une liste de serveurs dont les appels simultanés sont trop nombreux dans la fenêtre de temps.

- La requête pour l’alerte de réinitialisation est la suivante :

  ```Kusto
  Perf  | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName ==  "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls < 500
  ```

    La requête de réinitialisation effectue exactement l’inverse de la requête d’erreur. Pour chaque ordinateur, la requête obtient les derniers compteurs pour l’appel entrant et l’appel sortant, puis additionner ces deux valeurs. Elle retourne un journal si la valeur de somme est inférieure à 500 ; il ne retournera rien d’autre.

#### <a name="create-an-alert-cpu-usage--90-or-rtcmediarelay-stopped-in-servers-alert"></a>Créer une alerte : alerte « Utilisation \> du processeur 90 ou RTCMEDIARELAY arrêtée dans les serveurs »

Pour créer cette alerte, la requête est la suivante :

```Kusto
search *| where Computer contains "MediationServer" | where (Type == "Perf" or Type == "Event") | where ((ObjectName ==  "Processor" and CounterName == "% Processor Time") or EventLog == "Lync Server") | where (CounterValue > 90 or EventID == 22003)
```

La requête obtient tous les événements d’arrêt de service et de compteur d’utilisation du processeur de tous les ordinateurs et retourne un journal si l’utilisation du processeur dépasse 90 % ou si le service est arrêté.

## <a name="analyze-the-alerts-in-your-log-analytics-repository"></a>Analyser les alertes dans votre référentiel Log Analytics

Pour analyser les alertes dans votre référentiel, utilisez la solution Gestion des alertes. Pour plus d’informations, consultez [la solution Gestion des alertes dans Operations Management Suite (OMS)](/azure/log-analytics/log-analytics-solution-alert-management)

## <a name="recommended-minimal-monitoring-set"></a>Ensemble de supervision minimal recommandé

Pour identifier les problèmes liés aux journaux des événements et aux compteurs de performances :

- **Journaux des événements.** Pour tout problème, il doit y avoir une paire d’événements, avec un ensemble d’événements pour indiquer un problème, tandis que l’autre indique que tout va bien. Pour une période donnée, il s’agit du dernier événement enregistré qui indique si quelque chose ne va pas pour cette période.

- **Compteurs de performances.** Il doit y avoir un seuil pour les compteurs surveillés.

Le tableau suivant répertorie les services que Microsoft recommande de surveiller en répertoriant les ID d’événement d’arrêt et de démarrage :

|Nom du service  <br/> |Rôle serveur cible  <br/> |Arrêter l’ID d’événement  <br/> |Démarrer l’ID d’événement  <br/> |
|:-----|:-----|:-----|:-----|
|RTCMEDSRV  <br/> |Serveur de médiation  <br/> |25003  <br/> |25002  <br/> |
|RTCSRV  <br/> |Serveur Edge  <br/> |12289  <br/> |12288  <br/> |
|RTCMRAUTH  <br/> |Serveur Edge  <br/> |19003  <br/> |19002  <br/> |
|RTCMEDIARELAY  <br/> |Serveur Edge  <br/> |22003  <br/> |22002  <br/> |

Le tableau suivant répertorie les problèmes réseau que Microsoft recommande de surveiller :


| Nom du moniteur  <br/>                                        | Rôle serveur cible  <br/> | Expression d’ID d’événement Success  <br/> | Expression d’ID d’événement d’erreur  <br/> | Exemple d’échec  <br/> |
|:-----------------------------------------------------------|:--------------------------|:-----------------------------------|:---------------------------------|:-----------------------|
| Échec de connectivité du serveur de médiation à la passerelle  <br/>    | Serveur de médiation  <br/>   | 25062                              |                                  | 25002  <br/>           |
| Échec de la saisie semi-automatique d’un serveur de médiation vers une passerelle  <br/> | Serveur de médiation  <br/>   | 25064                              |                                  | 25002  <br/>           |
| Problèmes réseau critiques  <br/>                           | Serveur Edge  <br/>        | 14353                              |                                  | 12288  <br/>           |

L’exemple suivant répertorie les compteurs de capacité d’appel qui doivent être surveillés. Ces nombres doivent être inférieurs à 500 pour l’édition standard de Cloud Connector ; moins de 50 pour l’édition minimale de Cloud Connector.

- LS:MediationServer - Appels entrants (_Total)\- actuels

- LS:MediationServer - Appels sortants (_Total)\- actuels

- LS:MediationServer - Appels entrants (_Total)\- Appels de contournement multimédia actifs

- LS:MediationServer - Appels sortants (_Total)\- Appels de contournement de média actifs

## <a name="see-also"></a>Voir aussi

Pour plus d’informations sur l’utilisation d’OMS, consultez les rubriques suivantes :

- [Rechercher des données à l’aide de recherches dans les journaux dans Log Analytics](/azure/log-analytics/log-analytics-log-searches)

- [Présentation des alertes dans Log Analytics](/azure/log-analytics/log-analytics-alerts)

- [Connecter Windows des ordinateurs au service Log Analytics dans Azure](/azure/log-analytics/log-analytics-windows-agents)