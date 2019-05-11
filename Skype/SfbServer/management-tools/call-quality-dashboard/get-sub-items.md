---
title: Obtenir des sous-éléments
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 0542eba9-3dda-40de-bba8-095d22825e4e
description: 'Résumé : Découvrez l’opération obtenir les sous-éléments, qui fait partie du Service de l’élément. Le Service de l’élément fait partie de l’API de référentiel pour appeler le tableau de bord qualité. Tableau de bord de qualité des appels est un outil de Skype pour Business Server.'
ms.openlocfilehash: 4d0e5c19a4bfb5d66db95738cab5b0c2eaf33985
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930678"
---
# <a name="get-sub-items"></a>Obtenir des sous-éléments
 
**Résumé :** Obtenir des informations sur l’opération obtenir les sous-éléments, qui fait partie du Service de l’élément. Le Service de l’élément fait partie de l’API de référentiel pour appeler le tableau de bord qualité. Tableau de bord de qualité des appels est un outil de Skype pour Business Server.
  
L’opération obtenir les sous-éléments fait partie du Service d’élément dans l’API de référentiel pour appeler le tableau de bord qualité.
  
## <a name="get-sub-items"></a>Obtenir des sous-éléments

Obtenez les sous-éléments renvoie les sous-éléments d’un élément spécifique.
  

|**Méthode**|**URI de la demande**|**Version HTTP**|
|:-----|:-----|:-----|
|Avoir  <br/> |https://\<portal\>/QoERepositoryService/référentiel/élément / {itemId} / sous-éléments  <br/> |HTTP/1.1.  <br/> |
   
 **Paramètres d’URI** - None.
  
 **En-têtes de demande** - aucun en-tête supplémentaire.
  
 **Corps de requête** - None.
  
 **Réponse** - la réponse inclut un code d’état HTTP et un ensemble d’en-têtes de réponse.
  
 **Code d’état** - une opération réussie retourne un code d’état 200 (OK). Si un utilisateur spécifié QU'ID est introuvable, elle renvoie le code d’état 404 (introuvable).
  
 **En-têtes de réponse** - aucun en-tête supplémentaire.
  
 **Corps de réponse** - vous trouverez ci-dessous une charge utile d’exemple réponse au format JSON.
  
> [!NOTE]
> Un tableau de l’objet Item est renvoyé. 
  
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

L’objet renvoyé par opération sous-éléments contient uniquement les trois champs suivants. 
  
 *itemId* - ID de l’élément.
  
 *userId* - ID de l’utilisateur qui possède cet article.
  
 *type* : le type de contenu. Ce champ est défini par les applications.
  
> [!NOTE]
>  `Content`et `subItems` champs ne sont pas inclus dans la réponse afin de réduire la quantité de données transmises via le réseau.
  

