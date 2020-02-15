---
title: 'Lync Server 2013 : Résumé des certificats-découverte automatique'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - Autodiscover
ms:assetid: 16ac96bb-882a-4141-b75c-9530637548d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945616(v=OCS.15)
ms:contentKeyID: 51541451
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ae57440d4843151da61d24a9ff015778a5c65b07
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043986"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---autodiscover-in-lync-server-2013"></a>Résumé des certificats-découverte automatique dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-14_

Le service de découverte automatique Lync Server 2013 s’exécute sur les serveurs de pools frontaux et de directeurs et, lorsqu’il est publié dans DNS, peut être utilisé par les clients Lync pour localiser les services de serveur et d’utilisateur. Si vous effectuez une mise à niveau à partir de Lync Server 2010 et que vous n’avez pas déployé la mobilité, avant que les clients puissent utiliser la découverte automatique, vous devez modifier les listes des autres noms de sujet du certificat sur un directeur et un serveur frontal exécutant le service de découverte automatique. En outre, il peut s’avérer nécessaire de modifier les listes des autres noms de sujet sur les certificats utilisés pour les règles de publication des services web externes sur les proxys inverses.

La décision d’utiliser des listes d’autres noms de sujet sur les proxys inverses est basée sur la publication du service de découverte automatique sur le port 80 ou sur le port 443 :

  - **Publié sur le port 80**   aucune modification de certificat n’est requise si la requête initiale du service de découverte automatique a lieu sur le port 80. Cela est dû au fait que les appareils mobiles exécutant Lync accèdent au proxy inverse sur le port 80 de manière externe, puis sont transférés vers un directeur ou un serveur frontal sur le port 8080 en interne. Pour plus d’informations, reportez-vous à la section « processus de découverte automatique à l’aide du port 80 » [configuration technique requise pour la mobilité dans Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).

  - **Publié sur le port 443**   la liste autre nom du sujet sur les certificats utilisés par la règle de publication des services Web externes doit contenir un *lyncdiscover.\< entrée\> sipdomain* pour chaque domaine SIP au sein de votre organisation.
    
    <div>
    

    > [!IMPORTANT]  
    > Nous vous recommandons vivement d’utiliser le protocole HTTPs sur HTTP. HTTPs utilise des certificats pour chiffrer le trafic. HTTP ne fournit pas de chiffrement, et toutes les données envoyées seront en texte brut.

    
    </div>

La réémission de certificats à l’aide d’une autorité de certification interne est généralement un processus simple. Toutefois, pour les certificats publics utilisés sur la règle de publication du service Web, l’ajout de plusieurs entrées de l’autre nom du sujet peut devenir onéreux. Pour contourner ce problème, nous prenons en charge la connexion de découverte automatique initiale via le port 80, qui est ensuite redirigé vers le port 8080 sur le directeur ou le serveur frontal.

<div>


> [!NOTE]  
> Si votre infrastructure Lync Server 2013 utilise des certificats internes émis par une autorité de certification interne et que vous envisagez de prendre en charge les appareils mobiles qui se connectent sans fil, la chaîne de certificats racine de l’autorité de certification interne doit être installée. sur les appareils mobiles ou vous devez passer à un certificat public sur votre infrastructure Lync Server 2013.



</div>

Cette rubrique décrit les autres noms d’objet supplémentaires requis pour le directeur, le serveur frontal et le proxy inverse. Seuls les autres noms de sujet (SAN) sont référencés. Reportez-vous aux sections de planification pour obtenir des instructions sur les autres entrées sur les certificats. Pour plus d’informations, reportez-vous à [la rubrique scénarios pour le directeur dans Lync server 2013](lync-server-2013-scenarios-for-the-director.md), [scénarios pour l’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md)et [scénarios pour le proxy inverse dans Lync Server 2013](lync-server-2013-scenarios-for-reverse-proxy.md).

Les tableaux suivants définissent les entrées SAN de découverte automatique pour le pool Directeur, le pool frontal et le proxy inverse :

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
> Vous affectez le certificat que vous venez de mettre à jour avec la nouvelle entrée SAN au certificat par défaut. Vous pouvez également utiliser le SAN = *. &lt;sipdomain&gt;.



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
> Vous affectez le certificat que vous venez de mettre à jour avec la nouvelle entrée SAN au certificat par défaut. Vous pouvez également utiliser le SAN = *. &lt;sipdomain&gt;



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
<td><p>SAN = lyncdiscover. &lt;sipdomain&gt;</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Vous affectez le certificat récemment mis à jour avec la nouvelle entrée SAN à l’écouteur SSL sur le proxy inverse.



</div>

</div>

<span> </span>

</div>

</div>

</div>

