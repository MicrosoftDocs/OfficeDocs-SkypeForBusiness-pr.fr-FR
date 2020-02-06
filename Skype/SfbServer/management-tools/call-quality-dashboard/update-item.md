---
title: Mettre à jour un élément
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
ms.assetid: b1c15c56-cdae-4f3e-838a-52f0940cf729
description: 'Résumé : Découvrez l’opération de mise à jour des éléments, qui fait partie du service d’élément. Le service d’élément fait partie de l’API du référentiel pour le tableau de bord de qualité des appels. Le tableau de bord de qualité des appels est un outil pour Skype entreprise Server.'
ms.openlocfilehash: 460e6b26375bba28887d170c9827864bfc600138
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816673"
---
# <a name="update-item"></a>Mettre à jour un élément
 
**Résumé :** En savoir plus sur l’opération de mise à jour des éléments, qui fait partie de l’élément service. Le service d’élément fait partie de l’API du référentiel pour le tableau de bord de qualité des appels. Le tableau de bord de qualité des appels est un outil pour Skype entreprise Server.
  
L’opération de mise à jour des éléments fait partie du service d’élément dans l’API du référentiel pour le tableau de bord de qualité des appels.
  
## <a name="update-item"></a>Mettre à jour un élément

Mettre à jour l’élément met à jour un élément spécifique du référentiel.
  

|**Méthode**|**URI de la requête**|**Version HTTP**|
|:-----|:-----|:-----|
|PORT  <br/> |https://\<Portal\>/QoERepositoryService/Repository/Item/{ItemId}  <br/> |HTTP/1.1  <br/> |
   
 **Paramètres d’URI** -aucun.
  
 **En-têtes de requête** -type de contenu : application/JSON.
  
 **Demander le corps** JSON.
  
Exemple de charge utile de requête :
  
```json
{
  content : "{ 'Product' : 'New Product Name'",
  type: "application/json"
}
```

 *content (contenu* )  Les données au format JSON doivent être stockées en tant que nouveau contenu d’un sous-élément existant. Techniquement, un référentiel peut stocker tout contenu de tout schéma, mais lorsqu’il est utilisé pour le tableau de bord de qualité des appels, il doit s’agir d’un État ou d’une requête. *taper*  Spécifiez toujours « application/JSON » pour le tableau de bord de qualité des appels.
  
 **Réponse** : la réponse comprend un code d’État http et un ensemble d’en-têtes de réponse.
  
 **Code d’État** -une opération réussie renvoie le code d’État 204 (sans contenu). Si aucun ID d’élément spécifié n’est trouvé, il renvoie le code d’État 404 (introuvable).
  
> [!IMPORTANT]
> Le message « aucun contenu » n’est pas un état d’erreur. Cela signifie que la réponse n’a rien retourné dans le corps (en revanche, 200 OK renvoie du contenu dans corps). Le message indiquant que l’élément a été correctement mis à jour s’affiche. 
  
 **En-têtes de réponse** -aucun.
  
 **Corps** de la réponse : aucun.
  

