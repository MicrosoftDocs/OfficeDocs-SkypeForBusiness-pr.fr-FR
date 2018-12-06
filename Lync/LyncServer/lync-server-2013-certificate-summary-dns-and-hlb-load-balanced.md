---
title: "Lync Server 2013 : Résumé des certificats - Équilibrage de ch. DNS et mat."
TOCTitle: Résumé des certificats - Équilibrage de charge DNS et matérielle
ms:assetid: 8318a1a4-b423-47b7-95e6-9541adfad391
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205047(v=OCS.15)
ms:contentKeyID: 49297911
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Résumé des certificats - Équilibrage de charge DNS et matérielle dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

La configuration requise du certificat pour un directeur avec équilibrage de charge DNS et un équilibreur de charge matérielle utilisera un certificat par défaut avec un nom de sujet et d’autres noms de sujet pour les services que le directeur peut recevoir. Un certificat est demandé pour chaque directeur du pool. Il ne faut pas oublier que l’équilibreur de charge matérielle équilibre la charge uniquement pour le trafic du proxy inverse. De plus, un certificat de jeton OAuth pour le processus d’authentification serveur à serveur existe qui est installé sur chaque serveur.

### Certificats pour directeur

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

<p>Le certificat OAuthTokenIssuer est un certificat à usage unique qui permet d’authentifier des serveurs dans un environnement à grande échelle ; il peut être demandé auprès d’une autorité de certification interne ou publique. Ce certificat est obligatoire.</p></td>
</tr>
</tbody>
</table>

