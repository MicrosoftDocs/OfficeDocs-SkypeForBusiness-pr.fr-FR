---
title: 'Lync Server 2013 : Configuration des services Internet (IIS)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IIS configuration
ms:assetid: b458babf-bf64-43f0-8a8e-612f5096b63c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412871(v=OCS.15)
ms:contentKeyID: 48185169
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0cb8fe023d872ff19e29beb329488304048895b2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729324"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="iis-configuration-in-lync-server-2013"></a><span data-ttu-id="134bc-102">Configuration des services Internet (IIS) dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="134bc-102">IIS configuration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="134bc-103">_**Dernière modification de la rubrique :** 2014-02-17_</span><span class="sxs-lookup"><span data-stu-id="134bc-103">_**Topic Last Modified:** 2014-02-17_</span></span>

<span data-ttu-id="134bc-104">Pour effectuer cette procédure, vous devez être connecté au serveur au minimum en tant qu’administrateur local et utilisateur de domaine.</span><span class="sxs-lookup"><span data-stu-id="134bc-104">To successfully complete this procedure, you should be logged on to the server minimally as a local administrator and a domain user.</span></span>

<span data-ttu-id="134bc-105">Avant de configurer et d’installer le serveur frontal pour Lync Server 2013, Standard Edition ou le premier serveur frontal d’un pool, vous installez et configurez le rôle de serveur et les services Web pour Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="134bc-105">Before you configure and install the Front End Server for Lync Server 2013, Standard Edition or the first Front End Server in a pool, you install and configure the server role and Web Services for Internet Information Services (IIS).</span></span>

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="134bc-106">Si votre organisation nécessite que vous localisiez IIS et tous les services Web sur un lecteur autre que le lecteur système, vous pouvez modifier le chemin d’accès d’installation pour les fichiers Lync Server 2013 dans la boîte de dialogue de configuration lors de l’installation initiale de Lync Server 2013 Outils d’administration.</span><span class="sxs-lookup"><span data-stu-id="134bc-106">If your organization requires that you locate IIS and all Web Services on a drive other than the system drive, you can change the installation location path for the Lync Server 2013 files in the Setup dialog box when you initially install the Lync Server 2013 Administrative tools.</span></span> <span data-ttu-id="134bc-107">Vous installez les outils d’administration avant d’installer IIS.</span><span class="sxs-lookup"><span data-stu-id="134bc-107">You install the Administrative tools before installing IIS.</span></span> <span data-ttu-id="134bc-108">Si vous installez les fichiers d’installation dans ce chemin d’accès, y compris OCSCore. msi, les autres fichiers Lync Server 2013 sont déployés également sur ce lecteur.</span><span class="sxs-lookup"><span data-stu-id="134bc-108">If you install the Setup files to this path, including OCSCore.msi, the rest of the Lync Server 2013 files will be deployed to this drive as well.</span></span> <span data-ttu-id="134bc-109">Pour dtails, voir <A href="lync-server-2013-install-lync-server-administrative-tools.md">installer les outils d’administration de Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="134bc-109">For dtails, see <A href="lync-server-2013-install-lync-server-administrative-tools.md">Install Lync Server 2013 administrative tools</A>.</span></span> <span data-ttu-id="134bc-110">Pour plus d’informations sur la façon de déplacer le INETPUB déployé par Windows Server Manager lors de l' <A href="http://go.microsoft.com/fwlink/p/?linkid=216888">http://go.microsoft.com/fwlink/p/?linkId=216888</A>installation d’IIS, voir.</span><span class="sxs-lookup"><span data-stu-id="134bc-110">For details about how to relocate the INETPUB deployed by Windows Server Manager when installing IIS, see <A href="http://go.microsoft.com/fwlink/p/?linkid=216888">http://go.microsoft.com/fwlink/p/?linkId=216888</A>.</span></span>



</div>

<span data-ttu-id="134bc-111">Le tableau suivant indique les services de rôles IIS 7,5 requis.</span><span class="sxs-lookup"><span data-stu-id="134bc-111">The following table indicates the required IIS 7.5 role services.</span></span>

