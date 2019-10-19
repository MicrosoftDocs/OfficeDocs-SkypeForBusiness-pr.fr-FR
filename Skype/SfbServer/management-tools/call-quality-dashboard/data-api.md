---
title: API de données pour le tableau de bord de qualité des appels (bord) dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 25c2450a-f7b3-4dd2-987d-64f4246dd019
description: 'Résumé : en savoir plus sur l’API de données pour le tableau de bord de qualité des appels. Le tableau de bord de qualité des appels est un outil pour Skype entreprise Server.'
ms.openlocfilehash: 016cc1be9f5cd5506f8ee7d8ddbe2765e0015ffd
ms.sourcegitcommit: 9fd23cf0e03dd8fcf7ed04ef09dcdac048ebb44a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/18/2019
ms.locfileid: "36571918"
---
# <a name="data-api-for-call-quality-dashboard-cqd-in-skype-for-business-server"></a>API de données pour le tableau de bord de qualité des appels (bord) dans Skype entreprise Server
 
**Résumé :** En savoir plus sur l’API de données du tableau de bord de qualité des appels. Le tableau de bord de qualité des appels est un outil pour Skype entreprise Server.
  
L’API de données fournit un accès par programmation pour le tableau de bord de qualité des appels pour Skype entreprise Server.
  
## <a name="data-api-for-call-quality-dashboard"></a>API de données pour le tableau de bord de qualité des appels

L’API de données fournit une interface de requête au cube QoE. L’API de données est une API REST pour l’utilisation d’une base de données multidimensionnelle qui fournit des métriques QoE agrégées en fonction des dimensions et filtres spécifiés.
  
Les opérations REST sont comprises dans le tableau suivant.
  

|**Opération**|**Description**|
|:-----|:-----|
|[Obtenir un cube](get-cube.md) <br/> |Obtenez la liste des dimensions et mesures disponibles.  <br/> |
|[Obtenir les membres de dimension](get-dimension-members.md) <br/> |Opération obtenir les membres d’une dimension renvoie la liste des membres d’une dimension spécifique. Vous pouvez également filtrer la liste des membres et obtenir un sous-ensemble afin de réduire le coût de transfert bancaire.  <br/> |
|[Exécuter la requête](run-query.md) <br/> |L’opération exécuter une requête permet d’exécuter une requête sur le cube en fonction de dimensions, mesures et filtres spécifiés, puis de renvoyer les données.  <br/> |
|[Vider le cache](clear-cache.md) <br/> |L’opération d’effacement du cache supprime le cache du serveur pour les requêtes et les données. Cette opération a pour réinitialisation le cache et nous obtiendrons de nouvelles données du cube QoE par la suite pour de nouvelles demandes.  <br/> |
|[Obtenir le journal d’intégration](get-integration-log.md) <br/> |L’opération d’obtention du journal d’intégration renvoie une liste des entrées du journal décrivant les activités du traitement du cube QoE.  <br/> |
|[Obtenir les données de la dernière intégration](get-last-integration-data.md) <br/> |Obtenez les dernières données d’intégration du cube.  <br/> |
   
 **Prise en charge du partage de ressources intersession pour l’API de données**
  
API de données prend en charge le partage de ressources à l’origine. CORS est une fonctionnalité HTTP qui permet à une application Web exécutée sous un domaine d’accéder aux ressources d’un autre domaine. Les navigateurs Web mettent en œuvre une restriction de sécurité connue sous le nom de stratégie de [même origine qui](https://www.w3.org/Security/wiki/Same_Origin_Policy) empêche une page Web d’appeler des API dans un domaine différent. CORS fournit un moyen sécurisé pour permettre à un domaine (domaine d’origine) d’appeler des API dans un autre domaine. Pour plus d’informations sur l’affichage de l’une des [caractéristiques](https://www.w3.org/TR/cors/) de cors.
  
 **Activation de l’API CORS pour les données**
  
 Voici un extrait de l’API de données Web. config, montrant deux domaines répertoriés dans les paramètres de l’application corsTrustedOrigin. Toutes les demandes effectuées par les scripts chargés à partir de ces serveurs sont approuvées par l’API de données.
  
N’oubliez pas d’inclure le protocole, le nom d’hôte et le port exacts (le cas échéant). Ne placez aucun caractère barre oblique (/) à la fin. Plusieurs entrées peuvent être spécifiées en les séparant par des virgules.
  
```
<configuration>
  <appSettings>
    <add key="corsTrustedOrigin" value="https://<trusted-server>,http://<another-trusted-domain>:8080" /> <!-- Domains which are trusted to get the data -->
    <add key="QoEDataLib.DebugMode" value="True" /> <!-- Setting this to True, allows seeing of the detail logs in status page -->
…  </appSettings>
</configuration>
```


