---
title: 'Lync Server 2013 : Configuration d’un itinéraire statique pour le contrôle d’appel distant'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure a static route for remote call control
ms:assetid: f7003023-443d-48ee-989b-71e8b0b0abbd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615051(v=OCS.15)
ms:contentKeyID: 48185855
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2e6a388c602d30e6f60eac0c575d7640f63993f9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838462"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-a-static-route-for-remote-call-control-in-lync-server-2013"></a><span data-ttu-id="66791-102">Configuration d’un itinéraire statique pour le contrôle d’appel distant dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="66791-102">Configure a static route for remote call control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="66791-103">_**Dernière modification de la rubrique:** 2012-09-22_</span><span class="sxs-lookup"><span data-stu-id="66791-103">_**Topic Last Modified:** 2012-09-22_</span></span>

<span data-ttu-id="66791-104">Le contrôle d’appel distant nécessite que chaque pool de serveurs Lync soit configuré avec un chemin d’accès de ce pool à la passerelle SIP/CSTA qui se connecte au PBX (Private Branch Exchange).</span><span class="sxs-lookup"><span data-stu-id="66791-104">Remote call control requires that every Lync Server pool is configured with a path from that pool to the SIP/CSTA gateway that connects to the private branch exchange (PBX).</span></span> <span data-ttu-id="66791-105">Ce chemin d’accès nécessite que chaque pool dispose d’un itinéraire statique pour chaque passerelle vers laquelle le pool fera proxy les messages de contrôle d’appel SIP associés aux appels au PBX.</span><span class="sxs-lookup"><span data-stu-id="66791-105">This path requires that each pool has one static route for each gateway to which the pool will proxy SIP call control messages associated with calls to the PBX.</span></span> <span data-ttu-id="66791-106">Si vous configurez un itinéraire statique global pour le contrôle d’appel distant, chaque pool qui n’est pas configuré avec un itinéraire statique au niveau du pool utilisera l’itinéraire statique global.</span><span class="sxs-lookup"><span data-stu-id="66791-106">If you configure a global static route for remote call control, each pool that is not configured with a static route at the pool level will use the global static route.</span></span>

<div>

## <a name="to-configure-a-static-route-for-remote-call-control"></a><span data-ttu-id="66791-107">Pour configurer un itinéraire statique pour le contrôle d’appel distant</span><span class="sxs-lookup"><span data-stu-id="66791-107">To configure a static route for remote call control</span></span>

1.  <span data-ttu-id="66791-108">Connectez-vous à un ordinateur sur lequel Lync Server Management Shell est installé en tant que membre du groupe RTCUniversalServerAdmins ou d’un rôle de contrôle d’accès basé sur un rôle (RBAC) auquel vous avez affecté l’applet **de commande New-CsStaticRoute** .</span><span class="sxs-lookup"><span data-stu-id="66791-108">Log on to a computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or a role-based access control (RBAC) role to which you have assigned the **New-CsStaticRoute** cmdlet.</span></span>

