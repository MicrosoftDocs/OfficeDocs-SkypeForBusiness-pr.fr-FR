---
title: 'Lync Server 2013 : configuration des stratégies de contrôle de l’accès des utilisateurs fédérés XMPP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure policies to control XMPP federated user access
ms:assetid: 0fe0ff75-e52a-4e3e-923a-64f6412ac4e4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552446(v=OCS.15)
ms:contentKeyID: 48679557
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b7cc0eec0dc1371e27834dda69b25a32b9346ab5
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48535221"
---
# <a name="configure-policies-to-control-xmpp-federated-user-access-in-lync-server-2013"></a>Configurer des stratégies pour contrôler l’accès des utilisateurs fédérés XMPP dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-11-01_

Cette documentation est préliminaire et sujette à modification. Des rubriques vides sont incluses comme espaces réservés.

Lorsque vous configurez des stratégies visant à prendre en charge les partenaires fédérés du protocole XMPP, les stratégies s’appliquent aux utilisateurs des domaines fédérés XMPP, mais pas aux utilisateurs des fournisseurs de services de messagerie instantanée SIP (par exemple Windows Live) ou de domaines fédérés SIP. Vous configurez un **partenaire fédéré XMPP** pour chaque domaine fédéré XMPP avec lequel vous souhaitez que vos utilisateurs puissent communiquer et entrer en contact. Les stratégies des partenaires fédérés XMPP ne sont disponibles que dans une seule étendue, et même si elles ne sont pas définies comme une stratégie globale, elles se comportent comme une stratégie globale. Pour définir une stratégie globale, de site ou de l’utilisateur pour les partenaires de la fédération XMPP, configurez l’étendue de la stratégie en créant et en configurant d’abord la stratégie d’accès externe pour l’étendue dont vous avez besoin. Pour plus d’informations sur les types de stratégies que vous pouvez configurer pour l’accès externe et la Fédération, voir gestion de la [Fédération et de l’accès externe à Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md) dans la documentation des opérations.

<div>


> [!NOTE]  
> Toutes les stratégies de type  <STRONG>Fédération et accès externe</STRONG> s’appliquent par le biais d’une mise en service intrabande. Les stratégies qui s’appliquent à l’utilisateur, qui appartiennent à un site ou qui sont d’étendue globale, sont communiquées au client lors de la connexion. Vous pouvez configurer les stratégies de manière à contrôler l’accès aux partenaires fédérés XMPP, même si vous n’avez pas activé de fédération XMPP pour votre organisation. Toutefois, les stratégies que vous configurez ne prennent effet que lorsqu’une fédération de partenaires XMPP est déployée, activée et configurée pour votre organisation. Pour plus d’informations sur le déploiement et la configuration de la Fédération de partenaires XMPP, voir Configuration de la Fédération <A href="lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md">SIP, la Fédération XMPP et la messagerie instantanée publique dans Lync Server 2013</A> dans la documentation de déploiement. En outre, si vous spécifiez une stratégie utilisateur dans la stratégie d’accès externe pour contrôler les partenaires fédérés XMPP, la stratégie s’applique uniquement aux utilisateurs qui sont activés pour Lync Server 2013 et qui sont configurés pour utiliser la stratégie.



</div>

<div>

## <a name="to-edit-a-global-policy-for-xmpp-federated-partners"></a>Pour modifier une stratégie globale pour les partenaires fédérés XMPP

1.  Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Accès des utilisateurs externes**, puis sur **Stratégie d’accès externe**.

4.  Dans la page **Stratégie d’accès externe**, procédez comme suit pour la stratégie globale :

5.  Cliquez sur la stratégie globale, sur **Modifier**, puis sur Afficher les détails.

6.  Attribuer une description à la stratégie globale (facultatif).

7.  Sélectionnez **Autoriser les communications avec des utilisateurs fédérés**.

8.  Sélectionnez **Autoriser les communications avec des utilisateurs fédérés XMPP**.

9.  Cliquez sur **Valider** pour enregistrer les modifications apportées à la stratégie globale.

</div>

<div>

