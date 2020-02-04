---
title: 'Lync Server 2013 : Exigences relatives aux certificats pour la mobilité'
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
ms.openlocfilehash: 680eaf205959b67d8fef93ff56d379ae8cd293bf
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736774"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-requirements-for-mobility-in-lync-server-2013"></a>Exigences relatives aux certificats pour la mobilité dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-06-24_

Si vous déployez la fonctionnalité de mobilité et que vous prenez en charge la découverte automatique pour les clients mobiles, vous devez inclure certaines entrées de nom alternatif de sujet sur les certificats pour la prise en charge de connexions sécurisées à partir des clients mobiles.

Vous devez inclure les autres entrées de nom de l’objet pour la découverte automatique sur les certificats suivants :

  - pool de directeurs

  - pool de serveurs frontaux

  - Proxy inverse

Cette section décrit les entrées de nom alternatif requises sur vos certificats pour une découverte automatique.

<div>


> [!NOTE]  
> La réémission de certificats à l’aide d’une autorité de certification interne correspond généralement à un processus simple, mais l’ajout de plusieurs entrées de nom de remplacement de sujet à des certificats publics utilisés par le proxy inverse peut être coûteux. Si vous avez de nombreux domaines SIP, le fait d’ajouter des noms de substitution d’objet très coûteux, vous pouvez configurer le proxy inverse pour qu’il utilise HTTP pour la demande de service de découverte automatique initiale au lieu d’utiliser HTTPs (configuration par défaut). Pour plus d’informations, voir <A href="lync-server-2013-technical-requirements-for-mobility.md">Configuration requise pour la mobilité dans Lync Server 2013</A>.



</div>

### <a name="director-pool-certificate-requirements"></a>Conditions requises pour le certificat de pool de réalisateur

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Description</th>
<th>Entrée de l’autre nom de l’objet</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>URL du service de découverte automatique interne</p></td>
<td><p>SAN = lyncdiscoverinternal. &lt;sipdomain&gt;</p></td>
</tr>
<tr class="even">
<td><p>URL du service de découverte automatique externe</p></td>
<td><p>SAN = lyncdiscover. &lt;sipdomain&gt;</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Vous pouvez également utiliser le SAN = *. &lt;sipdomain&gt;



</div>

### <a name="front-end-pool-certificate-requirements"></a>Conditions requises pour le certificat de pool frontal

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Description</th>
<th>Entrée de l’autre nom de l’objet</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>URL du service de découverte automatique interne</p></td>
<td><p>SAN = lyncdiscoverinternal. &lt;sipdomain&gt;</p></td>
</tr>
<tr class="even">
<td><p>URL du service de découverte automatique externe</p></td>
<td><p>SAN = lyncdiscover. &lt;sipdomain&gt;</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Vous pouvez également utiliser le SAN = *. &lt;sipdomain&gt;



</div>

### <a name="reverse-proxy-public-ca-certificate-requirements"></a>Conditions requises pour les certificats de proxy inverse (AC publique)

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Description</th>
<th>Entrée de l’autre nom de l’objet</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>URL du service de découverte automatique externe</p></td>
<td><p>SAN = lyncdiscover. &lt;sipdomain&gt;</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Vous attribuez ce SAN au certificat attribué à l’écouteur SSL sur le proxy inverse.



</div>

<div>


> [!NOTE]  
> Votre écouteur de proxy inverse aura des noms de remplacement pour vos URL de services Web externes (par exemple, SAN = lyncwebextpool01. contoso. com et dirwebexternal.contoso.com si vous avez déployé le réalisateur facultatif).



</div>

</div>

<span> </span>

</div>

</div>

</div>

