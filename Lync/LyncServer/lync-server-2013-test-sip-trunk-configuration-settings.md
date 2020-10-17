---
title: 'Lync Server 2013 : test des paramètres de configuration de jonction SIP'
description: 'Lync Server 2013 : test des paramètres de configuration de jonction SIP.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test SIP trunk configuration settings
ms:assetid: c8712308-0e2d-4e39-8f90-d1a250487a94
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721880(v=OCS.15)
ms:contentKeyID: 49733814
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2d44fe2ef5123bec31fafaff2d811a501e5cca4a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558270"
---
# <a name="test-sip-trunk-configuration-settings-in-lync-server-2013"></a>Tester les paramètres de configuration de jonction SIP dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-11-01_

Les paramètres de configuration de jonction SIP définissent la relation et les capacités entre un serveur de médiation et la passerelle du réseau téléphonique commuté (PSTN), un autocommutateur privé IP (PBX) ou un contrôleur SBC du côté fournisseur de services. Ces paramètres permettent de spécifier ce qui suit :

  - L’activation ou non du contournement de média sur les jonctions.

  - Les conditions d’envoi des paquets RTCP (Real-time Transport Control Protocol).

  - L’application ou non du chiffrement SRTP (Secure Real-Time Protocol) sur chaque jonction.

Lorsque vous installez Microsoft Lync Server 2013, une collection globale de paramètres de configuration de jonction SIP (Session Initiation Protocol) est créée. En outre, les administrateurs peuvent créer des collections personnalisées sur l’étendue du site ou l’étendue du service (pour le service de passerelle PSTN, uniquement). Les administrateurs peuvent également utiliser l’applet de commande Test-CsTrunkConfiguration pour vérifier qu’une jonction peut convertir un numéro composé par un utilisateur en numéro pouvant être traité par la passerelle.

Les paramètres de configuration de jonction peuvent uniquement être testés à l’aide de Windows PowerShell et de l’applet de commande [Test-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/Test-CsTrunkConfiguration). Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync Server 2010 Using Remote PowerShell » (en anglais) à l’adresse [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

<div>

## <a name="to-test-sip-trunk-configuration-settings"></a>Pour tester les paramètres de configuration de jonction SIP

  - Cette commande vérifie que les paramètres de configuration de jonction pour le site Redmond peuvent convertir de façon correcte le numéro composé 4255551212.
    
        $trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
        Test-CsTrunkConfiguration -DialedNumber 4255551212 -TrunkConfiguration $trunk

</div>

</div>

<span> </span>

</div>

</div>

</div>

