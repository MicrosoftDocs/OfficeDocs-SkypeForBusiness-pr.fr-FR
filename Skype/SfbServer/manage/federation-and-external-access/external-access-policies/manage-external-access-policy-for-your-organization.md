---
title: Gestion de la stratégie d’accès externe pour votre organisation
ms.reviewer: ''
ms:assetid: 5571811e-34c8-443a-b94c-1ab5d4275581
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520995(v=OCS.15)
ms:contentKeyID: 48184160
mtps_version: v=OCS.15
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Une fois que vous avez déployé un ou plusieurs serveurs Edge, vous devez activer les types d’accès externes qui seront pris en charge pour votre organisation.
ms.openlocfilehash: 19ce17e4b33fee39c6b37df8967e6045ac3840dc
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60835292"
---
# <a name="manage-external-access-policy-for-your-organization"></a>Gestion de la stratégie d’accès externe pour votre organisation

Une fois que vous avez déployé un ou plusieurs serveurs Edge, vous devez activer les types d’accès externes qui seront pris en charge pour votre organisation.

Par défaut, aucune stratégie n’est configurée pour prendre en charge l’accès des utilisateurs externes, notamment l’accès des utilisateurs distants et des utilisateurs fédérés, même si vous avez déjà activé la prise en charge de l’accès des utilisateurs externes dans votre organisation. Pour contrôler l’accès des utilisateurs externes, vous devez configurer une ou plusieurs stratégies en spécifiant le type d’accès des utilisateurs externes pris en charge. Les étendues de stratégies suivantes sont disponibles à des fins de création et de configuration. Par défaut, la stratégie globale est créée mais elle ne peut pas être supprimée.

  - **Stratégie globale**   La stratégie globale est créée lors du déploiement des serveurs Edge. Par défaut, aucune option d’accès des utilisateurs externes n’est activée dans cette stratégie. Pour prendre en charge l’accès des utilisateurs externes au niveau global, vous devez configurer la stratégie globale pour qu’elle prenne en charge un ou plusieurs types d’option d’accès des utilisateurs externes. La stratégie globale s’applique à tous les utilisateurs de votre organisation. Toutefois, les stratégies de niveau site et utilisateur la supplantent. Si vous supprimez la stratégie globale, il n’est pas nécessaire de la retirer. Il vous suffit de rétablir ses paramètres par défaut.

  - **Stratégie de site**   Vous pouvez créer et configurer une ou plusieurs stratégies de site pour limiter la prise en charge de l’accès des utilisateurs externes à des sites spécifiques. La stratégie de site supplante la stratégie globale, uniquement pour le site pour lequel elle est définie. Par exemple, si vous activez l’accès des utilisateurs distants dans la stratégie globale, vous pouvez spécifier une stratégie de site qui désactive l’accès sur un site donné. Par défaut, une stratégie de site s’applique à tous les utilisateurs de ce site. Vous pouvez affecter une stratégie utilisateur qui supplante la stratégie de site.

  - **Stratégie utilisateur**   Vous pouvez créer et configurer une ou plusieurs stratégies utilisateur pour limiter la prise en charge de l’accès des utilisateurs distants à des utilisateurs spécifiques. La stratégie utilisateur supplante les stratégies globale et de site, uniquement pour les utilisateurs auxquels elle est affectée. Par exemple, si vous activez l’accès des utilisateurs distants dans les stratégies globale et de site, vous pouvez définir une stratégie utilisateur qui désactive l’accès des utilisateurs distants et l’affecter à des utilisateurs spécifiques. Si vous créez une stratégie utilisateur, vous devez l’appliquer à un ou plusieurs utilisateurs pour qu’elle prenne effet.


> [!IMPORTANT]  
> Les paramètres de stratégie appliqués au niveau d’une stratégie peuvent remplacer les paramètres appliqués à un autre niveau de stratégie. La politique de priorité de Skype Entreprise Server est la suivante : la stratégie utilisateur (la plus influente) remplace une stratégie site, et une stratégie site remplace une stratégie globale (la moins influente). Cela signifie que plus le paramètre de stratégie est proche de l’objet que la stratégie affecte, plus elle a d’influence sur l’objet.


Ces options incluent les types d’accès externe suivants :

  - **Activer les communications avec les utilisateurs fédérés**   Activez-le si vous souhaitez prendre en charge l’accès des utilisateurs aux domaines des partenaires fédérés. Ce paramètre configure la possibilité pour les utilisateurs de communiquer avec d’autres domaines fédérés SIP, ainsi que des fournisseurs hébergés tels que Microsoft 365 ou Office 365. 


  - **Activer les communications avec des utilisateurs distants**   Activez cette option si vous souhaitez que les utilisateurs de votre organisation qui sont en dehors de votre pare-feu, tels que les télétravailleurs et les utilisateurs en déplacement, puissent se connecter à Skype Entreprise Server via Internet.

  - **Activer les communications avec les utilisateurs publics**   Activez cette option si vous souhaitez que les utilisateurs internes puissent communiquer avec les contacts du fournisseur de messagerie instantanée public.
   

> [!NOTE]  
> En plus d’activer la prise en charge de l’accès des utilisateurs externes, vous devez aussi configurer les stratégies permettant de contrôler l’utilisation de l’accès des utilisateurs externes dans votre organisation avant que tout type d’accès des utilisateurs externes ne soit mis à la disposition des utilisateurs. Pour plus d’informations sur la création, la configuration et l’application des stratégies d’accès des utilisateurs externes, consultez [Activer ou désactiver l'accès des utilisateurs à distance](../access-edge/enable-or-disable-remote-user-access.md).



**Pour afficher les stratégies d’accès externe à l’aide des applets de commande Windows PowerShell**

  - Vous pouvez afficher les stratégies d’accès externe à l’aide de Skype Entreprise Server Management Shell et de l’applet de commande **Get-CsExternalAccessPolicy**. Vous pouvez exécuter cette applet de commande à partir de Skype Entreprise Server Management Shell ou d’une session distante de Windows PowerShell. 
    
    Pour afficher des informations sur l’ensemble de vos stratégies d’accès externes, tapez la commande suivante dans Lync Server Management Shell, puis appuyez sur Entrée :
    
    `Get-CsExternalAccessPolicy`
    
    Cette commande renvoie des informations comme celles-ci :
    
    ```console
    Identity                          : Global
    Description                       :
    EnableFederationAccess            : False
    EnableXmppAccess                  : False
    EnablePublicCloudAccess           : False
    EnablePublicCloudAudioVideoAccess : False
    EnableOutsideAccess               : False
    ```
