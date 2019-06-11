---
title: 'Lync Server 2013 : Certificats requis pour l’accès des utilisateurs externes'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Certificate requirements for external user access
ms:assetid: d45b6b10-556f-4b10-b1a7-fb0d0a64a498
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398920(v=OCS.15)
ms:contentKeyID: 48185503
ms.date: 03/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7e7a0802cee8b91e18eaf50e5c2c3942ca54308
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838662"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-requirements-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="f2d0c-102">Certificats requis pour l’accès des utilisateurs externes dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f2d0c-102">Certificate requirements for external user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f2d0c-103">_**Dernière modification de la rubrique:** 2016-03-29_</span><span class="sxs-lookup"><span data-stu-id="f2d0c-103">_**Topic Last Modified:** 2016-03-29_</span></span>

<span data-ttu-id="f2d0c-104">Le logiciel de communications Microsoft Lync Server 2013 prend en charge l’utilisation d’un certificat public unique pour les interfaces externes d’accès et de conférence Web, ainsi que le service d’authentification A/V.</span><span class="sxs-lookup"><span data-stu-id="f2d0c-104">Microsoft Lync Server 2013 communications software supports the use of a single public certificate for access and web conferencing Edge external interfaces, plus the A/V Authentication service.</span></span> <span data-ttu-id="f2d0c-105">L’interface interne Edge utilise généralement un certificat privé émis par une autorité de certification interne, mais peut également utiliser un certificat public, à condition qu’il émane d’une autorité de certification publique de confiance.</span><span class="sxs-lookup"><span data-stu-id="f2d0c-105">The Edge internal interface typically uses a private certificate issued by an internal certification authority (CA), but can also use a public certificate, provided that it is from a trusted public CA.</span></span> <span data-ttu-id="f2d0c-106">Le proxy inverse dans votre déploiement utilise un certificat public et chiffre la communication à partir du proxy inverse vers les clients et du proxy inverse vers les serveurs internes en utilisant HTTP (c’est-à-dire, Transport Layer Security sur HTTP).</span><span class="sxs-lookup"><span data-stu-id="f2d0c-106">The reverse proxy in your deployment uses a public certificate and encrypts the communication from the reverse proxy to clients and the reverse proxy to internal servers by using HTTP (that is, Transport Layer Security over HTTP).</span></span>

