---
title: Déplacer des objets contact de la messagerie unifiée Exchange
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Move Exchange Unified Messaging Contact objects
ms:assetid: 35c7e987-41b5-4798-b617-3303f20e52e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688022(v=OCS.15)
ms:contentKeyID: 49733612
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f3b3091a342b46b5c1aad1d456aa9159d951a4ba
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44756613"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="move-exchange-unified-messaging-contact-objects"></a>Déplacer des objets contact de la messagerie unifiée Exchange

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-19_

Pour migrer les objets de contact de standard automatique (AA) et d’accès abonné (SA) vers le nouveau déploiement Lync Server 2013, vous devez d’abord déplacer les objets depuis le déploiement hérité d’Office Communications Server 2007 R2 vers le nouveau déploiement Lync Server 2013 à l’aide des cmdlets **Get-CsExUmContact** et **Move-CsExUmContact** . Sur le serveur Exchange, exécutez le script Windows PowerShell **exchucutil** pour effectuer les opérations suivantes pour le pool Lync nouvellement déployé :

  - Ajoutez-le aux passerelles IP de messagerie unifiée.

  - l’ajouter aux groupes de recherche.

<div>


> [!NOTE]  
> In order to use the <STRONG>Get-CsExUmContact</STRONG> and <STRONG>Move-CsExUmContact</STRONG> cmdlets, you must be a member of the RTCUniversalUserAdmins group and have organizational unit (OU) permission to the OU where the contacts objects are stored. OU permission can be granted using the <STRONG>Grant-OUPermission</STRONG> cmdlet.



</div>

<div>

## <a name="to-move-contact-objects-by-using-the-lync-server-management-shell"></a>Pour déplacer des objets contact à l’aide de Lync Server Management Shell

1.  Ouvrez Lync Server Management Shell.

2.  Pour chaque pool enregistré avec la messagerie unifiée Exchange (où pool1.contoso.net est un pool du déploiement d’Office Communications Server 2007 R2 et pool2.contoso.net est le pool du déploiement de Lync Server 2013), tapez ce qui suit dans la ligne de commande :
    
        Get-CsExUmContact -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsExUmContact -Target pool02.contoso.net
    
    Pour vérifier que les objets contact sont déplacés, exécutez la cmdlet **Get-CsExumContact** et assurez-vous que **RegistrarPool** pointe maintenant vers le nouveau pool.

</div>

<div>

## <a name="to-run-the-exchucutil-windows-powershell-script"></a>Pour exécuter le script Windows PowerShell ExchUCUtilscript

1.  Ouvrez une session sur le serveur de messagerie unifiée Exchange en tant qu’utilisateur disposant des autorisations d’administrateur d’organisation Exchange.

2.  Naviguez jusqu’au script Windows PowerShell ExchUCUtil.
    
    Dans Exchange 2007, ExchUCUtil.ps1 se trouve à l’emplacement suivant : **% Program Files% \\ Microsoft \\ Exchange Server \\ scripts \\ExchUCUtil.ps1**
    
    Dans Exchange 2010, ExchUCUtil.ps1 se trouve à l’emplacement suivant : **% Program Files% \\ Microsoft \\ Exchange Server \\ v14 \\ scripts \\ExchUCUtil.ps1**

3.  Si Exchange est déployé dans une forêt unique, tapez ceci :
    
        exchucutil.ps1
    
    Ou, si Exchange est déployé dans plusieurs forêts, tapez ceci :
    
        exchucutil.ps1 -Forest:" <forest FQDN>"
    
    où Forest FQDN indique la forêt dans laquelle Lync Server 2013 est déployé.
    
    <div>
    

    > [!IMPORTANT]  
    > Redémarrez le service <STRONG>frontal Lync Server</STRONG> (rtcsrv.exe) <EM>après</EM> avoir exécuté exchucutil.ps1. Dans le cas contraire, Lync Server 2013 ne détecte pas la messagerie unifiée dans la topologie.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

