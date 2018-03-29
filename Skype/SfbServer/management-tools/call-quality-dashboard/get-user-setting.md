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
ms.assetid: 16611a55-79fb-487a-a936-20caca829f87
description: 'Résumé : Découvrez l’opération obtenir un paramètre utilisateur, qui fait partie du Service paramètres utilisateur. Le Service de paramètres utilisateur fait partie de l’API de référentiel pour appeler le tableau de bord qualité. Tableau de bord qualité appel est un outil de Skype pour Business Server 2015.'
ms.openlocfilehash: 562886196f06030aef30efbd6f583c29d7f29e59
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="get-user-setting"></a>Obtenir les paramètres de l’utilisateur
 
**Résumé :** Obtenir des informations sur l’opération obtenir un paramètre utilisateur, qui fait partie du Service paramètres utilisateur. Le Service de paramètres utilisateur fait partie de l’API de référentiel pour appeler le tableau de bord qualité. Tableau de bord qualité appel est un outil de Skype pour Business Server 2015.
  
L’opération obtenir un paramètre utilisateur fait partie du Service de paramètres utilisateur dans l’API de référentiel pour appeler le tableau de bord qualité.
  
## <a name="get-user-setting"></a>Obtenir les paramètres de l’utilisateur

Obtenir le paramètre utilisateur retourne un paramètre d’utilisateur unique.
  

|**Méthode**|**URI de la demande**|**Version de HTTP**|
|:-----|:-----|:-----|
|Télécharger  <br/> |https://\<portal\>{/QoERepositoryService/référentiel/utilisateur/ID utilisateur} /setting/ {clé}  <br/> |HTTP/1.1  <br/> |
   
 **Les paramètres URI** - None.
  
 **En-têtes de requête** - aucun en-tête supplémentaire.
  
 **Corps de requête** - None.
  
 **Réponse** : la réponse contient un code d’état HTTP et d’un ensemble d’en-têtes de réponse.
  
 **Code d’état** - une opération réussie retourne un code d’état 200 (OK).
  
 **En-têtes de réponse** - aucun en-tête supplémentaire.
  
 **Corps de la réponse** - Voici une charge utile d’exemple réponse au format JSON.
  
```
{
"userId": 6,
"key": "ShowDescriptions",
"value": "true"
}

```

 *pseudo* - ID de l’utilisateur.
  
 *clé* - clé du paramètre.
  
 *valeur* - valeur du paramètre.
  

