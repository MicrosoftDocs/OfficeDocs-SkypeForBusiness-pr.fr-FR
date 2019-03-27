---
title: Obtention des paramètres utilisateur
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bdfe063b-e808-4f3c-884a-acbbabb9be0a
description: 'Résumé : Découvrez l’opération obtenir les paramètres utilisateur, qui fait partie du Service de paramètres utilisateur. Le Service de paramètres utilisateur fait partie de l’API de référentiel pour appeler le tableau de bord qualité. Tableau de bord de qualité des appels est un outil de Skype pour Business Server.'
ms.openlocfilehash: 3c94f02f305ee2f779b6a31ef78bea875d462cbf
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30889020"
---
# <a name="get-user-settings"></a>Obtention des paramètres utilisateur
 
**Résumé :** Obtenir des informations sur l’opération obtenir les paramètres utilisateur, qui fait partie du Service de paramètres utilisateur. Le Service de paramètres utilisateur fait partie de l’API de référentiel pour appeler le tableau de bord qualité. Tableau de bord de qualité des appels est un outil de Skype pour Business Server.
  
L’opération obtenir les paramètres utilisateur fait partie du Service de paramètres utilisateur de l’API de référentiel pour appeler le tableau de bord qualité.
  
## <a name="get-user-settings"></a>Obtention des paramètres utilisateur

Obtenir les paramètres utilisateur renvoie une liste des paramètres pour un utilisateur spécifié.
  

|**Méthode**|**URI de la demande**|**Version HTTP**|
|:-----|:-----|:-----|
|Avoir  <br/> |https://\<portal\>/QoERepositoryService/référentiel/utilisateur / {userId} / définition  <br/> |HTTP/1.1.  <br/> |
   
 **Paramètres de l’URI**
  
- *efficace* : facultatif. Ce paramètre s’applique uniquement lorsque la valeur par défaut des ID utilisateur spécial est utilisé. Dans les autres cas, il sera ignoré. `True`Renvoie les paramètres utilisateur efficaces et `false` renvoie uniquement les paramètres utilisateur (par défaut).
    
  **En-têtes de demande** - aucun en-tête supplémentaire.
  
  **Corps de requête** - None.
  
  **Réponse** - la réponse inclut un code d’état HTTP et un ensemble d’en-têtes de réponse.
  
  **Code d’état** - une opération réussie retourne un code d’état 200 (OK).
  
  **En-têtes de réponse** - aucun en-tête supplémentaire.
  
  **Corps de réponse** - vous trouverez ci-dessous une charge utile d’exemple réponse au format JSON.
  
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
