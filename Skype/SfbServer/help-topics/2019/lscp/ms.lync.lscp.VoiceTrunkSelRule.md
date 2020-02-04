---
title: Sélection des règles de conversion
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.VoiceTrunkSelRule
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 55776a94-4888-4436-a3b6-0e6f8252e392
ROBOTS: NOINDEX, NOFOLLOW
description: Voix entreprise nécessite que toutes les chaînes de numérotation soient normalisées au format E. 164 pour pouvoir effectuer une recherche de numéro inverse (RNL). L’homologue de jonction (c’est-à-dire la jonction de passerelle, PBX ou SIP associée) peut exiger que les numéros soient au format de numérotation local. Pour convertir les numéros du format E.164 à un format de numérotation local, vous avez la possibilité de définir une ou plusieurs règles de conversion pour manipuler l’URI de demande avant de l’acheminer vers la jonction homologue. Par exemple, vous pouvez rédiger une règle de conversion destinée à remplacer le préfixe « +44 » au début de la chaîne de numérotation par « 0144 ».
ms.openlocfilehash: d25e4641673db68332cc52d1771fa1655782eec1
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41690199"
---
# <a name="select-translation-rules"></a>Sélection des règles de conversion
 
 Voix entreprise nécessite que toutes les chaînes de numérotation soient normalisées au format E. 164 pour pouvoir effectuer une recherche de numéro inverse (RNL). L’homologue de jonction (c’est-à-dire la jonction de passerelle, PBX ou SIP associée) peut exiger que les numéros soient au format de numérotation local. Pour convertir les numéros du format E.164 à un format de numérotation local, vous avez la possibilité de définir une ou plusieurs règles de conversion pour manipuler l’URI de demande avant de l’acheminer vers la jonction homologue. Par exemple, vous pouvez rédiger une règle de conversion destinée à remplacer le préfixe « +44 » au début de la chaîne de numérotation par « 0144 ».
  
> [!IMPORTANT]
> La possibilité d’associer une ou plusieurs règles de traduction à une configuration de Trunk vocale d’entreprise est conçue pour être utilisée comme alternative à la configuration de règles de traduction sur l’homologue de Trunk. N’associez pas de règles de traduction à une configuration de Trunk vocale d’entreprise si vous avez configuré des règles de traduction sur le Trunk homologue, car les deux règles peuvent entrer en conflit. 
  
Pour utiliser une règle de conversion existante, sélectionnez une règle dans la liste, puis cliquez sur **OK**.
  
 
  

