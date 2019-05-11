---
title: Configuration des stratégies de contrôler d’accès des utilisateurs fédérés
ms.reviewer: ''
ms:assetid: 5485e208-81e4-4e59-9aeb-1232c11dd8a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398359(v=OCS.15)
ms:contentKeyID: 48184180
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Lorsque vous configurez des stratégies pour prendre en charge les communications avec les partenaires fédérés, les stratégies s’appliquent aux utilisateurs des domaines fédérés. '
ms.openlocfilehash: 81eced8db10c9ffd017b5b79a54980b773b300bb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33920657"
---
# <a name="configure-policies-to-control-federated-user-access-in-skype-for-business-server"></a>Configurer des stratégies de contrôle d’accès des utilisateurs fédérés dans Skype pour Business Server

Lorsque vous configurez des stratégies pour prendre en charge les communications avec les partenaires fédérés, les stratégies s’appliquent aux utilisateurs des domaines fédérés. Vous pouvez configurer un ou plusieurs stratégies d’accès utilisateur externe au contrôle si les utilisateurs des domaines fédérés peuvent collaborer avec vos Skype pour les utilisateurs Business Server. Pour contrôler l’accès des utilisateurs fédérés, vous pouvez configurer des stratégies au niveau global, site et au niveau utilisateur. Skype pour les paramètres de stratégie Business Server qui sont appliqués à un niveau de stratégie permettre remplacer les paramètres qui sont appliqués au niveau de stratégie d’une autre. Skype pour la priorité de la stratégie Business Server est : stratégie utilisateur (influencent la plupart) substitue à une stratégie de Site, puis une stratégie de Site substitue à une stratégie globale (influence moins). Cela signifie que le paramètre de stratégie est proche de l’objet qui affecte la stratégie, la plus grande influence sur l’objet.


> [!NOTE]  
> Vous pouvez configurer des stratégies de contrôle d’accès des utilisateurs fédérés, même si vous n’avez pas activé la fédération pour votre organisation. Toutefois, les stratégies que vous configurez sont en effet que lorsque vous avez activée pour votre organisation de fédération. Pour plus d’informations sur l’activation de la fédération, voir [Activer ou désactiver l’accès des utilisateurs distants](../access-edge/enable-or-disable-remote-user-access.md).  En outre, si vous spécifiez une stratégie utilisateur pour contrôler l’accès des utilisateurs fédérés, la stratégie s’applique uniquement aux utilisateurs qui sont activés pour Skype pour Business Server et configurés pour utiliser la stratégie.


## <a name="to-configure-a-policy-to-support-access-by-users-of-federated-domains"></a>Pour configurer une stratégie pour prendre en charge l’accès par les utilisateurs des domaines fédérés

1.  À partir d’un compte d’utilisateur qui est membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou est affecté au rôle CsAdministrator, ouvrez une session sur n’importe quel ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business.

3.  Dans la barre de navigation de gauche, cliquez sur **Accès des utilisateurs externes**, puis cliquez sur **Stratégie d’accès externe**.

4.  Dans la page **Stratégie d’accès externe** , effectuez l’une des options suivantes :
    
      - Pour configurer la stratégie globale pour prendre en charge l’accès des utilisateurs fédérés, cliquez sur la stratégie globale, cliquez sur **Modifier**, puis cliquez sur **Afficher les détails**.
    
      - Pour créer une stratégie de site, cliquez sur **Nouveau**, puis cliquez sur **stratégie de Site**. Dans **Sélectionner un Site**, cliquez sur le site approprié dans la liste, puis cliquez sur **OK**.
    
      - Pour créer une nouvelle stratégie utilisateur, cliquez sur **Nouveau**, puis cliquez sur **stratégie de l’utilisateur**. Dans la **Nouvelle stratégie d’accès externe**, créez un nom unique dans le champ **nom** qui indique quel utilisateur concernés par cette stratégie (par exemple, **EnableFederatedUsers** pour une stratégie d’utilisateur qui permet de communications pour les utilisateurs du domaine fédéré).
    
      - Pour modifier une stratégie existante, cliquez sur la stratégie appropriée dans le tableau, cliquez sur **Modifier**, puis cliquez sur **Afficher les détails**.

5.  (Facultatif) Si vous souhaitez ajouter ou modifier une description, spécifiez les informations de la stratégie dans la zone **Description**.

6.  Effectuez l’une des actions suivantes :
    
      - Pour activer l’accès des utilisateurs fédérés pour la stratégie, activez la case à cocher **Activer les communications avec les utilisateurs fédérés** .
    
      - Pour désactiver l’accès des utilisateurs fédérés pour la stratégie, désactivez la case à cocher **Activer les communications avec les utilisateurs fédérés** .

