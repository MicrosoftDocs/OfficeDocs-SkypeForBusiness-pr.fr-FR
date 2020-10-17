---
title: 'Lync Server 2013 : configurer un itinéraire statique pour le contrôle d’appel distant'
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
ms.openlocfilehash: d773658b17d846409e303c23204f86ea1f0fce77
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48507671"
---
# <a name="configure-a-static-route-for-remote-call-control-in-lync-server-2013"></a>Configurer un itinéraire statique pour le contrôle d’appel distant dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-22_

Le contrôle d’appel distant exige que tous les pools Lync Server soient configurés avec un chemin d’accès à partir de ce pool vers la passerelle SIP/CSTA qui se connecte à l’autocommutateur privé (PBX). Ce chemin d’accès exige que chaque pool ait un itinéraire statique pour chaque passerelle vers laquelle le pool servira de proxy pour les messages de contrôle d’appel SIP associés aux appels vers le PBX. Si vous configurez un itinéraire statique global pour le contrôle d’appel distant, chaque pool qui n’est pas configuré avec un itinéraire statique au niveau du pool utilisera l’itinéraire statique global.

<div>

## <a name="to-configure-a-static-route-for-remote-call-control"></a>Pour configurer un itinéraire statique pour le contrôle d’appel distant

1.  Ouvrez une session sur un ordinateur sur lequel Lync Server Management Shell est installé en tant que membre du groupe RTCUniversalServerAdmins ou d’un rôle RBAC (contrôle d’accès basé sur un rôle) auquel vous avez affecté la cmdlet **New-CsStaticRoute** .

2.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Lync Server Management Shell**.

3.  Pour créer un itinéraire statique et le placer dans la variable $TLSRoute ou $TCPRoute, effectuez l’une des opérations suivantes :
    
    <div class="">
    

    > [!TIP]  
    > Pour faire correspondre les domaines enfants d’un domaine, vous pouvez spécifier une valeur à caractère générique dans le paramètre MatchUri. Par exemple, <STRONG>*.contoso.net</STRONG>. Cette valeur fait correspondre tout domaine se terminant par le suffixe <STRONG>contoso.net</STRONG>.

    
    </div>
    
      - Pour une connexion TLS (Transport Layer Security), tapez ce qui suit à l’invite de commandes :
        
        ```powershell
        $TLSRoute = New-CsStaticRoute -TLSRoute -Destination <gateway FQDN> -Port <gateway SIP listening port> -UseDefaultCertificate $true -MatchUri <destination domain>
        ```
        Par exemple :
        ```powershell
        $TLSRoute = New-CsStaticRoute -TLSRoute -Destination rccgateway.contoso.net -Port 5065 -UseDefaultCertificate $true -MatchUri *.contoso.net
        ```
        Si UseDefaultCertificate est défini sur False, vous devez préciser les paramètres TLSCertIssuer et TLSCertSerialNumber. Ces paramètres fournissent le nom de l’autorité de certification qui a émis le certificat utilisé dans l’itinéraire statique, et le numéro de série de ce certificat TLS, respectivement. Pour plus d’informations sur ces paramètres, reportez-vous à l’aide de Lync Server Management Shell en tapant ce qui suit à l’invite de commandes :
        ```powershell
        Get-Help New-CsStaticRoute -Full
        ```
      - Pour une connexion TCP (Transmission Control Protocol), tapez ce qui suit à l’invite de commandes :
        
        <div class="">
        

        > [!NOTE]  
        > Si vous spécifiez un nom de domaine complet (FQDN), vous devez commencer par configurer a enregistrement DNS (Domain Name System) A.

        
        </div>
        
        ```powershell
        $TCPRoute = New-CsStaticRoute -TCPRoute -Destination <gateway IP address or FQDN> -Port <gateway SIP listening port> -MatchUri <destination domain>
        ```
        Par exemple :
        ```powershell
        $TCPRoute = New-CsStaticRoute -TCPRoute -Destination 192.168.0.240 -Port 5065 -MatchUri *.contoso.net
        ```
        Les valeurs suivantes sont les valeurs par défaut des paramètres facultatifs pour les itinéraires statiques :
        
          - Enabled = True
        
          - MatchOnlyPhoneUri = False
        
          - ReplaceHostInRequestUri = False
        
        Nous vous déconseillons fortement de modifier ces valeurs par défaut. Toutefois, si vous devez modifier l’un de ces paramètres, reportez-vous à l’aide de Lync Server Management Shell en tapant ce qui suit à l’invite de commandes :
        ```powershell
        Get-Help New-CsStaticRoute -Full
        ```
4.  Pour conserver un itinéraire statique nouvellement créé dans le magasin central de gestion, exécutez l’une des opérations suivantes, selon le cas :
    
       ```powershell
        Set-CsStaticRoutingConfiguration -Route @{Add=$TLSRoute}
       ```
    
       ```powershell
        Set-CsStaticRoutingConfiguration -Route @{Add=$TCPRoute}
       ```

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Configurer une entrée d’application approuvée pour le contrôle d’appel distant dans Lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)  
[Définition d’une adresse IP de passerelle SIP/CSTA dans Lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

