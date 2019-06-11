---
title: 'Lync Server 2013 : Résumé DNS - Serveur Edge consolidé mis à l’échelle, équilibrage de charge DNS avec adresses IP privées avec la conversion d’adresses réseau'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT
ms:assetid: 11bc7b84-91cf-48f9-ad0e-06ad30b46a2e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398201(v=OCS.15)
ms:contentKeyID: 48183447
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7476f258ddd70adad7f200db90b39438a19f4f84
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831367"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-in-lync-server-2013"></a>Résumé DNS - Serveur Edge consolidé mis à l’échelle, équilibrage de charge DNS avec adresses IP privées avec la conversion d’adresses réseau dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-09-08_

Les exigences d’enregistrements DNS pour l’accès distant à Lync Server 2013 sont assez simples comparées à celles des certificats et des ports. De plus, de nombreux enregistrements sont facultatifs, en fonction de la configuration des clients exécutant Lync 2013 et de la possibilité d’activer la Fédération.

Pour plus d’informations sur les exigences DNS de Lync 2013, voir [déterminer les exigences DNS pour Lync Server 2013](lync-server-2013-determine-dns-requirements.md).

Pour plus d’informations sur la configuration de la configuration automatique de clients 2013 Lync si le DNS avec fractionnement n’est pas configuré, voir la section «Configuration automatique sans le service DNS partagé» dans [déterminer les exigences DNS pour Lync Server 2013](lync-server-2013-determine-dns-requirements.md).

Le tableau suivant contient un résumé des enregistrements DNS requis pour la prise en charge de la topologie de périphérie unique consolidée illustrée dans la figure unique. Notez que certains enregistrements DNS sont requis uniquement pour la configuration automatique de clients 2013 Lync. Si vous envisagez d’utiliser des objets de stratégie de groupe pour configurer des clients Lync, les enregistrements associés ne sont pas nécessaires.

<div>

## <a name="important-edge-server-network-adapter-requirements"></a>IMPORTANT: configuration requise pour les cartes réseau du serveur Edge

Pour éviter les problèmes de routage, assurez-vous qu’il y a au moins deux cartes réseau dans vos serveurs Edge et que la passerelle par défaut est définie uniquement sur l’adaptateur réseau associé à l’interface externe. Par exemple, comme illustré dans la figure dans le scénario d’arête consolidée ajusté [, l’équilibrage de charge DNS avec des adresses IP privées utilisant tar dans Lync Server 2013](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md), la passerelle par défaut pointe vers le pare-feu externe.

