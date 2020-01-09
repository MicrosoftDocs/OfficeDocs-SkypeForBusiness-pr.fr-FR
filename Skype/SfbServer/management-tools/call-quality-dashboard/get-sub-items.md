---
title: Obtenir des sous-éléments
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 0542eba9-3dda-40de-bba8-095d22825e4e
description: 'Résumé : Découvrez l’opération obtenir les sous-éléments, qui fait partie du service d’éléments. Le service d’élément fait partie de l’API du référentiel pour le tableau de bord de qualité des appels. Le tableau de bord de qualité des appels est un outil pour Skype entreprise Server.'
ms.openlocfilehash: 75fc4fcd331925c224d8dfb72c681d25e3485eb6
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992651"
---
# <a name="get-sub-items"></a>Obtenir des sous-éléments
 
**Résumé :** En savoir plus sur l’opération obtenir les sous-éléments, qui fait partie du service d’élément. Le service d’élément fait partie de l’API du référentiel pour le tableau de bord de qualité des appels. Le tableau de bord de qualité des appels est un outil pour Skype entreprise Server.
  
L’opération obtenir des sous-éléments fait partie du service d’élément dans l’API du référentiel pour le tableau de bord de qualité des appels.
  
## <a name="get-sub-items"></a>Obtenir des sous-éléments

L’option obtenir des sous-éléments renvoie les sous-éléments d’un élément spécifiques.
  

|**Méthode**|**URI de la requête**|**Version HTTP**|
|:-----|:-----|:-----|
|Télécharger  <br/> |https://\<Portal\>/QoERepositoryService/Repository/Item/{ItemId}/SubItem  <br/> |HTTP/1.1  <br/> |
   
 **Paramètres d’URI** -aucun.
  
 **En-têtes de requête** -aucun en-tête supplémentaire.
  
 Le corps de la **requête** .
  
 **Réponse** : la réponse comprend un code d’État http et un ensemble d’en-têtes de réponse.
  
 **Code d’État** -une opération réussie renvoie le code d’état 200 (OK). Si vous n’avez pas trouvé d’ID utilisateur spécifié, le code d’État 404 (introuvable) est renvoyé.
  
 **En-têtes de réponse** : aucun en-tête supplémentaire.
  
 Le corps de la **réponse** : Voici un exemple de charge utile de réponse dans JSON.
  
> [!NOTE]
> Un tableau d’objet Item est retourné. 
  
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

L’objet Item renvoyé par une opération de sous-éléments contient uniquement les trois champs suivants. 
  
 ID *de l'* élément.
  
 ID *d’utilisateur de* l’utilisateur propriétaire de cet élément.
  
 *tapez* le type du contenu. Ce champ est défini par les applications.
  
> [!NOTE]
>  `Content`et `subItems` les champs ne sont pas inclus dans la réponse afin de réduire la quantité de données transmises sur le réseau.
  

