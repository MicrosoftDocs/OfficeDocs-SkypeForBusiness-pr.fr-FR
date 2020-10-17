---
title: 'Lync Server 2013 : conditions requises pour les certificats pour les serveurs internes'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate requirements for internal servers
ms:assetid: 0444cdbd-538c-43b1-b9a1-9d7d6cf818d6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398094(v=OCS.15)
ms:contentKeyID: 48183270
ms.date: 02/17/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c56554a26e5f64089a766300f375039409680578
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526241"
---
# <a name="certificate-requirements-for-internal-servers-in-lync-server-2013"></a><span data-ttu-id="bec31-102">Exigences de certificat pour les serveurs internes dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bec31-102">Certificate requirements for internal servers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bec31-103">_**Dernière modification de la rubrique :** 2017-02-17_</span><span class="sxs-lookup"><span data-stu-id="bec31-103">_**Topic Last Modified:** 2017-02-17_</span></span>

<span data-ttu-id="bec31-104">Les serveurs internes qui exécutent Lync Server et qui nécessitent des certificats incluent le serveur Standard Edition, le serveur frontal Enterprise Edition, le serveur de médiation et le directeur.</span><span class="sxs-lookup"><span data-stu-id="bec31-104">Internal servers that are running Lync Server and that require certificates include Standard Edition server, Enterprise Edition Front End Server, Mediation Server, and Director.</span></span> <span data-ttu-id="bec31-105">Le tableau suivant indique les certificats requis pour ces serveurs.</span><span class="sxs-lookup"><span data-stu-id="bec31-105">The following table shows the certificate requirements for these servers.</span></span> <span data-ttu-id="bec31-106">Vous pouvez utiliser l’Assistant Certificat Lync Server pour demander ces certificats.</span><span class="sxs-lookup"><span data-stu-id="bec31-106">You can use the Lync Server certificate wizard to request these certificates.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="bec31-107">Les certificats génériques sont pris en charge pour les autres noms de sujet associés aux URL simples sur le pool frontal, le serveur frontal ou le directeur.</span><span class="sxs-lookup"><span data-stu-id="bec31-107">Wildcard certificates are supported for the subject alternative names associated with the simple URLs on the Front End pool, Front End Server, or Director.</span></span> <span data-ttu-id="bec31-108">Pour plus d’informations sur la prise en charge des certificats génériques, consultez la rubrique <A href="lync-server-2013-wildcard-certificate-support.md">générique Certificate support in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="bec31-108">For details about wildcard certificate support, see <A href="lync-server-2013-wildcard-certificate-support.md">Wildcard certificate support in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="bec31-109">Bien qu’il soit recommandé d’utiliser une autorité de certification d’entreprise interne pour les serveurs internes, vous pouvez également utiliser une autorité de certification publique.</span><span class="sxs-lookup"><span data-stu-id="bec31-109">Although an internal enterprise certification authority (CA) is recommended for internal servers, you can also use a public CA.</span></span> <span data-ttu-id="bec31-110">Pour obtenir la liste des autorités de certification publiques qui fournissent des certificats conformes aux exigences spécifiques pour les certificats de communications unifiées et qui ont conclu un partenariat avec Microsoft afin de s’assurer qu’ils fonctionnent avec l’Assistant Certificat Lync Server, consultez la base de connaissances Microsoft 929395, « partenaires de certificat de communications unifiées pour Exchange Server et Communications Server », à l’adresse [https://go.microsoft.com/fwlink/p/?linkId=202834](https://go.microsoft.com/fwlink/p/?linkid=202834) .</span><span class="sxs-lookup"><span data-stu-id="bec31-110">For a list of public CAs that provide certificates that comply with specific requirements for unified communications (UC) certificates and have partnered with Microsoft to ensure they work with the Lync Server Certificate Wizard, see article Microsoft Knowledge Base 929395, "Unified Communications Certificate Partners for Exchange Server and for Communications Server," at [https://go.microsoft.com/fwlink/p/?linkId=202834](https://go.microsoft.com/fwlink/p/?linkid=202834).</span></span>

<span data-ttu-id="bec31-111">La communication avec d’autres applications et serveurs, comme Exchange 2013, nécessite un certificat pris en charge par les autres applications et produits.</span><span class="sxs-lookup"><span data-stu-id="bec31-111">Communication with other applications and servers, such as Exchange 2013, requires a certificate that is supported by the other applications and products.</span></span> <span data-ttu-id="bec31-112">Pour la version 2013, Lync Server 2013 et d’autres produits serveur Microsoft, y compris Exchange 2013 et SharePoint Server, prennent en charge le protocole d’autorisation d’ouverture (OAuth) pour l’authentification et l’autorisation de serveur à serveur.</span><span class="sxs-lookup"><span data-stu-id="bec31-112">For the 2013 release, Lync Server 2013 and other Microsoft server products, including Exchange 2013 and SharePoint Server, support the Open Authorization (OAuth) protocol for server-to-server authentication and authorization.</span></span> <span data-ttu-id="bec31-113">Pour plus d’informations, reportez-vous à la rubrique [Managing Server-to-Server Authentication (OAuth) and Partner applications in Lync server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) dans la documentation de déploiement ou la documentation des opérations.</span><span class="sxs-lookup"><span data-stu-id="bec31-113">For details, see [Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) in the Deployment documentation or the Operations documentation.</span></span>

<span data-ttu-id="bec31-114">Pour les connexions à partir de clients exécutant le système d’exploitation Windows 7, le système d’exploitation Windows Server 2008, le système d’exploitation Windows Server 2008 R2, le système d’exploitation Windows Vista et Microsoft Lync Phone Edition, Lync Server 2013 inclut la prise en charge des certificats signés à l’aide de la fonction de hachage cryptographique SHA-256.</span><span class="sxs-lookup"><span data-stu-id="bec31-114">For connections from clients running Windows 7 operating system, Windows Server 2008 operating system, Windows Server 2008 R2 operating system, Windows Vista operating system, and Microsoft Lync Phone Edition, Lync Server 2013 includes support for (but does not require) certificates signed using the SHA-256 cryptographic hash function.</span></span> <span data-ttu-id="bec31-115">Pour permettre la prise en charge de l’accès externe via SHA-256, le certificat externe est émis par une autorité de certification publique utilisant SHA-256.</span><span class="sxs-lookup"><span data-stu-id="bec31-115">To support external access using SHA-256, the external certificate is issued by a public CA using SHA-256.</span></span>

<span data-ttu-id="bec31-p106">Les tableaux suivants indiquent les certificats requis par rôle serveur pour les pools frontaux et les serveurs Standard Edition Server. Tous ces certificats sont des certificats de serveur web standard à clé privée non exportables</span><span class="sxs-lookup"><span data-stu-id="bec31-p106">The following tables show certificate requirements by server role for Front End pools and Standard Edition servers. All these are standard web server certificates, private key, non-exportable.</span></span>

<span data-ttu-id="bec31-118">Notez que l’utilisation avancée de la clé pour l’authentification des serveurs est automatiquement configurée lorsque vous utilisez l’Assistant Certificat pour demander des certificats.</span><span class="sxs-lookup"><span data-stu-id="bec31-118">Note that server enhanced key usage (EKU) is automatically configured when you use the certificate wizard to request certificates.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="bec31-119">Chaque nom convivial de certificat doit être unique dans le magasin de l’ordinateur.</span><span class="sxs-lookup"><span data-stu-id="bec31-119">Each certificate Friendly Name must be unique in the computer store.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="bec31-120">Si vous avez configuré sipinternal.contoso.com ou sipexternal.contoso.com dans votre DNS, vous devrez les ajouter dans l’autre nom de sujet du certificat.</span><span class="sxs-lookup"><span data-stu-id="bec31-120">If you have configured sipinternal.contoso.com or sipexternal.contoso.com in your DNS, you will need to add them in the certificate’s Subject Alternative Name.</span></span>



</div>

### <a name="certificates-for-standard-edition-server"></a><span data-ttu-id="bec31-121">Certificats pour les serveurs Standard Edition Server</span><span class="sxs-lookup"><span data-stu-id="bec31-121">Certificates for Standard Edition Server</span></span>

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bec31-122">Certificat</span><span class="sxs-lookup"><span data-stu-id="bec31-122">Certificate</span></span></th>
<th><span data-ttu-id="bec31-123">Nom du sujet/nom commun</span><span class="sxs-lookup"><span data-stu-id="bec31-123">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="bec31-124">Autre nom du sujet</span><span class="sxs-lookup"><span data-stu-id="bec31-124">Subject alternative name</span></span></th>
<th><span data-ttu-id="bec31-125">Exemple</span><span class="sxs-lookup"><span data-stu-id="bec31-125">Example</span></span></th>
<th><span data-ttu-id="bec31-126">Comments</span><span class="sxs-lookup"><span data-stu-id="bec31-126">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bec31-127">Par défaut</span><span class="sxs-lookup"><span data-stu-id="bec31-127">Default</span></span></p></td>
<td><p><span data-ttu-id="bec31-128">Nom de domaine complet (FQDN) du pool</span><span class="sxs-lookup"><span data-stu-id="bec31-128">Fully qualified domain name (FQDN) of the pool</span></span></p></td>
<td><p><span data-ttu-id="bec31-129">Nom de domaine complet (FQDN) du pool et nom de domaine complet du serveur</span><span class="sxs-lookup"><span data-stu-id="bec31-129">FQDN of the pool and the FQDN of the server</span></span></p>
<p><span data-ttu-id="bec31-130">Si vous disposez de plusieurs domaines SIP et avez activé la configuration automatique des clients, l’Assistant Certificat détecte et ajoute le nom complet de chaque domaine SIP pris en charge.</span><span class="sxs-lookup"><span data-stu-id="bec31-130">If you have multiple SIP domains and have enabled automatic client configuration, the certificate wizard detects and adds each supported SIP domain FQDNs.</span></span></p>
<p><span data-ttu-id="bec31-131">Si ce pool est le serveur d’ouverture de session automatique pour les clients et si la correspondance DNS (Domain Name System) stricte est requise dans la stratégie de groupe, vous avez également besoin d’entrées pour sip.sipdomain (pour chacun des domaines SIP dont vous disposez).</span><span class="sxs-lookup"><span data-stu-id="bec31-131">If this pool is the auto-logon server for clients and strict Domain Name System (DNS) matching is required in group policy, you also need entries for sip.sipdomain (for each SIP domain you have).</span></span></p></td>
<td><p><span data-ttu-id="bec31-132">SN = SE01. contoso. com ; SAN = SE01. contoso. com</span><span class="sxs-lookup"><span data-stu-id="bec31-132">SN=se01.contoso.com; SAN=se01.contoso.com</span></span></p>
<p><span data-ttu-id="bec31-133">Si ce pool est le serveur d’ouverture de session automatique pour les clients et si la correspondance DNS stricte est requise dans la stratégie de groupe, SAN=sip.contoso.com et SAN=sip.fabrikam.com sont également nécessaires.</span><span class="sxs-lookup"><span data-stu-id="bec31-133">If this pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need SAN=sip.contoso.com; SAN=sip.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="bec31-134">Sur le serveur Standard Edition Server, le nom de domaine complet du serveur est le même que celui du pool.</span><span class="sxs-lookup"><span data-stu-id="bec31-134">On Standard Edition server, the server FQDN is the same as the pool FQDN.</span></span></p>
<p><span data-ttu-id="bec31-135">L’Assistant détecte les domaines SIP indiqués lors de l’installation et les ajoute automatiquement à l’autre nom du sujet.</span><span class="sxs-lookup"><span data-stu-id="bec31-135">The wizard detects any SIP domains you specified during setup and automatically adds them to the subject alternative name.</span></span></p>
<p><span data-ttu-id="bec31-136">Vous pouvez également utiliser ce certificat pour l’authentification de serveur à serveur.</span><span class="sxs-lookup"><span data-stu-id="bec31-136">You can also use this certificate for Server-to-Server Authentication.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bec31-137">Web interne</span><span class="sxs-lookup"><span data-stu-id="bec31-137">Web internal</span></span></p></td>
<td><p><span data-ttu-id="bec31-138">Nom de domaine complet du serveur</span><span class="sxs-lookup"><span data-stu-id="bec31-138">FQDN of the server</span></span></p></td>
<td><p><span data-ttu-id="bec31-139">Pour chaque élément suivant :</span><span class="sxs-lookup"><span data-stu-id="bec31-139">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="bec31-140">Nom de domaine complet web interne (qui est le même que celui du serveur)</span><span class="sxs-lookup"><span data-stu-id="bec31-140">Internal web FQDN (which is the same as the FQDN of the server)</span></span></p></li>
<li><p><span data-ttu-id="bec31-141">URL simples Meet</span><span class="sxs-lookup"><span data-stu-id="bec31-141">Meet simple URLs</span></span></p></li>
<li><p><span data-ttu-id="bec31-142">URL simple Dial-in</span><span class="sxs-lookup"><span data-stu-id="bec31-142">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="bec31-143">URL simple Admin</span><span class="sxs-lookup"><span data-stu-id="bec31-143">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="bec31-144">Ou, une entrée de caractère générique pour les URL simples</span><span class="sxs-lookup"><span data-stu-id="bec31-144">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="bec31-145">SN = SE01. contoso. com ; SAN = SE01. contoso. com ; SAN = réunion. contoso. com ; SAN = réunion. fabrikam. com ; SAN = Dialin. contoso. com ; SAN = admin. contoso. com</span><span class="sxs-lookup"><span data-stu-id="bec31-145">SN=se01.contoso.com; SAN=se01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</span></span></p>
<p><span data-ttu-id="bec31-146">Utilisation d’un certificat de caractère générique :</span><span class="sxs-lookup"><span data-stu-id="bec31-146">Using a wildcard certificate:</span></span></p>
<p><span data-ttu-id="bec31-147">SN = SE01. contoso. com ; SAN = SE01. contoso. com ; SAN = \*. contoso. com</span><span class="sxs-lookup"><span data-stu-id="bec31-147">SN=se01.contoso.com; SAN=se01.contoso.com; SAN=\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="bec31-148">Vous ne pouvez pas remplacer le nom de domaine complet Web interne dans le générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="bec31-148">You cannot override the Internal web FQDN in Topology Builder.</span></span></p>
<p><span data-ttu-id="bec31-149">Si vous disposez de plusieurs URL simples Meet, vous devez les inclure toutes en tant qu’autres noms du sujet.</span><span class="sxs-lookup"><span data-stu-id="bec31-149">If you have multiple Meet simple URLs, you must include all of them as subject alternative names.</span></span></p>
<p><span data-ttu-id="bec31-150">Les entrées de caractères génériques sont prises en charge pour les entrées d’URL simples.</span><span class="sxs-lookup"><span data-stu-id="bec31-150">Wildcard entries are supported for the simple URL entries.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bec31-151">Web externe</span><span class="sxs-lookup"><span data-stu-id="bec31-151">Web external</span></span></p></td>
<td><p><span data-ttu-id="bec31-152">Nom de domaine complet du serveur</span><span class="sxs-lookup"><span data-stu-id="bec31-152">FQDN of the server</span></span></p></td>
<td><p><span data-ttu-id="bec31-153">Pour chaque élément suivant :</span><span class="sxs-lookup"><span data-stu-id="bec31-153">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="bec31-154">Nom de domaine complet web externe</span><span class="sxs-lookup"><span data-stu-id="bec31-154">External web FQDN</span></span></p></li>
<li><p><span data-ttu-id="bec31-155">URL simple Dial-in</span><span class="sxs-lookup"><span data-stu-id="bec31-155">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="bec31-156">Répondre aux URL simples par domaine SIP</span><span class="sxs-lookup"><span data-stu-id="bec31-156">Meet simple URLs per SIP domain</span></span></p></li>
<li><p><span data-ttu-id="bec31-157">Ou, une entrée de caractère générique pour les URL simples</span><span class="sxs-lookup"><span data-stu-id="bec31-157">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="bec31-158">SN = SE01. contoso. com ; SAN = webcon01. contoso. com ; SAN = réunion. contoso. com ; SAN = réunion. fabrikam. com ; SAN = Dialin. contoso. com</span><span class="sxs-lookup"><span data-stu-id="bec31-158">SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</span></span></p>
<p><span data-ttu-id="bec31-159">Utilisation d’un certificat de caractère générique :</span><span class="sxs-lookup"><span data-stu-id="bec31-159">Using a wildcard certificate:</span></span></p>
<p><span data-ttu-id="bec31-160">SN = SE01. contoso. com ; SAN = webcon01. contoso. com ; SAN = \*. contoso. com</span><span class="sxs-lookup"><span data-stu-id="bec31-160">SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="bec31-161">Si vous disposez de plusieurs URL simples Meet, vous devez les inclure toutes en tant qu’autres noms du sujet.</span><span class="sxs-lookup"><span data-stu-id="bec31-161">If you have multiple Meet simple URLs, you must include all of them as subject alternative names.</span></span></p>
<p><span data-ttu-id="bec31-162">Les entrées de caractères génériques sont prises en charge pour les entrées d’URL simples.</span><span class="sxs-lookup"><span data-stu-id="bec31-162">Wildcard entries are supported for the simple URL entries.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-front-end-server-in-a-front-end-pool"></a><span data-ttu-id="bec31-163">Certificats pour les serveurs frontaux dans un pool frontal</span><span class="sxs-lookup"><span data-stu-id="bec31-163">Certificates for Front End Server in a Front End Pool</span></span>

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bec31-164">Certificat</span><span class="sxs-lookup"><span data-stu-id="bec31-164">Certificate</span></span></th>
<th><span data-ttu-id="bec31-165">Nom du sujet/nom commun</span><span class="sxs-lookup"><span data-stu-id="bec31-165">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="bec31-166">Autre nom du sujet</span><span class="sxs-lookup"><span data-stu-id="bec31-166">Subject alternative name</span></span></th>
<th><span data-ttu-id="bec31-167">Exemple</span><span class="sxs-lookup"><span data-stu-id="bec31-167">Example</span></span></th>
<th><span data-ttu-id="bec31-168">Comments</span><span class="sxs-lookup"><span data-stu-id="bec31-168">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bec31-169">Par défaut</span><span class="sxs-lookup"><span data-stu-id="bec31-169">Default</span></span></p></td>
<td><p><span data-ttu-id="bec31-170">Nom de domaine complet du pool</span><span class="sxs-lookup"><span data-stu-id="bec31-170">FQDN of the pool</span></span></p></td>
<td><p><span data-ttu-id="bec31-171">Nom de domaine complet du pool et nom de domaine complet du serveur.</span><span class="sxs-lookup"><span data-stu-id="bec31-171">FQDN of the pool and FQDN of the server.</span></span></p>
<p><span data-ttu-id="bec31-172">Si vous disposez de plusieurs domaines SIP et avez activé la configuration automatique des clients, l’Assistant Certificat détecte et ajoute le nom complet de chaque domaine SIP pris en charge.</span><span class="sxs-lookup"><span data-stu-id="bec31-172">If you have multiple SIP domains and have enabled automatic client configuration, the certificate wizard detects and adds each supported SIP domain FQDNs.</span></span></p>
<p><span data-ttu-id="bec31-173">Si ce pool est le serveur d’ouverture de session automatique pour les clients et si la correspondance DNS stricte est requise dans la stratégie de groupe, vous avez également besoin d’entrées pour sip.sipdomain (pour chacun des domaines SIP dont vous disposez).</span><span class="sxs-lookup"><span data-stu-id="bec31-173">If this pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need entries for sip.sipdomain (for each SIP domain you have).</span></span></p></td>
<td><p><span data-ttu-id="bec31-174">SN = EEpool. contoso. com ; SAN = EEpool. contoso. com ; SAN = ee01. contoso. com</span><span class="sxs-lookup"><span data-stu-id="bec31-174">SN=eepool.contoso.com; SAN=eepool.contoso.com; SAN=ee01.contoso.com</span></span></p>
<p><span data-ttu-id="bec31-175">Si ce pool est le serveur d’ouverture de session automatique pour les clients et si la correspondance DNS stricte est requise dans la stratégie de groupe, SAN=sip.contoso.com et SAN=sip.fabrikam.com sont également nécessaires.</span><span class="sxs-lookup"><span data-stu-id="bec31-175">If this pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need SAN=sip.contoso.com; SAN=sip.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="bec31-176">L’Assistant détecte les domaines SIP indiqués lors de l’installation et les ajoute automatiquement à l’autre nom du sujet.</span><span class="sxs-lookup"><span data-stu-id="bec31-176">The wizard detects any SIP domains you specified during setup and automatically adds them to the subject alternative name.</span></span></p>
<p><span data-ttu-id="bec31-177">Vous pouvez également utiliser ce certificat pour l’authentification de serveur à serveur.</span><span class="sxs-lookup"><span data-stu-id="bec31-177">You can also use this certificate for Server-to-Server Authentication.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bec31-178">Web interne</span><span class="sxs-lookup"><span data-stu-id="bec31-178">Web Internal</span></span></p></td>
<td><p><span data-ttu-id="bec31-179">Nom de domaine complet du pool</span><span class="sxs-lookup"><span data-stu-id="bec31-179">FQDN of the pool</span></span></p></td>
<td><p><span data-ttu-id="bec31-180">Pour chaque élément suivant :</span><span class="sxs-lookup"><span data-stu-id="bec31-180">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="bec31-181">Nom de domaine complet Web interne (qui n’est pas le même que le nom de domaine complet du serveur)</span><span class="sxs-lookup"><span data-stu-id="bec31-181">Internal web FQDN (which is NOT the same as the FQDN of the server)</span></span></p></li>
<li><p><span data-ttu-id="bec31-182">Nom de domaine complet du serveur</span><span class="sxs-lookup"><span data-stu-id="bec31-182">Server FQDN</span></span></p></li>
<li><p><span data-ttu-id="bec31-183">Nom de domaine complet du pool Lync</span><span class="sxs-lookup"><span data-stu-id="bec31-183">Lync pool FQDN</span></span></p></li>
<li><p><span data-ttu-id="bec31-184">URL simples Meet</span><span class="sxs-lookup"><span data-stu-id="bec31-184">Meet simple URLs</span></span></p></li>
<li><p><span data-ttu-id="bec31-185">URL simple Dial-in</span><span class="sxs-lookup"><span data-stu-id="bec31-185">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="bec31-186">URL simple Admin</span><span class="sxs-lookup"><span data-stu-id="bec31-186">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="bec31-187">Ou, une entrée de caractère générique pour les URL simples</span><span class="sxs-lookup"><span data-stu-id="bec31-187">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="bec31-188">SN = ee01. contoso. com ; SAN = ee01. contoso. com ; SAN = réunion. contoso. com ; SAN = réunion. fabrikam. com ; SAN = Dialin. contoso. com ; SAN = admin. contoso. com</span><span class="sxs-lookup"><span data-stu-id="bec31-188">SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</span></span></p>
<p><span data-ttu-id="bec31-189">Utilisation d’un certificat de caractère générique :</span><span class="sxs-lookup"><span data-stu-id="bec31-189">Using a wildcard certificate:</span></span></p>
<p><span data-ttu-id="bec31-190">SN = ee01. contoso. com ; SAN = ee01. contoso. com ; SAN = \*. contoso. com</span><span class="sxs-lookup"><span data-stu-id="bec31-190">SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN=\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="bec31-191">Si vous disposez de plusieurs URL simples Meet, vous devez les inclure toutes en tant qu’autres noms du sujet.</span><span class="sxs-lookup"><span data-stu-id="bec31-191">If you have multiple Meet simple URLs, you must include all of them as subject alternative names.</span></span></p>
<p><span data-ttu-id="bec31-192">Les entrées de caractères génériques sont prises en charge pour les entrées d’URL simples.</span><span class="sxs-lookup"><span data-stu-id="bec31-192">Wildcard entries are supported for the simple URL entries.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bec31-193">Web externe</span><span class="sxs-lookup"><span data-stu-id="bec31-193">Web external</span></span></p></td>
<td><p><span data-ttu-id="bec31-194">Nom de domaine complet du pool</span><span class="sxs-lookup"><span data-stu-id="bec31-194">FQDN of the pool</span></span></p></td>
<td><p><span data-ttu-id="bec31-195">Pour chaque élément suivant :</span><span class="sxs-lookup"><span data-stu-id="bec31-195">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="bec31-196">Nom de domaine complet web externe</span><span class="sxs-lookup"><span data-stu-id="bec31-196">External web FQDN</span></span></p></li>
<li><p><span data-ttu-id="bec31-197">URL simple Dial-in</span><span class="sxs-lookup"><span data-stu-id="bec31-197">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="bec31-198">URL simple Admin</span><span class="sxs-lookup"><span data-stu-id="bec31-198">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="bec31-199">Ou, une entrée de caractère générique pour les URL simples</span><span class="sxs-lookup"><span data-stu-id="bec31-199">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="bec31-200">SN = ee01. contoso. com ; SAN = webcon01. contoso. com ; SAN = réunion. contoso. com ; SAN = réunion. fabrikam. com ; SAN = Dialin. contoso. com</span><span class="sxs-lookup"><span data-stu-id="bec31-200">SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</span></span></p>
<p><span data-ttu-id="bec31-201">Utilisation d’un certificat de caractère générique :</span><span class="sxs-lookup"><span data-stu-id="bec31-201">Using a wildcard certificate:</span></span></p>
<p><span data-ttu-id="bec31-202">SN = ee01. contoso. com ; SAN = webcon01. contoso. com ; SAN = \*. contoso. com</span><span class="sxs-lookup"><span data-stu-id="bec31-202">SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="bec31-203">Si vous disposez de plusieurs URL simples Meet, vous devez les inclure toutes en tant qu’autres noms du sujet.</span><span class="sxs-lookup"><span data-stu-id="bec31-203">If you have multiple Meet simple URLs, you must include all of them as subject alternative names.</span></span></p>
<p><span data-ttu-id="bec31-204">Les entrées de caractères génériques sont prises en charge pour les entrées d’URL simples.</span><span class="sxs-lookup"><span data-stu-id="bec31-204">Wildcard entries are supported for the simple URL entries.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-director"></a><span data-ttu-id="bec31-205">Certificats pour le directeur</span><span class="sxs-lookup"><span data-stu-id="bec31-205">Certificates for Director</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bec31-206">Certificat</span><span class="sxs-lookup"><span data-stu-id="bec31-206">Certificate</span></span></th>
<th><span data-ttu-id="bec31-207">Nom du sujet/nom commun</span><span class="sxs-lookup"><span data-stu-id="bec31-207">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="bec31-208">Autre nom du sujet</span><span class="sxs-lookup"><span data-stu-id="bec31-208">Subject alternative name</span></span></th>
<th><span data-ttu-id="bec31-209">Exemple</span><span class="sxs-lookup"><span data-stu-id="bec31-209">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bec31-210">Par défaut</span><span class="sxs-lookup"><span data-stu-id="bec31-210">Default</span></span></p></td>
<td><p><span data-ttu-id="bec31-211">Nom de domaine complet du pool directeur</span><span class="sxs-lookup"><span data-stu-id="bec31-211">FQDN of the Director pool</span></span></p></td>
<td><p><span data-ttu-id="bec31-212">Nom de domaine complet du directeur, nom de domaine complet du pool directeur</span><span class="sxs-lookup"><span data-stu-id="bec31-212">FQDN of the Director, FQDN of the Director pool</span></span></p>
<p><span data-ttu-id="bec31-213">Si ce pool est le serveur d’ouverture de session automatique pour les clients et si la correspondance DNS stricte est requise dans la stratégie de groupe, vous avez également besoin d’entrées pour sip.sipdomain (pour chacun des domaines SIP dont vous disposez).</span><span class="sxs-lookup"><span data-stu-id="bec31-213">If this pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need entries for sip.sipdomain (for each SIP domain you have).</span></span></p></td>
<td><p><span data-ttu-id="bec31-214">SN = dir-pool.contoso.com ; SAN = dir-pool.contoso.com ; SAN = DIR01. contoso. com</span><span class="sxs-lookup"><span data-stu-id="bec31-214">SN=dir-pool.contoso.com; SAN=dir-pool.contoso.com; SAN=dir01.contoso.com</span></span></p>
<p><span data-ttu-id="bec31-215">Si ce pool directeur est le serveur d’ouverture de session automatique pour les clients et si la correspondance DNS stricte est requise dans la stratégie de groupe, SAN=sip.contoso.com et SAN=sip.fabrikam.com sont également nécessaires.</span><span class="sxs-lookup"><span data-stu-id="bec31-215">If this Director pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need SAN=sip.contoso.com; SAN=sip.fabrikam.com</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bec31-216">Web interne</span><span class="sxs-lookup"><span data-stu-id="bec31-216">Web Internal</span></span></p></td>
<td><p><span data-ttu-id="bec31-217">Nom de domaine complet du serveur</span><span class="sxs-lookup"><span data-stu-id="bec31-217">FQDN of the server</span></span></p></td>
<td><p><span data-ttu-id="bec31-218">Pour chaque élément suivant :</span><span class="sxs-lookup"><span data-stu-id="bec31-218">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="bec31-219">Nom de domaine complet web interne (qui est le même que celui du serveur)</span><span class="sxs-lookup"><span data-stu-id="bec31-219">Internal web FQDN (which is the same as the FQDN of the server)</span></span></p></li>
<li><p><span data-ttu-id="bec31-220">Nom de domaine complet du serveur</span><span class="sxs-lookup"><span data-stu-id="bec31-220">Server FQDN</span></span></p></li>
<li><p><span data-ttu-id="bec31-221">Nom de domaine complet du pool Lync</span><span class="sxs-lookup"><span data-stu-id="bec31-221">Lync pool FQDN</span></span></p></li>
<li><p><span data-ttu-id="bec31-222">URL simples Meet</span><span class="sxs-lookup"><span data-stu-id="bec31-222">Meet simple URLs</span></span></p></li>
<li><p><span data-ttu-id="bec31-223">URL simple Dial-in</span><span class="sxs-lookup"><span data-stu-id="bec31-223">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="bec31-224">URL simple Admin</span><span class="sxs-lookup"><span data-stu-id="bec31-224">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="bec31-225">Ou, une entrée de caractère générique pour les URL simples</span><span class="sxs-lookup"><span data-stu-id="bec31-225">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="bec31-226">SN = DIR01. contoso. com ; SAN = DIR01. contoso. com ; SAN = réunion. contoso. com ; SAN = réunion. fabrikam. com ; SAN = Dialin. contoso. com ; SAN = admin. contoso. com</span><span class="sxs-lookup"><span data-stu-id="bec31-226">SN=dir01.contoso.com; SAN=dir01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</span></span></p>
<p><span data-ttu-id="bec31-227">SN = DIR01. contoso. com ; SAN = DIR01. contoso. com SAN = \*. contoso. com</span><span class="sxs-lookup"><span data-stu-id="bec31-227">SN=dir01.contoso.com; SAN=dir01.contoso.com SAN=\*.contoso.com</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bec31-228">Web externe</span><span class="sxs-lookup"><span data-stu-id="bec31-228">Web external</span></span></p></td>
<td><p><span data-ttu-id="bec31-229">Nom de domaine complet du serveur</span><span class="sxs-lookup"><span data-stu-id="bec31-229">FQDN of the server</span></span></p></td>
<td><p><span data-ttu-id="bec31-230">Pour chaque élément suivant :</span><span class="sxs-lookup"><span data-stu-id="bec31-230">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="bec31-231">Nom de domaine complet web externe</span><span class="sxs-lookup"><span data-stu-id="bec31-231">External web FQDN</span></span></p></li>
<li><p><span data-ttu-id="bec31-232">URL simple Dial-in</span><span class="sxs-lookup"><span data-stu-id="bec31-232">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="bec31-233">URL simple Admin</span><span class="sxs-lookup"><span data-stu-id="bec31-233">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="bec31-234">Ou, une entrée de caractère générique pour les URL simples</span><span class="sxs-lookup"><span data-stu-id="bec31-234">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="bec31-235">Le nom de domaine complet du directeur de site Web externe doit être différent du pool frontal ou du serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="bec31-235">The Director external web FQDN must be different from the Front End pool or Front End Server.</span></span></p>
<p><span data-ttu-id="bec31-236">SN = DIR01. contoso. com ; SAN = directorwebcon01. contoso. com SAN = réunion. contoso. com ; SAN = réunion. fabrikam. com ; SAN = Dialin. contoso. com</span><span class="sxs-lookup"><span data-stu-id="bec31-236">SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</span></span></p>
<p><span data-ttu-id="bec31-237">SN = DIR01. contoso. com ; SAN = directorwebcon01. contoso. com SAN = \*. contoso. com</span><span class="sxs-lookup"><span data-stu-id="bec31-237">SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=\*.contoso.com</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="bec31-p107">Si vous disposez d’un pool de serveurs de médiation autonomes, chaque serveur dans le pool nécessite les certificats répertoriés dans le tableau suivant. (Si vous colocalisez les serveurs de médiation avec les serveurs frontaux, les certificats répertoriés dans le tableau « Certificats pour les serveurs frontaux dans un pool frontal » plus haut dans cette rubrique suffisent).</span><span class="sxs-lookup"><span data-stu-id="bec31-p107">If you have a stand-alone Mediation Server pool, the Mediation Servers in it each need the certificates listed in the following table. If you collocate Mediation Server with the Front End Servers, the certificates listed in the “Certificates for Front End Server in Front End Pool” table earlier in this topic are sufficient.</span></span>

### <a name="certificates-for-stand-alone-mediation-server"></a><span data-ttu-id="bec31-240">Certificats pour les serveurs de médiation autonomes</span><span class="sxs-lookup"><span data-stu-id="bec31-240">Certificates for Stand-alone Mediation Server</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bec31-241">Certificat</span><span class="sxs-lookup"><span data-stu-id="bec31-241">Certificate</span></span></th>
<th><span data-ttu-id="bec31-242">Nom du sujet/nom commun</span><span class="sxs-lookup"><span data-stu-id="bec31-242">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="bec31-243">Autre nom du sujet</span><span class="sxs-lookup"><span data-stu-id="bec31-243">Subject alternative name</span></span></th>
<th><span data-ttu-id="bec31-244">Exemple</span><span class="sxs-lookup"><span data-stu-id="bec31-244">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bec31-245">Par défaut</span><span class="sxs-lookup"><span data-stu-id="bec31-245">Default</span></span></p></td>
<td><p><span data-ttu-id="bec31-246">Nom de domaine complet du pool</span><span class="sxs-lookup"><span data-stu-id="bec31-246">FQDN of the pool</span></span></p></td>
<td><p><span data-ttu-id="bec31-247">Nom de domaine complet du pool</span><span class="sxs-lookup"><span data-stu-id="bec31-247">FQDN of the pool</span></span></p>
<p><span data-ttu-id="bec31-248">Nom de domaine complet du serveur membre du pool</span><span class="sxs-lookup"><span data-stu-id="bec31-248">FQDN of pool member server</span></span></p></td>
<td><p><span data-ttu-id="bec31-249">SN = medsvr-pool.contoso.net ; SAN = medsvr-pool.contoso.net ; SAN = medsvr01. contoso. net</span><span class="sxs-lookup"><span data-stu-id="bec31-249">SN=medsvr-pool.contoso.net; SAN=medsvr-pool.contoso.net; SAN=medsvr01.contoso.net</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-survivable-branch-appliance"></a><span data-ttu-id="bec31-250">Certificats pour les Survivable Branch Appliances</span><span class="sxs-lookup"><span data-stu-id="bec31-250">Certificates for Survivable Branch Appliance</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bec31-251">Certificat</span><span class="sxs-lookup"><span data-stu-id="bec31-251">Certificate</span></span></th>
<th><span data-ttu-id="bec31-252">Nom du sujet/nom commun</span><span class="sxs-lookup"><span data-stu-id="bec31-252">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="bec31-253">Autre nom du sujet</span><span class="sxs-lookup"><span data-stu-id="bec31-253">Subject alternative name</span></span></th>
<th><span data-ttu-id="bec31-254">Exemple</span><span class="sxs-lookup"><span data-stu-id="bec31-254">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bec31-255">Par défaut</span><span class="sxs-lookup"><span data-stu-id="bec31-255">Default</span></span></p></td>
<td><p><span data-ttu-id="bec31-256">Nom de domaine complet de l’appliance</span><span class="sxs-lookup"><span data-stu-id="bec31-256">FQDN of the appliance</span></span></p></td>
<td><p><span data-ttu-id="bec31-257">SIP. &lt; sipdomain &gt; (nécessite une entrée par domaine SIP)</span><span class="sxs-lookup"><span data-stu-id="bec31-257">SIP.&lt;sipdomain&gt; (need one entry per SIP domain)</span></span></p></td>
<td><p><span data-ttu-id="bec31-258">SN = sba01. contoso. net ; SAN = SIP. contoso. com ; SAN = SIP. fabrikam. com</span><span class="sxs-lookup"><span data-stu-id="bec31-258">SN=sba01.contoso.net; SAN=sip.contoso.com; SAN=sip.fabrikam.com</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="bec31-259">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="bec31-259">See Also</span></span>


[<span data-ttu-id="bec31-260">Prise en charge de certificat générique dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bec31-260">Wildcard certificate support in Lync Server 2013</span></span>](lync-server-2013-wildcard-certificate-support.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

