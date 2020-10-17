---
title: 'Lync Server 2013 : Résumé des enregistrements DNS-serveur Edge consolidé ajusté, équilibrage de charge DNS avec adresses IP privées à l’aide de la traduction d’adresses réseau'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT
ms:assetid: 11bc7b84-91cf-48f9-ad0e-06ad30b46a2e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398201(v=OCS.15)
ms:contentKeyID: 48183447
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 269d5a687baba53ed0bd60d4854b79643f23f0e0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532121"
---
# <a name="dns-summary---scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-in-lync-server-2013"></a>Résumé DNS-serveur Edge consolidé ajusté, équilibrage de charge DNS avec adresses IP privées à l’aide de la conversion d’adresses réseau dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-08_

Les exigences liées aux enregistrements DNS pour l’accès à distance à Lync Server 2013 sont relativement simples par rapport à celles des certificats et des ports. De plus, de nombreux enregistrements sont facultatifs, en fonction de la configuration des clients exécutant Lync 2013 et de l’activation de la Fédération.

Pour plus d’informations sur les exigences DNS de Lync 2013, voir [determine DNS Requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).

Pour plus d’informations sur la configuration automatique des clients Lync 2013 si le DNS split-brain n’est pas configuré, consultez la section « Configuration automatique sans DNS split brain » dans [determine DNS Requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).

Le tableau suivant contient un résumé des enregistrements DNS requis pour prendre en charge la topologie Edge consolidée indiquée dans la figure Topologie Edge consolidée unique. Notez que certains enregistrements DNS sont requis uniquement pour la configuration automatique des clients Lync 2013. Si vous envisagez d’utiliser des objets de stratégie de groupe (GPO) pour configurer des clients Lync, les enregistrements associés ne sont pas nécessaires.

<div>

## <a name="important-edge-server-network-adapter-requirements"></a>IMPORTANT : configuration requise pour la carte réseau de serveur Edge

Pour éviter les problèmes de routage, vérifiez qu’il y a au moins deux cartes réseau dans vos serveurs Edge et que la passerelle par défaut est définie uniquement sur la carte réseau associée à l’interface externe. Par exemple, comme illustré dans la figure du scénario de serveur Edge consolidé ajusté dans le [serveur Edge consolidé ajusté, l’équilibrage de charge DNS avec des adresses IP privées utilisant la conversion d’adresses réseau dans Lync Server 2013](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md), la passerelle par défaut pointerait vers le pare-feu externe.

