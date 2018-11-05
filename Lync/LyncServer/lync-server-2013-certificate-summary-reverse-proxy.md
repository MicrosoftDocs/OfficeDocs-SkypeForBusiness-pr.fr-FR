---
title: 'Lync Server 2013 : Résumé des certificats - Proxy inverse'
TOCTitle: Résumé des certificats - Proxy inverse
ms:assetid: f2b9a53f-aead-413d-81e9-4a294a010fbb
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205381(v=OCS.15)
ms:contentKeyID: 49299307
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Résumé des certificats - Proxy inverse dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

Les exigences en matière de certificats pour le proxy inverse sont plus simples que celles des serveurs Edge. L’organigramme fourni présente les conditions requises. Le tableau qui l’accompagne présente les noms de sujets de certificats typiques et les autres noms de sujets liés aux scénarios présentés dans les discussions sur le serveur Edge. Pour plus d’informations sur les scénarios de serveur Edge, reportez-vous à [Scénarios d’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).

**Organigramme des certificats pour le proxy inverse**

![Diagramme de certificats pour le serveur Edge](images/JJ205381.026045d7-1b4b-4651-b32f-2d43a7161198(OCS.15).jpg "Diagramme de certificats pour le serveur Edge")

### Proxy inverse : interface externe

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
<th>Autre nom de sujet/commande</th>
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
<p>(Facultatif) : *.contoso.com</p></td>
<td><p>Le certificat doit être émis par une autorité de certification publique et avec l’utilisation améliorée de la clé du serveur. Les services incluent un service de carnet d’adresses, un développement de groupe de distribution Office Web Apps pour la conférence et des règles de publication de périphérique IP Lync. L’autre nom de sujet inclut :</p>
<ul>
<li><p>Le nom de domaine complet (FQDN) pour serveur frontal ou pool de serveurs frontaux</p></li>
<li><p>FQDN des services web externes pour directeur ou pool de directeurs</p></li>
<li><p>Conférence rendez-vous</p></li>
<li><p>Règle de publication de réunion en ligne</p></li>
<li><p>Office Web Apps pour la conférence</p></li>
<li><p>Lyncdiscover (Autodiscover)</p></li>
</ul>
<p>Le caractère générique facultatif remplace les autres noms de sujet meet et dialin à la fois.</p></td>
</tr>
</tbody>
</table>

