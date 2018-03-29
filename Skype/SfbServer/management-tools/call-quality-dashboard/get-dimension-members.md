---
title: Obtenir les membres de Dimension
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bd89bbf7-cb98-4cd8-bbfa-0484663d14db
description: 'Résumé : Découvrez l’opération obtenir les membres de Dimension. L’opération obtenir les membres de Dimension fait partie de l’API de données pour appeler le tableau de bord qualité. Tableau de bord qualité appel est un outil de Skype pour Business Server 2015.'
ms.openlocfilehash: 6da1b8f6d93dc197df320f1fb5875a6269a9b45a
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="get-dimension-members"></a>Obtenir les membres de Dimension
 
**Résumé :** Obtenir des informations sur l’opération obtenir les membres de Dimension. L’opération obtenir les membres de Dimension fait partie de l’API de données pour appeler le tableau de bord qualité. Tableau de bord qualité appel est un outil de Skype pour Business Server 2015.
  
L’opération obtenir les membres de Dimension fait partie de l’API de données pour appeler le tableau de bord qualité.
  
## <a name="get-dimension-members"></a>Obtenir les membres de Dimension

Opération d’obtention de membres de Dimension renvoie la liste des membres d’une dimension spécifique. Cela donne aussi la possibilité de filtrer la liste des membres et obtenir un sous-ensemble, afin de réduire le coût de transfert de fil.
  

|**Méthode**|**URI de la demande**|**Version de HTTP**|
|:-----|:-----|:-----|
|Publier  <br/> |https://\<portal\>/QoEDataService/DimensionMembers  <br/> |HTTP/1.1  <br/> |
   
 **Les paramètres URI** - None.
  
 **En-têtes de requête** - aucun en-tête supplémentaire.
  
 **Corps de la demande** - cela contient le nom de dimension, nous souhaitons que les membres de. Également un nombre maximal de membres retournés, à côté de vous pouvez spécifier un filtrage pour limiter les membres renvoyés.
  
```
{
"ByPassCache": false,
"DataModelName": "[StartDate].[Month]",
"SearchCaption": "",
"SearchValue": "",
"PageNumber": 0,
"PageSize": 8000
}

```

 **Réponse** : la réponse contient un code d’état HTTP et d’un ensemble d’en-têtes de réponse.
  
 **Code d’état** - une opération réussie retourne un code d’état 200 (OK).
  
 **En-têtes de réponse** - aucun en-tête supplémentaire.
  
 **Corps de la réponse** - vous trouverez ci-dessous une exemple charge utile de réponse au format JSON en réponse à une demande de « [DateDébut]. [Mois] » dimension.
  
> [!NOTE]
> La liste affiche uniquement une petite partie de la liste. 
  
```
{
"MembersCount": 493,
"Members": [["[1990-01-01T00:00:00]",
"January 1990"],
["[1990-02-01T00:00:00]",
"February 1990"],
["[1990-03-01T00:00:00]",
"March 1990"],
 
    ...
    
["[2030-10-01T00:00:00]",
"October 2030"],
["[2030-11-01T00:00:00]",
"November 2030"],
["[2030-12-01T00:00:00]",
"December 2030"],
["[2031-01-01T00:00:00]",
"January 2031"]]
}

```


