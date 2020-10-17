---
title: 'Lync Server 2013 : exigences en matière de certificats pour la mobilité'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate requirements for mobility
ms:assetid: bb0e97af-cf60-4271-a0ab-654429d884ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690044(v=OCS.15)
ms:contentKeyID: 48185251
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 87657340205722a721485f213029220641885075
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533391"
---
# <a name="certificate-requirements-for-mobility-in-lync-server-2013"></a>Exigences relatives aux certificats pour la mobilité dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-06-24_

Si vous déployez la fonctionnalité de mobilité et prenez en charge la découverte automatique pour les clients mobiles, vous devez inclure certaines entrée d’autres noms de sujet sur les certificats de manière prendre en charge les connexions sécurisées établies à partir de clients mobiles.

Vous devez inclure des entrées d’autres noms de sujet pour la découverte automatique sur les certificats suivants :

  - pool directeur

  - pool frontal

  - Proxy inverse

Cette section décrit les entrées d’autres noms de sujet requises sur vos certificats pour la découverte automatique.

<div>


> [!NOTE]  
> La réémission de certificats à l’aide d’une autorité de certification interne est généralement un processus simple, mais l’ajout de plusieurs entrées d’autres noms de sujet à des certificats publics utilisés par le proxy inverse peut être une opération coûteuse. Si vous avez de nombreux domaines SIP, ce qui rend l’ajout d’autres noms de sujet très coûteux, vous pouvez configurer le proxy inverse de façon à utiliser le protocole HTTP pour la demande initiale du service de découverte automatique, plutôt que le protocole HTTPS (configuration par défaut). Pour plus d’informations, voir <A href="lync-server-2013-technical-requirements-for-mobility.md">Technical Requirements for Mobility in Lync Server 2013</A>.



</div>

### <a name="director-pool-certificate-requirements"></a>Exigences relatives au certificat du pool directeur

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
<td><p>SAN = lyncdiscoverinternal. &lt; sipdomain&gt;</p></td>
</tr>
<tr class="even">
<td><p>URL du service de découverte automatique externe</p></td>
<td><p>SAN = lyncdiscover. &lt; sipdomain&gt;</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Vous pouvez également utiliser le SAN = *. &lt; sipdomain&gt;



</div>

### <a name="front-end-pool-certificate-requirements"></a>Exigences relatives au certificat du pool frontal

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
<td><p>SAN = lyncdiscoverinternal. &lt; sipdomain&gt;</p></td>
</tr>
<tr class="even">
<td><p>URL du service de découverte automatique externe</p></td>
<td><p>SAN = lyncdiscover. &lt; sipdomain&gt;</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Vous pouvez également utiliser le SAN = *. &lt; sipdomain&gt;



</div>

### <a name="reverse-proxy-public-ca-certificate-requirements"></a>Exigences relatives au certificat de proxy inverse (autorité de certification publique)

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
<td><p>SAN = lyncdiscover. &lt; sipdomain&gt;</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Vous affecté cet autre nom d’objet (SAN) au certificat assigné à l’écouteur SSL sur le proxy inverse.



</div>

<div>


> [!NOTE]  
> Votre écouteur de proxy inverse aura des noms d’objet alternatifs pour vos URL de services Web externes (par exemple, SAN = lyncwebextpool01. contoso. com et dirwebexternal.contoso.com si vous avez déployé le directeur facultatif).



</div>

</div>

<span> </span>

</div>

</div>

</div>

