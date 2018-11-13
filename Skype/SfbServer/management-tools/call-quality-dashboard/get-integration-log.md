---
title: Obtenir le journal d’intégration
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 8856f6bc-5460-4f35-acf2-f7662f01579b
description: 'Résumé : Découvrez l’opération obtenir les journaux de l’intégration, qui fait partie de l’API de données pour le tableau de bord qualité des appels. Tableau de bord de qualité des appels est un outil de Skype pour Business Server 2015.'
ms.openlocfilehash: 1b21e078578b9e198c743f77f77e4beca94ddeaf
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/13/2018
ms.locfileid: "26294831"
---
# <a name="get-integration-log"></a>Obtenir le journal d’intégration
 
**Résumé :** Obtenir des informations sur l’opération obtenir les journaux de l’intégration, qui fait partie de l’API de données pour le tableau de bord qualité des appels. Tableau de bord de qualité des appels est un outil de Skype pour Business Server 2015.
  
L’opération obtenir un journal intégration fait partie de l’API de données pour le tableau de bord qualité des appels
  
## <a name="get-integration-log"></a>Obtenir le journal d’intégration

Obtenir le journal d’intégration opération retourne une liste d’entrées de journal décrivant les activités dans le QoE Cube.
  
Cette opération est désactivée par défaut pour des raisons de sécurité. Lorsque désactivée, elle renvoie une chaîne vide. Pour activer cette opération, les administrateurs doivent configurer le fichier web.config pour l’application web de l’API de données hôte.
  

|Méthode|**URI de la demande**|**Version HTTP**|
|:-----|:-----|:-----|
|Télécharger  <br/> |https://\<portal\>/QoEDataService/IntegrationLog  <br/> |HTTP/1.1.  <br/> |
   
 **Paramètres d’URI** - None.
  
 **En-têtes de demande** - aucun en-tête supplémentaire.
  
 **Corps de requête** - None.
  
 **Réponse** - la réponse inclut un code d’état HTTP et un ensemble d’en-têtes de réponse.
  
 **Code d’état** - une opération réussie retourne un code d’état 200 (OK).
  
 **En-têtes de réponse** - aucun en-tête supplémentaire.
  
 **Corps de réponse** - Voici un exemple de structure des entrées du journal.
  
```
[
{"LogCategory":"<category>","LogTime":"2015-03-18T10:28:29.10","LogDescription":"<log description>"}
]
```


