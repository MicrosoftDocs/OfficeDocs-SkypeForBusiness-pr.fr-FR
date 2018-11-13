---
title: Obtenir des données de l’intégration de la dernières
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: e7967dd9-0d6a-4a80-8b59-b8fc2e5615f8
description: 'Résumé : Découvrez l’opération obtenir les données de l’intégration de la dernière, qui fait partie de l’API de données pour le tableau de bord qualité des appels. Tableau de bord de qualité des appels est un outil de Skype pour Business Server 2015.'
ms.openlocfilehash: a5b6ee83cab333ebbacbd4986d6550b60dfa65dd
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/13/2018
ms.locfileid: "26296364"
---
# <a name="get-last-integration-data"></a>Obtenir des données de l’intégration de la dernières
 
**Résumé :** Obtenir des informations sur l’opération obtenir les données de l’intégration de la dernière, qui fait partie de l’API de données pour le tableau de bord qualité des appels. Tableau de bord de qualité des appels est un outil de Skype pour Business Server 2015.
  
L’opération obtenir les données de l’intégration de la dernière fait partie de l’API de données pour le tableau de bord qualité des appels.
  
## <a name="get-last-integration-data"></a>Obtenir des données de l’intégration de la dernières

Obtenir les données de l’intégration de la dernière opération renvoie la liste des derniers 5 réussite/échec de l’archivage et le traitement du cube.
  
Cette fonctionnalité est désactivée par défaut et il doit être activé en configurant l’API de données.
  

|**Méthode**|**URI de la demande**|**Version HTTP**|
|:-----|:-----|:-----|
|Télécharger  <br/> |https://\<portal\>/QoEDataService/IntegrationLog/Status  <br/> |HTTP/1.1.  <br/> |
   
 **Paramètres d’URI** - None.
  
 **En-têtes de demande** - aucun en-tête supplémentaire.
  
 **Corps de requête** - None.
  
 **Réponse** - la réponse inclut un code d’état HTTP et un ensemble d’en-têtes de réponse.
  
 **Code d’état** - une opération réussie retourne un code d’état 200 (OK).
  
 **En-têtes de réponse** - aucun en-tête supplémentaire.
  
 **Corps de réponse** - Voici un état de journal exemple.
  
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