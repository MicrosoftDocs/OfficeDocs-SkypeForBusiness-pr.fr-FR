---
title: Résumé des enregistrements DNS - Serveur Edge consolidé mis à l’échelle avec des équilibreurs de charge matérielle
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS summary - Scaled consolidated edge with hardware load balancers
ms:assetid: 8453297c-da1d-4b9e-a37e-6721458c6feb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398670(v=OCS.15)
ms:contentKeyID: 48184700
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d411b004edde96314e3c06d7f28a9f9d294688ad
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831353"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---scaled-consolidated-edge-with-hardware-load-balancers-in-lync-server-2013"></a>Résumé des enregistrements DNS - Serveur Edge consolidé mis à l’échelle avec des équilibreurs de charge matérielle dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-01-27_

Les exigences d’enregistrements DNS pour l’accès distant à Lync Server 2013 sont assez simples comparées à celles des certificats et des ports. De plus, de nombreux enregistrements sont facultatifs, en fonction de la configuration des clients exécutant Lync 2013 et de la possibilité d’activer la Fédération.

Pour plus d’informations sur les exigences DNS de Lync 2013, voir [déterminer les exigences DNS pour Lync Server 2013](lync-server-2013-determine-dns-requirements.md).

Pour plus d’informations sur la configuration de la configuration automatique de clients 2013 Lync si le DNS avec fractionnement n’est pas configuré, voir la section «Configuration automatique sans le service DNS partagé» dans [déterminer les exigences DNS pour Lync Server 2013](lync-server-2013-determine-dns-requirements.md).

Le tableau suivant contient un résumé des enregistrements DNS qui sont requis pour prendre en charge la figure de topologie de frontière consolidée à l’échelle (équilibrage de charge matérielle). Notez que certains enregistrements DNS sont requis uniquement pour la configuration automatique pour les clients Lync. Si vous envisagez d’utiliser des objets de stratégie de groupe pour configurer des clients Lync, les enregistrements associés ne sont pas nécessaires.

<div>

## <a name="important-edge-server-network-adapter-requirements"></a>IMPORTANT: configuration requise pour les cartes réseau du serveur Edge

Pour éviter les problèmes de routage, assurez-vous qu’il y a au moins deux cartes réseau dans vos serveurs Edge et que la passerelle par défaut est définie uniquement sur l’adaptateur réseau associé à l’interface externe. Par exemple, comme illustré dans la figure dans le cadre de la configuration consolidée de l’option frontière consolidée à l’échelle de l’application, le [2013 serveur](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md)passerelle par défaut pointe vers le pare-feu externe.

Vous pouvez configurer deux cartes réseau sur chaque serveur Edge comme suit:

  - **Carte réseau 1 (interface interne)**
    
    Interface interne avec 172.25.33.10 attribué.
    
    Aucune passerelle par défaut.
    
    Assurez-vous qu’il existe un itinéraire à partir du réseau contenant l’interface interne du serveur Edge vers les réseaux contenant des clients Lync Server ou des serveurs exécutant Lync Server (par exemple, de 172.25.33.0 à 192.168.10.0).

  - **Carte réseau 2 (interface externe)**
    
    Trois adresses IP publiques sont attribuées à cette carte réseau (par exemple, 131.107.155.10 pour le service Edge d’Access 131.107.155.20 pour le service Edge de conférence Web, 131.107.155.30 pour les services Edge A/V.
    
    <div>
    

    > [!NOTE]
    > Les adresses IP affectées aux interfaces du réseau externe réel du serveur Edge peuvent dépendre du ou des équilibreurs de charge matérielle que vous choisissez. Reportez-vous à la documentation de votre équilibrage de charge matérielle pour comprendre les exigences réelles de l’adresse IP.<BR>Il est possible, mais déconseillé, d’utiliser une seule adresse IP pour les trois interfaces de service Edge. Même si cela enregistre les adresses IP, il est nécessaire de disposer d’un numéro de port différent pour chaque service. Le numéro de port par défaut est 443/TCP, ce qui permet à la plupart des pare-feu distants d’autoriser le trafic. La modification des valeurs de port à (par exemple) 5061/TCP pour le service Edge d’accès, 444/TCP pour le service Edge de conférence Web et 443/TCP pour le service Edge A/V, peut poser des problèmes pour les utilisateurs distants dans lesquels un pare-feu est derrière n’autorise pas le trafic 5061/TCP et 444/TCP. Par ailleurs, trois adresses IP distinctes simplifient la résolution des problèmes en raison de la possibilité de filtrer sur l’adresse IP.

    
    </div>
    
    L’adresse IP du service Edge d’accès est principale avec la passerelle par défaut définie sur routeur Internet (131.107.155.1).
    
    Service de conférence Web et adresses IP de service Edge/V

<div>


> [!TIP]
> La configuration du serveur Edge avec deux cartes réseau est l’une des deux options suivantes. L’autre option consiste à utiliser une carte réseau pour le côté interne et trois cartes réseau pour le côté externe du serveur Edge. Le principal avantage de cette option est une carte réseau distincte par service de serveur Edge et une collection de données plus concise lorsque le dépannage est nécessaire.



</div>

### <a name="dns-records-required-for-scaled-consolidated-edge-hardware-load-balanced-example"></a>Enregistrements DNS requis pour le contour consolidé mis à l’échelle (exemple)

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Emplacement/TYPE/port</th>
<th>Nom de domaine complet/enregistrement DNS</th>
<th>IP address/FQDN</th>
<th>Cartes sur/Commentaires</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DNS/A externe</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>131.107.155.10</p></td>
<td><p>Interface externe du Service Access Edge (contoso). Répétez cette opération pour tous les domaines SIP pour lesquels Lync est compatible avec les utilisateurs.</p></td>
</tr>
<tr class="even">
<td><p>DNS/A externe</p></td>
<td><p>webcon.contoso.com</p></td>
<td><p>131.107.155.20</p></td>
<td><p>Interface externe du service de conférence Web</p></td>
</tr>
<tr class="odd">
<td><p>DNS/A externe</p></td>
<td><p>av.contoso.com</p></td>
<td><p>131.107.155.30</p></td>
<td><p>Interface externe du service A/V Edge</p></td>
</tr>
<tr class="even">
<td><p>DNS/SRV/443 externes</p></td>
<td><p>_sip._tls.contoso.com</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Interface externe du service Edge d’accès. Requis pour la configuration automatique de clients 2013 et Lync 2010 pour une utilisation externe. Répétez cette opération pour tous les domaines SIP pour lesquels Lync est compatible avec les utilisateurs.</p></td>
</tr>
<tr class="odd">
<td><p>DNS/SRV/5061 externes</p></td>
<td><p>_sipfederationtls._tcp.contoso.com</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Interface externe du service d’accès au serveur SIP requis pour la détection automatique de DNS des partenaires fédérés connus sous le nom de «domaine SIP autorisé» (appelé Fédération avancée dans les versions précédentes). Répétez cette opération pour tous les domaines SIP avec des utilisateurs compatibles Lync et des clients mobiles Microsoft Lync qui utilisent le service de notifications d’émission ou le service de notifications de transmission d’Apple.</p></td>
</tr>
<tr class="even">
<td><p>DNS interne/A</p></td>
<td><p>lsedge.contoso.net</p></td>
<td><p>172.25.33.10</p></td>
<td><p>Interface interne consolidée Edge</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

