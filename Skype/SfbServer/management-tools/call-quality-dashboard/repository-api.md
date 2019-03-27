---
title: API de référentiel pour l’appel de tableau de bord qualité (CQD) dans Skype pour Business Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d53e990f-1c5f-46d1-9eb1-8396782c2753
description: 'Résumé : Découvrez l’API de référentiel pour le tableau de bord de qualité des appels. Tableau de bord de qualité des appels est un outil de Skype pour Business Server.'
ms.openlocfilehash: 9181cd1454311bb5446bb18f51af56914387e7c3
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30898809"
---
# <a name="repository-api-for-call-quality-dashboard-cqd-in-skype-for-business-server"></a>API de référentiel pour l’appel de tableau de bord qualité (CQD) dans Skype pour Business Server
 
**Résumé :** Découvrez l’API de référentiel pour le tableau de bord de qualité des appels. Tableau de bord de qualité des appels est un outil de Skype pour Business Server.
  
L’API de référentiel fournit l’accès par programme pour appeler le tableau de bord qualité pour Skype pour Business Server.
  
## <a name="repository-api-for-call-quality-dashboard"></a>API de référentiel pour le tableau de bord de qualité des appels

API de référentiel offre une interface d’accès de données pour la base de données de référentiel. Le référentiel permet au contenu d’être organisées dans une structure d’arborescence ou graphique tels que les utilisateurs peuvent regrouper les façons que pertinent pour les utilisateurs. Le référentiel prend en charge deux types généraux d’utilisateurs : utilisateur du système, qui est un utilisateur intégrée représentant le référentiel et les utilisateurs régulières qui représentent les utilisateurs autorisés du référentiel.
  
API de référentiel se compose de trois services généraux : 
  
- [Service utilisateur pour CQD](user-service.md) - pour l’accès aux utilisateurs.
    
- [Service de l’élément de tableau de bord de qualité des appels (CQD)](item-service.md) - pour accéder aux éléments et le contenu stocké dans les éléments.
    
- [Service de paramètres utilisateur de tableau de bord de qualité des appels (CQD)](user-settings-service.md) - pour accéder aux paramètres utilisateur.
    
Tableau de bord qualité appel utilise l’API de référentiel pour gérer les informations suivantes : 
  
- **Utilisateur** : représentation des utilisateurs qui ont accès au référentiel.
    
- **Rapport** - contient une liste de requêtes, stockées en tant que contenu dans les éléments du référentiel.
    
- **Requête** - permet de récupérer des données à partir des API de données stockées en tant que contenu dans les éléments du référentiel.
    
- Le **Paramètre utilisateur** - décrit un comportement d’application facultative pour l’utilisateur.
    
  **Ressources Cross-Origin (CORS) prise en charge pour l’API de référentiel de partage**
  
API de référentiel prend en charge le partage de ressources Cross-Origin (CORS). CORS est une fonctionnalité HTTP qui permet à une application web en cours d’exécution dans un domaine d’accéder aux ressources dans un autre domaine. Navigateurs Web implémentent une restriction de sécurité de stratégie de même origine [Stratégie de même origine](https://www.w3.org/Security/wiki/Same_Origin_Policy) qui empêche une page web d’appeler des API dans un domaine différent. CORS fournit un moyen sécurisé pour autoriser un domaine (le domaine d’origine) appeler des API dans un autre domaine. Voir les [spécifications CORS](https://www.w3.org/TR/cors/) pour plus d’informations sur CORS.
  
 **Activer CORS d’API de référentiel**
  
 Voici un extrait du fichier web.config API de référentiel, affichant deux domaines répertoriés dans les paramètres de l’application corsTrustedOrigin. Toutes les demandes effectuées par les scripts chargés à partir de ces serveurs sont approuvés par l’API de référentiel.
  
N’oubliez pas d’inclure le protocole exact, le nom d’hôte et le port (le cas échéant). Ne pas pour mettre les oblique (/) de caractères à la fin. Plusieurs entrées peuvent être spécifiées en séparant par des virgules.
  
```
<repositoryConfiguration>
    <service corsTrustedOrigin="https://<trusted-server>,http://<another-trusted-domain>:8080"" />
    <diagnostics eventLevel="Verbose" systemLoggedEventLevel="Error">
      <traceLog enabled="true" fileName="repository_trace.log" />
    </diagnostics>
 </repositoryConfiguration>
```


