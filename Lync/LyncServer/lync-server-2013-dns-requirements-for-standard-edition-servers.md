---
title: 'Lync Server 2013 : configuration DNS requise pour les serveurs Standard Edition Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for Standard Edition servers
ms:assetid: 3d6bbe65-e7ce-491b-a0bd-d2f7197f240d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425900(v=OCS.15)
ms:contentKeyID: 48183920
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2064181a7c4d60015905d5974ac01378b7d025e2
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029595"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-standard-edition-servers-in-lync-server-2013"></a>Configuration DNS requise pour les serveurs Standard Edition Server dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-06-19_

Cette section décrit les enregistrements DNS (Domain Name System) requis pour le déploiement de serveurs Standard Edition.

<div>

## <a name="dns-records-for-standard-edition-servers"></a>Enregistrements DNS requis pour les serveurs Standard Edition

Le tableau suivant spécifie les exigences DNS pour le déploiement de Lync Server 2013 Standard Edition Server.

### <a name="dns-requirements-for-a-standard-edition-server"></a>Enregistrements DNS requis pour les serveurs Standard Edition

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
<td><p>Serveur Standard Edition</p></td>
<td><p>Enregistrement A interne associant le nom de domaine complet (FQDN) du serveur à son adresse IP.</p></td>
</tr>
<tr class="even">
<td><p>Ouverture de session client automatique</p></td>
<td><p>Pour chaque domaine SIP pris en charge, un enregistrement SRV pour _sipinternaltls. _tcp. &lt;domaine&gt; sur le port 5061 qui correspond au nom de domaine complet (FQDN) du serveur Standard Edition qui authentifie et redirige les demandes client de connexion. Pour plus d’informations, consultez la rubrique <a href="lync-server-2013-dns-requirements-for-automatic-client-sign-in.md">DNS Requirements for Automatic client Sign-in dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p>Détection du service web de mise à jour des périphériques par les périphériques de communications unifiées</p></td>
<td><p>Un enregistrement A interne portant le nom ucupdates-r2. &lt;Domaine&gt; SIP qui est résolu en adresse IP du service Web de mise à jour des périphériques hébergeant le serveur Standard Edition. Dans le cas où un périphérique de communications unifiées est activé, alors qu’un utilisateur ne s’y est jamais connecté, l’enregistrement A permet au périphérique de détecter le serveur hébergeant le service web de mise à jour des périphériques et d’obtenir des mises à jour. Les périphériques peuvent autrement se procurer ces informations via une mise en service de la bande entrante la première fois qu’un utilisateur se connecte.</p></td>
</tr>
<tr class="even">
<td><p>Proxy inverse de prise en charge du trafic HTTP</p></td>
<td><p>Enregistrement A externe qui résout le nom de domaine complet de la batterie de serveurs web externes en adresse IP externe du proxy inverse. Les clients et les périphériques de communications unifiées utilisent cet enregistrement pour se connecter au proxy inverse. Pour plus d’informations, reportez-vous à la rubrique <a href="lync-server-2013-determine-dns-requirements.md">determine DNS Requirements for Lync Server 2013</a> dans la documentation de planification.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

