---
title: 'Lync Server 2013 : applets de commande d’archivage et de surveillance'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Archiving and Monitoring cmdlets
ms:assetid: 04e1d0f6-d00e-4d8f-b969-daf092b2cdb4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415629(v=OCS.15)
ms:contentKeyID: 48183281
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 11cd7a2f9cb9eceb68535cec1160dc48ce12b2a9
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48517971"
---
# <a name="archiving-and-monitoring-cmdlets-in-lync-server-2013"></a>Applets de commande d’archivage et de surveillance dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-04_

Les applets de commande d’archivage et de surveillance permettent aux administrateurs de gérer l’archivage des sessions de messagerie instantanée et de conférence ; pour enregistrer les informations détaillées des appels ; et pour surveiller Microsoft Lync Server 2013 à l’aide de la qualité de l’expérience (QoE).


> [!NOTE]
> Pour plus d’informations sur les applets de commande, voir le blog Lync Server &nbsp; Windows PowerShell à l’adresse <A href="https://go.microsoft.com/fwlink/p/?linkid=263432">https://go.microsoft.com/fwlink/p/?linkId=263432</A> . Le contenu de chaque blog et les URL correspondantes peuvent faire l'objet de modifications sans préavis.



<div>

## <a name="archiving-and-monitoring-cmdlets"></a>Applets de commande d’archivage et de surveillance

La liste suivante indique les applets de commande qui sont directement associées à la gestion de l’archivage et de la surveillance :

**Archivage et surveillance**

  - <span></span>  
    [Get-applet csarchivingconfiguration](https://technet.microsoft.com/library/Gg399012(v=OCS.15))

  - <span></span>  
    [New-applet csarchivingconfiguration](https://technet.microsoft.com/library/Gg398471(v=OCS.15))

  - <span></span>  
    [Remove-applet csarchivingconfiguration](https://technet.microsoft.com/library/Gg398951(v=OCS.15))

  - <span></span>  
    [Set-applet csarchivingconfiguration](https://technet.microsoft.com/library/Gg413030(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Export-applet csarchivingdata](https://technet.microsoft.com/library/Gg398452(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Invoke-applet csarchivingdatabasepurge](https://technet.microsoft.com/library/JJ204627(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-applet csarchivingpolicy](https://technet.microsoft.com/library/Gg425731(v=OCS.15))

  - <span></span>  
    [Grant-applet csarchivingpolicy](https://technet.microsoft.com/library/Gg398475(v=OCS.15))

  - <span></span>  
    [New-applet csarchivingpolicy](https://technet.microsoft.com/library/Gg399032(v=OCS.15))

  - <span></span>  
    [Remove-applet csarchivingpolicy](https://technet.microsoft.com/library/Gg425924(v=OCS.15))

  - <span></span>  
    [Set-applet csarchivingpolicy](https://technet.microsoft.com/library/Gg398294(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Set-CsArchivingServer](https://technet.microsoft.com/library/Gg398923(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-applet cscdrconfiguration](https://technet.microsoft.com/library/Gg398298(v=OCS.15))

  - <span></span>  
    [New-applet cscdrconfiguration](https://technet.microsoft.com/library/Gg399018(v=OCS.15))

  - <span></span>  
    [Remove-applet cscdrconfiguration](https://technet.microsoft.com/library/Gg398451(v=OCS.15))

  - <span></span>  
    [Set-applet cscdrconfiguration](https://technet.microsoft.com/library/Gg398774(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Set-CsMonitoringServer](https://technet.microsoft.com/library/Gg425776(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsQoEConfiguration](https://technet.microsoft.com/library/Gg399004(v=OCS.15))

  - <span></span>  
    [New-CsQoEConfiguration](https://technet.microsoft.com/library/Gg398325(v=OCS.15))

  - <span></span>  
    [Remove-CsQoEConfiguration](https://technet.microsoft.com/library/Gg425879(v=OCS.15))

  - <span></span>  
    [Set-CsQoEConfiguration](https://technet.microsoft.com/library/Gg398245(v=OCS.15))

[Invoke-CsCdrDatabasePurge](https://technet.microsoft.com/library/JJ205113(v=OCS.15))

  - <span></span>  
    [Export-applet csarchivingdata](https://technet.microsoft.com/library/Gg398452(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Invoke-applet csqoedatabasepurge](https://technet.microsoft.com/library/JJ205247(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-applet csreportingconfiguration](https://technet.microsoft.com/library/JJ205356(v=OCS.15))

  - <span></span>  
    [New-applet csreportingconfiguration](https://technet.microsoft.com/library/JJ204787(v=OCS.15))

  - <span></span>  
    [Remove-applet csreportingconfiguration](https://technet.microsoft.com/library/JJ204711(v=OCS.15))

  - <span></span>  
    [Set-applet csreportingconfiguration](https://technet.microsoft.com/library/JJ205075(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-applet cstestusercredential](https://technet.microsoft.com/library/JJ204759(v=OCS.15))

  - <span></span>  
    [Remove-applet cstestusercredential](https://technet.microsoft.com/library/JJ204870(v=OCS.15))

  - <span></span>  
    [Set-applet cstestusercredential](https://technet.microsoft.com/library/JJ205341(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-applet cswatchernodeconfiguration](https://technet.microsoft.com/library/JJ204739(v=OCS.15))

  - <span></span>  
    [New-applet cswatchernodeconfiguration](https://technet.microsoft.com/library/JJ205254(v=OCS.15))

  - <span></span>  
    [Remove-applet cswatchernodeconfiguration](https://technet.microsoft.com/library/JJ204926(v=OCS.15))

  - <span></span>  
    [Set-applet cswatchernodeconfiguration](https://technet.microsoft.com/library/JJ204620(v=OCS.15))

  - <span></span>  
    [Test-applet cswatchernodeconfiguration](https://technet.microsoft.com/library/JJ204652(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [New-CsExtendedTest](https://technet.microsoft.com/library/JJ205275(v=OCS.15))

</div>

</div>

<span> </span>

</div>

</div>

</div>

