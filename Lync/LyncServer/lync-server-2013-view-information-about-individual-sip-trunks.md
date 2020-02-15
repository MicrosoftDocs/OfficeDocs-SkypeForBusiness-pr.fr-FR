---
title: 'Lync Server 2013 : affichage des informations sur les jonctions SIP individuelles'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View information about individual SIP trunks
ms:assetid: adfacb74-7ea5-4c53-934e-ba7ec59879eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721847(v=OCS.15)
ms:contentKeyID: 49733780
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3163bb6298bef570a68f2fcfd7dec66167549b21
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029725"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-information-about-individual-sip-trunks-in-lync-server-2013"></a>Afficher des informations sur les jonctions SIP individuelles dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-21_

Les jonctions SIP sont utilisées pour connecter le réseau téléphonique IP de Lync Server 2013 avec le réseau téléphonique commuté public. Dans la version précédente du produit, les jonctions étaient utilisées pour acheminer les appels sortants d’un serveur de médiation vers une passerelle PSTN et chaque passerelle était limitée à une jonction unique. Par conséquent, une passerelle PSTN et une jonction SIP étaient fondamentalement identiques. Pour les administrateurs, cela signifie qu’ils pouvaient afficher des informations sur une jonction SIP individuelle en affichant simplement des informations sur la passerelle PSTN associée.

Dans Lync Server 2013, toutefois, plusieurs jonctions peuvent désormais être attribuées à une seule passerelle PSTN ; Cela signifie que les passerelles et les jonctions ne sont plus de l’un et le même. En retour, cela signifie que les administrateurs doivent utiliser la nouvelle cmdlet [Get-CsTrunk](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunk) pour afficher des informations sur une jonction SIP individuelle.

La cmdlet Get-CsTrunk peut être exécutée à partir de Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 Using Remote PowerShell » (en anglais) à l’adresse.

<div>

## <a name="to-view-information-for-all-your-sip-trunks"></a>Pour afficher les informations de toutes vos jonctions SIP

  - La commande suivante retourne des informations sur toutes les jonctions SIP utilisées dans votre organisation :
    
        Get-CsTrunk

</div>

<div>

## <a name="to-view-information-for-a-specific-sip-trunk"></a>Pour afficher les informations d’une jonction SIP spécifique

  - Cette commande renvoie des informations uniquement pour la jonction SIP avec l’identité PstnGateway : 192.168.0.240 :
    
        Get-CsTrunk -Identity "PstnGateway:192.168.0.240"

</div>

<div>

## <a name="viewing-information-for-all-the-sip-trunks-assigned-to-a-pool"></a>Affichage des informations pour toutes les jonctions SIP affectées à un pool

  - Dans cet exemple, les informations sont renvoyées pour toutes les jonctions SIP affectées au pool atl-cs-001.litwareinc.com :
    
        Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"

</div>

</div>

<span> </span>

</div>

</div>

</div>

