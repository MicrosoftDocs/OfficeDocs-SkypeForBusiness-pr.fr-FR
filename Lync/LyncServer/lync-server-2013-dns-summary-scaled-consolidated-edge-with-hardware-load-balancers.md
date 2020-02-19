---
title: Résumé des enregistrements DNS-serveur Edge consolidé ajusté avec programmes d’équilibrage de la charge matérielle
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Scaled consolidated edge with hardware load balancers
ms:assetid: 8453297c-da1d-4b9e-a37e-6721458c6feb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398670(v=OCS.15)
ms:contentKeyID: 48184700
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c45802282c57ebcf80fbc55b030c985fe7d977cd
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137803"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-summary---scaled-consolidated-edge-with-hardware-load-balancers-in-lync-server-2013"></a>Résumé des enregistrements DNS-serveur Edge consolidé ajusté avec programmes d’équilibrage de la charge matérielle dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-01-27_

Les exigences liées aux enregistrements DNS pour l’accès à distance à Lync Server 2013 sont relativement simples par rapport à celles des certificats et des ports. De plus, de nombreux enregistrements sont facultatifs, en fonction de la configuration des clients exécutant Lync 2013 et de l’activation de la Fédération.

Pour plus d’informations sur les exigences DNS de Lync 2013, voir [determine DNS Requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).

Pour plus d’informations sur la configuration automatique des clients Lync 2013 si le DNS split-brain n’est pas configuré, consultez la section « Configuration automatique sans DNS split brain » dans [determine DNS Requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).

Le tableau suivant contient une synthèse des enregistrements DNS requis pour prendre en charge le serveur Edge consolidé ajusté (avec équilibrage de charge matérielle) présenté dans la figure. Notez que certains enregistrements DNS sont requis uniquement pour la configuration automatique des clients Lync. Si vous envisagez d’utiliser des objets de stratégie de groupe (GPO) pour configurer des clients Lync, les enregistrements associés ne sont pas nécessaires.

<div>

## <a name="important-edge-server-network-adapter-requirements"></a>IMPORTANT : configuration requise pour la carte réseau de serveur Edge

Pour éviter les problèmes de routage, vérifiez qu’il y a au moins deux cartes réseau dans vos serveurs Edge et que la passerelle par défaut est définie uniquement sur la carte réseau associée à l’interface externe. Par exemple, comme illustré dans la figure du scénario de serveur Edge consolidé ajusté dans le [serveur Edge consolidé ajusté avec des programmes d’équilibrage de la charge matérielle dans Lync Server 2013](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md), la passerelle par défaut pointe vers le pare-feu externe.

Vous pouvez configurer deux cartes réseau dans chacun de vos serveurs Edge comme suit :

  - **Carte réseau 1 (interface interne)**
    
    Interface interne avec 172.25.33.10 affecté.
    
    Aucune passerelle par défaut.
    
    Assurez-vous qu’il existe un itinéraire entre le réseau contenant l’interface interne du serveur Edge et les réseaux qui contiennent des clients ou des serveurs Lync Server exécutant Lync Server (par exemple, de 172.25.33.0 à 192.168.10.0).

  - **Carte réseau 2 (interface externe)**
    
    Trois adresses IP publiques sont attribuées à cette carte réseau, par exemple 131.107.155.10 pour le service Edge d’accès, 131.107.155.20 pour le service Edge de conférence Web, 131.107.155.30 pour le service Edge A/V.
    
    <div>
    

    > [!NOTE]
    > Les adresses IP affectées aux interfaces réseau externes réelles du serveur Edge peuvent être tributaires de l’équilibreur de charge matériel que vous choisissez. Reportez-vous à la documentation de votre équilibreur de charge matérielle pour comprendre l’adresse IP réelle requise.<BR>Il est possible, mais déconseillé, d’utiliser une adresse IP unique pour les interfaces des trois services Edge. Bien que les adresses IP soient enregistrées, les numéros de port doivent être différents pour chaque service. Le numéro de port par défaut est 443/TCP, ce qui permet de s’assurer que la plupart des pare-feu distants autoriseront le trafic. La modification des valeurs de port à (par exemple) 5061/TCP pour le service Edge d’accès, 444/TCP pour le service Edge de conférence Web et 443/TCP pour le service Edge A/V pourrait entraîner des problèmes pour les utilisateurs distants où un pare-feu dont ils sont derrière n’autorise pas le trafic sur 5061/TCP et 444/TCP. Par ailleurs, l’utilisation de trois adresses IP distinctes facilite le dépannage puisqu’il est possible d’appliquer un filtre selon l’adresse IP.

    
    </div>
    
    L’adresse IP du service Edge d’accès est principale avec la passerelle par défaut définie sur le routeur accessible sur Internet (131.107.155.1).
    
    Service Edge de conférence Web et adresses IP du service Edge A/V secondaires.

<div>


> [!TIP]
> La configuration du serveur Edge avec deux cartes réseau est l’une des deux options. L’autre option consiste à utiliser une carte réseau pour le côté interne et trois cartes réseau pour le côté externe du serveur Edge. Le principal avantage de cette option est une carte réseau distincte par serveur de serveur Edge et une collecte de données potentiellement plus concise lorsque la résolution des problèmes est nécessaire.



</div>

### <a name="dns-records-required-for-scaled-consolidated-edge-hardware-load-balanced-example"></a>Enregistrements DNS requis pour le serveur Edge consolidé ajusté, équilibrage de charge matérielle (exemple)

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
<td><p>131.107.155.10</p></td>
<td><p>Interface externe du service Edge d’accès (contoso). Répétez cette opération autant que nécessaire pour tous les domaines SIP avec des utilisateurs activés pour Lync.</p></td>
</tr>
<tr class="even">
<td><p>DNS externe/A</p></td>
<td><p>webcon.contoso.com</p></td>
<td><p>131.107.155.20</p></td>
<td><p>Interface externe du service Edge de conférence Web</p></td>
</tr>
<tr class="odd">
<td><p>DNS externe/A</p></td>
<td><p>av.contoso.com</p></td>
<td><p>131.107.155.30</p></td>
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
<td><p>Interface externe du service Edge d’accès SIP requise pour la découverte DNS automatique des partenaires fédérés connus sous le nom de « domaine SIP autorisé » (appelée fédération étendue dans les versions précédentes). Répétez cette opération autant que nécessaire pour tous les domaines SIP avec des utilisateurs de Lync et des clients mobiles Microsoft Lync qui utilisent le service de notifications ou le service de notification poussé Apple.</p></td>
</tr>
<tr class="even">
<td><p>DNS interne/A</p></td>
<td><p>lsedge.contoso.net</p></td>
<td><p>172.25.33.10</p></td>
<td><p>Interface interne de serveur Edge consolidé</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

