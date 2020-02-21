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

# <a name="encryption-for-lync-server-2013"></a><span data-ttu-id="c914b-102">Chiffrement pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c914b-102">Encryption for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c914b-103">_**Dernière modification de la rubrique :** 2017-09-14_</span><span class="sxs-lookup"><span data-stu-id="c914b-103">_**Topic Last Modified:** 2017-09-14_</span></span>

<span data-ttu-id="c914b-104">Microsoft Lync Server 2013 utilise TLS et MTLS pour chiffrer les messages instantanés.</span><span class="sxs-lookup"><span data-stu-id="c914b-104">Microsoft Lync Server 2013 uses TLS and MTLS to encrypt instant messages.</span></span> <span data-ttu-id="c914b-105">Tout le trafic de serveur à serveur nécessite MTLS, que le trafic soit limité au réseau interne ou qu’il croise le périmètre réseau interne.</span><span class="sxs-lookup"><span data-stu-id="c914b-105">All server-to-server traffic requires MTLS, regardless of whether the traffic is confined to the internal network or crosses the internal network perimeter.</span></span> <span data-ttu-id="c914b-106">TLS est facultatif mais fortement recommandé entre le serveur de médiation et la passerelle multimédia.</span><span class="sxs-lookup"><span data-stu-id="c914b-106">TLS is optional but strongly recommended between the Mediation Server and media gateway.</span></span> <span data-ttu-id="c914b-107">Si TLS est configuré sur cette liaison, MTLS est requis.</span><span class="sxs-lookup"><span data-stu-id="c914b-107">If TLS is configured on this link, MTLS is required.</span></span> <span data-ttu-id="c914b-108">Par conséquent, la passerelle doit être configurée avec un certificat provenant d’une autorité de certification approuvée par le serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="c914b-108">Therefore, the gateway must be configured with a certificate from a CA that is trusted by the Mediation Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c914b-109">Un avis de sécurité concernant SSL 3,0 a été publié en 2014.</span><span class="sxs-lookup"><span data-stu-id="c914b-109">A security advisory regarding SSL 3.0 was published in 2014.</span></span> <span data-ttu-id="c914b-110">La désactivation de SSL 3,0 dans Lync Server 2013 est une option prise en charge.</span><span class="sxs-lookup"><span data-stu-id="c914b-110">Disabling SSL 3.0 in Lync Server 2013 is a supported option.</span></span> <span data-ttu-id="c914b-111">Pour en savoir plus sur l’avis de sécurité <A class=uri href="https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/">https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/</A>, reportez-vous à la rubrique.</span><span class="sxs-lookup"><span data-stu-id="c914b-111">To learn more about the security advisory, see <A class=uri href="https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/">https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/</A>.</span></span>



</div>

<div>

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="caution" alt="security" /><span data-ttu-id="c914b-113">Note de sécurité :</span><span class="sxs-lookup"><span data-stu-id="c914b-113">Security Note:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="c914b-114">Pour vous assurer que le protocole de chiffrement le plus puissant est utilisé, Lync Server 2013 propose des protocoles de chiffrement TLS dans l’ordre suivant pour les clients : <strong>tls 1,2</strong> , <strong>TLS 1,1</strong>, <strong>TLS 1,0</strong>.</span><span class="sxs-lookup"><span data-stu-id="c914b-114">To ensure the strongest cryptographic protocol is used, Lync Server 2013 will offer TLS encryption protocols in the following order to clients: <strong>TLS 1.2</strong> , <strong>TLS 1.1</strong>, <strong>TLS 1.0</strong>.</span></span> <span data-ttu-id="c914b-115">Le protocole TLS est un aspect critique de Lync Server 2013 et, par conséquent, il est nécessaire pour maintenir un environnement pris en charge.</span><span class="sxs-lookup"><span data-stu-id="c914b-115">TLS is a critical aspect of Lync Server 2013 and thus it is required in order to maintain a supported environment.</span></span></td>
</tr>
</tbody>
</table>


</div>

<span data-ttu-id="c914b-p104">Les exigences applicables au trafic entre les clients varient, selon qu’il franchit ou non le pare-feu de l’entreprise. S’il s’agit d’un trafic exclusivement en interne, il peut utiliser TLS, ce qui implique le chiffrement des messages instantanés, ou TCP, sans ce chiffrement.</span><span class="sxs-lookup"><span data-stu-id="c914b-p104">Requirements for client-to-client traffic depend on whether that traffic crosses the internal corporate firewall. Strictly internal traffic can use either TLS, in which case the instant message is encrypted, or TCP, in which case it is not.</span></span>

