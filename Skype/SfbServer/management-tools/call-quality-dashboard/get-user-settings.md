---
title: Obtention des paramètres utilisateur
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bdfe063b-e808-4f3c-884a-acbbabb9be0a
description: 'Résumé: en savoir plus sur l’opération obtenir les paramètres d’utilisateur, qui fait partie du service des paramètres utilisateur. Le service de paramètres utilisateur fait partie de l’API du référentiel pour le tableau de bord de qualité des appels. Le tableau de bord de qualité des appels est un outil pour Skype entreprise Server.'
ms.openlocfilehash: 8d1bb1da9e9a186cbc10f0c8ba36275348bb7267
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274617"
---
# <a name="get-user-settings"></a>Obtention des paramètres utilisateur
 
**Résumé:** En savoir plus sur l’opération obtenir les paramètres d’utilisateur, qui fait partie du service des paramètres utilisateur. Le service de paramètres utilisateur fait partie de l’API du référentiel pour le tableau de bord de qualité des appels. Le tableau de bord de qualité des appels est un outil pour Skype entreprise Server.
  
L’opération obtenir les paramètres utilisateur fait partie du service de paramètres utilisateur de l’API du référentiel pour le tableau de bord de qualité des appels.
  
## <a name="get-user-settings"></a>Obtention des paramètres utilisateur

Obtenir les paramètres d’utilisateur renvoie une liste de paramètres pour un utilisateur spécifié.
  

|**Méthode**|**URI de la requête**|**Version HTTP**|
|:-----|:-----|:-----|
|Télécharger  <br/> |https://\<Portal\>/QoERepositoryService/Repository/User/{userid}/Setting  <br/> |HTTP/1.1  <br/> |
   
 **Paramètres d’URI**
  
- *effective* -facultatif. Ce paramètre s’applique uniquement lorsque la valeur par défaut de l’ID utilisateur spécial est utilisée. Dans les autres cas, elle est ignorée. `True`renvoie des paramètres utilisateur efficaces `false` et renvoie des paramètres utilisateur uniquement (par défaut).
    
  **En-têtes de requête** -aucun en-tête supplémentaire.
  
  Le corps de la **requête** .
  
  **Réponse** : la réponse comprend un code d’État http et un ensemble d’en-têtes de réponse.
  
  **Code d’État** -une opération réussie renvoie le code d’état 200 (OK).
  
  **En-têtes de réponse** : aucun en-tête supplémentaire.
  
  Le corps de la **réponse** : Voici un exemple de charge utile de réponse dans JSON.
  
```
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
