---
title: Obtenir le journal d’intégration
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
ms.assetid: 8856f6bc-5460-4f35-acf2-f7662f01579b
description: 'Résumé : Découvrez l’opération d’obtention du journal d’intégration, qui fait partie de l’API de données pour le tableau de bord de qualité des appels. Le tableau de bord de qualité des appels est un outil pour Skype entreprise Server.'
ms.openlocfilehash: 9caa909e80a0bab5257af16fe77e9d154947a56e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816813"
---
# <a name="get-integration-log"></a>Obtenir le journal d’intégration
 
**Résumé :** Découvrez l’opération d’obtention du journal d’intégration, qui fait partie de l’API de données pour le tableau de bord de qualité des appels. Le tableau de bord de qualité des appels est un outil pour Skype entreprise Server.
  
L’opération obtenir le journal d’intégration fait partie de l’API de données pour le tableau de bord de qualité des appels
  
## <a name="get-integration-log"></a>Obtenir le journal d’intégration

L’opération d’obtention du journal d’intégration renvoie une liste des entrées du journal décrivant les activités du traitement du cube QoE.
  
Cette opération est désactivée par défaut pour des raisons de sécurité. Lorsqu’elle est désactivée, elle renvoie une chaîne vide. Pour activer cette opération, les administrateurs doivent configurer le fichier Web. config de l’application Web hôte de l’API de données.
  

|Méthode|**URI de la requête**|**Version HTTP**|
|:-----|:-----|:-----|
|Télécharger  <br/> |https://\<Portal\>/QoEDataService/IntegrationLog  <br/> |HTTP/1.1  <br/> |
   
 **Paramètres d’URI** -aucun.
  
 **En-têtes de requête** -aucun en-tête supplémentaire.
  
 Le corps de la **requête** .
  
 **Réponse** : la réponse comprend un code d’État http et un ensemble d’en-têtes de réponse.
  
 **Code d’État** -une opération réussie renvoie le code d’état 200 (OK).
  
 **En-têtes de réponse** : aucun en-tête supplémentaire.
  
 **Corps** de la réponse : Voici un exemple de structure d’entrées du journal.
  
```
[
{"LogCategory":"<category>","LogTime":"2015-03-18T10:28:29.10","LogDescription":"<log description>"}
]
```


