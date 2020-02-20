---
title: 'Lync Server 2013 : applets de commande de Fédération et d’accès externe'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Federation and external access cmdlets
ms:assetid: 4a384a57-257f-47a6-98d9-54cea2c647b7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415651(v=OCS.15)
ms:contentKeyID: 48184018
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a125329cd7c76d5f5f8e40c4dae1dd78dcabc3dd
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153706"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="federation-and-external-access-cmdlets-in-lync-server-2013"></a>Cmdlets de Fédération et d’accès externe dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-06-26_

La Fédération et l’accès externe offrent deux fonctionnalités importantes : la Fédération permet aux utilisateurs de communiquer avec des personnes extérieures à votre organisation, tandis que l’accès externe permet aux utilisateurs de se connecter à Microsoft Lync Server 2013 depuis l’extérieur du réseau interne. Les applets de commande disponibles pour la gestion de la Fédération et de l’accès externe dans Lync Server 2013 vous permettent de déterminer les personnes que vos utilisateurs peuvent (et ne peuvent pas) communiquer avec, et de déterminer si ces utilisateurs peuvent se connecter à Lync Server sans avoir à se connecter au serveur interne. réseau.

<div>

## <a name="federation-and-external-access-cmdlets"></a>Applets de commande de fédération et d’accès externe

La plupart des tâches de gestion qui s’appliquent à la Fédération et l’accès externe peuvent être effectuées à partir du panneau de configuration Lync Server. Ces mêmes tâches peuvent être exécutées à l’aide d’applets de commande de Lync Server Management Shell ou à partir d’un script ; l’utilisation d’un script vous permet d’automatiser certaines tâches. Vous trouverez ci-dessous une liste des applets de commande qui sont directement liées à la gestion de la fédération et de l’accès externe :

  - <span></span>  
    [Get-CsAllowedDomain](https://technet.microsoft.com/library/Gg398164(v=OCS.15))

  - <span></span>  
    [New-CsAllowedDomain](https://technet.microsoft.com/library/Gg398628(v=OCS.15))

  - <span></span>  
    [Remove-CsAllowedDomain](https://technet.microsoft.com/library/Gg398913(v=OCS.15))

  - <span></span>  
    [Set-CsAllowedDomain](https://technet.microsoft.com/library/Gg398931(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-applet csblockeddomain](https://technet.microsoft.com/library/Gg398424(v=OCS.15))

  - <span></span>  
    [New-applet csblockeddomain](https://technet.microsoft.com/library/Gg398822(v=OCS.15))

  - <span></span>  
    [Remove-applet csblockeddomain](https://technet.microsoft.com/library/Gg425832(v=OCS.15))

  - <span></span>  
    [Set-applet csblockeddomain](https://technet.microsoft.com/library/Gg398090(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsExternalAccessPolicy](https://technet.microsoft.com/library/Gg425805(v=OCS.15))

  - <span></span>  
    [Grant-CsExternalAccessPolicy](https://technet.microsoft.com/library/Gg425942(v=OCS.15))

  - <span></span>  
    [New-CsExternalAccessPolicy](https://technet.microsoft.com/library/Gg398441(v=OCS.15))

  - <span></span>  
    [Remove-CsExternalAccessPolicy](https://technet.microsoft.com/library/Gg399057(v=OCS.15))

  - <span></span>  
    [Set-CsExternalAccessPolicy](https://technet.microsoft.com/library/Gg398916(v=OCS.15))

<!-- end list -->

  - [Get-applet csfipsconfiguration](https://technet.microsoft.com/library/JJ204904(v=OCS.15))

  - [New-applet csfipsconfiguration](https://technet.microsoft.com/library/JJ205114(v=OCS.15))

  - [Remove-applet csfipsconfiguration](https://technet.microsoft.com/library/JJ205201(v=OCS.15))

  - [Set-applet csfipsconfiguration](https://technet.microsoft.com/library/JJ205084(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Disable-CsHostingProvider](https://technet.microsoft.com/library/Gg398481(v=OCS.15))

  - <span></span>  
    [Enable-CsHostingProvider](https://technet.microsoft.com/library/Gg398166(v=OCS.15))

  - <span></span>  
    [Get-CsHostingProvider](https://technet.microsoft.com/library/Gg413078(v=OCS.15))

  - <span></span>  
    [New-CsHostingProvider](https://technet.microsoft.com/library/Gg398490(v=OCS.15))

  - <span></span>  
    [Remove-CsHostingProvider](https://technet.microsoft.com/library/Gg425809(v=OCS.15))

  - <span></span>  
    [Set-CsHostingProvider](https://technet.microsoft.com/library/Gg398532(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Disable-applet cspublicprovider](https://technet.microsoft.com/library/Gg398984(v=OCS.15))

  - <span></span>  
    [Enable-applet cspublicprovider](https://technet.microsoft.com/library/Gg398780(v=OCS.15))

  - <span></span>  
    [Get-applet cspublicprovider](https://technet.microsoft.com/library/Gg412945(v=OCS.15))

  - <span></span>  
    [New-applet cspublicprovider](https://technet.microsoft.com/library/Gg398161(v=OCS.15))

  - <span></span>  
    [Remove-applet cspublicprovider](https://technet.microsoft.com/library/Gg412906(v=OCS.15))

  - <span></span>  
    [Set-applet cspublicprovider](https://technet.microsoft.com/library/Gg413087(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Test-CsFederatedPartner](https://technet.microsoft.com/library/Gg398281(v=OCS.15))

<!-- end list -->

  - [Get-CsXmppAllowedPartner](https://technet.microsoft.com/library/JJ204981(v=OCS.15))

  - [New-CsXmppAllowedPartner](https://technet.microsoft.com/library/JJ204631(v=OCS.15))

  - [Remove-CsXmppAllowedPartner](https://technet.microsoft.com/library/JJ205055(v=OCS.15))

  - [Set-CsXmppAllowedPartner](https://technet.microsoft.com/library/JJ204686(v=OCS.15))

<!-- end list -->

  - [Get-applet csxmppgatewayconfiguration ne](https://technet.microsoft.com/library/JJ204869(v=OCS.15))

  - [Set-applet csxmppgatewayconfiguration ne](https://technet.microsoft.com/library/JJ204769(v=OCS.15))

<!-- end list -->

  - [Test-CsXmppIM](https://technet.microsoft.com/library/JJ205423(v=OCS.15))

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Blog Lync Server PowerShell](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

