---
title: Appel Park, créer ou modifier une existante
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/24/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.VoiceFeaCallParkEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e834d485-d25a-4eec-9090-2b8534ecf65d
description: Les plages de numéros appel Park définissent les numéros temporaires où sont conservés les appels en stationnement jusqu'à ce qu’une personne récupère les ou délai d’attente.
ms.openlocfilehash: 840caf654e1264d7355f117303e8ded9efbca7d3
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="call-park-create-new-or-edit-existing"></a>Parcage d’appel : création d’un parcage ou modification d’un parcage existant
 
Les plages de numéros appel Park définissent les numéros temporaires où sont conservés les appels en stationnement jusqu'à ce qu’une personne récupère les ou délai d’attente.
  
## <a name="ui-reference"></a>Référence d’interface utilisateur

La liste ci-dessous décrit les champs de la page.
  
- **Nom** Tapez un nom descriptif qui identifie la plage de numéros. Après avoir enregistré la plage de numéros, ce nom ne peut pas être modifié.
    
- **Numéro de gamme** Dans le premier champ, tapez le numéro de début de la plage de numéros. Dans le second champ, tapez le numéro de fin de la plage de numéros.
    
  - Le numéro de début de la plage doit être inférieur ou égal au numéro de fin de cette plage.
    
  - La valeur du numéro de début de la plage doit être de même longueur que celle du numéro de fin.
    
  - La plage de numéros doit être unique. Cette plage ne peut pas chevaucher une autre plage.
    
  - Si la plage de numéros commence par le caractère \* ou #, la plage doit être supérieure à 100.
    
  - Valeurs valides : doit correspondre à la chaîne d’expression régulière ([\\* | #] ?[1-9]\d{0,7}) | ([1-9] \d 0,8 {}). Cela signifie que la valeur doit être une chaîne commençant par un caractère \* ou # ou un nombre de 1 à 9 (le premier caractère ne peut pas être un zéro). Si le premier caractère est \* ou #, le caractère suivant doit être un nombre de 1 à 9 (il ne peut pas être un zéro). Les autres caractères peuvent être n’importe quel nombre de 0 à 9 jusqu'à sept caractères supplémentaires (par exemple, « #6000 », «\*92000","\*95551212" et « 915551212 »). Si le premier caractère n’est pas \* ou #, le premier caractère doit être un numéro de 1 à 9 (il ne peut pas être égal à zéro), suivi de huit caractères, chaque un nombre de 0 à 9 (par exemple : 915551212 ; 41212 ; 300).
    
  - En tout, il ne doit pas y avoir plus de 50 000 numéros par pool. Chaque plage de numéros comporte en général un maximum de 100 numéros, mais peut être beaucoup plus importante et inclure jusqu’à 10 000 numéros. Par exemple, au lieu de spécifier « 7 000 000 » comme numéro de début et « 8 000 000 » comme numéro de fin, envisagez de spécifier « 7 000 000 » comme numéro de début et « 7 000 100 » comme numéro de fin.
    
- **Nom de domaine complet du serveur de destination** Sélectionnez le nom de domaine pleinement qualifié (FQDN) ou l’ID du service d’Application qui héberge l’application Park de l’appel de service. Tous les appels calée en nombres dans une plage spécifiée par le numéro de départ et numéro de fin de la plage de numéros est routé vers ce serveur ou le pool.
    
Pour plus d’informations sur les fonctionnalités d’appel Park de, voir [planification de parc d’appel dans Skype pour entreprise 2015](../../plan-your-deployment/enterprise-voice-solution/call-park.md). Pour plus d’informations sur l’utilisation des plages de numéros d’appel Park, consultez [Configurer les Extensions numéro de téléphone pour les appels de stationnement](http://technet.microsoft.com/library/fbf97624-9587-42a6-b276-1b69c574a74d.aspx).
  

