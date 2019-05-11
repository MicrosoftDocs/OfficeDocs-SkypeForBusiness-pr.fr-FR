---
title: Sélection des membres autorisés
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/24/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.SelectAllowedMembers
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e9e6df4a-e58a-4104-9f72-2f5c818353e1
description: Création et gestion des salles de conversation permanente sont beaucoup plus facile avec l’utilisation correcte des catégories. Un administrateur de conversation permanente peut définir AllowedMembers et créateurs pour chaque catégorie et peuvent également définir les paramètres de salle de conversation par défaut et les comportements qui seront appliquées à toutes les salles de conversation créées dans la catégorie. Les administrateurs de conversation permanente créer et gérer des catégories à l’aide du Panneau de configuration ou les applets de commande Windows PowerShell.
ms.openlocfilehash: d7dcb2b6b3fb8712acfb6c35b134a4b15441454d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33924625"
---
# <a name="select-allowed-members"></a>Sélection des membres autorisés

Création et gestion des salles de conversation permanente sont beaucoup plus facile avec l’utilisation correcte des catégories. Un administrateur de conversation permanente peut définir **AllowedMembers** et **créateurs** pour chaque catégorie et peuvent également définir les paramètres de salle de conversation par défaut et les comportements qui seront appliquées à toutes les salles de conversation créées dans la catégorie. Les administrateurs de conversation permanente créer et gérer des catégories à l’aide du Panneau de configuration ou les applets de commande Windows PowerShell.

Les utilisateurs, les unités d’organisation et les groupes d’utilisateurs identifiés comme créateurs de la catégorie sont les seuls individus et groupes autorisés à créer des salles dans la catégorie. Une fois la catégorie est créée, ils peuvent choisir les utilisateurs, les unités d’organisation et les groupes d’utilisateurs à partir de la liste de **AllowedMembers** de la catégorie en tant que gestionnaires de salles de conversation et des membres pour gérer et participer à la salle.

## <a name="tasks-that-you-can-perform"></a>Tâches que vous pouvez effectuer

Dans la page **Sélectionner les membres autorisés**, vous pouvez effectuer les tâches suivantes :

- [Configure Categories](https://technet.microsoft.com/library/4547f514-f0c0-404d-890f-092ddeeac852.aspx)

- [New Persistent Chat Server Features](https://technet.microsoft.com/library/c3ec6f33-6261-4bf5-aa31-baa8ab2a87d8.aspx)

Pour plus d’informations sur les différentes procédures que vous pouvez effectuer à l’aide de la Skype pour le panneau de configuration serveur Business, voir [Gérer les Skype pour Business Server 2015](../../manage/manage.md).

## <a name="to-configure-categories-for-chat-rooms"></a>Pour configurer les catégories des salles de conversation

Dans **l’appartenance**, dans la section **membres autorisés** , ajouter ou supprimer des utilisateurs et autres entités de Services de domaine Active Directory (utilisateurs, groupes de distribution, unités d’organisation et ainsi de suite) sont autorisées à ajouter en tant que membres des salles de conversation appartenant à la catégorie. Les principaux autorisés par une catégorie peuvent rechercher les salles dans la catégorie (sauf si la salle est masquée ; dans ce cas, seuls les membres de la salle peuvent la rechercher dans l’annuaire).


Pour plus d’informations sur les serveurs de conversation permanente des fonctionnalités, voir [Vue d’ensemble de Persistent Chat Server](https://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx) dans la documentation de planification. Pour plus d’informations sur l’utilisation des configurations de serveur de conversation permanente, voir [Configuring Persistent Chat Server](https://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx) dans la documentation de déploiement et la [gestion de Lync Server 2013, Persistent Chat Server](https://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx) dans la documentation des opérations.

## <a name="see-also"></a>Voir aussi

[Understanding Persistent Chat Membership](https://technet.microsoft.com/library/900392d6-6e9f-4dae-93d6-39d7474409ef.aspx)
