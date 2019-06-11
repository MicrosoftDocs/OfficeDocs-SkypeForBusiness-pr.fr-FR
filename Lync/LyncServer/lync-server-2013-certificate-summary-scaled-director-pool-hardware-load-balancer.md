---
title: Résumé des certificats - Pool directeur mis à l’échelle, équilibreur de charge matérielle
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Certificate summary - Scaled Director pool, hardware load balancer
ms:assetid: 45940add-8027-418d-b79a-9033b494762f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204846(v=OCS.15)
ms:contentKeyID: 48183992
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 21b1688641d09e00c82ea952d57bd2a9547ac0dd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838626"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---scaled-director-pool-hardware-load-balancer-in-lync-server-2013"></a>Résumé des certificats - Pool directeur mis à l’échelle, équilibreur de charge matérielle dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-20_

Les exigences en matière de certificat pour un directeur avec un dispositif d’équilibrage de la charge matérielle utiliseront un certificat par défaut dont le nom du sujet comporte le nom de l’objet et des noms de remplacement pour les services que le pool de réalisateur peut recevoir. Un certificat est demandé pour chaque réalisateur du pool. De plus, il existe un certificat de jeton OAuth pour les rôles d’authentification de serveur à serveur qui est installé sur chaque serveur.

### <a name="certificates-for-a-scaled-director-using-a-hardware-load-balancer"></a>Certificats pour un directeur mis à l’échelle à l’aide d’un équilibreur de charge matérielle

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
<th>Autres noms d’objet (SAN)</th>
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
<p>(Facultatif) *. contoso.com</p></td>
<td><p>Les certificats de réalisateur peuvent être demandés auprès d’une autorité de certification (CA) gérée en interne ou auprès d’une autorité de certification publique.</p>
<p>Le directeur répond aux requêtes du proxy inverse dans le périmètre ou du serveur Edge.</p>
<p>Ou une entrée de caractère générique pour les URL simples</p></td>
</tr>
<tr class="even">
<td><p>OAuthTokenIssuer</p></td>
<td><p>dir01.contoso.net</p></td>
<td><p>Aucune entrée</p></td>
<td>


> [!IMPORTANT]
> Notez que la longueur de la clé minimum est de 1024, mais vous pouvez recevoir un avertissement indiquant que la longueur de la clé minimum recommandée est 2048 bits.


<p>Le certificat OAuthTokenIssuer est un certificat à usage unique qui permet d’authentifier des serveurs dans un environnement à grande échelle et qui peut être demandé auprès d’une autorité de certification interne ou d’une autorité de certification publique. Le certificat est requis.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

