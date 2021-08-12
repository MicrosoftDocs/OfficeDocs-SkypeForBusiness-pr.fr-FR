---
title: Table VideoMetricsThreshold
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 2e2f4711-35ba-48c6-b15b-5aba61c4eb75
description: La table VideoMetricsThreshold contient des valeurs optimales et acceptables pour les mesures de la qualité de l’expérience utilisées dans les appels vidéo.
ms.openlocfilehash: 1885e1d5bfbea10ffed518aaedcc8bf47a2b5217c333c187eaf2a2ee0dc7b0d2
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54340000"
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

