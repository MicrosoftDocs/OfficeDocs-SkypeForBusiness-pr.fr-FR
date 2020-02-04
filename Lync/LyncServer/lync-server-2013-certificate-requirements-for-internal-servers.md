---
title: 'Lync Server 2013 : Exigences de certificat pour les serveurs internes'
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
ms.openlocfilehash: 0351ab4f54273e1eccc09992ab933525cc2527ae
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736784"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-requirements-for-internal-servers-in-lync-server-2013"></a><span data-ttu-id="8e2fd-102">Exigences de certificat pour les serveurs internes dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8e2fd-102">Certificate requirements for internal servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8e2fd-103">_**Dernière modification de la rubrique :** 2017-02-17_</span><span class="sxs-lookup"><span data-stu-id="8e2fd-103">_**Topic Last Modified:** 2017-02-17_</span></span>

<span data-ttu-id="8e2fd-104">Les serveurs internes exécutant Lync Server et qui nécessitent des certificats incluent Standard Edition Server, Enterprise Edition front end Server, serveur de médiation et Director.</span><span class="sxs-lookup"><span data-stu-id="8e2fd-104">Internal servers that are running Lync Server and that require certificates include Standard Edition server, Enterprise Edition Front End Server, Mediation Server, and Director.</span></span> <span data-ttu-id="8e2fd-105">Le tableau suivant répertorie les conditions requises pour les certificats pour ces serveurs.</span><span class="sxs-lookup"><span data-stu-id="8e2fd-105">The following table shows the certificate requirements for these servers.</span></span> <span data-ttu-id="8e2fd-106">Vous pouvez utiliser l’Assistant certificat de serveur Lync pour demander ces certificats.</span><span class="sxs-lookup"><span data-stu-id="8e2fd-106">You can use the Lync Server certificate wizard to request these certificates.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="8e2fd-107">Les certificats génériques sont pris en charge pour les noms de remplacement d’objet associés aux URL simples sur le pool frontal, serveur frontal ou Director.</span><span class="sxs-lookup"><span data-stu-id="8e2fd-107">Wildcard certificates are supported for the subject alternative names associated with the simple URLs on the Front End pool, Front End Server, or Director.</span></span> <span data-ttu-id="8e2fd-108">Pour plus d’informations sur la prise en charge des certificats génériques, voir <A href="lync-server-2013-wildcard-certificate-support.md">prise en charge des certificats génériques dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="8e2fd-108">For details about wildcard certificate support, see <A href="lync-server-2013-wildcard-certificate-support.md">Wildcard certificate support in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="8e2fd-109">Même si une autorité de certification d’entreprise interne est recommandée pour les serveurs internes, vous pouvez également utiliser une autorité de certification publique.</span><span class="sxs-lookup"><span data-stu-id="8e2fd-109">Although an internal enterprise certification authority (CA) is recommended for internal servers, you can also use a public CA.</span></span> <span data-ttu-id="8e2fd-110">Pour obtenir une liste des autorités de certification publiques qui fournissent des certificats qui répondent à des exigences spécifiques pour les certificats de communications unifiées (UC) et qui ont un partenariat avec Microsoft pour s’assurer qu’ils fonctionnent avec l’Assistant certificat de Lync Server, voir l’article 929395 de la base de connaissances Microsoft, [https://go.microsoft.com/fwlink/p/?linkId=202834](https://go.microsoft.com/fwlink/p/?linkid=202834)« partenaires de certification de communications unifiées » pour Exchange Server et pour Communications Server».</span><span class="sxs-lookup"><span data-stu-id="8e2fd-110">For a list of public CAs that provide certificates that comply with specific requirements for unified communications (UC) certificates and have partnered with Microsoft to ensure they work with the Lync Server Certificate Wizard, see article Microsoft Knowledge Base 929395, "Unified Communications Certificate Partners for Exchange Server and for Communications Server," at [https://go.microsoft.com/fwlink/p/?linkId=202834](https://go.microsoft.com/fwlink/p/?linkid=202834).</span></span>

<span data-ttu-id="8e2fd-111">La communication avec d’autres applications et serveurs, comme Exchange 2013, nécessite un certificat pris en charge par les autres applications et produits.</span><span class="sxs-lookup"><span data-stu-id="8e2fd-111">Communication with other applications and servers, such as Exchange 2013, requires a certificate that is supported by the other applications and products.</span></span> <span data-ttu-id="8e2fd-112">Pour la version 2013, Lync Server 2013 et d’autres produits Microsoft Server, dont Exchange 2013 et SharePoint Server, prennent en charge le protocole d’autorisation Open (OAuth) pour l’authentification et l’autorisation de serveur à serveur.</span><span class="sxs-lookup"><span data-stu-id="8e2fd-112">For the 2013 release, Lync Server 2013 and other Microsoft server products, including Exchange 2013 and SharePoint Server, support the Open Authorization (OAuth) protocol for server-to-server authentication and authorization.</span></span> <span data-ttu-id="8e2fd-113">Pour plus d’informations, reportez-vous à la section [gestion des applications d’authentification de serveur à serveur (OAuth) et de partenariat dans Lync server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) dans la documentation de déploiement ou la documentation des opérations.</span><span class="sxs-lookup"><span data-stu-id="8e2fd-113">For details, see [Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) in the Deployment documentation or the Operations documentation.</span></span>

<span data-ttu-id="8e2fd-114">Pour les connexions de clients exécutant le système d’exploitation Windows 7, le système d’exploitation Windows Server 2008, le système d’exploitation Windows Server 2008 R2, le système d’exploitation Windows Vista et Microsoft Lync Phone Edition, Lync Server 2013 prend en charge (mais pas requis) certificats signés à l’aide de la fonction de hachage de chiffrement SHA-256.</span><span class="sxs-lookup"><span data-stu-id="8e2fd-114">For connections from clients running Windows 7 operating system, Windows Server 2008 operating system, Windows Server 2008 R2 operating system, Windows Vista operating system, and Microsoft Lync Phone Edition, Lync Server 2013 includes support for (but does not require) certificates signed using the SHA-256 cryptographic hash function.</span></span> <span data-ttu-id="8e2fd-115">Pour prendre en charge l’accès externe à l’aide de l’algorithme SHA-256, le certificat externe est émis par une autorité de certification publique utilisant SHA-256.</span><span class="sxs-lookup"><span data-stu-id="8e2fd-115">To support external access using SHA-256, the external certificate is issued by a public CA using SHA-256.</span></span>

<span data-ttu-id="8e2fd-116">Les tableaux suivants illustrent les exigences de certificat par rôle de serveur pour les pools frontaux et les serveurs Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="8e2fd-116">The following tables show certificate requirements by server role for Front End pools and Standard Edition servers.</span></span> <span data-ttu-id="8e2fd-117">Il s’agit d’un certificat de serveur Web standard, d’une clé privée, d’un serveur non transférable.</span><span class="sxs-lookup"><span data-stu-id="8e2fd-117">All these are standard web server certificates, private key, non-exportable.</span></span>

<span data-ttu-id="8e2fd-118">Notez que l’utilisation améliorée de la clé du serveur est automatiquement configurée lorsque vous utilisez l’Assistant Certificat pour demander des certificats.</span><span class="sxs-lookup"><span data-stu-id="8e2fd-118">Note that server enhanced key usage (EKU) is automatically configured when you use the certificate wizard to request certificates.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8e2fd-119">Chaque nom convivial de certificat doit être unique dans le magasin d’ordinateurs.</span><span class="sxs-lookup"><span data-stu-id="8e2fd-119">Each certificate Friendly Name must be unique in the computer store.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="8e2fd-120">Si vous avez configuré sipinternal.contoso.com ou sipexternal.contoso.com dans votre DNS, vous devez l’ajouter dans le nom de l’autre nom de l’objet du certificat.</span><span class="sxs-lookup"><span data-stu-id="8e2fd-120">If you have configured sipinternal.contoso.com or sipexternal.contoso.com in your DNS, you will need to add them in the certificate’s Subject Alternative Name.</span></span>



</div>

### <a name="certificates-for-standard-edition-server"></a><span data-ttu-id="8e2fd-121">Certificats pour Standard Edition Server</span><span class="sxs-lookup"><span data-stu-id="8e2fd-121">Certificates for Standard Edition Server</span></span>

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
<th><span data-ttu-id="8e2fd-122">Certificat</span><span class="sxs-lookup"><span data-stu-id="8e2fd-122">Certificate</span></span></th>
<th><span data-ttu-id="8e2fd-123">Nom de l’objet/nom usuel</span><span class="sxs-lookup"><span data-stu-id="8e2fd-123">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="8e2fd-124">Autre nom du sujet</span><span class="sxs-lookup"><span data-stu-id="8e2fd-124">Subject alternative name</span></span></th>
<th><span data-ttu-id="8e2fd-125">Exemple</span><span class="sxs-lookup"><span data-stu-id="8e2fd-125">Example</span></span></th>
<th><span data-ttu-id="8e2fd-126">Commentaires</span><span class="sxs-lookup"><span data-stu-id="8e2fd-126">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8e2fd-127">Par défaut</span><span class="sxs-lookup"><span data-stu-id="8e2fd-127">Default</span></span></p></td>
<td><p><span data-ttu-id="8e2fd-128">Nom de domaine complet (FQDN) du pool</span><span class="sxs-lookup"><span data-stu-id="8e2fd-128">Fully qualified domain name (FQDN) of the pool</span></span></p></td>
<td><p><span data-ttu-id="8e2fd-129">Nom de domaine complet (FQDN) du pool et nom de domaine complet du serveur</span><span class="sxs-lookup"><span data-stu-id="8e2fd-129">FQDN of the pool and the FQDN of the server</span></span></p>
<p><span data-ttu-id="8e2fd-130">Si vous disposez de plusieurs domaines SIP et avez activé la configuration automatique des clients, l’Assistant Certificat détecte et ajoute le nom complet de chaque domaine SIP pris en charge.</span><span class="sxs-lookup"><span data-stu-id="8e2fd-130">If you have multiple SIP domains and have enabled automatic client configuration, the certificate wizard detects and adds each supported SIP domain FQDNs.</span></span></p>
<p><span data-ttu-id="8e2fd-131">Si ce pool est le serveur d’ouverture de session automatique pour les clients et si la correspondance DNS (Domain Name System) stricte est requise dans la stratégie de groupe, vous avez également besoin d’entrées pour sip.sipdomain (pour chacun des domaines SIP dont vous disposez).</span><span class="sxs-lookup"><span data-stu-id="8e2fd-131">If this pool is the auto-logon server for clients and strict Domain Name System (DNS) matching is required in group policy, you also need entries for sip.sipdomain (for each SIP domain you have).</span></span></p></td>
<td><p><span data-ttu-id="8e2fd-132">SN=se01.contoso.com; SAN=se01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8e2fd-132">SN=se01.contoso.com; SAN=se01.contoso.com</span></span></p>
<p><span data-ttu-id="8e2fd-133">Si ce pool est le serveur d’ouverture de session automatique pour les clients et si la correspondance DNS stricte est requise dans la stratégie de groupe, SAN=sip.contoso.com et SAN=sip.fabrikam.com sont également nécessaires.</span><span class="sxs-lookup"><span data-stu-id="8e2fd-133">If this pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need SAN=sip.contoso.com; SAN=sip.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="8e2fd-134">Sur un serveur Standard Edition Server, le nom de domaine complet du serveur est identique au nom de domaine complet du pool.</span><span class="sxs-lookup"><span data-stu-id="8e2fd-134">On Standard Edition server, the server FQDN is the same as the pool FQDN.</span></span></p>
<p><span data-ttu-id="8e2fd-135">L’Assistant détecte les domaines SIP indiqués lors de l’installation et les ajoute automatiquement à l’autre nom du sujet.</span><span class="sxs-lookup"><span data-stu-id="8e2fd-135">The wizard detects any SIP domains you specified during setup and automatically adds them to the subject alternative name.</span></span></p>
<p><span data-ttu-id="8e2fd-136">Vous pouvez aussi utiliser ce certificat pour l’authentification de serveur à serveur.</span><span class="sxs-lookup"><span data-stu-id="8e2fd-136">You can also use this certificate for Server-to-Server Authentication.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e2fd-137">Web interne</span><span class="sxs-lookup"><span data-stu-id="8e2fd-137">Web internal</span></span></p></td>
<td><p><span data-ttu-id="8e2fd-138">Nom de domaine complet du serveur</span><span class="sxs-lookup"><span data-stu-id="8e2fd-138">FQDN of the server</span></span></p></td>
<td><p><span data-ttu-id="8e2fd-139">Pour chaque élément suivant :</span><span class="sxs-lookup"><span data-stu-id="8e2fd-139">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="8e2fd-140">Nom de domaine complet web interne (qui est le même que celui du serveur)</span><span class="sxs-lookup"><span data-stu-id="8e2fd-140">Internal web FQDN (which is the same as the FQDN of the server)</span></span></p></li>
<li><p><span data-ttu-id="8e2fd-141">URL simples Meet</span><span class="sxs-lookup"><span data-stu-id="8e2fd-141">Meet simple URLs</span></span></p></li>
<li><p><span data-ttu-id="8e2fd-142">URL simple Dial-in</span><span class="sxs-lookup"><span data-stu-id="8e2fd-142">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="8e2fd-143">URL simple Admin</span><span class="sxs-lookup"><span data-stu-id="8e2fd-143">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="8e2fd-144">Ou une entrée de caractère générique pour les URL simples</span><span class="sxs-lookup"><span data-stu-id="8e2fd-144">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="8e2fd-145">SN=se01.contoso.com; SAN=se01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8e2fd-145">SN=se01.contoso.com; SAN=se01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</span></span></p>
<p><span data-ttu-id="8e2fd-146">Utilisation d’un certificat de caractère générique :</span><span class="sxs-lookup"><span data-stu-id="8e2fd-146">Using a wildcard certificate:</span></span></p>
<p><span data-ttu-id="8e2fd-147">SN=se01.contoso.com; SAN=se01.contoso.com; SAN=\*.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8e2fd-147">SN=se01.contoso.com; SAN=se01.contoso.com; SAN=\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="8e2fd-148">Vous ne pouvez pas remplacer le FQDN Web interne dans le générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="8e2fd-148">You cannot override the Internal web FQDN in Topology Builder.</span></span></p>
<p><span data-ttu-id="8e2fd-149">Si vous avez plusieurs URL de la réunion, vous devez les inclure en tant qu’autres noms d’objet.</span><span class="sxs-lookup"><span data-stu-id="8e2fd-149">If you have multiple Meet simple URLs, you must include all of them as subject alternative names.</span></span></p>
<p><span data-ttu-id="8e2fd-150">Les entrées de caractères génériques sont prises en charge pour les entrées d’URL simples.</span><span class="sxs-lookup"><span data-stu-id="8e2fd-150">Wildcard entries are supported for the simple URL entries.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8e2fd-151">Web externe</span><span class="sxs-lookup"><span data-stu-id="8e2fd-151">Web external</span></span></p></td>
<td><p><span data-ttu-id="8e2fd-152">Nom de domaine complet du serveur</span><span class="sxs-lookup"><span data-stu-id="8e2fd-152">FQDN of the server</span></span></p></td>
<td><p><span data-ttu-id="8e2fd-153">Pour chaque élément suivant :</span><span class="sxs-lookup"><span data-stu-id="8e2fd-153">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="8e2fd-154">Nom de domaine complet web externe</span><span class="sxs-lookup"><span data-stu-id="8e2fd-154">External web FQDN</span></span></p></li>
<li><p><span data-ttu-id="8e2fd-155">URL simple Dial-in</span><span class="sxs-lookup"><span data-stu-id="8e2fd-155">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="8e2fd-156">URL simples de réunion par domaine SIP</span><span class="sxs-lookup"><span data-stu-id="8e2fd-156">Meet simple URLs per SIP domain</span></span></p></li>
<li><p><span data-ttu-id="8e2fd-157">Ou une entrée de caractère générique pour les URL simples</span><span class="sxs-lookup"><span data-stu-id="8e2fd-157">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="8e2fd-158">SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8e2fd-158">SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</span></span></p>
<p><span data-ttu-id="8e2fd-159">Utilisation d’un certificat de caractère générique :</span><span class="sxs-lookup"><span data-stu-id="8e2fd-159">Using a wildcard certificate:</span></span></p>
<p><span data-ttu-id="8e2fd-160">SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=\*.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8e2fd-160">SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="8e2fd-161">Si vous avez plusieurs URL de la réunion, vous devez les inclure en tant qu’autres noms d’objet.</span><span class="sxs-lookup"><span data-stu-id="8e2fd-161">If you have multiple Meet simple URLs, you must include all of them as subject alternative names.</span></span></p>
<p><span data-ttu-id="8e2fd-162">Les entrées de caractères génériques sont prises en charge pour les entrées d’URL simples.</span><span class="sxs-lookup"><span data-stu-id="8e2fd-162">Wildcard entries are supported for the simple URL entries.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-front-end-server-in-a-front-end-pool"></a><span data-ttu-id="8e2fd-163">Certificats pour serveur frontal dans un pool frontal</span><span class="sxs-lookup"><span data-stu-id="8e2fd-163">Certificates for Front End Server in a Front End Pool</span></span>

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
<th><span data-ttu-id="8e2fd-164">Certificat</span><span class="sxs-lookup"><span data-stu-id="8e2fd-164">Certificate</span></span></th>
<th><span data-ttu-id="8e2fd-165">Nom de l’objet/nom usuel</span><span class="sxs-lookup"><span data-stu-id="8e2fd-165">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="8e2fd-166">Autre nom du sujet</span><span class="sxs-lookup"><span data-stu-id="8e2fd-166">Subject alternative name</span></span></th>
<th><span data-ttu-id="8e2fd-167">Exemple</span><span class="sxs-lookup"><span data-stu-id="8e2fd-167">Example</span></span></th>
<th><span data-ttu-id="8e2fd-168">Commentaires</span><span class="sxs-lookup"><span data-stu-id="8e2fd-168">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8e2fd-169">Par défaut</span><span class="sxs-lookup"><span data-stu-id="8e2fd-169">Default</span></span></p></td>
<td><p><span data-ttu-id="8e2fd-170">Nom de domaine complet du pool</span><span class="sxs-lookup"><span data-stu-id="8e2fd-170">FQDN of the pool</span></span></p></td>
<td><p><span data-ttu-id="8e2fd-171">Nom de domaine complet (FQDN) du pool et du nom de domaine complet du serveur.</span><span class="sxs-lookup"><span data-stu-id="8e2fd-171">FQDN of the pool and FQDN of the server.</span></span></p>
<p><span data-ttu-id="8e2fd-172">Si vous disposez de plusieurs domaines SIP et avez activé la configuration automatique des clients, l’Assistant Certificat détecte et ajoute le nom complet de chaque domaine SIP pris en charge.</span><span class="sxs-lookup"><span data-stu-id="8e2fd-172">If you have multiple SIP domains and have enabled automatic client configuration, the certificate wizard detects and adds each supported SIP domain FQDNs.</span></span></p>
<p><span data-ttu-id="8e2fd-173">Si ce pool est le serveur de connexion automatique pour les clients et si la correspondance DNS stricte est requise dans la stratégie de groupe, vous avez également besoin d’entrées pour SIP. sipdomain (pour chaque domaine SIP que vous utilisez).</span><span class="sxs-lookup"><span data-stu-id="8e2fd-173">If this pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need entries for sip.sipdomain (for each SIP domain you have).</span></span></p></td>
<td><p><span data-ttu-id="8e2fd-174">SN=eepool.contoso.com; SAN=eepool.contoso.com; SAN=ee01.contoso.com </span><span class="sxs-lookup"><span data-stu-id="8e2fd-174">SN=eepool.contoso.com; SAN=eepool.contoso.com; SAN=ee01.contoso.com</span></span></p>
<p><span data-ttu-id="8e2fd-175">Si ce pool est le serveur d’ouverture de session automatique pour les clients et si la correspondance DNS stricte est requise dans la stratégie de groupe, SAN=sip.contoso.com et SAN=sip.fabrikam.com sont également nécessaires.</span><span class="sxs-lookup"><span data-stu-id="8e2fd-175">If this pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need SAN=sip.contoso.com; SAN=sip.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="8e2fd-176">L’Assistant détecte les domaines SIP indiqués lors de l’installation et les ajoute automatiquement à l’autre nom du sujet.</span><span class="sxs-lookup"><span data-stu-id="8e2fd-176">The wizard detects any SIP domains you specified during setup and automatically adds them to the subject alternative name.</span></span></p>
<p><span data-ttu-id="8e2fd-177">Vous pouvez aussi utiliser ce certificat pour l’authentification de serveur à serveur.</span><span class="sxs-lookup"><span data-stu-id="8e2fd-177">You can also use this certificate for Server-to-Server Authentication.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e2fd-178">Site Web interne</span><span class="sxs-lookup"><span data-stu-id="8e2fd-178">Web Internal</span></span></p></td>
<td><p><span data-ttu-id="8e2fd-179">Nom de domaine complet du pool</span><span class="sxs-lookup"><span data-stu-id="8e2fd-179">FQDN of the pool</span></span></p></td>
<td><p><span data-ttu-id="8e2fd-180">Pour chaque élément suivant :</span><span class="sxs-lookup"><span data-stu-id="8e2fd-180">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="8e2fd-181">Nom de domaine complet web interne (qui N’EST PAS le même que celui du serveur)</span><span class="sxs-lookup"><span data-stu-id="8e2fd-181">Internal web FQDN (which is NOT the same as the FQDN of the server)</span></span></p></li>
<li><p><span data-ttu-id="8e2fd-182">Nom de domaine complet du serveur</span><span class="sxs-lookup"><span data-stu-id="8e2fd-182">Server FQDN</span></span></p></li>
<li><p><span data-ttu-id="8e2fd-183">Nom de domaine complet du pool Lync</span><span class="sxs-lookup"><span data-stu-id="8e2fd-183">Lync pool FQDN</span></span></p></li>
<li><p><span data-ttu-id="8e2fd-184">URL simples Meet</span><span class="sxs-lookup"><span data-stu-id="8e2fd-184">Meet simple URLs</span></span></p></li>
<li><p><span data-ttu-id="8e2fd-185">URL simple Dial-in</span><span class="sxs-lookup"><span data-stu-id="8e2fd-185">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="8e2fd-186">URL simple Admin</span><span class="sxs-lookup"><span data-stu-id="8e2fd-186">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="8e2fd-187">Ou une entrée de caractère générique pour les URL simples</span><span class="sxs-lookup"><span data-stu-id="8e2fd-187">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="8e2fd-188">SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8e2fd-188">SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</span></span></p>
<p><span data-ttu-id="8e2fd-189">Utilisation d’un certificat de caractère générique :</span><span class="sxs-lookup"><span data-stu-id="8e2fd-189">Using a wildcard certificate:</span></span></p>
<p><span data-ttu-id="8e2fd-190">SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN=\*.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8e2fd-190">SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN=\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="8e2fd-191">Si vous avez plusieurs URL de la réunion, vous devez les inclure en tant qu’autres noms d’objet.</span><span class="sxs-lookup"><span data-stu-id="8e2fd-191">If you have multiple Meet simple URLs, you must include all of them as subject alternative names.</span></span></p>
<p><span data-ttu-id="8e2fd-192">Les entrées de caractères génériques sont prises en charge pour les entrées d’URL simples.</span><span class="sxs-lookup"><span data-stu-id="8e2fd-192">Wildcard entries are supported for the simple URL entries.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8e2fd-193">Web externe</span><span class="sxs-lookup"><span data-stu-id="8e2fd-193">Web external</span></span></p></td>
<td><p><span data-ttu-id="8e2fd-194">Nom de domaine complet du pool</span><span class="sxs-lookup"><span data-stu-id="8e2fd-194">FQDN of the pool</span></span></p></td>
<td><p><span data-ttu-id="8e2fd-195">Pour chaque élément suivant :</span><span class="sxs-lookup"><span data-stu-id="8e2fd-195">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="8e2fd-196">Nom de domaine complet web externe</span><span class="sxs-lookup"><span data-stu-id="8e2fd-196">External web FQDN</span></span></p></li>
<li><p><span data-ttu-id="8e2fd-197">URL simple Dial-in</span><span class="sxs-lookup"><span data-stu-id="8e2fd-197">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="8e2fd-198">URL simple Admin</span><span class="sxs-lookup"><span data-stu-id="8e2fd-198">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="8e2fd-199">Ou une entrée de caractère générique pour les URL simples</span><span class="sxs-lookup"><span data-stu-id="8e2fd-199">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="8e2fd-200">SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8e2fd-200">SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</span></span></p>
<p><span data-ttu-id="8e2fd-201">Utilisation d’un certificat de caractère générique :</span><span class="sxs-lookup"><span data-stu-id="8e2fd-201">Using a wildcard certificate:</span></span></p>
<p><span data-ttu-id="8e2fd-202">SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=\*.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8e2fd-202">SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="8e2fd-203">Si vous avez plusieurs URL de la réunion, vous devez les inclure en tant qu’autres noms d’objet.</span><span class="sxs-lookup"><span data-stu-id="8e2fd-203">If you have multiple Meet simple URLs, you must include all of them as subject alternative names.</span></span></p>
<p><span data-ttu-id="8e2fd-204">Les entrées de caractères génériques sont prises en charge pour les entrées d’URL simples.</span><span class="sxs-lookup"><span data-stu-id="8e2fd-204">Wildcard entries are supported for the simple URL entries.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-director"></a><span data-ttu-id="8e2fd-205">Certificats pour Director</span><span class="sxs-lookup"><span data-stu-id="8e2fd-205">Certificates for Director</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8e2fd-206">Certificat</span><span class="sxs-lookup"><span data-stu-id="8e2fd-206">Certificate</span></span></th>
<th><span data-ttu-id="8e2fd-207">Nom de l’objet/nom usuel</span><span class="sxs-lookup"><span data-stu-id="8e2fd-207">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="8e2fd-208">Autre nom du sujet</span><span class="sxs-lookup"><span data-stu-id="8e2fd-208">Subject alternative name</span></span></th>
<th><span data-ttu-id="8e2fd-209">Exemple</span><span class="sxs-lookup"><span data-stu-id="8e2fd-209">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8e2fd-210">Par défaut</span><span class="sxs-lookup"><span data-stu-id="8e2fd-210">Default</span></span></p></td>
<td><p><span data-ttu-id="8e2fd-211">Nom de domaine complet (FQDN) du pool de réalisateurs</span><span class="sxs-lookup"><span data-stu-id="8e2fd-211">FQDN of the Director pool</span></span></p></td>
<td><p><span data-ttu-id="8e2fd-212">Nom de domaine complet (FQDN) du réalisateur du pool</span><span class="sxs-lookup"><span data-stu-id="8e2fd-212">FQDN of the Director, FQDN of the Director pool</span></span></p>
<p><span data-ttu-id="8e2fd-213">Si ce pool est le serveur de connexion automatique pour les clients et si la correspondance DNS stricte est requise dans la stratégie de groupe, vous avez également besoin d’entrées pour SIP. sipdomain (pour chaque domaine SIP que vous utilisez).</span><span class="sxs-lookup"><span data-stu-id="8e2fd-213">If this pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need entries for sip.sipdomain (for each SIP domain you have).</span></span></p></td>
<td><p><span data-ttu-id="8e2fd-214">SN = dir-pool.contoso.com ; SAN = dir-pool.contoso.com ; SAN = DIR01. contoso. com</span><span class="sxs-lookup"><span data-stu-id="8e2fd-214">SN=dir-pool.contoso.com; SAN=dir-pool.contoso.com; SAN=dir01.contoso.com</span></span></p>
<p><span data-ttu-id="8e2fd-215">Si ce pool de directeurs est le serveur de connexion automatique pour les clients et si la correspondance DNS stricte est requise dans la stratégie de groupe, vous devez également disposer de SAN = SIP. contoso. com ; SAN = SIP. fabrikam. com</span><span class="sxs-lookup"><span data-stu-id="8e2fd-215">If this Director pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need SAN=sip.contoso.com; SAN=sip.fabrikam.com</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e2fd-216">Site Web interne</span><span class="sxs-lookup"><span data-stu-id="8e2fd-216">Web Internal</span></span></p></td>
<td><p><span data-ttu-id="8e2fd-217">Nom de domaine complet du serveur</span><span class="sxs-lookup"><span data-stu-id="8e2fd-217">FQDN of the server</span></span></p></td>
<td><p><span data-ttu-id="8e2fd-218">Pour chaque élément suivant :</span><span class="sxs-lookup"><span data-stu-id="8e2fd-218">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="8e2fd-219">Nom de domaine complet web interne (qui est le même que celui du serveur)</span><span class="sxs-lookup"><span data-stu-id="8e2fd-219">Internal web FQDN (which is the same as the FQDN of the server)</span></span></p></li>
<li><p><span data-ttu-id="8e2fd-220">Nom de domaine complet du serveur</span><span class="sxs-lookup"><span data-stu-id="8e2fd-220">Server FQDN</span></span></p></li>
<li><p><span data-ttu-id="8e2fd-221">Nom de domaine complet du pool Lync</span><span class="sxs-lookup"><span data-stu-id="8e2fd-221">Lync pool FQDN</span></span></p></li>
<li><p><span data-ttu-id="8e2fd-222">URL simples Meet</span><span class="sxs-lookup"><span data-stu-id="8e2fd-222">Meet simple URLs</span></span></p></li>
<li><p><span data-ttu-id="8e2fd-223">URL simple Dial-in</span><span class="sxs-lookup"><span data-stu-id="8e2fd-223">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="8e2fd-224">URL simple Admin</span><span class="sxs-lookup"><span data-stu-id="8e2fd-224">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="8e2fd-225">Ou une entrée de caractère générique pour les URL simples</span><span class="sxs-lookup"><span data-stu-id="8e2fd-225">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="8e2fd-226">SN=dir01.contoso.com; SAN=dir01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8e2fd-226">SN=dir01.contoso.com; SAN=dir01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</span></span></p>
<p><span data-ttu-id="8e2fd-227">SN=dir01.contoso.com; SAN=dir01.contoso.com SAN=\*.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8e2fd-227">SN=dir01.contoso.com; SAN=dir01.contoso.com SAN=\*.contoso.com</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8e2fd-228">Web externe</span><span class="sxs-lookup"><span data-stu-id="8e2fd-228">Web external</span></span></p></td>
<td><p><span data-ttu-id="8e2fd-229">Nom de domaine complet du serveur</span><span class="sxs-lookup"><span data-stu-id="8e2fd-229">FQDN of the server</span></span></p></td>
<td><p><span data-ttu-id="8e2fd-230">Pour chaque élément suivant :</span><span class="sxs-lookup"><span data-stu-id="8e2fd-230">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="8e2fd-231">Nom de domaine complet web externe</span><span class="sxs-lookup"><span data-stu-id="8e2fd-231">External web FQDN</span></span></p></li>
<li><p><span data-ttu-id="8e2fd-232">URL simple Dial-in</span><span class="sxs-lookup"><span data-stu-id="8e2fd-232">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="8e2fd-233">URL simple Admin</span><span class="sxs-lookup"><span data-stu-id="8e2fd-233">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="8e2fd-234">Ou une entrée de caractère générique pour les URL simples</span><span class="sxs-lookup"><span data-stu-id="8e2fd-234">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="8e2fd-235">Le FQDN Web de Director doit être différent du serveur frontal ou du pool frontal.</span><span class="sxs-lookup"><span data-stu-id="8e2fd-235">The Director external web FQDN must be different from the Front End pool or Front End Server.</span></span></p>
<p><span data-ttu-id="8e2fd-236">SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8e2fd-236">SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</span></span></p>
<p><span data-ttu-id="8e2fd-237">SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=\*.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8e2fd-237">SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=\*.contoso.com</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="8e2fd-238">Si vous disposez d’un pool de serveurs de médiation autonome, vous avez besoin des certificats répertoriés dans le tableau ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="8e2fd-238">If you have a stand-alone Mediation Server pool, the Mediation Servers in it each need the certificates listed in the following table.</span></span> <span data-ttu-id="8e2fd-239">Si vous collocate un serveur de médiation avec les serveurs frontaux, les certificats répertoriés dans le tableau « certificats pour le serveur frontal du pool frontal », plus haut dans cette rubrique sont suffisants.</span><span class="sxs-lookup"><span data-stu-id="8e2fd-239">If you collocate Mediation Server with the Front End Servers, the certificates listed in the “Certificates for Front End Server in Front End Pool” table earlier in this topic are sufficient.</span></span>

### <a name="certificates-for-stand-alone-mediation-server"></a><span data-ttu-id="8e2fd-240">Certificats pour un serveur de médiation autonome</span><span class="sxs-lookup"><span data-stu-id="8e2fd-240">Certificates for Stand-alone Mediation Server</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8e2fd-241">Certificat</span><span class="sxs-lookup"><span data-stu-id="8e2fd-241">Certificate</span></span></th>
<th><span data-ttu-id="8e2fd-242">Nom de l’objet/nom usuel</span><span class="sxs-lookup"><span data-stu-id="8e2fd-242">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="8e2fd-243">Autre nom du sujet</span><span class="sxs-lookup"><span data-stu-id="8e2fd-243">Subject alternative name</span></span></th>
<th><span data-ttu-id="8e2fd-244">Exemple</span><span class="sxs-lookup"><span data-stu-id="8e2fd-244">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8e2fd-245">Par défaut</span><span class="sxs-lookup"><span data-stu-id="8e2fd-245">Default</span></span></p></td>
<td><p><span data-ttu-id="8e2fd-246">Nom de domaine complet du pool</span><span class="sxs-lookup"><span data-stu-id="8e2fd-246">FQDN of the pool</span></span></p></td>
<td><p><span data-ttu-id="8e2fd-247">Nom de domaine complet du pool</span><span class="sxs-lookup"><span data-stu-id="8e2fd-247">FQDN of the pool</span></span></p>
<p><span data-ttu-id="8e2fd-248">Nom de domaine complet du serveur de membres du pool</span><span class="sxs-lookup"><span data-stu-id="8e2fd-248">FQDN of pool member server</span></span></p></td>
<td><p><span data-ttu-id="8e2fd-249">SN=medsvr-pool.contoso.net; SAN=medsvr-pool.contoso.net; SAN=medsvr01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="8e2fd-249">SN=medsvr-pool.contoso.net; SAN=medsvr-pool.contoso.net; SAN=medsvr01.contoso.net</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-survivable-branch-appliance"></a><span data-ttu-id="8e2fd-250">Certificats pour l’appareil de branchement survivant</span><span class="sxs-lookup"><span data-stu-id="8e2fd-250">Certificates for Survivable Branch Appliance</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8e2fd-251">Certificat</span><span class="sxs-lookup"><span data-stu-id="8e2fd-251">Certificate</span></span></th>
<th><span data-ttu-id="8e2fd-252">Nom de l’objet/nom usuel</span><span class="sxs-lookup"><span data-stu-id="8e2fd-252">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="8e2fd-253">Autre nom du sujet</span><span class="sxs-lookup"><span data-stu-id="8e2fd-253">Subject alternative name</span></span></th>
<th><span data-ttu-id="8e2fd-254">Exemple</span><span class="sxs-lookup"><span data-stu-id="8e2fd-254">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8e2fd-255">Par défaut</span><span class="sxs-lookup"><span data-stu-id="8e2fd-255">Default</span></span></p></td>
<td><p><span data-ttu-id="8e2fd-256">Nom de domaine complet de l’appareil</span><span class="sxs-lookup"><span data-stu-id="8e2fd-256">FQDN of the appliance</span></span></p></td>
<td><p><span data-ttu-id="8e2fd-257">SIP. &lt;sipdomain&gt; (nécessite une entrée par domaine SIP)</span><span class="sxs-lookup"><span data-stu-id="8e2fd-257">SIP.&lt;sipdomain&gt; (need one entry per SIP domain)</span></span></p></td>
<td><p><span data-ttu-id="8e2fd-258">SN=sba01.contoso.net; SAN=sip.contoso.com; SAN=sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="8e2fd-258">SN=sba01.contoso.net; SAN=sip.contoso.com; SAN=sip.fabrikam.com</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="8e2fd-259">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8e2fd-259">See Also</span></span>


[<span data-ttu-id="8e2fd-260">Prise en charge des certificats comportant des caractères génériques dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8e2fd-260">Wildcard certificate support in Lync Server 2013</span></span>](lync-server-2013-wildcard-certificate-support.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

