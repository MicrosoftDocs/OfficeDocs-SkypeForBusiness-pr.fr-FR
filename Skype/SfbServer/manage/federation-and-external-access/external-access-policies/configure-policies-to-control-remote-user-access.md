---
title: Configuration des stratégies de contrôle d’accès des utilisateurs distants
ms.reviewer: ''
ms:assetid: 8f556849-692b-44a0-9514-4468fc9a39d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398725(v=OCS.15)
ms:contentKeyID: 48184825
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Vous configurez une ou plusieurs stratégies d’accès des utilisateurs externes pour contrôler si les utilisateurs distants peuvent collaborer avec des utilisateurs de Skype entreprise Server internes. Pour contrôler l’accès des utilisateurs distants, vous pouvez configurer des stratégies au niveau du site, du site et de l’utilisateur.
ms.openlocfilehash: 96d91179e7b99910182ff360920f3d46b80aa6f4
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280137"
---
# <a name="configure-policies-to-control-remote-user-access-in-skype-for-business-server"></a>Configurer des stratégies pour contrôler l’accès des utilisateurs distants dans Skype entreprise Server

Vous configurez une ou plusieurs stratégies d’accès des utilisateurs externes pour contrôler si les utilisateurs distants peuvent collaborer avec des utilisateurs de Skype entreprise Server internes. Pour contrôler l’accès des utilisateurs distants, vous pouvez configurer des stratégies au niveau du site, du site et de l’utilisateur. Les stratégies de site remplacent la stratégie globale et les stratégies d’utilisateur remplacent les stratégies de site et globales. Pour plus d’informations sur les types de stratégies que vous pouvez configurer, voir gestion de la [Fédération et accès externe à Skype entreprise Server](../managing-federation-and-external-access.md). Les paramètres de stratégie de Skype entreprise Server appliqués à un niveau de stratégie peuvent remplacer les paramètres appliqués à un autre niveau de stratégie. Le niveau de priorité de la stratégie de Skype entreprise Server est le suivant: la stratégie de l’utilisateur (la plus influence) remplace une stratégie de site, puis une stratégie de site remplace une stratégie globale (moins l’influence). Cela signifie que le paramètre de stratégie est plus proche de l’objet affecté par la stratégie, plus l’influence sur l’objet.

> [!NOTE]  
> Vous pouvez configurer des stratégies pour contrôler l’accès des utilisateurs distants, même si vous n’avez pas activé l’accès des utilisateurs distants pour votre organisation. Toutefois, les stratégies que vous configurez ne s’appliquent que si l’accès des utilisateurs distants est activé pour votre organisation. Par ailleurs, si vous spécifiez une stratégie utilisateur pour contrôler l’accès des utilisateurs distants, la stratégie s’applique uniquement aux utilisateurs qui sont activés pour Skype entreprise Server et qui sont configurés pour utiliser cette stratégie. Pour plus d’informations sur la spécification des utilisateurs qui peuvent se connecter à Skype entreprise Server à partir d’emplacements distants, voir [affecter une stratégie d’accès des utilisateurs externes](assign-an-external-user-access-policy.md).

Utilisez la procédure suivante pour configurer chaque stratégie d’accès externe à utiliser pour contrôler l’accès des utilisateurs distants.


> [!NOTE]  
> Cette procédure décrit comment configurer une stratégie uniquement pour activer les communications avec les utilisateurs distants, mais chaque stratégie que vous configurez pour prendre en charge l’accès des utilisateurs distants peut également configurer l’accès des utilisateurs fédérés et l’accès des utilisateurs publics. Pour plus d’informations sur la configuration des stratégies pour la prise en charge des utilisateurs fédérés, voir [configurer des stratégies pour contrôler l’accès des utilisateurs fédérés dans Skype entreprise Server](configure-policies-to-control-federated-user-access.md). Pour plus d’informations sur la configuration des stratégies permettant de prendre en charge les utilisateurs publics, voir [gérer les fournisseurs fédérés SIP pour votre organisation dans Skype entreprise Server](../sip-providers/manage-sip-federated-providers-for-your-organization.md).


## <a name="to-configure-an-external-access-policy-to-support-remote-user-access"></a>Pour configurer une stratégie d’accès externe pour prendre en charge l’accès des utilisateurs distants

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server. 

3.  Dans la barre de navigation de gauche, cliquez sur **accès utilisateur externe**, puis sur **stratégie d’accès externe**.

4.  Dans la page de **stratégie d’accès externe** , effectuez l’une des opérations suivantes:
    
      - Pour configurer la stratégie globale de manière à prendre en charge l’accès des utilisateurs distants, cliquez sur la stratégie globale, cliquez sur **modifier**, puis sur **afficher les détails**.
    
      - Pour créer une stratégie de site, cliquez sur **nouveau**, puis cliquez sur **stratégie de site**. Dans **Sélectionner un site**, cliquez sur le site approprié dans la liste, puis cliquez sur **OK**.
    
      - Pour créer une nouvelle stratégie d’utilisateur, cliquez sur **nouveau**, puis cliquez sur stratégie de l' **utilisateur**. Dans **nouvelle stratégie d’accès externe**, créez un nom unique dans le champ **nom** qui indique le texte de la stratégie de l’utilisateur (par exemple, **EnableRemoteUsers** pour une stratégie utilisateur qui autorise les communications pour les utilisateurs distants).
    
      - Pour modifier une stratégie existante, cliquez sur la stratégie appropriée répertoriée dans le tableau, cliquez sur **modifier**, puis sur **afficher les détails**.

5.  Facultatif Si vous souhaitez ajouter ou modifier une description, spécifiez les informations relatives à la stratégie dans **Description**.

6.  Effectuez l’une des actions suivantes :
    
      - Pour autoriser l’accès des utilisateurs distants à la stratégie, activez la case à cocher **activer les communications avec les utilisateurs** distants.
    
      - Pour désactiver l’accès des utilisateurs distants de la stratégie, décochez la case **activer les communications avec les utilisateurs** distants.

7.  Cliquez sur **Valider**.

Pour autoriser l’accès des utilisateurs distants, vous devez également activer la prise en charge de l’accès des utilisateurs distants au sein de votre organisation. Pour plus d’informations, voir [activer ou désactiver la connectivité de Fédération et de messagerie instantanée publique](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md).

S’il s’agit d’une stratégie de l’utilisateur, vous devez également appliquer la stratégie aux utilisateurs auxquels vous voulez vous connecter à distance. Pour plus d’informations, voir [affecter une stratégie d’accès utilisateur externe](assign-an-external-user-access-policy.md).
