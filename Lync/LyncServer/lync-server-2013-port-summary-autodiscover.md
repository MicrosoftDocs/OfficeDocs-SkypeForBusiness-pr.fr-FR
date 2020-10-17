---
title: 'Lync Server 2013 : Résumé des ports-découverte automatique'
description: 'Lync Server 2013 : Résumé des ports-découverte automatique.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Autodiscover
ms:assetid: 8bd16363-5e18-4e4b-be99-b3e6457b4c99
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945642(v=OCS.15)
ms:contentKeyID: 51541497
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 20a5ef54d4ad8419fd6e73909f97764bf1290c22
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543140"
---
# <a name="port-summary---autodiscover-in-lync-server-2013"></a>Résumé des ports-découverte automatique dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-03-05_

Le service de découverte automatique Lync Server 2013 s’exécute sur les serveurs de pools frontaux et de directeurs et, lorsqu’il est publié dans DNS à l’aide des enregistrements de l' `lyncdiscover.<domain>` `lyncdiscoverinternal.<domain>` hôte et, peut être utilisé par les clients pour accéder aux fonctionnalités de Lync Server. Pour que les appareils mobiles exécutant Lync mobile puissent utiliser la découverte automatique, vous devez d’abord modifier les listes des autres noms de sujet du certificat sur un directeur et un serveur frontal exécutant le service de découverte automatique. En outre, il peut s’avérer nécessaire de modifier les listes des autres noms de sujet sur les certificats utilisés pour les règles de publication des services web externes sur les proxys inverses.

La décision d’utiliser des listes d’autres noms de sujet sur les proxys inverses est basée sur la publication du service de découverte automatique sur le port 80 ou sur le port 443 :

  - **Publié sur le port 80**     Pour les appareils mobiles, aucune modification de certificat n’est requise si la requête initiale du service de découverte automatique se produit sur le port 80. Cela est dû au fait que les appareils mobiles exécutant Lync accèdent au proxy inverse sur le port 80 de manière externe, puis sont redirigés vers un directeur ou un serveur frontal sur le port 8080 en interne.

  - **Publié sur le port 443**     La liste autre nom du sujet sur les certificats utilisés par la règle de publication des services Web externes doit contenir une `lyncdiscover.<sipdomain>` entrée pour chaque domaine SIP de votre organisation.
    
    <div>
    

    > [!IMPORTANT]  
    > Pour les nouvelles installations ou mises à niveau à partir de Lync Server 2010 où vous avez déployé la mobilité, vous avez utilisé le port 80 pour la découverte automatique du service de mobilité ou émis à nouveau les certificats avec le nom d’objet et les autres noms de sujet appropriés sur place. Passez en revue les certificats sur votre directeur et votre serveur frontal pour confirmer le chemin d’accès que vous avez choisi.

    
    </div>

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
<td><p>N’importe lequel</p></td>
<td><p>Port d’écoute du proxy inverse</p></td>
<td><p>Module Redirection vers HTTPs si l’utilisateur entre http:// &lt; publishedSiteFQDN &gt; . Également requis si vous utilisez Office Web Apps pour les conférences et le service de découverte automatique pour les appareils mobiles exécutant Lync dans les situations où l’organisation ne souhaite pas modifier le certificat de règle de publication du service Web externe.</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP/443</p></td>
<td><p>N’importe lequel</p></td>
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
<td><p>Serveur frontal, pool frontal, directeur, pool Directeur, Office Web Apps pour les conférences</p></td>
<td><p>Obligatoire si vous utilisez le service de découverte automatique pour les appareils mobiles exécutant Lync dans les situations où l’organisation ne souhaite pas modifier le certificat de règle de publication du service Web externe. Le trafic envoyé vers le port 80 sur l’interface externe du proxy inverse est redirigé vers un pool sur le port 8080 à partir de l’interface interne du proxy inverse. Ainsi, les services web du pool peuvent faire la distinction par rapport au trafic web interne.</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP/4443</p></td>
<td><p>Interface interne du proxy inverse</p></td>
<td><p>Serveur frontal, pool frontal, directeur, pool Directeur, Office Web Apps pour les conférences</p></td>
<td><p>Le trafic envoyé vers le port 443 sur l’interface externe du proxy inverse est redirigé vers un pool sur le port 4443 à partir de l’interface interne du proxy inverse. Ainsi, les services web du pool peuvent faire la distinction par rapport au trafic web interne.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

