---
title: Vider le cache
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 08648b16-7a64-41d8-9577-5000a20fce46
description: 'Résumé : Découvrez l’opération Effacer le cache, qui fait partie de l’API de données pour le tableau de bord de qualité des appels. Le Tableau de bord de qualité des appels est un outil pour Skype Entreprise Server.'
ms.openlocfilehash: c9b966bb1e35a5a6255cd75ea6c685daaf220a09
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806414"
---
# <a name="clear-cache"></a>Vider le cache
 
**Résumé :** Découvrez l’opération Effacer le cache, qui fait partie de l’API de données du tableau de bord de qualité des appels. Le Tableau de bord de qualité des appels est un outil pour Skype Entreprise Server.
  
L’opération Effacer le cache fait partie de l’API de données du Tableau de bord de qualité des appels.
  
## <a name="clear-cache"></a>Vider le cache

L’opération Effacer le cache supprime le cache sur le serveur pour les requêtes et les données. Cela réinitialise le cache et nous allons obtenir des données à jour à partir du cube QoE par la suite pour les nouvelles demandes.
  

|**Méthode**|**URI de demande**|**HTTP Version**|
|:-----|:-----|:-----|
|POST  <br/> |https:// \<portal\> /QoEDataService/ClearCache  <br/> |HTTP/1.1  <br/> |
   
 **Paramètres d’URI** - Aucun.
  
 **En-têtes de requête** : aucun en-tête supplémentaire.
  
 **Corps de la** demande - Aucun.
  
 **Réponse** : la réponse inclut un code d’état HTTP et un ensemble d’en-têtes de réponse.
  
 **Code d’état** : une opération réussie renvoie le code d’état 200 (OK).
  
 **En-têtes de réponse** : aucun en-tête supplémentaire.
  
 **Corps de la** réponse - Aucun.
  