2.  <span data-ttu-id="66791-109">Démarrez Lync Server Management Shell: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="66791-109">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="66791-110">Pour créer un itinéraire statique et le placer dans la variable $TLSRoute ou $TCPRoute, effectuez l’une des opérations suivantes:</span><span class="sxs-lookup"><span data-stu-id="66791-110">To create a static route and put it in the variable $TLSRoute or $TCPRoute, do one of the following:</span></span>
    
    <div class="">
    

    > [!TIP]  
    > <span data-ttu-id="66791-111">Pour correspondre aux domaines enfants d’un domaine, vous pouvez spécifier une valeur de caractère générique dans le paramètre MatchUri.</span><span class="sxs-lookup"><span data-stu-id="66791-111">To match child domains of a domain, you can specify a wildcard value in the MatchUri parameter.</span></span> <span data-ttu-id="66791-112">Par exemple, <STRONG>\*. contoso.net</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="66791-112">For example, <STRONG>\*.contoso.net</STRONG>.</span></span> <span data-ttu-id="66791-113">Cette valeur correspond à tout domaine se terminant par le suffixe <STRONG>contoso.net</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="66791-113">That value matches any domain that ends with the suffix <STRONG>contoso.net</STRONG>.</span></span>

    
    </div>
    
      - <span data-ttu-id="66791-114">Pour une connexion TLS (Transport Layer Security), à l’invite de commandes, tapez ce qui suit:</span><span class="sxs-lookup"><span data-stu-id="66791-114">For a Transport Layer Security (TLS) connection, type the following at the command prompt:</span></span>
        
            $TLSRoute = New-CsStaticRoute -TLSRoute -Destination <gateway FQDN> -Port <gateway SIP listening port> -UseDefaultCertificate $true -MatchUri <destination domain>
        
        <span data-ttu-id="66791-115">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="66791-115">For example:</span></span>
        
            $TLSRoute = New-CsStaticRoute -TLSRoute -Destination rccgateway.contoso.net -Port 5065 -UseDefaultCertificate $true -MatchUri *.contoso.net
        
        <span data-ttu-id="66791-116">Si UseDefaultCertificate est défini sur false, vous devez spécifier les paramètres TLSCertIssuer et TLSCertSerialNumber.</span><span class="sxs-lookup"><span data-stu-id="66791-116">If UseDefaultCertificate is set to False, you must specify TLSCertIssuer and TLSCertSerialNumber parameters.</span></span> <span data-ttu-id="66791-117">Ces paramètres indiquent le nom de l’autorité de certification qui a émis le certificat utilisé dans l’itinéraire statique, ainsi que le numéro de série de ce certificat TLS, respectivement.</span><span class="sxs-lookup"><span data-stu-id="66791-117">These parameters indicate the name of the certification authority (CA) that issued the certificate used in the static route, and the serial number of that TLS certificate, respectively.</span></span> <span data-ttu-id="66791-118">Pour plus d’informations sur ces paramètres, reportez-vous à l’aide de Lync Server Management Shell en tapant ce qui suit à l’invite de commandes:</span><span class="sxs-lookup"><span data-stu-id="66791-118">For details about these parameters, see Lync Server Management Shell Help by typing the following at the command prompt:</span></span>
        
            Get-Help New-CsStaticRoute -Full
    
      - <span data-ttu-id="66791-119">Pour une connexion TCP (Transmission Control Protocol), à l’invite de commandes, tapez ce qui suit:</span><span class="sxs-lookup"><span data-stu-id="66791-119">For a Transmission Control Protocol (TCP) connection, type the following at the command prompt:</span></span>
        
        <div class="">
        

        > [!NOTE]  
        > <span data-ttu-id="66791-120">Si vous spécifiez un nom de domaine complet (FQDN, Fully Qualified Domain Name), vous devez d’abord configurer un enregistrement DNS (Domain Name System).</span><span class="sxs-lookup"><span data-stu-id="66791-120">If you specify a fully qualified domain name (FQDN), you must configure a Domain Name System (DNS) A record first.</span></span>

        
        </div>
        
            $TCPRoute = New-CsStaticRoute -TCPRoute -Destination <gateway IP address or FQDN> -Port <gateway SIP listening port> -MatchUri <destination domain>
        
        <span data-ttu-id="66791-121">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="66791-121">For example:</span></span>
        
            $TCPRoute = New-CsStaticRoute -TCPRoute -Destination 192.168.0.240 -Port 5065 -MatchUri *.contoso.net
        
        <span data-ttu-id="66791-122">Vous trouverez ci-après les valeurs par défaut des paramètres facultatifs pour les itinéraires statiques:</span><span class="sxs-lookup"><span data-stu-id="66791-122">The following are default values for optional parameters for static routes:</span></span>
        
          - <span data-ttu-id="66791-123">Activée = vrai</span><span class="sxs-lookup"><span data-stu-id="66791-123">Enabled = True</span></span>
        
          - <span data-ttu-id="66791-124">MatchOnlyPhoneUri = false</span><span class="sxs-lookup"><span data-stu-id="66791-124">MatchOnlyPhoneUri = False</span></span>
        
          - <span data-ttu-id="66791-125">ReplaceHostInRequestUri = false</span><span class="sxs-lookup"><span data-stu-id="66791-125">ReplaceHostInRequestUri = False</span></span>
        
        <span data-ttu-id="66791-126">Nous vous recommandons vivement de ne pas modifier ces valeurs par défaut.</span><span class="sxs-lookup"><span data-stu-id="66791-126">We strongly recommend that you do not change these default values.</span></span> <span data-ttu-id="66791-127">Toutefois, si vous devez modifier l’un de ces paramètres, consultez l’aide de Lync Server Management Shell en tapant ce qui suit à l’invite de commandes:</span><span class="sxs-lookup"><span data-stu-id="66791-127">However, if you must change any of these parameters, see Lync Server Management Shell Help by typing the following at the command prompt:</span></span>
        
            Get-Help New-CsStaticRoute -Full

4.  <span data-ttu-id="66791-128">Pour conserver un itinéraire statique nouvellement créé dans le magasin de gestion central, exécutez l’une des actions suivantes, selon le cas:</span><span class="sxs-lookup"><span data-stu-id="66791-128">To persist a newly created static route in the Central Management store, run one of the following, as appropriate:</span></span>
    
       ```
        Set-CsStaticRoutingConfiguration -Route @{Add=$TLSRoute}
       ```
    
       ```
        Set-CsStaticRoutingConfiguration -Route @{Add=$TCPRoute}
       ```

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="66791-129">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="66791-129">See Also</span></span>


[<span data-ttu-id="66791-130">Configuration d’une entrée d’application approuvée pour le contrôle d’appel distant dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="66791-130">Configure a trusted application entry for remote call control in Lync Server 2013</span></span>](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)  
[<span data-ttu-id="66791-131">Définition d’une adresse IP de passerelle SIP/CSTA dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="66791-131">Define a SIP/CSTA gateway IP address in Lync Server 2013</span></span>](lync-server-2013-define-a-sip-csta-gateway-ip-address.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

