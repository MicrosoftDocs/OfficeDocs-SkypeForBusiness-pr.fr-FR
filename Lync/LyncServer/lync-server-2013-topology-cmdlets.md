---
title: 'Lync Server 2013: cmdlets Topology'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Topology cmdlets
ms:assetid: 3ed739a7-d58d-475d-8240-fa8d2c6dc7e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415648(v=OCS.15)
ms:contentKeyID: 48183942
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b2fc5224257c4bb228fdcb0b6f6f27f5416a3b03
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846492"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="topology-cmdlets-jn-lync-server-2013"></a>Cmdlets Topology Jn Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-06-20_

De nombreuses cmdlets de topologie incluses dans Microsoft Lync Server 2013 sont conçues pour une utilisation avec le générateur de configuration et de topologie. pour cette raison, il existe diverses cmdlets de topologie que les administrateurs peuvent rarement appeler directement. Néanmoins, il y aura des moments où les administrateurs seront obligés d’utiliser ces applets de cmdlet. par exemple, après la création de nouveaux comptes Kerberos, vous devez exécuter l’applet de demande [Enable-CsTopology](https://technet.microsoft.com/en-us/library/Gg398398(v=OCS.15)) pour que les modifications prennent effet. De plus, les administrateurs peuvent exécuter des cmdlets telles que [test-CsTopology](https://technet.microsoft.com/en-us/library/Gg398127(v=OCS.15)) et [test-CsComputer](https://technet.microsoft.com/en-us/library/Gg398162(v=OCS.15)) pour garantir que Lync Server 2013 a été correctement installé et qu’il fonctionne comme prévu.

<div>

## <a name="topology-cmdlets"></a>Cmdlets de topologie

Voici une liste des applets de commande qui concernent directement la topologie de votre Lync Server:

**Topologie**

  - <span></span>  
    [Get-CsPool](https://technet.microsoft.com/en-us/library/Gg398992(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsSite](https://technet.microsoft.com/en-us/library/Gg398185(v=OCS.15))

  - <span></span>  
    [Set-CsSite](https://technet.microsoft.com/en-us/library/Gg413023(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Enable-CsTopology](https://technet.microsoft.com/en-us/library/Gg398398(v=OCS.15))

  - <span></span>  
    [Get-CsTopology](https://technet.microsoft.com/en-us/library/Gg412824(v=OCS.15))

  - <span></span>  
    [Publisher-CsTopology](https://technet.microsoft.com/en-us/library/Gg398953(v=OCS.15))

  - <span></span>  
    [Test-CsTopology](https://technet.microsoft.com/en-us/library/Gg398127(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Export-CsConfiguration](https://technet.microsoft.com/en-us/library/Gg398627(v=OCS.15))

  - <span></span>  
    [Importation-CsConfiguration](https://technet.microsoft.com/en-us/library/Gg398800(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsServerVersion](https://technet.microsoft.com/en-us/library/Gg398470(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Disable-CsComputer](https://technet.microsoft.com/en-us/library/Gg399023(v=OCS.15))

  - <span></span>  
    [Enable-CsComputer](https://technet.microsoft.com/en-us/library/Gg412815(v=OCS.15))

  - <span></span>  
    [Get-CsComputer](https://technet.microsoft.com/en-us/library/Gg425959(v=OCS.15))

  - <span></span>  
    [Test-CsComputer](https://technet.microsoft.com/en-us/library/Gg398162(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsNetworkInterface](https://technet.microsoft.com/en-us/library/Gg398121(v=OCS.15))

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Blog Lync Server PowerShell](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

