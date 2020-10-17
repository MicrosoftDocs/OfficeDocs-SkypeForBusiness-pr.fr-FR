---
title: 'Lync Server 2013 : applets de commande voix entreprise'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enterprise Voice cmdlets
ms:assetid: 7d7c6d94-3ead-4d99-95f7-c31b448ab9e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415658(v=OCS.15)
ms:contentKeyID: 48184613
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 91f20a5a1df722e92454e0200a0c8174ff37d4dc
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533201"
---
# <a name="enterprise-voice-cmdlets-in-lync-server-2013"></a>Applets de commande voix entreprise dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-03-19_

Voix Entreprise est l’implémentation Microsoft du protocole VoIP (voix sur IP). Les applets de commande disponibles pour la gestion de voix entreprise dans Microsoft Lync Server 2013 vous permettent de créer et de modifier des plans de numérotation (anciennement appelés profils d’emplacement), des stratégies de voix, des itinéraires et des règles de normalisation.

<div>

## <a name="enterprise-voice-cmdlets"></a>Applets de commande de Voix Entreprise

La plupart des tâches de gestion qui s’appliquent à voix entreprise peuvent être effectuées à partir du panneau de configuration Lync Server. Ces mêmes tâches peuvent être exécutées à l’aide d’applets de commande de Lync Server Management Shell ou à partir d’un script, ce qui vous permet d’automatiser certaines tâches. Voici une liste des applets de commande qui sont directement liées à la gestion de voix entreprise :

**[Dépannage des applets de commande voix entreprise dans Lync Server 2013](lync-server-2013-troubleshooting-enterprise-voice-cmdlets.md)**

  - <span></span>  
    [Get-CsVoiceConfiguration](https://technet.microsoft.com/library/Gg398815(v=OCS.15))

  - <span></span>  
    [Remove-CsVoiceConfiguration](https://technet.microsoft.com/library/Gg398804(v=OCS.15))

  - <span></span>  
    [Set-CsVoiceConfiguration](https://technet.microsoft.com/library/Gg398967(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-applet csvoicetestconfiguration](https://technet.microsoft.com/library/Gg412957(v=OCS.15))

  - <span></span>  
    [New-applet csvoicetestconfiguration](https://technet.microsoft.com/library/Gg398961(v=OCS.15))

  - <span></span>  
    [Remove-applet csvoicetestconfiguration](https://technet.microsoft.com/library/Gg412813(v=OCS.15))

  - <span></span>  
    [Set-applet csvoicetestconfiguration](https://technet.microsoft.com/library/Gg398614(v=OCS.15))

  - <span></span>  
    [Test-applet csvoicetestconfiguration](https://technet.microsoft.com/library/Gg398260(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Test-CsDialPlan](https://technet.microsoft.com/library/Gg399024(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Test-CsVoiceNormalizationRule](https://technet.microsoft.com/library/Gg399003(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Test-CsVoicePolicy](https://technet.microsoft.com/library/Gg398310(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Test-CsVoiceRoute](https://technet.microsoft.com/library/Gg425873(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Test-CsVoiceUser](https://technet.microsoft.com/library/Gg413013(v=OCS.15))

**[Cmdlets de règles de normalisation vocale dans Lync Server 2013](lync-server-2013-voice-normalization-rules-cmdlets.md)**

  - <span></span>  
    [Get-CsVoiceNormalizationRule](https://technet.microsoft.com/library/Gg398393(v=OCS.15))

  - <span></span>  
    [New-CsVoiceNormalizationRule](https://technet.microsoft.com/library/Gg398240(v=OCS.15))

  - <span></span>  
    [Remove-CsVoiceNormalizationRule](https://technet.microsoft.com/library/Gg398501(v=OCS.15))

  - <span></span>  
    [Set-CsVoiceNormalizationRule](https://technet.microsoft.com/library/Gg398491(v=OCS.15))

  - <span></span>  
    [Test-CsVoiceNormalizationRule](https://technet.microsoft.com/library/Gg399003(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [New-CsVoiceRegex](https://technet.microsoft.com/library/Gg412751(v=OCS.15))

**[Applets de commande de stratégie de voix dans Lync Server 2013](lync-server-2013-voice-policy-cmdlets.md)**

  - <span></span>  
    [Get-CsDialPlan](https://technet.microsoft.com/library/Gg413043(v=OCS.15))

  - <span></span>  
    [Grant-CsDialPlan](https://technet.microsoft.com/library/Gg398547(v=OCS.15))

  - <span></span>  
    [New-CsDialPlan](https://technet.microsoft.com/library/Gg425860(v=OCS.15))

  - <span></span>  
    [Remove-CsDialPlan](https://technet.microsoft.com/library/Gg398791(v=OCS.15))

  - <span></span>  
    [Set-CsDialPlan](https://technet.microsoft.com/library/Gg398644(v=OCS.15))

  - <span></span>  
    [Test-CsDialPlan](https://technet.microsoft.com/library/Gg399024(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsPstnUsage](https://technet.microsoft.com/library/Gg412734(v=OCS.15))

  - <span></span>  
    [Set-CsPstnUsage](https://technet.microsoft.com/library/Gg399069(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsVoicePolicy](https://technet.microsoft.com/library/Gg398101(v=OCS.15))

  - <span></span>  
    [Grant-CsVoicePolicy](https://technet.microsoft.com/library/Gg398828(v=OCS.15))

  - <span></span>  
    [New-CsVoicePolicy](https://technet.microsoft.com/library/Gg425856(v=OCS.15))

  - <span></span>  
    [Remove-CsVoicePolicy](https://technet.microsoft.com/library/Gg398309(v=OCS.15))

  - <span></span>  
    [Set-CsVoicePolicy](https://technet.microsoft.com/library/Gg399021(v=OCS.15))

  - <span></span>  
    [Test-CsVoicePolicy](https://technet.microsoft.com/library/Gg398310(v=OCS.15))

**[Applets de commande de routage des communications vocales dans Lync Server 2013](lync-server-2013-voice-routing-cmdlets.md)**

  - <span></span>  
    [Get-CsRoutingConfiguration](https://technet.microsoft.com/library/Gg425851(v=OCS.15))

  - <span></span>  
    [New-CsRoutingConfiguration](https://technet.microsoft.com/library/Gg399056(v=OCS.15))

  - <span></span>  
    [Remove-CsRoutingConfiguration](https://technet.microsoft.com/library/Gg398643(v=OCS.15))

  - <span></span>  
    [Set-CsRoutingConfiguration](https://technet.microsoft.com/library/Gg412811(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsVoiceRoute](https://technet.microsoft.com/library/Gg425926(v=OCS.15))

  - <span></span>  
    [New-CsVoiceRoute](https://technet.microsoft.com/library/Gg398197(v=OCS.15))

  - <span></span>  
    [Remove-CsVoiceRoute](https://technet.microsoft.com/library/Gg398468(v=OCS.15))

  - <span></span>  
    [Set-CsVoiceRoute](https://technet.microsoft.com/library/Gg412893(v=OCS.15))

  - <span></span>  
    [Test-CsVoiceRoute](https://technet.microsoft.com/library/Gg425873(v=OCS.15))

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Applets de commande voix entreprise avancées dans Lync Server 2013](lync-server-2013-advanced-enterprise-voice-cmdlets.md)  
[Applets de commande pour les applications vocales dans Lync Server 2013](lync-server-2013-voice-application-cmdlets.md)  


[Blog Lync Server PowerShell](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

