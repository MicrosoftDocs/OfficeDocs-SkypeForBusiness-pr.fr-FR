---
title: Configuration des stratégies pour contrôler l’accès des utilisateurs fédérés
ms.reviewer: ''
ms:assetid: 5485e208-81e4-4e59-9aeb-1232c11dd8a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398359(v=OCS.15)
ms:contentKeyID: 48184180
mtps_version: v=OCS.15
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 'Lorsque vous configurez des stratégies pour prendre en charge les communications avec des partenaires fédérés, les stratégies s’appliquent aux utilisateurs de domaines fédérés. '
ms.openlocfilehash: 892ba1207f0c3426b3577364f19652514e8e2110
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60763752"
---
# <a name="configure-policies-to-control-federated-user-access-in-skype-for-business-server"></a>Configurer des stratégies pour contrôler l’accès des utilisateurs fédérés dans Skype Entreprise Server

Lorsque vous configurez des stratégies pour prendre en charge les communications avec des partenaires fédérés, les stratégies s’appliquent aux utilisateurs de domaines fédérés. Vous pouvez configurer une ou plusieurs stratégies d’accès des utilisateurs externes pour contrôler si les utilisateurs de domaines fédérés peuvent collaborer avec vos utilisateurs Skype Entreprise Server externes. Pour contrôler l’accès des utilisateurs fédérés, vous pouvez configurer des stratégies au niveau global, du site et de l’utilisateur. Skype Entreprise Server de stratégie appliquées à un niveau de stratégie peuvent remplacer les paramètres appliqués à un autre niveau de stratégie. La politique de priorité de Skype Entreprise Server est la suivante : la stratégie utilisateur (la plus influente) remplace une stratégie site, et une stratégie site remplace une stratégie globale (la moins influente). Cela signifie que plus le paramètre de stratégie est proche de l’objet que la stratégie affecte, plus elle a d’influence sur l’objet.


> [!NOTE]  
> Vous pouvez configurer des stratégies pour contrôler l’accès des utilisateurs fédérés, même si vous n’avez pas activé la fédération pour votre organisation. Toutefois, les stratégies que vous configurez s’appliquent uniquement si la fédération est activée pour votre organisation. Pour plus d’informations sur l’activation de la fédération, voir [Activer ou désactiver l’accès des utilisateurs distants.](../access-edge/enable-or-disable-remote-user-access.md)  En outre, si vous spécifiez une stratégie utilisateur pour contrôler l’accès des utilisateurs fédérés, la stratégie s’applique uniquement aux utilisateurs activés pour Skype Entreprise Server et configurés pour utiliser la stratégie.


## <a name="to-configure-a-policy-to-support-access-by-users-of-federated-domains"></a>Pour configurer une stratégie pour prendre en charge l’accès par les utilisateurs de domaines fédérés

1.  Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir Skype Entreprise Server panneau de bord.

3.  Dans la barre de navigation de gauche, cliquez sur **Accès des utilisateurs externes**, puis sur **Stratégie d’accès externe**.

4.  Dans la page **Stratégie d’accès externe**, effectuez l’une des opérations suivantes :
    
      - Pour configurer la stratégie globale pour prendre en charge l’accès des **utilisateurs fédérés,** cliquez sur la stratégie globale, cliquez sur **Modifier,** puis cliquez sur Afficher les détails.
    
      - Pour créer une nouvelle stratégie de site, cliquez sur **Nouveau**, puis sur **Stratégie du site**. Dans **Sélectionner un site**, cliquez sur le site approprié dans la liste, puis cliquez sur **OK**.
    
      - Pour créer une nouvelle stratégie utilisateur, cliquez sur **Nouveau**, puis sur **Stratégie de l’utilisateur**. Dans **nouvelle** stratégie d’accès externe,  créez un nom unique dans le champ Nom qui indique ce que couvre la stratégie utilisateur (par exemple, **EnableFederatedUsers** pour une stratégie utilisateur qui active les communications pour les utilisateurs de domaine fédérés).
    
      - Pour modifier une stratégie existante, cliquez sur la stratégie appropriée dans le tableau, cliquez sur **Modifier**, puis cliquez sur **Afficher les détails**.

5.  (Facultatif) Si vous souhaitez ajouter ou modifier une description, spécifiez les informations relatives à la stratégie dans **Description**.

6.  Effectuez l’une des opérations suivantes :
    
      - Pour activer l’accès des utilisateurs fédérés à la stratégie, activez la case à cocher Activer les communications avec les **utilisateurs fédérés.**
    
      - Pour désactiver l’accès des utilisateurs fédérés à la stratégie, désactivez la case à cocher Activer les communications avec les utilisateurs **fédérés.**

