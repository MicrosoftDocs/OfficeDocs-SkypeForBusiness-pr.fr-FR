---
title: "Lync Server 2013 : Conf. d’une entrée d’app. Appr. pr contrôle d’appel distant"
TOCTitle: Configuration d’une entrée d’application approuvée pour le contrôle d’appel distant
ms:assetid: 37777f93-8b24-40cf-808e-7c6230eb2132
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg558636(v=OCS.15)
ms:contentKeyID: 49296870
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration d’une entrée d’application approuvée pour le contrôle d’appel distant dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-11-02_

Vous devez configurer la passerelle SIP/CSTA en tant qu’application approuvée pour que Lync Server achemine les appels vers la passerelle au moyen d’un itinéraire statique.

> [!IMPORTANT]  
> Si vous effectuez une migration d’utilisateurs à partir d’une version précédente du déploiement Lync Server, vérifiez que vous avez supprimé toutes les entrées d’applications approuvées existantes (auparavant appelées entrées d’hôtes autorisés) que vous aviez créées pour la passerelle SIP/CSTA avant d’appliquer la procédure indiquée dans cette rubrique. Pour plus d’informations, reportez-vous à <a href="lync-server-2013-remove-a-legacy-authorized-host-optional.md">Suppression d’un hôte autorisé hérité dans Lync Server 2013 (facultatif)</a>.

## Pour configurer une entrée d’application approuvée pour la passerelle SIP/CSTA

1.  Ouvrez une session sur l’ordinateur sur lequel Lync Server Management Shell est installé en tant que membre du groupe RTCUniversalServerAdmins ou un rôle de contrôle d’accès basé sur un rôle (RBAC) auquel vous avez affecté l’applet de commande **New-CsTrustedApplicationPool**.

2.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

3.  Pour créer une entrée d’application approuvée, procédez comme suit :
    
      - Pour une connexion TLS (Transport Layer Security), tapez ce qui suit dans l’invite de commandes :
        
            New-CsTrustedApplicationPool -Identity <FQDN of the SIP/CSTA gateway> [-Registrar <Service ID or FQDN of the Registrar service>] -Site <Site ID for the site where you want to create the trusted application pool>
        
        Exemple :
        
            New-CsTrustedApplicationPool -Identity rccgateway.contoso.net -Registrar registrar1.contoso.net -Site co1 -TreatAsAuthenticated $true -ThrottleAsServer $true
    
      - Pour une connexion TCP (Transmission Control Protocol), tapez ce qui suit dans l’invite de commandes :
        
            New-CsTrustedApplicationPool -Identity <IP address or FQDN of the SIP/CSTA gateway> [-Registrar <Service ID or FQDN of the Registrar service>] -Site <Site ID for the site where you want to create the trusted application pool>
        
        Exemple :
        
            New-CsTrustedApplicationPool -Identity 192.168.0.240 -Registrar registrar1.contoso.net -Site co1 -TreatAsAuthenticated $true -ThrottleAsServer $true

4.  Pour ajouter l’application approuvée au pool, procédez de l’une des manières suivantes :
    
      - Pour une connexion TLS, tapez ce qui suit dans l’invite de commandes :
        
            New-CsTrustedApplication -ApplicationID <application name> -TrustedApplicationPoolFqdn <FQDN of the SIP/CSTA gateway> -Port <SIP listening port on the gateway>
        
        Exemple :
        
            New-CsTrustedApplication -ApplicationID RccGateway-1 -TrustedApplicationPoolFqdn rccgateway.contoso.net -Port 5065
    
      - Pour une connexion TCP, tapez ce qui suit dans l’invite de commandes :
        
            New-CsTrustedApplication -ApplicationID <application name> -TrustedApplicationPoolFqdn <IP address or FQDN of the SIP/CSTA gateway> -Port <SIP listening port on the gateway> -EnableTcp
        
        Exemple :
        
            New-CsTrustedApplication -ApplicationID RccGateway-1 -TrustedApplicationPoolFqdn 192.169.0.240 -Port 5065 -EnableTcp

5.  Pour implémenter les modifications publiées que vous avez apportées à la topologie, tapez ce qui suit dans l’invite de commandes :
    
        Enable-CsTopology

## Voir aussi

#### Tâches

[Configuration d’un itinéraire statique pour le contrôle d’appel distant dans Lync Server 2013](lync-server-2013-configure-a-static-route-for-remote-call-control.md)  
[Définition d’une adresse IP de passerelle SIP/CSTA dans Lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md)

