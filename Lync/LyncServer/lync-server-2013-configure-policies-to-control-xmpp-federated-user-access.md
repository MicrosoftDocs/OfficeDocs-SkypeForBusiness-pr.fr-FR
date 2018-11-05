---
title: "Lync Server 2013 : Conf. des strat. de contrôle d’accès des ut. fédérés XMPP"
TOCTitle: Configuration des stratégies de contrôle d’accès des utilisateurs fédérés XMPP
ms:assetid: 0fe0ff75-e52a-4e3e-923a-64f6412ac4e4
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ552446(v=OCS.15)
ms:contentKeyID: 49296286
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration des stratégies de contrôle d’accès des utilisateurs fédérés XMPP dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-11-01_

Cette rubrique fait partie de la documentation préliminaire. Elle est susceptible d’être modifiée au cours des prochaines mises à jour. Les rubriques vides apparaissent sous la forme d’espaces réservés.

Lorsque vous configurez des stratégies visant à prendre en charge les partenaires fédérés du protocole XMPP, les stratégies s’appliquent aux utilisateurs des domaines fédérés XMPP, mais pas aux utilisateurs des fournisseurs de services de messagerie instantanée SIP (par exemple, Windows Live) ou de domaines fédérés SIP. Vous configurez un **partenaire fédéré XMPP** pour chaque domaine fédéré XMPP avec lequel vous souhaitez que vos utilisateurs puissent communiquer et entrer en contact. Les stratégies des partenaires fédérés XMPP ne sont disponibles que dans une seule étendue et même si elles ne sont pas définies comme une stratégie globale, elles se comportent comme une stratégie globale. Pour définir une stratégie globale, de site ou de l’utilisateur pour les partenaires de la fédération XMPP, configurez l’étendue de la stratégie en créant et en configurant d’abord la stratégie d’accès externe pour l’étendue dont vous avez besoin. Pour plus d’informations sur les types de stratégies que vous pouvez configurer pour l’accès externe et la fédération, reportez-vous à [Gestion de la fédération et de l’accès externe à Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md) dans la documentation des opérations.

> [!NOTE]  
> Toutes les stratégies de type <strong>Fédération et accès externe</strong> s’appliquent par le biais d’une mise en service intrabande. Les stratégies qui s’appliquent à l’utilisateur, qui appartiennent à un site ou qui sont d’étendue globale, sont communiquées au client lors de la connexion. Vous pouvez configurer les stratégies de manière à contrôler l’accès aux partenaires fédérés XMPP, même si vous n’avez pas activé de fédération XMPP pour votre organisation. Cependant, les stratégies que vous configurez ne prennent effet que lorsqu’une fédération de partenaires XMPP est déployée, activée et configurée pour votre organisation. Pour plus d’informations sur le déploiement et la configuration de la fédération de partenaires XMPP, reportez-vous à <a href="lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md">Configuration des fédérations SIP et XMPP et de la messagerie instantanée publique dans Lync Server 2013</a> dans la documentation de déploiement. En outre, si vous spécifiez une stratégie de l’utilisateur dans la stratégie d’accès externe pour contrôler les partenaires fédérés XMPP, la stratégie s’applique uniquement aux utilisateurs activés pour Lync Server 2013 et configurés pour utiliser la stratégie.

## Pour modifier une stratégie globale pour les partenaires fédérés XMPP

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant des mêmes droits) ou affecté au rôle CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Accès des utilisateurs externes** , puis sur **Stratégie d’accès externe** .

4.  Dans la page **Stratégie d’accès externe** , procédez comme suit pour la stratégie globale :

5.  Cliquez sur la stratégie globale, sur **Modifier** , puis sur Afficher les détails.

6.  Attribuer une description à la stratégie globale (facultatif).

7.  Sélectionnez **Autoriser les communications avec des utilisateurs fédérés** .

8.  Sélectionnez **Autoriser les communications avec des utilisateurs fédérés XMPP** .

