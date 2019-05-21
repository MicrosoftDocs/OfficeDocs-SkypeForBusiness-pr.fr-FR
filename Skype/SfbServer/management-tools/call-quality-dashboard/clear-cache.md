---
title: Vider le cache
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 08648b16-7a64-41d8-9577-5000a20fce46
description: 'Résumé: Découvrez l’opération effacer le cache, qui fait partie de l’API de données du tableau de bord de qualité des appels. Le tableau de bord de qualité des appels est un outil pour Skype entreprise Server.'
ms.openlocfilehash: 38648e1a910f93a30bd6da8807321acad0330e62
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274834"
---
# <a name="clear-cache"></a>Vider le cache
 
**Résumé:** Apprenez-en davantage sur l’opération d’effacement du cache, qui fait partie de l’API de données du tableau de bord de qualité des appels. Le tableau de bord de qualité des appels est un outil pour Skype entreprise Server.
  
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
  
 **Corps** de la réponse: aucun.
  

