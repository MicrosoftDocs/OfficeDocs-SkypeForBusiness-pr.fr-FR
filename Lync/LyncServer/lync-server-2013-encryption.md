---
title: 'Lync Server 2013 : chiffrement'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Encryption for Lync Server 2013
ms:assetid: d18c74a6-385b-407b-98eb-0d525fa38fea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481135(v=OCS.15)
ms:contentKeyID: 59893874
ms.date: 09/14/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2b87e395f56c7dfdbd03bf35c5c1c8cf37795652
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207730"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="encryption-for-lync-server-2013"></a>Chiffrement pour Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2017-09-14_

Microsoft Lync Server 2013 utilise TLS et MTLS pour chiffrer les messages instantanés. Tout le trafic de serveur à serveur nécessite MTLS, que le trafic soit limité au réseau interne ou qu’il croise le périmètre réseau interne. TLS est facultatif mais fortement recommandé entre le serveur de médiation et la passerelle multimédia. Si TLS est configuré sur cette liaison, MTLS est requis. Par conséquent, la passerelle doit être configurée avec un certificat provenant d’une autorité de certification approuvée par le serveur de médiation.

<div>


> [!NOTE]  
> Un avis de sécurité concernant SSL 3,0 a été publié en 2014. La désactivation de SSL 3,0 dans Lync Server 2013 est une option prise en charge. Pour en savoir plus sur l’avis de sécurité <A class=uri href="https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/">https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/</A>, reportez-vous à la rubrique.



</div>

<div>

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="caution" alt="security" />Note de sécurité :</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Pour vous assurer que le protocole de chiffrement le plus puissant est utilisé, Lync Server 2013 propose des protocoles de chiffrement TLS dans l’ordre suivant pour les clients : <strong>tls 1,2</strong> , <strong>TLS 1,1</strong>, <strong>TLS 1,0</strong>. Le protocole TLS est un aspect critique de Lync Server 2013 et, par conséquent, il est nécessaire pour maintenir un environnement pris en charge.</td>
</tr>
</tbody>
</table>


</div>

Les exigences applicables au trafic entre les clients varient, selon qu’il franchit ou non le pare-feu de l’entreprise. S’il s’agit d’un trafic exclusivement en interne, il peut utiliser TLS, ce qui implique le chiffrement des messages instantanés, ou TCP, sans ce chiffrement.

Le tableau suivant résume les protocoles requis pour chaque type de trafic.

### <a name="traffic-protection"></a>Protection du trafic

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Type de trafic</th>
<th>Protégé par</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Serveur à serveur</p></td>
<td><p>MTLS</p></td>
</tr>
<tr class="even">
<td><p>Client à serveur</p></td>
<td><p>TLS</p></td>
</tr>
<tr class="odd">
<td><p>Messagerie instantanée et présence</p></td>
<td><p>TLS (si configuré pour TLS)</p></td>
</tr>
<tr class="even">
<td><p>Partage de données audio, vidéo ou du Bureau</p></td>
<td><p>SRTP</p></td>
</tr>
<tr class="odd">
<td><p>Partage du Bureau (signalisation)</p></td>
<td><p>TLS</p></td>
</tr>
<tr class="even">
<td><p>Conférence web</p></td>
<td><p>TLS</p></td>
</tr>
<tr class="odd">
<td><p>Téléchargement de contenu de réunion, de carnets d’adresses, développement des groupes de distribution</p></td>
<td><p>HTTPS</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="media-encryption"></a>Chiffrement des données multimédias

Le trafic multimédia est chiffré à l’aide du protocole SRTP (Secure RTP), un profil du protocole RTP (Real-Time Transport Protocol). Le contenu multimédia transitant dans les deux sens entre le serveur de médiation et son tronçon suivant interne est également chiffré à l’aide de SRTP. Les flux de médias dans les deux directions entre le serveur de médiation et une passerelle multimédia ne sont pas chiffrés par défaut. Le serveur de médiation peut prendre en charge le chiffrement sur la passerelle multimédia mais, dans ce cas, celle-ci doit prendre en charge MTLS et le stockage d’un certificat.

<div>


> [!NOTE]  
> Audio/vidéo (A/V) est pris en charge avec la nouvelle version de Windows Live Messenger. Si vous implémentez la fédération A/V avec Windows Live Messenger, vous devez également modifier le niveau de chiffrement de Lync Server. Par défaut, le niveau de chiffrement est Requis. Vous devez définir ce paramètre sur pris en charge à l’aide de Lync Server Management Shell. Pour plus d’informations, reportez-vous à la rubrique <A href="lync-server-2013-deploying-external-user-access.md">Deploying External User Access in Lync Server 2013</A> dans la documentation de déploiement.



</div>

Le trafic audio et vidéo n’est pas chiffré entre Microsoft Lync 2013 et les clients Windows Live.

</div>

<div>

## <a name="fips"></a>AGRÉÉ

Lync Server 2013 et Microsoft Exchange Server 2013 fonctionnent avec la prise en charge des algorithmes FIPS (Federal Information Processing Standard) 140-2 si les systèmes d’exploitation Windows Server sont configurés pour utiliser les algorithmes FIPS 140-2 pour la cryptographie système. Pour implémenter la prise en charge du cryptage FIPS, vous devez configurer chaque serveur exécutant Lync Server 2013 afin de le prendre en charge. Pour plus d’informations sur l’utilisation des algorithmes compatibles FIPS et sur l’implémentation de la prise en charge du FIPS, voir l’article 811833 de la base de connaissances Microsoft sur les effets de l’activation du paramètre de sécurité « chiffrement du système : utiliser des algorithmes compatibles FIPS pour le chiffrement, le [https://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=811833](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=811833)hachage et la signature » dans. Pour plus d’informations sur la prise en charge et les limitations du FIPS 140-2 dans Exchange 2010, consultez la rubrique Exchange 2010 SP1 [https://go.microsoft.com/fwlink/p/?LinkId=205335](https://go.microsoft.com/fwlink/p/?linkid=205335)et prise en charge des algorithmes compatibles FIPS à l’adresse.

</div>

</div>

<span> </span>

</div>

</div>

</div>