Vous pouvez configurer deux cartes réseau sur chacun de votre serveur Edge comme suit:

  - **Carte réseau 1-nœud 1 (interface interne)**
    
    Interface interne avec 172.25.33.10 attribué.
    
    Aucune passerelle par défaut n’est définie.
    
    Assurez-vous qu’il existe un itinéraire du réseau contenant l’interface interne latérale vers tout réseau qui contient des serveurs exécutant Lync Server 2013 ou des clients Lync Server 2013 (par exemple, de 172.25.33.0 à 192.168.10.0).

  - **Carte réseau 1-nœud 2 (interface interne)**
    
    Interface interne avec 172.25.33.11 attribué.
    
    Aucune passerelle par défaut n’est définie.
    
    Assurez-vous qu’il existe un itinéraire du réseau contenant l’interface interne latérale vers tout réseau qui contient des serveurs exécutant Lync Server 2013 ou des clients Lync Server 2013 (par exemple, de 172.25.33.0 à 192.168.10.0).

  - **Carte réseau 2-nœud 1 (interface externe)**
    
    Trois adresses IP privées sont affectées à cette carte réseau (par exemple, 10.45.16.10 pour Access Edge, 10.45.16.20 pour les conférences Web, 10.45.16.30 pour AV Edge.
    
    <div>
    

    > [!NOTE]  
    > Il est possible, mais déconseillé, d’utiliser une seule adresse IP pour les trois interfaces de service Edge. Même si cela enregistre les adresses IP, il est nécessaire de disposer d’un numéro de port différent pour chaque service. Le numéro de port par défaut est 443/TCP, ce qui permet à la plupart des pare-feu distants d’autoriser le trafic. Le fait de changer les valeurs de port (par exemple) 5061/TCP pour le Edge d’accès, 444/TCP pour les conférences Web et 443/TCP pour le bord AV peut poser des problèmes pour les utilisateurs distants dans lesquels un pare-feu est derrière n’autorise pas le trafic de 5061/TCP et 444/TCP. Par ailleurs, trois adresses IP distinctes simplifient la résolution des problèmes en raison de la possibilité de filtrer sur l’adresse IP.

    
    </div>
    
    L’adresse IP publique d’Access Edge est principale avec passerelle par défaut définie sur le routeur intégré (10.45.16.1).
    
    Les adresses IP privées des conférences Web et des adresses IP privées d’un/V sont des adresses IP supplémentaires dans la section **avancé** des propriétés de **protocole Internet version 4 (TCP/IPv4)** et de **protocole Internet (TCP/IPv6)** de la **zone locale. Propriétés de connexion** dans Windows Server.

  - **Carte réseau 2-nœud 2 (interface externe)**
    
    Trois adresses IP privées sont affectées à cette carte réseau (par exemple, 10.45.16.11 pour Access Edge, 10.45.16.21 pour les conférences Web, 10.45.16.31 pour AV Edge.
    
    L’adresse IP publique d’Access Edge est principale avec passerelle par défaut définie sur le routeur intégré (10.45.16.1).
    
    Les adresses IP privées des conférences Web et des adresses IP privées d’un/V sont des adresses IP supplémentaires dans la section **avancé** des propriétés de **protocole Internet version 4 (TCP/IPv4)** et de **protocole Internet (TCP/IPv6)** de la **zone locale. Propriétés de connexion** dans Windows Server.

<div>


> [!TIP]  
> La configuration du serveur Edge avec deux cartes réseau est l’une des deux options suivantes. L’autre option consiste à utiliser une carte réseau pour le côté interne et trois cartes réseau pour le côté externe du serveur Edge. Le principal avantage de cette option est une carte réseau distincte par service de serveur Edge et une collection de données plus concise lorsque le dépannage est nécessaire.



</div>

### <a name="dns-records-required-for-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-example"></a>Enregistrements DNS requis pour l’équilibrage de charge DNS à l’échelle (par exemple, adresses IP privées)

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
<td><p>131.107.155.10 et 131.107.155.11</p></td>
<td><p>Accès à l’interface externe d’Access Edge (contoso) si nécessaire pour tous les domaines SIP pour lesquels Lync a activé les utilisateurs</p></td>
</tr>
<tr class="even">
<td><p>DNS/A externe</p></td>
<td><p>webcon.contoso.com</p></td>
<td><p>131.107.155.20 et 131.107.155.21</p></td>
<td><p>Interface externe de conférence Web</p></td>
</tr>
<tr class="odd">
<td><p>DNS/A externe</p></td>
<td><p>av.contoso.com</p></td>
<td><p>131.107.155.30 et 131.107.155.31</p></td>
<td><p>Interface externe A/V Edge</p></td>
</tr>
<tr class="even">
<td><p>DNS/SRV/443 externes</p></td>
<td><p>_sip._tls.contoso.com</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Interface externe d’Access Edge. Requis pour la configuration automatique de clients 2013 et Lync 2010 pour une utilisation externe. Répétez cette opération pour tous les domaines SIP pour lesquels Lync est compatible avec les utilisateurs.</p></td>
</tr>
<tr class="odd">
<td><p>DNS/SRV/5061 externes</p></td>
<td><p>_sipfederationtls._tcp.contoso.com</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Interface externe d’accès SIP. Requis pour la découverte automatique du DNS des partenaires fédérés connus sous le nom de «domaine SIP autorisé» (appelé Fédération avancée dans les versions précédentes). Répétez cette opération pour tous les domaines SIP pour lesquels Lync est compatible avec les utilisateurs.</p></td>
</tr>
<tr class="even">
<td><p>DNS interne/A</p></td>
<td><p>lsedge.contoso.net</p></td>
<td><p>172.25.33.10 et 172.25.33.11</p></td>
<td><p>Interface interne consolidée Edge</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="records-required-for-federation"></a>Enregistrements requis pour la Fédération


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
<th>FQDN</th>
<th>Enregistrement d’adresse IP/nom de domaine complet</th>
<th>Cartes sur/Commentaires</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DNS/SRV/5061 externes</p></td>
<td><p>_sipfederationtls._tcp.contoso.com</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>L’interface externe d’accès SIP SIP doit être requise pour la découverte automatique du DNS de votre Fédération par le biais d’autres partenaires de Fédération potentiels, et est désignée sous le nom de «domaines SIP autorisés» (appelé Fédération avancée dans les versions antérieures). Répétez cette opération pour tous les domaines SIP pour lesquels Lync est compatible avec les utilisateurs.</p>
<div>

> [!IMPORTANT]  
> Cet enregistrement SRV est requis pour la mobilité et le centre de suppression des notifications de transmission


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-summary--public-instant-messaging-connectivity"></a>DNS Summary-connectivité de messagerie instantanée publique


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
<td><p>Interface du service Edge d’accès</p></td>
<td><p>Accès à l’interface externe d’Access Edge (contoso) si nécessaire pour tous les domaines SIP pour lesquels Lync a activé les utilisateurs</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-summary-for-extensible-messaging-and-presence-protocol"></a>DNS Summary pour le protocole de messagerie et de présence extensible


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
<th>FQDN</th>
<th>Enregistrement d’adresse IP/nom de domaine complet</th>
<th>Cartes sur/Commentaires</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DNS externe/SRV/5269</p></td>
<td><p>_xmpp-server._tcp.contoso.com</p></td>
<td><p>xmpp.contoso.com</p></td>
<td><p>Interface externe du proxy XMPP du service Edge d’accès ou du pool Edge. Répétez cette opération pour tous les domaines SIP internes avec Lync pour les utilisateurs pour lesquels le contact avec les contacts XMPP est autorisé via la configuration de la stratégie d’accès externe par le biais d’une stratégie globale, d’une stratégie de site à l’emplacement de l’utilisateur ou d’une stratégie utilisateur appliquée au Utilisateur compatible Lync. Un domaine XMPP autorisé doit également être configuré dans la stratégie partenaires fédérés de XMPP. Pour plus d’informations, voir rubriques supplémentaires dans la <strong>section Voir aussi</strong> .</p></td>
</tr>
<tr class="even">
<td><p>DNS/A externe</p></td>
<td><p>xmpp.contoso.com (par exemple)</p></td>
<td><p>Adresse IP du service Edge d’accès sur votre serveur Edge ou pool d’hébergement de proxy XMPP</p></td>
<td><p>Pointe vers le service Edge d’accès ou le pool Edge qui héberge le service proxy XMPP. En général, l’enregistrement SRV que vous créez pointe vers cet enregistrement hôte (A ou AAAA).</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

