---
title: API de référentiel pour le tableau de bord (CQD) appel qualité dans Skype pour Business Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d53e990f-1c5f-46d1-9eb1-8396782c2753
description: 'Résumé : En savoir plus sur l’API de référentiel pour l’appel du tableau de bord qualité. Tableau de bord qualité appel est un outil de Skype pour Business Server 2015.'
ms.openlocfilehash: 0f84e3967bd4f78f8852dbcfed8ce5d59cbe4e8c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="repository-api-for-call-quality-dashboard-cqd-in-skype-for-business-server-2015"></a>API de référentiel pour le tableau de bord (CQD) appel qualité dans Skype pour Business Server 2015
 
**Résumé :** Obtenir des informations sur l’API de référentiel pour l’appel du tableau de bord qualité. Tableau de bord qualité appel est un outil de Skype pour Business Server 2015.
  
L’API de référentiel permet d’accéder par programmation pour appeler le tableau de bord qualité pour Skype pour Business Server 2015.
  
## <a name="repository-api-for-call-quality-dashboard"></a>API de référentiel pour le tableau de bord qualité appel

API de référentiel offre une interface d’accès de données de la base de données de référentiel. Le référentiel permet au contenu d’être organisées dans une structure d’arbre ou graphique tels que les utilisateurs peuvent regrouper les manières ayant un sens pour les utilisateurs. Le référentiel prend en charge les deux types généraux d’utilisateurs : utilisateur du système, qui est un utilisateur du référentiel intégré et les utilisateurs ordinaires qui représentent les utilisateurs autorisés du référentiel.
  
API de référentiel est composé de trois services généraux : 
  
- [Service utilisateur pour CQD](user-service.md) - pour l’accès à des utilisateurs.
    
- [Service de l’élément de tableau de bord qualité appeler (CQD)](item-service.md) - pour accéder aux éléments et le contenu stocké dans des éléments.
    
- [Service de paramètres utilisateur pour appeler qualité du tableau de bord (CQD)](user-settings-service.md) - pour l’accès aux paramètres de l’utilisateur.
    
Tableau de bord qualité appel utilise l’API de référentiel pour gérer les informations suivantes : 
  
- **Utilisateur** : représentation des utilisateurs qui ont accès au référentiel.
    
- **Rapport** - contient une liste de requêtes, stockées sous la forme d’un contenu d’éléments du référentiel.
    
- **Requête** - permet de récupérer des données à partir des API de données stockées sous la forme d’un contenu d’éléments d’un référentiel.
    
- Le **Paramètre utilisateur** - décrit un comportement d’application facultative pour l’utilisateur.
    
 **La prise en charge pour l’API de référentiel (CORS) le partage des ressources entre-origine**
  
Partage de ressources entre origine (CORS) prend en charge les API de référentiel. CORS est une fonctionnalité HTTP qui permet à une application web en cours d’exécution dans un domaine d’accéder aux ressources dans un autre domaine. Navigateurs Web implémentent une restriction de sécurité appelée stratégie de même origine [Stratégie de même origine](https://www.w3.org/Security/wiki/Same_Origin_Policy) qui empêche une page web à partir de l’appel d’API dans un autre domaine. CORS offre un moyen sécurisé pour permettre à un domaine (le domaine d’origine) appeler des API dans un autre domaine. Consultez la [spécification de CORS](https://www.w3.org/TR/cors/) pour plus de détails sur les CORS.
  
 **L’activation de CORS pour l’API de référentiel**
  
 Voici un extrait du fichier web.config de API de référentiel, montrant deux domaines répertoriés dans les paramètres de l’application corsTrustedOrigin. Toutes les demandes effectuées par les scripts chargés à partir de ces serveurs sont approuvés par les API de référentiel.
  
N’oubliez pas d’inclure le protocole exact, le nom d’hôte et le port (le cas échéant). Ne pas pour placer les oblique (/) de caractère à la fin. Plusieurs entrées peuvent être spécifiées en les séparant par des virgules.
  
```
<repositoryConfiguration>
    <service corsTrustedOrigin="https://<trusted-server>,http://<another-trusted-domain>:8080"" />
    <diagnostics eventLevel="Verbose" systemLoggedEventLevel="Error">
      <traceLog enabled="true" fileName="repository_trace.log" />
    </diagnostics>
 </repositoryConfiguration>

```


