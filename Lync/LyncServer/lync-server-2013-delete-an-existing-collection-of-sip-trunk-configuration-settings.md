---
title: Supprimer une collection existante de paramètres de configuration de jonction SIP
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an existing collection of SIP trunk configuration settings
ms:assetid: 3b25f14d-884b-42dd-a866-460d276d3e43
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688024(v=OCS.15)
ms:contentKeyID: 49733614
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 657efcf53b48c0aab2df661ddf142587e02e235e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134650"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-collection-of-sip-trunk-configuration-settings-in-lync-server-2013"></a>Supprimer une collection existante de paramètres de configuration de jonction SIP dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-22_

Les paramètres de configuration de jonction SIP définissent la relation et les capacités entre un serveur de médiation et la passerelle du réseau téléphonique commuté (PSTN), un autocommutateur privé IP (PBX) ou un contrôleur SBC du côté fournisseur de services. Ces paramètres permettent de spécifier ce qui suit :

  - L’activation ou non du contournement de média sur les jonctions.

  - Les conditions d’envoi des paquets RTCP (Real-time Transport Control Protocol).

  - L’application ou non du chiffrement SRTP (Secure Real-Time Protocol) sur chaque jonction.

Lorsque vous installez Microsoft Lync Server 2013, une collection globale de paramètres de configuration de jonction SIP (Session Initiation Protocol) est créée. Cette collection globale de paramètres ne peut pas être supprimée. Toutefois, vous pouvez utiliser le panneau de configuration Lync Server ou l’applet de commande [Remove-applet cstrunkconfiguration](https://technet.microsoft.com/library/Gg425943(v=OCS.15)) pour « réinitialiser » les propriétés de la collection globale à leurs valeurs par défaut. Par exemple, si vous avez défini la propriété Enable3pccRefer sur true, lorsque vous réinitialisez la collection globale, la propriété Enable3pccRefer reprend sa valeur par défaut false.

Les administrateurs peuvent aussi créer des paramètres de configuration de jonction personnalisés étendus à un site ou un service (pour une passerelle PSTN individuelle) ; ces paramètres personnalisés peuvent être supprimés. Au moment de supprimer ces paramètres personnalisés, tenez compte des points suivants :

  - Si vous supprimez des paramètres étendus à un service, la jonction SIP gérée par ces paramètres est gérée par les paramètres appliqués à son site, le cas échéant. En l’absence de paramètres de site, la jonction est gérée par la collection globale de paramètres de configuration de jonction.

  - Si vous supprimez des paramètres étendus à un site, les jonctions SIP gérées par ces paramètres sont alors gérées par la collection globale de paramètres de configuration de jonction.

<div>

## <a name="to-remove-trunk-configuration-settings-with-lync-server-control-panel"></a>Pour supprimer les paramètres de configuration de jonction avec le panneau de configuration Lync Server

1.  Dans le panneau de configuration Lync Server, cliquez sur **routage des communications vocales** , puis sur Configuration de la **jonction**.

2.  Sous l’onglet **Configuration de la jonction**, sélectionnez la collection de paramètres de configuration de jonction SIP à supprimer, cliquez sur **Modifier**, puis sur **Supprimer**. Pour supprimer plusieurs collections en une seule opération, cliquez sur la première collection à supprimer, maintenez la touche Ctrl enfoncée, puis cliquez sur les autres collections à supprimer.

3.  La propriété **État** de la collection est mise à jour et présente la valeur **Non validé**. Pour valider les modifications et supprimer la collection, cliquez sur **Valider**, puis sur **Valider tout**.

4.  Dans la boîte de dialogue **Paramètres de configuration de la voix non validés**, cliquez sur **OK**.

5.  Dans la boîte de dialogue **Panneau de configuration Microsoft Lync Server 2013**, cliquez sur **OK**.

6.  Si vous changez d’avis et décidez de ne pas supprimer la collection, cliquez sur **Valider**, puis sur **Annuler toutes les modifications non validées**. Quand la boîte de dialogue **Panneau de configuration Microsoft Lync Server 2013** s’affiche, cliquez sur **OK**.

</div>

<div>

## <a name="removing-trunk-configuration-settings-by-using-windows-powershell-cmdlets"></a>Suppression des paramètres de configuration de jonction à l’aide des applets de commande Windows PowerShell

Vous pouvez supprimer les paramètres de configuration de jonction à l’aide de Windows PowerShell et de l’applet de commande **Remove-applet cstrunkconfiguration** . Vous pouvez exécuter cette cmdlet à partir de Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 Using Remote PowerShell » (en anglais) à l’adresse.

<div>

## <a name="to-remove-a-specified-collection-of-settings"></a>Pour supprimer une collection de paramètres spécifiée

  - La commande suivante supprime les paramètres de configuration de jonction appliqués au site Redmond :
    
        Remove-CsTrunkConfiguration -Identity site:Redmond

</div>

<div>

## <a name="to-remove-all-the-collections-applied-to-the-site-scope"></a>Pour supprimer toutes les collections appliquées à l’étendue site

  - Cette commande supprime tous les paramètres de configuration de jonction appliqués dans l’étendue du site :
    
        Get-CsTrunkConfiguration -Filter "service:*" | Remove-CsTrunkConfiguration

</div>

<div>

## <a name="to-remove-all-the-collections-where-media-bypass-is-enabled"></a>Pour supprimer toutes les collections pour lesquelles la déviation du trafic multimédia est activée

  - La commande suivante supprime tous les paramètres de configuration de jonction dès lors que le contournement de média est activé :
    
        Get-CsTrunkConfiguration | Where-Object {$_.EnableBypass -eq $True} | Remove-CsTrunkConfiguration

</div>

Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de commande [Remove-applet cstrunkconfiguration](https://technet.microsoft.com/library/Gg425943(v=OCS.15)) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

