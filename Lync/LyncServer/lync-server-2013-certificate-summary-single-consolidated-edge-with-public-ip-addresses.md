---
title: "Lync Server 2013 : Résumé des certif. - SE unique cons. avec adr. IP publiques"
TOCTitle: Résumé des certificats - Serveur Edge unique consolidé avec adresses IP publiques
ms:assetid: 25b8ae7a-e5a0-43c0-92ae-7e144d5e4a36
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204747(v=OCS.15)
ms:contentKeyID: 49296610
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Résumé des certificats - Serveur Edge unique consolidé avec adresses IP publiques dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

Microsoft Lync Server 2013 utilise des certificats pour authentifier mutuellement les autres serveurs et chiffrer les données de serveur à serveur et de serveur à client. Les certificats nécessitent la correspondance des noms des enregistrements DNS (domain name system) associés aux serveurs, aux nom de sujet (SN) et autre nom de sujet (SAN) indiqués sur le certificat. Pour mapper correctement les serveurs, les enregistrements DNS et les entrées de certificat, vous devez attentivement planifier vos noms de domaine complets de serveur voulus, tels qu’indiqués dans les entrées DNS, SN et SAN du certificat.

Le certificat affecté aux interfaces externes du serveur Edge est demandé auprès d’une autorité de certification (AC) publique. Celles qui réussissent à fournir des certificats aux fins de Communications unifiées sont répertoriées dans l’article suivant : [http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=929395](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=929395) Lors de la demande du certificat, vous pouvez utiliser celle générée par le Assistant Déploiement de Lync Server ou la créer manuellement, ou via un processus fourni par la AC publique. Le certificat est affecté aux interfaces service Edge d’accès et service Edge de conférence web, ainsi qu’au service d’authentification audio/vidéo (à ne pas confondre avec le service Edge A/V, qui n’utilise aucun certificat pour crypter les flux audio et vidéo). L’interface serveur Edge peut utiliser un certificat provenant d’une AC interne (pour votre organisation) ou publique. Le certificat de l’interface interne utilise uniquement le nom de sujet et n’exige ni n’utilise aucune entrée SAN.

> [!NOTE]  
> Le tableau ci-dessous montre une seconde entrée SIP (sip.fabrikam.com) dans la liste des autres noms de sujets pour référence. Pour chaque domaine SIP de votre entreprise, vous devez ajouter un nom de domaine complet correspondant répertorié dans la liste des autres noms de sujets du certificat.

## Certificats requis pour un serveur Edge consolidé unique avec adresses IP publiques


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
<th>Nom du sujet (SN)</th>
<th>Autres noms de sujets (SAN)/Ordre</th>
<th>Commentaires</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Serveur Edge consolidé unique (serveur Edge externe)</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>webcon.contoso.com</p>
<p>sip.contoso.com</p>
<p>sip.fabrikam.com</p></td>
<td><p>Le certificat doit émaner d’une autorité de certification publique et doit avoir les EKU (utilisation avancée de la clé) serveur et client si la solution PIC (Public IM Connectivity) avec AOL doit être déployée. Le certificat est attribué aux interfaces Edge externes pour :</p><ul><li><p>Serveur Edge d’accès</p></li><li><p>Serveur Edge de conférence</p></li><li><p>Edge A/V</p></li></ul>
<p>Notez que les autres noms de sujet sont automatiquement ajoutés au certificat en fonction de vos définitions dans le générateur de topologie. Vous ajoutez les entrées d’autres noms de sujet dont vous avez besoin pour les domaines SIP supplémentaires, ainsi que d’autres entrées que vous devez prendre en charge. Le nom de sujet est répliqué dans l’autre nom de sujet et doit être présent pour un fonctionnement correct.</p></td>
</tr>
<tr class="even">
<td><p>Serveur Edge consolidé unique (serveur Edge interne)</p></td>
<td><p>lsedge.contoso.net</p></td>
<td><p>Aucun SAN requis</p></td>
<td><p>Le certificat peut être émis par une autorité de certification privée ou publique et doit contenir l’EKU du serveur. Le certificat est attribué à l’interface Edge interne.</p></td>
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
<td><p>Serveur Edge d’accès/périmètre externe</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>sip.contoso.com</p>
<p>webcon.contoso.com</p>
<p>sip.fabrikam.com</p></td>
<td><p>Le certificat doit émaner d’une autorité de certification publique et doit avoir les EKU (utilisation avancée de la clé) serveur et client si la solution PIC (Public IM Connectivity) avec AOL doit être déployée. Le certificat est attribué aux interfaces Edge externes pour :</p><ul><li><p>Serveur Edge d’accès</p></li><li><p>Serveur Edge de conférence</p></li><li><p>Edge A/V</p></li></ul>
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

