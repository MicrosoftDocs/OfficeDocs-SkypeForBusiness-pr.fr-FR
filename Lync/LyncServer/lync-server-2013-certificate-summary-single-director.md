---
title: 'Lync Server 2013 : Résumé des certificats - Directeur unique'
TOCTitle: Résumé des certificats - Directeur unique
ms:assetid: 1b769a76-cbf3-46e9-a955-f6cde5faff93
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204720(v=OCS.15)
ms:contentKeyID: 49296409
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Résumé des certificats - Directeur unique dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

Les certificats requis pour un seul directeur se composent d’un certificat par défaut doté d’un nom de sujet et d’autres noms de sujet pour les services que le directeur peut recevoir. Il existe en outre un certificat de jeton OAuth servant à l’authentification de serveur à serveur.

### Certificats pour le directeur

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
<td><p>dir01.contoso.net</p></td>
<td><p>dir01.contoso.net</p>
<p>dialin.contoso.com</p>
<p>meet.contoso.com</p>
<p>lyncdiscoverinternal.contoso.com</p>
<p>lyncdiscover.contoso.com</p>
<p>(Facultatif) *.contoso.com</p></td>
<td><p>Il est possible de demander des certificats de directeur depuis une autorité de certification gérée en interne ou depuis une autorité de certification publique.</p>
<p>Le directeur répond aux demandes à partir du proxy inverse dans le périmètre ou à partir du serveur Edge. Les clients internes n’utilisent pas le directeur.</p>
<p>Ou, une entrée de caractère générique pour les URL simples</p></td>
</tr>
<tr class="even">
<td><p>OAuthTokenIssuer</p></td>
<td><p>dir01.contoso.net</p></td>
<td><p>Aucune entrée</p></td>
<td>

> [!IMPORTANT]  
> Notez que la longueur de clé minimale s’élève à 1 024 bits ; toutefois, vous pouvez recevoir un avertissement indiquant que la longueur de clé minimale recommandée s’élève à 2 048 bits.

<p>Le certificat OAuthTokenIssuer est un certificat à usage unique qui permet d’authentifier des serveurs dans un environnement à grande échelle ; il peut être demandé auprès d’une autorité de certification interne ou publique. Ce certificat est obligatoire.</p>
<p></p></td>
</tr>
</tbody>
</table>

