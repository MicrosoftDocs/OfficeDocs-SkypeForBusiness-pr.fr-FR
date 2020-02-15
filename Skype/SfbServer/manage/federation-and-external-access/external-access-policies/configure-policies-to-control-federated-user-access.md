---
title: Configurer des stratégies pour contrôler l’accès des utilisateurs fédérés
ms.reviewer: ''
ms:assetid: 5485e208-81e4-4e59-9aeb-1232c11dd8a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398359(v=OCS.15)
ms:contentKeyID: 48184180
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Lorsque vous configurez des stratégies pour prendre en charge les communications avec les partenaires fédérés, les stratégies s’appliquent aux utilisateurs de domaines fédérés. '
ms.openlocfilehash: 447aad751ce6fc91bf2d6b80c8a14e92f9d4da82
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037404"
---
# <a name="configure-policies-to-control-federated-user-access-in-skype-for-business-server"></a>Configuration des stratégies de contrôle d’accès des utilisateurs fédérés dans Skype entreprise Server

Lorsque vous configurez des stratégies pour prendre en charge les communications avec les partenaires fédérés, les stratégies s’appliquent aux utilisateurs de domaines fédérés. Vous pouvez configurer une ou plusieurs stratégies d’accès des utilisateurs externes pour contrôler si les utilisateurs de domaines fédérés peuvent collaborer avec vos utilisateurs de Skype entreprise Server. Pour contrôler l’accès des utilisateurs fédérés, vous pouvez configurer des stratégies au niveau global, site et utilisateur. Les paramètres de stratégie de Skype entreprise Server appliqués à un niveau de stratégie peuvent remplacer les paramètres appliqués à un autre niveau de stratégie. La priorité de la stratégie de Skype entreprise Server est la suivante : la stratégie utilisateur (la plus grande influence) remplace une stratégie de site, puis une stratégie de site remplace une stratégie globale (la moins influencée). Cela signifie que plus le paramètre de stratégie est proche de l’objet que la stratégie affecte, plus elle a d’influence sur l’objet.


> [!NOTE]  
> Vous pouvez configurer des stratégies pour contrôler l’accès des utilisateurs fédérés, même si vous n’avez pas activé la Fédération pour votre organisation. Toutefois, les stratégies que vous configurez s’appliquent uniquement si la fédération est activée pour votre organisation. Pour plus d’informations sur l’activation de la Fédération, consultez la rubrique [activer ou désactiver l’accès des utilisateurs distants](../access-edge/enable-or-disable-remote-user-access.md).  De plus, si vous spécifiez une stratégie utilisateur pour contrôler l’accès des utilisateurs fédérés, la stratégie s’applique uniquement aux utilisateurs qui sont activés pour Skype entreprise Server et qui sont configurés pour utiliser cette stratégie.


## <a name="to-configure-a-policy-to-support-access-by-users-of-federated-domains"></a>Pour configurer une stratégie afin de prendre en charge l’accès des utilisateurs des domaines fédérés

1.  Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Skype entreprise Server.

3.  Dans la barre de navigation de gauche, cliquez sur **Accès des utilisateurs externes**, puis sur **Stratégie d’accès externe**.

4.  Dans la page **Stratégie d’accès externe**, effectuez l’une des opérations suivantes :
    
      - Pour configurer la stratégie globale afin qu’elle prenne en charge l’accès des utilisateurs fédérés, cliquez sur la stratégie globale, sur **modifier**, puis sur **afficher les détails**.
    
      - Pour créer une nouvelle stratégie de site, cliquez sur **Nouveau**, puis sur **Stratégie du site**. Dans **Sélectionner un site**, cliquez sur le site approprié dans la liste, puis cliquez sur **OK**.
    
      - Pour créer une nouvelle stratégie utilisateur, cliquez sur **Nouveau**, puis sur **Stratégie de l’utilisateur**. Dans **nouvelle stratégie d’accès externe**, créez un nom unique dans le champ **nom** qui indique ce que couvre la stratégie utilisateur (par exemple, **EnableFederatedUsers** pour une stratégie utilisateur qui active les communications pour les utilisateurs de domaine fédéré).
    
      - Pour modifier une stratégie existante, cliquez sur la stratégie appropriée dans le tableau, cliquez sur **Modifier**, puis cliquez sur **Afficher les détails**.

5.  (Facultatif) Si vous souhaitez ajouter ou modifier une description, spécifiez les informations relatives à la stratégie dans **Description**.

