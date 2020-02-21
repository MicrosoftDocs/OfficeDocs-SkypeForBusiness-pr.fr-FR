---
title: 'Lync Server 2013 : applets de commande de messagerie instantanée et de présence'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IM and presence cmdlets
ms:assetid: 7b882480-f3d5-44a2-bb75-fffb7e5caede
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398611(v=OCS.15)
ms:contentKeyID: 48184589
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8a39f195bf6424f76a98e2b5c25dc4bf21942911
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42199757"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="im-and-presence-cmdlets-in-lync-server-2013"></a>Applets de commande de messagerie instantanée et de présence dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-06-26_

Les applets de commande de messagerie instantanée et de présence vous permettent de gérer ces fonctionnalités clientes via Windows PowerShell. Vous pouvez définir des stratégies de présence qui s’appliquent aux utilisateurs dans l’étendue globale, Site ou utilisateur. Vous pouvez également configurer différentes fonctionnalités de confidentialité et de messagerie instantanée.

<div>

## <a name="im-and-presence-cmdlets"></a>Applets de commande de messagerie instantanée et de présence

Pour configurer la messagerie instantanée et la présence, utilisez les applets de commande suivantes :

  - <span></span>  
    [Get-CsPresencePolicy](https://technet.microsoft.com/library/Gg398463(v=OCS.15))

  - <span></span>  
    [GRANT-CsPresencePolicy](https://technet.microsoft.com/library/Gg398571(v=OCS.15))

  - <span></span>  
    [New-CsPresencePolicy](https://technet.microsoft.com/library/Gg412747(v=OCS.15))

  - <span></span>  
    [Remove-CsPresencePolicy](https://technet.microsoft.com/library/Gg399070(v=OCS.15))

  - <span></span>  
    [Set-CsPresencePolicy](https://technet.microsoft.com/library/Gg425782(v=OCS.15))

<!-- end list -->

  - [Get-applet cspresenceprovider](https://technet.microsoft.com/library/JJ204705(v=OCS.15))

  - [New-applet cspresenceprovider](https://technet.microsoft.com/library/JJ204895(v=OCS.15))

  - [Remove-applet cspresenceprovider](https://technet.microsoft.com/library/JJ205036(v=OCS.15))

  - [Set-applet cspresenceprovider](https://technet.microsoft.com/library/JJ204833(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsPrivacyConfiguration](https://technet.microsoft.com/library/Gg413002(v=OCS.15))

  - <span></span>  
    [New-CsPrivacyConfiguration](https://technet.microsoft.com/library/Gg398807(v=OCS.15))

  - <span></span>  
    [Remove-CsPrivacyConfiguration](https://technet.microsoft.com/library/Gg425821(v=OCS.15))

  - <span></span>  
    [Set-CsPrivacyConfiguration](https://technet.microsoft.com/library/Gg398484(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Set-CsUserServer](https://technet.microsoft.com/library/Gg413026(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsUserServicesConfiguration](https://technet.microsoft.com/library/Gg398133(v=OCS.15))

  - <span></span>  
    [New-CsUserServicesConfiguration](https://technet.microsoft.com/library/Gg412926(v=OCS.15))

  - <span></span>  
    [Remove-CsUserServicesConfiguration](https://technet.microsoft.com/library/Gg398722(v=OCS.15))

  - <span></span>  
    [Set-CsUserServicesConfiguration](https://technet.microsoft.com/library/Gg398340(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsFileTransferFilterConfiguration](https://technet.microsoft.com/library/Gg398527(v=OCS.15))

  - <span></span>  
    [New-CsFileTransferFilterConfiguration](https://technet.microsoft.com/library/Gg425897(v=OCS.15))

  - <span></span>  
    [Remove-CsFileTransferFilterConfiguration](https://technet.microsoft.com/library/Gg413064(v=OCS.15))

  - <span></span>  
    [Set-CsFileTransferFilterConfiguration](https://technet.microsoft.com/library/Gg425736(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsImFilterConfiguration](https://technet.microsoft.com/library/Gg398980(v=OCS.15))

  - <span></span>  
    [New-CsImFilterConfiguration](https://technet.microsoft.com/library/Gg398244(v=OCS.15))

  - <span></span>  
    [Remove-CsImFilterConfiguration](https://technet.microsoft.com/library/Gg398171(v=OCS.15))

  - <span></span>  
    [Set-CsImFilterConfiguration](https://technet.microsoft.com/library/Gg412960(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Test-CsGroupExpansion](https://technet.microsoft.com/library/Gg399009(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Test-CsGroupIM](https://technet.microsoft.com/library/Gg398273(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Test-CsIM](https://technet.microsoft.com/library/Gg425802(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Test-CsP2PAV](https://technet.microsoft.com/library/Gg412821(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Test-CsPresence](https://technet.microsoft.com/library/Gg398148(v=OCS.15))

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Applets de commande de gestion des clients dans Lync Server 2013](lync-server-2013-client-management-cmdlets.md)  


[Blog Lync Server PowerShell](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

