---
title: Table VideoMetricsThreshold
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 2e2f4711-35ba-48c6-b15b-5aba61c4eb75
description: La table VideoMetricsThreshold contient des valeurs optimales et acceptables pour les métriques de qualité de l’utilisation des appels vidéo.
ms.openlocfilehash: 89d3095ef7222cacc7633116c43d66cbcc2be2e2
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41804734"
---
# <a name="videometricsthreshold-table"></a>Table VideoMetricsThreshold
 
La table VideoMetricsThreshold contient des valeurs optimales et acceptables pour les métriques de qualité de l’utilisation des appels vidéo.
  

| **Colonne**                                               | **Type de données**       | **Clé/Index**  | **Détails**                          |
|:---------------------------------------------------------|:--------------------|:---------------|:-------------------------------------|
| **CallType** <br/>                                       | int  <br/>          | Principal  <br/> | Type d’appel placé.  <br/> |
| **VideoPostFECPLROptimal** <br/>                         | décimale (5 ; 2)  <br/> |                | La valeur par défaut est 0,05.  <br/>    |
| **VideoPostFECPLRAcceptable** <br/>                      | décimale (5 ; 2)  <br/> |                | La valeur par défaut est 0,10.  <br/>    |
| **VideoLocalFrameLostPercentageAverageOptimal** <br/>    | décimale (5 ; 2)  <br/> |                | La valeur par défaut est 5,0.  <br/>     |
| **VideoLocalFrameLostPercentageAverageAcceptable** <br/> | décimale (5 ; 2)  <br/> |                | La valeur par défaut est 10,0.  <br/>    |
| **RecvFrameRateAverageOptimal** <br/>                    | décimale (9 ; 4)  <br/> |                | La valeur par défaut est 12,0000.  <br/> |
| **RecvFramerateAverageAcceptable** <br/>                 | décimale (9 ; 4)  <br/> |                | La valeur par défaut est 7,0000.  <br/>  |
| **LowFrameRateCallPercentOptimal** <br/>                 | décimale (5 ; 2)  <br/> |                | La valeur par défaut est 5,0.  <br/>     |
| \****LowFrameRateCallPercentAcceptable***\* <br/>        | décimale (5 ; 2)  <br/> |                | La valeur par défaut est 10.0/  <br/>    |
| **LowResolutionCallPercentOptimal** <br/>                | décimale (5 ; 2)  <br/> |                | La valeur par défaut est 5,0.  <br/>     |
| **LowResolutionCallPercentAcceptable** <br/>             | décimale (5 ; 2)  <br/> |                | La valeur par défaut est 10,0.  <br/>    |
| **VideoPacketLossRateOptimal** <br/>                     | foat  <br/>         |                | La valeur par défaut est 0,05.  <br/>    |
| **VideoPacketLossRateAcceptable** <br/>                  | float  <br/>        |                | La valeur par défaut est 0,10.  <br/>    |
| **VideoFrameRateAvgOptimal** <br/>                       | float  <br/>        |                | La valeur par défaut est 12.  <br/>      |
| **VideoFrameRateAvgAcceptable** <br/>                    | float  <br/>        |                | La valeur par défaut est 7.  <br/>       |
| **DynamicCapabilityPercentOptimal** <br/>                | décimale (5 ; 2)  <br/> |                | La valeur par défaut est 5,00.  <br/>    |
| **DynamicCapabilityPercentAcceptable** <br/>             | décimale (5 ; 2)  <br/> |                | La valeur par défaut est 10,00.  <br/>   |