6.  Effectuez l’une des opérations suivantes :
    
      - Pour activer l’accès des utilisateurs fédérés pour la stratégie, activez la case à cocher **autoriser les communications avec des utilisateurs fédérés** .
    
      - Pour désactiver l’accès des utilisateurs fédérés pour la stratégie, désactivez la case à cocher **autoriser les communications avec des utilisateurs fédérés** .

7.  Cliquez sur **Valider**.

Pour activer l’accès des utilisateurs fédérés, vous devez également activer la prise en charge de la Fédération dans votre organisation. Pour plus d’informations, consultez la rubrique [activation ou désactivation de la Fédération et de la connectivité PIC](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md).

S’il s’agit d’une stratégie utilisateur, vous devez également appliquer la stratégie aux utilisateurs que vous voulez être en mesure de collaborer avec des utilisateurs fédérés. Pour plus d’informations, consultez la rubrique [assigner une stratégie d’accès des utilisateurs externes](assign-an-external-user-access-policy.md).

## <a name="to-configure-an-existing-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a>Pour configurer une stratégie existante à l’aide de Windows PowerShell afin de prendre en charge l’accès des utilisateurs des domaines fédérés

1.  Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Démarrez Skype outil Server Management Shell : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Skype entreprise Server**, puis sur **Skype entreprise Server Management Shell**.

3.  Tapez ce qui suit dans Skype entreprise Server Management Shell :
    
    ```PowerShell
    Set-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAcess <$true, $false> -EnablePublicCloudAudioVideoAcess <$true, $false> -EnableOutsideAcess <$true, $false>
    ```
       

    > [!TIP]  
    > Le paramètre « EnablePublicCloudAudioVideoAccess » n’a pas de sélection correspondante dans le panneau de configuration de Skype entreprise Server


## <a name="to-create-a-new-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a>Pour créer une stratégie à l’aide de Windows PowerShell afin de prendre en charge l’accès des utilisateurs des domaines fédérés

1.  Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Démarrez Skype entreprise Server Management Shell : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Skype entreprise Server**, puis sur **Skype entreprise Server Management Shell**.

3.  Tapez ce qui suit dans Skype entreprise Server Management Shell :
    
    ```PowerShell
    New-CsExtenalAccessPolicy -Identity <name of site or user policy - you cannot create a new global policy using New-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAccess <$true, $false> -EnablePublicCloudAudioVideoAccess <$true, $false> -EnableOutsideAccess <$true, $false>
    ```
    
    Exemple de création d’une nouvelle stratégie de site :
    
    ```PowerShell
    New-CsExternalAccessPolicy -Identity site:Redmond -EnableFederationAccess $true -EnableXmppAccess $true -EnableOutsideAccess $true -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true
    ```


## <a name="to-delete-or-reset-a-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a>Pour supprimer ou réinitialiser une stratégie à l’aide de Windows PowerShell afin de prendre en charge l’accès des utilisateurs des domaines fédérés

1.  Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Tapez ce qui suit dans Skype entreprise Server Management Shell
    
    `Remove-CsExternalAccessPolicy -Identity <name of global, site or user policy>`
    
    Exemple de réinitialisation de la stratégie globale (la stratégie globale peut uniquement avoir son paramètre supprimé. La stratégie ne peut pas être supprimée) :
    
    `Remove-CsExternalAccessPolicy -Identity global`
    
    Pour supprimer une stratégie de site, tapez :
    
    `Remove-CsExternalAccessPolicy -Identity site:Redmond` 
    
    Supprime la stratégie de site Redmond. Pour supprimer une stratégie utilisateur nommée UserEAPPolicy, tapez :
    
    `Remove-CsExternalAccessPolicy -Identity UserEAPPolicy`


## <a name="see-also"></a>Voir aussi


[Activer ou désactiver la Fédération et la connectivité PIC](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md) 

[Affecter une stratégie d’accès des utilisateurs externes](assign-an-external-user-access-policy.md)

[Gérer les domaines fédérés SIP pour votre organisation](../sip-domains/manage-sip-federated-domains-for-your-organization.md)
 
[Gestion des fournisseurs fédérés SIP pour votre organisation](../sip-providers/manage-sip-federated-providers-for-your-organization.md)

[Set-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsExternalAccessPolicy)  
[New-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsExternalAccessPolicy)  
[Get-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsExternalAccessPolicy)  
[Remove-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy)  
[Grant-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy)  
  

