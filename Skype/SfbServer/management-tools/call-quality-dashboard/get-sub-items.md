---
title: Obtenir les sous-éléments
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
description: 'Résumé : Découvrez l’opération obtenir les sous-éléments, qui fait partie du Service de l’élément. Le Service de l’élément fait partie de l’API de référentiel pour appeler le tableau de bord qualité. Tableau de bord de qualité des appels est un outil de Skype pour Business Server 2015.'
ms.openlocfilehash: f125a10ac9d3f608216ea23d17f614d0bff88af7
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/13/2018
ms.locfileid: "26295938"
---
# <a name="get-sub-items"></a>Obtenir les sous-éléments
 
**Résumé :** Obtenir des informations sur l’opération obtenir les sous-éléments, qui fait partie du Service de l’élément. Le Service de l’élément fait partie de l’API de référentiel pour appeler le tableau de bord qualité. Tableau de bord de qualité des appels est un outil de Skype pour Business Server 2015.
  
L’opération obtenir les sous-éléments fait partie du Service d’élément dans l’API de référentiel pour appeler le tableau de bord qualité.
  
## <a name="get-sub-items"></a>Obtenir les sous-éléments

Obtenez les sous-éléments renvoie les sous-éléments d’un élément spécifique.
  

|**Méthode**|**URI de la demande**|**Version HTTP**|
|:-----|:-----|:-----|
|Télécharger  <br/> |https://\<portal\>/QoERepositoryService/référentiel/élément / {itemId} / sous-éléments  <br/> |HTTP/1.1.  <br/> |
   
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
  

