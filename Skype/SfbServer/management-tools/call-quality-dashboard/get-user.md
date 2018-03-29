---
title: Obtenir l’utilisateur
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 52b89a4b-a0bd-493d-bb5e-e21904eb8e48
description: 'Résumé : Découvrez l’opération obtenir l’utilisateur, qui fait partie du Service de l’utilisateur. Le Service de l’utilisateur est la partie de l’API de référentiel pour appeler le tableau de bord qualité. Tableau de bord qualité appel est un outil de Skype pour Business Server 2015.'
ms.openlocfilehash: e3863819ea15a1039a3a02b1a35cfc7326af7e1d
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="get-user"></a>Obtenir l’utilisateur
 
**Résumé :** Obtenir des informations sur l’opération de l’utilisateur d’obtenir, qui fait partie du Service de l’utilisateur. Le Service de l’utilisateur est la partie de l’API de référentiel pour appeler le tableau de bord qualité. Tableau de bord qualité appel est un outil de Skype pour Business Server 2015.
  
L’opération obtenir des utilisateurs fait partie du Service utilisateur dans l’API de référentiel pour appeler le tableau de bord qualité.
  
## <a name="get-user"></a>Obtenir l’utilisateur

Obtenir les retours utilisateur un enregistrement d’utilisateur à partir du référentiel.
  
|**Méthode**|**URI de la demande**|**Version de HTTP**|
|:-----|:-----|:-----|
|Télécharger  <br/> |https://\<portal\>{/QoERepositoryService/repository/utilisateur/ID utilisateur}  <br/> |HTTP/1.1  <br/> |
   
 **Les paramètres URI** - None.
  
 **En-têtes de requête** - aucun en-tête supplémentaire.
  
 **Corps de requête** - None.
  
 **Réponse** : la réponse contient un code d’état HTTP et d’un ensemble d’en-têtes de réponse.
  
 **Code d’état** - une opération réussie retourne un code d’état 200 (OK). Si un utilisateur spécifié QU'ID n’est pas trouvé, il renvoie le code d’état 404 (introuvable).
  
 **En-têtes de réponse** - aucun en-tête supplémentaire.
  
 **Corps de la réponse** - Voici une charge utile d’exemple réponse au format JSON.
  
```
{
"userId": 0,
"loginName": "system",
"defaultItemId": 1655
}

```

 *pseudo* - ID de l’utilisateur.
  
 *loginName* - identification de l’utilisateur externe pour les utilisateurs normaux. Si l’authentification Windows est utilisée pour authentifier les utilisateurs, cela peut être un nom de domaine complet de l’utilisateur.
  
 *defaultItemId* - ID de l’élément par défaut pour cet utilisateur. L’élément par défaut est l’élément supérieur qui est associée à l’utilisateur. Tous les autres éléments que cet utilisateur peuvent être parcourus à partir de l’élément par défaut.
  
> [!NOTE]
> Fournir le `defaultItemId` valeur à opération obtenir l’élément à récupérer les détails de l’élément par défaut.
  

