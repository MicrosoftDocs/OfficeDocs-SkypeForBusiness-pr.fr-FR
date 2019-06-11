---
title: 'Lync Server 2013: Résumé du certificat-découverte automatique'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Certificate summary - Autodiscover
ms:assetid: 16ac96bb-882a-4141-b75c-9530637548d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945616(v=OCS.15)
ms:contentKeyID: 51541451
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 59c3777f9b13dc18e3e52e80120009f93c20db3d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838656"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---autodiscover-in-lync-server-2013"></a>Résumé du certificat-découverte automatique dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-02-14_

Le service de découverte automatique de Lync Server 2013 s’exécute sur le directeur et les serveurs du pool frontal, et lorsqu’il est publié en DNS, il est possible d’utiliser les clients Lync pour localiser les services de serveur et d’utilisateur. Si vous effectuez une mise à niveau à partir de Lync Server 2010 et que vous n’avez pas déployé de mobilité, pour que les clients puissent utiliser la découverte automatique, vous devez modifier les listes de noms de remplacement du sujet du certificat sur tout directeur et serveur frontal exécutant le service de découverte automatique. Par ailleurs, il est possible que vous deviez modifier les listes nom de remplacement de l’objet sur les certificats utilisés pour les règles de publication de service Web externe sur les proxys inverses.

La décision concernant l’utilisation des listes de noms de substitution sur les proxys inverse est basée sur le fait que vous publiez le service de découverte automatique sur le port 80 ou sur le port 443:

  - **Publié sur le port 80**   , aucune modification de certificat n’est requise si la requête initiale au service de découverte automatique a lieu sur le port 80. En effet, les appareils mobiles exécutant Lync accèdent au proxy inverse sur le port 80 en externe, puis ils sont connectés à un serveur directeur ou frontal sur le port 8080 en interne. Pour plus d’informations, consultez la section exigences techniques de découverte automatique à l’aide de port 80» [pour la mobilité dans Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).

  - **Publié sur le port 443**   la liste autre nom de l’objet sur les certificats utilisés par la règle de publication des services Web externes doit contenir un *lyncdiscover.\< entrée\> sipdomain* pour chaque domaine SIP au sein de votre organisation.
    
    <div>
    

    > [!IMPORTANT]  
    > Nous vous recommandons vivement d’utiliser HTTPs sur HTTP. HTTPs utilise des certificats pour chiffrer le trafic. HTTP ne permet pas d’effectuer le chiffrement et les données envoyées seront au format texte brut.

    
    </div>

La réémission de certificats à l’aide d’une autorité de certification interne est généralement un processus simple. En revanche, pour les certificats publics utilisés sur la règle de publication de service Web, l’ajout de plusieurs entrées de nom de domaine alternatif peut devenir coûteux. Pour contourner ce problème, nous prenons en charge la connexion automatique de découverte automatique sur le port 80, qui est ensuite redirigée vers le port 8080 du directeur ou du serveur principal.

<div>


> [!NOTE]  
> Si votre infrastructure Lync Server 2013 utilise des certificats internes émis auprès d’une autorité de certification interne et que vous envisagez de prendre en charge les appareils mobiles qui se connectent sans fil, soit la chaîne de certificats racine de l’autorité de certification interne doit être installée sur les appareils mobiles ou vous devez changer de certificat public sur votre infrastructure Lync Server 2013.



</div>

Cette rubrique décrit les noms de remplacement d’objet ajoutés requis pour le directeur, le serveur frontal et le proxy inverse. Seuls les noms d’autres noms d’objet. Reportez-vous aux sections planification pour plus d’informations sur les autres entrées des certificats. Pour plus d’informations, reportez-vous à [la rubrique scénarios pour le directeur dans Lync server 2013](lync-server-2013-scenarios-for-the-director.md), [scénarios d’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md)et [scénarios de proxy inverse dans Lync Server 2013](lync-server-2013-scenarios-for-reverse-proxy.md).

Les tableaux suivants définissent les entrées du SAN de découverte automatique pour le pool de directeurs, le pool frontal et le proxy inverse:

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
<td><p>SAN = lyncdiscoverinternal. &lt;nom de domaine interne&gt;</p></td>
</tr>
<tr class="even">
<td><p>URL du service de découverte automatique externe</p></td>
<td><p>SAN = lyncdiscover. &lt;sipdomain&gt;</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Vous attribuez le certificat qui vient d’être mis à jour avec la nouvelle entrée SAN au certificat par défaut. Vous pouvez également utiliser le SAN = *. &lt;sipdomain&gt;.



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
<td><p>SAN = lyncdiscoverinternal. &lt;nom de domaine interne&gt;</p></td>
</tr>
<tr class="even">
<td><p>URL du service de découverte automatique externe</p></td>
<td><p>SAN = lyncdiscover. &lt;sipdomain&gt;</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Vous attribuez le certificat qui vient d’être mis à jour avec la nouvelle entrée SAN au certificat par défaut. Vous pouvez également utiliser le SAN = *. &lt;sipdomain&gt;



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
> Vous attribuez le certificat récemment mis à jour avec la nouvelle entrée SAN à l’écouteur SSL du proxy inverse.



</div>

</div>

<span> </span>

</div>

</div>

</div>