<span data-ttu-id="f2d0c-107">Vous trouverez ci-après les exigences relatives au certificat public utilisé pour les interfaces externes d’accès et de conférence Web, ainsi que le service d’authentification A/V:</span><span class="sxs-lookup"><span data-stu-id="f2d0c-107">Following are the requirements for the public certificate used for access and web conferencing Edge external interfaces, and the A/V authentication service:</span></span>

  - <span data-ttu-id="f2d0c-108">Le certificat doit être émis par une autorité de certification publique approuvée prenant en charge le nom alternatif de l’objet.</span><span class="sxs-lookup"><span data-stu-id="f2d0c-108">The certificate must be issued by an approved public CA that supports subject alternative name.</span></span> <span data-ttu-id="f2d0c-109">Pour plus d’informations, reportez-vous à l’article 929395 de la base de connaissances Microsoft «partenaires de certification de [http://go.microsoft.com/fwlink/p/?linkId=202834](http://go.microsoft.com/fwlink/p/?linkid=202834)communications unifiées pour Exchange Server et pour Communications Server».</span><span class="sxs-lookup"><span data-stu-id="f2d0c-109">For details, see Microsoft Knowledge Base article 929395, "Unified Communications Certificate Partners for Exchange Server and for Communications Server," at [http://go.microsoft.com/fwlink/p/?linkId=202834](http://go.microsoft.com/fwlink/p/?linkid=202834).</span></span>

  - <span data-ttu-id="f2d0c-110">Si le certificat doit être utilisé sur un pool de bords, il doit être créé en tant qu’exportable, avec le même certificat utilisé sur chaque serveur Edge du pool de bords.</span><span class="sxs-lookup"><span data-stu-id="f2d0c-110">If the certificate will be used on an Edge pool, it must be created as exportable, with the same certificate used on each Edge Server in the Edge pool.</span></span> <span data-ttu-id="f2d0c-111">La configuration requise pour une clé privée interportée est utilisée dans le cadre du service d’authentification A/V, qui doit utiliser la même clé privée sur tous les serveurs Edge du pool.</span><span class="sxs-lookup"><span data-stu-id="f2d0c-111">The exportable private key requirement is for the purposes of the A/V Authentication service, which must use the same private key across all Edge Servers in the pool.</span></span>

  - <span data-ttu-id="f2d0c-112">Si vous souhaitez optimiser la durée de fonctionnement de vos services audio et vidéo, consultez les conditions requises pour l’implémentation d’un certificat de service Edge A/v (autrement dit, un certificat de service Edge A/V distinct à partir de l’autre application de certificat Edge externe).</span><span class="sxs-lookup"><span data-stu-id="f2d0c-112">If you want to maximize the uptime for your Audio/Video services, review the certificate requirements for implementing a decoupled A/V Edge service certificate (that is, a separate A/V Edge service certificate from the other External Edge certificate purposes).</span></span> <span data-ttu-id="f2d0c-113">Pour plus d’informations, reportez-vous à la section [modifications dans Lync server 2013 qui affectent la planification du serveur Edge](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md), [planifier les certificats de serveur Edge dans Lync Server 2013](lync-server-2013-plan-for-edge-server-certificates.md) et les [certificats OAuth dans Lync Server 2013 à l’aide de Set-CsCertificate](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate).</span><span class="sxs-lookup"><span data-stu-id="f2d0c-113">For details, see [Changes in Lync Server 2013 that affect Edge Server planning](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md), [Plan for Edge Server certificates in Lync Server 2013](lync-server-2013-plan-for-edge-server-certificates.md) and [Staging AV and OAuth certificates in Lync Server 2013 using -Roll in Set-CsCertificate](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate).</span></span>

  - <span data-ttu-id="f2d0c-114">Le nom du sujet du certificat est le nom de domaine complet (FQDN) du service Edge d’accès ou le protocole VIP d’équilibrage de charge matérielle (par exemple, access.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="f2d0c-114">The subject name of the certificate is the Access Edge service external interface fully qualified domain name (FQDN) or hardware load balancer VIP (for example, access.contoso.com).</span></span> <span data-ttu-id="f2d0c-115">).</span><span class="sxs-lookup"><span data-stu-id="f2d0c-115"></span></span> <span data-ttu-id="f2d0c-116">Le nom du sujet ne peut pas contenir de caractère générique, il doit s’agir d’un nom explicite.</span><span class="sxs-lookup"><span data-stu-id="f2d0c-116">The subject name can’t have a wildcard character, it must be an explicit name.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f2d0c-117">Pour Lync Server 2013, il ne s’agit plus d’une exigence, mais elle est toujours recommandée pour la compatibilité avec Office Communications Server.</span><span class="sxs-lookup"><span data-stu-id="f2d0c-117">For Lync Server 2013, this is no longer a requirement, but it is still recommended for compatibility with Office Communications Server.</span></span>

    
    </div>

  - <span data-ttu-id="f2d0c-118">La liste autre nom de l’objet contient les noms de domaine complets des éléments suivants:</span><span class="sxs-lookup"><span data-stu-id="f2d0c-118">The subject alternative name list contains the FQDNs of the following:</span></span>
    
      - <span data-ttu-id="f2d0c-119">L’interface externe du service Edge d’accès ou l’adresse VIP d’équilibrage de charge matérielle (par exemple, sip.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="f2d0c-119">The Access Edge service external interface or hardware load balancer VIP (for example, sip.contoso.com).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="f2d0c-120">Même si le nom du sujet du certificat est égal au nom de domaine complet du bord d’accès, le nom de l’autre sujet doit également contenir le nom de domaine complet Edge d’accès, car TLS (Transport Layer Security) ignore le nom du sujet et utilise les entrées de nom de l’objet pour Liquid.</span><span class="sxs-lookup"><span data-stu-id="f2d0c-120">Even though the certificate subject name is equal to the access Edge FQDN, the subject alternative name must also contain the access Edge FQDN because Transport Layer Security (TLS) ignores the subject name and uses the subject alternative name entries for validation.</span></span>

        
        </div>
    
      - <span data-ttu-id="f2d0c-121">L’interface ou l’adresse IP (par exemple, webcon.contoso.com) pour la conférence Web.</span><span class="sxs-lookup"><span data-stu-id="f2d0c-121">The web conferencing Edge external interface or hardware load balancer VIP (for example, webcon.contoso.com).</span></span>
    
      - <span data-ttu-id="f2d0c-122">Si vous utilisez la configuration automatique du client ou la Fédération, incluez également les noms de domaine complets du domaine SIP utilisés au sein de votre entreprise (par exemple, sip.contoso.com, sip.fabrikam.com).</span><span class="sxs-lookup"><span data-stu-id="f2d0c-122">If you are using client auto-configuration or federation, also include any SIP domain FQDNs used within your company (for example, sip.contoso.com, sip.fabrikam.com).</span></span>
    
      - <span data-ttu-id="f2d0c-123">Le service Edge A/V n’utilise pas le nom du sujet ou les entrées de noms de substitution d’objet.</span><span class="sxs-lookup"><span data-stu-id="f2d0c-123">The A/V Edge service does not use the subject name or the subject alternative names entries.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f2d0c-124">L’ordre des noms de domaine complets dans la liste des noms de remplacement de l’objet n’a pas d’importance.</span><span class="sxs-lookup"><span data-stu-id="f2d0c-124">The order of the FQDNs in the subject alternative names list does not matter.</span></span>

    
    </div>

<span data-ttu-id="f2d0c-125">Si vous déployez plusieurs serveurs Edge équilibrés sur un site, le certificat de service d’authentification A/V qui est installé sur chaque serveur Edge doit être issu de la même autorité de certification et doit utiliser la même clé privée.</span><span class="sxs-lookup"><span data-stu-id="f2d0c-125">If you are deploying multiple, load-balanced Edge Servers at a site, the A/V authentication service certificate that is installed on each Edge Server must be from the same CA and must use the same private key.</span></span> <span data-ttu-id="f2d0c-126">Notez que la clé privée du certificat doit être exportable, qu’elle soit utilisée ou non sur un serveur Edge ou sur de nombreux serveurs Edge.</span><span class="sxs-lookup"><span data-stu-id="f2d0c-126">Note that the certificate's private key must be exportable, regardless of whether it is used on one Edge Server or many Edge Servers.</span></span> <span data-ttu-id="f2d0c-127">Elle doit également être exportée si vous demandez le certificat à partir de n’importe quel ordinateur autre que le serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="f2d0c-127">It must also be exportable if you request the certificate from any computer other than the Edge Server.</span></span> <span data-ttu-id="f2d0c-128">Dans la mesure où le service d’authentification A/V n’utilise pas le nom du sujet ou l’autre nom de l’objet, vous pouvez réutiliser le certificat de bord d’accès tant que le nom de l’objet et le nom de l’objet autre nom doivent être satisfaits pour le bord d’accès et le bord de conférence Web. la clé privée du certificat est alors exportable.</span><span class="sxs-lookup"><span data-stu-id="f2d0c-128">Because the A/V authentication service does not use the subject name or subject alternative name, you can reuse the access Edge certificate as long as the subject name and subject alternative name requirements are met for the access Edge and the web conferencing Edge and the certificate’s private key is exportable.</span></span>

<span data-ttu-id="f2d0c-129">Les conditions requises pour le certificat privé (ou public) utilisé pour l’interface interne latérale sont les suivantes:</span><span class="sxs-lookup"><span data-stu-id="f2d0c-129">Requirements for the private (or public) certificate used for the Edge internal interface are as follows:</span></span>

  - <span data-ttu-id="f2d0c-130">Le certificat peut être émis par une autorité de certification interne ou par un certificat public approuvé.</span><span class="sxs-lookup"><span data-stu-id="f2d0c-130">The certificate can be issued by an internal CA or an approved public certificate CA.</span></span>

  - <span data-ttu-id="f2d0c-131">Le nom du sujet du certificat est généralement le nom de domaine complet (FQDN) de l’interface interne Edge ou l’adresse VIP de l’équilibrage de charge matérielle (par exemple, lsedge.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="f2d0c-131">The subject name of the certificate is typically the Edge internal interface FQDN or hardware load balancer VIP (for example, lsedge.contoso.com).</span></span> <span data-ttu-id="f2d0c-132">Toutefois, vous pouvez utiliser un certificat générique sur le bord interne.</span><span class="sxs-lookup"><span data-stu-id="f2d0c-132">However, you can use a wildcard certificate on the Edge internal.</span></span>

  - <span data-ttu-id="f2d0c-133">Il n’y a pas besoin d’une autre liste de noms d’objet.</span><span class="sxs-lookup"><span data-stu-id="f2d0c-133">No subject alternative name list is required.</span></span>

<span data-ttu-id="f2d0c-134">Le proxy inverse dans vos demandes de services de déploiement pour:</span><span class="sxs-lookup"><span data-stu-id="f2d0c-134">The reverse proxy in your deployment services requests for:</span></span>

  - <span data-ttu-id="f2d0c-135">Accès des utilisateurs externes au contenu de la réunion pour les réunions</span><span class="sxs-lookup"><span data-stu-id="f2d0c-135">External user access to meeting content for meetings</span></span>

  - <span data-ttu-id="f2d0c-136">Accès d’un utilisateur externe pour développer et afficher des membres de groupes de distribution.</span><span class="sxs-lookup"><span data-stu-id="f2d0c-136">External user access to expand and display members of distribution groups</span></span>

  - <span data-ttu-id="f2d0c-137">Accès des utilisateurs externes aux fichiers téléchargeables à partir du service de carnet d’adresses</span><span class="sxs-lookup"><span data-stu-id="f2d0c-137">External user access to downloadable files from the Address Book Service</span></span>

  - <span data-ttu-id="f2d0c-138">Accès des utilisateurs externes au client Lync Web App</span><span class="sxs-lookup"><span data-stu-id="f2d0c-138">External user access to the Lync Web App client</span></span>

  - <span data-ttu-id="f2d0c-139">Accès des utilisateurs externes à la page Web des paramètres de conférence rendez-vous</span><span class="sxs-lookup"><span data-stu-id="f2d0c-139">External user access to the Dial-in Conferencing Settings web page</span></span>

  - <span data-ttu-id="f2d0c-140">Accès des utilisateurs externes au service d’information d’emplacement</span><span class="sxs-lookup"><span data-stu-id="f2d0c-140">External user access to the Location Information Service</span></span>

  - <span data-ttu-id="f2d0c-141">Accès d’appareil externe au service de mise à jour de l’appareil et obtention des mises à jour</span><span class="sxs-lookup"><span data-stu-id="f2d0c-141">External device access to the Device Update Service and obtain updates</span></span>

<span data-ttu-id="f2d0c-142">Le proxy inverse publie les URL des composants internes du serveur Web.</span><span class="sxs-lookup"><span data-stu-id="f2d0c-142">The reverse proxy publishes the internal server Web Components URLs.</span></span> <span data-ttu-id="f2d0c-143">Les URL des composants WebPart sont définies sur le directeur, le serveur frontal ou le pool frontal comme **services Web externes** dans le générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="f2d0c-143">The Web Components URLs are defined on the Director, Front End Server or Front End pool as the **External web services** in Topology Builder.</span></span>

<span data-ttu-id="f2d0c-144">Les entrées de caractères génériques sont prises en charge dans le champ autre nom de l’objet du certificat attribué au proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="f2d0c-144">Wildcard entries are supported in the subject alternative name field of the certificate assigned to the reverse proxy.</span></span> <span data-ttu-id="f2d0c-145">Pour plus d’informations sur la configuration de la demande de certificat pour le proxy inverse, voir [demander et configurer un certificat pour votre proxy http inverse dans Lync Server 2013](lync-server-2013-request-and-configure-a-certificate-for-your-reverse-http-proxy.md).</span><span class="sxs-lookup"><span data-stu-id="f2d0c-145">For details about how to configure the certificate request for the reverse proxy, see [Request and configure a certificate for your reverse HTTP proxy in Lync Server 2013](lync-server-2013-request-and-configure-a-certificate-for-your-reverse-http-proxy.md).</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="f2d0c-146">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f2d0c-146">See Also</span></span>


[<span data-ttu-id="f2d0c-147">Prise en charge des certificats comportant des caractères génériques dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f2d0c-147">Wildcard certificate support in Lync Server 2013</span></span>](lync-server-2013-wildcard-certificate-support.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

