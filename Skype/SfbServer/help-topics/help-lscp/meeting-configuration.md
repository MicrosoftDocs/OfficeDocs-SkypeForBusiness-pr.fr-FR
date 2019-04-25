---
title: Configuration de la réunion
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/24/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ConfMeetingSettingMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 24e8f749-d54c-4315-a8fe-bb9303b356ef
description: Paramètres de configuration de réunion définissent le type de conférences (également calledmeetings) que les utilisateurs peuvent créer et contrôler comment (ou si) les utilisateurs anonymes et les utilisateurs de conférence rendez-vous peuvent rejoindre ces conférences. Ces paramètres ne concernent que les réunions planifiées. Ils ne concernent pas les réunions ad hoc créées en cliquant sur l’option Conférence maintenant du client.
ms.openlocfilehash: 32bbb6861271623e0a4126d98e36c28542ddfc8d
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32220318"
---
# <a name="meeting-configuration"></a>Configuration de la réunion

Les paramètres de configuration de réunion définissent le type de conférence (également appelées « réunions ») que les utilisateurs peuvent créer. Ils contrôlent également la façon dont les utilisateurs anonymes et les utilisateurs de conférences rendez-vous peuvent participer aux conférences et s’ils peuvent y participer. Ces paramètres concernent uniquement les réunions planifiées. Ils ne concernent pas les réunions ad hoc créées en cliquant sur l’option Conférence maintenant du client.

Les configurations de réunion s’appliquent au niveau du site, au niveau du pool ou au niveau global :

- **Configuration de réunion globale :** La configuration de réunion globale est créée par défaut. Vous pouvez modifier la configuration de réunion globale, mais vous ne pouvez pas le supprimer. Si vous essayez de supprimer la configuration de réunion globale, tous les paramètres sont réinitialisées sur les valeurs par défaut.

- **Configuration de réunion de site (facultative) :** Vous pouvez en créer un ou plusieurs sites configurations de réunion, chacun d'entre eux s’applique à un site spécifique. Configurations de site remplacent la configuration globale.

- **Configuration de réunion de pool (facultatif) :** Vous pouvez en créer un ou plusieurs pool configurations de réunion, chacun d'entre eux s’applique à un pool spécifique. Configurations de pool remplacent la configuration globale et les configurations de site.

La page **Configuration de la réunion** affiche la liste de toutes les configurations de réunion définies pour votre organisation.

## <a name="tasks-you-can-perform"></a>Tâches que vous pouvez effectuer

Dans la page **Configuration de la réunion**, vous pouvez effectuer les tâches suivantes :

- Création d’une configuration de réunion de site ou configuration de réunion de pool

- Modification de la configuration globale ou d’une configuration de site ou de pool existante

- Suppression d’une configuration de site ou de pool

## <a name="ui-reference"></a>Référence d’interface utilisateur

La liste ci-dessous décrit les commandes de la page.

- **Nouveau** Démarre une nouvelle configuration de réunion de site ou de pool.

- **Modifier** Ouvre la configuration de réunion sélectionnée pour le modifier, sélectionne toutes les configurations de réunion dans la liste ou supprime la configuration du site sélectionné ou la configuration du pool.

    > [!NOTE]
    > Pour la configuration de réunion globale, la commande **Supprimer** restaure les valeurs par défaut des paramètres.

- **Actualiser** Actualise la liste des configurations de réunion.

La liste ci-dessous décrit les champs de la page.

- **Nom** Identifie la configuration de la réunion.

- **Étendue** Identifie l’étendue de la configuration de réunion : globale, site ou pool.

Pour plus d’informations sur l’utilisation des configurations de réunion, reportez-vous à la rubrique [Create a or modify a Collection of Meeting Configuration Settings](https://technet.microsoft.com/library/ce6773c1-a0d5-4405-8e32-33a6f3a46a1a.aspx) de la documentation des opérations.


