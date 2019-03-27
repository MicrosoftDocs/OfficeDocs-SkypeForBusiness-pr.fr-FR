---
title: Activation ou désactivation de l’accès des utilisateurs distants
ms.reviewer: ''
ms:assetid: cd9d3ddc-4839-457a-86d9-b15413e74002
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182586(v=OCS.15)
ms:contentKeyID: 48185660
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Si vous activez l’accès des utilisateurs distants pour les utilisateurs distants, pris en charge les utilisateurs distants se connectent via Internet et n’ont pas à se connecter à l’aide d’un réseau privé virtuel pour collaborer avec des utilisateurs internes à l’aide de Skype pour Business Server.
ms.openlocfilehash: aea136e6c8758fd646a20b8bc7a64a393d45a3e7
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30898915"
---
# <a name="enable-or-disable-remote-user-access-in-skype-for-business-server"></a>Activer ou désactiver l’accès des utilisateurs distants dans Skype pour Business Server

Les utilisateurs distants sont des utilisateurs de votre organisation qui ont une identité Active Directory persistante au sein de l’organisation. Les utilisateurs distants souvent connectez-vous à Skype pour Business Server à partir d’en dehors de votre réseau à l’aide d’un réseau privé virtuel (VPN) lorsqu’ils ne sont pas connectés au réseau de votre organisation. Les utilisateurs distants incluent les employés travaillant à domicile ou sur la route et d’autres travailleurs à distance, comme des fournisseurs approuvés, des informations d’identification de l’entreprise qui ont été accordées. Si vous activez l’accès des utilisateurs distants pour les utilisateurs distants, pris en charge les utilisateurs distants se connectent via Internet et n’ont pas à se connecter à l’aide d’un réseau privé virtuel pour collaborer avec des utilisateurs internes à l’aide de Skype pour Business Server.

Pour prendre en charge l’accès des utilisateurs distants, vous devez activer l’accès des utilisateurs distants. Lorsque vous activez l’accès des utilisateurs distants, vous l’activez pour toute votre organisation. Si vous souhaitez ultérieurement à titre temporaire ou permanent empêcher l’accès des utilisateurs distants, vous pouvez le désactiver pour votre organisation. Utilisez la procédure de cette section pour activer ou désactiver l’accès des utilisateurs distants pour votre organisation.


> [!NOTE]  
> Activer l’accès des utilisateurs distants indique uniquement que vos serveurs exécutant le service Edge d’accès prennent en charge les communications avec les utilisateurs distants, mais les utilisateurs distants ne peut pas participer à la messagerie instantanée (MI) ou des conférences dans votre organisation jusqu'à ce que vous configurez également au au moins une stratégie pour gérer l’utilisation de l’accès des utilisateurs distants. Skype pour les paramètres de stratégie Business Server qui sont appliqués à un niveau de stratégie permettre remplacer les paramètres qui sont appliqués au niveau de stratégie d’une autre. Skype pour la priorité de la stratégie Business Server est : stratégie utilisateur (influencent la plupart) substitue à une stratégie de Site, puis une stratégie de Site substitue à une stratégie globale (influence moins). Cela signifie que le paramètre de stratégie est proche de l’objet qui affecte la stratégie, la plus grande influence sur l’objet. Pour plus d’informations sur la configuration de stratégies pour l’utilisation de l’accès des utilisateurs distants, voir [Configuration des stratégies pour contrôler l’accès des utilisateurs distants dans Skype pour Business Server](../external-access-policies/configure-policies-to-control-remote-user-access.md).


## <a name="to-enable-or-disable-remote-user-access-for-your-organization"></a>Pour activer ou désactiver l’accès des utilisateurs distants pour votre organisation

1.  À partir d’un compte d’utilisateur qui est membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou est affecté au rôle CsAdministrator, ouvrez une session sur n’importe quel ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business. 

3.  Dans la barre de navigation de gauche, cliquez sur **Fédération et accès externe**, puis sur **Configuration du serveur Edge d’accès**.

4.  Dans la page **Configuration du serveur Edge d’accès** , cliquez sur **Global**, cliquez sur **Modifier**, puis cliquez sur **Afficher les détails**.

5.  Dans **Modifier la Configuration Edge accès**, effectuez l’une des options suivantes :
    
      - Pour activer l’accès des utilisateurs distants pour votre organisation, activez la case à cocher **Activer l’accès des utilisateurs distants** .
    
      - Pour désactiver l’accès des utilisateurs distants pour votre organisation, désactivez la case à cocher **Activer l’accès des utilisateurs distants** .

6.  Cliquez sur **Valider**.

Pour permettre aux utilisateurs distants de se connecter à vos serveurs exécutant Skype pour Business Server, vous devez également configurer au moins une stratégie d’accès externe pour prendre en charge l’accès des utilisateurs distants. Pour plus d’informations, voir [Configuration des stratégies pour contrôler l’accès des utilisateurs distants dans Skype pour Business Server](../external-access-policies/configure-policies-to-control-remote-user-access.md).


## <a name="enabling-or-disabling-remote-user-access-by-using-windows-powershell-cmdlets"></a>Activation ou désactivation de l’accès des utilisateurs distants à l’aide des applets de commande Windows PowerShell

Accès des utilisateurs distants peuvent être gérés à l’aide de Windows PowerShell et l’applet de commande Set-CsAccessEdgeConfiguration. Cette applet de commande peut être exécutée à partir de la Skype pour Business Server 2013 Management Shell ou à partir d’une session à distance de Windows PowerShell. 

## <a name="to-enable-remote-user-access"></a>Pour activer l’accès des utilisateurs distants

  - Pour activer l’accès des utilisateurs distants, définissez la valeur de la propriété **AllowOutsideUsers** sur True ($True) :
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $True

## <a name="to-disable-remote-user-access"></a>Pour désactiver l’accès des utilisateurs distants

  - Pour désactiver l’accès des utilisateurs distants, définissez la valeur de la propriété **AllowOutsideUsers** sur False ($False) :
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $False


