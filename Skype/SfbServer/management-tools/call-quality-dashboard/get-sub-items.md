---
title: Obtenir des sous-éléments
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 0542eba9-3dda-40de-bba8-095d22825e4e
description: 'Résumé : Découvrez l’opération Get Sub-Items, qui fait partie du service d’élément. Le service d’élément fait partie de l’API de référentiel pour le tableau de bord de qualité des appels. Le Tableau de bord de qualité des appels est un outil pour Skype Entreprise Server.'
ms.openlocfilehash: 3d17ab46ece202ea36dce45b6266a1cd3de74928
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60774644"
---
# <a name="get-sub-items"></a>Obtenir des sous-éléments
 
**Résumé :** Découvrez l’opération Get Sub-Items, qui fait partie du service d’élément. Le service d’élément fait partie de l’API de référentiel pour le tableau de bord de qualité des appels. Le Tableau de bord de qualité des appels est un outil pour Skype Entreprise Server.
  
L’opération Get Sub-Items fait partie du service d’élément dans l’API référentiel pour le tableau de bord de qualité des appels.
  
## <a name="get-sub-items"></a>Obtenir des sous-éléments

Obtenir Sub-Items renvoie les sous-éléments d’un élément spécifique.
  

|**Méthode**|**URI de demande**|**HTTP Version**|
|:-----|:-----|:-----|
|GET  <br/> |https:// \<portal\> /QoERepositoryService/repository/item/{itemId}/eusem  <br/> |HTTP/1.1  <br/> |
   
 **Paramètres d’URI** - Aucun.
  
 **En-têtes de requête** : aucun en-tête supplémentaire.
  
 **Corps de la** demande - Aucun.
  
 **Réponse** : la réponse inclut un code d’état HTTP et un ensemble d’en-têtes de réponse.
  
 **Code d’état** : une opération réussie renvoie le code d’état 200 (OK). Si un ID utilisateur spécifié est in trouvé, il renvoie le code d’état 404 (In trouvé).
  
 **En-têtes de réponse** : aucun en-tête supplémentaire.
  
 **Corps de la** réponse : voici un exemple de charge utile de réponse dans JSON.
  
> [!NOTE]
> Un tableau d’objets Item est renvoyé. 
  
```json
[{
"itemId": 1653,
"userId": 0,
"type": "application/json"
},
{
"itemId": 1710,
"userId": 0,
"type": "json"
}]
```

L’objet Item renvoyé par Sub-Items opération contient uniquement les trois champs suivants. 
  
 *itemId*  - ID de l’élément.
  
 *userId*  - ID de l’utilisateur propriétaire de cet élément.
  
 *type*  : type du contenu. Ce champ est définie par les applications.
  
> [!NOTE]
>  `Content` et les champs ne sont pas inclus dans la réponse pour réduire la quantité de données `subItems` transmises sur le réseau.
  

