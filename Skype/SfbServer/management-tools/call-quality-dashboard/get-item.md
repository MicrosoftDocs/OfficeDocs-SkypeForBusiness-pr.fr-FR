---
title: Obtenir un élément
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: e77bf649-d62a-4d94-80de-066ba47730cd
description: 'Résumé : en savoir plus sur l’opération obtenir un élément qui fait partie du service d’article. Le service d’élément fait partie de l’API du référentiel pour le tableau de bord de qualité des appels. Le tableau de bord de qualité des appels est un outil pour Skype entreprise Server.'
ms.openlocfilehash: 208ad3d1852ab58b7fcd0d01eeb440097328f733
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992671"
---
# <a name="get-item"></a>Obtenir un élément
 
**Résumé :** En savoir plus sur l’opération obtenir l’élément, qui fait partie du service d’élément. Le service d’élément fait partie de l’API du référentiel pour le tableau de bord de qualité des appels. Le tableau de bord de qualité des appels est un outil pour Skype entreprise Server.
  
L’opération obtenir l’élément fait partie du service d’élément dans l’API du référentiel pour le tableau de bord de qualité des appels.
  
## <a name="get-item"></a>Obtenir un élément

Obtient l’élément renvoie un élément spécifique du référentiel.
  
|**Méthode**|**URI de la requête**|**Version HTTP**|
|:-----|:-----|:-----|
|Télécharger  <br/> |https://\<Portal\>/QoERepositoryService/Repository/Item/{ItemId}  <br/> |HTTP/1.1  <br/> |
   
 **Paramètres d’URI** -aucun.
  
 **En-têtes de requête** -aucun en-tête supplémentaire.
  
 Le corps de la **requête** .
  
 **Réponse** : la réponse comprend un code d’État http et un ensemble d’en-têtes de réponse.
  
 **Code d’État** -une opération réussie renvoie le code d’état 200 (OK). Si aucun ID d’élément spécifié n’est trouvé, il renvoie le code d’État 404 (introuvable).
  
 **En-têtes de réponse** : aucun en-tête supplémentaire.
  
 Le corps de la **réponse** : Voici un exemple de charge utile de réponse dans JSON.
  
```json
{
"itemId": 1652,
"userId": 0,
"content": "{\"Title\":\"All Audio Streams\",...}",
"type": "application/json",
"subItemIds": [1653, 1710]
}
```

 ID *de l'* élément.
  
 ID *d’utilisateur de* l’utilisateur propriétaire de cet élément.
  
 *content* : contenu spécifique à l’application.
  
 *tapez* le type du contenu. Ce champ est défini par les applications.
  
 *subItemIds* -ID des sous-éléments, le cas échéant. Il s’agit d’un court-circuit d’opération de commande de sous-éléments permettant d’enregistrer un appel. Les applications peuvent également obtenir les mêmes informations à l’aide de l’opération utiliser les sous-éléments.
  

