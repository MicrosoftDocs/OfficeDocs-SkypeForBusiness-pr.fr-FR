---
title: 'Lync Server 2013 : configuration DNS requise pour les URL simples'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for simple URLs
ms:assetid: 3a3c9b22-892f-45a7-b05c-539d358a1a86
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425874(v=OCS.15)
ms:contentKeyID: 48183912
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 98db338c48bbb764aefe3d5cab4bcba58b2b23c4
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48501371"
---
# <a name="dns-requirements-for-simple-urls-in-lync-server-2013"></a><span data-ttu-id="84a4d-102">Configuration DNS requise pour les URL simples dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="84a4d-102">DNS requirements for simple URLs in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="https://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="84a4d-103">_**Dernière modification de la rubrique :** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="84a4d-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="84a4d-104">Lync Server 2013 prend en charge les URL simples qui facilitent la participation des réunions pour vos utilisateurs et facilitent l’accès aux outils d’administration de Lync Server pour vos administrateurs.</span><span class="sxs-lookup"><span data-stu-id="84a4d-104">Lync Server 2013 supports simple URLs, which make joining meetings easier for your users, and make getting to Lync Server administrative tools easier for your administrators.</span></span> <span data-ttu-id="84a4d-105">Pour plus d’informations sur les URL simples, voir [Planning for simple URLs in Lync Server 2013](lync-server-2013-planning-for-simple-urls.md).</span><span class="sxs-lookup"><span data-stu-id="84a4d-105">For details about simple URLs, see [Planning for simple URLs in Lync Server 2013](lync-server-2013-planning-for-simple-urls.md).</span></span>

<span data-ttu-id="84a4d-106">Lync Server prend en charge les trois URL simples suivantes : réunion, Conférence rendez-vous et administrateur. Vous devez configurer des URL simples pour la réunion et l’appel entrant, et l’URL simple d’administration est facultative.</span><span class="sxs-lookup"><span data-stu-id="84a4d-106">Lync Server supports the following three simple URLs: Meet, Dial-In, and Admin. You are required to set up simple URLs for Meet and Dial-In, and the Admin simple URL is optional.</span></span> <span data-ttu-id="84a4d-107">Les enregistrements DNS (Domain Name System) dont vous avez besoin pour prendre en charge les URL simples dépendent de la façon dont vous avez défini ces URL simples et si vous souhaitez prendre en charge la récupération d’urgence pour les URL simples.</span><span class="sxs-lookup"><span data-stu-id="84a4d-107">The Domain Name System (DNS) records that you need to support simple URLs depend on how you have defined these simple URLs, and whether you want to support disaster recovery for Simple URLs.</span></span>

<div>

## <a name="simple-url-option-1"></a><span data-ttu-id="84a4d-108">Option 1 de définition des URL simples</span><span class="sxs-lookup"><span data-stu-id="84a4d-108">Simple URL Option 1</span></span>

<span data-ttu-id="84a4d-109">Dans l’option 1, vous devez créer une URL de base pour chaque URL simple.</span><span class="sxs-lookup"><span data-stu-id="84a4d-109">In Option 1, you create a new base URL for each simple URL.</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="84a4d-p103">Lorsqu’un utilisateur clique sur un lien d’URL simple de réunion, le serveur que l’enregistrement DNS A résout détermine le logiciel client à démarrer. Une fois que le logiciel client a démarré, il communique automatiquement avec le pool hébergeant la conférence. Ainsi, les utilisateurs sont acheminés vers le serveur approprié indépendamment du serveur ou pool sur lequel les enregistrements DNS A d’URL simple sont résolus.</span><span class="sxs-lookup"><span data-stu-id="84a4d-p103">When a user clicks a simple URL meeting link, the server that the DNS A record resolves to determines the correct client software to start. After the client software is started, it automatically communicates with the pool where the conference is hosted. This way, users are directed to the appropriate server for meeting content no matter which server or pool the simple URL DNS A records resolve to.</span></span>



