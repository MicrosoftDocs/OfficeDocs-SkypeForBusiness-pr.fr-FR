---
title: Surveiller le connecteur de nuage à l’aide de la Suite de gestion des opérations (OMS)
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: edf4a04c-d4c9-4c05-aacc-9e084618bb55
description: Lisez cette rubrique pour savoir comment surveiller votre version de nuage connecteur 2.1 et de déploiement ultérieure à l’aide de Microsoft Operations Management Suite (OMS).
ms.openlocfilehash: 36d70a1504eab085d319e46d03c3c6f0bd9d14f3
ms.sourcegitcommit: 7d65eafd5b0163ece91deb7801458c7a45fcc4f7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/29/2018
ms.locfileid: "25839822"
---
# <a name="monitor-cloud-connector-using-operations-management-suite-oms"></a>Surveiller le connecteur de nuage à l’aide de la Suite de gestion des opérations (OMS)

Lisez cette rubrique pour savoir comment surveiller votre version de nuage connecteur 2.1 et de déploiement ultérieure à l’aide de Microsoft Operations Management Suite (OMS).

Vous pouvez maintenant surveiller votre version de nuage connecteur 2.1 et de déploiement ultérieure à l’aide des opérations de gestion de Suite (OMS), un solution de gestion informatique en nuage de Microsoft. OMS journal Analytique vous permet de surveiller et d’analyser la disponibilité et les performances des ressources, y compris physiques et les machines virtuelles. Pour plus d’informations sur OMS et journal Analytique, voir [Quelle est la Suite de gestion des opérations (OMS) ?](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview).

Cette rubrique contient les sections suivantes :

- Conditions requises

- Configurer le connecteur sur le nuage pour utiliser OMS

- Configurer OMS

- Analyser les alertes dans le référentiel de journal Analytique

- Jeu de surveillance recommandé

## <a name="prerequisites"></a>Conditions requises

Avant de pouvoir utiliser OMS pour analyser votre déploiement en nuage connecteur, vous devez les éléments suivants :

