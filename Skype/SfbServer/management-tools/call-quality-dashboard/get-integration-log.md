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
description: 'Résumé : Découvrez l’opération obtenir journal d’intégration, qui fait partie de l’API de données pour appeler le tableau de bord qualité. Tableau de bord qualité appel est un outil de Skype pour Business Server 2015.'
ms.openlocfilehash: 8ccd4fc299cbf5310a5974d55b181aa1f42255ce
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="get-integration-log"></a>Obtenir le journal d’intégration
 
**Résumé :** Obtenir des informations sur l’opération obtenir journal d’intégration, qui fait partie de l’API de données pour appeler le tableau de bord qualité. Tableau de bord qualité appel est un outil de Skype pour Business Server 2015.
  
L’opération obtenir le journal intégration fait partie de l’API de données pour appeler le tableau de bord qualité
  
## <a name="get-integration-log"></a>Obtenir le journal d’intégration

Obtenir le journal d’intégration opération retourne une liste d’entrées de journal décrivant les activités QoE cube de traitement.
  
Cette opération est désactivée par défaut pour des raisons de sécurité. Lorsque désactivé, il retourne une chaîne vide. Pour activer cette opération, les administrateurs doivent configurer le fichier web.config pour l’application de l’API de données hôte web.
  

|Méthode|**URI de la demande**|**Version de HTTP**|
|:-----|:-----|:-----|
|Télécharger  <br/> |https://\<portal\>/QoEDataService/IntegrationLog  <br/> |HTTP/1.1  <br/> |
   
 **Les paramètres URI** - None.
  
 **En-têtes de requête** - aucun en-tête supplémentaire.
  
 **Corps de requête** - None.
  
 **Réponse** : la réponse contient un code d’état HTTP et d’un ensemble d’en-têtes de réponse.
  
 **Code d’état** - une opération réussie retourne un code d’état 200 (OK).
  
 **En-têtes de réponse** - aucun en-tête supplémentaire.
  
 **Corps de la réponse** - vous trouverez ci-dessous un exemple de structure d’entrées de journal.
  
```
[
{"LogCategory":"<category>","LogTime":"2015-03-18T10:28:29.10","LogDescription":"<log description>"}
]

```


