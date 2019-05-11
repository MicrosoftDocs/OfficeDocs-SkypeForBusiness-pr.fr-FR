---
title: Service utilisateur pour CQD
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: abd5c828-42dd-4f48-bf87-29993193cb3a
description: 'Résumé : En savoir plus sur le Service de l’utilisateur, qui fait partie de l’API de référentiel pour appeler le tableau de bord qualité. Tableau de bord de qualité des appels est un outil de Skype pour Business Server.'
ms.openlocfilehash: 631ccfefe7a4503f325c288ef1bf27d4366869e4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33915079"
---
# <a name="user-service-for-cqd"></a>Service utilisateur pour CQD
 
**Résumé :** Obtenir des informations sur le Service de l’utilisateur, qui fait partie de l’API de référentiel pour appeler le tableau de bord qualité. Tableau de bord de qualité des appels est un outil de Skype pour Business Server.
  
Le Service de l’utilisateur fait partie de l’API de référentiel pour appeler le tableau de bord qualité.
  
## <a name="user-service"></a>Service destiné aux utilisateurs

API de référentiel fournit un modèle de gestion simplifiée utilisateur où l’utilisateur (création de nouveaux comptes d’utilisateurs) de la mise en service est automatique et implicite. Lorsqu’un utilisateur effectuer une requête par rapport à l’API de référentiel pour la première fois, le référentiel crée un nouvel enregistrement d’utilisateur. 
  
Appel de que tableau de bord qualité crée automatiquement un utilisateur dédiée des éléments pour le nouvel utilisateur. Les nouveaux éléments utilisateur dédiée sont clones complètes d’éléments de l’utilisateur du système. Ainsi, les utilisateurs commencent avec leurs propres copies des rapports et des requêtes qu’ils peuvent démarrer immédiatement personnalisation. 
  
> [!NOTE]
> À l’aide du tableau de bord qualité des appels, les utilisateurs peuvent réinitialiser leurs éléments dédiés à tout moment. 
  
 **ID d’utilisateur spéciaux**
  
API de référentiel inclut URIs REST API qui attend une valeur entière pour spécifier un utilisateur particulier. Exemple : `https://<portal>/QoERepositoryService/repository/user/{userId}`. Ici, {userId} doit être remplacée par une valeur entière, telles que 0, 1, etc..
  
En outre, les API de référentiel accepte deux ID d’utilisateur spéciaux à {userId} dans les URI.
  
-  *par défaut* - représente l’utilisateur qui est en train d’interagir avec l’API. Cela permet aux applications d’accéder à contenu de l’utilisateur actuel sans suivi de la valeur d’ID réel de l’utilisateur. Exemple : ` https://<portal>/QoERepositoryService/repository/user/default`.
    
-  *système* - représente l’utilisateur du système. Cela permet aux applications d’accéder à contenu de l’utilisateur sans connaître la valeur d’ID réel de l’utilisateur. Exemple : `https://<portal>/QoERepositoryService/repository/user/system`.
    
Sauf indication contraire, les ID utilisateur spéciaux peuvent être utilisée à {userId} dans les URI. 
  
Les opérations REST sont incluses dans le tableau suivant.
  
|**Opération**|**Description**|
|:-----|:-----|
|[Obtenir les utilisateurs](get-users.md) <br/> |Renvoie une liste d’utilisateurs dans le référentiel.  <br/> |
|[Obtenir un utilisateur](get-user.md) <br/> |Renvoie un enregistrement d’utilisateur.  <br/> |
   

