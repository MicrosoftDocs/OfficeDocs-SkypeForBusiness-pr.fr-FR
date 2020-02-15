---
title: Configuration requise pour les services Internet (IIS) pour les pools frontaux et les serveurs Standard Edition
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IIS requirements for Front End pools and Standard Edition servers
ms:assetid: e8a6c7ac-b6d5-4c7e-abe9-d8ea5eedbc62
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399038(v=OCS.15)
ms:contentKeyID: 48185888
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bc92cc4c27f7af395a8e41bec26679a27010562d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037866"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="iis-requirements-for-front-end-pools-and-standard-edition-servers-in-lync-server-2013"></a><span data-ttu-id="c6612-102">Configuration requise pour les services Internet (IIS) pour les pools frontaux et les serveurs Standard Edition dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c6612-102">IIS requirements for Front End pools and Standard Edition servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c6612-103">_**Dernière modification de la rubrique :** 2012-06-19_</span><span class="sxs-lookup"><span data-stu-id="c6612-103">_**Topic Last Modified:** 2012-06-19_</span></span>

<span data-ttu-id="c6612-104">Pour les serveurs Standard Edition et les serveurs frontaux et les directeurs, le programme d’installation de Lync Server 2013 crée des répertoires virtuels dans les services Internet (IIS) aux fins suivantes :</span><span class="sxs-lookup"><span data-stu-id="c6612-104">For Standard Edition servers and Front End Servers, and Directors, the Lync Server 2013 installer creates virtual directories in Internet Information Services (IIS) for the following purposes:</span></span>

  - <span data-ttu-id="c6612-105">permettre aux utilisateurs de télécharger des fichiers du service de carnet d’adresses ;</span><span class="sxs-lookup"><span data-stu-id="c6612-105">To enable users to download files from the Address Book Service</span></span>

  - <span data-ttu-id="c6612-106">Pour permettre aux clients d’obtenir des mises à jour</span><span class="sxs-lookup"><span data-stu-id="c6612-106">To enable clients to obtain updates</span></span>

  - <span data-ttu-id="c6612-107">activer les conférences ;</span><span class="sxs-lookup"><span data-stu-id="c6612-107">To enable conferencing</span></span>

  - <span data-ttu-id="c6612-108">permettre aux utilisateurs de télécharger le contenu de réunions ;</span><span class="sxs-lookup"><span data-stu-id="c6612-108">To enable users to download meeting content</span></span>

  - <span data-ttu-id="c6612-109">permettre aux utilisateurs de développer des groupes de distribution ;</span><span class="sxs-lookup"><span data-stu-id="c6612-109">To enable users to expand distribution groups</span></span>

  - <span data-ttu-id="c6612-110">activer la téléconférence ;</span><span class="sxs-lookup"><span data-stu-id="c6612-110">To enable phone conferencing</span></span>

  - <span data-ttu-id="c6612-111">activer les fonctionnalités du service Response Group.</span><span class="sxs-lookup"><span data-stu-id="c6612-111">To enable response group features</span></span>

<span data-ttu-id="c6612-112">En outre, la mise à jour cumulative de Lync Server 2010 : novembre 2011 installer crée des répertoires virtuels dans les services Internet (IIS) dans les buts suivants :</span><span class="sxs-lookup"><span data-stu-id="c6612-112">In addition, the cumulative update for Lync Server 2010: November 2011 installer creates virtual directories in IIS for the following purposes:</span></span>

  - <span data-ttu-id="c6612-113">Sur les serveurs frontaux ou les serveurs Standard Edition pour prendre en charge la fonctionnalité de mobilité, telle que la messagerie instantanée et la présence, sur les appareils mobiles</span><span class="sxs-lookup"><span data-stu-id="c6612-113">On Front End Servers or Standard Edition servers to support mobility functionality, such as instant messaging (IM) and presence, on mobile devices</span></span>

  - <span data-ttu-id="c6612-114">Sur les serveurs frontaux ou Standard Edition et sur les directeurs pour permettre aux appareils mobiles de découvrir automatiquement les ressources de mobilité</span><span class="sxs-lookup"><span data-stu-id="c6612-114">On Front End Servers or Standard Edition servers and on Directors to enable mobile devices to automatically discover mobility resources</span></span>