7.  Cliquez sur **Valider**.

Pour activer l’accès des utilisateurs fédérés, vous devez également activer la prise en charge pour la fédération dans votre organisation. Pour plus d’informations, voir [Activer ou désactiver la fédération et la connectivité PIC](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md).

S’il s’agit d’une stratégie utilisateur, vous devez également appliquer la stratégie aux utilisateurs que vous souhaitez être en mesure de collaborer avec des utilisateurs fédérés. Pour plus d’informations, voir [attribuer une stratégie d’accès utilisateur externe](assign-an-external-user-access-policy.md).

## <a name="to-configure-an-existing-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a>Pour configurer une stratégie existante à l’aide de Windows PowerShell pour prendre en charge l’accès par les utilisateurs des domaines fédérés

1.  À partir d’un compte d’utilisateur qui est membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou est affecté au rôle CsAdministrator, ouvrez une session sur n’importe quel ordinateur dans votre déploiement interne.

2.  Démarrez le Skype pour Busines Server Management Shell : cliquez sur **Démarrer**, sur **Tous les programmes**, cliquez sur **Skype pour Business Server**, puis cliquez sur **Skype pour Business Server Management Shell**.

3.  Tapez ce qui suit dans le Skype pour Business Server Management Shell :
    
    ```
    Set-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAcess <$true, $false> -EnablePublicCloudAudioVideoAcess <$true, $false> -EnableOutsideAcess <$true, $false>
    ```
       

    > [!TIP]  
    > Le paramètre « EnablePublicCloudAudioVideoAccess » n’a pas de sélection correspondante dans le Skype pour Business Server Control Panel


## <a name="to-create-a-new-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a>Pour créer une nouvelle stratégie à l’aide de Windows PowerShell pour prendre en charge l’accès par les utilisateurs des domaines fédérés

1.  À partir d’un compte d’utilisateur qui est membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou est affecté au rôle CsAdministrator, ouvrez une session sur n’importe quel ordinateur dans votre déploiement interne.

2.  Démarrez le Skype pour Business Server Management Shell : cliquez sur **Démarrer**, sur **Tous les programmes**, cliquez sur **Microsoft Skype pour Business Server**, puis cliquez sur **Skype pour Business Server Management Shell**.

3.  Tapez ce qui suit dans le Skype pour Business Server Management Shell :
    
    ```
    New-CsExtenalAccessPolicy -Identity <name of site or user policy - you cannot create a new global policy using New-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAccess <$true, $false> -EnablePublicCloudAudioVideoAccess <$true, $false> -EnableOutsideAccess <$true, $false>
    ```
    
    Exemple de création d’une stratégie de site :
    
    ```
    New-CsExternalAccessPolicy -Identity site:Redmond -EnableFederationAccess $true -EnableXmppAccess $true -EnableOutsideAccess $true -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true
    ```


## <a name="to-delete-or-reset-a-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a>Pour supprimer ou réinitialiser une stratégie à l’aide de Windows PowerShell pour prendre en charge l’accès par les utilisateurs des domaines fédérés

1.  À partir d’un compte d’utilisateur qui est membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou est affecté au rôle CsAdministrator, ouvrez une session sur n’importe quel ordinateur dans votre déploiement interne.

2.  Tapez ce qui suit dans le Skype pour Business Server Management Shell
    
    `Remove-CsExternalAccessPolicy -Identity <name of global, site or user policy>`
    
    Un exemple de la réinitialisation de la stratégie globale (la stratégie globale ne peut avoir le paramètre supprimé. La stratégie ne peut pas être supprimée) :
    
    `Remove-CsExternalAccessPolicy -Identity global`
    
    Pour supprimer une stratégie de site, tapez :
    
    `Remove-CsExternalAccessPolicy -Identity site:Redmond` 
    
    Supprime la stratégie de site Redmond. Pour supprimer une stratégie utilisateur nommée UserEAPPolicy, tapez :
    
    `Remove-CsExternalAccessPolicy -Identity UserEAPPolicy`


## <a name="see-also"></a>Voir aussi


[Activation ou désactivation de la fédération et de la connectivité PIC](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md) 

[Attribution d’une stratégie d’accès des utilisateurs externes](assign-an-external-user-access-policy.md)

[Gestion des domaines fédérés SIP pour l’organisation](../sip-domains/manage-sip-federated-domains-for-your-organization.md)
 
[Gestion des fournisseurs fédérés SIP pour l’organisation](../sip-providers/manage-sip-federated-providers-for-your-organization.md)

[Set-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsExternalAccessPolicy)  
[Nouvelle-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsExternalAccessPolicy)  
[Get-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsExternalAccessPolicy)  
[Remove-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy)  
[Grant-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsExternalAccessPolicy)  
  

