---
title: Sélectionner les règles de traduction
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.VoiceTrunkSelRule
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 55776a94-4888-4436-a3b6-0e6f8252e392
description: Voix Entreprise exige que toutes les chaînes de numérotation adoptent le format standard E.164 pour des besoins de recherche de numéros inverse. L’homologue de jonction (c’est-à-dire la jonction de passerelle, PBX ou SIP associée) peut exiger que les numéros soient au format de numérotation local. Pour convertir les numéros du format E.164 à un format de numérotation local, vous pouvez définir en option une ou plusieurs règles de conversion pour manipuler l’URI de demande avant de l’acheminer vers l’homologue de jonction. Par exemple, vous pouvez rédiger une règle de traduction pour remplacer « +44 » au début de la chaîne de numérotation par « 0144 ».
ms.openlocfilehash: a6617aca841ec0c2c448a5e642b0250bc3373201
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62410191"
---
# <a name="select-translation-rules"></a>Sélectionner les règles de traduction
 
 Voix Entreprise exige que toutes les chaînes de numérotation adoptent le format standard E.164 pour des besoins de recherche de numéros inverse. L’homologue de jonction (c’est-à-dire la jonction de passerelle, PBX ou SIP associée) peut exiger que les numéros soient au format de numérotation local. Pour convertir les numéros du format E.164 à un format de numérotation local, vous pouvez définir en option une ou plusieurs règles de conversion pour manipuler l’URI de demande avant de l’acheminer vers l’homologue de jonction. Par exemple, vous pouvez rédiger une règle de traduction pour remplacer « +44 » au début de la chaîne de numérotation par « 0144 ».
  
> [!IMPORTANT]
> La possibilité d’associer une ou plusieurs règles de traduction à une configuration de jonction Voix Entreprise peut servir d’alternative à la définition de règles de traduction sur l’homologue de jonction. N’associez pas de règles de traduction avec une configuration de jonction Voix Entreprise si vous avez configuré les règles de traduction sur le pair de jonction, car les deux règles risqueraient de provoquer un conflit. 
  
Pour utiliser une règle de traduction existante, cliquez sur une règle dans la liste, puis sur **OK**.
  
Pour plus d’informations sur les différentes procédures que vous pouvez effectuer à l’aide du Panneau de Skype Entreprise Server, voir [Manage Skype Entreprise Server 2015](../../manage/manage.md).
  

