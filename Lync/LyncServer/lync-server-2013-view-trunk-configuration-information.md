---
title: 'Lync Server 2013 : afficher les informations de configuration de jonction'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View trunk configuration information
ms:assetid: ebe10e14-08c2-4797-9254-9ed89516d5cd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721927(v=OCS.15)
ms:contentKeyID: 49733862
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b85e0398dc02c6138ebd41914f6edeb35ecefe01
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036372"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-trunk-configuration-information-in-lync-server-2013"></a><span data-ttu-id="2c0c5-102">Afficher les informations de configuration de jonction dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2c0c5-102">View trunk configuration information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2c0c5-103">_**Dernière modification de la rubrique :** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="2c0c5-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="2c0c5-p101">Les paramètres de configuration de jonction SIP définissent la relation et les capacités entre un serveur de médiation et la passerelle du réseau téléphonique commuté (PSTN), un autocommutateur privé IP (PBX) ou un contrôleur SBC du côté fournisseur de services. Ces paramètres permettent de spécifier ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="2c0c5-p101">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the public switched telephone network (PSTN) gateway, an IP-public branch exchange (PBX), or a Session Border Controller (SBC) at the service provider. These settings do such things as specify:</span></span>

  - <span data-ttu-id="2c0c5-106">L’activation ou non du contournement de média sur les jonctions.</span><span class="sxs-lookup"><span data-stu-id="2c0c5-106">Whether media bypass should be enabled on the trunks.</span></span>

  - <span data-ttu-id="2c0c5-107">Les conditions d’envoi des paquets RTCP (Real-time Transport Control Protocol).</span><span class="sxs-lookup"><span data-stu-id="2c0c5-107">The conditions under which real-time transport control protocol (RTCP) packets are sent.</span></span>

  - <span data-ttu-id="2c0c5-108">L’application ou non du chiffrement SRTP (Secure Real-Time Protocol) sur chaque jonction.</span><span class="sxs-lookup"><span data-stu-id="2c0c5-108">Whether or not secure real-time protocol (SRTP) encryption is required on each trunk.</span></span>

<span data-ttu-id="2c0c5-109">Lorsque vous installez Microsoft Lync Server 2013, une collection globale de paramètres de configuration de jonction SIP (Session Initiation Protocol) est créée.</span><span class="sxs-lookup"><span data-stu-id="2c0c5-109">When you install Microsoft Lync Server 2013, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="2c0c5-110">En outre, les administrateurs peuvent créer des collections personnalisées sur l’étendue du site ou l’étendue du service (pour le service de passerelle PSTN, uniquement).</span><span class="sxs-lookup"><span data-stu-id="2c0c5-110">In addition, administrators can create custom setting collections at the site scope or at the service scope (for the PSTN gateway service, only).</span></span>

<div>

## <a name="to-view-sip-trunk-configuration-information-by-using-lync-server-control-panel"></a><span data-ttu-id="2c0c5-111">Pour afficher les informations de configuration de jonction SIP à l’aide du panneau de configuration Lync Server</span><span class="sxs-lookup"><span data-stu-id="2c0c5-111">To view SIP trunk configuration information by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="2c0c5-112">Dans le panneau de configuration Lync Server, cliquez sur **routage des communications vocales** , puis sur Configuration de la **jonction**.</span><span class="sxs-lookup"><span data-stu-id="2c0c5-112">In Lync Server Control Panel, click **Voice Routing** and then click **Trunk Configuration**.</span></span>

2.  <span data-ttu-id="2c0c5-113">Dans l’onglet Configuration de la **jonction** , vous verrez une liste de tous vos paramètres de configuration de jonction ; pour chaque collection, vous verrez des valeurs pour les propriétés **nom**, **étendue**, **État**et déviation du trafic **multimédia** , ainsi que le nombre d' **utilisations RTC**, de **règles de numéro d’appel**et de règles de **numérotation** associées à la collection.</span><span class="sxs-lookup"><span data-stu-id="2c0c5-113">On the **Trunk Configuration** tab you will see a list of all your trunk configuration settings collection; for each collection you will see values for the **Name**, **Scope**, **State**, and **Media bypass** properties, along with the number of **PSTN usages**, **Calling number rules**, and **Called number rules** associated with the collection.</span></span> <span data-ttu-id="2c0c5-114">Pour afficher des détails supplémentaires sur une collection de paramètres de configuration de jonction, cliquez sur la collection d’intérêt, sur **modifier**, puis sur **afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="2c0c5-114">To see additional details about a collection of trunk configuration settings, click the collection of interest, click **Edit**, and then click **Show details**.</span></span> <span data-ttu-id="2c0c5-115">Notez que vous pouvez afficher des informations détaillées uniquement pour une collection de paramètres de configuration de jonction à la fois.</span><span class="sxs-lookup"><span data-stu-id="2c0c5-115">Note that you can view detailed information only for one collection of trunk configuration settings at a time.</span></span>

</div>

<div>

## <a name="viewing-sip-trunk-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="2c0c5-116">Affichage des informations de configuration de jonction SIP à l’aide des applets de commande Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="2c0c5-116">Viewing SIP Trunk Configuration Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="2c0c5-117">Les paramètres de configuration de jonction SIP peuvent être affichés à l’aide de Lync Server PowerShell et de la cmdlet Get-applet cstrunkconfiguration.</span><span class="sxs-lookup"><span data-stu-id="2c0c5-117">SIP trunk configuration settings can be viewed by using Lync Server PowerShell and the Get-CsTrunkConfiguration cmdlet.</span></span> <span data-ttu-id="2c0c5-118">Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2c0c5-118">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session Windows PowerShell.</span></span> <span data-ttu-id="2c0c5-119">Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 Using Remote PowerShell » (en anglais) à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="2c0c5-119">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-sip-trunk-configuration-information"></a><span data-ttu-id="2c0c5-120">Pour afficher les informations de configuration de jonction SIP</span><span class="sxs-lookup"><span data-stu-id="2c0c5-120">To view SIP trunk configuration information</span></span>

  - <span data-ttu-id="2c0c5-121">Pour afficher des informations sur tous les paramètres de configuration de jonction SIP, tapez la commande suivante dans Lync Server Management Shell, puis appuyez sur entrée :</span><span class="sxs-lookup"><span data-stu-id="2c0c5-121">To view information about all your SIP trunk configuration settings, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsTrunkConfiguration
    
    <span data-ttu-id="2c0c5-122">Cette action a pour effet de renvoyer des informations similaires à ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="2c0c5-122">That will return information similar to this:</span></span>
    
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

<span data-ttu-id="2c0c5-123">Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de commande [Get-applet cstrunkconfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunkConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="2c0c5-123">For more information, see the help topic for the [Get-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunkConfiguration) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

