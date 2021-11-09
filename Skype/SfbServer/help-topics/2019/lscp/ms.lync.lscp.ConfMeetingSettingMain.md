---
title: Configuration de la réunion
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ConfMeetingSettingMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.assetid: 24e8f749-d54c-4315-a8fe-bb9303b356ef
ROBOTS: NOINDEX, NOFOLLOW
description: Les paramètres de configuration de réunion définissent le type de conférences (également appelées « événements de réunion » ) que les utilisateurs peuvent créer, et contrôlent comment (ou si) les utilisateurs anonymes et les utilisateurs de conférence rendez-vous peuvent participer à ces conférences. Ces paramètres s’appliquent uniquement aux réunions planifiées. Elles ne s’appliquent pas aux réunions ad hoc créées en cliquant sur l’option Conférence maintenant dans le client.
ms.openlocfilehash: 4eb66e999cfc8c3682e0c1f5b54004bf57efa1e7
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60831528"
---
# <a name="meeting-configuration"></a>Configuration de la réunion

Les paramètres de configuration de réunion définissent le type de conférences (également appelées « réunions ») que les utilisateurs peuvent créer et contrôlent comment (ou si) les utilisateurs anonymes et les utilisateurs de conférence rendez-vous peuvent participer à ces conférences. Ces paramètres s’appliquent uniquement aux réunions planifiées. Elles ne s’appliquent pas aux réunions ad hoc créées en cliquant sur l’option Conférence maintenant dans le client.

Les configurations de réunion s’appliquent au niveau du site, au niveau du pool ou au niveau global :

- **Configuration de réunion globale :** La configuration de réunion globale est créée par défaut. Vous pouvez la modifier mais vous ne pouvez pas la supprimer. Si vous essayez de la supprimer, toutes les valeurs par défaut des paramètres sont rétablies.

- **Configuration de réunion de site (facultative) :** Vous pouvez créer une ou plusieurs configurations de réunion de site, chacune s’applique à un site spécifique. Les configurations de site supplantent la configuration globale.

- **Configuration de réunion de pool (facultative) :** Vous pouvez créer une ou plusieurs configurations de réunion de pool, chacune s’applique à un pool spécifique. Les configurations de pool supplantent la configuration globale et les configurations de site.

La page **Configuration de la réunion** affiche la liste de toutes les configurations de réunion définies pour votre organisation.

## <a name="tasks-you-can-perform"></a>Tâches que vous pouvez effectuer

Vous pouvez effectuer les tâches suivantes dans la page **Configuration de la réunion** :

- Créer une nouvelle configuration de réunion de site ou configuration de réunion de pool

- Modifier la configuration globale ou une configuration de site ou de pool existante

- Supprimer une configuration de site ou de pool

## <a name="ui-reference"></a>Référence d’interface utilisateur

La liste suivante décrit les commandes de la page.

- **Nouveau** Démarre une nouvelle configuration de réunion de site ou de pool.

- **Modifier** Ouvre la configuration de réunion sélectionnée pour la modifier, sélectionne toutes les configurations de réunion dans la liste ou supprime la configuration de site ou de pool sélectionnée.

    > [!NOTE]
    > Pour la configuration de réunion globale, la commande **Supprimer** rétablit les valeurs par défaut des paramètres.

- **Actualiser** Actualise la liste des configurations de réunion.

La liste suivante décrit les champs de la page.

- **Nom** Identifie la configuration de la réunion.

- **Étendue** Identifie l’étendue de la configuration de réunion : globale, de site ou de pool.

Pour plus d’informations sur l’utilisation des configurations de réunion, voir [Create a or modify a Collection of Meeting Configuration Settings](/previous-versions/office/lync-server-2013/lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings) dans la documentation des opérations.