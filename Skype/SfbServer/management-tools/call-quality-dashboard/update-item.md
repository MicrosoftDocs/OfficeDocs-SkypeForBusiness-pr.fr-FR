---
title: Élément de la mise à jour
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 6/8/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b1c15c56-cdae-4f3e-838a-52f0940cf729
description: 'Résumé : Découvrez l’opération élément mise à jour, qui fait partie du Service de l’élément. Le Service de l’élément fait partie de l’API de référentiel pour appeler le tableau de bord qualité. Tableau de bord de qualité des appels est un outil de Skype pour Business Server 2015.'
ms.openlocfilehash: 0616f41a3ae680412bdc435716d805af77e72f3a
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/13/2018
ms.locfileid: "26295265"
---
# <a name="update-item"></a>Élément de la mise à jour
 
**Résumé :** Obtenir des informations sur l’opération élément mise à jour, qui fait partie du Service de l’élément. Le Service de l’élément fait partie de l’API de référentiel pour appeler le tableau de bord qualité. Tableau de bord de qualité des appels est un outil de Skype pour Business Server 2015.
  
L’opération de mise à jour élément fait partie du Service d’élément dans l’API de référentiel pour appeler le tableau de bord qualité.
  
## <a name="update-item"></a>Élément de la mise à jour

Élément de la mise à jour met à jour un élément spécifique dans le référentiel.
  

|**Méthode**|**URI de la demande**|**Version HTTP**|
|:-----|:-----|:-----|
|PUT  <br/> |https://\<portal\>/QoERepositoryService/référentiel/élément / {itemId}  <br/> |HTTP/1.1.  <br/> |
   
 **Paramètres d’URI** - None.
  
 **En-têtes de demande** -Content-Type : application/json.
  
 **Corps de requête** - JSON.
  
Charge utile de demande exemple :
  
```
{
  content : "{ 'Product' : 'New Product Name'",
  type: "application/json"
}
```

 *contenu*  JSON mise en forme des données sont stockées en tant que le nouveau contenu d’un élément existant de sous-sites. Techniquement, un référentiel peut stocker le contenu d’un schéma, mais lorsqu’il est utilisé pour appeler le tableau de bord qualité, il doit être un rapport ou une requête. *type*  Toujours spécifier « application/json » pour appeler le tableau de bord qualité.
  
 **Réponse** - la réponse inclut un code d’état HTTP et un ensemble d’en-têtes de réponse.
  
 **Code d’état** - une opération réussie renvoie le code d’état 204 (sans contenu). Si un ID de l’élément spécifié est introuvable, elle renvoie le code d’état 404 (introuvable).
  
> [!IMPORTANT]
> « Aucun contenu » n’est pas un état d’erreur. Cela signifie qu’une réponse n’a pas renvoyé rien dans le corps (à l’inverse, 200 renvoie OK contenus dans le corps). Il indique que l’élément a été correctement mis à jour. 
  
 **En-têtes de réponse** - None.
  
 **Corps de réponse** - None.
  

