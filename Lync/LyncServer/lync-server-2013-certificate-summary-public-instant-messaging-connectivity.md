---
title: Résumé des certificats - Connectivité PIC (Public IM Connectivity)
TOCTitle: Résumé des certificats - Connectivité PIC (Public IM Connectivity)
ms:assetid: 2b3687ee-50c2-4c1c-880e-8dcf8bd4f309
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ618370(v=OCS.15)
ms:contentKeyID: 49296706
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Résumé des certificats - Connectivité PIC (Public IM Connectivity)

 

_**Dernière rubrique modifiée :** 2015-03-09_

Avant de configurer des certificats pour la connectivité PIC (Public IM Connectivity), notez qu’ils ne sont en rien différents des certificats des autres types de fédération SIP ou même des certificats de serveur Edge standard. La seule exception concerne America Online qui nécessite une configuration de certificat unique. Outre l’utilisation améliorée de la clé du serveur habituelle, America Online nécessite requiert du ou des certificats (dans le cas d’un pool de serveurs Edge) qu’ils contiennent également l’utilisation améliorée de la clé du client. Cette dernière constitue un ajout au certificat et fait partie du certificat public externe attribué à votre serveur Edge.

## Résumé du certificat – Connectivité PIC (Public IM Connectivity)


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
<th>Autres noms du sujet (SAN)/Ordre</th>
<th>Commentaires</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Serveur Edge externe/d’accès</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>sip.contoso.com</p>
<p>webcon.contoso.com</p>
<p>sip.fabrikam.com</p></td>
<td><p>Le certificat doit provenir d’une autorité de certification publique et comporter l’utilisation améliorée de la clé du serveur et l’utilisation améliorée de la clé du client si la connectivité PIC (Public IM Connectivity) avec AOL doit être déployée. Le certificat est attribué aux interfaces de serveur Edge externes pour :</p>
<ul>
<li><p>service Edge d’accès</p></li>
<li><p>service Edge de conférence web</p></li>
<li><p>service Edge A/V</p></li>
</ul>
<p>Notez que les autres noms du sujet sont automatiquement ajoutés au certificat en fonction de vos définitions dans le Générateur de topologie. Vous ajoutez des entrées SAN selon les besoins liés aux autres domaines SIP et entrées que vous devez prendre en charge. Le nom du sujet est répliqué dans l’autre nom du sujet et doit être présent pour assurer un fonctionnement correct.</p></td>
</tr>
</tbody>
</table>


## Voir aussi

#### Concepts

[Scénarios d’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md)

