---
title: Configuration de Version du client créer ou modifier une existant
ms.author: SerdarS
author: SerdarSoysal
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientCVSettingEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 07fec57c-5cd3-422a-829a-0b62cb0092c4
description: Les paramètres de configuration de version du client sont utilisés pour activer ou désactiver le contrôle de version du client. La configuration de version client globale installe avec Skype pour Business Server et est utilisée pour activer ou désactiver le contrôle de version du client pour le déploiement de serveurs entière. Lorsque la configuration globale est activée, toutes les stratégies de version du client en place prendront effet lorsque les utilisateurs tenteront de se connecter. Vous pouvez désactiver la configuration globale de version du client si vous voulez que la version du client ne soit pas contrôlée.
ms.openlocfilehash: 3b03ae27b20ddd84a371c91c95bb3372457df33b
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/21/2018
ms.locfileid: "19987577"
---
# <a name="client-version-configuration-create-new-or-edit-existing"></a>Configuration de version du client : création d’une version ou modification d’une version existante
 
Les paramètres de configuration de version du client sont utilisés pour activer ou désactiver le contrôle de version du client. La configuration de version client globale installe avec Skype pour Business Server et est utilisée pour activer ou désactiver le contrôle de version du client pour le déploiement de serveurs entière. Lorsque la configuration globale est activée, toutes les stratégies de version du client en place prendront effet lorsque les utilisateurs tenteront de se connecter. Vous pouvez désactiver la configuration globale de version du client si vous voulez que la version du client ne soit pas contrôlée. 
  
Vous pouvez également créer des configurations de version du client spécifiques au site, ce qui vous permet d’activer ou de désactiver le contrôle de la version du client site par site. Les configurations spécifiques au site seront prioritaires sur la configuration globale.
  
## <a name="tasks-you-can-perform"></a>Tâches que vous pouvez effectuer

Dans la page **Nouvelle configuration de version du client** ou **Modifier la configuration de version du client**, vous pouvez effectuer les tâches suivantes :
  
- Ajout ou modification du nom de la configuration de version du client
    
- Activation ou désactivation du contrôle de version du client au niveau global ou pour le site spécifique
    
- Ajout ou modification de l’action par défaut pour la configuration de version du client
    
## <a name="ui-reference"></a>Référence d’interface utilisateur

Les listes ci-dessous décrivent les menus, les commandes, les champs et les propriétés de la page.
  
- **Étendue** Identifie l’étendue (globale ou Site) de la configuration de version du client.
    
- **Nom** Vous pouvez ajouter ou modifier le nom de la configuration de version du client.
    
- **Activer le contrôle de version** Vous pouvez activer ou désactiver le contrôle de version du client globalement ou pour le site, en fonction de l’étendue de la configuration.
    
- **Action par défaut** Vous pouvez sélectionner l’action par défaut qui sera appliquée lorsqu’un utilisateur tente de se connecter à l’aide d’une application cliente pour laquelle il n’existe aucune stratégie de version du client spécifique. Vous disposez des options suivantes :
    
  - **Autoriser** Autorise le client à se connecter si sa version ne correspond pas à aucun filtre dans la liste de stratégies de version de client.
    
  - **Bloc** Empêche le client de se connecter si sa version ne correspond pas à aucun filtre dans la liste de stratégies de version de client.
    
  - **Bloquer avec une URL** Empêche le client de se connecter si sa version ne correspond pas à aucun filtre dans la liste de stratégies de version de client et inclut un message d’erreur contenant une URL où un client plus récent peut être téléchargé.
    
  - **Autoriser avec une URL** Autorise le client à se connecter si la version du client ne correspond pas à aucun filtre dans la liste de stratégies de version de client et inclut un message d’erreur contenant une URL où un client plus récent peut être téléchargé.
    
  - **URL** Si vous avez sélectionné **bloquer avec une URL** ou **Autoriser avec une URL**, vous pouvez spécifier l’URL de téléchargement du client à inclure dans le message d’erreur.
    
Pour plus d’informations sur l’interopérabilité entre les clients et les versions du client, voir [Interopérabilité des clients](http://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) dans la documentation de planification. Pour plus d’informations sur l’utilisation des configurations de version du client, voir [Modifier l’Action par défaut pour les Clients pas explicitement pris en charge ou restreints](http://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx) dans la documentation des opérations.

