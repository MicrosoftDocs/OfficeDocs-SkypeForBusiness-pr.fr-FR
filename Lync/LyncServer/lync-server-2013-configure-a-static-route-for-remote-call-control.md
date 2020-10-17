---
title: 'Lync Server 2013 : configurer un itinéraire statique pour le contrôle d’appel distant'
description: 'Lync Server 2013 : configurez un itinéraire statique pour le contrôle d’appel distant.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure a static route for remote call control
ms:assetid: f7003023-443d-48ee-989b-71e8b0b0abbd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615051(v=OCS.15)
ms:contentKeyID: 48185855
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8ecf6478d4fb7ab4f04f8a452d4837b327ba254a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48551690"
---
# <a name="configure-a-static-route-for-remote-call-control-in-lync-server-2013"></a><span data-ttu-id="9732c-103">Configurer un itinéraire statique pour le contrôle d’appel distant dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9732c-103">Configure a static route for remote call control in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9732c-104">_**Dernière modification de la rubrique :** 2012-09-22_</span><span class="sxs-lookup"><span data-stu-id="9732c-104">_**Topic Last Modified:** 2012-09-22_</span></span>

<span data-ttu-id="9732c-105">Le contrôle d’appel distant exige que tous les pools Lync Server soient configurés avec un chemin d’accès à partir de ce pool vers la passerelle SIP/CSTA qui se connecte à l’autocommutateur privé (PBX).</span><span class="sxs-lookup"><span data-stu-id="9732c-105">Remote call control requires that every Lync Server pool is configured with a path from that pool to the SIP/CSTA gateway that connects to the private branch exchange (PBX).</span></span> <span data-ttu-id="9732c-106">Ce chemin d’accès exige que chaque pool ait un itinéraire statique pour chaque passerelle vers laquelle le pool servira de proxy pour les messages de contrôle d’appel SIP associés aux appels vers le PBX.</span><span class="sxs-lookup"><span data-stu-id="9732c-106">This path requires that each pool has one static route for each gateway to which the pool will proxy SIP call control messages associated with calls to the PBX.</span></span> <span data-ttu-id="9732c-107">Si vous configurez un itinéraire statique global pour le contrôle d’appel distant, chaque pool qui n’est pas configuré avec un itinéraire statique au niveau du pool utilisera l’itinéraire statique global.</span><span class="sxs-lookup"><span data-stu-id="9732c-107">If you configure a global static route for remote call control, each pool that is not configured with a static route at the pool level will use the global static route.</span></span>

<div>

## <a name="to-configure-a-static-route-for-remote-call-control"></a><span data-ttu-id="9732c-108">Pour configurer un itinéraire statique pour le contrôle d’appel distant</span><span class="sxs-lookup"><span data-stu-id="9732c-108">To configure a static route for remote call control</span></span>

1.  <span data-ttu-id="9732c-109">Ouvrez une session sur un ordinateur sur lequel Lync Server Management Shell est installé en tant que membre du groupe RTCUniversalServerAdmins ou d’un rôle RBAC (contrôle d’accès basé sur un rôle) auquel vous avez affecté la cmdlet **New-CsStaticRoute** .</span><span class="sxs-lookup"><span data-stu-id="9732c-109">Log on to a computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or a role-based access control (RBAC) role to which you have assigned the **New-CsStaticRoute** cmdlet.</span></span>

