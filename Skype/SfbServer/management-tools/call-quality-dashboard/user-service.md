---
title: Service utilisateur pour le CQD
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
ms.assetid: abd5c828-42dd-4f48-bf87-29993193cb3a
description: 'Résumé : Découvrez le service utilisateur, qui fait partie de l’API référentiel pour le tableau de bord de qualité des appels. Le Tableau de bord de qualité des appels est un outil pour Skype Entreprise Server.'
ms.openlocfilehash: e8be18304cad02e1ed39cf84327a58f84d134c6d
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60851007"
---
# <a name="user-service-for-cqd"></a>Service utilisateur pour le CQD
 
**Résumé :** Découvrez le service utilisateur, qui fait partie de l’API référentiel pour le tableau de bord de qualité des appels. Le Tableau de bord de qualité des appels est un outil pour Skype Entreprise Server.
  
Le service utilisateur fait partie de l’API référentiel pour le tableau de bord de qualité des appels.
  
## <a name="user-service"></a>Service destiné aux utilisateurs

L’API de référentiel fournit un modèle de gestion des utilisateurs simplifié dans lequel la mise en service des utilisateurs (création de comptes d’utilisateurs) est automatique et implicite. Lorsqu’un utilisateur fait une demande par rapport à l’API du référentiel pour la première fois, le référentiel crée un nouvel enregistrement d’utilisateur. 
  
Le Tableau de bord de qualité des appels crée également automatiquement des éléments dédiés par l’utilisateur pour le nouvel utilisateur. Les nouveaux éléments dédiés aux utilisateurs sont des clones complets des éléments de l’utilisateur système. Ainsi, les utilisateurs commencent par leurs propres copies de rapports et de requêtes qu’ils peuvent immédiatement personnaliser. 
  
> [!NOTE]
> À l’aide du Tableau de bord de qualité des appels, les utilisateurs peuvent réinitialiser leurs éléments dédiés à tout moment. 
  
 **ID d’utilisateur spéciaux**
  
L’API de référentiel inclut les URIs d’API REST qui s’attendent à ce qu’une valeur d’ensemble spécifie un utilisateur particulier. Exemple :  `https://<portal>/QoERepositoryService/repository/user/{userId}` . Ici, {userId} doit être remplacé par une valeur de type 0, 1, etc.
  
En outre, l’API de référentiel accepte deux ID d’utilisateur spéciaux sur {userId} dans les UR.
  
-  *par*  défaut : représente l’utilisateur qui interagit actuellement avec l’API. Cela permet aux applications d’accéder au contenu de l’utilisateur actuel sans suivre la valeur réelle de l’ID utilisateur. Exemple : `https://<portal>/QoERepositoryService/repository/user/default`.
    
-  *system*  - représente l’utilisateur système. Cela permet aux applications d’accéder au contenu de l’utilisateur système sans connaître la valeur réelle de l’ID utilisateur. Exemple : `https://<portal>/QoERepositoryService/repository/user/system`.
    
Sauf indication contraire, les ID d’utilisateur spéciaux peuvent être utilisés à l’adresse {userId} dans les UR. 
  
Les opérations REST sont incluses dans le tableau suivant.
  
|**Opération**|**Description**|
|:-----|:-----|
|[Obtenir les utilisateurs](get-users.md) <br/> |Renvoie une liste d’utilisateurs dans le référentiel.  <br/> |
|[Obtenir un utilisateur](get-user.md) <br/> |Renvoie un enregistrement utilisateur.  <br/> |
   

