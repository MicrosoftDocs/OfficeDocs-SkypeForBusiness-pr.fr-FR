---
title: Vider le cache
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 08648b16-7a64-41d8-9577-5000a20fce46
description: 'Résumé : Découvrez l’opération vider le Cache, qui fait partie de l’API de données pour le tableau de bord qualité des appels. Tableau de bord de qualité des appels est un outil de Skype pour Business Server.'
ms.openlocfilehash: c2371a7f99eb37e8e01be919bf6c31b0c9a452cb
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30889237"
---
# <a name="clear-cache"></a>Vider le cache
 
**Résumé :** Obtenir des informations sur l’opération de vider le Cache, ce qui fait partie de l’API de données pour le tableau de bord qualité des appels. Tableau de bord de qualité des appels est un outil de Skype pour Business Server.
  
L’opération de vider le Cache fait partie de l’API de données pour le tableau de bord qualité des appels.
  
## <a name="clear-cache"></a>Vider le cache

Opération de Cache Clear supprime le cache sur le serveur pour les requêtes et les données. Le cache seront réinitialisés et nous allons les données du cube QoE ultérieurement pour de nouvelles demandes.
  

|**Méthode**|**URI de la demande**|**Version HTTP**|
|:-----|:-----|:-----|
|Publier  <br/> |https://\<portal\>/QoEDataService/ClearCache  <br/> |HTTP/1.1.  <br/> |
   
 **Paramètres d’URI** - None.
  
 **En-têtes de demande** - aucun en-tête supplémentaire.
  
 **Corps de requête** - None.
  
 **Réponse** - la réponse inclut un code d’état HTTP et un ensemble d’en-têtes de réponse.
  
 **Code d’état** - une opération réussie retourne un code d’état 200 (OK).
  
 **En-têtes de réponse** - aucun en-tête supplémentaire.
  
 **Corps de réponse** - None.
  

