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
ms.openlocfilehash: 5f4b655ff632a50d2c28451a577f5be03bfabc82
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735614"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="encryption-for-lync-server-2013"></a><span data-ttu-id="9cbd0-102">Chiffrement pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9cbd0-102">Encryption for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9cbd0-103">_**Dernière modification de la rubrique :** 2017-09-14_</span><span class="sxs-lookup"><span data-stu-id="9cbd0-103">_**Topic Last Modified:** 2017-09-14_</span></span>

<span data-ttu-id="9cbd0-104">Microsoft Lync Server 2013 utilise TLS et MTLS pour chiffrer les messages instantanés.</span><span class="sxs-lookup"><span data-stu-id="9cbd0-104">Microsoft Lync Server 2013 uses TLS and MTLS to encrypt instant messages.</span></span> <span data-ttu-id="9cbd0-105">L’ensemble du trafic serveur à serveur nécessite MTLS, et ce que le trafic soit confiné au réseau interne ou qu’il traverse le périmètre du réseau interne.</span><span class="sxs-lookup"><span data-stu-id="9cbd0-105">All server-to-server traffic requires MTLS, regardless of whether the traffic is confined to the internal network or crosses the internal network perimeter.</span></span> <span data-ttu-id="9cbd0-106">TLS est facultatif, mais fortement recommandé entre le serveur de médiation et la passerelle multimédia.</span><span class="sxs-lookup"><span data-stu-id="9cbd0-106">TLS is optional but strongly recommended between the Mediation Server and media gateway.</span></span> <span data-ttu-id="9cbd0-107">Si TLS est configuré sur cette liaison, MTLS est requis.</span><span class="sxs-lookup"><span data-stu-id="9cbd0-107">If TLS is configured on this link, MTLS is required.</span></span> <span data-ttu-id="9cbd0-108">Par conséquent, la passerelle doit être configurée avec un certificat provenant d’une autorité de certification approuvée par le serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="9cbd0-108">Therefore, the gateway must be configured with a certificate from a CA that is trusted by the Mediation Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9cbd0-109">Un avis de sécurité relatif à SSL 3.0 a été publié en 2014.</span><span class="sxs-lookup"><span data-stu-id="9cbd0-109">A security advisory regarding SSL 3.0 was published in 2014.</span></span> <span data-ttu-id="9cbd0-110">La désactivation de SSL 3,0 dans Lync Server 2013 est une option prise en charge.</span><span class="sxs-lookup"><span data-stu-id="9cbd0-110">Disabling SSL 3.0 in Lync Server 2013 is a supported option.</span></span> <span data-ttu-id="9cbd0-111">Pour en savoir plus sur l’avis de sécurité <A class=uri href="https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/">https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/</A>, voir.</span><span class="sxs-lookup"><span data-stu-id="9cbd0-111">To learn more about the security advisory, see <A class=uri href="https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/">https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/</A>.</span></span>



</div>

<div>

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="sûreté" alt="security" /><span data-ttu-id="9cbd0-113">Note de sécurité :</span><span class="sxs-lookup"><span data-stu-id="9cbd0-113">Security Note:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="9cbd0-114">Pour vous assurer que le protocole cryptographique le plus puissant est utilisé, Lync Server 2013 propose des protocoles de chiffrement TLS dans l’ordre suivant pour les clients : <strong>tls 1,2</strong> , <strong>TLS 1,1</strong>, <strong>TLS 1,0</strong>.</span><span class="sxs-lookup"><span data-stu-id="9cbd0-114">To ensure the strongest cryptographic protocol is used, Lync Server 2013 will offer TLS encryption protocols in the following order to clients: <strong>TLS 1.2</strong> , <strong>TLS 1.1</strong>, <strong>TLS 1.0</strong>.</span></span> <span data-ttu-id="9cbd0-115">Le protocole TLS est un aspect essentiel de Lync Server 2013 et donc requis pour gérer un environnement pris en charge.</span><span class="sxs-lookup"><span data-stu-id="9cbd0-115">TLS is a critical aspect of Lync Server 2013 and thus it is required in order to maintain a supported environment.</span></span></td>
</tr>
</tbody>
</table>


</div>

<span data-ttu-id="9cbd0-116">La configuration requise pour le trafic client à client varie selon que le trafic traverse le pare-feu interne de l’entreprise.</span><span class="sxs-lookup"><span data-stu-id="9cbd0-116">Requirements for client-to-client traffic depend on whether that traffic crosses the internal corporate firewall.</span></span> <span data-ttu-id="9cbd0-117">Le trafic interne strictement disponible peut utiliser la valeur TLS, auquel cas le message instantané est crypté, et ce n’est pas le cas.</span><span class="sxs-lookup"><span data-stu-id="9cbd0-117">Strictly internal traffic can use either TLS, in which case the instant message is encrypted, or TCP, in which case it is not.</span></span>

