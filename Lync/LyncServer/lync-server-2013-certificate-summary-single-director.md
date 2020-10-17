---
title: 'Lync Server 2013 : Résumé des certificats-directeur unique'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - Single Director
ms:assetid: 1b769a76-cbf3-46e9-a955-f6cde5faff93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204720(v=OCS.15)
ms:contentKeyID: 48183546
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ceb2543cece60a32c733d2efad6023fc30bb2bf6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48517931"
---
# <a name="certificate-summary---single-director-in-lync-server-2013"></a>Résumé des certificats-directeur unique dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-08_

Les certificats requis pour un seul directeur consistent en un certificat par défaut dont le nom d’objet et les autres noms de sujet pour les services que le directeur peut recevoir. Il existe en outre un certificat de jeton OAuth servant à l’authentification de serveur à serveur.

### <a name="certificates-for-director"></a>Certificats pour le directeur

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
<th>Comments</th>
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
<td><p>Les certificats directeurs peuvent être demandés auprès d’une autorité de certification gérée en interne ou auprès d’une autorité de certification publique.</p>
<p>Le directeur répond aux demandes du proxy inverse dans le périmètre ou à partir du serveur Edge. Les clients internes n’utiliseront pas le directeur.</p>
<p>Ou, une entrée de caractère générique pour les URL simples</p></td>
</tr>
<tr class="even">
<td><p>OAuthTokenIssuer</p></td>
<td><p>dir01.contoso.net</p></td>
<td><p>Aucune entrée</p></td>
<td><div>

> [!IMPORTANT]  
> Notez que la longueur de clé minimale s’élève à 1 024 bits ; toutefois, vous pouvez recevoir un avertissement indiquant que la longueur de clé minimale recommandée s’élève à 2 048 bits.


</div>
<p>Le certificat OAuthTokenIssuer est un certificat à usage unique qui permet d’authentifier des serveurs dans un environnement à grande échelle ; il peut être demandé auprès d’une autorité de certification interne ou publique. Ce certificat est obligatoire.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

