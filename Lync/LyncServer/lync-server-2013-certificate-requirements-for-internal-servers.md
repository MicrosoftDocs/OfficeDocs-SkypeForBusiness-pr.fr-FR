---
title: 'Lync Server 2013 : conditions requises pour les certificats pour les serveurs internes'
description: 'Lync Server 2013 : conditions requises pour les certificats pour les serveurs internes.'
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
ms.openlocfilehash: dc1a627dd762c849b848087a96e00e19d320ef01
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575210"
---
# <a name="certificate-requirements-for-internal-servers-in-lync-server-2013"></a><span data-ttu-id="d7083-103">Exigences de certificat pour les serveurs internes dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d7083-103">Certificate requirements for internal servers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d7083-104">_**Dernière modification de la rubrique :** 2017-02-17_</span><span class="sxs-lookup"><span data-stu-id="d7083-104">_**Topic Last Modified:** 2017-02-17_</span></span>

<span data-ttu-id="d7083-105">Les serveurs internes qui exécutent Lync Server et qui nécessitent des certificats incluent le serveur Standard Edition, le serveur frontal Enterprise Edition, le serveur de médiation et le directeur.</span><span class="sxs-lookup"><span data-stu-id="d7083-105">Internal servers that are running Lync Server and that require certificates include Standard Edition server, Enterprise Edition Front End Server, Mediation Server, and Director.</span></span> <span data-ttu-id="d7083-106">Le tableau suivant indique les certificats requis pour ces serveurs.</span><span class="sxs-lookup"><span data-stu-id="d7083-106">The following table shows the certificate requirements for these servers.</span></span> <span data-ttu-id="d7083-107">Vous pouvez utiliser l’Assistant Certificat Lync Server pour demander ces certificats.</span><span class="sxs-lookup"><span data-stu-id="d7083-107">You can use the Lync Server certificate wizard to request these certificates.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="d7083-108">Les certificats génériques sont pris en charge pour les autres noms de sujet associés aux URL simples sur le pool frontal, le serveur frontal ou le directeur.</span><span class="sxs-lookup"><span data-stu-id="d7083-108">Wildcard certificates are supported for the subject alternative names associated with the simple URLs on the Front End pool, Front End Server, or Director.</span></span> <span data-ttu-id="d7083-109">Pour plus d’informations sur la prise en charge des certificats génériques, consultez la rubrique <A href="lync-server-2013-wildcard-certificate-support.md">générique Certificate support in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="d7083-109">For details about wildcard certificate support, see <A href="lync-server-2013-wildcard-certificate-support.md">Wildcard certificate support in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="d7083-110">Bien qu’il soit recommandé d’utiliser une autorité de certification d’entreprise interne pour les serveurs internes, vous pouvez également utiliser une autorité de certification publique.</span><span class="sxs-lookup"><span data-stu-id="d7083-110">Although an internal enterprise certification authority (CA) is recommended for internal servers, you can also use a public CA.</span></span> <span data-ttu-id="d7083-111">Pour obtenir la liste des autorités de certification publiques qui fournissent des certificats conformes aux exigences spécifiques pour les certificats de communications unifiées et qui ont conclu un partenariat avec Microsoft afin de s’assurer qu’ils fonctionnent avec l’Assistant Certificat Lync Server, consultez la base de connaissances Microsoft 929395, « partenaires de certificat de communications unifiées pour Exchange Server et Communications Server », à l’adresse [https://go.microsoft.com/fwlink/p/?linkId=202834](https://go.microsoft.com/fwlink/p/?linkid=202834) .</span><span class="sxs-lookup"><span data-stu-id="d7083-111">For a list of public CAs that provide certificates that comply with specific requirements for unified communications (UC) certificates and have partnered with Microsoft to ensure they work with the Lync Server Certificate Wizard, see article Microsoft Knowledge Base 929395, "Unified Communications Certificate Partners for Exchange Server and for Communications Server," at [https://go.microsoft.com/fwlink/p/?linkId=202834](https://go.microsoft.com/fwlink/p/?linkid=202834).</span></span>

<span data-ttu-id="d7083-112">La communication avec d’autres applications et serveurs, comme Exchange 2013, nécessite un certificat pris en charge par les autres applications et produits.</span><span class="sxs-lookup"><span data-stu-id="d7083-112">Communication with other applications and servers, such as Exchange 2013, requires a certificate that is supported by the other applications and products.</span></span> <span data-ttu-id="d7083-113">Pour la version 2013, Lync Server 2013 et d’autres produits serveur Microsoft, y compris Exchange 2013 et SharePoint Server, prennent en charge le protocole d’autorisation d’ouverture (OAuth) pour l’authentification et l’autorisation de serveur à serveur.</span><span class="sxs-lookup"><span data-stu-id="d7083-113">For the 2013 release, Lync Server 2013 and other Microsoft server products, including Exchange 2013 and SharePoint Server, support the Open Authorization (OAuth) protocol for server-to-server authentication and authorization.</span></span> <span data-ttu-id="d7083-114">Pour plus d’informations, reportez-vous à la rubrique [Managing Server-to-Server Authentication (OAuth) and Partner applications in Lync server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) dans la documentation de déploiement ou la documentation des opérations.</span><span class="sxs-lookup"><span data-stu-id="d7083-114">For details, see [Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) in the Deployment documentation or the Operations documentation.</span></span>

<span data-ttu-id="d7083-115">Pour les connexions à partir de clients exécutant le système d’exploitation Windows 7, le système d’exploitation Windows Server 2008, le système d’exploitation Windows Server 2008 R2, le système d’exploitation Windows Vista et Microsoft Lync Phone Edition, Lync Server 2013 inclut la prise en charge des certificats signés à l’aide de la fonction de hachage cryptographique SHA-256.</span><span class="sxs-lookup"><span data-stu-id="d7083-115">For connections from clients running Windows 7 operating system, Windows Server 2008 operating system, Windows Server 2008 R2 operating system, Windows Vista operating system, and Microsoft Lync Phone Edition, Lync Server 2013 includes support for (but does not require) certificates signed using the SHA-256 cryptographic hash function.</span></span> <span data-ttu-id="d7083-116">Pour permettre la prise en charge de l’accès externe via SHA-256, le certificat externe est émis par une autorité de certification publique utilisant SHA-256.</span><span class="sxs-lookup"><span data-stu-id="d7083-116">To support external access using SHA-256, the external certificate is issued by a public CA using SHA-256.</span></span>

<span data-ttu-id="d7083-p106">Les tableaux suivants indiquent les certificats requis par rôle serveur pour les pools frontaux et les serveurs Standard Edition Server. Tous ces certificats sont des certificats de serveur web standard à clé privée non exportables</span><span class="sxs-lookup"><span data-stu-id="d7083-p106">The following tables show certificate requirements by server role for Front End pools and Standard Edition servers. All these are standard web server certificates, private key, non-exportable.</span></span>

<span data-ttu-id="d7083-119">Notez que l’utilisation avancée de la clé pour l’authentification des serveurs est automatiquement configurée lorsque vous utilisez l’Assistant Certificat pour demander des certificats.</span><span class="sxs-lookup"><span data-stu-id="d7083-119">Note that server enhanced key usage (EKU) is automatically configured when you use the certificate wizard to request certificates.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d7083-120">Chaque nom convivial de certificat doit être unique dans le magasin de l’ordinateur.</span><span class="sxs-lookup"><span data-stu-id="d7083-120">Each certificate Friendly Name must be unique in the computer store.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="d7083-121">Si vous avez configuré sipinternal.contoso.com ou sipexternal.contoso.com dans votre DNS, vous devrez les ajouter dans l’autre nom de sujet du certificat.</span><span class="sxs-lookup"><span data-stu-id="d7083-121">If you have configured sipinternal.contoso.com or sipexternal.contoso.com in your DNS, you will need to add them in the certificate’s Subject Alternative Name.</span></span>



</div>

### <a name="certificates-for-standard-edition-server"></a><span data-ttu-id="d7083-122">Certificats pour les serveurs Standard Edition Server</span><span class="sxs-lookup"><span data-stu-id="d7083-122">Certificates for Standard Edition Server</span></span>

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
<th><span data-ttu-id="d7083-123">Certificat</span><span class="sxs-lookup"><span data-stu-id="d7083-123">Certificate</span></span></th>
<th><span data-ttu-id="d7083-124">Nom du sujet/nom commun</span><span class="sxs-lookup"><span data-stu-id="d7083-124">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="d7083-125">Autre nom du sujet</span><span class="sxs-lookup"><span data-stu-id="d7083-125">Subject alternative name</span></span></th>
<th><span data-ttu-id="d7083-126">Exemple</span><span class="sxs-lookup"><span data-stu-id="d7083-126">Example</span></span></th>
<th><span data-ttu-id="d7083-127">Comments</span><span class="sxs-lookup"><span data-stu-id="d7083-127">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d7083-128">Par défaut</span><span class="sxs-lookup"><span data-stu-id="d7083-128">Default</span></span></p></td>
<td><p><span data-ttu-id="d7083-129">Nom de domaine complet (FQDN) du pool</span><span class="sxs-lookup"><span data-stu-id="d7083-129">Fully qualified domain name (FQDN) of the pool</span></span></p></td>
<td><p><span data-ttu-id="d7083-130">Nom de domaine complet (FQDN) du pool et nom de domaine complet du serveur</span><span class="sxs-lookup"><span data-stu-id="d7083-130">FQDN of the pool and the FQDN of the server</span></span></p>
<p><span data-ttu-id="d7083-131">Si vous disposez de plusieurs domaines SIP et avez activé la configuration automatique des clients, l’Assistant Certificat détecte et ajoute le nom complet de chaque domaine SIP pris en charge.</span><span class="sxs-lookup"><span data-stu-id="d7083-131">If you have multiple SIP domains and have enabled automatic client configuration, the certificate wizard detects and adds each supported SIP domain FQDNs.</span></span></p>
<p><span data-ttu-id="d7083-132">Si ce pool est le serveur d’ouverture de session automatique pour les clients et si la correspondance DNS (Domain Name System) stricte est requise dans la stratégie de groupe, vous avez également besoin d’entrées pour sip.sipdomain (pour chacun des domaines SIP dont vous disposez).</span><span class="sxs-lookup"><span data-stu-id="d7083-132">If this pool is the auto-logon server for clients and strict Domain Name System (DNS) matching is required in group policy, you also need entries for sip.sipdomain (for each SIP domain you have).</span></span></p></td>
<td><p><span data-ttu-id="d7083-133">SN = SE01. contoso. com ; SAN = SE01. contoso. com</span><span class="sxs-lookup"><span data-stu-id="d7083-133">SN=se01.contoso.com; SAN=se01.contoso.com</span></span></p>
<p><span data-ttu-id="d7083-134">Si ce pool est le serveur d’ouverture de session automatique pour les clients et si la correspondance DNS stricte est requise dans la stratégie de groupe, SAN=sip.contoso.com et SAN=sip.fabrikam.com sont également nécessaires.</span><span class="sxs-lookup"><span data-stu-id="d7083-134">If this pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need SAN=sip.contoso.com; SAN=sip.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="d7083-135">Sur le serveur Standard Edition Server, le nom de domaine complet du serveur est le même que celui du pool.</span><span class="sxs-lookup"><span data-stu-id="d7083-135">On Standard Edition server, the server FQDN is the same as the pool FQDN.</span></span></p>
<p><span data-ttu-id="d7083-136">L’Assistant détecte les domaines SIP indiqués lors de l’installation et les ajoute automatiquement à l’autre nom du sujet.</span><span class="sxs-lookup"><span data-stu-id="d7083-136">The wizard detects any SIP domains you specified during setup and automatically adds them to the subject alternative name.</span></span></p>
<p><span data-ttu-id="d7083-137">Vous pouvez également utiliser ce certificat pour l’authentification de serveur à serveur.</span><span class="sxs-lookup"><span data-stu-id="d7083-137">You can also use this certificate for Server-to-Server Authentication.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7083-138">Web interne</span><span class="sxs-lookup"><span data-stu-id="d7083-138">Web internal</span></span></p></td>
<td><p><span data-ttu-id="d7083-139">Nom de domaine complet du serveur</span><span class="sxs-lookup"><span data-stu-id="d7083-139">FQDN of the server</span></span></p></td>
<td><p><span data-ttu-id="d7083-140">Pour chaque élément suivant :</span><span class="sxs-lookup"><span data-stu-id="d7083-140">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="d7083-141">Nom de domaine complet web interne (qui est le même que celui du serveur)</span><span class="sxs-lookup"><span data-stu-id="d7083-141">Internal web FQDN (which is the same as the FQDN of the server)</span></span></p></li>
<li><p><span data-ttu-id="d7083-142">URL simples Meet</span><span class="sxs-lookup"><span data-stu-id="d7083-142">Meet simple URLs</span></span></p></li>
<li><p><span data-ttu-id="d7083-143">URL simple Dial-in</span><span class="sxs-lookup"><span data-stu-id="d7083-143">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="d7083-144">URL simple Admin</span><span class="sxs-lookup"><span data-stu-id="d7083-144">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="d7083-145">Ou, une entrée de caractère générique pour les URL simples</span><span class="sxs-lookup"><span data-stu-id="d7083-145">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="d7083-146">SN = SE01. contoso. com ; SAN = SE01. contoso. com ; SAN = réunion. contoso. com ; SAN = réunion. fabrikam. com ; SAN = Dialin. contoso. com ; SAN = admin. contoso. com</span><span class="sxs-lookup"><span data-stu-id="d7083-146">SN=se01.contoso.com; SAN=se01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</span></span></p>
<p><span data-ttu-id="d7083-147">Utilisation d’un certificat de caractère générique :</span><span class="sxs-lookup"><span data-stu-id="d7083-147">Using a wildcard certificate:</span></span></p>
<p><span data-ttu-id="d7083-148">SN = SE01. contoso. com ; SAN = SE01. contoso. com ; SAN = \*. contoso. com</span><span class="sxs-lookup"><span data-stu-id="d7083-148">SN=se01.contoso.com; SAN=se01.contoso.com; SAN=\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="d7083-149">Vous ne pouvez pas remplacer le nom de domaine complet Web interne dans le générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="d7083-149">You cannot override the Internal web FQDN in Topology Builder.</span></span></p>
<p><span data-ttu-id="d7083-150">Si vous disposez de plusieurs URL simples Meet, vous devez les inclure toutes en tant qu’autres noms du sujet.</span><span class="sxs-lookup"><span data-stu-id="d7083-150">If you have multiple Meet simple URLs, you must include all of them as subject alternative names.</span></span></p>
<p><span data-ttu-id="d7083-151">Les entrées de caractères génériques sont prises en charge pour les entrées d’URL simples.</span><span class="sxs-lookup"><span data-stu-id="d7083-151">Wildcard entries are supported for the simple URL entries.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7083-152">Web externe</span><span class="sxs-lookup"><span data-stu-id="d7083-152">Web external</span></span></p></td>
<td><p><span data-ttu-id="d7083-153">Nom de domaine complet du serveur</span><span class="sxs-lookup"><span data-stu-id="d7083-153">FQDN of the server</span></span></p></td>
<td><p><span data-ttu-id="d7083-154">Pour chaque élément suivant :</span><span class="sxs-lookup"><span data-stu-id="d7083-154">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="d7083-155">Nom de domaine complet web externe</span><span class="sxs-lookup"><span data-stu-id="d7083-155">External web FQDN</span></span></p></li>
<li><p><span data-ttu-id="d7083-156">URL simple Dial-in</span><span class="sxs-lookup"><span data-stu-id="d7083-156">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="d7083-157">Répondre aux URL simples par domaine SIP</span><span class="sxs-lookup"><span data-stu-id="d7083-157">Meet simple URLs per SIP domain</span></span></p></li>
<li><p><span data-ttu-id="d7083-158">Ou, une entrée de caractère générique pour les URL simples</span><span class="sxs-lookup"><span data-stu-id="d7083-158">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="d7083-159">SN = SE01. contoso. com ; SAN = webcon01. contoso. com ; SAN = réunion. contoso. com ; SAN = réunion. fabrikam. com ; SAN = Dialin. contoso. com</span><span class="sxs-lookup"><span data-stu-id="d7083-159">SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</span></span></p>
<p><span data-ttu-id="d7083-160">Utilisation d’un certificat de caractère générique :</span><span class="sxs-lookup"><span data-stu-id="d7083-160">Using a wildcard certificate:</span></span></p>
<p><span data-ttu-id="d7083-161">SN = SE01. contoso. com ; SAN = webcon01. contoso. com ; SAN = \*. contoso. com</span><span class="sxs-lookup"><span data-stu-id="d7083-161">SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="d7083-162">Si vous disposez de plusieurs URL simples Meet, vous devez les inclure toutes en tant qu’autres noms du sujet.</span><span class="sxs-lookup"><span data-stu-id="d7083-162">If you have multiple Meet simple URLs, you must include all of them as subject alternative names.</span></span></p>
<p><span data-ttu-id="d7083-163">Les entrées de caractères génériques sont prises en charge pour les entrées d’URL simples.</span><span class="sxs-lookup"><span data-stu-id="d7083-163">Wildcard entries are supported for the simple URL entries.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-front-end-server-in-a-front-end-pool"></a><span data-ttu-id="d7083-164">Certificats pour les serveurs frontaux dans un pool frontal</span><span class="sxs-lookup"><span data-stu-id="d7083-164">Certificates for Front End Server in a Front End Pool</span></span>

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
<th><span data-ttu-id="d7083-165">Certificat</span><span class="sxs-lookup"><span data-stu-id="d7083-165">Certificate</span></span></th>
<th><span data-ttu-id="d7083-166">Nom du sujet/nom commun</span><span class="sxs-lookup"><span data-stu-id="d7083-166">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="d7083-167">Autre nom du sujet</span><span class="sxs-lookup"><span data-stu-id="d7083-167">Subject alternative name</span></span></th>
<th><span data-ttu-id="d7083-168">Exemple</span><span class="sxs-lookup"><span data-stu-id="d7083-168">Example</span></span></th>
<th><span data-ttu-id="d7083-169">Comments</span><span class="sxs-lookup"><span data-stu-id="d7083-169">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d7083-170">Par défaut</span><span class="sxs-lookup"><span data-stu-id="d7083-170">Default</span></span></p></td>
<td><p><span data-ttu-id="d7083-171">Nom de domaine complet du pool</span><span class="sxs-lookup"><span data-stu-id="d7083-171">FQDN of the pool</span></span></p></td>
<td><p><span data-ttu-id="d7083-172">Nom de domaine complet du pool et nom de domaine complet du serveur.</span><span class="sxs-lookup"><span data-stu-id="d7083-172">FQDN of the pool and FQDN of the server.</span></span></p>
<p><span data-ttu-id="d7083-173">Si vous disposez de plusieurs domaines SIP et avez activé la configuration automatique des clients, l’Assistant Certificat détecte et ajoute le nom complet de chaque domaine SIP pris en charge.</span><span class="sxs-lookup"><span data-stu-id="d7083-173">If you have multiple SIP domains and have enabled automatic client configuration, the certificate wizard detects and adds each supported SIP domain FQDNs.</span></span></p>
<p><span data-ttu-id="d7083-174">Si ce pool est le serveur d’ouverture de session automatique pour les clients et si la correspondance DNS stricte est requise dans la stratégie de groupe, vous avez également besoin d’entrées pour sip.sipdomain (pour chacun des domaines SIP dont vous disposez).</span><span class="sxs-lookup"><span data-stu-id="d7083-174">If this pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need entries for sip.sipdomain (for each SIP domain you have).</span></span></p></td>
<td><p><span data-ttu-id="d7083-175">SN = EEpool. contoso. com ; SAN = EEpool. contoso. com ; SAN = ee01. contoso. com</span><span class="sxs-lookup"><span data-stu-id="d7083-175">SN=eepool.contoso.com; SAN=eepool.contoso.com; SAN=ee01.contoso.com</span></span></p>
<p><span data-ttu-id="d7083-176">Si ce pool est le serveur d’ouverture de session automatique pour les clients et si la correspondance DNS stricte est requise dans la stratégie de groupe, SAN=sip.contoso.com et SAN=sip.fabrikam.com sont également nécessaires.</span><span class="sxs-lookup"><span data-stu-id="d7083-176">If this pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need SAN=sip.contoso.com; SAN=sip.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="d7083-177">L’Assistant détecte les domaines SIP indiqués lors de l’installation et les ajoute automatiquement à l’autre nom du sujet.</span><span class="sxs-lookup"><span data-stu-id="d7083-177">The wizard detects any SIP domains you specified during setup and automatically adds them to the subject alternative name.</span></span></p>
<p><span data-ttu-id="d7083-178">Vous pouvez également utiliser ce certificat pour l’authentification de serveur à serveur.</span><span class="sxs-lookup"><span data-stu-id="d7083-178">You can also use this certificate for Server-to-Server Authentication.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7083-179">Web interne</span><span class="sxs-lookup"><span data-stu-id="d7083-179">Web Internal</span></span></p></td>
<td><p><span data-ttu-id="d7083-180">Nom de domaine complet du pool</span><span class="sxs-lookup"><span data-stu-id="d7083-180">FQDN of the pool</span></span></p></td>
<td><p><span data-ttu-id="d7083-181">Pour chaque élément suivant :</span><span class="sxs-lookup"><span data-stu-id="d7083-181">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="d7083-182">Nom de domaine complet Web interne (qui n’est pas le même que le nom de domaine complet du serveur)</span><span class="sxs-lookup"><span data-stu-id="d7083-182">Internal web FQDN (which is NOT the same as the FQDN of the server)</span></span></p></li>
<li><p><span data-ttu-id="d7083-183">Nom de domaine complet du serveur</span><span class="sxs-lookup"><span data-stu-id="d7083-183">Server FQDN</span></span></p></li>
<li><p><span data-ttu-id="d7083-184">Nom de domaine complet du pool Lync</span><span class="sxs-lookup"><span data-stu-id="d7083-184">Lync pool FQDN</span></span></p></li>
<li><p><span data-ttu-id="d7083-185">URL simples Meet</span><span class="sxs-lookup"><span data-stu-id="d7083-185">Meet simple URLs</span></span></p></li>
<li><p><span data-ttu-id="d7083-186">URL simple Dial-in</span><span class="sxs-lookup"><span data-stu-id="d7083-186">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="d7083-187">URL simple Admin</span><span class="sxs-lookup"><span data-stu-id="d7083-187">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="d7083-188">Ou, une entrée de caractère générique pour les URL simples</span><span class="sxs-lookup"><span data-stu-id="d7083-188">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="d7083-189">SN = ee01. contoso. com ; SAN = ee01. contoso. com ; SAN = réunion. contoso. com ; SAN = réunion. fabrikam. com ; SAN = Dialin. contoso. com ; SAN = admin. contoso. com</span><span class="sxs-lookup"><span data-stu-id="d7083-189">SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</span></span></p>
<p><span data-ttu-id="d7083-190">Utilisation d’un certificat de caractère générique :</span><span class="sxs-lookup"><span data-stu-id="d7083-190">Using a wildcard certificate:</span></span></p>
<p><span data-ttu-id="d7083-191">SN = ee01. contoso. com ; SAN = ee01. contoso. com ; SAN = \*. contoso. com</span><span class="sxs-lookup"><span data-stu-id="d7083-191">SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN=\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="d7083-192">Si vous disposez de plusieurs URL simples Meet, vous devez les inclure toutes en tant qu’autres noms du sujet.</span><span class="sxs-lookup"><span data-stu-id="d7083-192">If you have multiple Meet simple URLs, you must include all of them as subject alternative names.</span></span></p>
<p><span data-ttu-id="d7083-193">Les entrées de caractères génériques sont prises en charge pour les entrées d’URL simples.</span><span class="sxs-lookup"><span data-stu-id="d7083-193">Wildcard entries are supported for the simple URL entries.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7083-194">Web externe</span><span class="sxs-lookup"><span data-stu-id="d7083-194">Web external</span></span></p></td>
<td><p><span data-ttu-id="d7083-195">Nom de domaine complet du pool</span><span class="sxs-lookup"><span data-stu-id="d7083-195">FQDN of the pool</span></span></p></td>
<td><p><span data-ttu-id="d7083-196">Pour chaque élément suivant :</span><span class="sxs-lookup"><span data-stu-id="d7083-196">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="d7083-197">Nom de domaine complet web externe</span><span class="sxs-lookup"><span data-stu-id="d7083-197">External web FQDN</span></span></p></li>
<li><p><span data-ttu-id="d7083-198">URL simple Dial-in</span><span class="sxs-lookup"><span data-stu-id="d7083-198">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="d7083-199">URL simple Admin</span><span class="sxs-lookup"><span data-stu-id="d7083-199">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="d7083-200">Ou, une entrée de caractère générique pour les URL simples</span><span class="sxs-lookup"><span data-stu-id="d7083-200">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="d7083-201">SN = ee01. contoso. com ; SAN = webcon01. contoso. com ; SAN = réunion. contoso. com ; SAN = réunion. fabrikam. com ; SAN = Dialin. contoso. com</span><span class="sxs-lookup"><span data-stu-id="d7083-201">SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</span></span></p>
<p><span data-ttu-id="d7083-202">Utilisation d’un certificat de caractère générique :</span><span class="sxs-lookup"><span data-stu-id="d7083-202">Using a wildcard certificate:</span></span></p>
<p><span data-ttu-id="d7083-203">SN = ee01. contoso. com ; SAN = webcon01. contoso. com ; SAN = \*. contoso. com</span><span class="sxs-lookup"><span data-stu-id="d7083-203">SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="d7083-204">Si vous disposez de plusieurs URL simples Meet, vous devez les inclure toutes en tant qu’autres noms du sujet.</span><span class="sxs-lookup"><span data-stu-id="d7083-204">If you have multiple Meet simple URLs, you must include all of them as subject alternative names.</span></span></p>
<p><span data-ttu-id="d7083-205">Les entrées de caractères génériques sont prises en charge pour les entrées d’URL simples.</span><span class="sxs-lookup"><span data-stu-id="d7083-205">Wildcard entries are supported for the simple URL entries.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-director"></a><span data-ttu-id="d7083-206">Certificats pour le directeur</span><span class="sxs-lookup"><span data-stu-id="d7083-206">Certificates for Director</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d7083-207">Certificat</span><span class="sxs-lookup"><span data-stu-id="d7083-207">Certificate</span></span></th>
<th><span data-ttu-id="d7083-208">Nom du sujet/nom commun</span><span class="sxs-lookup"><span data-stu-id="d7083-208">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="d7083-209">Autre nom du sujet</span><span class="sxs-lookup"><span data-stu-id="d7083-209">Subject alternative name</span></span></th>
<th><span data-ttu-id="d7083-210">Exemple</span><span class="sxs-lookup"><span data-stu-id="d7083-210">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d7083-211">Par défaut</span><span class="sxs-lookup"><span data-stu-id="d7083-211">Default</span></span></p></td>
<td><p><span data-ttu-id="d7083-212">Nom de domaine complet du pool directeur</span><span class="sxs-lookup"><span data-stu-id="d7083-212">FQDN of the Director pool</span></span></p></td>
<td><p><span data-ttu-id="d7083-213">Nom de domaine complet du directeur, nom de domaine complet du pool directeur</span><span class="sxs-lookup"><span data-stu-id="d7083-213">FQDN of the Director, FQDN of the Director pool</span></span></p>
<p><span data-ttu-id="d7083-214">Si ce pool est le serveur d’ouverture de session automatique pour les clients et si la correspondance DNS stricte est requise dans la stratégie de groupe, vous avez également besoin d’entrées pour sip.sipdomain (pour chacun des domaines SIP dont vous disposez).</span><span class="sxs-lookup"><span data-stu-id="d7083-214">If this pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need entries for sip.sipdomain (for each SIP domain you have).</span></span></p></td>
<td><p><span data-ttu-id="d7083-215">SN = dir-pool.contoso.com ; SAN = dir-pool.contoso.com ; SAN = DIR01. contoso. com</span><span class="sxs-lookup"><span data-stu-id="d7083-215">SN=dir-pool.contoso.com; SAN=dir-pool.contoso.com; SAN=dir01.contoso.com</span></span></p>
<p><span data-ttu-id="d7083-216">Si ce pool directeur est le serveur d’ouverture de session automatique pour les clients et si la correspondance DNS stricte est requise dans la stratégie de groupe, SAN=sip.contoso.com et SAN=sip.fabrikam.com sont également nécessaires.</span><span class="sxs-lookup"><span data-stu-id="d7083-216">If this Director pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need SAN=sip.contoso.com; SAN=sip.fabrikam.com</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7083-217">Web interne</span><span class="sxs-lookup"><span data-stu-id="d7083-217">Web Internal</span></span></p></td>
<td><p><span data-ttu-id="d7083-218">Nom de domaine complet du serveur</span><span class="sxs-lookup"><span data-stu-id="d7083-218">FQDN of the server</span></span></p></td>
<td><p><span data-ttu-id="d7083-219">Pour chaque élément suivant :</span><span class="sxs-lookup"><span data-stu-id="d7083-219">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="d7083-220">Nom de domaine complet web interne (qui est le même que celui du serveur)</span><span class="sxs-lookup"><span data-stu-id="d7083-220">Internal web FQDN (which is the same as the FQDN of the server)</span></span></p></li>
<li><p><span data-ttu-id="d7083-221">Nom de domaine complet du serveur</span><span class="sxs-lookup"><span data-stu-id="d7083-221">Server FQDN</span></span></p></li>
<li><p><span data-ttu-id="d7083-222">Nom de domaine complet du pool Lync</span><span class="sxs-lookup"><span data-stu-id="d7083-222">Lync pool FQDN</span></span></p></li>
<li><p><span data-ttu-id="d7083-223">URL simples Meet</span><span class="sxs-lookup"><span data-stu-id="d7083-223">Meet simple URLs</span></span></p></li>
<li><p><span data-ttu-id="d7083-224">URL simple Dial-in</span><span class="sxs-lookup"><span data-stu-id="d7083-224">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="d7083-225">URL simple Admin</span><span class="sxs-lookup"><span data-stu-id="d7083-225">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="d7083-226">Ou, une entrée de caractère générique pour les URL simples</span><span class="sxs-lookup"><span data-stu-id="d7083-226">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="d7083-227">SN = DIR01. contoso. com ; SAN = DIR01. contoso. com ; SAN = réunion. contoso. com ; SAN = réunion. fabrikam. com ; SAN = Dialin. contoso. com ; SAN = admin. contoso. com</span><span class="sxs-lookup"><span data-stu-id="d7083-227">SN=dir01.contoso.com; SAN=dir01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</span></span></p>
<p><span data-ttu-id="d7083-228">SN = DIR01. contoso. com ; SAN = DIR01. contoso. com SAN = \*. contoso. com</span><span class="sxs-lookup"><span data-stu-id="d7083-228">SN=dir01.contoso.com; SAN=dir01.contoso.com SAN=\*.contoso.com</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7083-229">Web externe</span><span class="sxs-lookup"><span data-stu-id="d7083-229">Web external</span></span></p></td>
<td><p><span data-ttu-id="d7083-230">Nom de domaine complet du serveur</span><span class="sxs-lookup"><span data-stu-id="d7083-230">FQDN of the server</span></span></p></td>
<td><p><span data-ttu-id="d7083-231">Pour chaque élément suivant :</span><span class="sxs-lookup"><span data-stu-id="d7083-231">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="d7083-232">Nom de domaine complet web externe</span><span class="sxs-lookup"><span data-stu-id="d7083-232">External web FQDN</span></span></p></li>
<li><p><span data-ttu-id="d7083-233">URL simple Dial-in</span><span class="sxs-lookup"><span data-stu-id="d7083-233">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="d7083-234">URL simple Admin</span><span class="sxs-lookup"><span data-stu-id="d7083-234">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="d7083-235">Ou, une entrée de caractère générique pour les URL simples</span><span class="sxs-lookup"><span data-stu-id="d7083-235">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="d7083-236">Le nom de domaine complet du directeur de site Web externe doit être différent du pool frontal ou du serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="d7083-236">The Director external web FQDN must be different from the Front End pool or Front End Server.</span></span></p>
<p><span data-ttu-id="d7083-237">SN = DIR01. contoso. com ; SAN = directorwebcon01. contoso. com SAN = réunion. contoso. com ; SAN = réunion. fabrikam. com ; SAN = Dialin. contoso. com</span><span class="sxs-lookup"><span data-stu-id="d7083-237">SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</span></span></p>
<p><span data-ttu-id="d7083-238">SN = DIR01. contoso. com ; SAN = directorwebcon01. contoso. com SAN = \*. contoso. com</span><span class="sxs-lookup"><span data-stu-id="d7083-238">SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=\*.contoso.com</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="d7083-p107">Si vous disposez d’un pool de serveurs de médiation autonomes, chaque serveur dans le pool nécessite les certificats répertoriés dans le tableau suivant. (Si vous colocalisez les serveurs de médiation avec les serveurs frontaux, les certificats répertoriés dans le tableau « Certificats pour les serveurs frontaux dans un pool frontal » plus haut dans cette rubrique suffisent).</span><span class="sxs-lookup"><span data-stu-id="d7083-p107">If you have a stand-alone Mediation Server pool, the Mediation Servers in it each need the certificates listed in the following table. If you collocate Mediation Server with the Front End Servers, the certificates listed in the “Certificates for Front End Server in Front End Pool” table earlier in this topic are sufficient.</span></span>

### <a name="certificates-for-stand-alone-mediation-server"></a><span data-ttu-id="d7083-241">Certificats pour les serveurs de médiation autonomes</span><span class="sxs-lookup"><span data-stu-id="d7083-241">Certificates for Stand-alone Mediation Server</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d7083-242">Certificat</span><span class="sxs-lookup"><span data-stu-id="d7083-242">Certificate</span></span></th>
<th><span data-ttu-id="d7083-243">Nom du sujet/nom commun</span><span class="sxs-lookup"><span data-stu-id="d7083-243">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="d7083-244">Autre nom du sujet</span><span class="sxs-lookup"><span data-stu-id="d7083-244">Subject alternative name</span></span></th>
<th><span data-ttu-id="d7083-245">Exemple</span><span class="sxs-lookup"><span data-stu-id="d7083-245">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d7083-246">Par défaut</span><span class="sxs-lookup"><span data-stu-id="d7083-246">Default</span></span></p></td>
<td><p><span data-ttu-id="d7083-247">Nom de domaine complet du pool</span><span class="sxs-lookup"><span data-stu-id="d7083-247">FQDN of the pool</span></span></p></td>
<td><p><span data-ttu-id="d7083-248">Nom de domaine complet du pool</span><span class="sxs-lookup"><span data-stu-id="d7083-248">FQDN of the pool</span></span></p>
<p><span data-ttu-id="d7083-249">Nom de domaine complet du serveur membre du pool</span><span class="sxs-lookup"><span data-stu-id="d7083-249">FQDN of pool member server</span></span></p></td>
<td><p><span data-ttu-id="d7083-250">SN = medsvr-pool.contoso.net ; SAN = medsvr-pool.contoso.net ; SAN = medsvr01. contoso. net</span><span class="sxs-lookup"><span data-stu-id="d7083-250">SN=medsvr-pool.contoso.net; SAN=medsvr-pool.contoso.net; SAN=medsvr01.contoso.net</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-survivable-branch-appliance"></a><span data-ttu-id="d7083-251">Certificats pour les Survivable Branch Appliances</span><span class="sxs-lookup"><span data-stu-id="d7083-251">Certificates for Survivable Branch Appliance</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d7083-252">Certificat</span><span class="sxs-lookup"><span data-stu-id="d7083-252">Certificate</span></span></th>
<th><span data-ttu-id="d7083-253">Nom du sujet/nom commun</span><span class="sxs-lookup"><span data-stu-id="d7083-253">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="d7083-254">Autre nom du sujet</span><span class="sxs-lookup"><span data-stu-id="d7083-254">Subject alternative name</span></span></th>
<th><span data-ttu-id="d7083-255">Exemple</span><span class="sxs-lookup"><span data-stu-id="d7083-255">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d7083-256">Par défaut</span><span class="sxs-lookup"><span data-stu-id="d7083-256">Default</span></span></p></td>
<td><p><span data-ttu-id="d7083-257">Nom de domaine complet de l’appliance</span><span class="sxs-lookup"><span data-stu-id="d7083-257">FQDN of the appliance</span></span></p></td>
<td><p><span data-ttu-id="d7083-258">SIP. &lt; sipdomain &gt; (nécessite une entrée par domaine SIP)</span><span class="sxs-lookup"><span data-stu-id="d7083-258">SIP.&lt;sipdomain&gt; (need one entry per SIP domain)</span></span></p></td>
<td><p><span data-ttu-id="d7083-259">SN = sba01. contoso. net ; SAN = SIP. contoso. com ; SAN = SIP. fabrikam. com</span><span class="sxs-lookup"><span data-stu-id="d7083-259">SN=sba01.contoso.net; SAN=sip.contoso.com; SAN=sip.fabrikam.com</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="d7083-260">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d7083-260">See Also</span></span>


[<span data-ttu-id="d7083-261">Prise en charge de certificat générique dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d7083-261">Wildcard certificate support in Lync Server 2013</span></span>](lync-server-2013-wildcard-certificate-support.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

