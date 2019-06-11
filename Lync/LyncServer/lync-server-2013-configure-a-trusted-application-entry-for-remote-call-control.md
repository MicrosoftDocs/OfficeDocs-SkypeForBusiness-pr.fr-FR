---
title: Configuration d’une entrée d’application approuvée pour le contrôle d’appel distant
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure a trusted application entry for remote call control
ms:assetid: 37777f93-8b24-40cf-808e-7c6230eb2132
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558636(v=OCS.15)
ms:contentKeyID: 48183829
ms.date: 11/03/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: be0dda3eedc73e5c64f7c275714955f3ce92af3a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838455"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-a-trusted-application-entry-for-remote-call-control-in-lync-server-2013"></a>Configuration d’une entrée d’application approuvée pour le contrôle d’appel distant dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2015-11-02_

La passerelle SIP/CSTA doit être configurée en tant qu’application approuvée afin que Lync Server applique un itinéraire statique pour acheminer les appels vers la passerelle.

<div>


> [!IMPORTANT]
> Si vous migrez des utilisateurs à partir d’une version précédente du déploiement de Lync Server, assurez-vous que vous avez supprimé toutes les entrées d’applications approuvées (auparavant connues sous le nom d’entrées d’hébergement autorisées) que vous avez créées pour la passerelle SIP/CSTA avant de suivre les procédures décrites dans Cette rubrique. Pour plus d’informations, reportez-vous à <A href="lync-server-2013-remove-a-legacy-authorized-host-optional.md">la rubrique supprimer un ancien hôte autorisé de Lync Server 2013 (facultatif)</A>.<BR>Si vous envisagez de déployer le nouveau contrôle d’appel distant à l’aide d’une connexion TCP (Transmission Control Protocol), vous devez vérifier que <STRONG>l’utilisation du service de limitation aux adresses IP sélectionnées</STRONG> doit être définie sur les applications et les pools de confiance existants, si vous souhaitez utiliser la même Port TCP pour la nouvelle application de confiance.



</div>

<div>

## <a name="to-configure-a-trusted-application-entry-for-the-sipcsta-gateway"></a>Pour configurer une entrée d’application fiable pour la passerelle SIP/CSTA

1.  Ouvrez une session sur l’ordinateur sur lequel Lync Server Management Shell est installé en tant que membre du groupe RTCUniversalServerAdmins ou d’un rôle de contrôle d’accès basé sur un rôle (RBAC) auquel vous avez affecté l’applet **de commande New-CsTrustedApplicationPool** .

2.  Démarrez Lync Server Management Shell: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

3.  Pour créer une entrée d’application fiable, effectuez l’une des opérations suivantes:
    
      - Pour une connexion TLS (Transport Layer Security), à l’invite de commandes, tapez ce qui suit:
        
            New-CsTrustedApplicationPool -Identity <FQDN of the SIP/CSTA gateway> [-Registrar <Service ID or FQDN of the Registrar service>] -Site <Site ID for the site where you want to create the trusted application pool>
        
        Par exemple :
        
            New-CsTrustedApplicationPool -Identity rccgateway.contoso.net -Registrar registrar1.contoso.net -Site co1 -TreatAsAuthenticated $true -ThrottleAsServer $true
    
      - Pour une connexion TCP (Transmission Control Protocol), à l’invite de commandes, tapez ce qui suit:
        
            New-CsTrustedApplicationPool -Identity <IP address or FQDN of the SIP/CSTA gateway> [-Registrar <Service ID or FQDN of the Registrar service>] -Site <Site ID for the site where you want to create the trusted application pool>
        
        Par exemple :
        
            New-CsTrustedApplicationPool -Identity 192.168.0.240 -Registrar registrar1.contoso.net -Site co1 -TreatAsAuthenticated $true -ThrottleAsServer $true

4.  Pour ajouter l’application fiable au pool, effectuez l’une des opérations suivantes:
    
      - Pour une connexion TLS, à l’invite de commandes, tapez ce qui suit:
        
            New-CsTrustedApplication -ApplicationID <application name> -TrustedApplicationPoolFqdn <FQDN of the SIP/CSTA gateway> -Port <SIP listening port on the gateway>
        
        Par exemple :
        
            New-CsTrustedApplication -ApplicationID RccGateway-1 -TrustedApplicationPoolFqdn rccgateway.contoso.net -Port 5065
    
      - Pour une connexion TCP, à l’invite de commandes, tapez ce qui suit:
        
            New-CsTrustedApplication -ApplicationID <application name> -TrustedApplicationPoolFqdn <IP address or FQDN of the SIP/CSTA gateway> -Port <SIP listening port on the gateway> -EnableTcp
        
        Par exemple :
        
            New-CsTrustedApplication -ApplicationID RccGateway-1 -TrustedApplicationPoolFqdn 192.169.0.240 -Port 5065 -EnableTcp

5.  Pour implémenter les modifications publiées apportées à la topologie, à l’invite de commandes, tapez ce qui suit:
    
        Enable-CsTopology

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Configuration d’un itinéraire statique pour le contrôle d’appel distant dans Lync Server 2013](lync-server-2013-configure-a-static-route-for-remote-call-control.md)  
[Définition d’une adresse IP de passerelle SIP/CSTA dans Lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

