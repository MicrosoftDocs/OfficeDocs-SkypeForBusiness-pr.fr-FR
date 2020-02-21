---
title: 'Lync Server 2013 : Résumé des enregistrements DNS-serveur Edge consolidé ajusté, équilibrage de charge DNS avec des adresses IP publiques'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Scaled consolidated edge, DNS load balancing with public IP addresses
ms:assetid: dc8f096a-a0a4-4f71-8930-88ff8fc089d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205319(v=OCS.15)
ms:contentKeyID: 48185594
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 48dab867ac7ae408f544e4dbc6bc55ff555e20a3
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213090"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-summary---scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses-in-lync-server-2013"></a>Résumé des enregistrements DNS-serveur Edge consolidé ajusté, équilibrage de charge DNS avec adresses IP publiques dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2017-03-09_

Les exigences liées aux enregistrements DNS pour l’accès à distance à Lync Server 2013 sont relativement simples par rapport à celles des certificats et des ports. De plus, de nombreux enregistrements sont facultatifs, en fonction de la configuration des clients exécutant Lync 2013 et de l’activation de la Fédération.

Pour plus d’informations sur les exigences DNS de Lync 2013, voir [determine DNS Requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).

Pour plus d’informations sur la configuration automatique des clients Lync 2013 si le DNS split-brain n’est pas configuré, consultez la section « Configuration automatique sans DNS split brain » dans [determine DNS Requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).

Le tableau suivant contient un résumé des enregistrements DNS requis pour prendre en charge la topologie Edge consolidée indiquée dans la figure Topologie Edge consolidée unique. Notez que certains enregistrements DNS sont requis uniquement pour la configuration automatique des clients Lync 2013. Si vous envisagez d’utiliser des objets de stratégie de groupe (GPO) pour configurer des clients Lync, les enregistrements associés ne sont pas nécessaires.

<div>

## <a name="important-edge-server-network-adapter-requirements"></a>IMPORTANT : configuration requise pour la carte réseau de serveur Edge

Pour éviter les problèmes de routage, vérifiez qu’il y a au moins deux cartes réseau dans vos serveurs Edge et que la passerelle par défaut est définie uniquement sur la carte réseau associée à l’interface externe. Par exemple, comme illustré dans la figure du scénario de serveur Edge consolidé ajusté dans le [serveur Edge consolidé ajusté, l’équilibrage de charge DNS avec des adresses IP publiques dans Lync Server 2013](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md) , la passerelle par défaut pointerait vers le pare-feu externe.

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
    
    Trois adresses IP privées sont attribuées à cette carte réseau, par exemple 131.107.155.10 pour le service Edge d’accès, 131.107.155.20 pour le service Edge de conférence Web, 131.107.155.30 pour le service Edge A/V.
    
    L’adresse IP publique du service Edge d’accès est principale avec la passerelle par défaut définie sur le routeur public (131.107.155.1).
    
    Le service Edge de conférence Web et le service Edge A/V sont des adresses IP supplémentaires dans la section **avancé** des propriétés de **protocole Internet version 4 (TCP/IPv4)** et **Internet Protocol version 6 (TCP/IPv6)** des **Propriétés de connexion au réseau local** dans Windows Server.
    
    <div>
    

    > [!NOTE]  
    > Il est possible, mais déconseillé, d’utiliser une adresse IP unique pour les interfaces des trois services Edge. Bien que les adresses IP soient enregistrées, les numéros de port doivent être différents pour chaque service. Le numéro de port par défaut est 443/TCP, ce qui permet de s’assurer que la plupart des pare-feu distants autoriseront le trafic. La modification des valeurs de port à (par exemple) 5061/TCP pour le service Edge d’accès, 444/TCP pour le service Edge de conférence Web et 443/TCP pour le service Edge A/V pourrait entraîner des problèmes pour les utilisateurs distants où un pare-feu dont ils sont derrière n’autorise pas le trafic sur 5061/TCP et 444/TCP. En outre, trois adresses IP distinctes facilitent le dépannage, car vous pouvez filtrer selon l’adresse IP.

    
    </div>

  - **Carte réseau 2 - nœud 2 (interface externe)**
    
    Trois adresses IP privées sont attribuées à cette carte réseau, par exemple 131.107.155.11 pour le service Edge d’accès, 131.107.155.21 pour le service Edge de conférence Web, 131.107.155.31 pour le service Edge A/V.
    
    L’adresse IP publique du service Edge d’accès est principale avec la passerelle par défaut définie sur le routeur public (131.107.155.1).
    
    Le service Edge de conférence Web et le service Edge A/V sont des adresses IP supplémentaires dans la section **avancé** des propriétés de **protocole Internet version 4 (TCP/IPv4)** et **Internet Protocol version 6 (TCP/IPv6)** des **Propriétés de connexion au réseau local** dans Windows Server.

