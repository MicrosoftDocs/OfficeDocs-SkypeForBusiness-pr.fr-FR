---
title: Obtention d’un paramètre utilisateur
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
ms.assetid: 16611a55-79fb-487a-a936-20caca829f87
description: 'Résumé : en savoir plus sur l’opération Get User Setting, qui fait partie du service de paramètres utilisateur. Le service de paramètres utilisateur fait partie de l’API du référentiel pour le tableau de bord de qualité des appels. Le tableau de bord de qualité des appels est un outil pour Skype entreprise Server.'
ms.openlocfilehash: 4ab9d4d718a2ff411db72f38b59a758523935504
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816753"
---
# <a name="get-user-setting"></a>Obtention d’un paramètre utilisateur
 
**Résumé :** Apprenez-en davantage sur l’opération Get User Setting, qui fait partie du service de paramètres utilisateur. Le service de paramètres utilisateur fait partie de l’API du référentiel pour le tableau de bord de qualité des appels. Le tableau de bord de qualité des appels est un outil pour Skype entreprise Server.
  
L’opération Get User Setting fait partie du service de paramètres utilisateur de l’API du référentiel pour le tableau de bord de qualité des appels.
  
## <a name="get-user-setting"></a>Obtention d’un paramètre utilisateur

Le paramètre Get est un paramètre utilisateur unique.
  

|**Méthode**|**URI de la requête**|**Version HTTP**|
|:-----|:-----|:-----|
|Télécharger  <br/> |https://\<Portal\>/QoERepositoryService/Repository/User/{userid}/Setting/{Key}  <br/> |HTTP/1.1  <br/> |
   
 **Paramètres d’URI** -aucun.
  
 **En-têtes de requête** -aucun en-tête supplémentaire.
  
 Le corps de la **requête** .
  
 **Réponse** : la réponse comprend un code d’État http et un ensemble d’en-têtes de réponse.
  
 **Code d’État** -une opération réussie renvoie le code d’état 200 (OK).
  
 **En-têtes de réponse** : aucun en-tête supplémentaire.
  
 Le corps de la **réponse** : Voici un exemple de charge utile de réponse dans JSON.
  
```json
{
"userId": 6,
"key": "ShowDescriptions",
"value": "true"
}
```

 *ID de* l’utilisateur.
  
 *clé du* paramètre.
  
 valeur *valeur* du paramètre.
  

