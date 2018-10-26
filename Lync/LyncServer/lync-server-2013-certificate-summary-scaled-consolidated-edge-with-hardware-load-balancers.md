---
title: "Lync Server 2013 : Résumé des cert. - SE cons. màé avec des éq. de ch. mat."
TOCTitle: Résumé des certificats - Serveur Edge consolidé mis à l’échelle avec des équilibreurs de charge matérielle
ms:assetid: 894a9f3e-7cba-4915-8fdf-e52f2f25126f
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398692(v=OCS.15)
ms:contentKeyID: 49297978
ms.date: 12/17/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Résumé des certificats - Serveur Edge consolidé mis à l’échelle avec des équilibreurs de charge matérielle dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2016-12-15_

Microsoft Lync Server 2013 utilise des certificats pour authentifier mutuellement les autres serveurs et chiffrer les données de serveur à serveur et de serveur à client. Les certificats nécessitent la correspondance des noms des enregistrements DNS (domain name system) associés aux serveurs, aux nom de sujet (SN) et autre nom de sujet (SAN) indiqués sur le certificat. Pour mapper correctement les serveurs, les enregistrements DNS et les entrées de certificat, vous devez attentivement planifier vos noms de domaine complets de serveur voulus, tels qu’indiqués dans les entrées DNS, SN et SAN du certificat.

Le certificat attribué aux interfaces externes du serveur Edge est requis de la part d’une autorité de certification publique. Les autorités de certification publique ayant réussi à fournir des certificats aux fins de Communications unifiées sont répertoriées dans l’article suivant : [http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=929395](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=929395). Pour demander un certificat, vous pouvez utiliser la demande de certificat générée par l’Assistant Déploiement de Lync Server ou créée manuellement ou via un processus fourni par l’autorité de certification publique. Le certificat est attribué aux interfaces service Edge d’accès et service Edge de conférence web, ainsi qu’au service d’authentification Audio/vidéo (à ne pas confondre avec le service Edge A/V, qui n’utilise pas de certificat pour chiffrer les flux audio et vidéo). L’interface serveur Edge peut utiliser un certificat émis par une autorité de certification interne (à votre organisation) ou une autorité de certification publique. Le certificat de l’interface interne utilise uniquement le nom de sujet et n’exige ni n’utilise aucune entrée d’autre nom de sujet.

> [!NOTE]  
> Le tableau ci-dessous montre une seconde entrée SIP (sip.fabrikam.com) dans la liste des autres noms de sujets pour référence. Pour chaque domaine SIP de votre entreprise, vous devez ajouter un nom de domaine complet correspondant répertorié dans la liste des autres noms de sujets du certificat.

## Certificats requis pour le serveur Edge consolidé ajusté avec équilibreurs de charge matérielle


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
<th>Autres noms de sujets (SAN)/Ordre</th>
<th>Commentaires</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>serveur Edge consolidé (Edge externe)</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>webcon.contoso.com</p>
<p>sip.contoso.com</p>
<p>sip.fabrikam.com</p></td>
<td><p>Le certificat doit émaner d’une autorité de certification publique, et doit avoir les EKU (utilisation avancée de la clé) de serveur et de client si la solution PIC (Public IM Connectivity) avec AOL doit être déployée. De plus, pour les serveurs Edge à l’échelle, la clé privée du certificat doit être exportable, et le certificat et la clé privée doivent être copiés dans chaque serveur Edge. Le certificat est attribué aux interfaces Edge externes pour :</p><ul><li><p>service Edge d’accès</p></li><li><p>service Edge de conférence web</p></li><li><p>service Edge A/V</p></li></ul>
<p>Notez que les autres noms de sujet sont automatiquement ajoutés au certificat en fonction de vos définitions dans le générateur de topologie. Vous ajoutez les entrées d’autres noms de sujet dont vous avez besoin pour les domaines SIP supplémentaires, ainsi que d’autres entrées que vous devez prendre en charge. Le nom de sujet est répliqué dans l’autre nom de sujet et doit être présent pour un fonctionnement correct.</p></td>
</tr>
<tr class="even">
<td><p>serveur Edge consolidé (Edge interne)</p></td>
<td><p>lsedge.contoso.net</p></td>
<td><p>Aucun SAN requis</p></td>
<td><p>Le certificat peut être émis par une autorité de certification publique ou privée et il doit contenir l’utilisation améliorée de la clé du serveur. Il est affecté à l’interface serveur Edge interne</p></td>
</tr>
</tbody>
</table>


## Résumé du certificat – PIC (Public Instant Messaging Connectivity)


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
<th>Autres noms de sujets (SAN)/Ordre</th>
<th>Commentaires</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Externe/ service Edge d’accès</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>sip.contoso.com</p>
<p>webcon.contoso.com</p>
<p>sip.fabrikam.com</p></td>
<td><p>Le certificat doit émaner d’une autorité de certification publique et doit avoir les EKU (utilisation avancée de la clé) serveur et client si la solution PIC (Public IM Connectivity) avec AOL doit être déployée. Le certificat est attribué aux interfaces Edge externes pour :</p><ul><li><p>service Edge d’accès</p></li><li><p>service Edge de conférence web</p></li><li><p>service Edge A/V</p></li></ul>
<p>Notez que les autres noms de sujet sont automatiquement ajoutés au certificat en fonction de vos définitions dans le générateur de topologie. Vous ajoutez les entrées d’autres noms de sujet dont vous avez besoin pour les domaines SIP supplémentaires, ainsi que d’autres entrées que vous devez prendre en charge. Le nom de sujet est répliqué dans l’autre nom de sujet et doit être présent pour un fonctionnement correct.</p></td>
</tr>
</tbody>
</table>


## Résumé de certificat pour XMPP (Extensible Messaging and Presence Protocol)


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
<th>Autres noms de sujets (SAN)/Ordre</th>
<th>Commentaires</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Attribuer au service Edge d’accès des serveur Edge ou du pool de serveurs Edge</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>webcon.contoso.com</p>
<p>sip.contoso.com</p>
<p>sip.fabrikam.com</p>
<p>xmpp.contoso.com</p>
<p><strong>*.contoso.com</strong></p></td>
<td><p>Les trois premières entrées SAN sont les entrées SAN normales pour un serveur Edge complet. L’entrée contoso.com est requise pour la fédération avec le partenaire XMPP au niveau du domaine racine. Cette entrée active XMPP pour tous les domaines ayant comme suffixe *.contoso.com.</p></td>
</tr>
</tbody>
</table>

