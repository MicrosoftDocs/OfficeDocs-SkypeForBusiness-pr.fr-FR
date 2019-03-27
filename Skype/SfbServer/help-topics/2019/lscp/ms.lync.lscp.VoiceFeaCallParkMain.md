---
title: Parcage d’appel
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.VoiceFeaCallParkMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b752617d-554d-470e-b17b-387403ac74ed
ROBOTS: NOINDEX, NOFOLLOW
description: Lors de la mise en garde un appel, il est transféré vers un numéro temporaire où l’appel est conservé jusqu'à ce qu’une personne récupère ou qu’il arrive à expiration. Vous devez configurer un tableau avec les plages de numéros de poste que vous réservez pour les appels mis en garde. Ces postes doivent être des postes virtuels (autrement dit, des postes auxquels aucun utilisateur ni téléphone n’est affecté). Chaque pool qui exécute l’application de parcage d’appel peut avoir une ou plusieurs plages d’extensions. Ces plages doivent être globalement uniques dans votre déploiement.
ms.openlocfilehash: f23ec10607c8cd1f6ec15dca3f9e3b99666abf1a
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30890261"
---
# <a name="call-park"></a>parcage d’appel

Lors de la mise en garde un appel, il est transféré vers un numéro temporaire où l’appel est conservé jusqu'à ce qu’une personne récupère ou qu’il arrive à expiration. Vous devez configurer un tableau avec les plages de numéros de poste que vous réservez pour les appels mis en garde. Ces postes doivent être des postes virtuels (autrement dit, des postes auxquels aucun utilisateur ni téléphone n’est affecté). Chaque pool qui exécute l’application de parcage d’appel peut avoir une ou plusieurs plages d’extensions. Ces plages doivent être globalement uniques dans votre déploiement.

La page **Parcage d’appel** affiche une liste de toutes les plages numéros parcage d’appel sont définies pour votre organisation.

## <a name="tasks-you-can-perform"></a>Tâches que vous pouvez effectuer

Dans la page **Parcage d’appel**, vous pouvez effectuer les tâches suivantes :

- Création d’une plage de numéros

- Modification d’une plage de numéros existante

- Suppression d’une plage de numéros

## <a name="ui-reference"></a>Référence d’interface utilisateur

La liste ci-dessous décrit les commandes de la page.

- **Nouveau** Démarre une nouvelle plage de numéros de parcage d’appel.

- **Modifier** Ouvre la plage de numéros sélectionnée pour modification, sélectionne toutes les plages de numéros dans la liste ou supprime la plage de numéros sélectionnée.

- **Actualiser** Actualise la liste des plages de numéros.

La liste ci-dessous décrit les champs de la page.

- **Nom** Nom unique qui identifie la plage de numéros.

- **Plage de début** Le numéro de début de la plage.

- **Plage de fin** Numéro de fin de la plage.

- **Destination** Le nom de domaine complet (FQDN) de nom ou ID de service du service d’Application qui héberge l’application de parcage d’appel pour la plage de numéros.

Pour plus d’informations sur les fonctionnalités de parcage d’appel, voir [planifier la mise en garde d’appels dans Skype pour les entreprises](../../../plan-your-deployment/enterprise-voice-solution/call-park.md). Pour plus d’informations sur l’utilisation des plages de numéros de parcage d’appel, voir [Configurer les Extensions numéro de téléphone pour les appels parcage](https://technet.microsoft.com/library/fbf97624-9587-42a6-b276-1b69c574a74d.aspx).


