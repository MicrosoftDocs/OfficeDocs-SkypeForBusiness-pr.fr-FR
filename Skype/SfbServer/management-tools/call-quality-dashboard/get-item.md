---
title: Obtenir l’élément
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: e77bf649-d62a-4d94-80de-066ba47730cd
description: 'Résumé : Découvrez l’opération obtenir l’élément, qui fait partie de l’article de Service. L’article de Service fait partie de l’API de référentiel pour appeler le tableau de bord qualité. Tableau de bord qualité appel est un outil de Skype pour Business Server 2015.'
ms.openlocfilehash: 6e4ba82c804937025b72da2d443c2a828d92d98a
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="get-item"></a>Obtenir l’élément
 
**Résumé :** Obtenir des informations sur l’opération obtenir l’élément, qui fait partie de l’article de Service. L’article de Service fait partie de l’API de référentiel pour appeler le tableau de bord qualité. Tableau de bord qualité appel est un outil de Skype pour Business Server 2015.
  
L’opération obtenir l’élément fait partie de l’article Service dans l’API de référentiel pour appeler le tableau de bord qualité.
  
## <a name="get-item"></a>Obtenir l’élément

Obtenir élément renvoie un élément spécifique dans le référentiel.
  
|**Méthode**|**URI de la demande**|**Version de HTTP**|
|:-----|:-----|:-----|
|Télécharger  <br/> |https://\<portal\>/QoERepositoryService/repository/article / {itemId}  <br/> |HTTP/1.1  <br/> |
   
 **Les paramètres URI** - None.
  
 **En-têtes de requête** - aucun en-tête supplémentaire.
  
 **Corps de requête** - None.
  
 **Réponse** : la réponse contient un code d’état HTTP et d’un ensemble d’en-têtes de réponse.
  
 **Code d’état** - une opération réussie retourne un code d’état 200 (OK). Si un ID de l’élément spécifié n’est pas trouvé, il renvoie le code d’état 404 (introuvable).
  
 **En-têtes de réponse** - aucun en-tête supplémentaire.
  
 **Corps de la réponse** - Voici une charge utile d’exemple réponse au format JSON.
  
```
{
"itemId": 1652,
"userId": 0,
"content": "{\"Title\":\"All Audio Streams\",...}",
"type": "application/json",
"subItemIds": [1653, 1710]
}

```

 *itemId* - ID de l’élément.
  
 *pseudo* - ID de l’utilisateur propriétaire de cet élément.
  
 *contenu* - le contenu spécifique à l’application.
  
 *type* - le type de contenu. Ce champ est défini par les applications.
  
 *subItemIds* - l’ID des sous-éléments, le cas échéant. Il s’agit d’un court-circuit d’opération obtenir des sous-éléments pour enregistrer un appel. Les applications peuvent également obtenir les mêmes informations à l’aide d’opération d’obtenir les éléments de sous-menu.
  

