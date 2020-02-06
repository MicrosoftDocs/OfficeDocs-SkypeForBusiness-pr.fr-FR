---
title: API du référentiel pour le tableau de bord de qualité des appels (bord) dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d53e990f-1c5f-46d1-9eb1-8396782c2753
description: 'Résumé : en savoir plus sur l’API du référentiel pour le tableau de bord de qualité des appels. Le tableau de bord de qualité des appels est un outil pour Skype entreprise Server.'
ms.openlocfilehash: a027cc7402bad7524343391f9bf7039dd077a46c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816693"
---
# <a name="repository-api-for-call-quality-dashboard-cqd-in-skype-for-business-server"></a>API du référentiel pour le tableau de bord de qualité des appels (bord) dans Skype entreprise Server
 
**Résumé :** En savoir plus sur l’API du référentiel pour le tableau de bord de qualité des appels. Le tableau de bord de qualité des appels est un outil pour Skype entreprise Server.
  
L’API du référentiel fournit un accès par programmation pour le tableau de bord de qualité des appels pour Skype entreprise Server.
  
## <a name="repository-api-for-call-quality-dashboard"></a>API du référentiel pour le tableau de bord de qualité des appels

L’API du référentiel offre une interface d’accès aux données à la base de données du référentiel. Le référentiel permet d’organiser le contenu dans une arborescence ou une structure de graphique de telle sorte que les utilisateurs puissent les regrouper selon les besoins des utilisateurs. Le référentiel prend en charge deux types d’utilisateurs généraux : l’utilisateur système, qui est un utilisateur intégré représentant le référentiel, et les utilisateurs normaux qui représentent les utilisateurs autorisés du référentiel.
  
L’API du référentiel se compose de trois services généraux : 
  
- [Service utilisateur pour bord](user-service.md) -pour accéder aux utilisateurs.
    
- [Service d’article pour le tableau de bord de qualité des appels (bord)](item-service.md) -pour accéder aux éléments et au contenu stocké dans les éléments.
    
- [Service de paramètres utilisateur pour le tableau de bord de qualité des appels (bord)](user-settings-service.md) -pour accéder aux paramètres de l’utilisateur.
    
Le tableau de bord de qualité des appels utilise l’API du référentiel pour gérer les informations suivantes : 
  
- Représentation **utilisateur** des utilisateurs qui ont accès au référentiel.
    
- **Rapport** -contient une liste de requêtes, stockée en tant que contenu dans les éléments du référentiel.
    
- **Requête** utilisée pour récupérer les données à partir de l’API de données, stockées en tant que contenu dans les éléments du référentiel.
    
- **Paramètre utilisateur** -décrit un comportement d’application facultatif pour l’utilisateur.
    
  **Prise en charge du partage de ressources intersession pour l’API du référentiel**
  
L’API du référentiel prend en charge le partage de ressources de traversée. CORS est une fonctionnalité HTTP qui permet à une application Web exécutée sous un domaine d’accéder aux ressources d’un autre domaine. Les navigateurs Web mettent en œuvre une restriction de sécurité connue sous le nom de stratégie de [même origine qui](https://www.w3.org/Security/wiki/Same_Origin_Policy) empêche une page Web d’appeler des API dans un domaine différent. CORS fournit un moyen sécurisé pour permettre à un domaine (domaine d’origine) d’appeler des API dans un autre domaine. Pour plus d’informations sur l’affichage de l’une des [caractéristiques](https://www.w3.org/TR/cors/) de cors.
  
 **Activation de CORS pour l’API du référentiel**
  
 Voici un extrait de l’API du référentiel Web. config, montrant deux domaines répertoriés dans les paramètres de l’application corsTrustedOrigin. Toutes les demandes effectuées par les scripts chargés à partir de ces serveurs sont approuvées par l’API du référentiel.
  
N’oubliez pas d’inclure le protocole, le nom d’hôte et le port exacts (le cas échéant). Ne placez aucun caractère barre oblique (/) à la fin. Plusieurs entrées peuvent être spécifiées en les séparant par des virgules.
  
```
<repositoryConfiguration>
    <service corsTrustedOrigin="https://<trusted-server>,http://<another-trusted-domain>:8080"" />
    <diagnostics eventLevel="Verbose" systemLoggedEventLevel="Error">
      <traceLog enabled="true" fileName="repository_trace.log" />
    </diagnostics>
 </repositoryConfiguration>
```


