---
title: Obtenir des éléments
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 9e189a48-4944-4f93-88d7-9d56b56770a6
description: 'Résumé : Découvrez l’opération obtenir les éléments, qui fait partie de l’article de Service. L’article de Service fait partie de l’API de référentiel pour appeler le tableau de bord qualité. Tableau de bord qualité appel est un outil de Skype pour Business Server 2015.'
ms.openlocfilehash: 526d578d65ded98a6cd1a5cfc09a6749319683c3
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="get-items"></a>Obtenir des éléments
 
**Résumé :** Obtenir des informations sur l’opération obtenir les éléments, qui fait partie de l’article de Service. L’article de Service fait partie de l’API de référentiel pour appeler le tableau de bord qualité. Tableau de bord qualité appel est un outil de Skype pour Business Server 2015.
  
L’opération obtenir les éléments fait partie de l’article Service dans l’API de référentiel pour appeler le tableau de bord qualité.
  
## <a name="get-items"></a>Obtenir des éléments

Obtenir les éléments retourne tous les éléments dans le référentiel.
  
|**Méthode**|**URI de la demande**|**Version de HTTP**|
|:-----|:-----|:-----|
|Télécharger  <br/> |https://\<portal\>/QoERepositoryService/repository/item  <br/> |HTTP/1.1  <br/> |
   
 **Les paramètres URI** - None.
  
 **En-têtes de requête** - aucun en-tête supplémentaire.
  
 **Corps de requête** - None.
  
 **Réponse** : la réponse contient un code d’état HTTP et d’un ensemble d’en-têtes de réponse.
  
 **Code d’état** - une opération réussie retourne un code d’état 200 (OK).
  
 **En-têtes de réponse** - aucun en-tête supplémentaire.
  
 **Corps de la réponse** - Voici une charge utile d’exemple réponse au format JSON.
  
> [!NOTE]
> Un tableau d’objets d’élément est retourné. Pour plus d’informations sur l’objet de l’élément, consultez obtenir l’élément. 
  
```
[{
"itemId": 1652,
"userId": 0,
"type": "application/json"
},
{
"itemId": 1653,
"userId": 0,
"type": "application/json"
},
{
"itemId": 1654,
"userId": 0,
"type": "application/json"
}]

```


