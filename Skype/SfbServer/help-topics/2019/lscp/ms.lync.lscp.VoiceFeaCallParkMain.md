---
title: Parcage d’appel
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.VoiceFeaCallParkMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: b752617d-554d-470e-b17b-387403ac74ed
ROBOTS: NOINDEX, NOFOLLOW
description: Lorsqu’un appel est paré, il est transféré vers un numéro temporaire où l’appel est maintenu jusqu’à ce que quelqu’un le récupère ou qu’il n’sorte pas. Vous devez configurer un tableau avec les plages de numéros de poste que vous réservez pour les appels par parcés. Ces postes doivent être des postes virtuels (autrement dit, des postes auxquels aucun utilisateur ni téléphone n’est assigné). Chaque pool qui exécute l’application de parcage d’appel peut avoir une ou plusieurs plages d’extensions. Ces plages doivent être globalement uniques dans votre déploiement.
ms.openlocfilehash: 679e13cdeb6ef6cf614f5703f5711e86fa1c8c59
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812164"
---
# <a name="call-park"></a>Parcage d’appel

Lorsqu’un appel est paré, il est transféré vers un numéro temporaire où l’appel est maintenu jusqu’à ce que quelqu’un le récupère ou qu’il n’sorte pas. Vous devez configurer un tableau avec les plages de numéros de poste que vous réservez pour les appels par parcés. Ces postes doivent être des postes virtuels (autrement dit, des postes auxquels aucun utilisateur ni téléphone n’est assigné). Chaque pool qui exécute l’application de parcage d’appel peut avoir une ou plusieurs plages d’extensions. Ces plages doivent être globalement uniques dans votre déploiement.

La page **Parcer** des appels affiche la liste de toutes les plages de numéro de parc d’appel définies pour votre organisation.

## <a name="tasks-you-can-perform"></a>Tâches que vous pouvez effectuer

Vous pouvez effectuer les tâches suivantes dans la page **Parcage d’appel** :

- Créer une nouvelle plage de numéros

- Modifier une plage de numéros existante

- Supprimer une plage de numéros

## <a name="ui-reference"></a>Référence d’interface utilisateur

La liste suivante décrit les commandes de la page.

- **Nouveau** Démarre une nouvelle plage de numéro de parcier d’appel.

- **Modifier** Ouvre la plage de nombres sélectionnée pour modification, sélectionne toutes les plages de numéro dans la liste ou supprime la plage de nombres sélectionnée.

- **Actualiser** Actualise la liste des plages de nombres.

La liste suivante décrit les champs de la page.

- **Nom** Nom unique qui identifie la plage de nombres.

- **Plage de début** Numéro de début de la plage.

- **Plage de fin** Numéro de fin de la plage.

- **Destination** Nom de domaine complet (FQDN) ou ID de service du service d’application qui héberge l’application de parcage d’appel pour la plage de numéro.

Pour plus d’informations sur les fonctionnalités et fonctionnalités de parcier d’appel, voir [Plan for Call Park in Skype for Business](../../../plan-your-deployment/enterprise-voice-solution/call-park.md). Pour plus d’informations sur l’working with Call Park number ranges, see [Configure Phone Number Extensions for Parking Calls](https://technet.microsoft.com/library/fbf97624-9587-42a6-b276-1b69c574a74d.aspx).


