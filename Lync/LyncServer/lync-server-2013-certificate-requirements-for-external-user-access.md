---
title: 'Lync Server 2013 : conditions requises pour les certificats pour l’accès des utilisateurs externes'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate requirements for external user access
ms:assetid: d45b6b10-556f-4b10-b1a7-fb0d0a64a498
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398920(v=OCS.15)
ms:contentKeyID: 48185503
ms.date: 03/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7000456629a91742350b9866dc9e1441c18eee57
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030868"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-requirements-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="79bb1-102">Conditions requises pour les certificats pour l’accès des utilisateurs externes dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="79bb1-102">Certificate requirements for external user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="79bb1-103">_**Dernière modification de la rubrique :** 2016-03-29_</span><span class="sxs-lookup"><span data-stu-id="79bb1-103">_**Topic Last Modified:** 2016-03-29_</span></span>

<span data-ttu-id="79bb1-104">Le logiciel de communication Microsoft Lync Server 2013 prend en charge l’utilisation d’un certificat public unique pour les interfaces externes d’accès et de conférence Web, ainsi que le service d’authentification A/V.</span><span class="sxs-lookup"><span data-stu-id="79bb1-104">Microsoft Lync Server 2013 communications software supports the use of a single public certificate for access and web conferencing Edge external interfaces, plus the A/V Authentication service.</span></span> <span data-ttu-id="79bb1-105">L’interface interne Edge utilise généralement un certificat privé émis par une autorité de certification interne, mais peut également utiliser un certificat public s’il provient d’une autorité de certification approuvée.</span><span class="sxs-lookup"><span data-stu-id="79bb1-105">The Edge internal interface typically uses a private certificate issued by an internal certification authority (CA), but can also use a public certificate, provided that it is from a trusted public CA.</span></span> <span data-ttu-id="79bb1-106">Le proxy inverse de votre déploiement utilise un certificat public et chiffre les communications du proxy inverse vers les clients et les serveurs internes en utilisant HTTP (c’est-à-dire, TLS sur HTTP).</span><span class="sxs-lookup"><span data-stu-id="79bb1-106">The reverse proxy in your deployment uses a public certificate and encrypts the communication from the reverse proxy to clients and the reverse proxy to internal servers by using HTTP (that is, Transport Layer Security over HTTP).</span></span>