<span data-ttu-id="9cbd0-118">Le tableau suivant résume les exigences de protocole pour chaque type de trafic.</span><span class="sxs-lookup"><span data-stu-id="9cbd0-118">The following table summarizes the protocol requirements for each type of traffic.</span></span>

### <a name="traffic-protection"></a><span data-ttu-id="9cbd0-119">Protection du trafic</span><span class="sxs-lookup"><span data-stu-id="9cbd0-119">Traffic Protection</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9cbd0-120">Type de trafic</span><span class="sxs-lookup"><span data-stu-id="9cbd0-120">Traffic type</span></span></th>
<th><span data-ttu-id="9cbd0-121">Protégé par</span><span class="sxs-lookup"><span data-stu-id="9cbd0-121">Protected by</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9cbd0-122">Serveur à serveur</span><span class="sxs-lookup"><span data-stu-id="9cbd0-122">Server-to-server</span></span></p></td>
<td><p><span data-ttu-id="9cbd0-123">MTLS</span><span class="sxs-lookup"><span data-stu-id="9cbd0-123">MTLS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9cbd0-124">Client à serveur</span><span class="sxs-lookup"><span data-stu-id="9cbd0-124">Client-to-server</span></span></p></td>
<td><p><span data-ttu-id="9cbd0-125">TLS</span><span class="sxs-lookup"><span data-stu-id="9cbd0-125">TLS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9cbd0-126">Messagerie instantanée et présence</span><span class="sxs-lookup"><span data-stu-id="9cbd0-126">Instant messaging and presence</span></span></p></td>
<td><p><span data-ttu-id="9cbd0-127">TLS (si TLS est configuré)</span><span class="sxs-lookup"><span data-stu-id="9cbd0-127">TLS (if configured for TLS)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9cbd0-128">Partage multimédia audio, vidéo et de bureau</span><span class="sxs-lookup"><span data-stu-id="9cbd0-128">Audio and video and desktop sharing of media</span></span></p></td>
<td><p><span data-ttu-id="9cbd0-129">SRTP</span><span class="sxs-lookup"><span data-stu-id="9cbd0-129">SRTP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9cbd0-130">Partage du bureau (signalisation)</span><span class="sxs-lookup"><span data-stu-id="9cbd0-130">Desktop sharing (signaling)</span></span></p></td>
<td><p><span data-ttu-id="9cbd0-131">TLS</span><span class="sxs-lookup"><span data-stu-id="9cbd0-131">TLS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9cbd0-132">Conférence web</span><span class="sxs-lookup"><span data-stu-id="9cbd0-132">Web conferencing</span></span></p></td>
<td><p><span data-ttu-id="9cbd0-133">TLS</span><span class="sxs-lookup"><span data-stu-id="9cbd0-133">TLS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9cbd0-134">Téléchargement de contenu de réunion, téléchargement de carnet d’adresses, développement de groupe de distribution</span><span class="sxs-lookup"><span data-stu-id="9cbd0-134">Meeting content download, address book download, distribution group expansion</span></span></p></td>
<td><p><span data-ttu-id="9cbd0-135">HTTPS</span><span class="sxs-lookup"><span data-stu-id="9cbd0-135">HTTPS</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="media-encryption"></a><span data-ttu-id="9cbd0-136">Chiffrement multimédia</span><span class="sxs-lookup"><span data-stu-id="9cbd0-136">Media Encryption</span></span>

