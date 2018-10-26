---
title: "Lync Server 2013 : Conf. d’un itin. statique pour le contr. d’appel distant"
TOCTitle: Configuration d’un itinéraire statique pour le contrôle d’appel distant
ms:assetid: f7003023-443d-48ee-989b-71e8b0b0abbd
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg615051(v=OCS.15)
ms:contentKeyID: 49299361
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration d’un itinéraire statique pour le contrôle d’appel distant dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-09-22_

Le contrôle d’appel distant exige que chaque pool Lync Server soit configuré avec un chemin d’accès entre ce pool et la passerelle SIP/CSTA qui établisse une connexion à l’autocommutateur privé (PBX). Ce chemin d’accès exige que chaque pool ait un itinéraire statique pour chaque passerelle vers laquelle le pool servira de proxy pour les messages de contrôle d’appel SIP associés aux appels vers le PBX. Si vous configurez un itinéraire statique global pour le contrôle d’appel distant, chaque pool qui n’est pas configuré avec un itinéraire statique au niveau du pool utilisera l’itinéraire statique global.

## Pour configurer un itinéraire statique pour le contrôle d’appel distant

1.  Connectez-vous à un ordinateur sur lequel Lync Server Management Shell est installé en tant que membre du groupe RTCUniversalServerAdmins ou à un rôle de contrôle d’accès basé sur le rôle auquel vous avez affecté l’applet de commande **New-CsStaticRoute**.

2.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

3.  Pour créer un itinéraire statique et le placer dans la variable $TLSRoute ou $TCPRoute, effectuez l’une des opérations suivantes :
    
    > [!TIP]  
    > Pour faire correspondre les domaines enfants d’un domaine, vous pouvez spécifier une valeur à caractère générique dans le paramètre MatchUri. Par exemple, <strong>*.contoso.net</strong> . Cette valeur fait correspondre tout domaine se terminant par le suffixe <strong>contoso.net</strong> .    
      - Pour une connexion TLS (Transport Layer Security), tapez ce qui suit dans l’invite de commandes :
        
            $TLSRoute = New-CsStaticRoute -TLSRoute -Destination <gateway FQDN> -Port <gateway SIP listening port> -UseDefaultCertificate $true -MatchUri <destination domain>
        
        Exemple :
        
            $TLSRoute = New-CsStaticRoute -TLSRoute -Destination rccgateway.contoso.net -Port 5065 -UseDefaultCertificate $true -MatchUri *.contoso.net
        
        Si UseDefaultCertificate est défini sur False, vous devez préciser les paramètres TLSCertIssuer et TLSCertSerialNumber. Ces paramètres fournissent le nom de l’autorité de certification qui a émis le certificat utilisé dans l’itinéraire statique, et le numéro de série de ce certificat TLS, respectivement. Pour plus d’informations sur ces paramètres, reportez-vous à l’Aide de Lync Server Management Shell en tapant la commande suivante dans l’invite :
        
            Get-Help New-CsStaticRoute -Full
    
      - Pour une connexion TCP (Transmission Control Protocol), tapez ce qui suit dans l’invite de commandes :
        
        > [!NOTE]  
        > Si vous spécifiez un nom de domaine complet (FQDN), vous devez commencer par configurer a enregistrement DNS (Domain Name System) A.        
            
            
            $TCPRoute = New-CsStaticRoute -TCPRoute -Destination <gateway IP address or FQDN> -Port <gateway SIP listening port> -MatchUri <destination domain>
        
        Exemple :
        
            $TCPRoute = New-CsStaticRoute -TCPRoute -Destination 192.168.0.240 -Port 5065 -MatchUri *.contoso.net
        
        Les valeurs suivantes sont les valeurs par défaut des paramètres facultatifs pour les itinéraires statiques :
        
          - Enabled = True
        
          - MatchOnlyPhoneUri = False
        
          - ReplaceHostInRequestUri = False
        
        Nous vous déconseillons fortement de modifier ces valeurs par défaut. Cependant, si vous devez modifier l’un ou l’autre de ces paramètres, consultez l’Aide de Lync Server Management Shell en tapant la commande suivante dans l’invite :
        
            Get-Help New-CsStaticRoute -Full

4.  Pour conserver un itinéraire statique nouvellement créé dans le magasin central de gestion, effectuez l’une des opérations suivantes, selon le cas :
    
    ```
    Set-CsStaticRoutingConfiguration -Route @{Add=$TLSRoute}
    ```
    ```
    Set-CsStaticRoutingConfiguration -Route @{Add=$TCPRoute}
    ```

## Voir aussi

#### Tâches

[Configuration d’une entrée d’application approuvée pour le contrôle d’appel distant dans Lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)  
[Définition d’une adresse IP de passerelle SIP/CSTA dans Lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md)