</div>

### <a name="simple-url-option-1"></a><span data-ttu-id="84a4d-113">Option 1 de définition des URL simples</span><span class="sxs-lookup"><span data-stu-id="84a4d-113">Simple URL Option 1</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="84a4d-114"><strong>URL simple</strong></span><span class="sxs-lookup"><span data-stu-id="84a4d-114"><strong>Simple URL</strong></span></span></p></td>
<td><p><span data-ttu-id="84a4d-115"><strong>Exemple</strong></span><span class="sxs-lookup"><span data-stu-id="84a4d-115"><strong>Example</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84a4d-116">Satisfaction</span><span class="sxs-lookup"><span data-stu-id="84a4d-116">Meet</span></span></p></td>
<td><p><span data-ttu-id="84a4d-117">https://meet.contoso.com, https://meet.fabrikam.com , et ainsi de suite (une pour chaque domaine SIP de votre organisation)</span><span class="sxs-lookup"><span data-stu-id="84a4d-117">https://meet.contoso.com, https://meet.fabrikam.com, and so on (one for each SIP domain in your organization)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="84a4d-118">Appels entrants</span><span class="sxs-lookup"><span data-stu-id="84a4d-118">Dial-in</span></span></p></td>
<td><p>https://dialin.contoso.com</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84a4d-119">Administrateur</span><span class="sxs-lookup"><span data-stu-id="84a4d-119">Admin</span></span></p></td>
<td><p>https://admin.contoso.com</p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="84a4d-120">Si vous utilisez l’Option 1, vous devez définir ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="84a4d-120">If you use Option 1, you must define the following:</span></span>

  - <span data-ttu-id="84a4d-p104">Pour chaque URL simple Meet, il est nécessaire de définir un enregistrement DNS A pour résoudre l’URL en adresse IP du directeur, si vous en avez déployé un. Sinon, il doit résoudre l’adresse IP du programme d’équilibrage de la charge d’un pool frontal. Si vous avez déployé un pool et utilisez un déploiement de serveur Standard Edition, l’enregistrement DNS A doit résoudre l’adresse IP d’un serveur Standard Edition de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="84a4d-p104">For each Meet simple URL, you need a DNS A record that resolves the URL to the IP address of the Director, if you have one deployed. Otherwise, it should resolve to the IP address of the load balancer of a Front End pool. If you have not deployed a pool and are using a Standard Edition server deployment, the DNS A record must resolve to the IP address of one Standard Edition server in your organization.</span></span>
    
    <span data-ttu-id="84a4d-124">Si votre organisation compte plusieurs domaines SIP et si vous utilisez cette option, vous devez créer des URL simples Meet pour chaque domaine SIP et créer un enregistrement DNS A pour chaque URL simple Meet.</span><span class="sxs-lookup"><span data-stu-id="84a4d-124">If you have more than one SIP domain in your organization and you use this option, you must create Meet simple URLs for each SIP domain and you need a DNS A record for each Meet simple URL.</span></span> <span data-ttu-id="84a4d-125">Par exemple, si vous avez à la fois contoso.com et fabrikam.com, vous allez créer des enregistrements DNS A pour les deux https://meet.contoso.com et https://meet.fabrikam.com .</span><span class="sxs-lookup"><span data-stu-id="84a4d-125">For example, if you have both contoso.com and fabrikam.com, you will create DNS A records for both https://meet.contoso.com and https://meet.fabrikam.com.</span></span>
    
    <span data-ttu-id="84a4d-126">En outre, si vous disposez de plusieurs domaines SIP et si vous souhaitez minimiser les enregistrements et les certificats DNS requis pour ces URL simples, utilisez l’option 3 présentée plus loin dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="84a4d-126">Alternatively, if you have multiple SIP domains and you want to minimize the DNS record and certificate requirements for these simple URLs, use Option 3 as described later in this topic.</span></span>

  - <span data-ttu-id="84a4d-p106">Pour chaque URL simple Dial-In, il est nécessaire de créer un enregistrement DNS A pour résoudre l’URL en adresse IP du directeur, si vous en avez déployé un. Sinon, il doit résoudre l’adresse IP du programme d’équilibrage de la charge d’un pool frontal. Si vous avez déployé un pool et utilisez un déploiement de serveur Standard Edition, l’enregistrement DNS A doit résoudre l’adresse IP d’un serveur Standard Edition de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="84a4d-p106">For the Dial-in simple URL, you need a DNS A record that resolves the URL to the IP address of the Director, if you have one deployed. Otherwise, it should resolve to the IP address of the load balancer of a Front End pool. If you have not deployed a pool and are using a Standard Edition server deployment, the DNS A record must resolve to the IP address of one Standard Edition server in your organization.</span></span>

  - <span data-ttu-id="84a4d-p107">L’URL simple Admin ne sert qu’en interne. Elle requiert un enregistrement DNS A pour résoudre l’URL en adresse IP du directeur, si vous en avez déployé un. Sinon, il doit résoudre l’adresse IP du programme d’équilibrage de la charge d’un pool frontal. Si vous avez déployé un pool et utilisez un déploiement de serveur Standard Edition, l’enregistrement DNS A doit résoudre l’adresse IP d’un serveur Standard Edition de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="84a4d-p107">The Admin simple URL is internal only. It requires a DNS A record that resolves the URL to the IP address of the Director, if you have one deployed. Otherwise, it should resolve to the IP address of the load balancer of a Front End pool. If you have not deployed a pool and are using a Standard Edition server deployment, the DNS A record must resolve to the IP address of one Standard Edition server in your organization.</span></span>

