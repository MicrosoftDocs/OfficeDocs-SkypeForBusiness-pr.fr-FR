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
ms.openlocfilehash: 7d835669f0acc7cd2a2e42acb1aa9fa9d2fdf765
ms.sourcegitcommit: 26d93a15c9d4704c08f3fabc5635839ce2456b2d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/06/2018
ms.locfileid: "20205077"
---
# <a name="what-are-the-special-character-restrictions-in-teams-policies"></a>Quelles sont les restrictions de caractère spécial dans les stratégies d’équipes ?

**Bien que les caractères spéciaux peuvent être utilisés pour créer des stratégies d’équipes avec PowerShell, vous serez limité dans la gestion de ces stratégies.  Par conséquent, nous vous recommandons vivement de noms de stratégies n’incluent pas de caractères spéciaux.**

Les noms de stratégie que vous créez à l’aide de PowerShell pour les réunions et de conversation dans les équipes peuvent avoir des caractères spéciaux tels que @, #, $. Toutefois, si vous souhaitez modifier la stratégie dans le Microsoft Teams et Skype entreprise centre d’administration, vous ne pourrez. Vous devez utiliser Windows PowerShell et l’applet de commande stratégie correcte pour apporter des modifications.

Si vous disposez d’un objet de stratégie avec des caractères spéciaux et que vous souhaitez supprimer les caractères spéciaux afin de mieux gérer la stratégie dans le Microsoft Teams et Skype entreprise centre d’administration, vous devez utiliser la procédure ci-dessous. 

Remarque : La procédure articulée ici utilise l’exemple d’une stratégie de messagerie.  Le même processus doit être utilisé pour un autre type de stratégie (par exemple de réunions) en subsituting les applets de commande pertinents. 

1.) appeler Get-CSMessagingPolicy-identity < ancien_nom_stratégie > et la capture de la sortie de la stratégie.
2.) appeler Set-CSMessagingPolicy-identity < nouveau_nom_stratégie > pour créer une nouvelle stratégie avec la même configuration que la stratégie d’origine, mais sans caractères spéciaux dans le nom.
3.) appel Delete-CSMessagingPolicy-identity < ancien_nom_stratégie > pour supprimer la stratégie.  Si cette commande réussit, vous avez terminé et vous pouvez commencer à affecter des utilisateurs à la nouvelle stratégie à l’aide de PowerShell ou les Microsoft Teams et Skype entreprise centre d’administration.
4.) si la commande ci-dessus n’aboutit pas, il est, car l’ancienne stratégie a été affecté à un utilisateur.  Exécuter annuler l’affectation d’applet de commande pour annuler l’affectation de la stratégie de l’utilisateur, affecter la nouvelle stratégie, puis réexécutez dwlete.


