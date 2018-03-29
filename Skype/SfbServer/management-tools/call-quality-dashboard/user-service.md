---
title: Service utilisateur pour CQD
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: abd5c828-42dd-4f48-bf87-29993193cb3a
description: 'Résumé : En savoir plus sur le Service de l’utilisateur, qui fait partie de l’API de référentiel pour appeler le tableau de bord qualité. Tableau de bord qualité appel est un outil de Skype pour Business Server 2015.'
ms.openlocfilehash: c4bb2395ea3fa4541140a7966bbfb554ef53c168
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="user-service-for-cqd"></a>Service utilisateur pour CQD
 
**Résumé :** Obtenir des informations sur le Service de l’utilisateur, qui fait partie de l’API de référentiel pour appeler le tableau de bord qualité. Tableau de bord qualité appel est un outil de Skype pour Business Server 2015.
  
Le Service de l’utilisateur est la partie de l’API de référentiel pour appeler le tableau de bord qualité.
  
## <a name="user-service"></a>Service de l’utilisateur

API de référentiel fournit un modèle de gestion d’utilisateur simplifiée où approvisionnement (création de comptes d’utilisateur) de l’utilisateur est automatique et implicite. Lorsqu’un utilisateur effectuer une requête par rapport à l’API de référentiel pour la première fois, le référentiel crée un nouvel enregistrement d’utilisateur. 
  
Appel de que tableau de bord qualité crée également automatiquement un utilisateur dédié des éléments pour le nouvel utilisateur. Les nouveaux éléments utilisateur dédiée sont des clones complètes d’éléments de l’utilisateur du système. De cette façon, les utilisateurs démarrent avec leurs propres copies des rapports et des requêtes qu’ils peuvent immédiatement commencer à personnaliser. 
  
> [!NOTE]
> À l’aide d’appeler le tableau de bord qualité, utilisateurs peuvent réinitialiser leurs éléments dédiés à tout moment. 
  
 **ID utilisateur spécial**
  
API de référentiel inclut d’autres API URIs qui attend un nombre entier pour spécifier un utilisateur particulier. Exemple : `https://<portal>/QoERepositoryService/repository/user/{userId}`. Ici, {ID utilisateur} doit être remplacé par une valeur entière, telle que 0, 1, etc..
  
En outre, les API de référentiel accepte deux ID utilisateur spécial à {ID} utilisateur URI.
  
-  *par défaut* - représente l’utilisateur qui est en train d’interagir avec l’API. Cela permet aux applications d’accéder à des matières de l’utilisateur actuel sans assurer le suivi de la valeur de l’ID réel de l’utilisateur. Exemple : ` https://<portal>/QoERepositoryService/repository/user/default`.
    
-  *système* - représente l’utilisateur du système. Cela permet aux applications d’accéder aux contenu de l’utilisateur sans connaître la valeur de l’ID réel de l’utilisateur. Exemple : `https://<portal>/QoERepositoryService/repository/user/system`.
    
Sauf mention contraire, les ID utilisateur spéciaux peuvent être utilisé à {utilisateur} dans les URI. 
  
Les opérations de repos sont incluses dans le tableau suivant.
  
|**Opération**|**Description**|
|:-----|:-----|
|[Obtenir les utilisateurs](get-users.md) <br/> |Retourne une liste d’utilisateurs dans le référentiel.  <br/> |
|[Obtenir l’utilisateur](get-user.md) <br/> |Retourne un enregistrement d’utilisateur.  <br/> |
   

