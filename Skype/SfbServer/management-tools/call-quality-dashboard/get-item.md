---
title: Obtenir l’élément
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: e77bf649-d62a-4d94-80de-066ba47730cd
description: 'Résumé : Découvrez l’opération Obtenir un élément, qui fait partie du service d’élément. Le service d’élément fait partie de l’API de référentiel pour le tableau de bord de qualité des appels. Le Tableau de bord de qualité des appels est un outil pour Skype Entreprise Server.'
ms.openlocfilehash: c99e848860d12b77a13dbf453298dc697cd2a665
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62390986"
---
# <a name="get-item"></a>Obtenir l’élément
 
**Résumé :** Découvrez l’opération Obtenir un élément, qui fait partie du service d’élément. Le service d’élément fait partie de l’API de référentiel pour le tableau de bord de qualité des appels. Le Tableau de bord de qualité des appels est un outil pour Skype Entreprise Server.
  
L’opération Obtenir un élément fait partie du service d’élément dans l’API référentiel pour le tableau de bord de qualité des appels.
  
## <a name="get-item"></a>Obtenir l’élément

Obtenir l’élément renvoie un élément spécifique dans le référentiel.
  
|**Méthode**|**URI de demande**|**HTTP Version**|
|:-----|:-----|:-----|
|GET  <br/> |\<portal\>https:///QoERepositoryService/repository/item/{itemId}  <br/> |HTTP/1.1  <br/> |
   
 **Paramètres d’URI** - Aucun.
  
 **En-têtes de requête** : aucun en-tête supplémentaire.
  
 **Corps de la** demande - Aucun.
  
 **Réponse** : la réponse inclut un code d’état HTTP et un ensemble d’en-têtes de réponse.
  
 **Code d’état** : une opération réussie renvoie le code d’état 200 (OK). Si un ID d’élément spécifié est in trouvé, il renvoie le code d’état 404 (In trouvé).
  
 **En-têtes de réponse** : aucun en-tête supplémentaire.
  
 **Corps de la** réponse : voici un exemple de charge utile de réponse dans JSON.
  
```json
{
"itemId": 1652,
"userId": 0,
"content": "{\"Title\":\"All Audio Streams\",...}",
"type": "application/json",
"subItemIds": [1653, 1710]
}
```

 *itemId*  - ID de l’élément.
  
 *userId*  : ID de l’utilisateur propriétaire de cet élément.
  
 *contenu*  - Contenu propre à l’application.
  
 *type*  : type du contenu. Ce champ est définie par les applications.
  
 *subItemIds*  : ID des sous-éléments, le cas cas. Il s’agit d’un court-circuit de l’opération Get Sub-Items pour enregistrer un appel. Les applications peuvent également obtenir les mêmes informations à l’aide de l’opération Get Sub-Items.
  

