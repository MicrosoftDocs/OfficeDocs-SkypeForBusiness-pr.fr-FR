---
title: 'Lync Server 2013 : Enregistrements DNS requis pour un serveur Standard Edition'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for a Standard Edition server
ms:assetid: 5d1daf54-6e60-4ce0-9254-7d57a0835fa4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204936(v=OCS.15)
ms:contentKeyID: 48184259
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3ab4280ca3ed329d0dc926756f6bfd933595ca08
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739174"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-a-standard-edition-server-in-lync-server-2013"></a>Enregistrements DNS requis pour un serveur Standard Edition dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-22_

Cette section décrit les enregistrements DNS (Domain Name System) requis pour le déploiement de serveurs Standard Edition.

<div>

## <a name="dns-records-for-standard-edition-servers"></a>Enregistrements DNS pour les serveurs Standard Edition Server

Le tableau suivant indique les exigences DNS pour le déploiement de Lync Server 2013 Standard Edition Server.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Scénario de déploiement</th>
<th>Enregistrement DNS requis</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>serveur Standard Edition</p></td>
<td><p>Un enregistrement interne A qui associe le nom de domaine complet (FQDN) du serveur à son adresse IP.</p></td>
</tr>
<tr class="even">
<td><p>Connexion automatique au client</p></td>
<td><p>Pour chaque domaine SIP pris en charge, un enregistrement SRV pour _sipinternaltls. _tcp. &lt;domaine&gt; sur le port 5061 qui correspond au nom de domaine complet du serveur Standard Edition qui authentifie et redirige les demandes de connexion du client. Pour plus d’informations, voir <a href="lync-server-2013-dns-requirements-for-automatic-client-sign-in.md">configuration DNS requise pour la connexion automatique au client dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p>Découverte du service Web de mise à jour d’appareil par des appareils de communications unifiées (UC)</p></td>
<td><p>Un enregistrement A interne du nom ucupdates-r2. &lt;Domaine&gt; SIP résolu sur l’adresse IP du service Web de mise à jour des appareils d’hébergement Standard Edition Server. Dans le cas où un périphérique UC est activé, mais qu’aucun utilisateur ne s’est connecté à l’appareil, l’enregistrement A permet à l’appareil de détecter le service Web de mise à jour de l’appareil d’hébergement du serveur et d’obtenir les mises à jour. Les périphériques peuvent autrement se procurer ces informations via une mise en service de la bande entrante la première fois qu’un utilisateur se connecte. Pour plus d’informations, reportez-vous à la rubrique <a href="lync-server-2013-device-update-web-service.md">service Web de mise à jour des appareils de Lync Server 2013</a> dans la documentation opérations.</p></td>
</tr>
<tr class="even">
<td><p>Proxy inverse pour la prise en charge du trafic HTTP</p></td>
<td><p>Un enregistrement A externe qui résout le nom de domaine complet de la batterie de serveurs Web externe à l’adresse IP externe du proxy inverse. Les clients et les appareils UC utilisent cet enregistrement pour se connecter au proxy inverse. Pour plus d’informations, reportez-vous à la rubrique <a href="lync-server-2013-determine-dns-requirements.md">déterminer les exigences DNS pour Lync Server 2013</a> dans la documentation de planification.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>Voir aussi


[Configuration DNS requise pour la connexion automatique au client dans Lync Server 2013](lync-server-2013-dns-requirements-for-automatic-client-sign-in.md)  
[Détermination de la configuration requise pour DNS pour Lync Server 2013](lync-server-2013-determine-dns-requirements.md)  


[Service web de mise à jour des dispositifs dans Lync Server 2013](lync-server-2013-device-update-web-service.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

