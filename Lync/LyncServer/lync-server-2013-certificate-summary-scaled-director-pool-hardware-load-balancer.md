---
title: "Lync Server 2013 : Résumé des cert. - Pool dir. màé, équil. de ch. matérielle"
TOCTitle: Résumé des certificats - Pool directeur mis à l’échelle, équilibreur de charge matérielle
ms:assetid: 45940add-8027-418d-b79a-9033b494762f
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204846(v=OCS.15)
ms:contentKeyID: 49297071
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Résumé des certificats - Pool directeur mis à l’échelle, équilibreur de charge matérielle dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

Les exigences relatives aux certificats d’un directeur avec un appareil d’équilibrage de charge impliquent l’utilisation d’un certificat par défaut ayant un nom d’objet et d’autres noms de l’objet pour les services que le pool de directeurs peut recevoir. Un certificat est demandé pour chaque directeur du pool. En outre, un certificat de jeton OAuth pour les authentifications de serveur à serveur est installé sur chaque serveur.

### Certificats pour un directeur ayant fait l’objet d’une montée en charge via un appareil d’équilibrage de charge

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
<th>Autres noms du sujet (SAN)</th>
<th>Commentaires</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Par défaut</p></td>
<td><p>dirpool01.contoso.net</p></td>
<td><p>dirpool01.contoso.net</p>
<p>dir01.contoso.net</p>
<p>dialin.contoso.com</p>
<p>meet.contoso.com</p>
<p>lyncdiscoverinternal.contoso.com</p>
<p>lyncdiscover.contoso.com</p>
<p>(Facultatif) *.contoso.com</p></td>
<td><p>Il est possible de demander des certificats de directeur depuis une autorité de certification gérée en interne ou depuis une autorité de certification publique.</p>
<p>Le directeur répond aux demandes à partir du proxy inverse dans le périmètre ou à partir du serveur Edge.</p>
<p>Ou, une entrée de caractère générique pour les URL simples</p></td>
</tr>
<tr class="even">
<td><p>OAuthTokenIssuer</p></td>
<td><p>dir01.contoso.net</p></td>
<td><p>Aucune entrée</p></td>
<td>

> [!IMPORTANT]  
> Notez que la longueur de clé minimale s’élève à 1 024 bits ; toutefois, vous pouvez recevoir un avertissement indiquant que la longueur de clé minimale recommandée s’élève à 2 048 bits.

<p>Le certificat OAuthTokenIssuer est un certificat à usage unique qui permet d’authentifier des serveurs dans un environnement à grande échelle ; il peut être demandé auprès d’une autorité de certification interne ou publique. Ce certificat est obligatoire.</p></td>
</tr>
</tbody>
</table>

