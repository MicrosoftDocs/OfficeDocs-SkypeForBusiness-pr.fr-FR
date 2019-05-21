---
title: Parking ou modifier un nouveau parc d’appels
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.VoiceFeaCallParkEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e834d485-d25a-4eec-9090-2b8534ecf65d
ROBOTS: NOINDEX, NOFOLLOW
description: Les plages de numéros de parc d’appels définissent les numéros temporaires dans lesquels les appels en attente sont maintenus jusqu’à ce qu’une personne les récupère ou le délai d’expiration.
ms.openlocfilehash: 7257327081be46f343ef8aeb6076ad9a788f46bb
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34290169"
---
# <a name="call-park-create-new-or-edit-existing"></a>Parcage d’appel : création d’un parcage ou modification d’un parcage existant

Les plages de numéros de parc d’appels définissent les numéros temporaires dans lesquels les appels en attente sont maintenus jusqu’à ce qu’une personne les récupère ou le délai d’expiration.

## <a name="ui-reference"></a>Référence d’interface utilisateur

La liste ci-dessous décrit les champs de la page.

- **Nom** Tapez un nom descriptif identifiant la plage de nombres. Ce nom ne peut pas être modifié après enregistrement de la plage de nombres.

- **Plage de nombres** Dans le premier champ, tapez le nombre de début de la plage de nombres. Dans le deuxième champ, tapez le nombre de fin de la plage de nombres.

  - Le numéro de début de la plage doit être inférieur ou égal au numéro de fin de cette plage.

  - La valeur du numéro de début de la plage doit être de même longueur que celle du numéro de fin.

  - La plage de numéros doit être unique. Cette plage ne peut pas chevaucher une autre plage.

  - Si la plage numérique commence par le caractère \* ou #, la plage doit être supérieure à 100.

  - Valeurs valides: doit correspondre à la chaîne d’expression\\normale ([* | #] ? [1-{0,7}9] \d) | ([1-9] \d{0,8}). Cela signifie que la valeur doit être une chaîne commençant par le caractère \* ou # ou par un nombre 1 à 9 (le premier caractère ne peut pas être zéro). Si le premier caractère est \* ou #, le caractère suivant doit être un nombre 1 à 9 (il ne peut pas être zéro). Les caractères suivants peuvent être n’importe quelle valeur comprise entre 0 et 9 (par exemple, "#6000"\*, "92000"\*, "95551212" et "915551212"). Si le premier caractère n’est \* pas ou #, le premier caractère doit être un nombre compris entre 1 et 9 (il ne peut pas être zéro), suivi de huit caractères maximum (par exemple: 915551212; 41212; 300).

  - En tout, il ne doit pas y avoir plus de 50 000 numéros par pool. Chaque plage de numéros comporte en général un maximum de 100 numéros, mais peut être beaucoup plus importante et inclure jusqu’à 10 000 numéros. Par exemple, au lieu de spécifier « 7 000 000 » comme numéro de début et « 8 000 000 » comme numéro de fin, envisagez de spécifier « 7 000 000 » comme numéro de début et « 7 000 100 » comme numéro de fin.

- **Nom de domaine complet du serveur de destination** Sélectionnez le nom de domaine complet (FQDN) ou l’ID de service du service d’application qui héberge l’application de parc d’appels. Le nombre d’appels dans la plage spécifiée par le numéro de début et le numéro de fin dans la plage de numéros est acheminé vers ce serveur ou pool.

Pour plus d’informations sur les fonctionnalités et les fonctionnalités de stationnement d’appels, reportez-vous à la rubrique [planification du parc d’appels dans Skype entreprise](../../../plan-your-deployment/enterprise-voice-solution/call-park.md). Pour plus d’informations sur l’utilisation des plages de numéros de parc d’appels, voir [configurer les extensions de numéro de téléphone pour les appels en stationnement](https://technet.microsoft.com/library/fbf97624-9587-42a6-b276-1b69c574a74d.aspx).


