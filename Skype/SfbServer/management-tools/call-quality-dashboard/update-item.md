---
title: Mettre à jour un élément
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
ms.assetid: b1c15c56-cdae-4f3e-838a-52f0940cf729
description: 'Résumé : Découvrez l’opération Mettre à jour l’élément, qui fait partie du service d’élément. Le service d’élément fait partie de l’API de référentiel pour le tableau de bord de qualité des appels. Le Tableau de bord de qualité des appels est un outil pour Skype Entreprise Server.'
ms.openlocfilehash: ef77a4a73cd83743b718988657dcf4f4eb9fd404
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60759686"
---
# <a name="update-item"></a>Mettre à jour un élément
 
**Résumé :** Découvrez l’opération Mettre à jour l’élément, qui fait partie du service d’élément. Le service d’élément fait partie de l’API de référentiel pour le tableau de bord de qualité des appels. Le Tableau de bord de qualité des appels est un outil pour Skype Entreprise Server.
  
L’opération Mettre à jour un élément fait partie du service d’élément dans l’API de référentiel pour le tableau de bord de qualité des appels.
  
## <a name="update-item"></a>Mettre à jour un élément

L’élément de mise à jour met à jour un élément spécifique dans le référentiel.
  

|**Méthode**|**URI de demande**|**HTTP Version**|
|:-----|:-----|:-----|
|PUT  <br/> |https:// \<portal\> /QoERepositoryService/repository/item/{itemId}  <br/> |HTTP/1.1  <br/> |
   
 **Paramètres d’URI** - Aucun.
  
 **En-têtes de requête** -Content-Type: application/json.
  
 **Corps de la** demande - JSON.
  
Exemple de charge utile de demande :
  
```json
{
  content : "{ 'Product' : 'New Product Name'",
  type: "application/json"
}
```

 *content*  Données au format JSON à stocker en tant que nouveau contenu d’un sous-élément existant. Techniquement, un référentiel peut stocker n’importe quel contenu de n’importe quel schéma, mais lorsqu’il est utilisé pour le Tableau de bord de qualité des appels, il doit s’agit d’un rapport ou d’une requête. *type*  Spécifiez toujours « application/json » pour le Tableau de bord de qualité des appels.
  
 **Réponse** : la réponse inclut un code d’état HTTP et un ensemble d’en-têtes de réponse.
  
 **Code d’état** : une opération réussie renvoie le code d’état 204 (Aucun contenu). Si un ID d’élément spécifié est in trouvé, il renvoie le code d’état 404 (In trouvé).
  
> [!IMPORTANT]
> « Aucun contenu » n’est pas un état d’erreur. Cela signifie qu’une réponse n’a rien renvoyé dans le corps (en revanche, 200 OK renvoie du contenu dans Le corps). Il indique que l’élément a été mis à jour avec succès. 
  
 **En-têtes de réponse** - Aucun.
  
 **Corps de la** réponse - Aucun.
  

