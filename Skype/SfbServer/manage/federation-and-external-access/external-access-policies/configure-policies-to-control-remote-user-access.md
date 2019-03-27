---
title: Configuration des stratégies de contrôle d’accès des utilisateurs distants
ms.reviewer: ''
ms:assetid: 8f556849-692b-44a0-9514-4468fc9a39d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398725(v=OCS.15)
ms:contentKeyID: 48184825
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Vous configurez une ou plusieurs stratégies d’accès utilisateur externe au contrôle si les utilisateurs distants peuvent collaborer avec Skype interne pour les utilisateurs Business Server. Pour contrôler l’accès des utilisateurs distants, vous pouvez configurer des stratégies au niveau global, site et au niveau utilisateur.
ms.openlocfilehash: f6d316f022e671bc7f7e70ebbe2a801b0b3e312c
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30899532"
---
# <a name="configure-policies-to-control-remote-user-access-in-skype-for-business-server"></a>Configurer des stratégies de contrôle d’accès des utilisateurs distants dans Skype pour Business Server

Vous configurez une ou plusieurs stratégies d’accès utilisateur externe au contrôle si les utilisateurs distants peuvent collaborer avec Skype interne pour les utilisateurs Business Server. Pour contrôler l’accès des utilisateurs distants, vous pouvez configurer des stratégies au niveau global, site et au niveau utilisateur. La stratégie globale remplacent les stratégies de site et utilisateur remplacent les stratégies globales et site. Pour plus d’informations sur les types de stratégies que vous pouvez configurer, voir [Managing fédération et accès externe aux Skype pour Business Server](../managing-federation-and-external-access.md). Skype pour les paramètres de stratégie Business Server qui sont appliqués à un niveau de stratégie permettre remplacer les paramètres qui sont appliqués au niveau de stratégie d’une autre. Skype pour la priorité de la stratégie Business Server est : stratégie utilisateur (influencent la plupart) substitue à une stratégie de Site, puis une stratégie de Site substitue à une stratégie globale (influence moins). Cela signifie que le paramètre de stratégie est proche de l’objet qui affecte la stratégie, la plus grande influence sur l’objet.

> [!NOTE]  
> Vous pouvez configurer des stratégies de contrôle d’accès des utilisateurs distants, même si vous n’avez pas activé l’accès des utilisateurs distants pour votre organisation. Toutefois, les stratégies que vous configurez sont en effet que lorsque vous avez l’accès des utilisateurs distants pour votre organisation. En outre, si vous spécifiez une stratégie utilisateur pour contrôler l’accès des utilisateurs distants, la stratégie s’applique uniquement aux utilisateurs qui sont activés pour Skype pour Business Server et configurés pour utiliser la stratégie. Pour plus d’informations sur la spécification des utilisateurs qui peuvent se connecter à Skype pour Business Server à partir d’emplacements distants, voir [attribuer une stratégie d’accès utilisateur externe](assign-an-external-user-access-policy.md).

Utilisez la procédure suivante pour configurer chaque stratégie d’accès externe que vous souhaitez utiliser pour contrôler l’accès des utilisateurs distants.


> [!NOTE]  
> Cette procédure explique comment configurer une stratégie uniquement pour activer les communications avec des utilisateurs distants, mais chaque stratégie que vous configurez pour prendre en charge l’accès des utilisateurs distants permettre également configurer l’accès des utilisateurs fédérés et l’accès des utilisateurs publics. Pour plus d’informations sur la configuration des stratégies pour prendre en charge les utilisateurs fédérés, voir [configurer les stratégies de contrôle d’un accès utilisateur dans Skype pour Business Server fédéré](configure-policies-to-control-federated-user-access.md). Pour plus d’informations sur la configuration des stratégies pour prendre en charge des utilisateurs publics, consultez la rubrique [Manage SIP federated fournisseurs pour votre organisation dans Skype pour Business Server](../sip-providers/manage-sip-federated-providers-for-your-organization.md).


## <a name="to-configure-an-external-access-policy-to-support-remote-user-access"></a>Pour configurer une stratégie d’accès externe pour prendre en charge l’accès des utilisateurs distants

1.  À partir d’un compte d’utilisateur qui est membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou est affecté au rôle CsAdministrator, ouvrez une session sur n’importe quel ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business. 

3.  Dans la barre de navigation de gauche, cliquez sur **Accès des utilisateurs externes**, puis cliquez sur **Stratégie d’accès externe**.

4.  Dans la page **Stratégie d’accès externe** , effectuez l’une des options suivantes :
    
      - Pour configurer la stratégie globale pour prendre en charge l’accès des utilisateurs distants, cliquez sur la stratégie globale, cliquez sur **Modifier**, puis cliquez sur **Afficher les détails**.
    
      - Pour créer une stratégie de site, cliquez sur **Nouveau**, puis cliquez sur **stratégie de Site**. Dans **Sélectionner un Site**, cliquez sur le site approprié dans la liste, puis cliquez sur **OK**.
    
      - Pour créer une nouvelle stratégie utilisateur, cliquez sur **Nouveau**, puis cliquez sur **stratégie de l’utilisateur**. Dans la **Nouvelle stratégie d’accès externe**, créez un nom unique dans le champ **nom** qui indique quel utilisateur concernés par cette stratégie (par exemple, **EnableRemoteUsers** pour une stratégie d’utilisateur qui permet les communications des utilisateurs distants).
    
      - Pour modifier une stratégie existante, cliquez sur la stratégie appropriée dans le tableau, cliquez sur **Modifier**, puis cliquez sur **Afficher les détails**.

5.  (Facultatif) Si vous souhaitez ajouter ou modifier une description, spécifiez les informations de la stratégie dans la zone **Description**.

6.  Effectuez l’une des actions suivantes :
    
      - Pour activer l’accès des utilisateurs distants pour la stratégie, activez la case à cocher **Activer les communications avec des utilisateurs distants** .
    
      - Pour désactiver l’accès des utilisateurs distants pour la stratégie, désactivez la case à cocher **Activer les communications avec des utilisateurs distants** .

7.  Cliquez sur **Valider**.

Pour activer l’accès des utilisateurs distants, vous devez également activer la prise en charge pour l’accès des utilisateurs distants de votre organisation. Pour plus d’informations, voir [Activer ou désactiver la fédération et la connectivité PIC](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md).

S’il s’agit d’une stratégie utilisateur, vous devez également appliquer la stratégie aux utilisateurs que vous souhaitez être en mesure de se connecter à distance. Pour plus d’informations, voir [attribuer une stratégie d’accès utilisateur externe](assign-an-external-user-access-policy.md).
