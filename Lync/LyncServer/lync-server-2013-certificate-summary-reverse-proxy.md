---
title: 'Lync Server 2013 : Résumé des certificats-proxy inverse'
description: 'Lync Server 2013 : Résumé des certificats-proxy inverse.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - Reverse proxy
ms:assetid: f2b9a53f-aead-413d-81e9-4a294a010fbb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205381(v=OCS.15)
ms:contentKeyID: 48185820
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0cc250d6de2eb1a0b6c3ad3495c8df62942f9a81
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572300"
---
# <a name="certificate-summary---reverse-proxy-in-lync-server-2013"></a>Résumé des certificats-proxy inverse dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-11-14_

Les exigences de certificat pour le proxy inverse sont plus simples que celles des serveurs Edge. Le diagramme de flux fourni présente les conditions requises. Le tableau associé présente le nom de sujet du certificat et les autres noms du sujet par rapport aux scénarios que nous avons consultés dans les discussions de serveur Edge. Pour plus d’informations sur les scénarios de serveur Edge, voir [Scenarios for External User Access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).

**Organigramme des certificats pour le proxy inverse**

![Organigramme des certificats pour le serveur Edge](images/JJ205381.026045d7-1b4b-4651-b32f-2d43a7161198(OCS.15).jpg "Organigramme des certificats pour le serveur Edge")

### <a name="reverse-proxy-external-interface"></a>Proxy inverse : interface externe

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Composant</th>
<th>Nom du sujet</th>
<th>Autre nom de l’objet (SAN)/Order</th>
<th>Comments</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Proxy inverse</p></td>
<td><p>webext.contoso.com</p></td>
<td><p>webext.contoso.com</p>
<p>webdirext.contoso.com</p>
<p>dialin.contoso.com</p>
<p>meet.contoso.com</p>
<p>officewebapps01.contoso.com</p>
<p>lyncdiscover.contoso.com</p>
<p>(Facultatif) :*. contoso.com</p></td>
<td><p>Le certificat doit être émis par une autorité de certification publique et avec l’utilisation améliorée de l’extension serveur. Les services incluent le service de carnet d’adresses, le développement de groupes de distribution Office Web Apps pour les conférences et les règles de publication d’appareils IP Lync. Les autres noms de sujet incluent :</p>
<ul>
<li><p>Nom de domaine complet externe des services Web pour le serveur frontal ou le pool frontal</p></li>
<li><p>Nom de domaine complet externe des services Web pour le directeur ou le pool directeur</p></li>
<li><p>Conférence rendez-vous</p></li>
<li><p>Règle de publication de réunion en ligne</p></li>
<li><p>Office Web Apps pour les conférences</p></li>
<li><p>Lyncdiscover (découverte automatique)</p></li>
</ul>
<p>Le caractère générique facultatif remplace le SAN de conférence et de numérotation.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

