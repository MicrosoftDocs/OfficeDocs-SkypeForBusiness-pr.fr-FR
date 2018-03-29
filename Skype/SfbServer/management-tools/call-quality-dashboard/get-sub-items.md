---
title: Obtenir des éléments de sous-menu
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 0542eba9-3dda-40de-bba8-095d22825e4e
description: 'Résumé : Découvrez l’opération obtenir les éléments de sous-menu, qui fait partie de l’article de Service. L’article de Service fait partie de l’API de référentiel pour appeler le tableau de bord qualité. Tableau de bord qualité appel est un outil de Skype pour Business Server 2015.'
ms.openlocfilehash: 8b9ec0c1c849e22f285ef1b5bbb2db806a153b76
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="get-sub-items"></a>Obtenir des éléments de sous-menu
 
**Résumé :** Obtenir des informations sur l’opération obtenir les éléments de sous-menu, qui fait partie de l’article de Service. L’article de Service fait partie de l’API de référentiel pour appeler le tableau de bord qualité. Tableau de bord qualité appel est un outil de Skype pour Business Server 2015.
  
L’opération obtenir les sous-éléments fait partie de l’article Service dans l’API de référentiel pour appeler le tableau de bord qualité.
  
## <a name="get-sub-items"></a>Obtenir des éléments de sous-menu

Obtenir les sous-éléments retourne les sous-éléments d’un élément spécifique.
  

|**Méthode**|**URI de la demande**|**Version de HTTP**|
|:-----|:-----|:-----|
|Télécharger  <br/> |https://\<portal\>/QoERepositoryService/repository/article / {itemId} / de sous-éléments  <br/> |HTTP/1.1  <br/> |
   
 **Les paramètres URI** - None.
  
 **En-têtes de requête** - aucun en-tête supplémentaire.
  
 **Corps de requête** - None.
  
 **Réponse** : la réponse contient un code d’état HTTP et d’un ensemble d’en-têtes de réponse.
  
 **Code d’état** - une opération réussie retourne un code d’état 200 (OK). Si un utilisateur spécifié QU'ID n’est pas trouvé, il renvoie le code d’état 404 (introuvable).
  
 **En-têtes de réponse** - aucun en-tête supplémentaire.
  
 **Corps de la réponse** - Voici une charge utile d’exemple réponse au format JSON.
  
> [!NOTE]
> Un tableau d’élément objet est retourné. 
  
```
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

L’objet retourné par l’opération de sous-éléments ne contient que les trois champs suivants. 
  
 *itemId* - ID de l’élément.
  
 *pseudo* - ID de l’utilisateur propriétaire de cet élément.
  
 *type* - le type de contenu. Ce champ est défini par les applications.
  
> [!NOTE]
>  `Content`et `subItems` champs ne sont pas inclus dans la réponse afin de réduire la quantité de données transmises sur le réseau.
  