</div>

<div>

## <a name="simple-url-option-2"></a><span data-ttu-id="84a4d-134">Option 2 de définition des URL simples</span><span class="sxs-lookup"><span data-stu-id="84a4d-134">Simple URL Option 2</span></span>

<span data-ttu-id="84a4d-p108">Avec l’Option 2, les URL simples Meet, Dial-in et Admin ont une URL de base commune, telle que lync.contoso.com. Ainsi, ces URL simples ne requièrent qu’un enregistrement DNS A pour résoudre lync.contoso.com en l’adresse IP du pool directeur ou du pool frontal. Si vous avez déployé un pool et utilisez un déploiement de serveur Standard Edition, l’enregistrement DNS A doit résoudre l’adresse IP d’un serveur Standard Edition de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="84a4d-p108">With Option 2, the Meet, Dial-in, and Admin simple URLs all have a common base URL, such as lync.contoso.com. Therefore, you need only one DNS A record for these simple URLs, which resolves lync.contoso.com to the IP address of a Director pool or Front End pool. If you have not deployed a pool and are using a Standard Edition server deployment, the DNS A record must resolve to the IP address of one Standard Edition server in your organization.</span></span>

<span data-ttu-id="84a4d-138">Notez que si votre organisation compte plusieurs domaines SIP, vous devez tout de même créer des URL simples Meet pour chaque domaine SIP et un enregistrement DNS A pour chaque URL simple Meet.</span><span class="sxs-lookup"><span data-stu-id="84a4d-138">Note that if you have more than one SIP domain in your organization, you must still create Meet simple URLs for each SIP domain and you need a DNS A record for each Meet simple URL.</span></span> <span data-ttu-id="84a4d-139">Dans cet exemple, trois URL simples sont basées sur lync.contoso.com et une URL simple Meet supplémentaire est configurée avec une autre URL de base pour fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="84a4d-139">In this example, while three simple URLs are all based on lync.contoso.com, an additional Meet simple URL for fabrikam.com is set up with a different base URL.</span></span> <span data-ttu-id="84a4d-140">Dans cet exemple, vous devez créer des enregistrements DNS A pour les deux https://lync.contoso.com et https://lync.fabrikam.com .</span><span class="sxs-lookup"><span data-stu-id="84a4d-140">In this example, you must create DNS A records for both https://lync.contoso.com and https://lync.fabrikam.com.</span></span> <span data-ttu-id="84a4d-141">L’Option 3 présente une autre méthode de gestion des noms et des enregistrements DNS A si vous disposez de plusieurs domaines SIP.</span><span class="sxs-lookup"><span data-stu-id="84a4d-141">Simple URL Option 3 shows another way to handle naming and DNS A records if you have multiple SIP domains.</span></span>

