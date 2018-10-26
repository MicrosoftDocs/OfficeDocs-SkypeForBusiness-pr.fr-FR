---
title: "Lync Server 2013 : Conf. des stratégies de contrôle d’accès des ut. fédérés"
TOCTitle: Configuration des stratégies de contrôler d’accès des utilisateurs fédérés
ms:assetid: 5485e208-81e4-4e59-9aeb-1232c11dd8a2
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398359(v=OCS.15)
ms:contentKeyID: 49297221
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration des stratégies de contrôle d’accès des utilisateurs fédérés dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2014-02-05_

Quand vous configurez des stratégies de prise en charge des communications avec les partenaires fédérés, ces stratégies s’appliquent aux utilisateurs des domaines fédérés. Vous pouvez configurer une ou plusieurs stratégies d’accès des utilisateurs externes afin de vérifier si les utilisateurs des domaines fédérés peuvent collaborer avec vos utilisateurs Lync Server 2013. Pour contrôler l’accès des utilisateurs fédérés, vous pouvez configurer des stratégies au niveau global, du site et de l’utilisateur. Les paramètres de stratégie Lync Server qui sont appliqués au niveau d’une stratégie peuvent remplacer les paramètres appliqués à un autre niveau de stratégie. La politique de priorité de Lync Server est la suivante : la stratégie utilisateur (la plus influente) remplace une stratégie site, et une stratégie site remplace une stratégie globale (la moins influente). Cela signifie que plus le paramètre de stratégie est proche de l’objet que la stratégie affecte, plus elle a d’influence sur l’objet.

> [!NOTE]  
> Vous pouvez configurer des stratégies de contrôle d’accès des utilisateurs fédérés, même si vous n’avez pas activé la fédération pour votre organisation. Cependant, les stratégies que vous configurez s’appliquent uniquement si la fédération est activée pour votre organisation. Pour plus d’informations sur l’activation de la fédération, reportez-vous à <a href="lync-server-2013-enable-or-disable-remote-user-access.md">Activation ou désactivation de l’accès des utilisateurs distants dans Lync Server 2013</a> dans la documentation de déploiement ou des opérations. En outre, si vous spécifiez une stratégie utilisateur pour contrôler l’accès des utilisateurs fédérés, la stratégie s’applique uniquement aux utilisateurs activés pour Lync Server 2013 et configurés pour utiliser la stratégie.

## Pour configurer une stratégie permettant la prise en charge de l’accès des utilisateurs des domaines fédérés

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant des mêmes droits) ou affecté au rôle CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Accès des utilisateurs externes** , puis sur **Stratégie d’accès externe** .

4.  Dans la page **Stratégie d’accès externe** , effectuez l’une des opérations suivantes :
    
      - Pour configurer la stratégie globale permettant la prise en charge de l’accès des utilisateurs fédérés, cliquez sur la stratégie globale, sur **Modifier** , puis sur **Afficher les détails** .
    
      - Pour créer une nouvelle stratégie de site, cliquez sur **Nouveau** , puis sur **Stratégie du site** . Dans **Sélectionner un site** , cliquez sur le site approprié dans la liste, puis cliquez sur **OK** .
    
      - Pour créer une nouvelle stratégie utilisateur, cliquez sur **Nouveau** , puis sur **Stratégie de l’utilisateur** . Dans **Nouvelle stratégie d’accès externe** , créez dans le champ **Nom** un nom unique qui indique ce que couvre la stratégie utilisateur (par exemple, **EnableFederatedUsers** pour une stratégie utilisateur qui autorise les communications des utilisateurs de domaines fédérés).
    
      - Pour modifier une stratégie existante, cliquez sur la stratégie appropriée dans le tableau, cliquez sur **Modifier** , puis cliquez sur **Afficher les détails** .

5.  (Facultatif) Si vous souhaitez ajouter ou modifier une description, spécifiez les informations relatives à la stratégie dans **Description** .

6.  Effectuez l’une des actions suivantes :
    
      - Pour activer l’accès des utilisateurs fédérés pour la stratégie, activez la case à cocher **Autoriser les communications avec des utilisateurs fédérés** .
    
      - Pour désactiver l’accès des utilisateurs fédérés pour la stratégie, désactivez la case à cocher **Autoriser les communications avec des utilisateurs fédérés** .

