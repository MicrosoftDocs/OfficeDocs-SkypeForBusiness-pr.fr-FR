---
title: API de données pour l’appel de tableau de bord qualité (CQD) dans Skype pour Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 25c2450a-f7b3-4dd2-987d-64f4246dd019
description: 'Résumé : Découvrez l’API Rata pour le tableau de bord de qualité des appels. Tableau de bord de qualité des appels est un outil de Skype pour Business Server.'
ms.openlocfilehash: e1143752031406885a77e5afab975463d5732220
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930699"
---
# <a name="data-api-for-call-quality-dashboard-cqd-in-skype-for-business-server"></a>API de données pour l’appel de tableau de bord qualité (CQD) dans Skype pour Business Server
 
**Résumé :** Découvrez l’API Rata pour le tableau de bord de qualité des appels. Tableau de bord de qualité des appels est un outil de Skype pour Business Server.
  
L’API de données fournit l’accès par programme pour appeler le tableau de bord qualité pour Skype pour Business Server.
  
## <a name="data-api-for-call-quality-dashboard"></a>API de données pour le tableau de bord de qualité des appels

L’API de données offre une interface de requête au QoE Cube. L’API de données est une API REST pour travailler avec une base de données multidimensionnelle qui fournit les mesures QoE agrégées selon les filtres et les dimensions spécifiées.
  
Les opérations REST sont incluses dans le tableau suivant.
  

|**Opération**|**Description**|
|:-----|:-----|
|[Obtenir un cube](get-cube.md) <br/> |Obtenir la liste des dimensions disponibles et des mesures.  <br/> |
|[Obtenir les membres de dimension](get-dimension-members.md) <br/> |Opération de membres de Dimension Get renvoie la liste des membres d’une dimension spécifique. Cela donne aussi la possibilité de filtrer la liste des membres et obtenir un sous-ensemble, afin de réduire le coût de transfert filaire.  <br/> |
|[Exécuter la requête](run-query.md) <br/> |Exécuter la requête d’opération offre la possibilité d’exécuter une requête sur le cube basé sur des filtres, des mesures et dimensions spécifiées et renvoyer dans les données.  <br/> |
|[Vider le cache](clear-cache.md) <br/> |Opération de Cache Clear supprime le cache sur le serveur pour les requêtes et les données. Le cache seront réinitialisés et nous allons les données du cube QoE ultérieurement pour de nouvelles demandes.  <br/> |
|[Obtenir le journal d’intégration](get-integration-log.md) <br/> |Obtenir le journal d’intégration opération retourne une liste d’entrées de journal décrivant les activités dans le QoE Cube.  <br/> |
|[Obtenir les données de la dernière intégration](get-last-integration-data.md) <br/> |Obtenir les dernières données de l’intégration du cube.  <br/> |
   
 **Ressources Cross-Origin (CORS) prise en charge pour les API de données de partage**
  
API de données prend en charge le partage de ressources Cross-Origin (CORS). CORS est une fonctionnalité HTTP qui permet à une application web en cours d’exécution dans un domaine d’accéder aux ressources dans un autre domaine. Navigateurs Web implémentent une restriction de sécurité de stratégie de même origine [Stratégie de même origine](https://www.w3.org/Security/wiki/Same_Origin_Policy) qui empêche une page web d’appeler des API dans un domaine différent. CORS fournit un moyen sécurisé pour autoriser un domaine (le domaine d’origine) appeler des API dans un autre domaine. Voir les [spécifications CORS](https://www.w3.org/TR/cors/) pour plus d’informations sur CORS.
  
 **Activer CORS d’API de données**
  
 Voici un extrait du fichier web.config API de données, affichant deux domaines répertoriés dans les paramètres de l’application corsTrustedOrigin. Toutes les demandes effectuées par les scripts chargés à partir de ces serveurs sont approuvés par l’API de données.
  
N’oubliez pas d’inclure le protocole exact, le nom d’hôte et le port (le cas échéant). Ne pas pour mettre les oblique (/) de caractères à la fin. Plusieurs entrées peuvent être spécifiées en séparant par des virgules.
  
```
<configuration>
  <appSettings>
    <add key="corsTrustedOrigin" value="https://<trusted-server>,http://<another-trusted-domain>:8080" /> <!-- Domains which are trusted to get the data -->
    <add key="QoEDataLib.DebugMode" value="True" /> <!-- Setting this to True, allows seeing of the detail logs in status page -->
…  </appSettings>
</configuration>
```


