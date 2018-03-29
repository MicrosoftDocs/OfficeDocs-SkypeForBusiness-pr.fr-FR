---
title: Vider le Cache
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 08648b16-7a64-41d8-9577-5000a20fce46
description: 'Résumé : Découvrez l’opération vider le Cache, ce qui fait partie de l’API de données pour appeler le tableau de bord qualité. Tableau de bord qualité appel est un outil de Skype pour Business Server 2015.'
ms.openlocfilehash: 2356997facfa0057f90ea3d6c8b4cda06add2615
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="clear-cache"></a>Vider le Cache
 
**Résumé :** Obtenir des informations sur l’opération vider le Cache, ce qui fait partie de l’API de données pour appeler le tableau de bord qualité. Tableau de bord qualité appel est un outil de Skype pour Business Server 2015.
  
L’opération vider le Cache est la partie de l’API de données pour appeler le tableau de bord qualité.
  
## <a name="clear-cache"></a>Vider le Cache

Opération d’effacement du Cache supprime le cache sur le serveur pour les requêtes et les données. Cela réinitialisera le cache et nous allons les données actualisées QoE cube par la suite pour les nouvelles demandes.
  

|**Méthode**|**URI de la demande**|**Version de HTTP**|
|:-----|:-----|:-----|
|Publier  <br/> |https://\<portal\>/QoEDataService/ClearCache  <br/> |HTTP/1.1  <br/> |
   
 **Les paramètres URI** - None.
  
 **En-têtes de requête** - aucun en-tête supplémentaire.
  
 **Corps de requête** - None.
  
 **Réponse** : la réponse contient un code d’état HTTP et d’un ensemble d’en-têtes de réponse.
  
 **Code d’état** - une opération réussie retourne un code d’état 200 (OK).
  
 **En-têtes de réponse** - aucun en-tête supplémentaire.
  
 **Corps de la réponse** - None.
  

