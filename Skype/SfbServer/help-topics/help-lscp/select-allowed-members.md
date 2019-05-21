---
title: Sélection des membres autorisés
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.SelectAllowedMembers
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e9e6df4a-e58a-4104-9f72-2f5c818353e1
description: La création et la gestion des salles de conversation permanentes sont beaucoup plus simples grâce à l’utilisation correcte des catégories. Un administrateur de chat permanent peut définir des AllowedMembers et des créateurs pour chaque catégorie, et peut également définir les paramètres et les comportements de la salle de conversation par défaut qui seront appliqués à l’ensemble des salles de conversation créées dans la catégorie. Les administrateurs de discussions permanentes peuvent créer et gérer des catégories à l’aide du panneau de configuration ou des applets de commande Windows PowerShell.
ms.openlocfilehash: dedc022853738ad02b4da2ce0ab2cdc7ccbee576
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34282251"
---
# <a name="select-allowed-members"></a>Sélection des membres autorisés

La création et la gestion des salles de conversation permanentes sont beaucoup plus simples grâce à l’utilisation correcte des catégories. Un administrateur de chat permanent peut définir des **AllowedMembers** et des **créateurs** pour chaque catégorie, et peut également définir les paramètres et les comportements de la salle de conversation par défaut qui seront appliqués à l’ensemble des salles de conversation créées dans la catégorie. Les administrateurs de discussions permanentes peuvent créer et gérer des catégories à l’aide du panneau de configuration ou des applets de commande Windows PowerShell.

Les utilisateurs, les unités d’organisation et les groupes d’utilisateurs identifiés comme créateurs de la catégorie sont les seuls individus et groupes autorisés à créer des salles dans la catégorie. Une fois la catégorie créée, les utilisateurs et les groupes d’utilisateurs de la liste **AllowedMembers** de la catégorie peuvent choisir comme responsables de salles de conversation et membres pour gérer et participer à cette salle.

## <a name="tasks-that-you-can-perform"></a>Tâches que vous pouvez effectuer

Dans la page **Sélectionner les membres autorisés**, vous pouvez effectuer les tâches suivantes :

- [Configure Categories](https://technet.microsoft.com/library/4547f514-f0c0-404d-890f-092ddeeac852.aspx)

- [New Persistent Chat Server Features](https://technet.microsoft.com/library/c3ec6f33-6261-4bf5-aa31-baa8ab2a87d8.aspx)

Pour plus d’informations sur les différentes procédures que vous pouvez effectuer à l’aide du panneau de configuration Skype entreprise Server, reportez-vous à la rubrique [gestion de Skype entreprise server 2015](../../manage/manage.md).

## <a name="to-configure-categories-for-chat-rooms"></a>Pour configurer les catégories des salles de conversation

Dans **appartenance**, dans la section **membres autorisés** , ajoutez ou supprimez des utilisateurs et d’autres principaux services de domaine Active Directory (utilisateurs, groupes de distribution, unités organisationnelles, etc.) qui sont autorisés à être ajoutés en tant que membres de salles de conversation. appartenant à la catégorie. Les principaux autorisés par une catégorie peuvent rechercher les salles dans la catégorie (sauf si la salle est masquée ; dans ce cas, seuls les membres de la salle peuvent la rechercher dans l’annuaire).


Pour plus d’informations sur les fonctionnalités et les fonctionnalités du serveur Chat permanent, voir [vue d’ensemble du serveur de chat permanent](https://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx) dans la documentation de planification. Pour plus d’informations sur l’utilisation des configurations serveur de chat permanent, voir [configuration du serveur de chat permanent](https://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx) dans la documentation de déploiement et [gestion de Lync Server 2013, serveur de chat permanent](https://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx) dans la documentation des opérations.

## <a name="see-also"></a>Voir aussi

[Understanding Persistent Chat Membership](https://technet.microsoft.com/library/900392d6-6e9f-4dae-93d6-39d7474409ef.aspx)