### <a name="iis-75-role-services"></a><span data-ttu-id="134bc-112">Services de rôle 7,5 IIS</span><span class="sxs-lookup"><span data-stu-id="134bc-112">IIS 7.5 Role Services</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="134bc-113">Titre du rôle</span><span class="sxs-lookup"><span data-stu-id="134bc-113">Role Heading</span></span></th>
<th><span data-ttu-id="134bc-114">Service de rôle</span><span class="sxs-lookup"><span data-stu-id="134bc-114">Role Service</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="134bc-115">Fonctionnalités HTTP communes installées</span><span class="sxs-lookup"><span data-stu-id="134bc-115">Common HTTP features installed</span></span></p></td>
<td><p><span data-ttu-id="134bc-116">Contenu statique</span><span class="sxs-lookup"><span data-stu-id="134bc-116">Static content</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="134bc-117">Fonctionnalités HTTP communes installées</span><span class="sxs-lookup"><span data-stu-id="134bc-117">Common HTTP features installed</span></span></p></td>
<td><p><span data-ttu-id="134bc-118">Document par défaut</span><span class="sxs-lookup"><span data-stu-id="134bc-118">Default document</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="134bc-119">Fonctionnalités HTTP communes installées</span><span class="sxs-lookup"><span data-stu-id="134bc-119">Common HTTP features installed</span></span></p></td>
<td><p><span data-ttu-id="134bc-120">Erreurs HTTP</span><span class="sxs-lookup"><span data-stu-id="134bc-120">HTTP errors</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="134bc-121">Développement d’applications</span><span class="sxs-lookup"><span data-stu-id="134bc-121">Application development</span></span></p></td>
<td><p><span data-ttu-id="134bc-122">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="134bc-122">ASP.NET</span></span></p>
<p><span data-ttu-id="134bc-123">Windows Server 2012 nécessite également ASP. NET 4.5</span><span class="sxs-lookup"><span data-stu-id="134bc-123">Windows Server 2012 also requires ASP.NET4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="134bc-124">Développement d’applications</span><span class="sxs-lookup"><span data-stu-id="134bc-124">Application development</span></span></p></td>
<td><p><span data-ttu-id="134bc-125">Extensibilité .NET</span><span class="sxs-lookup"><span data-stu-id="134bc-125">.NET extensibility</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="134bc-126">Développement d’applications</span><span class="sxs-lookup"><span data-stu-id="134bc-126">Application development</span></span></p></td>
<td><p><span data-ttu-id="134bc-127">Extensions ISAPI (Internet Server API)</span><span class="sxs-lookup"><span data-stu-id="134bc-127">Internet Server API (ISAPI) extensions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="134bc-128">Développement d’applications</span><span class="sxs-lookup"><span data-stu-id="134bc-128">Application development</span></span></p></td>
<td><p><span data-ttu-id="134bc-129">Filtres ISAPI</span><span class="sxs-lookup"><span data-stu-id="134bc-129">ISAPI filters</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="134bc-130">État d’intégrité et diagnostics</span><span class="sxs-lookup"><span data-stu-id="134bc-130">Health and diagnostics</span></span></p></td>
<td><p><span data-ttu-id="134bc-131">Journalisation HTTP</span><span class="sxs-lookup"><span data-stu-id="134bc-131">HTTP logging</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="134bc-132">État d’intégrité et diagnostics</span><span class="sxs-lookup"><span data-stu-id="134bc-132">Health and diagnostics</span></span></p></td>
<td><p><span data-ttu-id="134bc-133">Outils de journalisation</span><span class="sxs-lookup"><span data-stu-id="134bc-133">Logging tools</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="134bc-134">État d’intégrité et diagnostics</span><span class="sxs-lookup"><span data-stu-id="134bc-134">Health and diagnostics</span></span></p></td>
<td><p><span data-ttu-id="134bc-135">Suivi</span><span class="sxs-lookup"><span data-stu-id="134bc-135">Tracing</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="134bc-136">Sécurité</span><span class="sxs-lookup"><span data-stu-id="134bc-136">Security</span></span></p></td>
<td><p><span data-ttu-id="134bc-137">Authentification anonyme (installée et activée par défaut)</span><span class="sxs-lookup"><span data-stu-id="134bc-137">Anonymous authentication (installed and enabled by default)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="134bc-138">Sécurité</span><span class="sxs-lookup"><span data-stu-id="134bc-138">Security</span></span></p></td>
<td><p><span data-ttu-id="134bc-139">Authentification Windows</span><span class="sxs-lookup"><span data-stu-id="134bc-139">Windows authentication</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="134bc-140">Sécurité</span><span class="sxs-lookup"><span data-stu-id="134bc-140">Security</span></span></p></td>
<td><p><span data-ttu-id="134bc-141">Authentification du mappage de certificat client</span><span class="sxs-lookup"><span data-stu-id="134bc-141">Client Certificate Mapping authentication</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="134bc-142">Sécurité</span><span class="sxs-lookup"><span data-stu-id="134bc-142">Security</span></span></p></td>
<td><p><span data-ttu-id="134bc-143">Filtrage de requête</span><span class="sxs-lookup"><span data-stu-id="134bc-143">Request filtering</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="134bc-144">Performances</span><span class="sxs-lookup"><span data-stu-id="134bc-144">Performance</span></span></p></td>
<td><p><span data-ttu-id="134bc-145">Compression de contenu statique</span><span class="sxs-lookup"><span data-stu-id="134bc-145">Static content compression</span></span></p>
<p><span data-ttu-id="134bc-146">Compression de contenu dynamique</span><span class="sxs-lookup"><span data-stu-id="134bc-146">Dynamic content compression</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="134bc-147">Outils de gestion</span><span class="sxs-lookup"><span data-stu-id="134bc-147">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="134bc-148">Console de gestion des services Internet (IIS)</span><span class="sxs-lookup"><span data-stu-id="134bc-148">IIS Management Console</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="134bc-149">Outils de gestion</span><span class="sxs-lookup"><span data-stu-id="134bc-149">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="134bc-150">Scripts et outils de gestion des services Internet (IIS)</span><span class="sxs-lookup"><span data-stu-id="134bc-150">IIS Management Scripts and Tools</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="134bc-151">Sur le système d’exploitation Windows Server 2008 R2 SP1 x64, vous pouvez utiliser Windows PowerShell 2,0.</span><span class="sxs-lookup"><span data-stu-id="134bc-151">On the Windows Server 2008 R2 SP1 x64 operating system, you can use Windows PowerShell 2.0.</span></span> <span data-ttu-id="134bc-152">Vous devez d’abord importer le module ServerManager, puis installer les services de rôles et de rôles IIS 7,5.</span><span class="sxs-lookup"><span data-stu-id="134bc-152">You must first import the ServerManager module, and then install the IIS 7.5 role and role services.</span></span>

   ```PowerShell
    Import-Module ServerManager
   ```

   ```PowerShell
    Add-WindowsFeature Web-Server, Web-Static-Content, Web-Default-Doc, Web-Scripting-Tools, Web-Windows-Auth, Web-Asp-Net, Web-Log-Libraries, Web-Http-Tracing, Web-Stat-Compression, Web-Dyn-Compression, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Errors, Web-Http-Logging, Web-Net-Ext, Web-Client-Auth, Web-Filtering, Web-Mgmt-Console
   ```

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="134bc-153">L’authentification anonyme est installée par défaut avec le rôle serveur IIS.</span><span class="sxs-lookup"><span data-stu-id="134bc-153">Anonymous authentication is installed by default with the IIS server role.</span></span> <span data-ttu-id="134bc-154">Vous pouvez gérer l’authentification anonyme après l’installation d’IIS.</span><span class="sxs-lookup"><span data-stu-id="134bc-154">You can manage anonymous authentication after the installation of IIS.</span></span> <span data-ttu-id="134bc-155">Pour en savoir plus, voir Activer l’authentification anonyme (IIS 7) <A href="http://go.microsoft.com/fwlink/p/?linkid=203935">http://go.microsoft.com/fwlink/p/?linkId=203935</A>.</span><span class="sxs-lookup"><span data-stu-id="134bc-155">For details, see “Enable Anonymous Authentication (IIS 7)” at <A href="http://go.microsoft.com/fwlink/p/?linkid=203935">http://go.microsoft.com/fwlink/p/?linkId=203935</A>.</span></span>



