---
title: 'Lync Server 2013: Résumé de port-découverte automatique'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Port summary - Autodiscover
ms:assetid: 8bd16363-5e18-4e4b-be99-b3e6457b4c99
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945642(v=OCS.15)
ms:contentKeyID: 51541497
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7a40d86799b4922a819642aedf2461f038330593
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824077"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---autodiscover-in-lync-server-2013"></a>Résumé du port-découverte automatique dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-03-05_

Le service de découverte automatique de Lync Server 2013 s’exécute sur le directeur et les serveurs du pool frontal, et lorsqu’il `lyncdiscover.<domain>` est `lyncdiscoverinternal.<domain>` publié dans DNS à l’aide des enregistrements d’hôte et, les clients peuvent utiliser les fonctionnalités de Lync Server. Pour que les appareils mobiles exécutant Lync mobile puissent utiliser la découverte automatique, il est possible que vous deviez modifier les listes de noms de remplacement de l’objet du certificat sur tout directeur et serveur frontal exécutant le service de découverte automatique. Par ailleurs, il est possible que vous deviez modifier les listes nom de remplacement de l’objet sur les certificats utilisés pour les règles de publication de service Web externe sur les proxys inverses.

La décision concernant l’utilisation des listes de noms de substitution sur les proxys inverse est basée sur le fait que vous publiez le service de découverte automatique sur le port 80 ou sur le port 443:

  - **Publié sur le port 80**   pour les appareils mobiles, aucune modification de certificat n’est requise si la requête initiale au service de découverte automatique a lieu sur le port 80. En effet, les appareils mobiles exécutant Lync accèderont au proxy inverse sur le port 80 en externe, puis seront redirigés vers un serveur directeur ou frontal sur le port 8080 en interne.

  - **Publié sur le port 443**   la liste autre nom de l’objet sur les certificats utilisés par la règle de publication des `lyncdiscover.<sipdomain>` services Web externes doit contenir une entrée pour chaque domaine SIP au sein de votre organisation.
    
    <div>
    

    > [!IMPORTANT]  
    > Pour les nouvelles installations ou mises à niveau de Lync Server 2010 sur lequel vous avez déployé une mobilité, vous avez utilisé le port 80 pour la découverte automatique du service de mobilité ou les certificats ayant été renommés avec le nom d’objet approprié et les noms de substitution de l’objet en vigueur. Passez en revue les certificats de votre directeur et de votre serveur frontal pour vérifier le chemin que vous avez choisi.

    
    </div>

### <a name="firewall-details-for-reverse-proxy-server-external-interface"></a>Détails du pare-feu pour le serveur proxy inverse: interface externe

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
<th>Notes</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>HTTP/TCP/80</p></td>
<td><p>Indifférente</p></td>
<td><p>Écouteur de proxy inverse</p></td>
<td><p>Facultatif Redirection vers HTTPs si l’utilisateur entre http://&lt;publishedSiteFQDN&gt;. Également requis si vous utilisez Office Web Apps pour les conférences et le service de découverte automatique pour les appareils mobiles exécutant Lync dans les situations dans lesquelles l’organisation ne souhaite pas modifier le certificat de règle de publication de service Web externe.</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP/443</p></td>
<td><p>Indifférente</p></td>
<td><p>Écouteur de proxy inverse</p></td>
<td><p>Téléchargements de carnets d’adresses, service de requête sur le Web du carnet d’adresses, découverte automatique, mises à jour du client, contenu de la réunion, mises à jour de l’appareil, développement de groupe, Office Web Apps pour les conférences, Conférence rendez-vous et réunions.</p></td>
</tr>
</tbody>
</table>


### <a name="firewall-details-for-reverse-proxy-server-internal-interface"></a>Détails du pare-feu pour le serveur proxy inverse: interface interne

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
<th>Notes</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>HTTP/TCP/8080</p></td>
<td><p>Interface du proxy inverse interne</p></td>
<td><p>Serveur frontal, pool frontal, directeur, pool de directeurs, Office Web Apps pour les conférences</p></td>
<td><p>Obligatoire si vous utilisez le service de découverte automatique pour les appareils mobiles exécutant Lync dans les situations où l’organisation ne souhaite pas modifier le certificat de règle de publication de service Web externe. Le trafic envoyé au port 80 sur l’interface externe du proxy inverse est redirigé vers un pool sur le port 8080 à partir de l’interface interne du proxy, afin que les services Web de réserve puissent le différencier du trafic Web interne.</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP/4443</p></td>
<td><p>Interface du proxy inverse interne</p></td>
<td><p>Serveur frontal, pool frontal, directeur, pool de directeurs, Office Web Apps pour les conférences</p></td>
<td><p>Le trafic envoyé au port 443 sur l’interface externe du proxy inverse est redirigé vers un pool sur le port 4443 à partir de l’interface interne du proxy, afin que les services Web de réserve puissent le différencier du trafic Web interne.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

