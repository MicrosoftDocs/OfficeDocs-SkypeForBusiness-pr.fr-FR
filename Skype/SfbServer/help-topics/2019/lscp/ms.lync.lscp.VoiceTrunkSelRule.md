---
title: Sélection des règles de conversion
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.VoiceTrunkSelRule
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 55776a94-4888-4436-a3b6-0e6f8252e392
description: Voix entreprise requiert que toutes les chaînes de numérotation normaliser au format E.164 pour effectuer la recherche inversée de numéros (RNL). L’homologue de jonction (c’est-à-dire la jonction de passerelle, PBX ou SIP associée) peut exiger que les numéros soient au format de numérotation local. Pour convertir les numéros du format E.164 à un format de numérotation local, vous avez la possibilité de définir une ou plusieurs règles de conversion pour manipuler l’URI de demande avant de l’acheminer vers la jonction homologue. Par exemple, vous pouvez rédiger une règle de conversion destinée à remplacer le préfixe « +44 » au début de la chaîne de numérotation par « 0144 ».
ms.openlocfilehash: 326d56aea92bf63e9ea813d91d2a3f7c816bce48
ms.sourcegitcommit: b42a6a56a0e1e4be1239174c1c3b4ab86517d043
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/26/2018
ms.locfileid: "20044508"
---
# <a name="select-translation-rules"></a>Sélection des règles de conversion
 
 Voix entreprise requiert que toutes les chaînes de numérotation normaliser au format E.164 pour effectuer la recherche inversée de numéros (RNL). L’homologue de jonction (c’est-à-dire la jonction de passerelle, PBX ou SIP associée) peut exiger que les numéros soient au format de numérotation local. Pour convertir les numéros du format E.164 à un format de numérotation local, vous avez la possibilité de définir une ou plusieurs règles de conversion pour manipuler l’URI de demande avant de l’acheminer vers la jonction homologue. Par exemple, vous pouvez rédiger une règle de conversion destinée à remplacer le préfixe « +44 » au début de la chaîne de numérotation par « 0144 ».
  
> [!IMPORTANT]
> La possibilité d’associer une ou plusieurs règles de traduction à une configuration de jonction Enterprise Voice est destinée à être utilisé en guise d’alternative à la configuration des règles de traduction sur l’homologue de jonction. N’associez pas de règles de traduction à une configuration de jonction Enterprise Voice si vous avez configuré les règles de traduction sur l’homologue de jonction, car les deux règles peuvent entrer en conflit. 
  
Pour utiliser une règle de conversion existante, sélectionnez une règle dans la liste, puis cliquez sur **OK**.
  
 
  

