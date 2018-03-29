---
title: Sélection des règles de conversion
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/24/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.VoiceTrunkSelRule
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 55776a94-4888-4436-a3b6-0e6f8252e392
description: Voix Entreprise requiert que toutes les chaînes de connexion à être normalisé au format E.164 pour effectuer la recherche de numéro inversée (RNL). L’homologue de jonction (c’est-à-dire la jonction de passerelle, PBX ou SIP associée) peut exiger que les numéros soient au format de numérotation local. Pour convertir les numéros du format E.164 à un format de numérotation local, vous avez la possibilité de définir une ou plusieurs règles de conversion pour manipuler l’URI de demande avant de l’acheminer vers la jonction homologue. Par exemple, vous pouvez rédiger une règle de conversion destinée à remplacer le préfixe « +44 » au début de la chaîne de numérotation par « 0144 ».
ms.openlocfilehash: ab2a39442ce41f96769668d19de0694d4a464a4b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="select-translation-rules"></a>Sélection des règles de conversion
 
 Voix Entreprise requiert que toutes les chaînes de connexion à être normalisé au format E.164 pour effectuer la recherche de numéro inversée (RNL). L’homologue de jonction (c’est-à-dire la jonction de passerelle, PBX ou SIP associée) peut exiger que les numéros soient au format de numérotation local. Pour convertir les numéros du format E.164 à un format de numérotation local, vous avez la possibilité de définir une ou plusieurs règles de conversion pour manipuler l’URI de demande avant de l’acheminer vers la jonction homologue. Par exemple, vous pouvez rédiger une règle de conversion destinée à remplacer le préfixe « +44 » au début de la chaîne de numérotation par « 0144 ».
  
> [!IMPORTANT]
> Permet d’associer une ou plusieurs règles de traduction avec une configuration de jonction de Voix Entreprise est destinée à être utilisée comme alternative à la configuration des règles de traduction sur l’homologue du tronc. N’associez pas de règles de traduction à une configuration de jonction de Voix Entreprise si vous avez configuré des règles de traduction sur l’homologue du tronc, car les deux règles peuvent entrer en conflit. 
  
Pour utiliser une règle de conversion existante, sélectionnez une règle dans la liste, puis cliquez sur **OK**.
  
Pour plus d’informations sur les différentes procédures que vous pouvez effectuer à l’aide de la Skype pour Business Server du Panneau de configuration, voir [Gérer les Skype pour Business Server 2015](../../manage/manage.md).
  