### <a name="simple-url-option-2"></a><span data-ttu-id="84a4d-142">Option 2 de définition des URL simples</span><span class="sxs-lookup"><span data-stu-id="84a4d-142">Simple URL Option 2</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="84a4d-143"><strong>URL simple</strong></span><span class="sxs-lookup"><span data-stu-id="84a4d-143"><strong>Simple URL</strong></span></span></p></td>
<td><p><span data-ttu-id="84a4d-144"><strong>Exemple</strong></span><span class="sxs-lookup"><span data-stu-id="84a4d-144"><strong>Example</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84a4d-145">Satisfaction</span><span class="sxs-lookup"><span data-stu-id="84a4d-145">Meet</span></span></p></td>
<td><p><span data-ttu-id="84a4d-146">https://lync.contoso.com/Meet, https://lync.fabrikam.com/Meet , et ainsi de suite (une pour chaque domaine SIP de votre organisation)</span><span class="sxs-lookup"><span data-stu-id="84a4d-146">https://lync.contoso.com/Meet, https://lync.fabrikam.com/Meet, and so on (one for each SIP domain in your organization)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="84a4d-147">Appels entrants</span><span class="sxs-lookup"><span data-stu-id="84a4d-147">Dial-in</span></span></p></td>
<td><p>https://lync.contoso.com/Dialin</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84a4d-148">Administrateur</span><span class="sxs-lookup"><span data-stu-id="84a4d-148">Admin</span></span></p></td>
<td><p>https://lync.contoso.com/Admin</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="simple-url-option-3"></a><span data-ttu-id="84a4d-149">Option 3 de définition des URL simples</span><span class="sxs-lookup"><span data-stu-id="84a4d-149">Simple URL Option 3</span></span>

<span data-ttu-id="84a4d-p110">L’option 3 est particulièrement utile si vous disposez de plusieurs domaines SIP et si vous souhaitez qu’ils aient des URL simples distinctes, mais souhaitez minimiser les enregistrements et les certificats DNS requis pour ces URL simples. Dans cet exemple, un seul enregistrement DNS A est nécessaire. Il est chargé de résoudre lync.contoso.com en l’adresse IP du pool directeur ou du pool frontal.</span><span class="sxs-lookup"><span data-stu-id="84a4d-p110">Option 3 is most useful if you have many SIP domains, and you want them to have separate simple URLs but want to minimize the DNS record and certificate requirements for these simple URLs. In this example, you need only one DNS A record, which resolves lync.contoso.com to the IP address of a Director pool or Front End pool.</span></span>