2.  <span data-ttu-id="9732c-110">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="9732c-110">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="9732c-111">Pour créer un itinéraire statique et le placer dans la variable $TLSRoute ou $TCPRoute, effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="9732c-111">To create a static route and put it in the variable $TLSRoute or $TCPRoute, do one of the following:</span></span>
    
    <div class="">
    

    > [!TIP]  
    > <span data-ttu-id="9732c-p102">Pour faire correspondre les domaines enfants d’un domaine, vous pouvez spécifier une valeur à caractère générique dans le paramètre MatchUri. Par exemple, <STRONG>\*.contoso.net</STRONG>. Cette valeur fait correspondre tout domaine se terminant par le suffixe <STRONG>contoso.net</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="9732c-p102">To match child domains of a domain, you can specify a wildcard value in the MatchUri parameter. For example, <STRONG>\*.contoso.net</STRONG>. That value matches any domain that ends with the suffix <STRONG>contoso.net</STRONG>.</span></span>

    
    </div>
    
      - <span data-ttu-id="9732c-115">Pour une connexion TLS (Transport Layer Security), tapez ce qui suit à l’invite de commandes :</span><span class="sxs-lookup"><span data-stu-id="9732c-115">For a Transport Layer Security (TLS) connection, type the following at the command prompt:</span></span>
        
        ```powershell
        $TLSRoute = New-CsStaticRoute -TLSRoute -Destination <gateway FQDN> -Port <gateway SIP listening port> -UseDefaultCertificate $true -MatchUri <destination domain>
        ```
        <span data-ttu-id="9732c-116">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="9732c-116">For example:</span></span>
        ```powershell
        $TLSRoute = New-CsStaticRoute -TLSRoute -Destination rccgateway.contoso.net -Port 5065 -UseDefaultCertificate $true -MatchUri *.contoso.net
        ```
        <span data-ttu-id="9732c-117">Si UseDefaultCertificate est défini sur False, vous devez préciser les paramètres TLSCertIssuer et TLSCertSerialNumber.</span><span class="sxs-lookup"><span data-stu-id="9732c-117">If UseDefaultCertificate is set to False, you must specify TLSCertIssuer and TLSCertSerialNumber parameters.</span></span> <span data-ttu-id="9732c-118">Ces paramètres fournissent le nom de l’autorité de certification qui a émis le certificat utilisé dans l’itinéraire statique, et le numéro de série de ce certificat TLS, respectivement.</span><span class="sxs-lookup"><span data-stu-id="9732c-118">These parameters indicate the name of the certification authority (CA) that issued the certificate used in the static route, and the serial number of that TLS certificate, respectively.</span></span> <span data-ttu-id="9732c-119">Pour plus d’informations sur ces paramètres, reportez-vous à l’aide de Lync Server Management Shell en tapant ce qui suit à l’invite de commandes :</span><span class="sxs-lookup"><span data-stu-id="9732c-119">For details about these parameters, see Lync Server Management Shell Help by typing the following at the command prompt:</span></span>
        ```powershell
        Get-Help New-CsStaticRoute -Full
        ```
      - <span data-ttu-id="9732c-120">Pour une connexion TCP (Transmission Control Protocol), tapez ce qui suit à l’invite de commandes :</span><span class="sxs-lookup"><span data-stu-id="9732c-120">For a Transmission Control Protocol (TCP) connection, type the following at the command prompt:</span></span>
        
        <div class="">
        

        > [!NOTE]  
        > <span data-ttu-id="9732c-121">Si vous spécifiez un nom de domaine complet (FQDN), vous devez commencer par configurer a enregistrement DNS (Domain Name System) A.</span><span class="sxs-lookup"><span data-stu-id="9732c-121">If you specify a fully qualified domain name (FQDN), you must configure a Domain Name System (DNS) A record first.</span></span>

        
        </div>
        
        ```powershell
        $TCPRoute = New-CsStaticRoute -TCPRoute -Destination <gateway IP address or FQDN> -Port <gateway SIP listening port> -MatchUri <destination domain>
        ```
        <span data-ttu-id="9732c-122">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="9732c-122">For example:</span></span>
        ```powershell
        $TCPRoute = New-CsStaticRoute -TCPRoute -Destination 192.168.0.240 -Port 5065 -MatchUri *.contoso.net
        ```
        <span data-ttu-id="9732c-123">Les valeurs suivantes sont les valeurs par défaut des paramètres facultatifs pour les itinéraires statiques :</span><span class="sxs-lookup"><span data-stu-id="9732c-123">The following are default values for optional parameters for static routes:</span></span>
        
          - <span data-ttu-id="9732c-124">Enabled = True</span><span class="sxs-lookup"><span data-stu-id="9732c-124">Enabled = True</span></span>
        
          - <span data-ttu-id="9732c-125">MatchOnlyPhoneUri = False</span><span class="sxs-lookup"><span data-stu-id="9732c-125">MatchOnlyPhoneUri = False</span></span>
        
          - <span data-ttu-id="9732c-126">ReplaceHostInRequestUri = False</span><span class="sxs-lookup"><span data-stu-id="9732c-126">ReplaceHostInRequestUri = False</span></span>
        
        <span data-ttu-id="9732c-127">Nous vous déconseillons fortement de modifier ces valeurs par défaut.</span><span class="sxs-lookup"><span data-stu-id="9732c-127">We strongly recommend that you do not change these default values.</span></span> <span data-ttu-id="9732c-128">Toutefois, si vous devez modifier l’un de ces paramètres, reportez-vous à l’aide de Lync Server Management Shell en tapant ce qui suit à l’invite de commandes :</span><span class="sxs-lookup"><span data-stu-id="9732c-128">However, if you must change any of these parameters, see Lync Server Management Shell Help by typing the following at the command prompt:</span></span>
        ```powershell
        Get-Help New-CsStaticRoute -Full
        ```
4.  <span data-ttu-id="9732c-129">Pour conserver un itinéraire statique nouvellement créé dans le magasin central de gestion, exécutez l’une des opérations suivantes, selon le cas :</span><span class="sxs-lookup"><span data-stu-id="9732c-129">To persist a newly created static route in the Central Management store, run one of the following, as appropriate:</span></span>
    
       ```powershell
        Set-CsStaticRoutingConfiguration -Route @{Add=$TLSRoute}
       ```
    
       ```powershell
        Set-CsStaticRoutingConfiguration -Route @{Add=$TCPRoute}
       ```

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9732c-130">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9732c-130">See Also</span></span>


[<span data-ttu-id="9732c-131">Configurer une entrée d’application approuvée pour le contrôle d’appel distant dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9732c-131">Configure a trusted application entry for remote call control in Lync Server 2013</span></span>](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)  
[<span data-ttu-id="9732c-132">Définition d’une adresse IP de passerelle SIP/CSTA dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9732c-132">Define a SIP/CSTA gateway IP address in Lync Server 2013</span></span>](lync-server-2013-define-a-sip-csta-gateway-ip-address.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

