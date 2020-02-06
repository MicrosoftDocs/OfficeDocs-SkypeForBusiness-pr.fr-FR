---
title: Obtenir les données de la dernière intégration
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
ms.assetid: e7967dd9-0d6a-4a80-8b59-b8fc2e5615f8
description: 'Résumé : Découvrez l’opération obtenir les dernières données d’intégration, qui fait partie de l’API de données du tableau de bord de qualité des appels. Le tableau de bord de qualité des appels est un outil pour Skype entreprise Server.'
ms.openlocfilehash: a3b66114f457e48b169419baddbaa4e4dc8c0764
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816773"
---
# <a name="get-last-integration-data"></a>Obtenir les données de la dernière intégration
 
**Résumé :** Apprenez-en davantage sur la dernière opération d’obtention des données d’intégration, qui fait partie de l’API de données du tableau de bord de qualité des appels. Le tableau de bord de qualité des appels est un outil pour Skype entreprise Server.
  
L’opération Get Last Data Integration fait partie de l’API de données pour le tableau de bord de qualité des appels.
  
## <a name="get-last-integration-data"></a>Obtenir les données de la dernière intégration

Obtenir la dernière opération d’intégration de données renvoie la liste des 5 dernières réussites ou échecs d’archivage et de traitement du cube.
  
Cette fonctionnalité est désactivée par défaut et doit être activée en configurant l’API de données.
  

|**Méthode**|**URI de la requête**|**Version HTTP**|
|:-----|:-----|:-----|
|Télécharger  <br/> |https://\<Portal\>/QoEDataService/IntegrationLog/Status  <br/> |HTTP/1.1  <br/> |
   
 **Paramètres d’URI** -aucun.
  
 **En-têtes de requête** -aucun en-tête supplémentaire.
  
 Le corps de la **requête** .
  
 **Réponse** : la réponse comprend un code d’État http et un ensemble d’en-têtes de réponse.
  
 **Code d’État** -une opération réussie renvoie le code d’état 200 (OK).
  
 **En-têtes de réponse** : aucun en-tête supplémentaire.
  
 Le corps de la réponse : Voici un exemple d’état **du** journal.
  
```
{
"LastSuccessIntegrations": ["01/18/2015 10:30:13",
"01/18/2015 10:28:29",
"01/17/2015 15:15:17",
"01/17/2015 15:00:17",
"01/17/2015 14:45:13"],
"LastSuccessCubeProcessings": ["01/17/2015 15:16:40",
"01/17/2015 15:01:41",
"01/17/2015 14:47:19",
"01/17/2015 14:31:40",
"01/17/2015 14:17:01"],
"LastFailedIntegrations":  ,
"LastFailedCubeProcessings": ["01/18/2015 10:30:58",
"01/18/2015 10:29:28",
"01/17/2015 10:02:20",
"01/15/2015 20:01:56",
"01/15/2015 19:45:50"],
"LastDataIntegrationStart": null,
"LastCubeProcessingStart": "01/18/2015 10:30:16"
}
```