### <a name="simple-url-option-3"></a><span data-ttu-id="84a4d-152">Option 3 de définition des URL simples</span><span class="sxs-lookup"><span data-stu-id="84a4d-152">Simple URL Option 3</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="84a4d-153"><strong>URL simple</strong></span><span class="sxs-lookup"><span data-stu-id="84a4d-153"><strong>Simple URL</strong></span></span></p></td>
<td><p><span data-ttu-id="84a4d-154"><strong>Exemple</strong></span><span class="sxs-lookup"><span data-stu-id="84a4d-154"><strong>Example</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84a4d-155">Satisfaction</span><span class="sxs-lookup"><span data-stu-id="84a4d-155">Meet</span></span></p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Meet</p>
<p>https://lync.contoso.com/fabrikamSIPdomain/Meet</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="84a4d-156">Appels entrants</span><span class="sxs-lookup"><span data-stu-id="84a4d-156">Dial-in</span></span></p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Dialin</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84a4d-157">Administrateur</span><span class="sxs-lookup"><span data-stu-id="84a4d-157">Admin</span></span></p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Admin</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="disaster-recovery-option-for-simple-urls"></a><span data-ttu-id="84a4d-158">Option de récupération d’urgence pour les URL simples</span><span class="sxs-lookup"><span data-stu-id="84a4d-158">Disaster Recovery Option for Simple URLs</span></span>

<span data-ttu-id="84a4d-159">Si vous avez plusieurs sites qui contiennent des pools frontaux et que votre fournisseur DNS prend en charge GeoDNS, vous pouvez configurer vos enregistrements DNS pour des URL simples afin de prendre en charge la récupération d’urgence, de sorte que la fonctionnalité d’URL simple continue même si un pool frontal entier tombe en panne.</span><span class="sxs-lookup"><span data-stu-id="84a4d-159">If you have multiple sites that contain Front End pools and your DNS provider supports GeoDNS, you can set up your DNS records for Simple URLs to support disaster recovery, so that Simple URL functionality continues even if one entire Front End pool goes down.</span></span> <span data-ttu-id="84a4d-160">Cette fonctionnalité de récupération d’urgence prend en charge les URL simples de conférence et d’accès à distance.</span><span class="sxs-lookup"><span data-stu-id="84a4d-160">This disaster recovery feature supports the Meet and Dial-In simple URLs.</span></span>

<span data-ttu-id="84a4d-p112">Pour configurer cette option, créez deux adresses GeoDNS. Chacune d’elles comprend deux enregistrements DNS A ou CNAME qui aboutissent à deux pools couplés à des fins de récupération d’urgence. Une adresse GeoDNS est utilisée pour l’accès interne et aboutit au nom de domaine complet web interne ou à l’adresse IP d’équilibrage de charge des deux pools. L’autre adresse GeoDNS est utilisée pour l’accès externe et aboutit au nom de domaine complet web externe ou à l’adresse IP d’équilibrage de charge des deux pools. L’exemple ci-dessous s’applique à l’URL simple Meet et utilise les noms de domaine complets des pools.</span><span class="sxs-lookup"><span data-stu-id="84a4d-p112">To configure this, create two GeoDNS addresses. Each address has two DNS A or CNAME records that resolve to two pools which are paired together for disaster recovery purposes. One GeoDNS address is used for internal access, and resolves to the internal web FQDN or load balancer IP address for the two pools. The other GeoDNS address is used for external access and resolves to the external web FQDN or load balancer IP address for the two pools. The following is an example for the Meet simple URL, using the FQDNs for the pools.</span></span>

   ```console
    Meet-int.geolb.contoso.com
         Pool1InternalWebFQDN.contoso.com
         Pool2InternalWebFQDN.contoso.com
   ```

   ```console
   Meet-ext.geolb.contoso.com
         Pool1ExternalWebFQDN.contoso.com
         Pool2ExternalWebFQDN.contoso.com
   ``` 

<span data-ttu-id="84a4d-166">Créez ensuite des enregistrements CNAME qui font aboutir l’URL simple Meet (telles que meet.contoso.com) aux deux adresses GeoDNS.</span><span class="sxs-lookup"><span data-stu-id="84a4d-166">Then create CNAME records that resolve your Meet simple URL (such as meet.contoso.com) to the two GeoDNS addresses.</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="84a4d-167">Si votre réseau utilise le <EM>hairpinning</EM> (routage de l’ensemble du trafic de l’URL simple via le lien externe, y compris le trafic en provenance de votre organisation), vous pouvez simplement configurer l’adresse GeoDNS externe et faire aboutir votre adresse URL simple Meet uniquement à cette adresse externe.</span><span class="sxs-lookup"><span data-stu-id="84a4d-167">If your network uses <EM>hairpinning</EM> (routing all your Simple URL traffic through the external link, including traffic that comes from within your organization), then you can just configure the external GeoDNS address and resolve your Meet simple URL to only that external address.</span></span>