9.  Cliquez sur **Valider** pour enregistrer les modifications apportées à la stratégie globale.

## Pour créer une stratégie de site ou de l’utilisateur pour les partenaires fédérés XMPP

1.  Cliquez sur **Nouveau** , puis sur **Stratégie de site** ou **Stratégie de l’utilisateur** . Dans **Sélectionner un site** , cliquez sur le site approprié dans la liste, puis sur **OK** .

2.  Attribuer une description à la stratégie de site (facultatif).

3.  Dans la stratégie de site ou de l’utilisateur, sélectionnez **Autoriser les communications avec des utilisateurs fédérés** .

4.  Sélectionnez **Autoriser les communications avec des utilisateurs fédérés XMPP** .

5.  Cliquez sur **Valider** pour enregistrer vos modifications du site ou de la stratégie de l’utilisateur.

## Pour modifier une stratégie existante pour les partenaires fédérés XMPP

1.  Pour modifier une stratégie existante, sélectionnez la stratégie appropriée dans la liste, cliquez sur **Modifier** , puis sur **Afficher les détails** .

2.  Modifier ou actualiser la description de la stratégie (facultatif).

3.  Sélectionnez ou désélectionnez **Autoriser les communications avec des utilisateurs fédérés** .

4.  Sélectionnez ou désélectionnez **Autoriser les communications avec des utilisateurs fédérés XMPP** .

5.  Cliquez sur **Valider** pour enregistrer les modifications apportées à la stratégie.

## Pour modifier une stratégie existante pour les partenaires fédérés XMPP via Windows PowerShell

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant des mêmes droits) ou affecté au rôle CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur votre déploiement interne.

2.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

3.  Tapez ce qui suit dans Lync Server Management Shell :
    
        Set-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false>
    
    Exemple de commande permettant de définir sur True (activé) la stratégie globale d’accès des utilisateurs fédérés et l’accès au domaine XMPP :
    
        Set-CsExternalAccessPolicy -Identity global -EnableFederationAccess $true -EnableXmppAccess $true

## Pour créer une stratégie utilisateur ou de site pour les partenaires fédérés XMPP via Windows PowerShell

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant des mêmes droits) ou affecté au rôle CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur votre déploiement interne.

2.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

3.  Tapez ce qui suit dans Lync Server Management Shell :
    
        New-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false>
    
    Exemple de commande permettant d’activer une stratégie de site concernant le site Redmond pour Accès utilisateur fédéré et d’activer l’accès au domaine XMPP :
    
        New-CsExternalAccessPolicy -Identity site:Redmond -EnableFederationAccess $true -EnableXmppAccess $true

## Pour supprimer une stratégie existante pour les partenaires fédérés XMPP via Windows PowerShell

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant des mêmes droits) ou affecté au rôle CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur votre déploiement interne.

2.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

3.  Tapez ce qui suit dans Lync Server Management Shell :
    
        Remove-CsExternalAccessPolicy -Identity <name of global, site or user policy>
    
    Exemple de commande permettant de supprimer une stratégie de l’utilisateur :
    
        Remove-CsExternalAccessPolicy -Identity EAPUserPolicySetXMPP

4.  Exemple de commande permettant de rétablir les paramètres par défaut de la stratégie globale :
    
        Remove-CsExternalAccessPolicy -Identity global

## Voir aussi

#### Tâches

[Attribution d’une stratégie d’accès des utilisateurs externes à un utilisateur activé pour Lync dans Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)  
[Activation ou désactivation de la fédération et de la connectivité PIC dans Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)  

#### Autres ressources

[Gestion des partenaires fédérés XMPP dans Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
[Set-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsExternalAccessPolicy)  
[New-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsExternalAccessPolicy)  
[Get-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsExternalAccessPolicy)  
[Remove-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy)  
[Grant-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsExternalAccessPolicy)

