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

# <a name="configure-a-static-route-for-remote-call-control-in-lync-server-2013"></a>Configuration d’un itinéraire statique pour le contrôle d’appel distant dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-09-22_

Le contrôle d’appel distant nécessite que chaque pool de serveurs Lync soit configuré avec un chemin d’accès de ce pool à la passerelle SIP/CSTA qui se connecte au PBX (Private Branch Exchange). Ce chemin d’accès nécessite que chaque pool dispose d’un itinéraire statique pour chaque passerelle vers laquelle le pool fera proxy les messages de contrôle d’appel SIP associés aux appels au PBX. Si vous configurez un itinéraire statique global pour le contrôle d’appel distant, chaque pool qui n’est pas configuré avec un itinéraire statique au niveau du pool utilisera l’itinéraire statique global.

<div>

## <a name="to-configure-a-static-route-for-remote-call-control"></a>Pour configurer un itinéraire statique pour le contrôle d’appel distant

1.  Connectez-vous à un ordinateur sur lequel Lync Server Management Shell est installé en tant que membre du groupe RTCUniversalServerAdmins ou d’un rôle de contrôle d’accès basé sur un rôle (RBAC) auquel vous avez affecté l’applet **de commande New-CsStaticRoute** .

2.  Démarrez Lync Server Management Shell: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

3.  Pour créer un itinéraire statique et le placer dans la variable $TLSRoute ou $TCPRoute, effectuez l’une des opérations suivantes:
    
    <div class="">
    

    > [!TIP]  
    > Pour correspondre aux domaines enfants d’un domaine, vous pouvez spécifier une valeur de caractère générique dans le paramètre MatchUri. Par exemple, <STRONG>*. contoso.net</STRONG>. Cette valeur correspond à tout domaine se terminant par le suffixe <STRONG>contoso.net</STRONG>.

    
    </div>
    
      - Pour une connexion TLS (Transport Layer Security), à l’invite de commandes, tapez ce qui suit:
        
            $TLSRoute = New-CsStaticRoute -TLSRoute -Destination <gateway FQDN> -Port <gateway SIP listening port> -UseDefaultCertificate $true -MatchUri <destination domain>
        
        Par exemple :
        
            $TLSRoute = New-CsStaticRoute -TLSRoute -Destination rccgateway.contoso.net -Port 5065 -UseDefaultCertificate $true -MatchUri *.contoso.net
        
        Si UseDefaultCertificate est défini sur false, vous devez spécifier les paramètres TLSCertIssuer et TLSCertSerialNumber. Ces paramètres indiquent le nom de l’autorité de certification qui a émis le certificat utilisé dans l’itinéraire statique, ainsi que le numéro de série de ce certificat TLS, respectivement. Pour plus d’informations sur ces paramètres, reportez-vous à l’aide de Lync Server Management Shell en tapant ce qui suit à l’invite de commandes:
        
            Get-Help New-CsStaticRoute -Full
    
      - Pour une connexion TCP (Transmission Control Protocol), à l’invite de commandes, tapez ce qui suit:
        
        <div class="">
        

        > [!NOTE]  
        > Si vous spécifiez un nom de domaine complet (FQDN, Fully Qualified Domain Name), vous devez d’abord configurer un enregistrement DNS (Domain Name System).

        
        </div>
        
            $TCPRoute = New-CsStaticRoute -TCPRoute -Destination <gateway IP address or FQDN> -Port <gateway SIP listening port> -MatchUri <destination domain>
        
        Par exemple :
        
            $TCPRoute = New-CsStaticRoute -TCPRoute -Destination 192.168.0.240 -Port 5065 -MatchUri *.contoso.net
        
        Vous trouverez ci-après les valeurs par défaut des paramètres facultatifs pour les itinéraires statiques:
        
          - Activée = vrai
        
          - MatchOnlyPhoneUri = false
        
          - ReplaceHostInRequestUri = false
        
        Nous vous recommandons vivement de ne pas modifier ces valeurs par défaut. Toutefois, si vous devez modifier l’un de ces paramètres, consultez l’aide de Lync Server Management Shell en tapant ce qui suit à l’invite de commandes:
        
            Get-Help New-CsStaticRoute -Full

4.  Pour conserver un itinéraire statique nouvellement créé dans le magasin de gestion central, exécutez l’une des actions suivantes, selon le cas:
    
       ```
        Set-CsStaticRoutingConfiguration -Route @{Add=$TLSRoute}
       ```
    
       ```
        Set-CsStaticRoutingConfiguration -Route @{Add=$TCPRoute}
       ```

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Configuration d’une entrée d’application approuvée pour le contrôle d’appel distant dans Lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)  
[Définition d’une adresse IP de passerelle SIP/CSTA dans Lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

