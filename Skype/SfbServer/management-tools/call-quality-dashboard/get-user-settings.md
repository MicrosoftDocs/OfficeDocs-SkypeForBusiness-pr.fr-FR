---
title: Obtenir les paramètres de l’utilisateur
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bdfe063b-e808-4f3c-884a-acbbabb9be0a
description: 'Résumé : Découvrez l’opération obtenir les paramètres utilisateur, qui fait partie du Service paramètres utilisateur. Le Service de paramètres utilisateur fait partie de l’API de référentiel pour appeler le tableau de bord qualité. Tableau de bord qualité appel est un outil de Skype pour Business Server 2015.'
ms.openlocfilehash: 55c3247f0412a9ce10927496ee65255129edfd93
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="get-user-settings"></a>Obtenir les paramètres de l’utilisateur
 
**Résumé :** Obtenir des informations sur l’opération obtenir les paramètres utilisateur, qui fait partie du Service paramètres utilisateur. Le Service de paramètres utilisateur fait partie de l’API de référentiel pour appeler le tableau de bord qualité. Tableau de bord qualité appel est un outil de Skype pour Business Server 2015.
  
L’opération obtenir les paramètres utilisateur fait partie du Service de paramètres utilisateur dans l’API de référentiel pour appeler le tableau de bord qualité.
  
## <a name="get-user-settings"></a>Obtenir les paramètres de l’utilisateur

Paramètres d’utilisateur get retourne une liste de paramètres pour un utilisateur spécifié.
  

|**Méthode**|**URI de la demande**|**Version de HTTP**|
|:-----|:-----|:-----|
|Télécharger  <br/> |https://\<portal\>/QoERepositoryService/repository/utilisateur / {ID utilisateur} / définition  <br/> |HTTP/1.1  <br/> |
   
 **Paramètres URI**
  
-  *efficace* : facultatif. Ce paramètre s’applique uniquement lorsque la valeur par défaut des ID utilisateur spécial est utilisé. Dans les autres cas, il sera ignoré. `True`Renvoie les paramètres d’utilisateur efficace et `false` renvoie simplement les paramètres utilisateur (par défaut).
    
 **En-têtes de requête** - aucun en-tête supplémentaire.
  
 **Corps de requête** - None.
  
 **Réponse** : la réponse contient un code d’état HTTP et d’un ensemble d’en-têtes de réponse.
  
 **Code d’état** - une opération réussie retourne un code d’état 200 (OK).
  
 **En-têtes de réponse** - aucun en-tête supplémentaire.
  
 **Corps de la réponse** - Voici une charge utile d’exemple réponse au format JSON.
  
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


