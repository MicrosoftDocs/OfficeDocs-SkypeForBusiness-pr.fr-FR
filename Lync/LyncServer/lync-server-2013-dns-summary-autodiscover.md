---
title: 'Serveur Lync Server 2013 : Résumé DNS-découverte automatique'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Autodiscover
ms:assetid: b336a2ae-0e58-4b74-b606-aedbbd411587
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945644(v=OCS.15)
ms:contentKeyID: 51541504
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6ed7d6edb44ebca8656a50aec432fe3c0ac669d8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737344"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---autodiscover-in-lync-server-2013"></a>DNS Summary-découverte automatique dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-13_

La découverte automatique est un service flexible qui accepte les communications via HTTP ou HTTPs. Pour ce faire, le système de noms de domaine (DNS) et les certificats utilisés par les serveurs qui hébergent le service de découverte automatique doivent être correctement configurés. Les exigences en matière de certificats sont décrites dans [synthèse des certificats-découverte automatique dans Lync Server 2013](lync-server-2013-certificate-summary-autodiscover.md).

<div>


> [!IMPORTANT]  
> La logique de recherche DNS pour les clients du serveur Lync utilise un ordre de résolution spécifique. Vous devez toujours inclure le lyncdiscoverinternal. &lt;Domain&gt; et lyncdiscover. &lt;Domain&gt; de votre DNS. À l’exception du lyncdiscoverinternal. &lt;l'&gt; enregistrement du domaine entraîne l’échec de la connexion des clients internes aux services prévus ou la réception d’une réponse de découverte automatique incorrecte.



</div>

### <a name="internal-dns-records"></a>Enregistrements DNS internes

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Type d’enregistrement</th>
<th>Nom d’hôte</th>
<th>Résolu en</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CNAME</p></td>
<td><p>Lyncdiscoverinternal. &lt;nom de domaine interne&gt;</p></td>
<td><p>Nom de domaine complet (FQDN) des services Web internes de votre pool de Director, si vous en avez un ou pour votre pool frontal si vous n’avez pas de directeur.</p></td>
</tr>
<tr class="even">
<td><p>A (hôte, si IPv6, AAAA)</p></td>
<td><p>lyncdiscoverinternal. &lt;nom de domaine interne&gt;</p></td>
<td><p>Adresse IP des services Web internes (adresse IP virtuelle) si vous utilisez un équilibreur de charge, si vous en avez un, ou si vous n’avez pas de réalisateur, le cas échéant.</p></td>
</tr>
</tbody>
</table>


Vous devez créer un des enregistrements DNS externes suivants :

### <a name="external-dns-records"></a>Enregistrements DNS externes

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Type d’enregistrement</th>
<th>Nom d’hôte</th>
<th>Résolu en</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CNAME</p></td>
<td><p>lyncdiscover. &lt;sipdomain&gt;</p></td>
<td><p>Nom de domaine complet des services Web externes pour votre pool de directeurs, le cas échéant, ou pour votre pool frontal si vous n’avez pas de directeur.</p></td>
</tr>
<tr class="even">
<td><p>A (hôte, si IPv6, AAAA)</p></td>
<td><p>lyncdiscover. &lt;sipdomain&gt;</p></td>
<td><p>Adresse IP externe ou publique du proxy inverse.</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Le trafic externe traverse le proxy inverse.



</div>

<div>


> [!NOTE]  
> Les clients d’appareils mobiles ne prennent pas en charge plusieurs certificats SSL (Secure Sockets Layer) provenant de différents domaines. Par conséquent, la redirection CNAMe vers différents domaines n’est pas prise en charge sur HTTPs. Par exemple, un enregistrement CNAMe DNS pour lyncdiscover.contoso.com qui redirige vers une adresse de director.contoso.net n’est pas pris en charge sur HTTPs. Dans le cas d’une telle topologie, un client d’appareil mobile doit utiliser HTTP pour la première demande, de sorte que la redirection CNAMe soit résolue via HTTP. Les requêtes suivantes utilisent alors HTTPs. Pour prendre en charge ce scénario, vous devez configurer votre proxy inverse avec une règle de publication Web pour le port 80 (HTTP). Pour plus d’informations, reportez-vous à la section « pour créer une règle de publication Web pour le port 80 » dans <A href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">configuration du proxy inverse pour la mobilité dans Lync Server 2013</A>. La redirection CNAMe vers le même domaine est prise en charge sur HTTPs. Dans ce cas, le certificat du domaine de destination couvre le domaine d’origine.



</div>

<div>

## <a name="see-also"></a>Voir aussi


[Configuration du proxy inverse pour la mobilité dans Lync Server 2013](lync-server-2013-configuring-the-reverse-proxy-for-mobility.md)  


[Résumé du certificat-découverte automatique dans Lync Server 2013](lync-server-2013-certificate-summary-autodiscover.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

