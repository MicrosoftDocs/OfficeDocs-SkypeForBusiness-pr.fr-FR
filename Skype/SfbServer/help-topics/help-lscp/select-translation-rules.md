---
title: Sélection des règles de conversion
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.VoiceTrunkSelRule
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 55776a94-4888-4436-a3b6-0e6f8252e392
description: Voix entreprise nécessite que toutes les chaînes de numérotation soient normalisées au format E. 164 pour pouvoir effectuer une recherche de numéro inverse (RNL). L’homologue de jonction (c’est-à-dire la jonction de passerelle, PBX ou SIP associée) peut exiger que les numéros soient au format de numérotation local. Pour convertir les numéros du format E.164 à un format de numérotation local, vous avez la possibilité de définir une ou plusieurs règles de conversion pour manipuler l’URI de demande avant de l’acheminer vers la jonction homologue. Par exemple, vous pouvez rédiger une règle de conversion destinée à remplacer le préfixe « +44 » au début de la chaîne de numérotation par « 0144 ».
ms.openlocfilehash: 89505dda4bb534ad62455bf1fd835efb81ce6f0b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34293297"
---
# <a name="select-translation-rules"></a>Sélection des règles de conversion
 
 Voix entreprise nécessite que toutes les chaînes de numérotation soient normalisées au format E. 164 pour pouvoir effectuer une recherche de numéro inverse (RNL). L’homologue de jonction (c’est-à-dire la jonction de passerelle, PBX ou SIP associée) peut exiger que les numéros soient au format de numérotation local. Pour convertir les numéros du format E.164 à un format de numérotation local, vous avez la possibilité de définir une ou plusieurs règles de conversion pour manipuler l’URI de demande avant de l’acheminer vers la jonction homologue. Par exemple, vous pouvez rédiger une règle de conversion destinée à remplacer le préfixe « +44 » au début de la chaîne de numérotation par « 0144 ».
  
> [!IMPORTANT]
> La possibilité d’associer une ou plusieurs règles de traduction à une configuration de Trunk vocale d’entreprise est conçue pour être utilisée comme alternative à la configuration de règles de traduction sur l’homologue de Trunk. N’associez pas de règles de traduction à une configuration de Trunk vocale d’entreprise si vous avez configuré des règles de traduction sur le Trunk homologue, car les deux règles peuvent entrer en conflit. 
  
Pour utiliser une règle de conversion existante, sélectionnez une règle dans la liste, puis cliquez sur **OK**.
  
Pour plus d’informations sur les différentes procédures que vous pouvez effectuer à l’aide du panneau de configuration Skype entreprise Server, reportez-vous à la rubrique [gestion de Skype entreprise server 2015](../../manage/manage.md).
  

