---
title: Obtenir un utilisateur
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
ms.collection: IT_Skype16
ms.assetid: 52b89a4b-a0bd-493d-bb5e-e21904eb8e48
description: 'Résumé : Découvrez la procédure d’obtention d’un utilisateur, qui fait partie du service utilisateur. Le service d’utilisateur fait partie de l’API du référentiel pour le tableau de bord de qualité des appels. Le tableau de bord de qualité des appels est un outil pour Skype entreprise Server.'
ms.openlocfilehash: e07a232b61e5ef0bb7462b3fff58d642a14496ec
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816733"
---
# <a name="get-user"></a>Obtenir un utilisateur
 
**Résumé :** En savoir plus sur l’opération obtenir l’utilisateur, qui fait partie du service utilisateur. Le service d’utilisateur fait partie de l’API du référentiel pour le tableau de bord de qualité des appels. Le tableau de bord de qualité des appels est un outil pour Skype entreprise Server.
  
L’opération obtenir les utilisateurs fait partie du service utilisateur dans l’API du référentiel pour le tableau de bord de qualité des appels.
  
## <a name="get-user"></a>Obtenir un utilisateur

Obtenir renvoie un enregistrement utilisateur du référentiel.
  
|**Méthode**|**URI de la requête**|**Version HTTP**|
|:-----|:-----|:-----|
|Télécharger  <br/> |https://\<Portal\>/QoERepositoryService/Repository/User/{userid}  <br/> |HTTP/1.1  <br/> |
   
 **Paramètres d’URI** -aucun.
  
 **En-têtes de requête** -aucun en-tête supplémentaire.
  
 Le corps de la **requête** .
  
 **Réponse** : la réponse comprend un code d’État http et un ensemble d’en-têtes de réponse.
  
 **Code d’État** -une opération réussie renvoie le code d’état 200 (OK). Si vous n’avez pas trouvé d’ID utilisateur spécifié, le code d’État 404 (introuvable) est renvoyé.
  
 **En-têtes de réponse** : aucun en-tête supplémentaire.
  
 Le corps de la **réponse** : Voici un exemple de charge utile de réponse dans JSON.
  
```json
{
"userId": 0,
"loginName": "system",
"defaultItemId": 1655
}
```

 *ID de* l’utilisateur.
  
 *LoginName* -identification de l’utilisateur externe pour les utilisateurs normaux. Si l’authentification Windows est utilisée pour authentifier les utilisateurs, il peut s’agir d’un nom de domaine complet (FQDN) de l’utilisateur.
  
 *defaultItemId* -ID de l’élément par défaut de cet utilisateur. L’élément par défaut est l’élément le plus élevé qui est associé à l’utilisateur. Pour accéder à l’élément par défaut, vous pouvez accéder à tous les autres éléments de l’utilisateur.
  
> [!NOTE]
> Fournissez `defaultItemId` la valeur pour obtenir l’opération d’élément permettant de récupérer les détails de l’élément par défaut.
  

