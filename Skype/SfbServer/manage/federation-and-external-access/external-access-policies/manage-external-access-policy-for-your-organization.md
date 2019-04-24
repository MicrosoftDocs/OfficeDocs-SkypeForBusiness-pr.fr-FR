---
title: Gestion de la stratégie d’accès externe pour l’organisation
ms.reviewer: ''
ms:assetid: 5571811e-34c8-443a-b94c-1ab5d4275581
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520995(v=OCS.15)
ms:contentKeyID: 48184160
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Après avoir déployé un ou plusieurs serveurs de périphérie, vous devez activer les types d’accès externe qui sera prise en charge pour votre organisation.
ms.openlocfilehash: bdc1a87476849a6e8383d5561af6e1b3af477869
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32199883"
---
# <a name="manage-external-access-policy-for-your-organization"></a>Gestion de la stratégie d’accès externe pour l’organisation

Après avoir déployé un ou plusieurs serveurs de périphérie, vous devez activer les types d’accès externe qui sera prise en charge pour votre organisation.

Par défaut, il n’existe aucune stratégie configurée pour prendre en charge l’accès des utilisateurs externes, y compris l’accès des utilisateurs distants, l’accès des utilisateurs fédérés, même si vous avez déjà activé la prise en charge de l’accès utilisateur externe pour votre organisation. Pour contrôler l’utilisation de l’accès des utilisateurs externes, vous devez configurer une ou plusieurs stratégies, spécifiant le type d’accès des utilisateurs externes pris en charge pour chaque stratégie. Les étendues de stratégie suivantes sont disponibles pour la création et la configuration. Par défaut, la stratégie globale est créée, mais ne peut pas être supprimée.

  - **Stratégie globale**   la stratégie globale est créée lorsque vous déployez vos serveurs Edge. Par défaut, aucune option d’accès utilisateur externe n’est activées dans la stratégie globale. Pour prendre en charge l’accès des utilisateurs externes au niveau global, vous configurez la stratégie globale pour prendre en charge un ou plusieurs types d’options d’accès utilisateur externe. La stratégie globale s’applique à tous les utilisateurs de votre organisation, mais les stratégies de site et utilisateur remplacer la stratégie globale. Si vous supprimez la stratégie globale, vous ne le supprimez pas. Au lieu de cela, vous le réinitialiser les paramètres par défaut.

  - **Stratégie de site**   vous pouvez créer et configurer une ou plusieurs stratégies de site pour limiter la prise en charge pour l’accès des utilisateurs externes à des sites spécifiques. La configuration de la stratégie de site remplace la stratégie globale, uniquement pour le site pour lequel elle est définie. Par exemple, si vous activez l’accès des utilisateurs distants dans la stratégie globale, vous pouvez spécifier une stratégie de site qui désactive l’accès des utilisateurs distants pour un site spécifique. Par défaut, une stratégie de site est appliquée à tous les utilisateurs de ce site, mais vous pouvez attribuer une stratégie utilisateur à un utilisateur de remplacer le paramètre de stratégie de site.

  - **Stratégie utilisateur**   vous pouvez créer et configurer une ou plusieurs stratégies d’utilisateur pour limiter la prise en charge pour l’accès des utilisateurs distants à des utilisateurs spécifiques. La configuration dans la stratégie de site et de remplacements de la stratégie utilisateur global, mais uniquement pour les utilisateurs auxquels la stratégie utilisateur est affectée. Par exemple, si vous activez l’accès des utilisateurs distants dans la stratégie globale et stratégie de site, vous spécifiez une stratégie utilisateur désactive l’accès des utilisateurs distants et ensuite affecter cette stratégie utilisateur à des utilisateurs spécifiques. Si vous créez une stratégie utilisateur, vous devez l’appliquer à un ou plusieurs utilisateurs avant de prendre effet.


> [!IMPORTANT]  
> Paramètres de stratégie qui sont appliqués à un niveau de stratégie peuvent remplacer les paramètres qui sont appliqués au niveau de stratégie d’une autre. Skype pour la priorité de la stratégie Business Server est : stratégie utilisateur (influencent la plupart) substitue à une stratégie de Site, puis une stratégie de Site substitue à une stratégie globale (influence moins). Cela signifie que le paramètre de stratégie est proche de l’objet qui affecte la stratégie, la plus grande influence sur l’objet.


Ces options comprennent les types suivants d’accès externe :

  - **Activer les communications avec les utilisateurs fédérés**   activez-le si vous souhaitez prendre en charge de l’accès des utilisateurs aux domaines de partenaire fédéré. Ce paramètre configure la possibilité aux utilisateurs de communiquer avec d’autres domaines, ainsi que les fournisseurs hébergés à Microsoft Office 365 de fédérés SIP. 


  - **Activer les communications avec des utilisateurs distants**   activer cette option si vous souhaitez que les utilisateurs de votre organisation qui sont trouvent en dehors de votre pare-feu, tels que les télétravailleurs et les utilisateurs qui sont en déplacement, pour être en mesure de se connecter à Skype pour Business Server via Internet.

  - **Activer les communications avec des utilisateurs publics**   activer cette option si vous souhaitez que les utilisateurs internes puissent communiquer avec des contacts de fournisseur de messagerie instantanée publique.
   

> [!NOTE]  
> Outre l’activation de l’accès des utilisateurs externes prennent en charge, vous devez également configurer des stratégies de contrôle de l’utilisation de l’accès des utilisateurs externes de votre organisation avant de n’importe quel type d’accès des utilisateurs externes est accessible aux utilisateurs. Pour plus d’informations sur la création, la configuration et l’application des stratégies pour l’accès des utilisateurs externes, voir [Activer ou désactiver l’accès des utilisateurs distants](../access-edge/enable-or-disable-remote-user-access.md).



**Pour afficher les stratégies d’accès externe à l’aide des applets de commande Windows PowerShell**

  - Vous pouvez afficher les stratégies d’accès externe à l’aide de Skype pour Business Server Management Shell et l’applet de commande **Get-CsExternalAccessPolicy** . Vous pouvez exécuter cette applet de commande à partir de la Skype pour Business Server Management Shell ou d’une session à distance de Windows PowerShell. 
    
    Pour afficher des informations sur toutes les stratégies d’accès externe, tapez la commande suivante dans Lync Server Management Shell, puis appuyez sur ENTRÉE :
    
    `Get-CsExternalAccessPolicy`
    
    Cette commande renvoie le type d’informations suivant :
    
    ```
    Identity                          : Global
    Description                       :
    EnableFederationAccess            : False
    EnableXmppAccess                  : False
    EnablePublicCloudAccess           : False
    EnablePublicCloudAudioVideoAccess : False
    EnableOutsideAccess               : False
    ```