7.  Cliquez sur **Valider** .

Pour activer l’accès des utilisateurs fédérés, vous devez aussi activer la prise en charge de la fédération dans votre organisation. Pour plus d’informations, reportez-vous à [Activation ou désactivation de la fédération et de la connectivité PIC dans Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md).

S’il s’agit d’une stratégie utilisateur, vous devez aussi appliquer la stratégie aux utilisateurs que vous souhaitez autoriser à collaborer avec les utilisateurs fédérés. Pour plus d’informations, reportez-vous à [Attribution d’une stratégie d’accès des utilisateurs externes à un utilisateur activé pour Lync dans Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md).

## Pour configurer une stratégie existante via Windows PowerShell afin de prendre en charge l’accès des utilisateurs des domaines fédérés

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant des mêmes droits) ou affecté au rôle CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur votre déploiement interne.

2.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

3.  Tapez ce qui suit dans Lync Server Management Shell :
    
        Set-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAcess <$true, $false> -EnablePublicCloudAudioVideoAcess <$true, $false> -EnableOutsideAcess <$true, $false>
    
    Exemple de commande qui définit la stratégie globale permettant d’activer l’accès des utilisateurs fédérés, d’activer l’accès au domaine XMPP, d’activer l’accès des utilisateurs distants, d’activer l’accès des fournisseurs publics et d’autoriser l’utilisation des fonctionnalités audio et vidéo aux fournisseurs publics qui les prennent en charge :
    
        Set-CsExternalAccessPolicy -Identity global -EnableFederationAccess $true -EnableXmppAccess $true -EnableOutsideAccess $true -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true
    
    > [!TIP]  
    > Le paramètre « EnablePublicCloudAudioVideoAccess » n’a pas de sélection correspondante dans le Panneau de configuration Lync Server

## Pour créer une stratégie via Windows PowerShell afin de prendre en charge l’accès des utilisateurs des domaines fédérés

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant des mêmes droits) ou affecté au rôle CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur votre déploiement interne.

2.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

3.  Tapez ce qui suit dans Lync Server Management Shell :
    
        New-CsExtenalAccessPolicy -Identity <name of site or user policy - you cannot create a new global policy using New-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAccess <$true, $false> -EnablePublicCloudAudioVideoAccess <$true, $false> -EnableOutsideAccess <$true, $false>
    
    Exemple de création d’une stratégie de site :
    
        New-CsExternalAccessPolicy -Identity site:Redmond -EnableFederationAccess $true -EnableXmppAccess $true -EnableOutsideAccess $true -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true

## Pour supprimer ou réinitialiser une stratégie via Windows PowerShell afin de prendre en charge l’accès des utilisateurs des domaines fédérés

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant des mêmes droits) ou affecté au rôle CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur votre déploiement interne.

2.  Tapez ce qui suit dans Lync Server Management Shell :
    
        Remove-CsExternalAccessPolicy -Identity <name of global, site or user policy> 
    
    Exemple de réinitialisation de la stratégie globale (seuls les paramètres de la stratégie globale peuvent être supprimés. La stratégie ne peut pas être supprimée) :
    
        Remove-CsExternalAccessPolicy -Identity global 
    
    Pour supprimer une stratégie de site, tapez :
    
        Remove-CsExternalAccessPolicy -Identity site:Redmond 
    
    Supprime la stratégie de site Redmond. Pour supprimer une stratégie utilisateur nommée UserEAPPolicy, tapez :
    
        Remove-CsExternalAccessPolicy -Identity UserEAPPolicy

## Voir aussi

#### Tâches

[Activation ou désactivation de la fédération et de la connectivité PIC dans Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)  
[Attribution d’une stratégie d’accès des utilisateurs externes à un utilisateur activé pour Lync dans Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)  

#### Autres ressources

[Gestion des domaines fédérés SIP pour l’organisation dans Lync Server 2013](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)  
[Gestion des fournisseurs fédérés SIP pour l’organisation dans Lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)  
[Set-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsExternalAccessPolicy)  
[New-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsExternalAccessPolicy)  
[Get-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsExternalAccessPolicy)  
[Remove-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy)  
[Grant-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsExternalAccessPolicy)

