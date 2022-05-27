---
title: Data API for Call Quality Dashboard (CQD) dans Skype Entreprise Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 25c2450a-f7b3-4dd2-987d-64f4246dd019
description: 'Résumé : Découvrez l’API de données pour le tableau de bord qualité des appels. Call Quality Dashboard est un outil pour Skype Entreprise Server.'
ms.openlocfilehash: 3204398dcf667f785f1efe71cc4d6dc5478ce54d
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675736"
---
# <a name="data-api-for-call-quality-dashboard-cqd-in-skype-for-business-server"></a>Data API for Call Quality Dashboard (CQD) dans Skype Entreprise Server
 
**Résumé:** Découvrez l’API de données pour le tableau de bord qualité des appels. Call Quality Dashboard est un outil pour Skype Entreprise Server.
  
L’API De données fournit un accès par programmation au tableau de bord qualité des appels pour Skype Entreprise Server.
  
## <a name="data-api-for-call-quality-dashboard"></a>Tableau de bord de la qualité des appels de l’API de données

L’API De données offre une interface de requête au cube QoE. L’API De données est une API REST permettant d’utiliser une base de données multidimensionnelle qui fournit des métriques QoE agrégées basées sur des dimensions et des filtres spécifiés.
  
Les opérations REST sont incluses dans le tableau suivant.
  

|**Opération**|**Description**|
|:-----|:-----|
|[Obtenir un cube](get-cube.md) <br/> |Obtenez la liste des dimensions et mesures disponibles.  <br/> |
|[Obtenir les membres de dimension](get-dimension-members.md) <br/> |L’opération Get Dimension Members retourne la liste des membres d’une dimension spécifique. Il permet également de filtrer la liste des membres et d’obtenir un sous-ensemble, afin de réduire le coût de transfert de câble.  <br/> |
|[Exécuter la requête](run-query.md) <br/> |L’opération Exécuter la requête permet d’exécuter une requête sur le cube en fonction des dimensions, mesures et filtres spécifiés et de retourner les données.  <br/> |
|[Vider le cache](clear-cache.md) <br/> |L’opération Effacer le cache supprime le cache sur le serveur pour les requêtes et les données. Cela réinitialise le cache et nous obtenons des données actualisées à partir du cube QoE par la suite pour les nouvelles demandes.  <br/> |
|[Obtenir le journal d’intégration](get-integration-log.md) <br/> |L’opération Obtenir le journal d’intégration retourne une liste d’entrées de journal décrivant les activités dans le traitement du cube QoE.  <br/> |
|[Obtenir les données de la dernière intégration](get-last-integration-data.md) <br/> |Obtenez les dernières données d’intégration à partir du cube.  <br/> |
   
 **Prise en charge du partage de ressources cross-origin (CORS) pour l’API de données**
  
L’API de données prend en charge le partage de ressources cross-origin (CORS). CORS est une fonctionnalité HTTP qui permet à une application web s’exécutant sous un domaine d’accéder aux ressources d’un autre domaine. Les navigateurs web implémentent une restriction de sécurité appelée stratégie [de](https://www.w3.org/Security/wiki/Same_Origin_Policy) même origine de stratégie de même origine qui empêche une page web d’appeler des API dans un autre domaine. CORS offre un moyen sécurisé d’autoriser un domaine (le domaine d’origine) à appeler des API dans un autre domaine. Pour plus d’informations sur CORS, consultez la [spécification CORS](https://www.w3.org/TR/cors/) .
  
 **Activation de CORS pour l’API de données**
  
 Voici un extrait de web.config d’API de données, montrant deux domaines répertoriés dans les paramètres de l’application corsTrustedOrigin. Toutes les demandes effectuées par les scripts chargés à partir de ces serveurs sont approuvées par l’API de données.
  
N’oubliez pas d’inclure le protocole exact, le nom d’hôte et le port (le cas échéant). Ne pas placer de barre oblique (/) à la fin. Plusieurs entrées peuvent être spécifiées en les séparant par des virgules.
  
```xml
<configuration>
  <appSettings>
    <add key="corsTrustedOrigin" value="https://<trusted-server>,http://<another-trusted-domain>:8080" /> <!-- Domains which are trusted to get the data -->
    <add key="QoEDataLib.DebugMode" value="True" /> <!-- Setting this to True, allows seeing of the detail logs in status page -->
...  </appSettings>
</configuration>
```


