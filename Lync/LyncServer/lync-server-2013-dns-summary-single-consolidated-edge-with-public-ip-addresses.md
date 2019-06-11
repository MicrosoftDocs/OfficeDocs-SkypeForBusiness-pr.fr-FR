---
title: Résumé des enregistrements DNS - Serveur Edge unique consolidé avec adresses IP publiques
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS summary - Single consolidated edge with public IP addresses
ms:assetid: 7b83eae4-aa1a-4cc6-8077-42176d56cab5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205025(v=OCS.15)
ms:contentKeyID: 48184601
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 50aae14309e55919eb3f65560cd7cd0e7f1b1283
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831351"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---single-consolidated-edge-with-public-ip-addresses-in-lync-server-2013"></a>Résumé des enregistrements DNS - Serveur Edge unique consolidé avec adresses IP publiques dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2017-03-09_

Les exigences d’enregistrements DNS pour l’accès distant à Lync Server 2013 sont assez simples comparées à celles des certificats et des ports. De plus, de nombreux enregistrements sont facultatifs, en fonction de la configuration des clients exécutant Lync 2013 et de la possibilité d’activer la Fédération.

Pour plus d’informations sur les exigences DNS de Lync 2013, voir [déterminer les exigences DNS pour Lync Server 2013](lync-server-2013-determine-dns-requirements.md).

Pour plus d’informations sur la configuration automatique des clients exécutant Lync 2013 si le DNS fractionné-Brain n’est pas configuré, voir «Configuration automatique sans DNS fractionné-Brain» dans [déterminer les exigences DNS pour Lync Server 2013](lync-server-2013-determine-dns-requirements.md).

Le tableau suivant contient un résumé des enregistrements DNS requis pour la prise en charge de la topologie de périphérie unique consolidée illustrée dans la figure unique. Notez que certains enregistrements DNS sont requis uniquement pour la configuration automatique de clients 2013 et Lync 2010. Si vous envisagez d’utiliser des objets de stratégie de groupe pour configurer des clients Lync, les enregistrements de configuration automatique associés ne sont pas nécessaires.

<div>

## <a name="important-edge-server-network-adapter-requirements"></a>IMPORTANT: configuration requise pour les cartes réseau du serveur Edge

Pour éviter les problèmes de routage, assurez-vous qu’il y a au moins deux cartes réseau dans vos serveurs Edge et que la passerelle par défaut est définie uniquement sur l’adaptateur réseau associé à l’interface externe. Par exemple, comme indiqué dans la topologie de périphérie consolidée unique avec des adresses IP publiques, figure dans [une frontière consolidée unique avec des adresses IP publiques dans Lync Server 2013](lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md), la passerelle par défaut pointe vers le routeur externe de votre périmètre Internet ou un pare-feu qui peut fournir une adresse IP publique. La relation réseau pour les interfaces du serveur Edge est une relation de routage au lieu d’une relation NAT.

Vous pouvez configurer deux cartes réseau sur votre serveur Edge comme suit:

  - **Carte réseau 1 (interface interne)**
    
    Interface interne avec 172.25.33.10 attribué.
    
    Aucune passerelle par défaut n’est définie.
    
    Assurez-vous qu’il existe un itinéraire du réseau contenant l’interface interne latérale vers tout réseau qui contient des serveurs exécutant Lync Server 2013 ou des clients Lync Server 2013 (par exemple, de 172.25.33.0 à 192.168.10.0).

  - **Carte réseau 2 (interface externe)**
    
    Trois adresses IP publiques sont affectées à cette carte réseau (par exemple, 131.107.155.10 pour Access Edge, 131.107.155.20 pour les conférences Web, 131.107.155.30 pour AV Edge.
    
    <div>
    

    > [!NOTE]
    > Il est possible, mais déconseillé, d’utiliser une seule adresse IP pour les trois interfaces de service Edge. Même si cela enregistre les adresses IP, il est nécessaire de disposer d’un numéro de port différent pour chaque service. Le numéro de port par défaut est 443/TCP, ce qui permet à la plupart des pare-feu distants d’autoriser le trafic. Le fait de changer les valeurs de port (par exemple) 5061/TCP pour le Edge d’accès, 444/TCP pour les conférences Web et 443/TCP pour le bord AV peut poser des problèmes pour les utilisateurs distants dans lesquels un pare-feu est derrière n’autorise pas le trafic de 5061/TCP et 444/TCP. Par ailleurs, trois adresses IP distinctes simplifient la résolution des problèmes en raison de la possibilité de filtrer sur l’adresse IP.

    
    </div>
    
    L’adresse IP publique d’Access Edge est principale avec passerelle par défaut définie sur le routeur public (131.107.155.1).
    
    Les adresses IP publiques de conférences Web et de réseaux A/V constituent des adresses IP supplémentaires dans la section **avancé** des propriétés de **protocole Internet version 4 (TCP/IPv4)** et de **protocole Internet (TCP/IPv6)** de la **zone locale. Propriétés de connexion** dans Windows Server.

<div>


> [!TIP]
> La configuration du serveur Edge avec deux cartes réseau est l’une des deux options suivantes. L’autre option consiste à utiliser une carte réseau pour le côté interne et trois cartes réseau pour le côté externe du serveur Edge. Le principal avantage de cette option est une carte réseau distincte par service de serveur Edge et une collection de données plus concise lorsque le dépannage est nécessaire.



</div>

### <a name="dns-records-required-for-single-consolidated-edge-with-public-ip-addresses-example"></a>Enregistrements DNS requis pour une seule périphérie consolidée avec des adresses IP publiques (exemple)

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
<td><p>Accès à l’interface externe d’Access Edge (contoso) si nécessaire pour tous les domaines SIP pour lesquels Lync a activé les utilisateurs</p></td>
</tr>
<tr class="even">
<td><p>DNS/A externe</p></td>
<td><p>webcon.contoso.com</p></td>
<td><p>131.107.155.20</p></td>
<td><p>Interface externe de conférence Web</p></td>
</tr>
<tr class="odd">
<td><p>DNS/A externe</p></td>
<td><p>av.contoso.com</p></td>
<td><p>131.107.155.30</p></td>
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
<td><p>Interface externe de l’accès SIP SIP requise pour la détection automatique de DNS des partenaires fédérés connus sous le nom de «domaine SIP autorisé» (appelé Fédération avancée dans les versions précédentes). Répétez cette opération pour tous les domaines SIP pour lesquels Lync est compatible avec les utilisateurs.</p></td>
</tr>
<tr class="even">
<td><p>DNS interne/A</p></td>
<td><p>lsedge.contoso.net</p></td>
<td><p>172.25.33.10</p></td>
<td><p>Interface interne consolidée Edge</p></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]
> Les enregistrements répertoriés dans le tableau précédent sont affichés avec une extension <EM>.net</EM> ou une extension <EM>. com</EM> afin de mettre en évidence la zone dans laquelle ils doivent résider si vous n’utilisez pas le DNS fractionné-Brain. Si vous utilisez un système de contrôle DNS à Split-Brain, tous les enregistrements se trouvent dans la même zone, à la seule différence qu’il s’agit de la version interne ou externe. Pour plus d’informations, consultez la section «DNS split-brain» dans <A href="lync-server-2013-determine-dns-requirements.md">déterminer les exigences DNS pour Lync Server 2013</A>.



</div>

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



> [!IMPORTANT]
> Cet enregistrement SRV est requis pour la mobilité et le centre de suppression des notifications de transmission

</td>
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

