---
title: 'Lync Server 2013 : Configuration des stratégies de contrôle d’accès des utilisateurs fédérés XMPP'
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
ms.openlocfilehash: cc79a915d0735f87c0852dff0ba4228b1e391fd8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730027"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-policies-to-control-xmpp-federated-user-access-in-lync-server-2013"></a>Configuration des stratégies de contrôle d’accès des utilisateurs fédérés XMPP dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-11-01_

Il s’agit d’une documentation préliminaire susceptible d’être modifiée. Des rubriques vides sont incluses sous forme d’espaces réservés.

Lorsque vous configurez des stratégies pour la prise en charge des partenaires fédérés du protocole de messagerie extensible et de présence, les stratégies s’appliquent aux utilisateurs des domaines fédérés de XMPP, mais pas aux utilisateurs de services de messagerie instantanée SIP (Session Initiation Protocol). (par exemple, Windows Live) ou domaines fédérés SIP. Vous configurez un **partenaire fédéré de XMPP** pour chaque domaine fédéré XMPP que vous voulez autoriser vos utilisateurs à ajouter des contacts et à communiquer avec eux. Les stratégies des partenaires fédérés de XMPP ne sont disponibles qu’en une seule étendue, même si elle n’est pas définie en tant que stratégie globale, fait office de stratégie globale. Pour définir une stratégie globale de site ou d’utilisateur pour les partenaires de Fédération XMPP, vous devez configurer la portée de la stratégie en commençant par la création et la configuration de la stratégie d’accès externe dont vous avez besoin. Pour plus d’informations sur les types de stratégies que vous pouvez configurer pour l’accès externe et la Fédération, voir gestion de la [Fédération et accès externe à Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md) dans la documentation sur les opérations.

<div>


> [!NOTE]  
> Toutes les stratégies de <STRONG>Fédération et d’accès externe</STRONG> sont appliquées via la mise en service intrabande. Les politiques qui s’appliquent à l’utilisateur, qui font partie d’un site ou qui sont globales dans l’étendue, sont communiquées au client au moment de la connexion. Vous pouvez configurer des stratégies pour contrôler l’accès par le partenaire fédéré de XMPP, même si vous n’avez pas activé la Fédération XMPP pour votre organisation. Toutefois, les stratégies que vous configurez prennent effet uniquement lorsque vous avez déployé la Fédération de partenaires XMPP, activée et configurée pour votre organisation. Pour plus d’informations sur le déploiement et la configuration de la Fédération de partenaire XMPP, voir Configuration de la Fédération <A href="lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md">SIP, de la Fédération et de la messagerie instantanée publique dans Lync Server 2013</A> dans la documentation de déploiement. Par ailleurs, si vous spécifiez une stratégie d’utilisateur dans une stratégie d’accès externe pour contrôler les partenaires fédérés de XMPP, la stratégie s’applique uniquement aux utilisateurs qui sont activés pour Lync Server 2013 et qui sont configurés pour utiliser cette stratégie.



</div>

<div>

## <a name="to-edit-a-global-policy-for-xmpp-federated-partners"></a>Pour modifier une stratégie globale pour les partenaires fédérés de XMPP

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **accès utilisateur externe**, puis sur **stratégie d’accès externe**.

4.  Dans la page de **stratégie d’accès externe** , procédez comme suit pour la stratégie globale :

5.  Cliquez sur la stratégie globale, sur **modifier**, puis sur Afficher les détails.

6.  Entrez une description pour la politique globale (facultatif).

7.  Sélectionnez **activer les communications avec les utilisateurs fédérés**.

8.  Sélectionnez **activer les communications avec les utilisateurs fédérés de XMPP**.

9.  Cliquez sur **valider** pour enregistrer les modifications apportées à la stratégie globale.

</div>

<div>

## <a name="to-create-a-site-or-user-policy-for-xmpp-federated-partners"></a>Pour créer une stratégie de site ou d’utilisateur pour les partenaires fédérés de XMPP

