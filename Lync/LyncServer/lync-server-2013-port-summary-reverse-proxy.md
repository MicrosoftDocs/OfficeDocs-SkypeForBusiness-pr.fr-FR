---
title: 'Lync Server 2013 : Résumé des ports - Proxy inverse'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Reverse proxy
ms:assetid: 59b9ac3c-3e6f-4776-b366-174f0dd1f2eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204932(v=OCS.15)
ms:contentKeyID: 48184251
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f2944cde932413f00b5a4dcb75cd4a37bd5b3a3a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747594"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---reverse-proxy-in-lync-server-2013"></a>Résumé des ports - Proxy inverse dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-15_

Le proxy inverse est soumis à une configuration minimale pour le pare-feu et le port/protocole.

  - La configuration requise pour le pare-feu externe est HTTPs/TCP/443 et HTTP/TCP/80 facultatif. HTTPs est utilisé pour les communications sécurisées SSL et TLS par le biais du proxy inverse. HTTP est utilisé si vous choisissez d’autoriser l’accès au service de découverte automatique lors de la modification des certificats peut s’avérer difficile ou n’est pas justifié.

  - Les clients peuvent contacter le serveur Office Web Apps sur HTTPs. Office Web Apps Server attend la communication de clients internes sur HTTPs/TCP/443. La configuration recommandée consiste à autoriser HTTPs/TCP/443 du proxy inverse au serveur Office Web Apps.

  - Le port 8080 est utilisé pour acheminer le trafic de l’interface interne du proxy inverse vers le serveur frontal, le pool d’adresses IP virtuelles du pool frontal ou le point de terminaison du réalisateur ou du réalisateur facultatif. Le port TCP 8080 est requis pour les appareils mobiles exécutant Lync pour localiser le service de découverte automatique dans les cas où la modification du certificat de règle de publication de service Web externe n’est pas souhaitable (par exemple, si vous avez un grand nombre de domaines SIP). Si vous choisissez d’acquérir de nouveaux certificats avec les entrées SAN nécessaires, le port TCP 8080 n’est pas nécessaire et est facultatif.

  - Le port 4443 est utilisé pour le trafic de l’interface interne du proxy inverse vers le serveur frontal, le pool d’adresses IP virtuelles de pool frontal ou le directeur principal ou le protocole principal de pool de réalisateur
    
    ![13142405-D5C9-45b7-a8b7-a8c89f09c97c](images/JJ204932.13142405-d5c9-45b7-a8b7-a8c89f09c97c(OCS.15).jpg "13142405-D5C9-45b7-a8b7-a8c89f09c97c")  
    
    <div>
    

    > [!WARNING]  
    > Ne confondez pas le 4443 sur TCP à partir du proxy inverse vers le déploiement interne pour le port 4443 sur le trafic TCP à partir du serveur Standard Edition Server ou du pool frontal qui gère le rôle de magasin central de gestion.

    
    </div>

<div>

## <a name="port-and-protocol-details"></a>Détails sur les ports et protocoles

### <a name="firewall-details-for-reverse-proxy-server-external-interface"></a>Détails du pare-feu pour le serveur proxy inverse : interface externe

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Protocole/TCP ou UDP/Port</th>
<th>Adresse IP source</th>
<th>Adresse IP de destination</th>
<th>Remarques</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>HTTP/TCP/80</p></td>
<td><p>Indifférente</p></td>
<td><p>Écouteur de proxy inverse</p></td>
<td><p>Facultatif Redirection vers HTTPs si l’utilisateur entre http://&lt;publishedSiteFQDN&gt;.</p>
<p>Également requis si vous utilisez Office Web Apps pour les conférences et le service de découverte automatique pour les appareils mobiles exécutant Lync dans les situations dans lesquelles l’organisation ne souhaite pas modifier le certificat de règle de publication de service Web externe.</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP/443</p></td>
<td><p>Indifférente</p></td>
<td><p>Écouteur de proxy inverse</p></td>
<td><p>Téléchargements de carnets d’adresses, service de requête sur le Web du carnet d’adresses, découverte automatique, mises à jour du client, contenu de la réunion, mises à jour de l’appareil, développement de groupe, Office Web Apps pour les conférences, Conférence rendez-vous et réunions.</p></td>
</tr>
</tbody>
</table>


### <a name="firewall-details-for-reverse-proxy-server-internal-interface"></a>Détails du pare-feu pour le serveur proxy inverse : interface interne

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Protocole/TCP ou UDP/Port</th>
<th>Adresse IP source</th>
<th>Adresse IP de destination</th>
<th>Remarques</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>HTTP/TCP/8080</p></td>
<td><p>Interface du proxy inverse interne</p></td>
<td><p>Serveur frontal, pool frontal, directeur, pool de réalisateurs</p></td>
<td><p>Obligatoire si vous utilisez le service de découverte automatique pour les appareils mobiles exécutant Lync dans les situations où l’organisation ne souhaite pas modifier le certificat de règle de publication de service Web externe.</p>
<p>Le trafic envoyé au port 80 sur l’interface externe du proxy inverse est redirigé vers un pool sur le port 8080 à partir de l’interface interne du proxy, afin que les services Web de réserve puissent le différencier du trafic Web interne.</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP/4443</p></td>
<td><p>Interface du proxy inverse interne</p></td>
<td><p>Serveur frontal, pool frontal, directeur, pool de réalisateurs</p></td>
<td><p>Le trafic envoyé au port 443 sur l’interface externe du proxy inverse est redirigé vers un pool sur le port 4443 à partir de l’interface interne du proxy, afin que les services Web de réserve puissent le différencier du trafic Web interne.</p></td>
</tr>
<tr class="odd">
<td><p>HTTPS/TCP/443</p></td>
<td><p>Interface du proxy inverse interne</p></td>
<td><p>Office Web Apps pour les conférences</p></td>
<td></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

