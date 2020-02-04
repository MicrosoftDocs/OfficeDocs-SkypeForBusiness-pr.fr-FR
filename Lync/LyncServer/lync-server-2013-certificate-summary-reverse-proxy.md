---
title: 'Lync Server 2013 : Résumé des certificats - Proxy inverse'
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
ms.openlocfilehash: 42e52fa8522de53404fee3f3b5798f159361dbf5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736614"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---reverse-proxy-in-lync-server-2013"></a>Résumé des certificats - Proxy inverse dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-11-14_

Les exigences de certificat pour le proxy inverse sont beaucoup plus simples que celles des serveurs de périphérie. L’organigramme fourni présente les exigences nécessaires. La table associée présente le nom du sujet du certificat standard et les noms de remplacement de l’objet par rapport aux scénarios que nous avons examinés dans les discussions du serveur Edge. Pour plus d’informations sur les scénarios de serveur Edge, voir [scénarios d’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).

**Diagramme de flux de certificats pour un proxy inverse**

![Diagramme de certificats pour le serveur Edge](images/JJ205381.026045d7-1b4b-4651-b32f-2d43a7161198(OCS.15).jpg "Diagramme de certificats pour le serveur Edge")

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
<th>Nom de l’objet</th>
<th>Autre nom de l’objet (SAN)/Order</th>
<th>Commentaires</th>
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
<td><p>Le certificat doit être émis par une autorité de certification publique et par l’utilisation améliorée du serveur. Services : service de carnet d’adresses, extension de groupe de distribution applications Web Office pour les conférences et règles de publication de périphériques IP Lync. Le nom alternatif de l’objet inclut :</p>
<ul>
<li><p>Nom de domaine complet des services Web externes pour le serveur frontal ou le pool frontal</p></li>
<li><p>Nom de domaine complet des services Web externes pour le directeur ou le pool de réalisateurs</p></li>
<li><p>Conférence rendez-vous</p></li>
<li><p>Règle de publication de réunion en ligne</p></li>
<li><p>Office Web Apps pour les conférences</p></li>
<li><p>Lyncdiscover (découverte automatique)</p></li>
</ul>
<p>Le caractère générique facultatif remplace les SAN de connexion et de numérotation.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

