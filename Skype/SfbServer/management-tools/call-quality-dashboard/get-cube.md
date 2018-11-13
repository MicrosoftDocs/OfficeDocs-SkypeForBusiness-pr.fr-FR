---
title: Obtenir le Cube
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c8eeb387-dc1e-44e0-bbf9-a566f8bda551
description: 'Résumé : Découvrez l’opération obtenir un Cube, qui fait partie de l’API de données pour le tableau de bord qualité des appels. Tableau de bord de qualité des appels est un outil de Skype pour Business Server 2015.'
ms.openlocfilehash: 9c31650a5dc5471e0d5ad2dcdbf2214b16d91c56
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/13/2018
ms.locfileid: "26294435"
---
# <a name="get-cube"></a>Obtenir le Cube
 
**Résumé :** Obtenir des informations sur l’opération obtenir un Cube, qui fait partie de l’API de données pour le tableau de bord qualité des appels. Tableau de bord de qualité des appels est un outil de Skype pour Business Server 2015.
  
L’opération obtenir le Cube fait partie de l’API de données pour le tableau de bord qualité des appels.
  
## <a name="get-cube"></a>Obtenir le Cube

Opération de Cube Get renvoie la liste des dimensions disponibles et des mesures.
  

|**Méthode**|**URI de la demande**|**Version HTTP**|
|:-----|:-----|:-----|
|Télécharger  <br/> |https://\<portal\>/QoEDataService/CubeStructure  <br/> |HTTP/1.1.  <br/> |
   
 **Paramètres d’URI** - None.
  
 **En-têtes de demande** - aucun en-tête supplémentaire.
  
 **Corps de requête** - None.
  
 **Réponse** - la réponse inclut un code d’état HTTP et un ensemble d’en-têtes de réponse.
  
 **Code d’état** - une opération réussie retourne un code d’état 200 (OK).
  
 **En-têtes de réponse** - aucun en-tête supplémentaire.
  
 **Corps de réponse** - vous trouverez ci-dessous une charge utile d’exemple réponse au format JSON.
  
> [!NOTE]
> Cet exemple affiche uniquement les deux premiers éléments de chaque groupes d’éléments de Cube. 
  
```
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

 *Indicateurs de performance clés* - en réservé. La section des indicateurs de performance clés d’une charge utile de demande permet exécuter la requête renvoyer des valeurs pour les indicateurs de performance clés définis dans le cube. Aucun indicateurs de performance clés n’existent encore dans le QoE Cube.
  
 *Dimensions* - la liste des dimensions qui peut être utilisé dans les sections de filtres et les Dimensions d’une charge utile de demande pour l’opération d’exécuter la requête. Pour utiliser une dimension dans une expression de filtre, vous devez spécifier un membre de dimension, qui peut être obtenu à l’aide d’opération obtenir les membres de Dimension.
  
 *Des mesures* - la liste des mesures pouvant être utilisées dans la section mesures d’une charge utile de demande pour l’opération d’exécuter la requête.
  