- **Un compte Azure et un espace de travail OMS.** Si vous ne disposez pas d’un compte Azure, vous devrez créer un pour utiliser OMS journal Analytique. Pour plus d’informations sur la façon de créer un compte Azure et configurer un espace de travail OMS, voir [Démarrer avec un espace de travail journal Analytique](https://docs.microsoft.com/azure/log-analytics/log-analytics-get-started).

- **Nuage connecteur 2.1 ou version ultérieure**

- **Recherche de journal de journal Analytique** est requis pour la surveillance du connecteur sur le nuage. Pour plus d’informations, voir [l’espace de travail Azure journal Analytique nouvelle recherche de journal de mise à niveau](https://docs.microsoft.com/azure/log-analytics/log-analytics-log-search-upgrade).

## <a name="configure-cloud-connector-to-use-oms"></a>Configurer le connecteur sur le nuage pour utiliser OMS

Vous devez configurer votre environnement local de nuage connecteur pour utiliser OMS. Pour ce faire, vous aurez besoin de votre ID d’espace de travail OMS et la clé, vous pouvez trouver en utilisant le portail OMS comme suit : paramètres--\>Sources connectées--\> serveurs Windows :

![Capture d'écran pour Cloud Connector OMS](../../media/a4bb0a96-c940-435e-a3f5-5ef3062dea83.png)

Comment configurer le nuage connecteur pour utiliser OMS dépend de votre scénario :

- **Si vous installez un nouveau matériel nuage connecteur ou vous souhaitez redéployer un matériel**, procédez comme suit avant d’exécuter Install-CcAppliance :

1. Dans le fichier CloudConnector.ini section [courantes], définissez le paramètre OMSEnabled sur True.

    Chaque fois que le nuage connecteur est déployé ou mis à niveau, il essaiera d’installer l’agent d’OMS automatiquement sur les ordinateurs virtuels. Activer cette fonctionnalité afin que l’agent OMS puisse résister à la mise à jour automatique du nuage connecteur.

2. Pour configurer le OMS ID et la clé, exécutez Set-CcCredential - AccountType OMSWorkspace. 

- **Si vous installez un agent OMS sur une appliance nuage connecteur existant**, procédez comme suit :

1. Dans le fichier CloudConnector.ini section [courantes], définissez OMSEnabled = true. 

2. Exécutez Import-CcConfiguration. 

3. Exécutez Install-CcOMSAgent. 

    > [!NOTE]
    > Si les informations d’identification OMSWorkspace n’a jamais été définie, vous êtes invité pour les informations d’identification lorsque vous exécutez install-CcOMSAgent. 

- **Si vous souhaitez mettre à jour de l’ID d’espace de travail OMS ou clés dans une solution de nuage connecteur qui a déjà installé un agent OMS :**

1. Pour configurer le OMS ID et la clé, exécutez Set-CcCredential - AccountType OMSWorkspace. 

2. Pour appliquer les mises à jour, exécutez Install-CcOMSAgent. 

- **Pour tous les scénarios, vérifiez que les agents sont connectés comme suit :**

    Dans le portail OMS, accédez à paramètres -\> Sources connectées -\> serveurs Windows. Vous verrez une liste d’ordinateurs connectés. 

## <a name="configure-oms"></a>Configurer OMS

Ensuite, vous devrez spécifier votre configuration OMS à l’aide du portail OMS. Plus précisément, vous devez :

- Spécifier des informations sur les compteurs de performance et les journaux des événements.

- Créer des alertes. 

### <a name="specify-information-about-event-logs-and-performance-counters"></a>Spécifier des informations sur les compteurs de performance et les journaux des événements

Dans le portail OMS, vous devez spécifier les informations sur les journaux des événements et les compteurs de performance comme suit :

1. Accédez à paramètres -\>données -\>journaux des événements Windows et ajoutez des journaux des événements : 

   - Lync Server

   - Application

     > [!NOTE]
     > Vous devez entrer manuellement Lync Server dans la zone de texte. Il n’apparaît pas en tant qu’option dans la liste déroulante. 

     Pour plus d’informations, voir [les sources de données de journal des événements Windows dans le journal Analytique](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-windows-events)

2. Accédez à paramètres -\>données -\> les compteurs de performances de Windows, et ajoutez des compteurs de performance pour : 

   - **Compteurs de niveau du système d’exploitation**. Vous pouvez ajouter des compteurs au niveau du système d’exploitation, telles que l’utilisation du processeur, de la mémoire, l’utilisation du réseau, ou vous pouvez utiliser des solutions existantes telles que la capacité et les performances, l’Analyseur de performances réseau sans ajouter explicitement des compteurs. Quelle que soit la façon dont vous décidez d’analyser les, Microsoft recommande que vous analysez ces compteurs de système d’exploitation.

   - **Skype pour les compteurs de l’entreprise**. Il existe de nombreux compteurs fournis par Skype pour les entreprises. Vous trouverez ces compteurs en vous connectant à n’importe quel serveur de médiation et l’ouverture de l’Analyseur de performances. Ces compteurs commencent par « LS : ». Microsoft recommande que vous commencez par les compteurs suivants de la capacité au minimum et ajoutez d’autres personnes qui présentent un intérêt :

     Nombre total d’appels actif :

   - LS:MediationServer - entrant Calls(_Total)\- en cours 

   - LS:MediationServer - Calls(_Total) sortants\- en cours 

     Les appels déviés total multimédia active :

   - LS:MediationServer - entrant Calls(_Total)\- appels du contournement de média Active 

   - LS:MediationServer - Calls(_Total) sortants\- appels du contournement de média Active 

     > [!NOTE]
     > Vous devez entrer manuellement les compteurs de performance dans la zone de texte. Ils n’apparaissent pas en tant qu’options dans la liste déroulante. 

     Pour plus d’informations, voir les [sources de données de performances Windows et Linux dans journal Analytique](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-performance-counters)

### <a name="create-alerts"></a>Créer des alertes

Il existe deux types d’alertes dans OMS : nombre de résultats alertes et mesure métrique. Pour plus d’informations sur la création des alertes, voir [utilisation des règles d’alerte dans le journal Analytique](https://docs.microsoft.com/azure/log-analytics/log-analytics-alerts-creating).

Lors de la création des alertes, tenez compte des éléments suivants :

- Assurez-vous que l’alerte est une alerte nombre de résultats, qui est la sélection par défaut. 

- Les requêtes de démo nécessitent que « Nombre de résultats » est défini sur « supérieur à 0 ». 

- Il est recommandé de définir la fenêtre délai et fréquence de l’alerte à 5 minutes. 

- Il est recommandé que vous n’activez pas « supprimer « alertes pour les alertes de démonstration. 

- Pour les scénarios d’alerte par défaut, Microsoft recommande la création d’une paire d’alertes : alerte d’une erreur et une rétablir alerte. Pour le message d’erreur, sélectionnez le niveau de gravité critique ; la mise en garde reset, sélectionnez le niveau de gravité information.

Les sections suivantes décrivent comment créer des alertes de l’échantillon.

 **Créer une paire de l’alerte : « RTCMEDSRV ne fonctionne pas dans les serveurs de médiation » et « RTCMEDSRV est en cours d’exécution sur les serveurs de médiation dans »**

Pour créer cette paire de l’alerte :

- La requête pour le message d’erreur est la suivante :

  ```
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003)  | summarize arg_max(TimeGenerated, EventID) by Computer | where EventID == 25003
  ```

    La requête utilise le filtre d’ordinateur *où ordinateur contient « MediationServer »* . Le filtre sélectionne uniquement l’ordinateur dont le nom contient la chaîne « MediationServer ».

     Vous souhaiteriez remplacer le filtre par le filtre de votre propre ordinateur ou simplement le supprimer. Vous pouvez créer des filtres de chaîne complexe sans les expressions régulières. Pour plus d’informations, voir [opérateurs de chaîne](https://docs.loganalytics.io/docs/Language-Reference/Scalar-operators/String-operators). Vous pouvez également choisir d’utiliser des expressions régulières. En outre, vous pouvez créer un groupe d’ordinateurs en enregistrant une requête de recherche à l’aide de ce groupe comme filtre de votre ordinateur dans votre requête de l’alerte. Pour plus d’informations, voir [groupes d’ordinateurs dans le journal Analytique connecter des recherches](https://docs.microsoft.com/azure/log-analytics/log-analytics-computer-groups).

    Pour chaque ordinateur, l’erreur de la requête sera obtenir le dernier journal des événements pour les deux le démarrage du service RTCMEDSRV et arrêt de service. Il renverra une session si le dernier événement est l’événement stop service ; Il ne renvoie rien si le dernier événement est l’événement de démarrage du service. En résumé, la requête retourne une liste de serveurs dont RTCMEDSRV est arrêté dans la fenêtre de temps. 

- La requête de l’alerte de réinitialisation est la suivante :

  ```
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003) | summarize arg_max(TimeGenerated, EventID) by Computer  | where EventID == 2500
  ```

    La requête de réinitialisation effectue exactement la chose contraire à celui de la requête de l’erreur. Pour chaque ordinateur, elle renvoie 1 si le dernier événement est le service démarre l’événement ; Il ne renvoie rien si le dernier événement est l’événement d’arrêt de service.

  **Créer une paire de l’alerte : « trop grand nombre d’appels simultané sur les serveurs de médiation » et « appels simultanés rattachées à une charge normale »**

Pour créer cette alerte :

- La requête pour le message d’erreur est la suivante :

  ```
  Perf | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName == "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls >= 500
  ```

    Pour chaque ordinateur, la requête obtiendra dernières compteurs d’appels entrants et les appels sortants et somme ces deux valeurs. Il renverra une session si la valeur de la somme est supérieure à 500 ; Il ne renvoie rien si elle n’est pas. En résumé, la requête retourne une liste de serveurs dont les appels simultanés sont trop nombreux dans la fenêtre de temps.

- La requête de l’alerte de réinitialisation est la suivante :

  ```
  Perf  | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName ==  "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls < 500
  ```

    La requête de réinitialisation effectue exactement la chose contraire à celui de la requête de l’erreur. Pour chaque ordinateur, la requête obtiendra dernières compteurs d’appels entrants et les appels sortants et somme ces deux valeurs. Renvoie un seul journal si la valeur de la somme est inférieur à 500 ; elle renvoie nothing dans le cas contraire.

  **Créer une alerte : « utilisation de l’UC \> 90 ou RTCMEDIARELAY arrêté dans les serveurs « alerte**

Pour créer cette alerte, la requête est la suivante :

```
search *| where Computer contains "MediationServer" | where (Type == "Perf" or Type == "Event") | where ((ObjectName ==  "Processor" and CounterName == "% Processor Time") or EventLog == "Lync Server") | where (CounterValue > 90 or EventID == 22003)
```

La requête obtiendra tous les compteurs d’utilisation de processeur et événement arrêt du service de tous les ordinateurs et renvoyer un journal si l’utilisation du processeur est supérieure à 90 % ou le service est déjà arrêté. 

## <a name="analyze-the-alerts-in-your-log-analytics-repository"></a>Analyser les alertes dans le référentiel de journal Analytique

Pour analyser les alertes dans le référentiel, utilisez la solution de gestion des alertes. Pour plus d’informations, voir la [solution de gestion de l’alerte dans la Suite Gestion des opérations (OMS)](https://docs.microsoft.com/azure/log-analytics/log-analytics-solution-alert-management)

## <a name="recommended-minimal-monitoring-set"></a>Jeu de surveillance minimum recommandé

Pour identifier des problèmes avec les compteurs de performance et les journaux des événements : 

- **Journaux des événements.** Pour résoudre un problème, il doit être une paire d’événements, avec un ensemble d’événements pour indiquer qu'un élément est incorrect, tandis que l’autre indique que tout est bien. Pour une période donnée, il est le dernier événement enregistré qui indique si un élément est explosion pour cette période.

- **Compteurs de performance.** Il doit exister un seuil pour les compteurs surveillés.

Le tableau suivant répertorie les services que Microsoft vous recommande de surveillance en répertoriant les ID d’événement arrêt et démarrage :

|Nom de service  <br/> |Rôle de serveur cible  <br/> |Arrêter l’ID d’événement  <br/> |ID d’événement Démarrer  <br/> |
|:-----|:-----|:-----|:-----|
|RTCMEDSRV  <br/> |serveur de médiation  <br/> |25003  <br/> |25002  <br/> |
|RTCSRV  <br/> |Serveur Edge  <br/> |12289  <br/> |12288  <br/> |
|RTCMRAUTH  <br/> |Serveur Edge  <br/> |19003  <br/> |19002  <br/> |
|RTCMEDIARELAY  <br/> |Serveur Edge  <br/> |22003  <br/> |22002  <br/> |

Le tableau suivant répertorie les problèmes de réseau Microsoft vous recommande de surveillance :


| Nom de l’analyseur  <br/>                                        | Rôle de serveur cible  <br/> | Expression d’ID d’événement de réussite  <br/> | Expression de l’ID d’événement d’erreur  <br/> | Exemple de défaillance  <br/> |
|:-----------------------------------------------------------|:--------------------------|:-----------------------------------|:---------------------------------|:-----------------------|
| Échec de connectivité de passerelle du serveur de médiation  <br/>    | serveur de médiation  <br/>   | 25062                              |                                  | 25002  <br/>           |
| Serveur de médiation vers passerelle Échec de fin d’appel  <br/> | serveur de médiation  <br/>   | 25064                              |                                  | 25002  <br/>           |
| Problèmes de réseau  <br/>                           | Serveur Edge  <br/>        | 14353                              |                                  | 12288  <br/>           |

Voici les compteurs de la capacité d’appel qui doivent être surveillées. Ces numéros doit être inférieure 500 pour standard edition de nuage connecteur ; inférieur à 50 pour édition minimale nuage connecteur.

- LS:MediationServer - entrant Calls(_Total)\- en cours 

- LS:MediationServer - Calls(_Total) sortants\- en cours 

- LS:MediationServer - entrant Calls(_Total)\- appels du contournement de média Active

- LS:MediationServer - Calls(_Total) sortants\- appels du contournement de média Active

## <a name="see-also"></a>Voir aussi

Pour plus d’informations sur l’utilisation des OMS, voir :

- [Rechercher des données à l’aide de recherches de journal dans le journal Analytique](https://docs.microsoft.com/azure/log-analytics/log-analytics-log-searches)

- [Référence du langage Analytique journal Azure](https://docs.loganalytics.io/docs/Language-Reference)

- [Présentation des alertes dans le journal Analytique](https://docs.microsoft.com/azure/log-analytics/log-analytics-alerts)

- [Connecter des ordinateurs Windows au service journal Analytique dans Azure](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents)


