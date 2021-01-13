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
ms.openlocfilehash: 15bf482412973fe4b3a0178be6ecdcc593c762e7
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821374"
---
# <a name="videometricsthreshold-table"></a>Table VideoMetricsThreshold
 
La table VideoMetricsThreshold contient des valeurs optimales et acceptables pour les mesures de la qualité de l’expérience utilisées dans les appels vidéo.
  

| **Colonne**                                               | **Type de données**       | **Clé/Index**  | **Details**                          |
|:---------------------------------------------------------|:--------------------|:---------------|:-------------------------------------|
| **CallType** <br/>                                       | int  <br/>          | Primaire  <br/> | Type d’appel passé.  <br/> |
| **VideoPostFECPLROptimal** <br/>                         | décimal(5,2)  <br/> |                | La valeur par défaut est 0,05.  <br/>    |
| **VideoPostFECPLRAcceptable** <br/>                      | décimal(5,2)  <br/> |                | La valeur par défaut est 0,10.  <br/>    |
| **VideoLocalFrameLostPercentageAverageOptimal** <br/>    | décimal(5,2)  <br/> |                | La valeur par défaut est 5,0.  <br/>     |
| **VideoLocalFrameLostPercentageAverageAcceptable** <br/> | décimal(5,2)  <br/> |                | La valeur par défaut est 10,0.  <br/>    |
| **RecvFrameRateAverageOptimal** <br/>                    | decimal(9,4)  <br/> |                | La valeur par défaut est 12,0000.  <br/> |
| **RecvFramerateAverageAcceptable** <br/>                 | decimal(9,4)  <br/> |                | La valeur par défaut est 7,0000.  <br/>  |
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