<span data-ttu-id="c914b-118">Le tableau suivant résume les protocoles requis pour chaque type de trafic.</span><span class="sxs-lookup"><span data-stu-id="c914b-118">The following table summarizes the protocol requirements for each type of traffic.</span></span>

### <a name="traffic-protection"></a><span data-ttu-id="c914b-119">Protection du trafic</span><span class="sxs-lookup"><span data-stu-id="c914b-119">Traffic Protection</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c914b-120">Type de trafic</span><span class="sxs-lookup"><span data-stu-id="c914b-120">Traffic type</span></span></th>
<th><span data-ttu-id="c914b-121">Protégé par</span><span class="sxs-lookup"><span data-stu-id="c914b-121">Protected by</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c914b-122">Serveur à serveur</span><span class="sxs-lookup"><span data-stu-id="c914b-122">Server-to-server</span></span></p></td>
<td><p><span data-ttu-id="c914b-123">MTLS</span><span class="sxs-lookup"><span data-stu-id="c914b-123">MTLS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c914b-124">Client à serveur</span><span class="sxs-lookup"><span data-stu-id="c914b-124">Client-to-server</span></span></p></td>
<td><p><span data-ttu-id="c914b-125">TLS</span><span class="sxs-lookup"><span data-stu-id="c914b-125">TLS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c914b-126">Messagerie instantanée et présence</span><span class="sxs-lookup"><span data-stu-id="c914b-126">Instant messaging and presence</span></span></p></td>
<td><p><span data-ttu-id="c914b-127">TLS (si configuré pour TLS)</span><span class="sxs-lookup"><span data-stu-id="c914b-127">TLS (if configured for TLS)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c914b-128">Partage de données audio, vidéo ou du Bureau</span><span class="sxs-lookup"><span data-stu-id="c914b-128">Audio and video and desktop sharing of media</span></span></p></td>
<td><p><span data-ttu-id="c914b-129">SRTP</span><span class="sxs-lookup"><span data-stu-id="c914b-129">SRTP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c914b-130">Partage du Bureau (signalisation)</span><span class="sxs-lookup"><span data-stu-id="c914b-130">Desktop sharing (signaling)</span></span></p></td>
<td><p><span data-ttu-id="c914b-131">TLS</span><span class="sxs-lookup"><span data-stu-id="c914b-131">TLS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c914b-132">Conférence web</span><span class="sxs-lookup"><span data-stu-id="c914b-132">Web conferencing</span></span></p></td>
<td><p><span data-ttu-id="c914b-133">TLS</span><span class="sxs-lookup"><span data-stu-id="c914b-133">TLS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c914b-134">Téléchargement de contenu de réunion, de carnets d’adresses, développement des groupes de distribution</span><span class="sxs-lookup"><span data-stu-id="c914b-134">Meeting content download, address book download, distribution group expansion</span></span></p></td>
<td><p><span data-ttu-id="c914b-135">HTTPS</span><span class="sxs-lookup"><span data-stu-id="c914b-135">HTTPS</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="media-encryption"></a><span data-ttu-id="c914b-136">Chiffrement des données multimédias</span><span class="sxs-lookup"><span data-stu-id="c914b-136">Media Encryption</span></span>

