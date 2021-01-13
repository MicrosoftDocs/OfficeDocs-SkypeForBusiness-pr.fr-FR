---
title: Création d’un parcage d’appel ou modification d’un parcage existant
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.VoiceFeaCallParkEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e834d485-d25a-4eec-9090-2b8534ecf65d
description: Les plages de numéros de parcier d’appel définissent les numéros temporaires où les appels par parcés sont maintenus jusqu’à ce que quelqu’un les récupère ou qu’ils délai d’arrêt.
ms.openlocfilehash: 5ee0891ebaabc97b965aadc5f1ab1c4390669427
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49819384"
---
# <a name="call-park-create-new-or-edit-existing"></a>Parcage d’appel : créer un nouveau ou modifier un parcage existant

Les plages de numéros de parcier d’appel définissent les numéros temporaires où les appels par parcés sont maintenus jusqu’à ce que quelqu’un les récupère ou qu’ils délai d’arrêt.

## <a name="ui-reference"></a>Référence d’interface utilisateur

La liste suivante décrit les champs de la page.

- **Nom** Tapez un nom descriptif qui identifie la plage de nombres. Une fois que vous avez enregistrez la plage de nombres, ce nom ne peut pas être modifié.

- **Plage de nombres** Dans le premier champ, tapez le numéro de début de la plage de nombres. Dans le deuxième champ, tapez le numéro de fin de la plage de nombres.

  - Le numéro de début de la plage doit être inférieur ou égal au numéro de fin de celle-ci.

  - La valeur du numéro de début de la plage doit avoir la même longueur que celle du numéro de fin.

  - La plage de numéros doit être unique. Cette plage ne peut pas chevaucher une autre plage.

  - Si la plage de nombres commence par le caractère ou #, la plage doit être supérieure \* à 100.

  - Valeurs valides : doit correspondre à la chaîne d’expression régulière ([ \\ *|#]?[ 1-9]\d {0,7} )| ([1-9]\d {0,8} ). Cela signifie que la valeur doit être une chaîne commençant par le caractère ou # ou un nombre de 1 à 9 (le premier caractère ne peut \* pas être un zéro). Si le premier caractère est ou #, le caractère suivant doit être un nombre \* de 1 à 9 (il ne peut pas être un zéro). Les caractères suivants peuvent être n’importe quel nombre de 0 à 9, jusqu’à sept caractères supplémentaires (par exemple, « #6000 », « \* 92000 », « \* 95551212 » et « 915551212 »). Si le premier caractère n’est pas ou #, le premier caractère doit être un nombre de 1 à 9 (il ne peut pas être zéro), suivi de huit caractères au plus, chacun un nombre \* 0 à 9 (par exemple : 915551212;41212;300).

  - Il ne doit pas y avoir plus de 50 000 numéros par pool, au total. Chaque plage de numéros comporte en général un maximum de 100 numéros, mais peut être beaucoup plus grande et comporter jusqu’à 10 000 numéros. Par exemple, au lieu de spécifier « 7 000 000 » comme numéro de début et « 8 000 000 » comme numéro de fin, envisagez de spécifier « 7 000 000 » comme numéro de début et « 7 000 100 » comme numéro de fin.

- **FQDN du serveur de destination** Sélectionnez le nom de domaine complet (FQDN) ou l’ID de service du service d’application qui héberge l’application de parcage d’appel. Tous les appels parés sur des numéros dans la plage spécifiée par le numéro de début et le numéro de fin de la plage de numéros seront acheminés vers ce serveur ou ce pool.

Pour plus d’informations sur les fonctionnalités et fonctionnalités de parcier d’appel, voir [Plan for Call Park in Skype for Business 2015](../../plan-your-deployment/enterprise-voice-solution/call-park.md). Pour plus d’informations sur l’working with Call Park number ranges, see [Configure Phone Number Extensions for Parking Calls](https://technet.microsoft.com/library/fbf97624-9587-42a6-b276-1b69c574a74d.aspx).


