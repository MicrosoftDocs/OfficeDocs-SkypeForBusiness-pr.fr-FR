---
title: Mise en garde d’appels créer ou modifier une existant
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.VoiceFeaCallParkEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e834d485-d25a-4eec-9090-2b8534ecf65d
ROBOTS: NOINDEX, NOFOLLOW
description: Plages de numéros de parcage d’appel définissent les numéros temporaires où mis en garde d’appels sont conservés jusqu'à ce que quelqu'un les récupère ou qu’ils délai d’expiration.
ms.openlocfilehash: 7573b64f93f10d1592d1beba2edf33fef626232b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33890850"
---
# <a name="call-park-create-new-or-edit-existing"></a>Parcage d’appel : création d’un parcage ou modification d’un parcage existant

Plages de numéros de parcage d’appel définissent les numéros temporaires où mis en garde d’appels sont conservés jusqu'à ce que quelqu'un les récupère ou qu’ils délai d’expiration.

## <a name="ui-reference"></a>Référence d’interface utilisateur

La liste ci-dessous décrit les champs de la page.

- **Nom** Tapez un nom descriptif qui identifie la plage de numéros. Une fois que vous enregistrez la plage de numéros, ce nom ne peut pas être modifié.

- **Numéro de plage** Dans le premier champ, tapez le numéro de début de la plage de numéros. Dans le deuxième champ, tapez le numéro de fin de la plage de numéros.

  - Le numéro de début de la plage doit être inférieur ou égal au numéro de fin de cette plage.

  - La valeur du numéro de début de la plage doit être de même longueur que celle du numéro de fin.

  - La plage de numéros doit être unique. Cette plage ne peut pas chevaucher une autre plage.

  - Si la plage de numéros commence par le caractère \* ou #, la plage doit être supérieure à 100.

  - Valeurs valides : doit correspondre à la chaîne d’expression régulière ([\\* | #] ? [1-9] \d{0,7}) | (\d [1-9]{0,8}). Cela signifie que la valeur doit être une chaîne commençant par un caractère \* ou # ou un nombre de 1 à 9 (le premier caractère ne peut pas être zéro). Si le premier caractère est \* ou #, le caractère qui suit doit être un nombre de 1 à 9 (il ne peut pas être zéro). Les caractères suivants peuvent être n’importe quel nombre entre 0 et 9, jusqu'à sept caractères supplémentaires (par exemple, « #6000 », «\*92000"«\*95551212" et « 915551212 »). Si le premier caractère n’est pas \* ou #, le premier caractère doit être un nombre de 1 à 9 (il ne peut pas être égal à zéro), suivi de huit caractères, chaque un numéro de 0 à 9 (par exemple : 915551212 ; 41212 ; 300).

  - En tout, il ne doit pas y avoir plus de 50 000 numéros par pool. Chaque plage de numéros comporte en général un maximum de 100 numéros, mais peut être beaucoup plus importante et inclure jusqu’à 10 000 numéros. Par exemple, au lieu de spécifier « 7 000 000 » comme numéro de début et « 8 000 000 » comme numéro de fin, envisagez de spécifier « 7 000 000 » comme numéro de début et « 7 000 100 » comme numéro de fin.

- **Nom de domaine complet du serveur de destination** Sélectionnez le nom de domaine complet (FQDN) ou ID de service du service d’Application qui héberge l’application de parcage d’appel. Mise en garde de tous les appels de numéros dans la plage spécifiée par le numéro de départ et numéro de fin dans la plage de numéros est acheminé vers ce serveur ou ce pool.

Pour plus d’informations sur les fonctionnalités de parcage d’appel, voir [planifier la mise en garde d’appels dans Skype pour les entreprises](../../../plan-your-deployment/enterprise-voice-solution/call-park.md). Pour plus d’informations sur l’utilisation des plages de numéros de parcage d’appel, voir [Configurer les Extensions numéro de téléphone pour les appels parcage](https://technet.microsoft.com/library/fbf97624-9587-42a6-b276-1b69c574a74d.aspx).