<span data-ttu-id="c914b-137">Le trafic multimédia est chiffré à l’aide du protocole SRTP (Secure RTP), un profil du protocole RTP (Real-Time Transport Protocol).</span><span class="sxs-lookup"><span data-stu-id="c914b-137">Media traffic is encrypted using Secure RTP (SRTP), a profile of Real-Time Transport Protocol (RTP) that provides confidentiality, authentication, and replay attack protection to RTP traffic.</span></span> <span data-ttu-id="c914b-138">Le contenu multimédia transitant dans les deux sens entre le serveur de médiation et son tronçon suivant interne est également chiffré à l’aide de SRTP.</span><span class="sxs-lookup"><span data-stu-id="c914b-138">In addition, media flowing in both directions between the Mediation Server and its internal next hop is also encrypted using SRTP.</span></span> <span data-ttu-id="c914b-139">Les flux de médias dans les deux directions entre le serveur de médiation et une passerelle multimédia ne sont pas chiffrés par défaut.</span><span class="sxs-lookup"><span data-stu-id="c914b-139">Media flowing in both directions between the Mediation Server and a media gateway is not encrypted by default.</span></span> <span data-ttu-id="c914b-140">Le serveur de médiation peut prendre en charge le chiffrement sur la passerelle multimédia mais, dans ce cas, celle-ci doit prendre en charge MTLS et le stockage d’un certificat.</span><span class="sxs-lookup"><span data-stu-id="c914b-140">The Mediation Server can support encryption to the media gateway, but the gateway must support MTLS and storage of a certificate.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c914b-141">Audio/vidéo (A/V) est pris en charge avec la nouvelle version de Windows Live Messenger.</span><span class="sxs-lookup"><span data-stu-id="c914b-141">Audio/Video (A/V) is supported with the new version of Windows Live Messenger.</span></span> <span data-ttu-id="c914b-142">Si vous implémentez la fédération A/V avec Windows Live Messenger, vous devez également modifier le niveau de chiffrement de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c914b-142">If you are implementing A/V federation with Windows Live Messenger, you must also modify the Lync Server encryption level.</span></span> <span data-ttu-id="c914b-143">Par défaut, le niveau de chiffrement est Requis.</span><span class="sxs-lookup"><span data-stu-id="c914b-143">By default, the encryption level is Required.</span></span> <span data-ttu-id="c914b-144">Vous devez définir ce paramètre sur pris en charge à l’aide de Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="c914b-144">You must change this setting to Supported by using the Lync Server Management Shell.</span></span> <span data-ttu-id="c914b-145">Pour plus d’informations, reportez-vous à la rubrique <A href="lync-server-2013-deploying-external-user-access.md">Deploying External User Access in Lync Server 2013</A> dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="c914b-145">For more information, see <A href="lync-server-2013-deploying-external-user-access.md">Deploying external user access in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<span data-ttu-id="c914b-146">Le trafic audio et vidéo n’est pas chiffré entre Microsoft Lync 2013 et les clients Windows Live.</span><span class="sxs-lookup"><span data-stu-id="c914b-146">Audio and video media traffic is not encrypted between Microsoft Lync 2013 and Windows Live clients.</span></span>

</div>

<div>

## <a name="fips"></a><span data-ttu-id="c914b-147">AGRÉÉ</span><span class="sxs-lookup"><span data-stu-id="c914b-147">FIPS</span></span>

<span data-ttu-id="c914b-148">Lync Server 2013 et Microsoft Exchange Server 2013 fonctionnent avec la prise en charge des algorithmes FIPS (Federal Information Processing Standard) 140-2 si les systèmes d’exploitation Windows Server sont configurés pour utiliser les algorithmes FIPS 140-2 pour la cryptographie système.</span><span class="sxs-lookup"><span data-stu-id="c914b-148">Lync Server 2013 and Microsoft Exchange Server 2013 operate with support for Federal Information Processing Standard (FIPS) 140-2 algorithms if the Windows Server operating systems are configured to use the FIPS 140-2 algorithms for system cryptography.</span></span> <span data-ttu-id="c914b-149">Pour implémenter la prise en charge du cryptage FIPS, vous devez configurer chaque serveur exécutant Lync Server 2013 afin de le prendre en charge.</span><span class="sxs-lookup"><span data-stu-id="c914b-149">To implement FIPS support, you must configure each server running Lync Server 2013 to support it.</span></span> <span data-ttu-id="c914b-150">Pour plus d’informations sur l’utilisation des algorithmes compatibles FIPS et sur l’implémentation de la prise en charge du FIPS, voir l’article 811833 de la base de connaissances Microsoft sur les effets de l’activation du paramètre de sécurité « chiffrement du système : utiliser des algorithmes compatibles FIPS pour le chiffrement, le [https://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=811833](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=811833)hachage et la signature » dans.</span><span class="sxs-lookup"><span data-stu-id="c914b-150">For details about the use of FIPS-compliant algorithms and how to implement FIPS support, see Microsoft Knowledge Base article 811833, The effects of enabling the “System cryptography: Use FIPS compliant algorithms for encryption, hashing, and signing" security setting in Windows XP and in later versions of Windows at [https://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=811833](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=811833).</span></span> <span data-ttu-id="c914b-151">Pour plus d’informations sur la prise en charge et les limitations du FIPS 140-2 dans Exchange 2010, consultez la rubrique Exchange 2010 SP1 [https://go.microsoft.com/fwlink/p/?LinkId=205335](https://go.microsoft.com/fwlink/p/?linkid=205335)et prise en charge des algorithmes compatibles FIPS à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="c914b-151">For details about FIPS 140-2 support and limitations in Exchange 2010, see Exchange 2010 SP1 and Support for FIPS Compliant Algorithms at [https://go.microsoft.com/fwlink/p/?LinkId=205335](https://go.microsoft.com/fwlink/p/?linkid=205335).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

