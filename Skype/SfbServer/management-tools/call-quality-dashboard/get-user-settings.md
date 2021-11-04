---
title: Obtention des paramètres utilisateur
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
ms.assetid: bdfe063b-e808-4f3c-884a-acbbabb9be0a
description: 'Résumé : Découvrez l’opération Get User Paramètres, qui fait partie du service d’Paramètres utilisateur. Le service Paramètres utilisateur fait partie de l’API référentiel pour le tableau de bord de qualité des appels. Le Tableau de bord de qualité des appels est un outil pour Skype Entreprise Server.'
ms.openlocfilehash: b7be08df46aa63287d931a566d26671bfecfc3b8
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60778174"
---
# <a name="get-user-settings"></a>Obtention des paramètres utilisateur
 
**Résumé :** Découvrez l’opération Get User Paramètres, qui fait partie du service d’Paramètres utilisateur. Le service Paramètres utilisateur fait partie de l’API référentiel pour le tableau de bord de qualité des appels. Le Tableau de bord de qualité des appels est un outil pour Skype Entreprise Server.
  
L’opération Get User Paramètres fait partie du service d’Paramètres utilisateur dans l’API référentiel pour le tableau de bord de qualité des appels.
  
## <a name="get-user-settings"></a>Obtention des paramètres utilisateur

Get User Paramètres renvoie la liste des paramètres d’un utilisateur spécifié.
  

|**Méthode**|**URI de demande**|**HTTP Version**|
|:-----|:-----|:-----|
|GET  <br/> |https:// \<portal\> /QoERepositoryService/repository/user/{userId}/setting  <br/> |HTTP/1.1  <br/> |
   
 **Paramètres d’URI**
  
- *effective*  - Facultatif. Ce paramètre s’applique uniquement lorsque l’ID d’utilisateur spécial par défaut est utilisé. Dans d’autres cas, il sera ignoré. `True` renvoie les paramètres utilisateur effectifs et `false` renvoie uniquement les paramètres utilisateur (par défaut).
    
  **En-têtes de requête** : aucun en-tête supplémentaire.
  
  **Corps de la** demande - Aucun.
  
  **Réponse** : la réponse inclut un code d’état HTTP et un ensemble d’en-têtes de réponse.
  
  **Code d’état** : une opération réussie renvoie le code d’état 200 (OK).
  
  **En-têtes de réponse** : aucun en-tête supplémentaire.
  
  **Corps de la** réponse : voici un exemple de charge utile de réponse dans JSON.
  
```json
[{
"userId": 6,
"key": "ShowDescriptions",
"value": "true"
},
{
"userId": 6,
"key": "ShowTimeStamps",
"value": "true"
}]
```
