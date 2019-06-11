---
title: 'Lync Server 2013: chiffrement'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Encryption for Lync Server 2013
ms:assetid: d18c74a6-385b-407b-98eb-0d525fa38fea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481135(v=OCS.15)
ms:contentKeyID: 59893874
ms.date: 09/14/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 01c989213b050bdb536e95a8a42e8f7b35292eaf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831233"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="encryption-for-lync-server-2013"></a>Chiffrement pour Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2017-09-14_

Microsoft Lync Server 2013 utilise TLS et MTLS pour chiffrer les messages instantanés. L’ensemble du trafic serveur à serveur nécessite MTLS, et ce que le trafic soit confiné au réseau interne ou qu’il traverse le périmètre du réseau interne. TLS est facultatif, mais fortement recommandé entre le serveur de médiation et la passerelle multimédia. Si TLS est configuré sur cette liaison, MTLS est requis. Par conséquent, la passerelle doit être configurée avec un certificat provenant d’une autorité de certification approuvée par le serveur de médiation.

<div>


> [!NOTE]  
> Un avis de sécurité relatif à SSL 3.0 a été publié en 2014. La désactivation de SSL 3,0 dans Lync Server 2013 est une option prise en charge. Pour en savoir plus sur l’avis de sécurité <A class=uri href="https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/">https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/</A>, voir.



</div>

<div>

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="sûreté" alt="security" />Note de sécurité:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Pour vous assurer que le protocole cryptographique le plus puissant est utilisé, Lync Server 2013 propose des protocoles de chiffrement TLS dans l’ordre suivant pour les clients: <strong>tls 1,2</strong> , <strong>TLS 1,1</strong>, <strong>TLS 1,0</strong>. Le protocole TLS est un aspect essentiel de Lync Server 2013 et donc requis pour gérer un environnement pris en charge.</td>
</tr>
</tbody>
</table>


</div>

La configuration requise pour le trafic client à client varie selon que le trafic traverse le pare-feu interne de l’entreprise. Le trafic interne strictement disponible peut utiliser la valeur TLS, auquel cas le message instantané est crypté, et ce n’est pas le cas.

Le tableau suivant résume les exigences de protocole pour chaque type de trafic.

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
<td><p>TLS (si TLS est configuré)</p></td>
</tr>
<tr class="even">
<td><p>Partage multimédia audio, vidéo et de bureau</p></td>
<td><p>SRTP</p></td>
</tr>
<tr class="odd">
<td><p>Partage du bureau (signalisation)</p></td>
<td><p>TLS</p></td>
</tr>
<tr class="even">
<td><p>Conférence web</p></td>
<td><p>TLS</p></td>
</tr>
<tr class="odd">
<td><p>Téléchargement de contenu de réunion, téléchargement de carnet d’adresses, développement de groupe de distribution</p></td>
<td><p>HTTPS</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="media-encryption"></a>Chiffrement multimédia

Le trafic multimédia est chiffré à l'aide du protocole SRTP (Secure Real-time Transport Protocol), un profil du protocole RTP (Real-Time Transport Protocol) qui offre confidentialité, authentification et protection contre les attaques sur le trafic RTP. De plus, les données multimédias acheminées dans les deux directions entre le serveur de médiation et son tronçon suivant interne sont également chiffrées avec SRTP. Par défaut, le flux multimédia dans les deux directions entre le serveur de médiation et une passerelle multimédia n’est pas chiffré. Le serveur de médiation peut prendre en charge le chiffrement sur la passerelle multimédia, mais la passerelle doit prendre en charge MTLS et le stockage d’un certificat.

<div>


> [!NOTE]  
> L’audio/vidéo (A/V) est pris en charge avec la nouvelle version de Windows Live Messenger. Si vous implémentez une fédération A/V avec Windows Live Messenger, vous devez également modifier le niveau de chiffrement de Lync Server. Par défaut, ce paramètre est défini sur Requis. Vous devez définir ce paramètre sur pris en charge à l’aide de Lync Server Management Shell. Pour plus d’informations, reportez-vous à la rubrique <A href="lync-server-2013-deploying-external-user-access.md">déploiement d’un accès utilisateur externe dans Lync Server 2013</A> dans la documentation de déploiement.



</div>

Le trafic des contenus multimédias audio et vidéo n’est pas crypté entre les clients Microsoft Lync 2013 et Windows Live.

</div>

<div>

## <a name="fips"></a>FIPS

Lync Server 2013 et Microsoft Exchange Server 2013 prennent en charge les algorithmes 140-2 FIPS (Federal Information Processing Standard), si les systèmes d’exploitation Windows Server sont configurés pour utiliser les algorithmes 140-2 FIPS FIPS pour le chiffrement du système. Pour mettre en œuvre la prise en charge du FIPS, vous devez configurer chaque serveur exécutant Lync Server 2013 pour le prendre en charge. Pour plus d’informations sur l’utilisation des algorithmes compatibles FIPS et sur l’implémentation de la prise en charge du FIPS, voir l’article 811833 de la base de connaissances Microsoft sur les effets de l’activation de la sécurité «chiffre d’ordinateur: utiliser les algorithmes compatibles FIPS pour le chiffrement, le hachage et la signature». dans Windows XP et les versions ultérieures de Windows à [http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=811833](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=811833)l’adresse. Pour plus d’informations sur la prise en charge et les limitations de FIPS 140-2 dans Exchange 2010, voir Exchange 2010 SP1 et prise [https://go.microsoft.com/fwlink/p/?LinkId=205335](https://go.microsoft.com/fwlink/p/?linkid=205335)en charge des algorithmes compatibles FIPS à l’adresse.

</div>

</div>

<span> </span>

</div>

</div>

</div>

