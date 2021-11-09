---
title: API de données pour le tableau de bord de qualité des appels (CQD) dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 25c2450a-f7b3-4dd2-987d-64f4246dd019
description: 'Résumé : Découvrez l’API de données pour le tableau de bord de qualité des appels. Le Tableau de bord de qualité des appels est un outil pour Skype Entreprise Server.'
ms.openlocfilehash: 619a02d776f5eb55c6349d1f123181190bc0299d
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60862211"
---
# <a name="data-api-for-call-quality-dashboard-cqd-in-skype-for-business-server"></a>API de données pour le tableau de bord de qualité des appels (CQD) dans Skype Entreprise Server
 
**Résumé :** Découvrez l’API de données pour le tableau de bord de qualité des appels. Le Tableau de bord de qualité des appels est un outil pour Skype Entreprise Server.
  
L’API de données fournit un accès par programme au Tableau de bord de qualité des appels pour Skype Entreprise Server.
  
## <a name="data-api-for-call-quality-dashboard"></a>API de données pour le tableau de bord de qualité des appels

L’API données offre une interface de requête au cube QoE. L’API de données est une API REST permettant d’travailler avec une base de données multidimensionnelle qui fournit des mesures QoE agrégées basées sur des dimensions et des filtres spécifiés.
  
Les opérations REST sont incluses dans le tableau suivant.
  

|**Opération**|**Description**|
|:-----|:-----|
|[Obtenir un cube](get-cube.md) <br/> |Obtenir la liste des dimensions et mesures disponibles.  <br/> |
|[Obtenir les membres de dimension](get-dimension-members.md) <br/> |L’opération Obtenir les membres de dimension renvoie la liste des membres d’une dimension spécifique. Il permet également de filtrer la liste des membres et d’obtenir un sous-ensemble, afin de réduire le coût de transfert de câblage.  <br/> |
|[Exécuter la requête](run-query.md) <br/> |L’opération Exécuter une requête permet d’exécuter une requête sur le cube en fonction des dimensions, mesures et filtres spécifiés et de renvoyer les données.  <br/> |
|[Vider le cache](clear-cache.md) <br/> |L’opération Effacer le cache supprime le cache sur le serveur pour les requêtes et les données. Cela réinitialise le cache et nous allons obtenir des données à jour à partir du cube QoE par la suite pour les nouvelles demandes.  <br/> |
|[Obtenir le journal d’intégration](get-integration-log.md) <br/> |L’opération Obtenir le journal d’intégration renvoie une liste d’entrées de journal décrivant les activités dans le traitement du cube QoE.  <br/> |
|[Obtenir les données de la dernière intégration](get-last-integration-data.md) <br/> |Obtenez les dernières données d’intégration à partir du cube.  <br/> |
   
 **Prise en charge du partage de ressources d’origine croisée (CORS) pour l’API de données**
  
L’API de données prend en charge le partage de ressources d’origine croisée (CORS). CORS est une fonctionnalité HTTP qui permet à une application web s’exécutant sous un domaine d’accéder aux ressources d’un autre domaine. Les navigateurs web implémentent une restriction de sécurité appelée stratégie d’origine identique qui empêche une page web d’appeler des API dans un autre domaine. [](https://www.w3.org/Security/wiki/Same_Origin_Policy) CORS offre un moyen sécurisé d’autoriser un domaine (le domaine d’origine) à appeler des API dans un autre domaine. Pour plus [d’informations sur CORS,](https://www.w3.org/TR/cors/) voir la spécification CORS.
  
 **Activation de CORS pour l’API de données**
  
 Voici un extrait de données api web.config, montrant deux domaines répertoriés dans les paramètres de l’application corsTrustedOrigin. Toutes les demandes faites par les scripts chargés à partir de ces serveurs sont fiables par l’API de données.
  
N’oubliez pas d’inclure le protocole exact, le nom d’hôte et le port (le cas contraire). Ne placez pas de barre oblique (/) à la fin. Plusieurs entrées peuvent être spécifiées en les séparant par des virgules.
  
```xml
<configuration>
  <appSettings>
    <add key="corsTrustedOrigin" value="https://<trusted-server>,http://<another-trusted-domain>:8080" /> <!-- Domains which are trusted to get the data -->
    <add key="QoEDataLib.DebugMode" value="True" /> <!-- Setting this to True, allows seeing of the detail logs in status page -->
…  </appSettings>
</configuration>
```


