---
title: 'Lync Server 2013 : Résumé des ports-proxy inverse'
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
ms.openlocfilehash: 6259614da322e79f69db40441125b28c95e379c9
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42183907"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="port-summary---reverse-proxy-in-lync-server-2013"></a>Résumé des ports-proxy inverse dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-15_

Le proxy inverse a des exigences minimales en matière de pare-feu et de port/protocole.

  - Exigences de pare-feu externe : HTTPs/TCP/443 et HTTP/TCP/80 facultatif. HTTPs est utilisé pour les communications sécurisées SSL et TLS via le proxy inverse. HTTP est utilisé si vous choisissez d’autoriser l’accès au service de découverte automatique lors de la modification des certificats peut s’avérer difficile ou non justifié.

  - Les clients s’attendent à contacter Office Web Apps Server sur HTTPs. Office Web Apps Server attend la communication de clients internes sur HTTPs/TCP/443. La configuration recommandée consiste à autoriser le protocole HTTPs/TCP/443 à partir du proxy inverse vers le serveur Office Web Apps Server.

  - Le port 8080 est utilisé pour acheminer le trafic depuis l’interface interne du proxy inverse vers le serveur frontal, l’adresse IP virtuelle du pool frontal ou l’adresse IP virtuelle du pool directeur ou directeur facultatif. Le port TCP 8080 est requis pour les appareils mobiles exécutant Lync pour localiser le service de découverte automatique dans les situations où la modification du certificat de règle de publication du service Web externe est indésirable (par exemple, si vous avez un grand nombre de domaines SIP). Si vous choisissez d’acquérir de nouveaux certificats avec les entrées SAN nécessaires, le port TCP 8080 n’est pas nécessaire et devient facultatif.

  - Le port 4443 est utilisé pour le trafic provenant de l’interface interne du proxy inverse vers le serveur frontal, l’adresse IP virtuelle du pool frontal ou l’adresse IP virtuelle du pool directeur ou directeur facultatif.
    
    ![13142405-D5C9-45b7-a8b7-a8c89f09c97c](images/JJ204932.13142405-d5c9-45b7-a8b7-a8c89f09c97c(OCS.15).jpg "13142405-D5C9-45b7-a8b7-a8c89f09c97c")  
    
    <div>
    

    > [!WARNING]  
    > Ne confondez pas le 4443 sur TCP du proxy inverse au déploiement interne du port 4443 sur le trafic TCP à partir du serveur Standard Edition ou du pool frontal qui gère le rôle magasin central de gestion.

    
    </div>

<div>

## <a name="port-and-protocol-details"></a>Détails des ports et protocoles

### <a name="firewall-details-for-reverse-proxy-server-external-interface"></a>Informations sur le pare-feu pour le serveur proxy inverse : interface externe

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
<th>Adresse IP source</th>
<th>Adresse IP de destination</th>
<th>Notes</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>HTTP/TCP/80</p></td>
<td><p>N'importe lequel</p></td>
<td><p>Port d’écoute du proxy inverse</p></td>
<td><p>Module Redirection vers HTTPs si l’utilisateur entre http://&lt;publishedSiteFQDN&gt;.</p>
<p>Également requis si vous utilisez Office Web Apps pour les conférences et le service de découverte automatique pour les appareils mobiles exécutant Lync dans les situations où l’organisation ne souhaite pas modifier le certificat de règle de publication du service Web externe.</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP/443</p></td>
<td><p>N'importe lequel</p></td>
<td><p>Port d’écoute du proxy inverse</p></td>
<td><p>Téléchargements de carnets d’adresses, service de requête sur le Web du carnet d’adresses, découverte automatique, mises à jour du client, contenu de la réunion, mises à jour de périphériques, développement de groupes, Office Web Apps pour les conférences, Conférence rendez-vous et réunions.</p></td>
</tr>
</tbody>
</table>


### <a name="firewall-details-for-reverse-proxy-server-internal-interface"></a>Informations sur le pare-feu pour le serveur proxy inverse : interface interne

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
<th>Adresse IP source</th>
<th>Adresse IP de destination</th>
<th>Notes</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>HTTP/TCP/8080</p></td>
<td><p>Interface interne du proxy inverse</p></td>
<td><p>Serveur frontal, pool frontal, directeur, pool directeur</p></td>
<td><p>Obligatoire si vous utilisez le service de découverte automatique pour les appareils mobiles exécutant Lync dans les situations où l’organisation ne souhaite pas modifier le certificat de règle de publication du service Web externe.</p>
<p>Le trafic envoyé vers le port 80 sur l’interface externe du proxy inverse est redirigé vers un pool sur le port 8080 à partir de l’interface interne du proxy inverse. Ainsi, les services web du pool peuvent faire la distinction par rapport au trafic web interne.</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP/4443</p></td>
<td><p>Interface interne du proxy inverse</p></td>
<td><p>Serveur frontal, pool frontal, directeur, pool directeur</p></td>
<td><p>Le trafic envoyé vers le port 443 sur l’interface externe du proxy inverse est redirigé vers un pool sur le port 4443 à partir de l’interface interne du proxy inverse. Ainsi, les services web du pool peuvent faire la distinction par rapport au trafic web interne.</p></td>
</tr>
<tr class="odd">
<td><p>HTTPS/TCP/443</p></td>
<td><p>Interface interne du proxy inverse</p></td>
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