</div>

<span data-ttu-id="84a4d-168">Lorsque vous utilisez cette méthode, vous pouvez configurer chaque adresse GeoDNS de façon à distribuer les demandes aux deux pools selon la méthode du tourniquet (round robin), ou bien vous connecter principalement à un pool (par exemple, le pool le plus proche géographiquement) et utiliser l’autre pool seulement en cas de problème de connectivité.</span><span class="sxs-lookup"><span data-stu-id="84a4d-168">When you use this method, you can configure each GeoDNS address to use either a round robin method to distribute requests to the two pools, or to connect primarily to one pool (such as the pool located geographically closer) and use the other pool only in case of connectivity failure.</span></span>

<span data-ttu-id="84a4d-169">Vous pouvez définir la même configuration pour l’URL simple Dial-In.</span><span class="sxs-lookup"><span data-stu-id="84a4d-169">You can set up the same configuration for the Dial-In simple URL.</span></span> <span data-ttu-id="84a4d-170">Pour ce faire, créez des enregistrements supplémentaires comme ceux de l’exemple précédent, `dialin` en remplaçant `meet` les enregistrements DNS.</span><span class="sxs-lookup"><span data-stu-id="84a4d-170">To do so, create additional records like those in the previous example, substituting `dialin` for `meet` in the DNS records.</span></span> <span data-ttu-id="84a4d-171">Pour l’URL simple Admin, utilisez l’une des trois options mentionnées plus haut dans cette section.</span><span class="sxs-lookup"><span data-stu-id="84a4d-171">For the Admin simple URL, use one of the three options listed earlier in this section.</span></span>

<span data-ttu-id="84a4d-172">Après avoir défini cette configuration, vous devez utiliser une application de surveillance pour configurer la recherche de défaillance via la surveillance HTTP.</span><span class="sxs-lookup"><span data-stu-id="84a4d-172">Once this configuration is set up, you must use a monitoring application to set up HTTP monitoring to watch for failures.</span></span> <span data-ttu-id="84a4d-173">Pour l’accès externe, surveillez pour vous assurer que le protocole HTTPs obtient des demandes de découverte automatique pour le nom de domaine complet Web externe ou l’adresse IP du programme d’équilibrage de charge pour les deux pools.</span><span class="sxs-lookup"><span data-stu-id="84a4d-173">For external access, monitor to make sure that HTTPS GET autodiscovery requests to the external web FQDN or load balancer IP address for the two pools are successful.</span></span> <span data-ttu-id="84a4d-174">Par exemple, les demandes suivantes ne doivent pas contenir d’en-tête **ACCEPT** et doivent retourner **200 OK**.</span><span class="sxs-lookup"><span data-stu-id="84a4d-174">For example, the following requests must not contain any **ACCEPT** header and must return **200 OK**.</span></span>

```console
    HTTPS GET Pool1ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
    HTTPS GET Pool2ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
```

<span data-ttu-id="84a4d-p115">Pour l’accès interne, vous devez surveiller le port 5061 sur le nom de domaine complet web interne ou l’adresse IP d’équilibrage de charge pour les deux pools. Si des problèmes de connectivité sont détectés, l’adresse IP virtuelle de ces deux pools doit fermer les ports 80, 443 et 444.</span><span class="sxs-lookup"><span data-stu-id="84a4d-p115">For internal access, you must monitor port 5061 on the internal web FQDN or load balancer IP address for the two pools. If any connectivity failures are detected, the VIP for these pools must close ports 80, 443 and 444.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

