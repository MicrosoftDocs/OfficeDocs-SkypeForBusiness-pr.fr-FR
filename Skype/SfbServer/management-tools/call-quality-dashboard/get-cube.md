---
title: Obtenir un cube
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
ms.assetid: c8eeb387-dc1e-44e0-bbf9-a566f8bda551
description: 'Résumé : Découvrez l’opération Obtenir un cube, qui fait partie de l’API de données pour le tableau de bord de qualité des appels. Le Tableau de bord de qualité des appels est un outil pour Skype Entreprise Server.'
ms.openlocfilehash: bc65a9d6886b9375a799c62a6abaefd33738dae5fd8a4d4aee83a536d9a82948
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54278722"
---
# <a name="get-cube"></a>Obtenir un cube
 
**Résumé :** Découvrez l’opération Obtenir un cube, qui fait partie de l’API de données pour le tableau de bord de qualité des appels. Le Tableau de bord de qualité des appels est un outil pour Skype Entreprise Server.
  
L’opération Obtenir un cube fait partie de l’API de données du tableau de bord de qualité des appels.
  
## <a name="get-cube"></a>Obtenir un cube

L’opération Obtenir un cube renvoie la liste des dimensions et mesures disponibles.
  

|**Méthode**|**URI de demande**|**HTTP Version**|
|:-----|:-----|:-----|
|GET  <br/> |https:// \<portal\> /QoEDataService/CubeStructure  <br/> |HTTP/1.1  <br/> |
   
 **Paramètres d’URI** - Aucun.
  
 **En-têtes de requête** : aucun en-tête supplémentaire.
  
 **Corps de la** demande - Aucun.
  
 **Réponse** : la réponse inclut un code d’état HTTP et un ensemble d’en-têtes de réponse.
  
 **Code d’état** : une opération réussie renvoie le code d’état 200 (OK).
  
 **En-têtes de réponse** : aucun en-tête supplémentaire.
  
 **Corps de la** réponse : voici un exemple de charge utile de réponse dans JSON.
  
> [!NOTE]
> Cet exemple montre uniquement les deux premiers éléments de chaque groupe d’éléments Cube. 
  
```json
{
"Kpis": [{
"FriendlyName": "Poor Trend Month",
"DataModelName": "[KPIValue].Poor Trend Month",
"Description": null
},
{
"FriendlyName": "Poor Rate Trend Month",
"DataModelName": "[KPIValue].Poor Rate Trend Month",
"Description": null
}],
"Dimensions": [{
"Category": "Access Location Pair",
"Attributes": [{
"FriendlyName": "Location Pair",
"DataModelName": "[Access Location Pair].[Location Pair]",
"Description": "Description of Location Pair"
}]
},
{
"Category": "Audio Bandwidth Est",
"Attributes": [{
"FriendlyName": "Metric",
"DataModelName": "[Audio Bandwidth Est].[Metric]",
"Description": "Description of Metric"
}]
}],
"Measurements": [{
"FriendlyName": "Audio Streams Count",
"DataModelName": "[Measures].[Audio Streams Count]",
"Description": "Description of Audio Streams Count"
},
{
"FriendlyName": "Audio Good Streams JPDR Count",
"DataModelName": "[Measures].[Audio Good Streams JPDR Count]",
"Description": "Description of Audio Good Streams JPDR Count"
}]
}
```

 *KPIs*  - Réservé. La section Des KPIs d’une charge utile de demande permet à l’opération Exécuter une requête de renvoyer des valeurs pour les KPIs définis dans le cube. Il n’existe pas encore d’KPIs dans le cube QoE.
  
 *Dimensions*  : liste des dimensions qui peuvent être utilisées dans les sections Filtres et dimensions d’une charge utile de requête pour exécuter une requête. Pour utiliser une dimension dans une expression de filtre, vous devez spécifier un membre de dimension, qui peut être obtenu à l’aide de l’opération Obtenir les membres de dimension.
  
 *Mesures :*  liste des mesures qui peuvent être utilisées dans la section Mesures d’une charge utile de demande pour exécuter une requête.
  

