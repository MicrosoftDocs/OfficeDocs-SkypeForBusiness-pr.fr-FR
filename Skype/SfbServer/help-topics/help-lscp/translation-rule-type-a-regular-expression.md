---
title: Règle de traduction Tapez une expression régulière
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.VoiceRuleRegexEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5ee83724-b399-4f8d-8f6d-4b53a26296b4
description: Dans le champ Suivre ce modèle, spécifiez le modèle qui sera utilisé pour correspondre aux numéros à traduire. Dans le champ Règle de traduction, spécifiez un modèle pour le format des numéros traduits. Par exemple, si vous entrez ^ (\d \d+)$ dans le champ Suivre ce modèle et \+ 011$1 dans le champ règle de traduction, la règle traduit +441235551010 en {9} 011441235551010.
ms.openlocfilehash: 294a179056455ee5d0d256bf6feeb1f39f52664fcf61d785649154f6c3290549
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54338332"
---
# <a name="translation-rule-type-a-regular-expression"></a>Règle de traduction : taper une expression régulière
 
Dans le champ **Suivre ce modèle**, spécifiez le modèle qui sera utilisé pour correspondre aux numéros à traduire. Dans le champ **Règle de traduction**, spécifiez un modèle pour le format des numéros traduits. Par exemple, si vous entrez ^ (\d \d+)$ dans le champ Suivre ce modèle et \+ {9} 011$1   dans le champ règle de traduction, la règle traduit +441235551010 en 011441235551010.
  
Pour plus d’informations sur les différentes procédures que vous pouvez effectuer à l’aide du Panneau de Skype Entreprise Server, voir [Manage Skype Entreprise Server 2015](../../manage/manage.md).
  

