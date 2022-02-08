---
title: Obtenir le journal d’intégration
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 8856f6bc-5460-4f35-acf2-f7662f01579b
description: 'Résumé : Découvrez l’opération Obtenir le journal d’intégration, qui fait partie de l’API de données du tableau de bord de qualité des appels. Le Tableau de bord de qualité des appels est un outil pour Skype Entreprise Server.'
ms.openlocfilehash: b82ecffd5b39df6e149787ec7b3265f3e8176376
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62388072"
---
# <a name="get-integration-log"></a>Obtenir le journal d’intégration
 
**Résumé :** Découvrez l’opération Obtenir le journal d’intégration, qui fait partie de l’API de données pour le tableau de bord de qualité des appels. Le Tableau de bord de qualité des appels est un outil pour Skype Entreprise Server.
  
L’opération Obtenir le journal d’intégration fait partie de l’API de données du tableau de bord de qualité des appels
  
## <a name="get-integration-log"></a>Obtenir le journal d’intégration

L’opération Obtenir le journal d’intégration renvoie une liste d’entrées de journal décrivant les activités dans le traitement du cube QoE.
  
Cette opération est désactivée par défaut pour des raisons de sécurité. Lorsqu’elle est désactivée, elle renvoie une chaîne vide. Pour activer cette opération, les administrateurs doivent configurer le web.config pour l’application web hôte de l’API de données.
  

|Méthode|**URI de demande**|**HTTP Version**|
|:-----|:-----|:-----|
|GET  <br/> |\<portal\>https:///QoEDataService/IntegrationLog  <br/> |HTTP/1.1  <br/> |
   
 **Paramètres d’URI** - Aucun.
  
 **En-têtes de requête** : aucun en-tête supplémentaire.
  
 **Corps de la** demande - Aucun.
  
 **Réponse** : la réponse inclut un code d’état HTTP et un ensemble d’en-têtes de réponse.
  
 **Code d’état** : une opération réussie renvoie le code d’état 200 (OK).
  
 **En-têtes de réponse** : aucun en-tête supplémentaire.
  
 **Corps de la** réponse : voici un exemple de structure d’entrées de journal.
  
```json
[
{"LogCategory":"<category>","LogTime":"2015-03-18T10:28:29.10","LogDescription":"<log description>"}
]
```