</div>

<span data-ttu-id="134bc-156">Le tableau suivant indique les services de rôles IIS 8,0 et IIS 8,5 requis pour Windows Server 2012 et Windows Server 2012 R2.</span><span class="sxs-lookup"><span data-stu-id="134bc-156">The following table indicates the required IIS 8.0 and IIS 8.5 role services for Windows Server 2012 and Windows Server 2012 R2.</span></span>

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="134bc-157">Pour Windows Server 2012 et Windows Server 2012 R2, l’applet de la cmdlet Add-WindowsFeature a été remplacée par l’applet de passe install-WindowsFeature.</span><span class="sxs-lookup"><span data-stu-id="134bc-157">For Windows Server 2012 and Windows Server 2012 R2, the Add-WindowsFeature cmdlet has been replaced by the Install-WindowsFeature cmdlet.</span></span> <span data-ttu-id="134bc-158">Pour plus d’informations, consultez la rubrique <A href="http://go.microsoft.com/fwlink/p/?linkid=392274">installer-WindowsFeature</A>.</span><span class="sxs-lookup"><span data-stu-id="134bc-158">For details, see <A href="http://go.microsoft.com/fwlink/p/?linkid=392274">Install-WindowsFeature</A>.</span></span>



</div>

### <a name="iis-80-and-iis-85-role-services"></a><span data-ttu-id="134bc-159">Services de rôle IIS 8,0 et IIS 8,5</span><span class="sxs-lookup"><span data-stu-id="134bc-159">IIS 8.0 and IIS 8.5 Role Services</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="134bc-160">Titre du rôle</span><span class="sxs-lookup"><span data-stu-id="134bc-160">Role Heading</span></span></th>
<th><span data-ttu-id="134bc-161">Service de rôle</span><span class="sxs-lookup"><span data-stu-id="134bc-161">Role Service</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="134bc-162">Serveur Web (IIS)</span><span class="sxs-lookup"><span data-stu-id="134bc-162">Web Server (IIS)</span></span></p></td>
<td><p><span data-ttu-id="134bc-163">Serveur Web</span><span class="sxs-lookup"><span data-stu-id="134bc-163">Web Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="134bc-164">Fonctionnalités HTTP communes</span><span class="sxs-lookup"><span data-stu-id="134bc-164">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="134bc-165">Document par défaut</span><span class="sxs-lookup"><span data-stu-id="134bc-165">Default Document</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="134bc-166">Fonctionnalités HTTP communes</span><span class="sxs-lookup"><span data-stu-id="134bc-166">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="134bc-167">Exploration des répertoires</span><span class="sxs-lookup"><span data-stu-id="134bc-167">Directory Browsing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="134bc-168">Fonctionnalités HTTP communes</span><span class="sxs-lookup"><span data-stu-id="134bc-168">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="134bc-169">Erreurs HTTP</span><span class="sxs-lookup"><span data-stu-id="134bc-169">HTTP Errors</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="134bc-170">Fonctionnalités HTTP communes</span><span class="sxs-lookup"><span data-stu-id="134bc-170">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="134bc-171">Contenu statique</span><span class="sxs-lookup"><span data-stu-id="134bc-171">Static content</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="134bc-172">Fonctionnalités HTTP communes</span><span class="sxs-lookup"><span data-stu-id="134bc-172">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="134bc-173">Redirection HTTP</span><span class="sxs-lookup"><span data-stu-id="134bc-173">HTTP Redirection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="134bc-174">Intégrité et diagnostics</span><span class="sxs-lookup"><span data-stu-id="134bc-174">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="134bc-175">Journalisation HTTP</span><span class="sxs-lookup"><span data-stu-id="134bc-175">HTTP Logging</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="134bc-176">Intégrité et diagnostics</span><span class="sxs-lookup"><span data-stu-id="134bc-176">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="134bc-177">Outils de journalisation</span><span class="sxs-lookup"><span data-stu-id="134bc-177">Logging Tools</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="134bc-178">Intégrité et diagnostics</span><span class="sxs-lookup"><span data-stu-id="134bc-178">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="134bc-179">Moniteur de requête</span><span class="sxs-lookup"><span data-stu-id="134bc-179">Request Monitor</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="134bc-180">Intégrité et diagnostics</span><span class="sxs-lookup"><span data-stu-id="134bc-180">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="134bc-181">Suivi</span><span class="sxs-lookup"><span data-stu-id="134bc-181">Tracing</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="134bc-182">Sécurité</span><span class="sxs-lookup"><span data-stu-id="134bc-182">Security</span></span></p></td>
<td><p><span data-ttu-id="134bc-183">Filtrage des demandes</span><span class="sxs-lookup"><span data-stu-id="134bc-183">Request Filtering</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="134bc-184">Sécurité</span><span class="sxs-lookup"><span data-stu-id="134bc-184">Security</span></span></p></td>
<td><p><span data-ttu-id="134bc-185">Authentification de base</span><span class="sxs-lookup"><span data-stu-id="134bc-185">Basic Authentication</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="134bc-186">Sécurité</span><span class="sxs-lookup"><span data-stu-id="134bc-186">Security</span></span></p></td>
<td><p><span data-ttu-id="134bc-187">Authentification par mappage de certificat client</span><span class="sxs-lookup"><span data-stu-id="134bc-187">Client Certificate Mapping Authentication</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="134bc-188">Sécurité</span><span class="sxs-lookup"><span data-stu-id="134bc-188">Security</span></span></p></td>
<td><p><span data-ttu-id="134bc-189">Authentification Windows</span><span class="sxs-lookup"><span data-stu-id="134bc-189">Windows Authentication</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="134bc-190">Développement d’applications</span><span class="sxs-lookup"><span data-stu-id="134bc-190">Application Development</span></span></p></td>
<td><p><span data-ttu-id="134bc-191">Extensibilité .net 3,5</span><span class="sxs-lookup"><span data-stu-id="134bc-191">.Net Extensibility 3.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="134bc-192">Développement d’applications</span><span class="sxs-lookup"><span data-stu-id="134bc-192">Application Development</span></span></p></td>
<td><p><span data-ttu-id="134bc-193">Extensibilité .net 4,5</span><span class="sxs-lookup"><span data-stu-id="134bc-193">.Net Extensibility 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="134bc-194">Développement d’applications</span><span class="sxs-lookup"><span data-stu-id="134bc-194">Application Development</span></span></p></td>
<td><p><span data-ttu-id="134bc-195">ASP.Net 3,5</span><span class="sxs-lookup"><span data-stu-id="134bc-195">ASP.Net 3.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="134bc-196">Développement d’applications</span><span class="sxs-lookup"><span data-stu-id="134bc-196">Application Development</span></span></p></td>
<td><p><span data-ttu-id="134bc-197">ASP.Net 4,5</span><span class="sxs-lookup"><span data-stu-id="134bc-197">ASP.Net 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="134bc-198">Développement d’applications</span><span class="sxs-lookup"><span data-stu-id="134bc-198">Application Development</span></span></p></td>
<td><p><span data-ttu-id="134bc-199">Extensions ISAPI</span><span class="sxs-lookup"><span data-stu-id="134bc-199">ISAPI Extensions</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="134bc-200">Développement d’applications</span><span class="sxs-lookup"><span data-stu-id="134bc-200">Application Development</span></span></p></td>
<td><p><span data-ttu-id="134bc-201">Filtres ISAPI</span><span class="sxs-lookup"><span data-stu-id="134bc-201">ISAPI Filters</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="134bc-202">Développement d’applications</span><span class="sxs-lookup"><span data-stu-id="134bc-202">Application Development</span></span></p></td>
<td><p><span data-ttu-id="134bc-203">Inclusions côté serveur</span><span class="sxs-lookup"><span data-stu-id="134bc-203">Server Side Includes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="134bc-204">Outils de gestion</span><span class="sxs-lookup"><span data-stu-id="134bc-204">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="134bc-205">Console de gestion des services Internet (IIS)</span><span class="sxs-lookup"><span data-stu-id="134bc-205">IIS Management Console</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="134bc-206">Outils de gestion</span><span class="sxs-lookup"><span data-stu-id="134bc-206">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="134bc-207">Compatibilité de la métabase IIS 6</span><span class="sxs-lookup"><span data-stu-id="134bc-207">IIS 6 Metabase compatibility</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="134bc-208">Outils de gestion</span><span class="sxs-lookup"><span data-stu-id="134bc-208">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="134bc-209">Scripts et outils de gestion des services Internet (IIS)</span><span class="sxs-lookup"><span data-stu-id="134bc-209">IIS Management Scripts and Tools</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="134bc-210">Fonctionnalités d’infrastructure .net 3,5</span><span class="sxs-lookup"><span data-stu-id="134bc-210">.Net 3.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="134bc-211">.Net 3,5 Framework</span><span class="sxs-lookup"><span data-stu-id="134bc-211">.Net 3.5 Framework</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="134bc-212">Fonctionnalités d’infrastructure .net 4,5</span><span class="sxs-lookup"><span data-stu-id="134bc-212">.Net 4.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="134bc-213">.NET Framework 4,5</span><span class="sxs-lookup"><span data-stu-id="134bc-213">.Net Framework 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="134bc-214">Fonctionnalités d’infrastructure .net 4,5</span><span class="sxs-lookup"><span data-stu-id="134bc-214">.Net 4.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="134bc-215">ASP.Net 4,5</span><span class="sxs-lookup"><span data-stu-id="134bc-215">ASP.Net 4.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="134bc-216">Fonctionnalités d’infrastructure .net 4,5</span><span class="sxs-lookup"><span data-stu-id="134bc-216">.Net 4.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="134bc-217">Activation HTTP</span><span class="sxs-lookup"><span data-stu-id="134bc-217">HTTP Activation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="134bc-218">Fonctionnalités d’infrastructure .net 4,5</span><span class="sxs-lookup"><span data-stu-id="134bc-218">.Net 4.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="134bc-219">Partage de port TCP</span><span class="sxs-lookup"><span data-stu-id="134bc-219">TCP Port Sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="134bc-220">Service de transfert intelligent en arrière-plan</span><span class="sxs-lookup"><span data-stu-id="134bc-220">Background Intelligent Transfer Service</span></span></p></td>
<td><p><span data-ttu-id="134bc-221">Extensions serveur IIS</span><span class="sxs-lookup"><span data-stu-id="134bc-221">IIS Server Extensions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="134bc-222">Services d’entrée manuscrite</span><span class="sxs-lookup"><span data-stu-id="134bc-222">Ink and Handwriting Services</span></span></p></td>
<td><p><span data-ttu-id="134bc-223">Services d’entrée manuscrite</span><span class="sxs-lookup"><span data-stu-id="134bc-223">Ink and Handwriting Services</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="134bc-224">Media Foundation</span><span class="sxs-lookup"><span data-stu-id="134bc-224">Media Foundation</span></span></p></td>
<td><p><span data-ttu-id="134bc-225">Media Foundation</span><span class="sxs-lookup"><span data-stu-id="134bc-225">Media Foundation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="134bc-226">Interfaces utilisateur et infrastructure</span><span class="sxs-lookup"><span data-stu-id="134bc-226">User Interfaces and Infrastructure</span></span></p></td>
<td><p><span data-ttu-id="134bc-227">Outils et infrastructure de gestion graphique</span><span class="sxs-lookup"><span data-stu-id="134bc-227">Graphical Management Tools and Infrastructure</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="134bc-228">Interfaces utilisateur et infrastructure</span><span class="sxs-lookup"><span data-stu-id="134bc-228">User Interfaces and Infrastructure</span></span></p></td>
<td><p><span data-ttu-id="134bc-229">Expérience de bureau</span><span class="sxs-lookup"><span data-stu-id="134bc-229">Desktop Experience</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="134bc-230">Interfaces utilisateur et infrastructure</span><span class="sxs-lookup"><span data-stu-id="134bc-230">User Interfaces and Infrastructure</span></span></p></td>
<td><p><span data-ttu-id="134bc-231">Shell graphique serveur</span><span class="sxs-lookup"><span data-stu-id="134bc-231">Server Graphical Shell</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="134bc-232">Windows Identity Foundation 3.5</span><span class="sxs-lookup"><span data-stu-id="134bc-232">Windows Identity Foundation 3.5</span></span></p></td>
<td><p><span data-ttu-id="134bc-233">Windows Identity Foundation 3.5</span><span class="sxs-lookup"><span data-stu-id="134bc-233">Windows Identity Foundation 3.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="134bc-234">Service d’activation de processus Windows</span><span class="sxs-lookup"><span data-stu-id="134bc-234">Windows Process Activation Service</span></span></p></td>
<td><p><span data-ttu-id="134bc-235">Modèle de processus</span><span class="sxs-lookup"><span data-stu-id="134bc-235">Process Model</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="134bc-236">Service d’activation de processus Windows</span><span class="sxs-lookup"><span data-stu-id="134bc-236">Windows Process Activation Service</span></span></p></td>
<td><p><span data-ttu-id="134bc-237">API de configuration</span><span class="sxs-lookup"><span data-stu-id="134bc-237">Configuration APIs</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="134bc-238">Dans Windows Server 2012 et Windows Server 2012 R2, vous pouvez utiliser Windows PowerShell 3,0 pour installer la configuration requise pour les services Internet (IIS).</span><span class="sxs-lookup"><span data-stu-id="134bc-238">In Windows Server 2012 and Windows Server 2012 R2, you can use Windows PowerShell 3.0 to install the IIS Requirements.</span></span> <span data-ttu-id="134bc-239">À l’aide du module ServerManager dans Windows PowerShell 3,0, tapez :</span><span class="sxs-lookup"><span data-stu-id="134bc-239">Using the ServerManager module in Windows PowerShell 3.0, type:</span></span>

   ```PowerShell
    Import-Module ServerManager
   ```

   ```PowerShell
    Add-WindowsFeature Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-Framework-45-Core, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Console, Web-Mgmt-Compat, Windows-Identity-Foundation, Server-Media-Foundation, BITS -Source D:\sources\sxs
   ```

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="134bc-240">Une nouveauté de Windows Server 2012 est le paramètre – source qui définit l’emplacement où se trouve le média source de Windows Server 2012.</span><span class="sxs-lookup"><span data-stu-id="134bc-240">New with Windows Server 2012 is the –Source parameter that defines where the Windows Server 2012 source media can be found.</span></span> <span data-ttu-id="134bc-241">Le média peut être défini comme lecteur DVD (par exemple, D:\Sources\Sxs) ou sur un partage réseau pour lequel les fichiers multimédias ont été copiés (par exemple \\, fileserver\windows2012\sources\Sxs).</span><span class="sxs-lookup"><span data-stu-id="134bc-241">The media can be defined as a DVD drive (for example, D:\Sources\Sxs), or to a network share that the media files have been copied (for example, \\fileserver\windows2012\sources\Sxs).</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="134bc-242">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="134bc-242">See Also</span></span>


[<span data-ttu-id="134bc-243">Configuration requise pour les services Internet (IIS) pour les pools frontaux et les serveurs Standard Edition dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="134bc-243">IIS requirements for Front End pools and Standard Edition servers in Lync Server 2013</span></span>](lync-server-2013-iis-requirements-for-front-end-pools-and-standard-edition-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

