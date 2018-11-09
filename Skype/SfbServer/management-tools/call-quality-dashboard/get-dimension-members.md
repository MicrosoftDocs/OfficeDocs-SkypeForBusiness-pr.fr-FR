---
title: Obtenir les membres de Dimension
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bd89bbf7-cb98-4cd8-bbfa-0484663d14db
description: 'Résumé : Découvrez l’opération obtenir les membres de Dimension. L’opération obtenir les membres de Dimension fait partie de l’API de données pour le tableau de bord qualité des appels. Tableau de bord de qualité des appels est un outil de Skype pour Business Server.'
ms.openlocfilehash: 4c53e809d13b1ceb386c6727805402be9dfaf7f8
ms.sourcegitcommit: b680505c5dad435d98fbd0b235e0e7c67b9d8c9c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/07/2018
ms.locfileid: "26035665"
---
# <a name="get-dimension-members"></a>Obtenir les membres de Dimension
 
**Résumé :** Obtenir des informations sur l’opération obtenir les membres de Dimension. L’opération obtenir les membres de Dimension fait partie de l’API de données pour le tableau de bord qualité des appels. Tableau de bord de qualité des appels est un outil de Skype pour Business Server.
  
L’opération obtenir les membres de Dimension fait partie de l’API de données pour le tableau de bord qualité des appels.
  
## <a name="get-dimension-members"></a>Obtenir les membres de Dimension

Opération de membres de Dimension Get renvoie la liste des membres d’une dimension spécifique. Cela donne aussi la possibilité de filtrer la liste des membres et obtenir un sous-ensemble, afin de réduire le coût de transfert filaire.
  

|**Méthode**|**URI de la demande**|**Version HTTP**|
|:-----|:-----|:-----|
|Publier  <br/> |https://\<portal\>/QoEDataService/DimensionMembers  <br/> |HTTP/1.1.  <br/> |
   
 **Paramètres d’URI** - None.
  
 **En-têtes de demande** - aucun en-tête supplémentaire.
  
 **Corps de demande** - il contient le nom de nous voulons les membres de dimension. Nombre maximal de membres renvoyés, situé en regard de vous pouvez également spécifier une partie du filtrage pour limiter les membres renvoyés.
  
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

 **Réponse** - la réponse inclut un code d’état HTTP et un ensemble d’en-têtes de réponse.
  
 **Code d’état** - une opération réussie retourne un code d’état 200 (OK).
  
 **En-têtes de réponse** - aucun en-tête supplémentaire.
  
 **Corps de réponse** - Voici une exemple charge utile de réponse dans JSON en réponse à une demande de « [StartDate]. [Mois] » dimension.
  
> [!NOTE]
> La liste est visible uniquement une petite partie de la liste. 
  
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