---
title: Configuration de la réunion
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ConfMeetingSettingMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 24e8f749-d54c-4315-a8fe-bb9303b356ef
description: Les paramètres de configuration de réunion définissent le type de conférences (également calledmeetings) que les utilisateurs peuvent créer et contrôlent la façon dont les utilisateurs anonymes et les conférences rendez-vous peuvent participer à ces conférences. Ces paramètres ne concernent que les réunions planifiées. Ils ne concernent pas les réunions ad hoc créées en cliquant sur l’option Conférence maintenant du client.
ms.openlocfilehash: 82619b255f99dc5a82d6a9cb704fe5443fe83d23
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34293423"
---
# <a name="meeting-configuration"></a>Configuration de la réunion

Les paramètres de configuration de réunion définissent le type de conférence (également appelées « réunions ») que les utilisateurs peuvent créer. Ils contrôlent également la façon dont les utilisateurs anonymes et les utilisateurs de conférences rendez-vous peuvent participer aux conférences et s’ils peuvent y participer. Ces paramètres concernent uniquement les réunions planifiées. Ils ne concernent pas les réunions ad hoc créées en cliquant sur l’option Conférence maintenant du client.

Les configurations de réunion s’appliquent au niveau du site, au niveau du pool ou au niveau global :

- **Configuration globale de la réunion:** La configuration globale de la réunion est créée par défaut. Vous pouvez modifier la configuration globale de la réunion, mais vous ne pouvez pas la supprimer. Si vous tentez de supprimer la configuration globale de la réunion, tous les paramètres sont réinitialisés aux valeurs par défaut.

- **Configuration de la réunion site (facultatif):** Vous pouvez créer une ou plusieurs configurations de réunion de site, qui s’appliquent à un site spécifique. Les configurations de site remplacent la configuration globale.

- **Configuration d’une réunion en pool (facultatif):** Vous pouvez créer une ou plusieurs configurations de réunion de réserve qui s’appliquent à un pool spécifique. Les configurations de pool remplacent la configuration globale et les configurations de site.

La page **Configuration de la réunion** affiche la liste de toutes les configurations de réunion définies pour votre organisation.

## <a name="tasks-you-can-perform"></a>Tâches que vous pouvez effectuer

Dans la page **Configuration de la réunion**, vous pouvez effectuer les tâches suivantes :

- Création d’une configuration de réunion de site ou configuration de réunion de pool

- Modification de la configuration globale ou d’une configuration de site ou de pool existante

- Suppression d’une configuration de site ou de pool

## <a name="ui-reference"></a>Référence d’interface utilisateur

La liste ci-dessous décrit les commandes de la page.

- **Nouvelle** Démarre une configuration de réunion de nouvelle réunion ou de réserve de sites.

- **Modifier** Ouvre la configuration de la réunion sélectionnée pour la modifier, sélectionner toutes les configurations de la réunion dans la liste, ou supprimer la configuration ou le pool de configuration de site sélectionné.

    > [!NOTE]
    > Pour la configuration de réunion globale, la commande **Supprimer** restaure les valeurs par défaut des paramètres.

- **Actualiser** Actualise la liste des configurations de la réunion.

La liste ci-dessous décrit les champs de la page.

- **Nom** Identifie la configuration de la réunion.

- **Scope** Identifie l’étendue de la configuration de la réunion: global, site ou pool.

Pour plus d’informations sur l’utilisation des configurations de réunion, reportez-vous à la rubrique [Create a or modify a Collection of Meeting Configuration Settings](https://technet.microsoft.com/library/ce6773c1-a0d5-4405-8e32-33a6f3a46a1a.aspx) de la documentation des opérations.