Vous pouvez configurer deux cartes réseau dans chacun de vos serveurs Edge comme suit :

  - **Carte réseau 1 - nœud 1 (interface interne)**
    
    Interface interne avec 172.25.33.10 affecté.
    
    Aucune passerelle par défaut n’est définie.
    
    Assurez-vous qu’il existe un itinéraire entre le réseau contenant l’interface interne Edge et les réseaux qui contiennent des serveurs exécutant des clients Lync Server 2013 ou Lync Server 2013 (par exemple, de 172.25.33.0 à 192.168.10.0).

  - **Carte réseau 1 - nœud 2 (interface interne)**
    
    Interface interne avec 172.25.33.11 affecté.
    
    Aucune passerelle par défaut n’est définie.
    
    Assurez-vous qu’il existe un itinéraire entre le réseau contenant l’interface interne Edge et les réseaux qui contiennent des serveurs exécutant des clients Lync Server 2013 ou Lync Server 2013 (par exemple, de 172.25.33.0 à 192.168.10.0).

  - **Carte réseau 2 - nœud 1 (interface externe)**
    
    Trois adresses IP privées sont attribuées à cette carte réseau, par exemple 10.45.16.10 pour le serveur Edge d’accès, 10.45.16.20 pour la conférence Web, et 10.45.16.30 pour le serveur Edge AV.
    
    <div>
    

    > [!NOTE]  
    > Il est possible, mais déconseillé, d’utiliser une adresse IP unique pour les interfaces des trois services Edge. Bien que les adresses IP soient enregistrées, les numéros de port doivent être différents pour chaque service. Le numéro de port par défaut est 443/TCP, ce qui permet de s’assurer que la plupart des pare-feu distants autoriseront le trafic. Le fait d’affecter aux ports les valeurs 5061/TCP pour le service Edge d’accès, 444/TCP pour le service Edge de conférence web et 443/TCP pour le service Edge A/V, par exemple, peut générer des problèmes pour les utilisateurs distants se trouvant derrière un pare-feu qui n’autorise pas le trafic sur 5061/TCP et 444/TCP. Par ailleurs, l’utilisation de trois adresses IP distinctes facilite le dépannage puisqu’il est possible d’appliquer un filtre selon l’adresse IP.

    
    </div>
    
    L’adresse IP publique du serveur Edge d’accès est principale avec la passerelle par défaut définie sur le routeur intégré (10.45.16.1).
    
    Les adresses IP privées de conférence Web et de serveur Edge A/V sont des adresses IP supplémentaires dans la section **avancé** des propriétés du **protocole Internet version 4 (TCP/IPv4)** et du **protocole Internet version 6 (TCP/IPv6)** des **Propriétés de connexion au réseau local** dans Windows Server.

  - **Carte réseau 2 - nœud 2 (interface externe)**
    
    Trois adresses IP privées sont attribuées à cette carte réseau, par exemple 10.45.16.11 pour le serveur Edge d’accès, 10.45.16.21 pour la conférence Web, 10.45.16.31 pour le serveur Edge AV.
    
    L’adresse IP publique du serveur Edge d’accès est principale avec la passerelle par défaut définie sur le routeur intégré (10.45.16.1).
    
    Les adresses IP privées de conférence Web et de serveur Edge A/V sont des adresses IP supplémentaires dans la section **avancé** des propriétés du **protocole Internet version 4 (TCP/IPv4)** et du **protocole Internet version 6 (TCP/IPv6)** des **Propriétés de connexion au réseau local** dans Windows Server.

<div>


> [!TIP]  
> La configuration du serveur Edge avec deux cartes réseau est l’une des deux options. L’autre option consiste à utiliser une carte réseau pour le côté interne et trois cartes réseau pour le côté externe du serveur Edge. Le principal avantage de cette option est une carte réseau distincte par serveur de serveur Edge et une collecte de données potentiellement plus concise lorsque la résolution des problèmes est nécessaire.



</div>