<div>


> [!TIP]  
> La configuration du serveur Edge avec deux cartes réseau est l’une des deux options. L’autre option consiste à utiliser une carte réseau pour le côté interne et trois cartes réseau pour le côté externe du serveur Edge. Le principal avantage de cette option est une carte réseau distincte par serveur de serveur Edge et une collecte de données potentiellement plus concise lorsque la résolution des problèmes est nécessaire.



</div>

### <a name="dns-records-required-for-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses-example"></a>Enregistrements DNS requis pour la topologie Edge consolidée mise à l’échelle, équilibrage de la charge DNS avec des adresses IP publiques (exemple)

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
<th>Mappe vers/Commentaires</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DNS externe/A</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>131.107.155.10 et 131.107.155.11</p></td>
<td><p>Interface externe du service Edge d’accès (contoso) répéter si nécessaire pour tous les domaines SIP avec des utilisateurs activés pour Lync</p></td>
</tr>
<tr class="even">
<td><p>DNS externe/A</p></td>
<td><p>webcon.contoso.com</p></td>
<td><p>131.107.155.20 et 131.107.155.21</p></td>
<td><p>Interface externe du service Edge de conférence Web</p></td>
</tr>
<tr class="odd">
<td><p>DNS externe/A</p></td>
<td><p>av.contoso.com</p></td>
<td><p>131.107.155.30 et 131.107.155.31</p></td>
<td><p>Interface externe du service Edge A/V</p></td>
</tr>
<tr class="even">
<td><p>DNS externe/SRV/443</p></td>
<td><p>_sip. _tls. contoso. com</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Interface externe du service Edge d’accès. Nécessaire pour que la configuration automatique des clients Lync 2013 et Lync 2010 fonctionne en externe. Répétez si nécessaire pour tous les domaines SIP avec des utilisateurs prenant en charge Lync.</p></td>
</tr>
<tr class="odd">
<td><p>DNS externe/SRV/5061</p></td>
<td><p>_sipfederationtls. _tcp. contoso. com</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Interface externe du service Edge d’accès requise pour la découverte DNS automatique des partenaires fédérés connus sous le nom de « domaine SIP autorisé » (appelée fédération étendue dans les versions précédentes). Répétez cette opération autant que nécessaire pour tous les domaines SIP avec des utilisateurs activés pour Lync.</p></td>
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
<td><p>DNS externe /SRV/5061</p></td>
<td><p>_sipfederationtls. _tcp. contoso. com</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>L’interface externe du service Edge d’accès SIP est requise pour la découverte automatique de DNS de votre Fédération auprès des autres partenaires de Fédération potentiels et est appelée « domaines SIP autorisés » (appelée fédération étendue dans les versions précédentes).</p>
<div>

> [!IMPORTANT]  
> Répétez cette opération autant que nécessaire pour tous les domaines SIP avec des utilisateurs de Lync et des clients mobiles Microsoft Lync qui utilisent le service de notifications ou le service de notification poussé Apple.


</div></td>
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
<td><p>_xmpp-Server. _tcp. contoso. com</p></td>
<td><p>xmpp.contoso.com</p></td>
<td><p>Interface externe du proxy XMPP sur le service Edge d’accès ou le pool de serveurs Edge. Répétez cette opération si nécessaire pour tous les domaines SIP internes avec des utilisateurs activés de Lync où les contacts XMPP sont autorisés via la configuration de la stratégie d’accès externe par le biais d’une stratégie globale, de la stratégie de site où se trouve l’utilisateur ou de la stratégie de l’utilisateur appliquée au Utilisateur à extension Lync. Un domaine XMPP autorisé doit également être configuré dans la stratégie des partenaires fédérés XMPP. Voir les rubriques de la <strong>section Voir aussi</strong> pour plus de détails</p></td>
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

