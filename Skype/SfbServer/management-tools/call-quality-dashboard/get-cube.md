---
title: Obtenir un cube
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
ms.assetid: c8eeb387-dc1e-44e0-bbf9-a566f8bda551
description: 'Résumé : Découvrez l’opération obtenir le cube, qui fait partie de l’API de données du tableau de bord de qualité des appels. Le tableau de bord de qualité des appels est un outil pour Skype entreprise Server.'
ms.openlocfilehash: 1d8327439d79e7d02182dc7195bc0052bf6c923c
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888823"
---
# <a name="get-cube"></a>Obtenir un cube
 
**Résumé :** Apprenez-en davantage sur l’opération obtenir le cube, qui fait partie de l’API de données du tableau de bord de qualité des appels. Le tableau de bord de qualité des appels est un outil pour Skype entreprise Server.
  
L’opération obtenir le cube fait partie de l’API de données du tableau de bord de qualité des appels.
  
## <a name="get-cube"></a>Obtenir un cube

L’opération obtenir un cube renvoie la liste des dimensions et mesures disponibles.
  

|**Méthode**|**URI de la requête**|**Version HTTP**|
|:-----|:-----|:-----|
|Télécharger  <br/> |https://\<Portal\>/QoEDataService/CubeStructure  <br/> |HTTP/1.1  <br/> |
   
 **Paramètres d’URI** -aucun.
  
 **En-têtes de requête** -aucun en-tête supplémentaire.
  
 Le corps de la **requête** .
  
 **Réponse** : la réponse comprend un code d’État http et un ensemble d’en-têtes de réponse.
  
 **Code d’État** -une opération réussie renvoie le code d’état 200 (OK).
  
 **En-têtes de réponse** : aucun en-tête supplémentaire.
  
 Le corps de la **réponse** : Voici un exemple de charge utile de réponse dans JSON.
  
> [!NOTE]
> Cet exemple n’affiche que les deux premiers éléments de chaque groupe d’éléments cube. 
  
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

 *KPI* -réservé. La section KPI d’une charge utile de requête permet d’exécuter une requête afin de renvoyer des valeurs pour les indicateurs de performance clés définis dans le cube. Aucun KPI n’existe encore dans le cube QoE.
  
 *Dimensions* : liste des dimensions pouvant être utilisées dans les sections filtres et axes d’une charge utile de requête pour une opération d’exécution de requête. Pour utiliser une dimension dans une expression de filtre, vous devez spécifier un membre de dimension, qui peut être obtenu à l’aide de l’opération obtenir les membres de la dimension.
  
 *Mesures* : liste des mesures qui pourraient être utilisées dans la section mesures d’une charge utile de requête pour une opération d’exécution de requête.
  