> [!NOTE]
> <span data-ttu-id="c6612-115">Si vous déployez la mobilité, nous vous recommandons d’utiliser les services Internet (IIS) 7.5.</span><span class="sxs-lookup"><span data-stu-id="c6612-115">If you are deploying mobility, we recommend that you use IIS 7.5.</span></span> <span data-ttu-id="c6612-116">Le programme d’installation de Lync Server Mobility service définit certains indicateurs ASP.NET pour améliorer les performances.</span><span class="sxs-lookup"><span data-stu-id="c6612-116">The Lync Server Mobility Service installer sets some ASP.NET flags to improve performance.</span></span> <span data-ttu-id="c6612-117">Les services Internet (IIS) 7.5 sont installés par défaut sur Windows Server 2008 R2 et le programme d’installation du service de mobilité modifie automatiquement les paramètres ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="c6612-117">IIS 7.5 is installed by default on Windows Server 2008 R2, and the Mobility Service installer automatically changes the ASP.NET settings.</span></span> <span data-ttu-id="c6612-118">Si vous utilisez les services Internet (IIS) 7.0 sur Windows Server 2008, vous devez modifier manuellement ces paramètres.</span><span class="sxs-lookup"><span data-stu-id="c6612-118">If you use IIS 7.0 on Windows Server 2008, you need to manually change these settings.</span></span>



<span data-ttu-id="c6612-119">Lync Server nécessite l’installation des modules IIS suivants :</span><span class="sxs-lookup"><span data-stu-id="c6612-119">Lync Server requires the following IIS modules to be installed:</span></span>


> [!IMPORTANT]
> <span data-ttu-id="c6612-120">Si votre organisation exige que vous localisiez les services Internet (IIS) et tous les services Web sur un lecteur autre que le lecteur système, vous pouvez modifier le chemin d’accès de l’emplacement d’installation des fichiers Lync Server dans la boîte de dialogue de configuration.</span><span class="sxs-lookup"><span data-stu-id="c6612-120">If your organization requires that you locate IIS and all Web Services on a drive other than the system drive, you can change the installation location path for the Lync Server files in the Setup dialog box.</span></span> <span data-ttu-id="c6612-121">Si vous installez les fichiers d’installation dans ce chemin d’accès, y compris OCSCore. msi, les autres fichiers Lync Server seront également déployés sur ce lecteur.</span><span class="sxs-lookup"><span data-stu-id="c6612-121">If you install the Setup files to this path, including OCSCore.msi, the rest of the Lync Server files will be deployed to this drive as well.</span></span> <span data-ttu-id="c6612-122">Pour plus d’informations sur la façon de déplacer le INETPUB déployé par le gestionnaire Windows Server lors de <A href="http://go.microsoft.com/fwlink/p/?linkid=216888">http://go.microsoft.com/fwlink/p/?linkId=216888</A>l’installation d’IIS, reportez-vous à la rubrique.</span><span class="sxs-lookup"><span data-stu-id="c6612-122">For details about how to relocate the INETPUB deployed by Windows Server Manager when installing IIS, see <A href="http://go.microsoft.com/fwlink/p/?linkid=216888">http://go.microsoft.com/fwlink/p/?linkId=216888</A>.</span></span>


  - <span data-ttu-id="c6612-123">Contenu statique</span><span class="sxs-lookup"><span data-stu-id="c6612-123">Static Content</span></span>

  - <span data-ttu-id="c6612-124">Document par défaut</span><span class="sxs-lookup"><span data-stu-id="c6612-124">Default Document</span></span>

  - <span data-ttu-id="c6612-125">Erreurs HTTP</span><span class="sxs-lookup"><span data-stu-id="c6612-125">HTTP Errors</span></span>

  - <span data-ttu-id="c6612-126">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="c6612-126">ASP.NET</span></span>

  - <span data-ttu-id="c6612-127">Extensibilité .NET</span><span class="sxs-lookup"><span data-stu-id="c6612-127">.NET Extensibility</span></span>

  - <span data-ttu-id="c6612-128">Extensions ISAPI (Internet Server API)</span><span class="sxs-lookup"><span data-stu-id="c6612-128">Internet Server API (ISAPI) Extensions</span></span>

  - <span data-ttu-id="c6612-129">Filtres ISAPI</span><span class="sxs-lookup"><span data-stu-id="c6612-129">ISAPI Filters</span></span>

  - <span data-ttu-id="c6612-130">Journalisation HTTP</span><span class="sxs-lookup"><span data-stu-id="c6612-130">HTTP Logging</span></span>

  - <span data-ttu-id="c6612-131">Outils de journalisation</span><span class="sxs-lookup"><span data-stu-id="c6612-131">Logging Tools</span></span>

  - <span data-ttu-id="c6612-132">Analyzer</span><span class="sxs-lookup"><span data-stu-id="c6612-132">Tracing</span></span>

  - <span data-ttu-id="c6612-133">Authentification Windows</span><span class="sxs-lookup"><span data-stu-id="c6612-133">Windows Authentication</span></span>

  - <span data-ttu-id="c6612-134">Filtrage des demandes</span><span class="sxs-lookup"><span data-stu-id="c6612-134">Request Filtering</span></span>

  - <span data-ttu-id="c6612-135">Compression du contenu statique</span><span class="sxs-lookup"><span data-stu-id="c6612-135">Static Content Compression</span></span>

  - <span data-ttu-id="c6612-136">Compression du contenu dynamique</span><span class="sxs-lookup"><span data-stu-id="c6612-136">Dynamic Content Compression</span></span>

  - <span data-ttu-id="c6612-137">Console de gestion IIS</span><span class="sxs-lookup"><span data-stu-id="c6612-137">IIS Management Console</span></span>

  - <span data-ttu-id="c6612-138">Scripts et outils de gestion IIS</span><span class="sxs-lookup"><span data-stu-id="c6612-138">IIS Management Scripts and Tools</span></span>

  - <span data-ttu-id="c6612-139">Authentification anonyme (installée par défaut avec IIS)</span><span class="sxs-lookup"><span data-stu-id="c6612-139">Anonymous Authentication (installed by default when IIS is installed)</span></span>

  - <span data-ttu-id="c6612-140">Authentification par mappage de certificat client</span><span class="sxs-lookup"><span data-stu-id="c6612-140">Client Certificate Mapping Authentication</span></span>

