---
title: Stratégie d’emplacement
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.NcsLocMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.assetid: 5530cf17-4520-40b5-ba70-c62692685048
ROBOTS: NOINDEX, NOFOLLOW
description: Les stratégies d’emplacement déterminent si le service E9-1-1 (Enhanced 9-1-1) doit être activé et définissent son mode d’utilisation. Elles indiquent également la façon dont les informations d’emplacement sont traitées pour les utilisateurs et les contacts.
ms.openlocfilehash: 6a985be60453f70cf0cdb47a212f858d74d56032
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58613183"
---
# <a name="location-policy"></a>Stratégie d’emplacement

Les stratégies d’emplacement déterminent si le service E9-1-1 (Enhanced 9-1-1) doit être activé et définissent son mode d’utilisation. Elles indiquent également la façon dont les informations d’emplacement sont traitées pour les utilisateurs et les contacts.

Les stratégies d’emplacement incluent la stratégie globale et, éventuellement, une ou plusieurs stratégies de site et d’utilisateur :

- **Stratégie globale :** La stratégie globale est créée par défaut. Vous pouvez modifier la stratégie globale mais vous ne pouvez pas la supprimer. Si vous essayez de supprimer la stratégie globale, toutes les valeurs par défaut des paramètres sont réinitialisées.

- **Stratégies de site (facultatives) :** Vous pouvez créer une ou plusieurs stratégies d’emplacement de site, chacune s’applique à un site spécifique. Les stratégies de site remplacent la stratégie globale.

- **Stratégies utilisateur (facultatives) :** Vous pouvez créer une ou plusieurs stratégies d’emplacement utilisateur, chacune s’applique à un utilisateur ou à un groupe d’utilisateurs spécifique. Les stratégies utilisateur remplacent la stratégie globale et les stratégies de site.

> [!NOTE]
> Vous pouvez également affecter des stratégies d’emplacement à des sites réseau, qui sont des groupes de sous-réseaux. Les stratégies d’emplacement attribuées aux sites réseau prévalent sur toutes les autres stratégies utilisateur. Pour plus d’informations sur l’attribution de stratégies d’emplacement à des sites réseau à l’aide d’cmdlets, voir Ajouter une stratégie d’emplacement à un [site réseau dans Skype Entreprise Server](../../../deploy/deploy-enterprise-voice/add-a-location-policy-to-a-network-site.md). Pour plus d’informations sur l Skype Entreprise Server du Panneau de configuration pour affecter une stratégie d’emplacement à un site réseau, voir [Configuring Network Sites](/previous-versions/office/lync-server-2013/lync-server-2013-creating-or-modifying-network-sites).

La page **Stratégie d’emplacement** affiche la liste de toutes les stratégies d’emplacement définies pour votre organisation.

## <a name="tasks-you-can-perform"></a>Tâches que vous pouvez effectuer

Vous pouvez effectuer les tâches suivantes à partir de la page **Stratégie d’emplacement** :

- Créer une stratégie d’emplacement de site ou une stratégie d’emplacement utilisateur

- Modifier la stratégie globale ou une stratégie de site ou stratégie utilisateur existante

- Supprimer une stratégie de site ou une stratégie utilisateur

## <a name="ui-reference"></a>Référence d’interface utilisateur

La liste suivante décrit les commandes de la page.

- **Nouveau** Démarre une nouvelle stratégie d’emplacement de site ou une nouvelle stratégie d’emplacement utilisateur.

- **Modifier** Ouvre la stratégie d’emplacement sélectionnée pour la modifier, sélectionne toutes les stratégies d’emplacement dans la liste ou supprime la stratégie de site ou la stratégie utilisateur sélectionnée.

    > [!NOTE]
    > Pour la stratégie globale, **Supprimer** rétablit les valeurs par défaut des paramètres.

- **Actualiser** Actualisation de la liste des stratégies d’emplacement.

La liste suivante décrit les champs de la page.

- **Nom** Identifie la stratégie d’emplacement.

- **Étendue** Identifie l’étendue de la stratégie d’emplacement : globale, de site ou utilisateur.

- **E9-1-1** Vérifié si les utilisateurs affectés à cette stratégie d’emplacement sont activés pour E9-1-1.

- **Emplacement** Spécifie si les utilisateurs sont invités à entrer des informations d’emplacement lorsque leur client s’inscrit auprès de Skype Entreprise Server à un nouvel emplacement, et s’ils voient une clause d’exclusion de responsabilité s’ils font disparaître l’invite sans entrer d’informations d’emplacement.

- **Utilisation PSTN** Spécifie l’utilisation du réseau téléphonique commuté (PSTN) utilisée pour déterminer l’itinéraire des communications vocales utilisé pour router les appels d’urgence des clients à l’aide de ce profil.

- **Numéro E9-1-1** Spécifie le numéro composé pour joindre les services d’urgence.

- **Masque E9-1-1** Spécifie un numéro qu’un utilisateur compose puis converti en numéro de numéro d’urgence.

Pour plus d’informations Voix Entreprise fonctionnalités des services d’urgence, voir Vue d’ensemble du [service E9-1-1](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-e9-1-1) dans la documentation de planification. Pour plus d’informations sur l’utilisation des stratégies d’emplacement, voir [Configuring Location Policy](/previous-versions/office/lync-server-2013/lync-server-2013-viewing-location-policy-information) dans la documentation des opérations.