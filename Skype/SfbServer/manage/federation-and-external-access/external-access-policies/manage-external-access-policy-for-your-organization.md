---
title: Gestion de la stratégie d’accès externe pour l’organisation
ms.reviewer: ''
ms:assetid: 5571811e-34c8-443a-b94c-1ab5d4275581
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520995(v=OCS.15)
ms:contentKeyID: 48184160
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Après le déploiement d’un ou plusieurs serveurs Edge, vous devez activer les types d’accès externe qui seront pris en charge pour votre organisation.
ms.openlocfilehash: 014077fb331bc33933d0c673771f7765b9341570
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280116"
---
# <a name="manage-external-access-policy-for-your-organization"></a>Gestion de la stratégie d’accès externe pour l’organisation

Après le déploiement d’un ou plusieurs serveurs Edge, vous devez activer les types d’accès externe qui seront pris en charge pour votre organisation.

Par défaut, il n’y a pas de stratégies configurées pour prendre en charge l’accès des utilisateurs externes, y compris les accès utilisateurs distants, l’accès des utilisateurs fédérés, même si vous avez déjà activé la prise en charge de l’accès des utilisateurs externes pour votre organisation. Pour contrôler l’utilisation de l’accès des utilisateurs externes, vous devez configurer une ou plusieurs stratégies en spécifiant le type d’accès des utilisateurs externes pris en charge pour chaque stratégie. Les étendues de stratégie suivantes sont disponibles pour la création et la configuration. Par défaut, la stratégie globale est créée, mais elle ne peut pas être supprimée.

  - **Politique globale la**   stratégie globale est créée lors du déploiement de votre serveur Edge. Par défaut, aucune option d’accès utilisateur externe n’est activée dans la stratégie globale. Pour prendre en charge l’accès des utilisateurs externes au niveau global, vous pouvez configurer la stratégie globale pour prendre en charge un ou plusieurs types d’options d’accès utilisateurs externes. La politique globale s’applique à tous les utilisateurs de votre organisation, mais les stratégies de site et les stratégies d’utilisateur remplacent la stratégie globale. Si vous supprimez la stratégie globale, vous ne la supprimez pas. Au lieu de cela, vous rétablissez la valeur par défaut.

  - **Stratégie de site**   vous pouvez créer et configurer une ou plusieurs stratégies de site pour limiter l’accès des utilisateurs externes à des sites spécifiques. La configuration de la stratégie de site remplace la stratégie globale, uniquement pour le site pour lequel elle est définie. Par exemple, si vous autorisez l’accès des utilisateurs distants dans la stratégie globale, vous pouvez spécifier une stratégie de site qui désactive l’accès des utilisateurs distants pour un site spécifique. Par défaut, une stratégie de site est appliquée à tous les utilisateurs de ce site, mais vous pouvez affecter une stratégie d’utilisateur à un utilisateur pour remplacer le paramètre de stratégie de site.

  - **Stratégie**   de l’utilisateur vous pouvez créer et configurer une ou plusieurs stratégies utilisateur pour limiter la prise en charge de l’accès des utilisateurs distants à des utilisateurs spécifiques. La configuration de la stratégie utilisateur remplace la stratégie globale et la stratégie de site, mais uniquement pour les utilisateurs spécifiques auxquels la stratégie utilisateur est affectée. Par exemple, si vous autorisez l’accès des utilisateurs distants dans la stratégie globale et la stratégie de site, vous pouvez spécifier une stratégie d’utilisateur qui désactive l’accès des utilisateurs distants, puis affecter cette stratégie à des utilisateurs spécifiques. Si vous créez une stratégie d’utilisateur, vous devez l’appliquer à un ou plusieurs utilisateurs avant qu’elle ne soit appliquée.


> [!IMPORTANT]  
> Les paramètres de stratégie appliqués à un niveau de stratégie peuvent remplacer les paramètres appliqués à un autre niveau de stratégie. Le niveau de priorité de la stratégie de Skype entreprise Server est le suivant: la stratégie de l’utilisateur (la plus influence) remplace une stratégie de site, puis une stratégie de site remplace une stratégie globale (moins l’influence). Cela signifie que le paramètre de stratégie est plus proche de l’objet affecté par la stratégie, plus l’influence sur l’objet.


Ces options incluent les types d’accès externes suivants:

  - **Activer les communications avec les utilisateurs**   fédérés activez cette fonction si vous souhaitez prendre en charge l’accès des utilisateurs aux domaines partenaires fédérés. Ce paramètre configure la possibilité pour les utilisateurs de communiquer avec d’autres domaines fédérés SIP, ainsi que des fournisseurs hébergés tels que Microsoft Office 365. 


  - **Activer les communications avec les utilisateurs**   distants activez cette option si vous souhaitez que les utilisateurs de votre organisation qui se trouvent en dehors de votre pare-feu (par exemple, les télétravailleurs et les utilisateurs qui voyagent) puissent se connecter à Skype entreprise Server via Internet.

  - **Activer les communications avec les utilisateurs**   publics activez cette option si vous souhaitez que les utilisateurs internes puissent communiquer avec des contacts de fournisseurs de messagerie instantanée publics.
   

> [!NOTE]  
> Outre l’activation de la prise en charge de l’accès des utilisateurs externes, vous devez également configurer des stratégies pour contrôler l’utilisation de l’accès des utilisateurs externes au sein de votre organisation avant de pouvoir accéder aux utilisateurs externes. Pour plus d’informations sur la création, la configuration et l’application de stratégies pour l’accès des utilisateurs externes, voir [activer ou désactiver l’accès des utilisateurs](../access-edge/enable-or-disable-remote-user-access.md)distants.



**Pour afficher les stratégies d’accès externe à l’aide des cmdlets Windows PowerShell**

  - Vous pouvez afficher les stratégies d’accès externe à l’aide de Skype entreprise Server Management Shell et de l’applet **de passe Get-CsExternalAccessPolicy** . Vous pouvez exécuter cette applet de commande dans Skype entreprise Server Management Shell ou à partir d’une session distante de Windows PowerShell. 
    
    Pour afficher des informations sur les stratégies d’accès externe, tapez la commande suivante dans Lync Server Management Shell, puis appuyez sur entrée:
    
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