<span data-ttu-id="79bb1-107">Le certificat public utilisé pour les interfaces externes Edge d’accès et de conférence web et pour le service d’authentification A/V doit remplir les conditions suivantes :</span><span class="sxs-lookup"><span data-stu-id="79bb1-107">Following are the requirements for the public certificate used for access and web conferencing Edge external interfaces, and the A/V authentication service:</span></span>

  - <span data-ttu-id="79bb1-108">Le certificat doit être émis par une autorité de certification publique approuvée qui prend en charge les autres noms de sujet.</span><span class="sxs-lookup"><span data-stu-id="79bb1-108">The certificate must be issued by an approved public CA that supports subject alternative name.</span></span> <span data-ttu-id="79bb1-109">Pour plus d’informations, consultez l’article 929395 de la base de connaissances Microsoft « partenaires de certificat de communications unifiées pour Exchange [http://go.microsoft.com/fwlink/p/?linkId=202834](http://go.microsoft.com/fwlink/p/?linkid=202834)Server et Communications Server », à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="79bb1-109">For details, see Microsoft Knowledge Base article 929395, "Unified Communications Certificate Partners for Exchange Server and for Communications Server," at [http://go.microsoft.com/fwlink/p/?linkId=202834](http://go.microsoft.com/fwlink/p/?linkid=202834).</span></span>

  - <span data-ttu-id="79bb1-p103">Si vous comptez utiliser le certificat dans un pool de serveurs Edge, vous devez le créer de manière à pouvoir l’exporter, en utilisant le même certificat sur chaque serveur Edge du pool. Les exigences de clé privée exportable concernent le service d’authentification A/V, qui doit utiliser la même clé privée sur tous les serveurs Edge du pool.</span><span class="sxs-lookup"><span data-stu-id="79bb1-p103">If the certificate will be used on an Edge pool, it must be created as exportable, with the same certificate used on each Edge Server in the Edge pool. The exportable private key requirement is for the purposes of the A/V Authentication service, which must use the same private key across all Edge Servers in the pool.</span></span>

  - <span data-ttu-id="79bb1-112">Si vous souhaitez maximiser le temps de fonctionnement de vos services audio/vidéo, consultez les conditions requises pour l’implémentation d’un certificat de service Edge A/V découplé (c’est-à-dire un certificat de service Edge A/V distinct des autres rôles de certificat Edge externe).</span><span class="sxs-lookup"><span data-stu-id="79bb1-112">If you want to maximize the uptime for your Audio/Video services, review the certificate requirements for implementing a decoupled A/V Edge service certificate (that is, a separate A/V Edge service certificate from the other External Edge certificate purposes).</span></span> <span data-ttu-id="79bb1-113">Pour plus d’informations, reportez-vous à la rubrique [changes in Lync server 2013 qui affectent la planification des serveurs Edge](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md), [planification des certificats de serveur Edge dans Lync Server 2013](lync-server-2013-plan-for-edge-server-certificates.md) et la [mise en œuvre de certificats AV et OAuth dans Lync Server 2013 à l’aide](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)de la CsCertificate.</span><span class="sxs-lookup"><span data-stu-id="79bb1-113">For details, see [Changes in Lync Server 2013 that affect Edge Server planning](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md), [Plan for Edge Server certificates in Lync Server 2013](lync-server-2013-plan-for-edge-server-certificates.md) and [Staging AV and OAuth certificates in Lync Server 2013 using -Roll in Set-CsCertificate](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate).</span></span>

  - <span data-ttu-id="79bb1-114">Le nom du sujet du certificat est le nom de domaine complet (FQDN) de l’interface externe du service Edge d’accès ou l’adresse IP du programme d’équilibrage de la charge matérielle (par exemple, access.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="79bb1-114">The subject name of the certificate is the Access Edge service external interface fully qualified domain name (FQDN) or hardware load balancer VIP (for example, access.contoso.com).</span></span> <span data-ttu-id="79bb1-115">).</span><span class="sxs-lookup"><span data-stu-id="79bb1-115">).</span></span> <span data-ttu-id="79bb1-116">Le nom du sujet ne peut pas contenir de caractère générique, il doit s’agir d’un nom explicite.</span><span class="sxs-lookup"><span data-stu-id="79bb1-116">The subject name can’t have a wildcard character, it must be an explicit name.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="79bb1-117">Pour Lync Server 2013, il ne s’agit plus d’une condition requise, mais elle est toujours recommandée pour la compatibilité avec Office Communications Server.</span><span class="sxs-lookup"><span data-stu-id="79bb1-117">For Lync Server 2013, this is no longer a requirement, but it is still recommended for compatibility with Office Communications Server.</span></span>

    
    </div>

  - <span data-ttu-id="79bb1-118">La liste des autres noms de sujet contient les noms de domaines complets des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="79bb1-118">The subject alternative name list contains the FQDNs of the following:</span></span>
    
      - <span data-ttu-id="79bb1-119">L’interface externe du service Edge d’accès ou l’adresse IP du programme d’équilibrage de la charge matérielle (par exemple, sip.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="79bb1-119">The Access Edge service external interface or hardware load balancer VIP (for example, sip.contoso.com).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="79bb1-120">Bien que le nom de sujet du certificat soit le même que le nom de domaine complet du serveur Edge d’accès, l’autre nom du sujet doit également contenir le nom de domaine complet du serveur Edge d’accès, car le protocole TLS (Transport Layer Security) ignore le nom du sujet et utilise les entrées des autres noms de sujet pour la validation.</span><span class="sxs-lookup"><span data-stu-id="79bb1-120">Even though the certificate subject name is equal to the access Edge FQDN, the subject alternative name must also contain the access Edge FQDN because Transport Layer Security (TLS) ignores the subject name and uses the subject alternative name entries for validation.</span></span>

        
        </div>
    
      - <span data-ttu-id="79bb1-121">l’interface externe du serveur Edge de conférence web ou l’adresse IP du programme d’équilibrage de la charge matérielle (par exemple, webcon.contoso.com) ;</span><span class="sxs-lookup"><span data-stu-id="79bb1-121">The web conferencing Edge external interface or hardware load balancer VIP (for example, webcon.contoso.com).</span></span>
    
      - <span data-ttu-id="79bb1-122">Si vous faites appel à la fédération ou à la configuration automatique des clients, incluez également les noms de domaines complets SIP utilisés dans votre entreprise (par exemple, sip.contoso.com, sip.fabrikam.com).</span><span class="sxs-lookup"><span data-stu-id="79bb1-122">If you are using client auto-configuration or federation, also include any SIP domain FQDNs used within your company (for example, sip.contoso.com, sip.fabrikam.com).</span></span>
    
      - <span data-ttu-id="79bb1-123">Le service Edge A/V n’utilise pas les entrées nom de l’objet ou autres noms du sujet.</span><span class="sxs-lookup"><span data-stu-id="79bb1-123">The A/V Edge service does not use the subject name or the subject alternative names entries.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="79bb1-124">L’ordre des noms de domaines complets dans la liste des autres noms de sujet n’a pas d’importance.</span><span class="sxs-lookup"><span data-stu-id="79bb1-124">The order of the FQDNs in the subject alternative names list does not matter.</span></span>

    
    </div>

<span data-ttu-id="79bb1-p106">Si vous déployez plusieurs serveurs Edge à charge équilibrée sur un site, le certificat du service d’authentification A/V qui est installé sur chaque serveur Edge doit provenir de la même autorité de certification et utiliser la même clé privée. Il est à noter que la clé privée du certificat doit pouvoir être exportée, qu’elle soit utilisée sur un ou plusieurs serveurs Edge. Elle doit pouvoir être exportée si vous demandez le certificat à un ordinateur autre que le serveur Edge. Comme le service d’authentification A/V n’utilise pas le nom du sujet ni un autre nom du sujet, vous pouvez réutiliser le certificat Edge d’accès, pourvu que les conditions liées au nom du sujet et aux autres noms du sujet sont remplies pour le serveur Edge d’accès et le serveur Edge de conférence web et que la clé privée du certificat puisse être exportée.</span><span class="sxs-lookup"><span data-stu-id="79bb1-p106">If you are deploying multiple, load-balanced Edge Servers at a site, the A/V authentication service certificate that is installed on each Edge Server must be from the same CA and must use the same private key. Note that the certificate's private key must be exportable, regardless of whether it is used on one Edge Server or many Edge Servers. It must also be exportable if you request the certificate from any computer other than the Edge Server. Because the A/V authentication service does not use the subject name or subject alternative name, you can reuse the access Edge certificate as long as the subject name and subject alternative name requirements are met for the access Edge and the web conferencing Edge and the certificate’s private key is exportable.</span></span>

<span data-ttu-id="79bb1-129">Les conditions requises pour l’utilisation d’un certificat privé (ou public) pour l’interface interne du serveur Edge sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="79bb1-129">Requirements for the private (or public) certificate used for the Edge internal interface are as follows:</span></span>

  - <span data-ttu-id="79bb1-130">Le certificat peut être émis par une autorité de certification interne ou une autorité de certification publique approuvée.</span><span class="sxs-lookup"><span data-stu-id="79bb1-130">The certificate can be issued by an internal CA or an approved public certificate CA.</span></span>

  - <span data-ttu-id="79bb1-p107">Le nom de sujet du certificat est généralement le nom de domaine complet de l’interface interne du serveur Edge ou l’adresse IP du programme d’équilibrage de la charge matérielle (par exemple, lsedge.contoso.com). Mais vous pouvez utiliser un certificat générique sur l’interface interne du serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="79bb1-p107">The subject name of the certificate is typically the Edge internal interface FQDN or hardware load balancer VIP (for example, lsedge.contoso.com). However, you can use a wildcard certificate on the Edge internal.</span></span>

  - <span data-ttu-id="79bb1-133">Aucune liste des autres noms de sujet n’est requise.</span><span class="sxs-lookup"><span data-stu-id="79bb1-133">No subject alternative name list is required.</span></span>

<span data-ttu-id="79bb1-134">Les exigences du proxy inverse de vos services de déploiement sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="79bb1-134">The reverse proxy in your deployment services requests for:</span></span>

  - <span data-ttu-id="79bb1-135">accès utilisateur externe au contenu de réunion pour les réunions ;</span><span class="sxs-lookup"><span data-stu-id="79bb1-135">External user access to meeting content for meetings</span></span>

  - <span data-ttu-id="79bb1-136">accès utilisateur externe au développement et à l’affichage des membres des groupes de distribution ;</span><span class="sxs-lookup"><span data-stu-id="79bb1-136">External user access to expand and display members of distribution groups</span></span>

  - <span data-ttu-id="79bb1-137">accès utilisateur externe aux fichiers téléchargeables du service de carnet d’adresses ;</span><span class="sxs-lookup"><span data-stu-id="79bb1-137">External user access to downloadable files from the Address Book Service</span></span>

  - <span data-ttu-id="79bb1-138">Accès des utilisateurs externes au client Lync Web App</span><span class="sxs-lookup"><span data-stu-id="79bb1-138">External user access to the Lync Web App client</span></span>

  - <span data-ttu-id="79bb1-139">accès utilisateur externe à la page web des paramètres de configuration des conférences rendez-vous ;</span><span class="sxs-lookup"><span data-stu-id="79bb1-139">External user access to the Dial-in Conferencing Settings web page</span></span>

  - <span data-ttu-id="79bb1-140">accès utilisateur externe au service Informations d’emplacement ;</span><span class="sxs-lookup"><span data-stu-id="79bb1-140">External user access to the Location Information Service</span></span>

  - <span data-ttu-id="79bb1-141">accès périphérique externe au service de mise à jour des périphériques et obtention des mises à jour.</span><span class="sxs-lookup"><span data-stu-id="79bb1-141">External device access to the Device Update Service and obtain updates</span></span>

<span data-ttu-id="79bb1-142">Le proxy inverse publie les URL des composants web de serveur interne.</span><span class="sxs-lookup"><span data-stu-id="79bb1-142">The reverse proxy publishes the internal server Web Components URLs.</span></span> <span data-ttu-id="79bb1-143">Les URL de composants WebPart sont définies sur le directeur, le serveur frontal ou le pool frontal en tant que **services Web externes** dans le générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="79bb1-143">The Web Components URLs are defined on the Director, Front End Server or Front End pool as the **External web services** in Topology Builder.</span></span>

<span data-ttu-id="79bb1-144">Les entrées avec caractères génériques sont prises en charge dans le champ d’autre nom de sujet du certificat affecté au proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="79bb1-144">Wildcard entries are supported in the subject alternative name field of the certificate assigned to the reverse proxy.</span></span> <span data-ttu-id="79bb1-145">Pour plus d’informations sur la configuration de la demande de certificat pour le proxy inverse, voir [demander et configurer un certificat pour votre proxy http inverse dans Lync Server 2013](lync-server-2013-request-and-configure-a-certificate-for-your-reverse-http-proxy.md).</span><span class="sxs-lookup"><span data-stu-id="79bb1-145">For details about how to configure the certificate request for the reverse proxy, see [Request and configure a certificate for your reverse HTTP proxy in Lync Server 2013](lync-server-2013-request-and-configure-a-certificate-for-your-reverse-http-proxy.md).</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="79bb1-146">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="79bb1-146">See Also</span></span>


[<span data-ttu-id="79bb1-147">Prise en charge de certificat générique dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="79bb1-147">Wildcard certificate support in Lync Server 2013</span></span>](lync-server-2013-wildcard-certificate-support.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

