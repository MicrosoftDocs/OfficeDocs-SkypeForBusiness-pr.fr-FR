---
title: 'Lync Server 2013 : Exigences relatives aux certificats pour la mobilité'
TOCTitle: Exigences relatives aux certificats pour la mobilité
ms:assetid: bb0e97af-cf60-4271-a0ab-654429d884ea
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Hh690044(v=OCS.15)
ms:contentKeyID: 49298654
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Exigences relatives aux certificats pour la mobilité dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

Si vous déployez la fonctionnalité de mobilité et prenez en charge la découverte automatique pour les clients mobiles, vous devez inclure certaines entrée d’autres noms de sujet sur les certificats de manière prendre en charge les connexions sécurisées établies à partir de clients mobiles.

Vous devez inclure des entrées d’autres noms de sujet pour la découverte automatique sur les certificats suivants :

  - pool de directeurs

  - pool de serveurs frontaux

  - Proxy inverse

Cette section décrit les entrées d’autres noms de sujet requises sur vos certificats pour la découverte automatique.

> [!NOTE]  
> La réémission de certificats à l’aide d’une autorité de certification interne est généralement un processus simple, mais l’ajout de plusieurs entrées d’autres noms de sujet à des certificats publics utilisés par le proxy inverse peut être une opération coûteuse. Si vous avez de nombreux domaines SIP, ce qui rend l’ajout d’autres noms de sujet très coûteux, vous pouvez configurer le proxy inverse de façon à utiliser le protocole HTTP pour la demande initiale du service de découverte automatique, plutôt que le protocole HTTPS (configuration par défaut). Pour plus d’informations, reportez-vous à <a href="lync-server-2013-technical-requirements-for-mobility.md">Exigences techniques pour la mobilité dans Lync Server 2013</a>.

### Exigences relatives au certificat du pool directeur

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Description</th>
<th>Entrée d’autre nom de sujet</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>URL du service de découverte automatique interne</p></td>
<td><p>SAN=lyncdiscoverinternal.&lt;domaineSIP&gt;</p></td>
</tr>
<tr class="even">
<td><p>URL du service de découverte automatique externe</p></td>
<td><p>SAN=lyncdiscover.&lt;domaineSIP&gt;</p></td>
</tr>
</tbody>
</table>


> [!NOTE]  
> Vous pouvez également utiliser SAN=*.&lt;domaineSIP&gt;

### Exigences relatives au certificat du pool frontal

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Description</th>
<th>Entrée d’autre nom de sujet</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>URL du service de découverte automatique interne</p></td>
<td><p>SAN=lyncdiscoverinternal.&lt;domaineSIP&gt;</p></td>
</tr>
<tr class="even">
<td><p>URL du service de découverte automatique externe</p></td>
<td><p>SAN=lyncdiscover.&lt;domaineSIP&gt;</p></td>
</tr>
</tbody>
</table>


> [!NOTE]  
> Vous pouvez également utiliser SAN=*.&lt;domaineSIP&gt;

### Exigences relatives au certificat de proxy inverse (autorité de certification publique)

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Description</th>
<th>Entrée d’autre nom de sujet</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>URL du service de découverte automatique externe</p></td>
<td><p>SAN=lyncdiscover.&lt;domaineSIP&gt;</p></td>
</tr>
</tbody>
</table>


> [!NOTE]  
> Vous affecté cet autre nom d’objet (SAN) au certificat affecté à l’écouteur SSL sur le proxy inverse.

> [!NOTE]  
> Votre écouteur de proxy inverse aura d’autres noms d’objets pour vos URL des services web externes (par exemple, SAN=lyncwebextpool01.contoso.com), et dirwebexternal.contoso.com si vous avez déployé le directeur facultatif).
