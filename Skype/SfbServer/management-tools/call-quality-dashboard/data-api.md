---
title: Données API pour le tableau de bord (CQD) appel qualité dans Skype pour Business Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 25c2450a-f7b3-4dd2-987d-64f4246dd019
description: 'Résumé : Découvrez le Rata API d’appel de tableau de bord qualité. Tableau de bord qualité appel est un outil de Skype pour Business Server 2015.'
ms.openlocfilehash: 038324064177c110c0736092985e9da1b330ea8b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="data-api-for-call-quality-dashboard-cqd-in-skype-for-business-server-2015"></a>Données API pour le tableau de bord (CQD) appel qualité dans Skype pour Business Server 2015
 
**Résumé :** Obtenir des informations sur l’API de Rata pour tableau de bord qualité appel. Tableau de bord qualité appel est un outil de Skype pour Business Server 2015.
  
L’API de données permet d’accéder par programmation pour appeler le tableau de bord qualité pour Skype pour Business Server 2015.
  
## <a name="data-api-for-call-quality-dashboard"></a>API de données pour le tableau de bord qualité appel

L’API de données offre une interface de requête au QoE Cube. L’API de données est une API REST pour travailler avec une base de données multidimensionnelle qui fournit des métriques de QoE agrégées en fonction des filtres et des dimensions spécifiées.
  
Les opérations de repos sont incluses dans le tableau suivant.
  

|**Opération**|**Description**|
|:-----|:-----|
|[Obtenir le Cube](get-cube.md) <br/> |Obtenir la liste des dimensions disponibles et des mesures.  <br/> |
|[Obtenir les membres de Dimension](get-dimension-members.md) <br/> |Opération d’obtention de membres de Dimension renvoie la liste des membres d’une dimension spécifique. Cela donne aussi la possibilité de filtrer la liste des membres et obtenir un sous-ensemble, afin de réduire le coût de transfert de fil.  <br/> |
|[Exécuter requête](run-query.md) <br/> |Exécuter la requête d’opération fournit la possibilité d’exécuter une requête sur le cube basé sur les filtres, les mesures et les dimensions spécifiées et renvoyer de nouveau les données.  <br/> |
|[Vider le Cache](clear-cache.md) <br/> |Opération d’effacement du Cache supprime le cache sur le serveur pour les requêtes et les données. Cela réinitialisera le cache et nous allons les données actualisées QoE cube par la suite pour les nouvelles demandes.  <br/> |
|[Obtenir le journal d’intégration](get-integration-log.md) <br/> |Obtenir le journal d’intégration opération retourne une liste d’entrées de journal décrivant les activités QoE cube de traitement.  <br/> |
|[Obtenir les dernières données d’intégration](get-last-integration-data.md) <br/> |Obtenir les dernières données d’intégration à partir du cube.  <br/> |
   
 **La prise en charge des données API (CORS) le partage des ressources entre-origine**
  
API de données prend en charge le partage de ressources entre origine (CORS). CORS est une fonctionnalité HTTP qui permet à une application web en cours d’exécution dans un domaine d’accéder aux ressources dans un autre domaine. Navigateurs Web implémentent une restriction de sécurité appelée stratégie de même origine [Stratégie de même origine](https://www.w3.org/Security/wiki/Same_Origin_Policy) qui empêche une page web à partir de l’appel d’API dans un autre domaine. CORS offre un moyen sécurisé pour permettre à un domaine (le domaine d’origine) appeler des API dans un autre domaine. Consultez la [spécification de CORS](https://www.w3.org/TR/cors/) pour plus de détails sur les CORS.
  
 **L’activation de CORS pour données API**
  
 Voici un extrait du fichier web.config de données API, montrant deux domaines répertoriés dans les paramètres de l’application corsTrustedOrigin. Toutes les demandes effectuées par les scripts chargés à partir de ces serveurs sont approuvés par les API de données.
  
N’oubliez pas d’inclure le protocole exact, le nom d’hôte et le port (le cas échéant). Ne pas pour placer les oblique (/) de caractère à la fin. Plusieurs entrées peuvent être spécifiées en les séparant par des virgules.
  
```
<configuration>
  <appSettings>
    <add key="corsTrustedOrigin" value="https://<trusted-server>,http://<another-trusted-domain>:8080" /> <!-- Domains which are trusted to get the data -->
    <add key="QoEDataLib.DebugMode" value="True" /> <!-- Setting this to True, allows seeing of the detail logs in status page -->
…  </appSettings>
</configuration>

```


