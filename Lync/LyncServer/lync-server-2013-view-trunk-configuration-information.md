---
title: 'Lync Server 2013: afficher les informations de configuration de Trunk'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: View trunk configuration information
ms:assetid: ebe10e14-08c2-4797-9254-9ed89516d5cd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721927(v=OCS.15)
ms:contentKeyID: 49733862
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: abf496382ed33b95e8de9f387a8623fb0984ed28
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846283"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-trunk-configuration-information-in-lync-server-2013"></a>Afficher les informations de configuration de Trunk dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-02-22_

Les paramètres de configuration du Trunk SIP définissent la relation et les fonctionnalités entre un serveur de médiation et la passerelle de réseau téléphonique commuté (PSTN), un échange de succursale public (PBX) ou un contrôleur de bordure de session (SBC) au fournisseur de services. Ces paramètres spécifient, par exemple :

  - si la déviation du trafic multimédia doit être activée sur les jonctions ;

  - Les conditions dans lesquelles les paquets de contrôle de transport en temps réel (RTCP) sont envoyés.

  - Le chiffrement SRTP (Secure Real-Time Protocol) est requis sur chaque Trunk.

Lorsque vous installez Microsoft Lync Server 2013, une collection globale de paramètres de configuration de Trunk SIP est créée pour vous. En outre, les administrateurs peuvent créer des collections personnalisées sur l’étendue du site ou l’étendue du service (pour le service de passerelle PSTN, uniquement).

<div>

## <a name="to-view-sip-trunk-configuration-information-by-using-lync-server-control-panel"></a>Pour afficher les informations de configuration du Trunk SIP en utilisant le panneau de configuration de Lync Server

1.  Dans le panneau de configuration de Lync Server, cliquez sur **routage des communications vocales** , puis cliquez sur **configuration de Trunk**.

2.  Dans l’onglet **configuration de Trunk** , vous verrez la liste de toutes vos collections de paramètres de configuration de Trunk; pour chaque collection, des valeurs pour les propriétés **Name**, **scope**, **State**et **Bypass Bypass** sont disponibles, ainsi que le nombre d' **usages RTC**, de **règles de numéro d’appel**et de règles de **numéro appelées** avec la collection. Pour afficher des détails supplémentaires sur une collection de paramètres de configuration de ligne, cliquez sur l’ensemble d’intérêt, cliquez sur **modifier**, puis sur **afficher les détails**. Notez que vous pouvez afficher des informations détaillées pour une collection unique de paramètres de configuration de Trunk à la fois.

</div>

<div>

## <a name="viewing-sip-trunk-configuration-information-by-using-windows-powershell-cmdlets"></a>Affichage des informations de configuration de Trunk SIP à l’aide des cmdlets Windows PowerShell

Les paramètres de configuration de Trunk SIP peuvent être affichés à l’aide de Lync Server PowerShell et de l’applet de passe Get-CsTrunkConfiguration. Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou d’une session distante Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Lync Server, voir l’article de blog Lync Server Windows PowerShell «démarrage rapide: gestion de Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 à l’aide de Remote PowerShell».

<div>

## <a name="to-view-sip-trunk-configuration-information"></a>Pour afficher les informations de configuration du Trunk SIP

  - Pour afficher des informations sur l’ensemble des paramètres de configuration de Trunk SIP, tapez la commande suivante dans Lync Server Management Shell, puis appuyez sur entrée:
    
        Get-CsTrunkConfiguration
    
    Vous obtiendrez des indications semblables à ceci :
    
        Identity                                  : Global
        OutboundTranslationRulesList              : {}
        SipResponseCodeTranslationRulesList       : {}
        OutboundCallingNumberTranslationRulesList : {}
        PstnUsages                                : {}
        Description                               :
        ConcentratedTopology                      : True
        EnableBypass                              : False
        EnableMobileTrunkSupport                  : False
        EnableReferSupport                        : True
        EnableSessionTimer                        : False
        EnableSignalBoost                         : False
        MaxEarlyDialogs                           : 20
        RemovePlusFromUri                         : False
        RTCPActiveCalls                           : True
        RTCPCallsOnHold                           : True
        SRTPMode                                  : Required
        EnablePIDFLOSupport                       : False
        EnableRTPLatching                         : False
        EnableOnlineVoice                         : False
        ForwardCallHistory                        : False
        Enable3pccRefer                           : False
        ForwardPAI                                : False
        EnableFastFailoverTimer                   : True

</div>

Pour plus d’informations, consultez la rubrique d’aide de l’applet de passe [Get-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunkConfiguration) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

