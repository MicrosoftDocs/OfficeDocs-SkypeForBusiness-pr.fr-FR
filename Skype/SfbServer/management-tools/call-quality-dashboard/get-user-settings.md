---
title: Obtenir les paramètres utilisateur
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
ms.openlocfilehash: 9547479b95a8b321a9aa2f92c7cfcb2e88edf4bb
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/15/2018
ms.locfileid: "26532898"
---
# <a name="get-user-settings"></a>Obtenir les paramètres utilisateur
 
**Résumé :** Obtenir des informations sur l’opération obtenir les paramètres utilisateur, qui fait partie du Service de paramètres utilisateur. Le Service de paramètres utilisateur fait partie de l’API de référentiel pour appeler le tableau de bord qualité. Tableau de bord de qualité des appels est un outil de Skype pour Business Server.
  
L’opération obtenir les paramètres utilisateur fait partie du Service de paramètres utilisateur de l’API de référentiel pour appeler le tableau de bord qualité.
  
## <a name="get-user-settings"></a>Obtenir les paramètres utilisateur

Obtenir les paramètres utilisateur renvoie une liste des paramètres pour un utilisateur spécifié.
  

|**Méthode**|**URI de la demande**|**Version HTTP**|
|:-----|:-----|:-----|
|Télécharger  <br/> |https://\<portal\>/QoERepositoryService/référentiel/utilisateur / {userId} / définition  <br/> |HTTP/1.1.  <br/> |
   
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