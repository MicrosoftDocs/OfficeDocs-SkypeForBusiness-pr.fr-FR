---
title: 'Configuration de version du client : création d’une version ou modification d’une version existante'
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
  - ms.lync.lscp.ClientCVSettingEdit
ms.prod: skype-for-business-itpro
f1.keywords:
  - CSH
ms.localizationpriority: medium
ms.assetid: 07fec57c-5cd3-422a-829a-0b62cb0092c4
ROBOTS: 'NOINDEX, NOFOLLOW'
description: 'Les paramètres de configuration de version du client sont utilisés pour activer ou désactiver le contrôle de version du client. La configuration de la version globale du client s’installe Skype Entreprise Server et est utilisée pour activer ou désactiver le contrôle de version du client pour l’ensemble du déploiement du serveur. Lorsque la configuration globale est activée, toutes les stratégies de version du client qui sont en place prendront effet lorsque les utilisateurs tenteront de se connecter. Vous pouvez désactiver la configuration globale de version du client si vous voulez qu’aucun contrôle de la version du client ne se produise.'
---

# <a name="client-version-configuration-create-new-or-edit-existing"></a>Configuration de version du client : création d’une nouvelle ou modification d’une configuration existante

Les paramètres de configuration de version du client sont utilisés pour activer ou désactiver le contrôle de version du client. La configuration de la version globale du client s’installe Skype Entreprise Server et est utilisée pour activer ou désactiver le contrôle de version du client pour l’ensemble du déploiement du serveur. Lorsque la configuration globale est activée, toutes les stratégies de version du client qui sont en place prendront effet lorsque les utilisateurs tenteront de se connecter. Vous pouvez désactiver la configuration globale de version du client si vous voulez qu’aucun contrôle de la version du client ne se produise.

Vous pouvez également créer des configurations de version du client spécifiques au site, ce qui vous permet d’activer ou de désactiver le contrôle de la version du client site par site. Les configurations spécifiques au site auront priorité sur la configuration globale.

## <a name="tasks-you-can-perform"></a>Tâches que vous pouvez effectuer

Vous pouvez effectuer les tâches suivantes dans la page **Nouvelle configuration de version du client** ou **Modifier la configuration de version du client** :

- Ajouter ou modifier le nom de la configuration de version du client.

- Activer ou désactiver le contrôle de version du client globalement ou pour le site spécifique.

- Ajouter ou modifier l’action par défaut pour la configuration de version du client.

## <a name="ui-reference"></a>Référence d’interface utilisateur

Les listes suivantes décrivent les menus, commandes, champs et propriétés de la page.

- **Étendue** Identifie l’étendue (globale ou site) de la configuration de version du client.

- **Nom** Vous pouvez ajouter ou modifier le nom de la configuration de version du client.

- **Activer le contrôle de version** Vous pouvez activer ou désactiver le contrôle de version du client globalement ou pour le site, en fonction de l’étendue de la configuration.

- **Action par défaut** Vous pouvez sélectionner l’action par défaut qui sera appliquée lorsqu’un utilisateur tente de se connecter à l’aide d’une application cliente pour laquelle il n’existe aucune stratégie de version du client spécifique. Vous avez le choix parmi les options suivantes :

  - **Autoriser** Permet au client de se connecter si la version du client ne correspond à aucun filtre dans la liste des stratégies de version du client.

  - **Bloquer** Empêche le client de se connecter si la version du client ne correspond à aucun filtre dans la liste des stratégies de version du client.

  - **Bloquer avec une URL** Empêche le client de se connecter si la version du client ne correspond à aucun filtre dans la liste des stratégies de version du client et inclut un message d’erreur contenant une URL dans laquelle un client plus récente peut être téléchargé.

  - **Autoriser avec l’URL** Permet au client de se connecter si la version du client ne correspond à aucun filtre dans la liste des stratégies de version du client et inclut un message d’erreur contenant une URL dans laquelle un client plus récente peut être téléchargé.

  - **URL** Si vous avez sélectionné **Bloquer avec une URL** ou Autoriser **avec une URL**, vous pouvez spécifier l’URL de téléchargement du client à inclure dans le message d’erreur.

Pour plus d’informations sur l’interopérabilité entre les clients et les versions des clients, voir [Interopérabilité](/previous-versions/office/lync-server-2013/lync-server-2013-client-interoperability-in-lync-2013) du client dans la documentation de planification. Pour plus d’informations sur l’utilisation des configurations de version du client, voir [Modify the Default Action for Clients Not Explicitly Supported or Restricted](/previous-versions/office/lync-server-2013/lync-server-2013-modify-the-default-action-for-clients-not-explicitly-supported-or-restricted) dans la documentation des opérations.