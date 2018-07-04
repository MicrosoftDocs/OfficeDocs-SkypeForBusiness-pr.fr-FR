---
title: Quelles sont les restrictions de caractère spécial dans les stratégies d’équipes ?
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
f1keywords:
- me.teamsadmincenter.policies.naming.error
description: Voir existe avec des caractères spéciaux dans les noms des stratégies et ce que vous pouvez faire pour résoudre des problèmes.
ms.openlocfilehash: 43e2daba187bb3a381fe617e088518129d918d09
ms.sourcegitcommit: 2b15226723c299fe94f1a012aa21222173fe3af8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/03/2018
ms.locfileid: "20192163"
---
# <a name="what-are-the-special-character-restrictions-in-teams-policies"></a>Quelles sont les restrictions de caractère spécial dans les stratégies d’équipes ?

**Bien que vous pouvez utiliser des caractères spéciaux dans les noms de stratégies que vous avez créé dans les équipes, il est vivement recommandé que vous n’avez pas.**

Les noms de stratégie que vous créez pour les réunions, les conversations et prescense, et autres éléments dans les équipes peuvent avoir des caractères spéciaux tels que @, #, $. Toutefois, si vous souhaitez apporter des modifications sur le nom des Skype Teams Microsoft Business centre d’administration, vous ne pourrez. Vous devez utiliser Windows PowerShell et l’applet de commande stratégie correcte pour apporter des modifications.

Par exemple, si vous disposez d’une stratégie de réunion avec des caractères spéciaux et que vous souhaitez modifier le nom ou supprimer les caractères spéciaux à partir du nom, vous devez utiliser l’applet de commande Set-CsMeetingPolicy. 

Voici une liste des applets de commande stratégie que vous devrez peut-être effectuer cette opération :
1. Set-CsMeetingPolicy
2. Set-CsAppPolicy
3. Set-*


