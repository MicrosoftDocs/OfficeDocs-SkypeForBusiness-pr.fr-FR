---
title: Élément de mise à jour
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 6/8/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b1c15c56-cdae-4f3e-838a-52f0940cf729
description: 'Résumé : Découvrez l’opération de l’élément de mise à jour, qui fait partie de l’article de Service. L’article de Service fait partie de l’API de référentiel pour appeler le tableau de bord qualité. Tableau de bord qualité appel est un outil de Skype pour Business Server 2015.'
ms.openlocfilehash: 04a0ebf29537bbc2e62e6d5b35008fe9e329ab4f
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="update-item"></a>Élément de mise à jour
 
**Résumé :** Obtenir des informations sur l’opération de l’élément de mise à jour, qui fait partie de l’article de Service. L’article de Service fait partie de l’API de référentiel pour appeler le tableau de bord qualité. Tableau de bord qualité appel est un outil de Skype pour Business Server 2015.
  
L’opération de l’élément de mise à jour fait partie de l’article Service dans l’API de référentiel pour appeler le tableau de bord qualité.
  
## <a name="update-item"></a>Élément de mise à jour

Élément de mise à jour met à jour un élément spécifique dans le référentiel.
  

|**Méthode**|**URI de la demande**|**Version de HTTP**|
|:-----|:-----|:-----|
|PUT  <br/> |https://\<portal\>/QoERepositoryService/repository/article / {itemId}  <br/> |HTTP/1.1  <br/> |
   
 **Les paramètres URI** - None.
  
 **En-têtes de requête** -Content-Type : application/json.
  
 **Corps de requête** - JSON.
  
Charge utile de demande exemple :
  
```
{
  content : "{ 'Product' : 'New Product Name'",
  type: "application/json"
}
```

 *contenu*  JSON mis en forme les données à stocker en tant que le nouveau contenu d’un élément de sous-menu existant. Techniquement, un référentiel peut stocker n’importe quel contenu de n’importe quel schéma, mais lorsqu’il est utilisé pour appeler le tableau de bord qualité, il doit être une requête ou un état. *type de*  Spécifiez toujours « application/json » pour appeler le tableau de bord qualité.
  
 **Réponse** : la réponse contient un code d’état HTTP et d’un ensemble d’en-têtes de réponse.
  
 **Code d’état** - une opération réussie retourne un code d’état 204 (sans contenu). Si un ID de l’élément spécifié n’est pas trouvé, il renvoie le code d’état 404 (introuvable).
  
> [!IMPORTANT]
> « Aucun contenu » n’est pas un état d’erreur. Cela signifie qu’une réponse n’a pas renvoyé quoi que ce soit dans le corps (à l’inverse, les contenus de 200 renvoie OK dans le corps). Il indique que l’élément a été correctement mis à jour. 
  
 **En-têtes de réponse** - None.
  
 **Corps de la réponse** - None.
  

