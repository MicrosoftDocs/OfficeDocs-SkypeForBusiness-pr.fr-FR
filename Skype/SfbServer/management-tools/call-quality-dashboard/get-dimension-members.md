---
title: Obtenir les membres de dimension
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bd89bbf7-cb98-4cd8-bbfa-0484663d14db
description: 'Résumé : en savoir plus sur l’opération obtenir les membres d’une dimension. L’opération obtenir les membres de la dimension fait partie de l’API de données du tableau de bord de qualité des appels. Le tableau de bord de qualité des appels est un outil pour Skype entreprise Server.'
ms.openlocfilehash: 40e5ac8b95c24c3a8cb759da99f7d7aeaa391576
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888813"
---
# <a name="get-dimension-members"></a>Obtenir les membres de dimension
 
**Résumé :** En savoir plus sur l’opération obtenir les membres d’une dimension. L’opération obtenir les membres de la dimension fait partie de l’API de données du tableau de bord de qualité des appels. Le tableau de bord de qualité des appels est un outil pour Skype entreprise Server.
  
L’opération obtenir les membres de la dimension fait partie de l’API de données du tableau de bord de qualité des appels.
  
## <a name="get-dimension-members"></a>Obtenir les membres de dimension

Opération obtenir les membres d’une dimension renvoie la liste des membres d’une dimension spécifique. Vous pouvez également filtrer la liste des membres et obtenir un sous-ensemble afin de réduire le coût de transfert bancaire.
  

|**Méthode**|**URI de la requête**|**Version HTTP**|
|:-----|:-----|:-----|
|Publier  <br/> |https://\<Portal\>/QoEDataService/DimensionMembers  <br/> |HTTP/1.1  <br/> |
   
 **Paramètres d’URI** -aucun.
  
 **En-têtes de requête** -aucun en-tête supplémentaire.
  
 Le corps de la **requête** contient le nom de la dimension pour laquelle nous voulons les membres. Le nombre maximal de membres retourné, à côté de vous pouvez spécifier un filtre pour limiter les membres renvoyés.
  
```json
{
"ByPassCache": false,
"DataModelName": "[StartDate].[Month]",
"SearchCaption": "",
"SearchValue": "",
"PageNumber": 0,
"PageSize": 8000
}
```

 **Réponse** : la réponse comprend un code d’État http et un ensemble d’en-têtes de réponse.
  
 **Code d’État** -une opération réussie renvoie le code d’état 200 (OK).
  
 **En-têtes de réponse** : aucun en-tête supplémentaire.
  
 Le corps de la **réponse** : Voici un exemple de charge utile de réponse dans JSON en réponse à une demande de «[DateDébut]. [Mois] "dimension.
  
> [!NOTE]
> La liste affiche uniquement une petite partie de la liste. 
  
```json
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
