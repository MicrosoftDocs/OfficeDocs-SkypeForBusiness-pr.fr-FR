---
title: Vider le cache
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
ms.assetid: 08648b16-7a64-41d8-9577-5000a20fce46
description: 'Résumé : Découvrez l’opération effacer le cache, qui fait partie de l’API de données du tableau de bord de qualité des appels. Le tableau de bord de qualité des appels est un outil pour Skype entreprise Server.'
ms.openlocfilehash: 821b02f204c98f5acefe69df1c848c31cd2205b7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816883"
---
# <a name="clear-cache"></a>Vider le cache
 
**Résumé :** Apprenez-en davantage sur l’opération d’effacement du cache, qui fait partie de l’API de données du tableau de bord de qualité des appels. Le tableau de bord de qualité des appels est un outil pour Skype entreprise Server.
  
L’opération d’effacement du cache fait partie de l’API de données du tableau de bord de qualité des appels.
  
## <a name="clear-cache"></a>Vider le cache

L’opération d’effacement du cache supprime le cache du serveur pour les requêtes et les données. Cette opération a pour réinitialisation le cache et nous obtiendrons de nouvelles données du cube QoE par la suite pour de nouvelles demandes.
  

|**Méthode**|**URI de la requête**|**Version HTTP**|
|:-----|:-----|:-----|
|Publier  <br/> |https://\<Portal\>/QoEDataService/ClearCache  <br/> |HTTP/1.1  <br/> |
   
 **Paramètres d’URI** -aucun.
  
 **En-têtes de requête** -aucun en-tête supplémentaire.
  
 Le corps de la **requête** .
  
 **Réponse** : la réponse comprend un code d’État http et un ensemble d’en-têtes de réponse.
  
 **Code d’État** -une opération réussie renvoie le code d’état 200 (OK).
  
 **En-têtes de réponse** : aucun en-tête supplémentaire.
  
 **Corps** de la réponse : aucun.
  

