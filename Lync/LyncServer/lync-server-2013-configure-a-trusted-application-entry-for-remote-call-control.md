---
title: Configurer une entrée d’application approuvée pour le contrôle d’appel distant
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure a trusted application entry for remote call control
ms:assetid: 37777f93-8b24-40cf-808e-7c6230eb2132
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558636(v=OCS.15)
ms:contentKeyID: 48183829
ms.date: 11/03/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0135d26f0483b10752c8a823fdbda15ab9ba37b0
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205220"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-a-trusted-application-entry-for-remote-call-control-in-lync-server-2013"></a>Configurer une entrée d’application approuvée pour le contrôle d’appel distant dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2015-11-02_

La passerelle SIP/CSTA doit être configurée en tant qu’application approuvée afin de permettre à Lync Server d’appliquer un itinéraire statique pour acheminer les appels vers la passerelle.

<div>


> [!IMPORTANT]
> Si vous migrez des utilisateurs à partir d’une version précédente du déploiement Lync Server, veillez à supprimer toutes les entrées d’applications approuvées existantes (précédemment connues sous le nom d’entrées d’hôte autorisé) créées pour la passerelle SIP/CSTA avant de suivre les procédures décrites dans cette rubrique. Pour plus d’informations, consultez <A href="lync-server-2013-remove-a-legacy-authorized-host-optional.md">la rubrique supprimer un hôte autorisé hérité dans Lync Server 2013 (facultatif)</A>.<BR>Si vous envisagez de déployer un nouveau contrôle d’appel distant à l’aide d’une connexion TCP (Transmission Control Protocol), vous devez vérifier que la <STRONG>limite d’utilisation des services aux adresses IP sélectionnées</STRONG> doit être définie sur des pools et des applications approuvées existantes, si vous voulez utiliser le même port TCP pour la nouvelle application approuvée.



</div>

<div>

## <a name="to-configure-a-trusted-application-entry-for-the-sipcsta-gateway"></a>Pour configurer une entrée d’application approuvée pour la passerelle SIP/CSTA

1.  Ouvrez une session sur l’ordinateur sur lequel Lync Server Management Shell est installé en tant que membre du groupe RTCUniversalServerAdmins ou d’un rôle RBAC (contrôle d’accès basé sur un rôle) auquel vous avez affecté la cmdlet **New-CsTrustedApplicationPool** .

2.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Lync Server Management Shell**.

3.  Pour créer une entrée d’application approuvée, procédez comme suit :
    
      - Pour une connexion TLS (Transport Layer Security), tapez ce qui suit à l’invite de commandes :
        
            New-CsTrustedApplicationPool -Identity <FQDN of the SIP/CSTA gateway> [-Registrar <Service ID or FQDN of the Registrar service>] -Site <Site ID for the site where you want to create the trusted application pool>
        
        Par exemple :
        
            New-CsTrustedApplicationPool -Identity rccgateway.contoso.net -Registrar registrar1.contoso.net -Site co1 -TreatAsAuthenticated $true -ThrottleAsServer $true
    
      - Pour une connexion TCP (Transmission Control Protocol), tapez ce qui suit à l’invite de commandes :
        
            New-CsTrustedApplicationPool -Identity <IP address or FQDN of the SIP/CSTA gateway> [-Registrar <Service ID or FQDN of the Registrar service>] -Site <Site ID for the site where you want to create the trusted application pool>
        
        Par exemple :
        
            New-CsTrustedApplicationPool -Identity 192.168.0.240 -Registrar registrar1.contoso.net -Site co1 -TreatAsAuthenticated $true -ThrottleAsServer $true

4.  Pour ajouter l’application approuvée au pool, procédez de l’une des manières suivantes :
    
      - Pour une connexion TLS, tapez ce qui suit à l’invite de commandes :
        
            New-CsTrustedApplication -ApplicationID <application name> -TrustedApplicationPoolFqdn <FQDN of the SIP/CSTA gateway> -Port <SIP listening port on the gateway>
        
        Par exemple :
        
            New-CsTrustedApplication -ApplicationID RccGateway-1 -TrustedApplicationPoolFqdn rccgateway.contoso.net -Port 5065
    
      - Pour une connexion TCP, tapez ce qui suit à l’invite de commandes :
        
            New-CsTrustedApplication -ApplicationID <application name> -TrustedApplicationPoolFqdn <IP address or FQDN of the SIP/CSTA gateway> -Port <SIP listening port on the gateway> -EnableTcp
        
        Par exemple :
        
            New-CsTrustedApplication -ApplicationID RccGateway-1 -TrustedApplicationPoolFqdn 192.169.0.240 -Port 5065 -EnableTcp

5.  Pour implémenter les modifications publiées que vous avez apportées à la topologie, tapez ce qui suit à l’invite de commandes :
    
        Enable-CsTopology

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Configurer un itinéraire statique pour le contrôle d’appel distant dans Lync Server 2013](lync-server-2013-configure-a-static-route-for-remote-call-control.md)  
[Définition d’une adresse IP de passerelle SIP/CSTA dans Lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