<span data-ttu-id="c6612-141">Le tableau suivant répertorie les URI des répertoires virtuels pour l’accès interne et les ressources du système de fichiers auxquelles ils se rapportent.</span><span class="sxs-lookup"><span data-stu-id="c6612-141">The following table lists the URIs for the virtual directories for internal access and the file system resources to which they refer.</span></span>

### <a name="virtual-directories-for-internal-access"></a><span data-ttu-id="c6612-142">Répertoires virtuels pour l’accès interne</span><span class="sxs-lookup"><span data-stu-id="c6612-142">Virtual Directories for Internal Access</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c6612-143">Fonctionnalité</span><span class="sxs-lookup"><span data-stu-id="c6612-143">Feature</span></span></th>
<th><span data-ttu-id="c6612-144">URI du répertoire virtuel</span><span class="sxs-lookup"><span data-stu-id="c6612-144">Virtual directory URI</span></span></th>
<th><span data-ttu-id="c6612-145">Se rapporte à</span><span class="sxs-lookup"><span data-stu-id="c6612-145">Refers to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c6612-146">Serveur de carnet d’adresses</span><span class="sxs-lookup"><span data-stu-id="c6612-146">Address Book Server</span></span></p></td>
<td><p><span data-ttu-id="c6612-147">nom&lt;de domaine&gt;complet interne https:///ABS/int/Handler</span><span class="sxs-lookup"><span data-stu-id="c6612-147">https://&lt;Internal FQDN&gt;/ABS/int/Handler</span></span></p></td>
<td><p><span data-ttu-id="c6612-148">Emplacement des fichiers téléchargés du serveur de carnet d’adresses pour les utilisateurs internes.</span><span class="sxs-lookup"><span data-stu-id="c6612-148">Location of Address Book Server download files for internal users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6612-149">Service de découverte automatique</span><span class="sxs-lookup"><span data-stu-id="c6612-149">Autodiscover Service</span></span></p></td>
<td><p><span data-ttu-id="c6612-150">nom&lt;de domaine&gt;complet interne https:///autodiscover</span><span class="sxs-lookup"><span data-stu-id="c6612-150">https://&lt;Internal FQDN&gt;/Autodiscover</span></span></p></td>
<td><p><span data-ttu-id="c6612-151">Emplacement du service de découverte automatique Lync Server qui localise les ressources de mobilité pour les utilisateurs d’appareils mobiles internes.</span><span class="sxs-lookup"><span data-stu-id="c6612-151">Location of the Lync Server Autodiscover Service that locates mobility resources for internal mobile device users.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6612-152">Mises à jour du client</span><span class="sxs-lookup"><span data-stu-id="c6612-152">Client updates</span></span></p></td>
<td><p><span data-ttu-id="c6612-153">nom&lt;de domaine&gt;complet interne http:///AutoUpdate/int</span><span class="sxs-lookup"><span data-stu-id="c6612-153">http://&lt;Internal FQDN&gt;/AutoUpdate/Int</span></span></p></td>
<td><p><span data-ttu-id="c6612-154">Emplacement des fichiers de mise à jour pour les clients internes basés sur ordinateur.</span><span class="sxs-lookup"><span data-stu-id="c6612-154">Location of update files for internal computer-based clients.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6612-155">CONF</span><span class="sxs-lookup"><span data-stu-id="c6612-155">Conf</span></span></p></td>
<td><p><span data-ttu-id="c6612-156">nom&lt;de domaine&gt;complet interne http:///conf/int</span><span class="sxs-lookup"><span data-stu-id="c6612-156">http://&lt;Internal FQDN&gt;/Conf/Int</span></span></p></td>
<td><p><span data-ttu-id="c6612-157">Emplacement des ressources de conférence pour les utilisateurs internes.</span><span class="sxs-lookup"><span data-stu-id="c6612-157">Location of conferencing resources for internal users.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6612-158">Mises à jour des périphériques</span><span class="sxs-lookup"><span data-stu-id="c6612-158">Device updates</span></span></p></td>
<td><p><span data-ttu-id="c6612-159">nom&lt;de domaine&gt;complet (FQDN) interne http:///DeviceUpdateFiles_Int</span><span class="sxs-lookup"><span data-stu-id="c6612-159">http://&lt;Internal FQDN&gt;/DeviceUpdateFiles_Int</span></span></p></td>
<td><p><span data-ttu-id="c6612-160">Emplacement des fichiers de mise à jour des appareils de communications unifiées pour les appareils de communications unifiées internes.</span><span class="sxs-lookup"><span data-stu-id="c6612-160">Location of unified communications (UC) device update files for internal UC devices.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6612-161">Satisfaire</span><span class="sxs-lookup"><span data-stu-id="c6612-161">Meeting</span></span></p></td>
<td><p><span data-ttu-id="c6612-162">nom&lt;de domaine&gt;complet interne http:///etc/place/null</span><span class="sxs-lookup"><span data-stu-id="c6612-162">http://&lt;Internal FQDN&gt;/etc/place/null</span></span></p></td>
<td><p><span data-ttu-id="c6612-163">Emplacement du contenu de réunion pour les utilisateurs internes.</span><span class="sxs-lookup"><span data-stu-id="c6612-163">Location of meeting content for internal users.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6612-164">Service de mobilité</span><span class="sxs-lookup"><span data-stu-id="c6612-164">Mobility Service</span></span></p></td>
<td><p><span data-ttu-id="c6612-165">nom&lt;de domaine&gt;complet interne https:///MCX</span><span class="sxs-lookup"><span data-stu-id="c6612-165">https://&lt;Internal FQDN&gt;/Mcx</span></span></p></td>
<td><p><span data-ttu-id="c6612-166">Emplacement des ressources du service de mobilité pour les utilisateurs d’appareils mobiles internes.</span><span class="sxs-lookup"><span data-stu-id="c6612-166">Location of Mobility Service resources for internal mobile device users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6612-167">Développement de groupes et service de requête web du carnet d’adresses</span><span class="sxs-lookup"><span data-stu-id="c6612-167">Group Expansion and Address Book Web Query service</span></span></p></td>
<td><p><span data-ttu-id="c6612-168">nom&lt;de domaine&gt;complet interne http:///GroupExpansion/int/service.asmx</span><span class="sxs-lookup"><span data-stu-id="c6612-168">http://&lt;Internal FQDN&gt;/GroupExpansion/int/service.asmx</span></span></p></td>
<td><p><span data-ttu-id="c6612-169">Emplacement du service web qui active le développement des groupes pour les utilisateurs internes.</span><span class="sxs-lookup"><span data-stu-id="c6612-169">Location of the Web service that enables group expansion for internal users.</span></span> <span data-ttu-id="c6612-170">Il s’agit également de l’emplacement du service de requête sur le Web du carnet d’adresses qui fournit des informations de liste d’adresses globales aux clients mobiles Lync mobile Microsoft Lync 2010 internes.</span><span class="sxs-lookup"><span data-stu-id="c6612-170">Also, the location of the Address Book Web Query service that provides global address list information to internal Lync Mobile Microsoft Lync 2010 Mobile clients.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6612-171">Téléconférence</span><span class="sxs-lookup"><span data-stu-id="c6612-171">Phone Conferencing</span></span></p></td>
<td><p><span data-ttu-id="c6612-172">nom&lt;de domaine&gt;complet interne http:///PhoneConferencing/int</span><span class="sxs-lookup"><span data-stu-id="c6612-172">http://&lt;Internal FQDN&gt;/PhoneConferencing/Int</span></span></p></td>
<td><p><span data-ttu-id="c6612-173">Emplacement des données de téléconférence pour les utilisateurs internes.</span><span class="sxs-lookup"><span data-stu-id="c6612-173">Location of phone conferencing data for internal users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6612-174">Mises à jour des périphériques</span><span class="sxs-lookup"><span data-stu-id="c6612-174">Device updates</span></span></p></td>
<td><p><span data-ttu-id="c6612-175">nom&lt;de domaine&gt;complet interne http:///RequestHandler</span><span class="sxs-lookup"><span data-stu-id="c6612-175">http://&lt;Internal FQDN&gt;/RequestHandler</span></span></p></td>
<td><p><span data-ttu-id="c6612-176">Emplacement du Gestionnaire des demandes du service web de mise à jour des périphériques qui permet aux appareils de communications unifiées internes de télécharger des journaux et de vérifier l’existence de mises à jour.</span><span class="sxs-lookup"><span data-stu-id="c6612-176">Location of the Device Update Web service Request Handler that enables internal UC devices to upload logs and check for updates.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6612-177">Application Response Group</span><span class="sxs-lookup"><span data-stu-id="c6612-177">Response Group application</span></span></p></td>
<td><p><span data-ttu-id="c6612-178">nom&lt;de domaine&gt;complet interne http:///RgsConfig</span><span class="sxs-lookup"><span data-stu-id="c6612-178">http://&lt;Internal FQDN&gt;/RgsConfig</span></span></p>
<p><span data-ttu-id="c6612-179">nom&lt;de domaine&gt;complet interne http:///RgsClients</span><span class="sxs-lookup"><span data-stu-id="c6612-179">http://&lt;Internal FQDN&gt;/RgsClients</span></span></p></td>
<td><p><span data-ttu-id="c6612-180">Emplacement de l’outil de configuration du service Response Group.</span><span class="sxs-lookup"><span data-stu-id="c6612-180">Location of Response Group Configuration Tool.</span></span></p></td>
</tr>
</tbody>
</table>


> [!NOTE]
> <span data-ttu-id="c6612-181">Pour les pools frontaux dans une configuration consolidée, vous devez déployer les services Internet (IIS) avant de pouvoir ajouter des serveurs au pool.</span><span class="sxs-lookup"><span data-stu-id="c6612-181">For Front End pools in a consolidated configuration, you must deploy IIS before you can add servers to the pool.</span></span>


<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="caution" alt="security" /><span data-ttu-id="c6612-183">Note de sécurité :</span><span class="sxs-lookup"><span data-stu-id="c6612-183">Security Note:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="c6612-184">Vous devez utiliser le composant logiciel enfichable d’administration IIS pour assigner le certificat utilisé par le serveur de composants web IIS.</span><span class="sxs-lookup"><span data-stu-id="c6612-184">You must use the IIS administrative snap-in to assign the certificate used by the IIS web component server.</span></span></td>
</tr>
</tbody>
</table>



</div>

<span> </span>

</div>

</div>

</div>

