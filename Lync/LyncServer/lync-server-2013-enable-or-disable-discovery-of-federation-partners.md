---
title: 'Lync Server 2013 : Activation ou désactivation de la découverte de partenaires de fédération'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enable or disable discovery of federation partners
ms:assetid: 91fd036b-b1af-47cf-b1cf-0aa0a783c2aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182550(v=OCS.15)
ms:contentKeyID: 48184857
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7e83f261fe6fa3ece259518b7730239adf20944c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831304"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-discovery-of-federation-partners-in-lync-server-2013"></a>Activation ou désactivation de la découverte de partenaires de fédération dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-02-23_

Au moment où vous avez déployé vos serveurs de périphérie et la Fédération activée pour votre organisation, vous devez indiquer si vous souhaitez prendre en charge la découverte automatique des domaines partenaires fédérés. Suivez la procédure décrite dans cette rubrique pour modifier cette configuration.

<div>


> [!NOTE]  
> La procédure suivante suppose que vous avez déjà activé la Fédération pour votre organisation. Pour plus d’informations sur l’activation de la Fédération, voir <A href="lync-server-2013-enable-or-disable-remote-user-access.md">activation ou désactivation de l’accès des utilisateurs distants dans Lync Server 2013</A> dans la documentation de déploiement ou la documentation des opérations.



</div>

<div>

## <a name="to-enable-or-disable-automatic-discovery-of-federated-domains-for-your-organization"></a>Pour activer ou désactiver la découverte automatique des domaines fédérés pour votre organisation

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **accès utilisateur externe**, puis sur **configuration de Microsoft Edge Access**.

4.  Dans la page **configuration de Microsoft Edge** , cliquez sur **Global**, sur **modifier**, puis sur **afficher les détails**.

5.  Dans **modification**de la configuration d’un point d’accès, sous **activer les communications avec des utilisateurs fédérés**, activez ou désactivez la case à cocher **activer la découverte** automatique du domaine pour activer ou désactiver la découverte automatique des domaines partenaires.

6.  Cliquez sur **Valider**.

Pour permettre aux utilisateurs fédérés de collaborer avec des utilisateurs dans le déploiement de Lync Server, vous devez également avoir configuré au moins une stratégie d’accès externe pour prendre en charge l’accès des utilisateurs fédérés. Pour plus d’informations, reportez-vous à [activation ou désactivation de la connectivité de Fédération et de messagerie instantanée publique dans Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) dans la documentation de déploiement ou la documentation des opérations. Pour plus d’informations sur le contrôle de l’accès pour des domaines fédérés spécifiques, voir [gérer des domaines fédérés SIP pour votre organisation dans Lync server 2013](lync-server-2013-manage-sip-federated-domains-for-your-organization.md), [gérer des fournisseurs fédérés SIP pour votre organisation dans Lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md) et [gérer XMPP partenaires fédérés dans Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md) dans la documentation opérations.

</div>

<div>

## <a name="enabling-or-disabling-discovery-of-federation-partners-by-using-windows-powershell-cmdlets"></a>Activation ou désactivation de la découverte de partenaires de Fédération à l’aide d’applets de cmdlet Windows PowerShell

La découverte des partenaires de Fédération peut être gérée à l’aide de Windows PowerShell et de l’applet de la cmdlet Set-CsAccessEdgeConfiguration. Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Lync Server, voir l’article de blog Lync Server Windows PowerShell «démarrage rapide: gestion de Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 à l’aide de Remote PowerShell».

<div>

## <a name="to-enable-discovery-of-federation-partners"></a>Pour activer la découverte des partenaires de Fédération

  - Pour activer la découverte des partenaires de Fédération, définissez la valeur de la propriété **EnablePartnerDiscovery** sur True ($true). Notez que vous devez activer le routage DNS SRV pour pouvoir modifier cette valeur de propriété.
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $True

</div>

<div>

## <a name="to-disable-discovery-of-federation-partners"></a>Pour désactiver la découverte des partenaires de Fédération

  - Pour désactiver la découverte des partenaires de Fédération, définissez la valeur de la propriété **EnablePartnerDiscovery** sur false ($false):
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $False

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

