---
title: Obtenir un élément
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: e77bf649-d62a-4d94-80de-066ba47730cd
description: 'Résumé : Découvrez l’opération obtenir un élément, qui fait partie du Service de l’élément. Le Service de l’élément fait partie de l’API de référentiel pour appeler le tableau de bord qualité. Tableau de bord de qualité des appels est un outil de Skype pour Business Server.'
ms.openlocfilehash: 1f86c318139d328f414bf1290c66ddd7ccb7e20a
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32222694"
---
# <a name="get-item"></a>Obtenir un élément
 
**Résumé :** Obtenir des informations sur l’opération obtenir un élément, qui fait partie du Service de l’élément. Le Service de l’élément fait partie de l’API de référentiel pour appeler le tableau de bord qualité. Tableau de bord de qualité des appels est un outil de Skype pour Business Server.
  
L’opération obtenir un élément fait partie du Service d’élément dans l’API de référentiel pour appeler le tableau de bord qualité.
  
## <a name="get-item"></a>Obtenir un élément

Obtenir élément renvoie un élément spécifique dans le référentiel.
  
|**Méthode**|**URI de la demande**|**Version HTTP**|
|:-----|:-----|:-----|
|Avoir  <br/> |https://\<portal\>/QoERepositoryService/référentiel/élément / {itemId}  <br/> |HTTP/1.1.  <br/> |
   
 **Paramètres d’URI** - None.
  
 **En-têtes de demande** - aucun en-tête supplémentaire.
  
 **Corps de requête** - None.
  
 **Réponse** - la réponse inclut un code d’état HTTP et un ensemble d’en-têtes de réponse.
  
 **Code d’état** - une opération réussie retourne un code d’état 200 (OK). Si un ID de l’élément spécifié est introuvable, elle renvoie le code d’état 404 (introuvable).
  
 **En-têtes de réponse** - aucun en-tête supplémentaire.
  
 **Corps de réponse** - vous trouverez ci-dessous une charge utile d’exemple réponse au format JSON.
  
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
  
 *userId* - ID de l’utilisateur qui possède cet article.
  
 *contenu* - le contenu spécifique à l’application.
  
 *type* : le type de contenu. Ce champ est défini par les applications.
  
 *subItemIds* - identifiants des sous-éléments, le cas échéant. Il s’agit d’un court-circuit d’opération obtenir les sous-éléments pour enregistrer un appel. Les applications peuvent également obtenir les mêmes informations à l’aide d’opération obtenir les sous-éléments.
  