### <a name="dns-records-required-for-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-example"></a>Enregistrements DNS requis pour le serveur Edge consolidé ajusté, équilibrage de charge DNS avec adresses IP privées à l’aide de l’interface NAT (exemple)

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
<th>Adresse IP/Nom de domaine complet</th>
<th>Mappage à/Commentaires</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DNS externe/A</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>131.107.155.10 et 131.107.155.11</p></td>
<td><p>Interface externe du serveur Edge d’accès (Contoso). Répétez si nécessaire pour tous les domaines SIP avec des utilisateurs prenant en charge Lync.</p></td>
</tr>
<tr class="even">
<td><p>DNS externe/A</p></td>
<td><p>webcon.contoso.com</p></td>
<td><p>131.107.155.20 et 131.107.155.21</p></td>
<td><p>Interface externe de serveur Edge de conférence web</p></td>
</tr>
<tr class="odd">
<td><p>DNS externe/A</p></td>
<td><p>av.contoso.com</p></td>
<td><p>131.107.155.30 et 131.107.155.31</p></td>
<td><p>Interface externe de serveur Edge A/V</p></td>
</tr>
<tr class="even">
<td><p>DNS externe/SRV/443</p></td>
<td><p>_sip _sip._tls. contoso. com</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Interface externe du serveur Edge d’accès. Nécessaire pour que la configuration automatique des clients Lync 2013 et Lync 2010 fonctionne en externe. Répétez si nécessaire pour tous les domaines SIP avec des utilisateurs prenant en charge Lync.</p></td>
</tr>
<tr class="odd">
<td><p>DNS externe/SRV/5061</p></td>
<td><p>_sipfederationtls _sipfederationtls._tcp. contoso. com</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Interface externe du serveur Edge d’accès SIP. Obligatoire pour la découverte DNS automatique des partenaires fédérés connus sous le nom de « domaine SIP autorisé » (appelé fédération étendue dans les versions précédentes). Répétez cette opération autant que nécessaire pour tous les domaines SIP avec des utilisateurs activés pour Lync.</p></td>
</tr>
<tr class="even">
<td><p>DNS interne/A</p></td>
<td><p>lsedge.contoso.net</p></td>
<td><p>172.25.33.10 et 172.25.33.11</p></td>
<td><p>Interface interne de serveur Edge consolidé</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="records-required-for-federation"></a>Enregistrements requis pour la fédération


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
<th>Adresse IP/Enregistrement d’hôte FQDN</th>
<th>Mappage à/Commentaires</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DNS externe/SRV/5061</p></td>
<td><p>_sipfederationtls _sipfederationtls._tcp. contoso. com</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Interface externe du serveur Edge d’accès SIP. Requise pour permettre la découverte DNS automatique de votre fédération par d’autres partenaires de fédération potentiels, elle est aussi connue sous le nom de « Domaines SIP autorisés » (ou fédération étendue dans les versions précédentes). Répétez si nécessaire pour tous les domaines SIP avec des utilisateurs prenant en charge Lync.</p>
<div>

> [!IMPORTANT]  
> Cet enregistrement SRV est requis pour la mobilité et le centre d’échanges de notifications push.


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-summary--public-instant-messaging-connectivity"></a>Résumé DNS : connectivité de la messagerie instantanée publique


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
<th>Adresse IP/Nom de domaine complet</th>
<th>Mappage à/Commentaires</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DNS externe/A</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Interface du service Edge d’accès</p></td>
<td><p>Interface externe du serveur Edge d’accès (Contoso). Répétez si nécessaire pour tous les domaines SIP avec des utilisateurs prenant en charge Lync.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-summary-for-extensible-messaging-and-presence-protocol"></a>Résumé DNS pour le protocole XMPP


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
<th>Adresse IP/Enregistrement d’hôte FQDN</th>
<th>Mappage à/Commentaires</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DNS externe/SRV/5269</p></td>
<td><p>_xmpp-server._tcp. contoso. com</p></td>
<td><p>xmpp.contoso.com</p></td>
<td><p>Interface externe du proxy XMPP sur le service Edge d’accès ou le pool de serveurs Edge. Répétez cette opération autant que nécessaire pour tous les domaines SIP internes avec des utilisateurs activés de Lync où les contacts XMPP sont autorisés dans la configuration de la stratégie d’accès externe par le biais d’une stratégie globale, de la stratégie de site où se trouve l’utilisateur ou de la stratégie de l’utilisateur appliquée à l’utilisateur à extension Lync. Un domaine XMPP autorisé doit également être configuré dans la stratégie des partenaires fédérés XMPP. Voir les rubriques de la <strong>section Voir aussi</strong> pour plus de détails</p></td>
</tr>
<tr class="even">
<td><p>DNS externe/A</p></td>
<td><p>xmpp.contoso.com (par exemple)</p></td>
<td><p>Adresse IP du service Edge d’accès sur votre serveur Edge ou le pool de serveurs Edge qui héberge le proxy XMPP</p></td>
<td><p>Pointe vers le service Edge d’accès ou le pool de serveurs Edge qui héberge le service proxy XMPP. En général, l’enregistrement SRV que vous créez pointe vers cet enregistrement (A ou AAAA) d’hôte.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

