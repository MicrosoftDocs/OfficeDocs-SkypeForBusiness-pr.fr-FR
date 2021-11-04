---
title: Obtention d’un paramètre utilisateur
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
ms.assetid: 16611a55-79fb-487a-a936-20caca829f87
description: 'Résumé : Découvrez l’opération Obtenir les paramètres utilisateur, qui fait partie du service d’Paramètres utilisateur. Le service Paramètres utilisateur fait partie de l’API référentiel pour le tableau de bord de qualité des appels. Le Tableau de bord de qualité des appels est un outil pour Skype Entreprise Server.'
ms.openlocfilehash: 2be81d09c45a93c967af2556ba7ed8fbca9ce0f9
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60774624"
---
# <a name="get-user-setting"></a>Obtention d’un paramètre utilisateur
 
**Résumé :** Découvrez l’opération Obtenir les paramètres utilisateur, qui fait partie du service d’Paramètres utilisateur. Le service Paramètres utilisateur fait partie de l’API référentiel pour le tableau de bord de qualité des appels. Le Tableau de bord de qualité des appels est un outil pour Skype Entreprise Server.
  
L’opération Obtenir les paramètres utilisateur fait partie du service Paramètres utilisateur dans l’API référentiel pour le tableau de bord de qualité des appels.
  
## <a name="get-user-setting"></a>Obtention d’un paramètre utilisateur

Obtenir le paramètre utilisateur renvoie un paramètre utilisateur unique.
  

|**Méthode**|**URI de demande**|**HTTP Version**|
|:-----|:-----|:-----|
|GET  <br/> |https:// \<portal\> /QoERepositoryService/repository/user/{userId}/setting/{key}  <br/> |HTTP/1.1  <br/> |
   
 **Paramètres d’URI** - Aucun.
  
 **En-têtes de requête** : aucun en-tête supplémentaire.
  
 **Corps de la** demande - Aucun.
  
 **Réponse** : la réponse inclut un code d’état HTTP et un ensemble d’en-têtes de réponse.
  
 **Code d’état** : une opération réussie renvoie le code d’état 200 (OK).
  
 **En-têtes de réponse** : aucun en-tête supplémentaire.
  
 **Corps de la** réponse : voici un exemple de charge utile de réponse dans JSON.
  
```json
{
"userId": 6,
"key": "ShowDescriptions",
"value": "true"
}
```

 *userId*  : ID de l’utilisateur.
  
 *key*  - Clé du paramètre.
  
 *valeur*  - Valeur du paramètre.
  

