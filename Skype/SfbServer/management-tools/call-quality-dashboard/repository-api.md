---
title: API de référentiel pour le tableau de bord de qualité des appels (CQD) dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d53e990f-1c5f-46d1-9eb1-8396782c2753
description: 'Résumé : Découvrez l’API référentiel pour le tableau de bord de qualité des appels. Le Tableau de bord de qualité des appels est un outil pour Skype Entreprise Server.'
ms.openlocfilehash: 982ec0932f0a57958e1929a6ae2413ada0b5c9fa
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803124"
---
# <a name="repository-api-for-call-quality-dashboard-cqd-in-skype-for-business-server"></a>API de référentiel pour le tableau de bord de qualité des appels (CQD) dans Skype Entreprise Server
 
**Résumé :** Découvrez l’API référentiel pour le tableau de bord de qualité des appels. Le Tableau de bord de qualité des appels est un outil pour Skype Entreprise Server.
  
L’API Référentiel fournit un accès par programmation pour le Tableau de bord de qualité des appels pour Skype Entreprise Server.
  
## <a name="repository-api-for-call-quality-dashboard"></a>API de référentiel pour le tableau de bord de qualité des appels

L’API référentiel propose une interface d’accès aux données pour la base de données du référentiel. Le référentiel permet d’organiser le contenu dans une arborescence ou une structure graphique afin que les utilisateurs peuvent les grouper de la manière qui leur semble logique. Le référentiel prend en charge deux types d’utilisateurs généraux : l’utilisateur système, qui est un utilisateur intégré représentant le référentiel, et les utilisateurs réguliers qui représentent les utilisateurs autorisés du référentiel.
  
L’API de référentiel se compose de trois services généraux : 
  
- [Service utilisateur pour le CQD](user-service.md) - pour accéder aux utilisateurs.
    
- Service d’élément pour le tableau de bord de qualité des appels [(CQD)](item-service.md) : pour accéder aux éléments et au contenu stocké dans les éléments.
    
- Service de paramètres utilisateur pour le tableau de bord de qualité des appels [(CQD)](user-settings-service.md) : pour accéder aux paramètres utilisateur.
    
Le tableau de bord de qualité des appels utilise l’API référentiel pour gérer les informations suivantes : 
  
- **User** : représentation des utilisateurs qui ont accès au référentiel.
    
- **Rapport** : contient une liste de requêtes, stockées en tant que contenu dans des éléments de référentiel.
    
- **Requête :** utilisée pour récupérer des données à partir de l’API de données, stockées en tant que contenu dans des éléments de référentiel.
    
- **Paramètre utilisateur** : décrit un comportement d’application facultatif pour l’utilisateur.
    
  **Prise en charge du partage de ressources d’origine croisée (CORS) pour l’API de référentiel**
  
L’API de référentiel prend en charge le partage de ressources d’origine croisée (CORS). CORS est une fonctionnalité HTTP qui permet à une application web s’exécutant sous un domaine d’accéder aux ressources d’un autre domaine. Les navigateurs web implémentent une restriction de sécurité appelée stratégie de même origine qui empêche une page web d’appeler des API dans un autre domaine. [](https://www.w3.org/Security/wiki/Same_Origin_Policy) CORS offre un moyen sécurisé d’autoriser un domaine (le domaine d’origine) à appeler des API dans un autre domaine. Pour plus [d’informations sur CORS,](https://www.w3.org/TR/cors/) voir la spécification CORS.
  
 **Activation de CORS pour l’API référentiel**
  
 Voici un extrait de l’api web.config référentiel, montrant deux domaines répertoriés dans les paramètres de l’application corsTrustedOrigin. Toutes les demandes faites par les scripts chargés à partir de ces serveurs sont fiables par l’API du référentiel.
  
N’oubliez pas d’inclure le protocole exact, le nom d’hôte et le port (le cas contraire). Ne placez pas de barre oblique (/) à la fin. Plusieurs entrées peuvent être spécifiées en les séparant par des virgules.
  
```xml
<repositoryConfiguration>
    <service corsTrustedOrigin="https://<trusted-server>,http://<another-trusted-domain>:8080"" />
    <diagnostics eventLevel="Verbose" systemLoggedEventLevel="Error">
      <traceLog enabled="true" fileName="repository_trace.log" />
    </diagnostics>
 </repositoryConfiguration>
```


