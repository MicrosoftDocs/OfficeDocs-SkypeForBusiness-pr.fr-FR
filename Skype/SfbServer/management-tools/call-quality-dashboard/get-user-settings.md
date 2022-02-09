---
title: Obtention des paramètres utilisateur
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
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
ms.openlocfilehash: bcde4b170de7b95007c62c5083132504e16ef6c9
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62401878"
---
# <a name="get-user-settings"></a>Obtention des paramètres utilisateur
 
**Résumé :** Découvrez l’opération Get User Paramètres, qui fait partie du service d’Paramètres utilisateur. Le service Paramètres utilisateur fait partie de l’API référentiel pour le tableau de bord de qualité des appels. Le Tableau de bord de qualité des appels est un outil pour Skype Entreprise Server.
  
L’opération Get User Paramètres fait partie du service d’Paramètres utilisateur dans l’API référentiel pour le tableau de bord de qualité des appels.
  
## <a name="get-user-settings"></a>Obtention des paramètres utilisateur

Get User Paramètres renvoie la liste des paramètres d’un utilisateur spécifié.
  

|**Méthode**|**URI de demande**|**HTTP Version**|
|:-----|:-----|:-----|
|GET  <br/> |\<portal\>https:///QoERepositoryService/repository/user/{userId}/setting  <br/> |HTTP/1.1  <br/> |
   
 **Paramètres d’URI**
  
- *effective*  - Facultatif. Ce paramètre s’applique uniquement lorsque l’ID d’utilisateur spécial par défaut est utilisé. Dans d’autres cas, il sera ignoré. `True` renvoie les paramètres utilisateur effectifs et renvoie `false` uniquement les paramètres utilisateur (par défaut).
    
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