## <a name="to-create-a-site-or-user-policy-for-xmpp-federated-partners"></a>Pour créer une stratégie de site ou de l’utilisateur pour les partenaires fédérés XMPP

1.  Cliquez sur **Nouveau**, puis sur **Stratégie de site** ou **Stratégie de l’utilisateur**. Dans **Sélectionner un site**, cliquez sur le site approprié dans la liste, puis sur **OK**.

2.  Attribuer une description à la stratégie de site (facultatif).

3.  Dans la stratégie de site ou de l’utilisateur, sélectionnez **Autoriser les communications avec des utilisateurs fédérés**.

4.  Sélectionnez **Autoriser les communications avec des utilisateurs fédérés XMPP**.

5.  Cliquez sur **Valider** pour enregistrer les modifications apportées à la stratégie de site ou de l’utilisateur.

</div>

<div>

## <a name="to-edit-an-existing-policy-for-xmpp-federated-partners"></a>Pour modifier une stratégie existante pour les partenaires fédérés XMPP

1.  Pour modifier une stratégie existante, sélectionnez la stratégie appropriée dans la liste, cliquez sur **Modifier**, puis sur **Afficher les détails**.

2.  Modifier ou actualiser la description de la stratégie (facultatif).

3.  Sélectionnez ou désélectionnez **Autoriser les communications avec des utilisateurs fédérés**.

4.  Sélectionnez ou désélectionnez **Autoriser les communications avec des utilisateurs fédérés XMPP**.

5.  Cliquez sur **Valider** pour enregistrer les modifications apportées à la stratégie.

</div>

<div>

## <a name="to-edit-an-existing-policy-for-xmpp-federated-partners-by-using-windows-powershell"></a>Pour modifier une stratégie existante pour les partenaires fédérés XMPP à l’aide de Windows PowerShell

1.  Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Lync Server Management Shell**.

3.  Tapez ce qui suit dans Lync Server Management Shell :
    
        Set-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false>
    
    Exemple de commande qui définit la stratégie globale pour l’accès des utilisateurs fédérés à true (activé) et à l’accès au domaine XMPP sur true (activé) :
    
        Set-CsExternalAccessPolicy -Identity global -EnableFederationAccess $true -EnableXmppAccess $true

</div>

<div>

## <a name="to-create-a-site-or-user-policy-for-xmpp-federated-partners-using-windows-powershell"></a>Pour créer une stratégie de site ou d’utilisateur pour les partenaires fédérés XMPP à l’aide de Windows PowerShell

1.  Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Lync Server Management Shell**.

3.  Tapez ce qui suit dans Lync Server Management Shell :
    
        New-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false>
    
    Exemple de commande permettant d’activer une stratégie de site concernant le site Redmond pour Accès utilisateur fédéré et d’activer l’accès au domaine XMPP :
    
        New-CsExternalAccessPolicy -Identity site:Redmond -EnableFederationAccess $true -EnableXmppAccess $true

</div>

<div>

## <a name="to-delete-an-existing-policy-for-xmpp-federated-partners-by-using-windows-powershell"></a>Pour supprimer une stratégie existante pour les partenaires fédérés XMPP à l’aide de Windows PowerShell

1.  Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Lync Server Management Shell**.

3.  Tapez ce qui suit dans Lync Server Management Shell :
    
        Remove-CsExternalAccessPolicy -Identity <name of global, site or user policy>
    
    Exemple de commande permettant de supprimer une stratégie de l’utilisateur :
    
        Remove-CsExternalAccessPolicy -Identity EAPUserPolicySetXMPP

4.  Exemple de commande permettant de rétablir les paramètres par défaut de la stratégie globale :
    
        Remove-CsExternalAccessPolicy -Identity global

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Affectation d’une stratégie d’accès des utilisateurs externes à un utilisateur activé pour Lync dans Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)  
[Activation ou désactivation de la Fédération et de la connectivité PIC dans Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)  


[Gérer les partenaires fédérés XMPP dans Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
[Set-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsExternalAccessPolicy)  
[New-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsExternalAccessPolicy)  
[Get-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsExternalAccessPolicy)  
[Remove-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy)  
[Grant-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

