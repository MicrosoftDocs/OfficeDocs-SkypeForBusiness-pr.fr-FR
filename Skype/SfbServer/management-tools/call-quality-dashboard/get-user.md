---
title: Obtenir un utilisateur
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
ms.assetid: 52b89a4b-a0bd-493d-bb5e-e21904eb8e48
description: 'Résumé : Découvrez l’opération Obtenir un utilisateur, qui fait partie du service utilisateur. Le service utilisateur fait partie de l’API référentiel pour le tableau de bord de qualité des appels. Le Tableau de bord de qualité des appels est un outil pour Skype Entreprise Server.'
ms.openlocfilehash: bb99ec52cb270bdef51eac65070c1f5204bb03b93c81dd46d31f86a2ffc3b836
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54311042"
---
# <a name="get-user"></a>Obtenir un utilisateur
 
**Résumé :** Découvrez l’opération Obtenir un utilisateur, qui fait partie du service utilisateur. Le service utilisateur fait partie de l’API référentiel pour le tableau de bord de qualité des appels. Le Tableau de bord de qualité des appels est un outil pour Skype Entreprise Server.
  
L’opération Obtenir des utilisateurs fait partie du service utilisateur dans l’API référentiel pour le tableau de bord de qualité des appels.
  
## <a name="get-user"></a>Obtenir un utilisateur

Get User renvoie un enregistrement utilisateur à partir du référentiel.
  
|**Méthode**|**URI de demande**|**HTTP Version**|
|:-----|:-----|:-----|
|GET  <br/> |https:// \<portal\> /QoERepositoryService/repository/user/{userId}  <br/> |HTTP/1.1  <br/> |
   
 **Paramètres d’URI** - Aucun.
  
 **En-têtes de requête** : aucun en-tête supplémentaire.
  
 **Corps de la** demande - Aucun.
  
 **Réponse** : la réponse inclut un code d’état HTTP et un ensemble d’en-têtes de réponse.
  
 **Code d’état** : une opération réussie renvoie le code d’état 200 (OK). Si un ID utilisateur spécifié est in trouvé, il renvoie le code d’état 404 (In trouvé).
  
 **En-têtes de réponse** : aucun en-tête supplémentaire.
  
 **Corps de la** réponse : voici un exemple de charge utile de réponse dans JSON.
  
```json
{
"userId": 0,
"loginName": "system",
"defaultItemId": 1655
}
```

 *userId*  : ID de l’utilisateur.
  
 *loginName*  : identification des utilisateurs externes pour les utilisateurs réguliers. Si Windows’authentification est utilisée pour authentifier les utilisateurs, il peut s’agit d’un nom de groupe de l’utilisateur.
  
 *defaultItemId*  - ID de l’élément par défaut pour cet utilisateur. L’élément par défaut est l’élément le plus haut associé à l’utilisateur. Tous les autres éléments dont cet utilisateur est propriétaire peuvent être accédés à partir de l’élément par défaut.
  
> [!NOTE]
> Fournissez  `defaultItemId` la valeur de l’opération Obtenir un élément pour récupérer les détails de l’élément par défaut.
  