1.  Cliquez sur **nouveau**, puis sur **politique du site** ou stratégie de l' **utilisateur**. Dans **Sélectionner un site**, cliquez sur le site approprié dans la liste, puis cliquez sur **OK**.

2.  Entrez une description pour la stratégie de site (facultatif).

3.  Dans la stratégie de site ou d’utilisateur, sélectionnez **activer les communications avec les utilisateurs fédérés**.

4.  Sélectionnez **activer les communications avec les utilisateurs fédérés de XMPP**.

5.  Cliquez sur **valider** pour enregistrer les modifications apportées à la stratégie de site ou d’utilisateur.

</div>

<div>

## <a name="to-edit-an-existing-policy-for-xmpp-federated-partners"></a>Pour modifier une stratégie existante pour les partenaires fédérés de XMPP

1.  Pour modifier une stratégie existante, sélectionnez la stratégie appropriée dans la liste, cliquez sur **modifier**, puis sur **afficher les détails**.

2.  Modifiez ou mettez à jour la description de la stratégie (facultatif).

3.  Activez ou désactivez l’option **activer les communications avec les utilisateurs fédérés**.

4.  Activez ou désactivez l’option **activer les communications avec les utilisateurs fédérés de XMPP**.

5.  Cliquez sur **valider** pour enregistrer les modifications apportées à la stratégie.

</div>

<div>

## <a name="to-edit-an-existing-policy-for-xmpp-federated-partners-by-using-windows-powershell"></a>Pour modifier une stratégie existante pour les partenaires fédérés de XMPP à l’aide de Windows PowerShell

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.

2.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

3.  Dans Lync Server Management Shell, tapez ce qui suit :
    
        Set-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false>
    
    Un exemple de commande qui définit la stratégie globale pour l’accès utilisateur fédéré à vrai (activé) et à l’accès au domaine XMPP sur vrai (activé) :
    
        Set-CsExternalAccessPolicy -Identity global -EnableFederationAccess $true -EnableXmppAccess $true

</div>

<div>

## <a name="to-create-a-site-or-user-policy-for-xmpp-federated-partners-using-windows-powershell"></a>Pour créer une stratégie de site ou d’utilisateur pour les partenaires fédérés de XMPP utilisant Windows PowerShell

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.

2.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

3.  Dans Lync Server Management Shell, tapez ce qui suit :
    
        New-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false>
    
    Commande d’exemple qui définira une stratégie de site pour le site de Redmond pour l’accès des utilisateurs fédérés à l’accès au domaine activé et XMPP sur activé :
    
        New-CsExternalAccessPolicy -Identity site:Redmond -EnableFederationAccess $true -EnableXmppAccess $true

</div>

<div>

## <a name="to-delete-an-existing-policy-for-xmpp-federated-partners-by-using-windows-powershell"></a>Pour supprimer une stratégie existante pour les partenaires fédérés de XMPP à l’aide de Windows PowerShell

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.

2.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

3.  Dans Lync Server Management Shell, tapez ce qui suit :
    
        Remove-CsExternalAccessPolicy -Identity <name of global, site or user policy>
    
    Voici un exemple de commande qui supprimera une stratégie de l’utilisateur :
    
        Remove-CsExternalAccessPolicy -Identity EAPUserPolicySetXMPP

4.  Par exemple, la commande suivante réinitialise la stratégie globale sur les valeurs par défaut :
    
        Remove-CsExternalAccessPolicy -Identity global

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Attribution d’une stratégie d’accès des utilisateurs externes à un utilisateur activé pour Lync dans Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)  
[Activation ou désactivation de la fédération et de la connectivité PIC dans Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)  


[Gestion des partenaires fédérés XMPP dans Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
[Set-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsExternalAccessPolicy)  
[Nouveau-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsExternalAccessPolicy)  
[Get-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsExternalAccessPolicy)  
[Remove-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy)  
[Grant-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

