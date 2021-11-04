---
title: Table VideoMetricsThreshold
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 2e2f4711-35ba-48c6-b15b-5aba61c4eb75
description: La table VideoMetricsThreshold contient des valeurs optimales et acceptables pour les mesures de la qualité de l’expérience utilisées dans les appels vidéo.
ms.openlocfilehash: 08ebc41fd49fc29583059aa03601f9acc384c822
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60741780"
---
# <a name="videometricsthreshold-table"></a>Table VideoMetricsThreshold
 
La table VideoMetricsThreshold contient des valeurs optimales et acceptables pour les mesures de la qualité de l’expérience utilisées dans les appels vidéo.
  

| **Colonne**                                               | **Type de données**       | **Clé/Index**  | **Détails**                          |
|:---------------------------------------------------------|:--------------------|:---------------|:-------------------------------------|
| **CallType** <br/>                                       | int  <br/>          | Primaire  <br/> | Type d’appel passé.  <br/> |
| **VideoPostFECPLROptimal** <br/>                         | décimal(5,2)  <br/> |                | La valeur par défaut est 0,05.  <br/>    |
| **VideoPostFECPLRAcceptable** <br/>                      | décimal(5,2)  <br/> |                | La valeur par défaut est 0,10.  <br/>    |
| **VideoLocalFrameLostPercentageAverageOptimal** <br/>    | décimal(5,2)  <br/> |                | La valeur par défaut est 5,0.  <br/>     |
| **VideoLocalFrameLostPercentageAverageAcceptable** <br/> | décimal(5,2)  <br/> |                | La valeur par défaut est 10,0.  <br/>    |
| **RecvFrameRateAverageOptimal** <br/>                    | décimal(9,4)  <br/> |                | La valeur par défaut est 12,0000.  <br/> |
| **RecvFramerateAverageAcceptable** <br/>                 | décimal(9,4)  <br/> |                | La valeur par défaut est 7,0000.  <br/>  |
| **LowFrameRateCallPercentOptimal** <br/>                 | décimal(5,2)  <br/> |                | La valeur par défaut est 5,0.  <br/>     |
| \****LowFrameRateCallPercentAcceptable** _\_ <br/>        | décimal(5,2)  <br/> |                | La valeur par défaut est 10,0/  <br/>    |
| **LowResolutionCallPercentOptimal** <br/>                | décimal(5,2)  <br/> |                | La valeur par défaut est 5,0.  <br/>     |
| **LowResolutionCallPercentAcceptable** <br/>             | décimal(5,2)  <br/> |                | La valeur par défaut est 10,0.  <br/>    |
| **VideoPacketLossRateOptimal** <br/>                     | foat  <br/>         |                | La valeur par défaut est 0,05.  <br/>    |
| **VideoPacketLossRateAcceptable** <br/>                  | float  <br/>        |                | La valeur par défaut est 0,10.  <br/>    |
| **VideoFrameRateAvgOptimal** <br/>                       | float  <br/>        |                | La valeur par défaut est 12.  <br/>      |
| **VideoFrameRateAvgAcceptable** <br/>                    | float  <br/>        |                | La valeur par défaut est 7.  <br/>       |
| **DynamicCapabilityPercentOptimal** <br/>                | décimal(5,2)  <br/> |                | La valeur par défaut est 5,00.  <br/>    |
| **DynamicCapabilityPercentAcceptable** <br/>             | décimal(5,2)  <br/> |                | La valeur par défaut est 10,00.  <br/>   |

