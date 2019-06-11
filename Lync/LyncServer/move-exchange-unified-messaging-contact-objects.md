---
title: Déplacer les objets de contact de la messagerie unifiée Exchange
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Move Exchange Unified Messaging Contact objects
ms:assetid: 35c7e987-41b5-4798-b617-3303f20e52e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688022(v=OCS.15)
ms:contentKeyID: 49733612
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 946bf7221ab9f4c5a7111839bca25dabaad31d82
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846133"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-exchange-unified-messaging-contact-objects"></a>Déplacer les objets de contact de la messagerie unifiée Exchange

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-19_

Pour migrer des objets de contact de standard automatique (AA) et d’accès d’abonné (SA) vers le nouveau déploiement Lync Server 2013, vous devez d’abord déplacer les objets du déploiement d’Office Communications Server 2007 R2 hérités vers le nouveau déploiement de Lync Server 2013 via le ** Cmdlets Get-CsExUmContact** et **Move-CsExUmContact** . Sur le serveur Exchange, vous devez exécuter le script Windows PowerShell **exchucutil** pour effectuer les actions suivantes pour le pool Lync qui vient d’être déployé:

  - Ajoutez-le aux passerelles IP de messagerie unifiée.

  - Ajoutez-le au groupe de recherche de messagerie unifiée.

<div>


> [!NOTE]  
> Pour pouvoir utiliser les applets de commande <STRONG>Get-CsExUmContact</STRONG> et <STRONG>Move-CsExUmContact</STRONG> , vous devez être membre du groupe RTCUniversalUserAdmins et disposer de l’autorisation d’unité d’organisation (UO) pour l’unité d’organisation où les objets de contacts sont stockés. L’autorisation d’UO peut être accordée à l’aide de l’applet de commande <STRONG>Grant-OUPermission</STRONG> .



</div>

<div>

## <a name="to-move-contact-objects-by-using-the-lync-server-management-shell"></a>Pour déplacer des objets de contact à l’aide de Lync Server Management Shell

1.  Ouvrez Lync Server Management Shell.

2.  Pour chaque liste inscrite avec la messagerie unifiée Exchange (où pool1.contoso.net est un pool à partir du déploiement d’Office Communications Server 2007 R2 et pool2.contoso.net est le pool du déploiement de Lync Server 2013) sur la ligne de commande, tapez ce qui suit:
    
        Get-CsExUmContact -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsExUmContact -Target pool02.contoso.net
    
    Pour vérifier que les objets de contact sont déplacés, exécutez l’applet de contrôle **Get-CsExumContact** et vérifiez que **RegistrarPool** est désormais dirigé vers le nouveau pool.

</div>

<div>

## <a name="to-run-the-exchucutil-windows-powershell-script"></a>Pour exécuter le script Windows PowerShell ExchUCUtil

1.  Ouvrez une session sur le serveur de messagerie unifiée Exchange en tant qu’utilisateur disposant des privilèges d’administrateur de l’organisation Exchange.

2.  Accédez au script Windows PowerShell ExchUCUtil.
    
    Dans Exchange 2007, ExchUCUtil. ps1 se trouve à l’adresse: **% Program\\Files\\% Microsoft\\Exchange\\Server scripts exchucutil. ps1**
    
    Dans Exchange 2010, ExchUCUtil. ps1 se trouve à l’adresse: **% Program\\Files\\% Microsoft\\Exchange\\Server\\v14 scripts exchucutil. ps1**

3.  Si Exchange est déployé dans une seule forêt, tapez:
    
        exchucutil.ps1
    
    Ou, si Exchange est déployé dans plusieurs forêts, tapez:
    
        exchucutil.ps1 -Forest:" <forest FQDN>"
    
    où FQDN de forêt spécifie la forêt dans laquelle Lync Server 2013 est déployé.
    
    <div>
    

    > [!IMPORTANT]  
    > Assurez-vous de redémarrer le service <STRONG>frontal de Lync Server</STRONG> (rtcsrv. exe) <EM>après avoir</EM> exécuté exchucutil. ps1. Dans le cas contraire, Lync Server 2013 ne détectera pas la messagerie unifiée dans la topologie.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

