---
title: Service utilisateur pour bord
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
ms.assetid: abd5c828-42dd-4f48-bf87-29993193cb3a
description: 'Résumé : Découvrez le service utilisateur, qui fait partie de l’API du référentiel pour le tableau de bord de qualité des appels. Le tableau de bord de qualité des appels est un outil pour Skype entreprise Server.'
ms.openlocfilehash: 439df99c1c9d66547e681fdea90b33c6295344db
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816653"
---
# <a name="user-service-for-cqd"></a>Service utilisateur pour bord
 
**Résumé :** Découvrez le service utilisateur, qui fait partie de l’API du référentiel pour le tableau de bord de qualité des appels. Le tableau de bord de qualité des appels est un outil pour Skype entreprise Server.
  
Le service d’utilisateur fait partie de l’API du référentiel pour le tableau de bord de qualité des appels.
  
## <a name="user-service"></a>Service destiné aux utilisateurs

L’API du référentiel fournit un modèle de gestion des utilisateurs simplifié dans lequel la mise en service des utilisateurs (création de nouveaux comptes d’utilisateur) est automatique et implicite. Lorsqu’un utilisateur effectue une demande concernant l’API du référentiel pour la première fois, le référentiel crée un nouvel enregistrement utilisateur. 
  
Le tableau de bord de qualité des appels crée automatiquement un élément dédié aux utilisateurs pour le nouvel utilisateur. Le nouvel utilisateur éléments dédiés sont des clones complète des éléments de l’utilisateur système. De cette façon, les utilisateurs commencent par leurs propres copies de rapports et de requêtes qu’ils peuvent lancer immédiatement. 
  
> [!NOTE]
> Le tableau de bord de qualité des appels permet aux utilisateurs de réinitialiser leurs éléments dédiés à tout moment. 
  
 **ID d’utilisateur spéciaux**
  
L’API du référentiel inclut des URI REST qui attendent une valeur entière pour spécifier un utilisateur particulier. Par exemple `https://<portal>/QoERepositoryService/repository/user/{userId}`:. Dans cet exemple, {Id_utilisateur} doit être remplacé par une valeur de type entier (par exemple, 0, 1, etc.).
  
Par ailleurs, l’API du référentiel accepte deux ID utilisateur spéciaux à la fois à l’adresse de l’URI.
  
-  *par défaut* : représente l’utilisateur qui interagit actuellement avec l’API. Cela permet aux applications d’accéder au contenu actuel de l’utilisateur sans suivre la valeur de l’IDENTIFIant utilisateur réel. Par exemple `https://<portal>/QoERepositoryService/repository/user/default`:.
    
-  *System* -correspond à l’utilisateur système. Cela permet aux applications d’accéder au contenu de l’utilisateur système sans connaître la valeur de l’IDENTIFIant utilisateur réel. Par exemple `https://<portal>/QoERepositoryService/repository/user/system`:.
    
Sauf indication contraire, il est possible d’utiliser les ID d’utilisateur spéciaux au niveau de {Id_utilisateur} dans les URI. 
  
Les opérations REST sont comprises dans le tableau suivant.
  
|**Opération**|**Description**|
|:-----|:-----|
|[Obtenir les utilisateurs](get-users.md) <br/> |Renvoie une liste des utilisateurs du référentiel.  <br/> |
|[Obtenir un utilisateur](get-user.md) <br/> |Renvoie un enregistrement utilisateur.  <br/> |
   

