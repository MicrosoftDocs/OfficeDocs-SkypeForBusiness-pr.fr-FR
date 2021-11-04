---
title: Obtenir les ancêtres d’élément
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: d39b1dbc-1514-43ec-8593-9f23b3fcae62
description: 'Résumé : Découvrez l’opération Obtenir des ancêtres d’élément, qui fait partie du service d’élément. Le service d’élément fait partie de l’API de référentiel pour le tableau de bord de qualité des appels. Le Tableau de bord de qualité des appels est un outil pour Skype Entreprise Server.'
ms.openlocfilehash: 96fae0992ed6952d36ff966a559ef74da76e2606
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60765342"
---
# <a name="get-item-ancestors"></a>Obtenir les ancêtres d’élément
 
**Résumé :** Découvrez l’opération Obtenir les ancêtres d’élément, qui fait partie du service d’élément. Le service d’élément fait partie de l’API de référentiel pour le tableau de bord de qualité des appels. Le Tableau de bord de qualité des appels est un outil pour Skype Entreprise Server.
  
L’opération Obtenir des ancêtres d’élément fait partie du service d’élément dans l’API référentiel pour le tableau de bord de qualité des appels.
  
## <a name="get-item-ancestors"></a>Obtenir les ancêtres d’élément

Obtenir des ancêtres d’élément renvoie des ancêtres d’éléments spécifiques à partir du référentiel.
  

|**Méthode**|**URI de demande**|**HTTP Version**|
|:-----|:-----|:-----|
|GET  <br/> |https:// \<portal\> /QoERepositoryService/repository/itemAncestors/{itemId}  <br/> |HTTP/1.1  <br/> |
   
 **Paramètres d’URI** - Aucun.
  
 **En-têtes de requête** : aucun en-tête supplémentaire.
  
 **Corps de la** demande - Aucun.
  
 **Réponse** : la réponse inclut un code d’état HTTP et un ensemble d’en-têtes de réponse.
  
 **Code d’état** : une opération réussie renvoie le code d’état 200 (OK). Si un ID utilisateur spécifié est in trouvé, il renvoie le code d’état 404 (In trouvé).
  
 **En-têtes de réponse** : aucun en-tête supplémentaire.
  
 **Corps de la** réponse : voici un exemple de charge utile de réponse dans JSON.
  
```json
[{
"item1": 1653,
"item2": 0,
"item3": "Audio Streams Monthly Trend"
},
{
"item1": 1652,
"item2": 1,
"item3": "All Audio Streams"
}]
```

 *Item1*  : ID de l’élément.
  
 *Élément2*  : la profondeur est la distance à partir de l’élément. 0 est le parent immédiat.
  
 *Item3*  : titre de l’élément.
  

