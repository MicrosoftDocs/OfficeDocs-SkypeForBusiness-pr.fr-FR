---
title: Configuration de la version du client création d’un nouveau ou modification existante
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.ClientCVSettingEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 07fec57c-5cd3-422a-829a-0b62cb0092c4
description: Les paramètres de configuration de version du client sont utilisés pour activer ou désactiver le contrôle de version du client. La configuration de la version du client global s’installe avec Skype entreprise Server et est utilisée pour activer ou désactiver le contrôle de version du client pour le déploiement complet du serveur. Lorsque la configuration globale est activée, toutes les stratégies de version du client en place prendront effet lorsque les utilisateurs tenteront de se connecter. Vous pouvez désactiver la configuration globale de version du client si vous voulez que la version du client ne soit pas contrôlée.
ms.openlocfilehash: f970053cb359fb0735535720da7c8310e015ac37
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41686958"
---
# <a name="client-version-configuration-create-new-or-edit-existing"></a>Configuration de version du client : création d’une version ou modification d’une version existante

Les paramètres de configuration de version du client sont utilisés pour activer ou désactiver le contrôle de version du client. La configuration de la version du client global s’installe avec Skype entreprise Server et est utilisée pour activer ou désactiver le contrôle de version du client pour le déploiement complet du serveur. Lorsque la configuration globale est activée, toutes les stratégies de version du client en place prendront effet lorsque les utilisateurs tenteront de se connecter. Vous pouvez désactiver la configuration globale de version du client si vous voulez que la version du client ne soit pas contrôlée.

Vous pouvez également créer des configurations de version du client spécifiques au site, ce qui vous permet d’activer ou de désactiver le contrôle de la version du client site par site. Les configurations spécifiques au site seront prioritaires sur la configuration globale.

## <a name="tasks-you-can-perform"></a>Tâches que vous pouvez effectuer

Dans la page **Nouvelle configuration de version du client** ou **Modifier la configuration de version du client**, vous pouvez effectuer les tâches suivantes :

- Ajout ou modification du nom de la configuration de version du client

- Activation ou désactivation du contrôle de version du client au niveau global ou pour le site spécifique

- Ajout ou modification de l’action par défaut pour la configuration de version du client

## <a name="ui-reference"></a>Référence d’interface utilisateur

Les listes ci-dessous décrivent les menus, les commandes, les champs et les propriétés de la page.

- **Scope** Identifie l’étendue (globale ou site) de la configuration de la version du client.

- **Nom** Vous pouvez ajouter ou modifier le nom de la configuration de la version du client.

- **Activer le contrôle de version** Vous pouvez activer ou désactiver le contrôle de version du client globalement ou pour le site, en fonction de l’étendue de la configuration.

- **Action par défaut** Vous pouvez sélectionner l’action par défaut qui sera appliquée lorsqu’un utilisateur tente de se connecter à l’aide d’une application cliente pour laquelle il n’existe aucune stratégie de version de client spécifique. Les options suivantes s’offrent à vous :

  - **Autoriser** Permet au client de se connecter si la version du client ne correspond à aucun filtre dans la liste des stratégies de la version du client.

  - **Bloquer** Empêche le client de se connecter si la version du client ne correspond à aucun filtre dans la liste des stratégies de la version du client.

  - **Bloquer avec l’URL** Empêche le client de se connecter si la version du client ne correspond à aucun filtre dans la liste des stratégies de la version du client, et qu’il inclut un message d’erreur contenant une URL dans laquelle un client plus récent peut être téléchargé.

  - **Allow with URL** Permet au client de se connecter si la version du client ne correspond à aucun filtre dans la liste des stratégies de la version du client, et qu’il inclut un message d’erreur contenant une URL dans laquelle un client plus récent peut être téléchargé.

  - **URL (URL** ) Si vous avez sélectionné **bloquer avec une URL** ou **autoriser avec l’URL**, vous pouvez spécifier l’URL de téléchargement du client à inclure dans le message d’erreur.

Pour plus d’informations sur l’interopérabilité entre les clients et les versions des clients, reportez-vous à la rubrique [Client Interoperability in Lync 2013 Preview](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) de la documentation de planification. Pour plus d’informations sur l’utilisation des configurations de version du client, reportez-vous à la rubrique [Modify the Default Action for Clients Not Explicitly Supported or Restricted](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx) de la documentation des opérations.