<span data-ttu-id="9cbd0-137">Le trafic multimédia est chiffré à l'aide du protocole SRTP (Secure Real-time Transport Protocol), un profil du protocole RTP (Real-Time Transport Protocol) qui offre confidentialité, authentification et protection contre les attaques sur le trafic RTP.</span><span class="sxs-lookup"><span data-stu-id="9cbd0-137">Media traffic is encrypted using Secure RTP (SRTP), a profile of Real-Time Transport Protocol (RTP) that provides confidentiality, authentication, and replay attack protection to RTP traffic.</span></span> <span data-ttu-id="9cbd0-138">De plus, les données multimédias acheminées dans les deux directions entre le serveur de médiation et son tronçon suivant interne sont également chiffrées avec SRTP.</span><span class="sxs-lookup"><span data-stu-id="9cbd0-138">In addition, media flowing in both directions between the Mediation Server and its internal next hop is also encrypted using SRTP.</span></span> <span data-ttu-id="9cbd0-139">Par défaut, le flux multimédia dans les deux directions entre le serveur de médiation et une passerelle multimédia n’est pas chiffré.</span><span class="sxs-lookup"><span data-stu-id="9cbd0-139">Media flowing in both directions between the Mediation Server and a media gateway is not encrypted by default.</span></span> <span data-ttu-id="9cbd0-140">Le serveur de médiation peut prendre en charge le chiffrement sur la passerelle multimédia, mais la passerelle doit prendre en charge MTLS et le stockage d’un certificat.</span><span class="sxs-lookup"><span data-stu-id="9cbd0-140">The Mediation Server can support encryption to the media gateway, but the gateway must support MTLS and storage of a certificate.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9cbd0-141">L’audio/vidéo (A/V) est pris en charge avec la nouvelle version de Windows Live Messenger.</span><span class="sxs-lookup"><span data-stu-id="9cbd0-141">Audio/Video (A/V) is supported with the new version of Windows Live Messenger.</span></span> <span data-ttu-id="9cbd0-142">Si vous implémentez une fédération A/V avec Windows Live Messenger, vous devez également modifier le niveau de chiffrement de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9cbd0-142">If you are implementing A/V federation with Windows Live Messenger, you must also modify the Lync Server encryption level.</span></span> <span data-ttu-id="9cbd0-143">Par défaut, ce paramètre est défini sur Requis.</span><span class="sxs-lookup"><span data-stu-id="9cbd0-143">By default, the encryption level is Required.</span></span> <span data-ttu-id="9cbd0-144">Vous devez définir ce paramètre sur pris en charge à l’aide de Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="9cbd0-144">You must change this setting to Supported by using the Lync Server Management Shell.</span></span> <span data-ttu-id="9cbd0-145">Pour plus d’informations, reportez-vous à la rubrique <A href="lync-server-2013-deploying-external-user-access.md">déploiement d’un accès utilisateur externe dans Lync Server 2013</A> dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="9cbd0-145">For more information, see <A href="lync-server-2013-deploying-external-user-access.md">Deploying external user access in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<span data-ttu-id="9cbd0-146">Le trafic des contenus multimédias audio et vidéo n’est pas crypté entre les clients Microsoft Lync 2013 et Windows Live.</span><span class="sxs-lookup"><span data-stu-id="9cbd0-146">Audio and video media traffic is not encrypted between Microsoft Lync 2013 and Windows Live clients.</span></span>

</div>

<div>

## <a name="fips"></a><span data-ttu-id="9cbd0-147">FIPS</span><span class="sxs-lookup"><span data-stu-id="9cbd0-147">FIPS</span></span>

<span data-ttu-id="9cbd0-148">Lync Server 2013 et Microsoft Exchange Server 2013 prennent en charge les algorithmes 140-2 FIPS (Federal Information Processing Standard), si les systèmes d’exploitation Windows Server sont configurés pour utiliser les algorithmes 140-2 FIPS FIPS pour le chiffrement du système.</span><span class="sxs-lookup"><span data-stu-id="9cbd0-148">Lync Server 2013 and Microsoft Exchange Server 2013 operate with support for Federal Information Processing Standard (FIPS) 140-2 algorithms if the Windows Server operating systems are configured to use the FIPS 140-2 algorithms for system cryptography.</span></span> <span data-ttu-id="9cbd0-149">Pour mettre en œuvre la prise en charge du FIPS, vous devez configurer chaque serveur exécutant Lync Server 2013 pour le prendre en charge.</span><span class="sxs-lookup"><span data-stu-id="9cbd0-149">To implement FIPS support, you must configure each server running Lync Server 2013 to support it.</span></span> <span data-ttu-id="9cbd0-150">Pour plus d’informations sur l’utilisation des algorithmes compatibles FIPS et sur l’implémentation de la prise en charge du FIPS, voir l’article 811833 de la base de connaissances Microsoft, effets de l’activation du paramètre de sécurité « chiffrement de système : utiliser les algorithmes compatibles FIPS pour le chiffrement, le hachage [http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=811833](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=811833)et la signature » dans Windows XP et les versions ultérieures de Windows.</span><span class="sxs-lookup"><span data-stu-id="9cbd0-150">For details about the use of FIPS-compliant algorithms and how to implement FIPS support, see Microsoft Knowledge Base article 811833, The effects of enabling the “System cryptography: Use FIPS compliant algorithms for encryption, hashing, and signing" security setting in Windows XP and in later versions of Windows at [http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=811833](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=811833).</span></span> <span data-ttu-id="9cbd0-151">Pour plus d’informations sur la prise en charge et les limitations de FIPS 140-2 dans Exchange 2010, voir Exchange 2010 SP1 et prise [https://go.microsoft.com/fwlink/p/?LinkId=205335](https://go.microsoft.com/fwlink/p/?linkid=205335)en charge des algorithmes compatibles FIPS à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="9cbd0-151">For details about FIPS 140-2 support and limitations in Exchange 2010, see Exchange 2010 SP1 and Support for FIPS Compliant Algorithms at [https://go.microsoft.com/fwlink/p/?LinkId=205335](https://go.microsoft.com/fwlink/p/?linkid=205335).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