7.  Cliquez sur **Valider**.

Pour activer l’accès des utilisateurs fédérés, vous devez également activer la prise en charge de la fédération dans votre organisation. Pour plus d’informations, [voir Activer ou désactiver la fédération et la connectivité DE messagerie instantanée publique.](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md)

S’il s’agit d’une stratégie utilisateur, vous devez également appliquer la stratégie aux utilisateurs que vous souhaitez pouvoir collaborer avec des utilisateurs fédérés. Pour plus d’informations, voir [Affecter une stratégie d’accès des utilisateurs externes.](assign-an-external-user-access-policy.md)

## <a name="to-configure-an-existing-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a>Pour configurer une stratégie existante à l’aide de Windows PowerShell pour prendre en charge l’accès par les utilisateurs de domaines fédérés

1.  Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Démarrez la Skype busines Server Management Shell : cliquez sur **Démarrer,** sur Tous les **programmes,** sur **Skype Entreprise Server,** puis sur Skype Entreprise Server **Management Shell.**

3.  Tapez ce qui suit dans Skype Entreprise Server Management Shell :
    
    ```PowerShell
    Set-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAcess <$true, $false> -EnablePublicCloudAudioVideoAcess <$true, $false> -EnableOutsideAcess <$true, $false>
    ```
       

    > [!TIP]  
    > Le paramètre « EnablePublicCloudAudioVideoAccess » n’a pas de sélection correspondante dans le Panneau de Skype Entreprise Server de contrôle


## <a name="to-create-a-new-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a>Pour créer une stratégie à l’aide Windows PowerShell pour prendre en charge l’accès par les utilisateurs de domaines fédérés

1.  Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Démarrez l’Skype Entreprise Server Management Shell : cliquez sur Démarrer, sur Tous les **programmes,** sur **Microsoft Skype Entreprise Server,** puis sur Skype Entreprise Server **Management Shell.**

3.  Tapez ce qui suit dans Skype Entreprise Server Management Shell :
    
    ```PowerShell
    New-CsExtenalAccessPolicy -Identity <name of site or user policy - you cannot create a new global policy using New-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAccess <$true, $false> -EnablePublicCloudAudioVideoAccess <$true, $false> -EnableOutsideAccess <$true, $false>
    ```
    
    Exemple de création d’une stratégie de site :
    
    ```PowerShell
    New-CsExternalAccessPolicy -Identity site:Redmond -EnableFederationAccess $true -EnableXmppAccess $true -EnableOutsideAccess $true -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true
    ```


## <a name="to-delete-or-reset-a-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a>Pour supprimer ou réinitialiser une stratégie à l’Windows PowerShell pour prendre en charge l’accès par les utilisateurs de domaines fédérés

1.  Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Tapez ce qui suit dans Skype Entreprise Server Management Shell
    
    `Remove-CsExternalAccessPolicy -Identity <name of global, site or user policy>`
    
    Exemple de réinitialisation de la stratégie globale (seul son paramètre peut être supprimé. Impossible de supprimer la stratégie :
    
    `Remove-CsExternalAccessPolicy -Identity global`
    
    Pour supprimer une stratégie de site, tapez :
    
    `Remove-CsExternalAccessPolicy -Identity site:Redmond` 
    
    Supprime la stratégie de site Redmond. Pour supprimer une stratégie utilisateur nommée UserEAPPolicy, tapez :
    
    `Remove-CsExternalAccessPolicy -Identity UserEAPPolicy`


## <a name="see-also"></a>Voir aussi


[Activation ou désactivation de la fédération et de la connectivité PIC](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md) 

[Attribution d’une stratégie d’accès des utilisateurs externes](assign-an-external-user-access-policy.md)

[Gestion des domaines fédérés SIP pour l’organisation](../sip-domains/manage-sip-federated-domains-for-your-organization.md)
 
[Gestion des fournisseurs fédérés SIP pour l’organisation](../sip-providers/manage-sip-federated-providers-for-your-organization.md)

[Set-CsExternalAccessPolicy](/powershell/module/skype/Set-CsExternalAccessPolicy)  
[New-CsExternalAccessPolicy](/powershell/module/skype/New-CsExternalAccessPolicy)  
[Get-CsExternalAccessPolicy](/powershell/module/skype/Get-CsExternalAccessPolicy)  
[Remove-CsExternalAccessPolicy](/powershell/module/skype/Remove-CsExternalAccessPolicy)  
[Grant-CsExternalAccessPolicy](/powershell/module/skype/Grant-CsExternalAccessPolicy)  
