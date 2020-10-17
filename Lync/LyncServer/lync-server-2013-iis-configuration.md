---
title: 'Lync Server 2013 : configuration des services Internet (IIS)'
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
ms.openlocfilehash: 1fc8895a144b4911560af8fd6a2f12d576f3ec14
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528151"
---
# <a name="iis-configuration-in-lync-server-2013"></a><span data-ttu-id="f1da0-102">Configuration des services Internet (IIS) dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f1da0-102">IIS configuration in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f1da0-103">_**Dernière modification de la rubrique :** 2014-02-17_</span><span class="sxs-lookup"><span data-stu-id="f1da0-103">_**Topic Last Modified:** 2014-02-17_</span></span>

<span data-ttu-id="f1da0-104">Pour compléter cette procédure, vous devez être connecté au serveur au minimum en tant qu’administrateur local et en tant qu’utilisateur de domaine.</span><span class="sxs-lookup"><span data-stu-id="f1da0-104">To successfully complete this procedure, you should be logged on to the server minimally as a local administrator and a domain user.</span></span>

<span data-ttu-id="f1da0-105">Avant de configurer et d’installer le serveur frontal pour Lync Server 2013, Standard Edition ou le premier serveur frontal dans un pool, vous installez et configurez le rôle serveur et les services Web pour Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="f1da0-105">Before you configure and install the Front End Server for Lync Server 2013, Standard Edition or the first Front End Server in a pool, you install and configure the server role and Web Services for Internet Information Services (IIS).</span></span>

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="f1da0-106">Si votre organisation nécessite que vous localisiez les services Internet (IIS) et tous les services Web sur un lecteur autre que le lecteur système, vous pouvez modifier le chemin d’accès de l’emplacement d’installation des fichiers Lync Server 2013 dans la boîte de dialogue Configuration lors de l’installation initiale des outils d’administration Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f1da0-106">If your organization requires that you locate IIS and all Web Services on a drive other than the system drive, you can change the installation location path for the Lync Server 2013 files in the Setup dialog box when you initially install the Lync Server 2013 Administrative tools.</span></span> <span data-ttu-id="f1da0-107">Vous devez installer ces derniers avant d’installer IIS.</span><span class="sxs-lookup"><span data-stu-id="f1da0-107">You install the Administrative tools before installing IIS.</span></span> <span data-ttu-id="f1da0-108">Si vous installez les fichiers d’installation dans ce chemin d’accès, y compris OCSCore.msi, les autres fichiers Lync Server 2013 seront également déployés sur ce lecteur.</span><span class="sxs-lookup"><span data-stu-id="f1da0-108">If you install the Setup files to this path, including OCSCore.msi, the rest of the Lync Server 2013 files will be deployed to this drive as well.</span></span> <span data-ttu-id="f1da0-109">Pour dtails, voir <A href="lync-server-2013-install-lync-server-administrative-tools.md">install Lync Server 2013 administrative Tools</A>.</span><span class="sxs-lookup"><span data-stu-id="f1da0-109">For dtails, see <A href="lync-server-2013-install-lync-server-administrative-tools.md">Install Lync Server 2013 administrative tools</A>.</span></span> <span data-ttu-id="f1da0-110">Pour plus d’informations sur la façon de déplacer le INETPUB déployé par le gestionnaire Windows Server lors de l’installation d’IIS, reportez-vous à la rubrique <A href="https://go.microsoft.com/fwlink/p/?linkid=216888">https://go.microsoft.com/fwlink/p/?linkId=216888</A> .</span><span class="sxs-lookup"><span data-stu-id="f1da0-110">For details about how to relocate the INETPUB deployed by Windows Server Manager when installing IIS, see <A href="https://go.microsoft.com/fwlink/p/?linkid=216888">https://go.microsoft.com/fwlink/p/?linkId=216888</A>.</span></span>



</div>

<span data-ttu-id="f1da0-111">Le tableau suivant indique les services de rôle IIS 7,5 requis.</span><span class="sxs-lookup"><span data-stu-id="f1da0-111">The following table indicates the required IIS 7.5 role services.</span></span>

### <a name="iis-75-role-services"></a><span data-ttu-id="f1da0-112">Services de rôle IIS 7,5</span><span class="sxs-lookup"><span data-stu-id="f1da0-112">IIS 7.5 Role Services</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f1da0-113">Titre de rôle</span><span class="sxs-lookup"><span data-stu-id="f1da0-113">Role Heading</span></span></th>
<th><span data-ttu-id="f1da0-114">Service de rôle</span><span class="sxs-lookup"><span data-stu-id="f1da0-114">Role Service</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f1da0-115">Fonctionnalités HTTP communes installées</span><span class="sxs-lookup"><span data-stu-id="f1da0-115">Common HTTP features installed</span></span></p></td>
<td><p><span data-ttu-id="f1da0-116">Contenu statique</span><span class="sxs-lookup"><span data-stu-id="f1da0-116">Static content</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1da0-117">Fonctionnalités HTTP communes installées</span><span class="sxs-lookup"><span data-stu-id="f1da0-117">Common HTTP features installed</span></span></p></td>
<td><p><span data-ttu-id="f1da0-118">Document par défaut</span><span class="sxs-lookup"><span data-stu-id="f1da0-118">Default document</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f1da0-119">Fonctionnalités HTTP communes installées</span><span class="sxs-lookup"><span data-stu-id="f1da0-119">Common HTTP features installed</span></span></p></td>
<td><p><span data-ttu-id="f1da0-120">Erreurs HTTP</span><span class="sxs-lookup"><span data-stu-id="f1da0-120">HTTP errors</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1da0-121">Développement d’applications</span><span class="sxs-lookup"><span data-stu-id="f1da0-121">Application development</span></span></p></td>
<td><p><span data-ttu-id="f1da0-122">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="f1da0-122">ASP.NET</span></span></p>
<p><span data-ttu-id="f1da0-123">ASP.NET Server 2012 nécessite également ASP. NET 4.5</span><span class="sxs-lookup"><span data-stu-id="f1da0-123">Windows Server 2012 also requires ASP.NET4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f1da0-124">Développement d’applications</span><span class="sxs-lookup"><span data-stu-id="f1da0-124">Application development</span></span></p></td>
<td><p><span data-ttu-id="f1da0-125">Extensibilité .NET</span><span class="sxs-lookup"><span data-stu-id="f1da0-125">.NET extensibility</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1da0-126">Développement d’applications</span><span class="sxs-lookup"><span data-stu-id="f1da0-126">Application development</span></span></p></td>
<td><p><span data-ttu-id="f1da0-127">Extensions ISAPI (Internet Server API)</span><span class="sxs-lookup"><span data-stu-id="f1da0-127">Internet Server API (ISAPI) extensions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f1da0-128">Développement d’applications</span><span class="sxs-lookup"><span data-stu-id="f1da0-128">Application development</span></span></p></td>
<td><p><span data-ttu-id="f1da0-129">Filtres ISAPI</span><span class="sxs-lookup"><span data-stu-id="f1da0-129">ISAPI filters</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1da0-130">État de santé et diagnostics</span><span class="sxs-lookup"><span data-stu-id="f1da0-130">Health and diagnostics</span></span></p></td>
<td><p><span data-ttu-id="f1da0-131">Journalisation HTTP</span><span class="sxs-lookup"><span data-stu-id="f1da0-131">HTTP logging</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f1da0-132">État de santé et diagnostics</span><span class="sxs-lookup"><span data-stu-id="f1da0-132">Health and diagnostics</span></span></p></td>
<td><p><span data-ttu-id="f1da0-133">Outils de journalisation</span><span class="sxs-lookup"><span data-stu-id="f1da0-133">Logging tools</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1da0-134">État de santé et diagnostics</span><span class="sxs-lookup"><span data-stu-id="f1da0-134">Health and diagnostics</span></span></p></td>
<td><p><span data-ttu-id="f1da0-135">Analyzer</span><span class="sxs-lookup"><span data-stu-id="f1da0-135">Tracing</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f1da0-136">Sécurité</span><span class="sxs-lookup"><span data-stu-id="f1da0-136">Security</span></span></p></td>
<td><p><span data-ttu-id="f1da0-137">Authentification anonyme (installée et activée par défaut)</span><span class="sxs-lookup"><span data-stu-id="f1da0-137">Anonymous authentication (installed and enabled by default)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1da0-138">Sécurité</span><span class="sxs-lookup"><span data-stu-id="f1da0-138">Security</span></span></p></td>
<td><p><span data-ttu-id="f1da0-139">Authentification Windows</span><span class="sxs-lookup"><span data-stu-id="f1da0-139">Windows authentication</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f1da0-140">Sécurité</span><span class="sxs-lookup"><span data-stu-id="f1da0-140">Security</span></span></p></td>
<td><p><span data-ttu-id="f1da0-141">Authentification par mappage de certificat client</span><span class="sxs-lookup"><span data-stu-id="f1da0-141">Client Certificate Mapping authentication</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1da0-142">Sécurité</span><span class="sxs-lookup"><span data-stu-id="f1da0-142">Security</span></span></p></td>
<td><p><span data-ttu-id="f1da0-143">Filtrage des demandes</span><span class="sxs-lookup"><span data-stu-id="f1da0-143">Request filtering</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f1da0-144">Performances</span><span class="sxs-lookup"><span data-stu-id="f1da0-144">Performance</span></span></p></td>
<td><p><span data-ttu-id="f1da0-145">Compression du contenu statique</span><span class="sxs-lookup"><span data-stu-id="f1da0-145">Static content compression</span></span></p>
<p><span data-ttu-id="f1da0-146">Compression de contenu dynamique</span><span class="sxs-lookup"><span data-stu-id="f1da0-146">Dynamic content compression</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1da0-147">Outils de gestion</span><span class="sxs-lookup"><span data-stu-id="f1da0-147">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="f1da0-148">Console de gestion IIS</span><span class="sxs-lookup"><span data-stu-id="f1da0-148">IIS Management Console</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f1da0-149">Outils de gestion</span><span class="sxs-lookup"><span data-stu-id="f1da0-149">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="f1da0-150">Scripts et outils de gestion IIS</span><span class="sxs-lookup"><span data-stu-id="f1da0-150">IIS Management Scripts and Tools</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="f1da0-151">Sur le système d’exploitation Windows Server 2008 R2 SP1 x64, vous pouvez utiliser Windows PowerShell 2,0.</span><span class="sxs-lookup"><span data-stu-id="f1da0-151">On the Windows Server 2008 R2 SP1 x64 operating system, you can use Windows PowerShell 2.0.</span></span> <span data-ttu-id="f1da0-152">Vous devez d’abord importer le module ServerManager, puis installer le rôle et les services de rôle IIS 7.5.</span><span class="sxs-lookup"><span data-stu-id="f1da0-152">You must first import the ServerManager module, and then install the IIS 7.5 role and role services.</span></span>

   ```PowerShell
    Import-Module ServerManager
   ```

   ```PowerShell
    Add-WindowsFeature Web-Server, Web-Static-Content, Web-Default-Doc, Web-Scripting-Tools, Web-Windows-Auth, Web-Asp-Net, Web-Log-Libraries, Web-Http-Tracing, Web-Stat-Compression, Web-Dyn-Compression, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Errors, Web-Http-Logging, Web-Net-Ext, Web-Client-Auth, Web-Filtering, Web-Mgmt-Console
   ```

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="f1da0-153">L’authentification anonyme est installée par défaut avec le rôle de serveur IIS.</span><span class="sxs-lookup"><span data-stu-id="f1da0-153">Anonymous authentication is installed by default with the IIS server role.</span></span> <span data-ttu-id="f1da0-154">Vous pouvez gérer l’authentification anonyme après l’installation d’IIS.</span><span class="sxs-lookup"><span data-stu-id="f1da0-154">You can manage anonymous authentication after the installation of IIS.</span></span> <span data-ttu-id="f1da0-155">Pour plus d’informations, consultez la rubrique « activer l’authentification anonyme (IIS 7) » à l’adresse <A href="https://go.microsoft.com/fwlink/p/?linkid=203935">https://go.microsoft.com/fwlink/p/?linkId=203935</A> .</span><span class="sxs-lookup"><span data-stu-id="f1da0-155">For details, see “Enable Anonymous Authentication (IIS 7)” at <A href="https://go.microsoft.com/fwlink/p/?linkid=203935">https://go.microsoft.com/fwlink/p/?linkId=203935</A>.</span></span>



</div>

<span data-ttu-id="f1da0-156">Le tableau suivant indique les services de rôle IIS 8,0 et IIS 8,5 requis pour Windows Server 2012 et Windows Server 2012 R2.</span><span class="sxs-lookup"><span data-stu-id="f1da0-156">The following table indicates the required IIS 8.0 and IIS 8.5 role services for Windows Server 2012 and Windows Server 2012 R2.</span></span>

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="f1da0-157">Pour Windows Server 2012 et Windows Server 2012 R2, la cmdlet Add-WindowsFeature a été remplacée par la cmdlet Install-WindowsFeature.</span><span class="sxs-lookup"><span data-stu-id="f1da0-157">For Windows Server 2012 and Windows Server 2012 R2, the Add-WindowsFeature cmdlet has been replaced by the Install-WindowsFeature cmdlet.</span></span> <span data-ttu-id="f1da0-158">Pour plus d’informations, consultez la rubrique <A href="https://go.microsoft.com/fwlink/p/?linkid=392274">install-WindowsFeature</A>.</span><span class="sxs-lookup"><span data-stu-id="f1da0-158">For details, see <A href="https://go.microsoft.com/fwlink/p/?linkid=392274">Install-WindowsFeature</A>.</span></span>



</div>

### <a name="iis-80-and-iis-85-role-services"></a><span data-ttu-id="f1da0-159">Services de rôle IIS 8,0 et IIS 8,5</span><span class="sxs-lookup"><span data-stu-id="f1da0-159">IIS 8.0 and IIS 8.5 Role Services</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f1da0-160">Titre de rôle</span><span class="sxs-lookup"><span data-stu-id="f1da0-160">Role Heading</span></span></th>
<th><span data-ttu-id="f1da0-161">Service de rôle</span><span class="sxs-lookup"><span data-stu-id="f1da0-161">Role Service</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f1da0-162">Serveur Web (IIS)</span><span class="sxs-lookup"><span data-stu-id="f1da0-162">Web Server (IIS)</span></span></p></td>
<td><p><span data-ttu-id="f1da0-163">Serveur web</span><span class="sxs-lookup"><span data-stu-id="f1da0-163">Web Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1da0-164">Fonctionnalités HTTP courantes</span><span class="sxs-lookup"><span data-stu-id="f1da0-164">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="f1da0-165">Document par défaut</span><span class="sxs-lookup"><span data-stu-id="f1da0-165">Default Document</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f1da0-166">Fonctionnalités HTTP courantes</span><span class="sxs-lookup"><span data-stu-id="f1da0-166">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="f1da0-167">Exploration des répertoires</span><span class="sxs-lookup"><span data-stu-id="f1da0-167">Directory Browsing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1da0-168">Fonctionnalités HTTP courantes</span><span class="sxs-lookup"><span data-stu-id="f1da0-168">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="f1da0-169">Erreurs HTTP</span><span class="sxs-lookup"><span data-stu-id="f1da0-169">HTTP Errors</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f1da0-170">Fonctionnalités HTTP courantes</span><span class="sxs-lookup"><span data-stu-id="f1da0-170">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="f1da0-171">Contenu statique</span><span class="sxs-lookup"><span data-stu-id="f1da0-171">Static content</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1da0-172">Fonctionnalités HTTP communes</span><span class="sxs-lookup"><span data-stu-id="f1da0-172">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="f1da0-173">Redirection HTTP</span><span class="sxs-lookup"><span data-stu-id="f1da0-173">HTTP Redirection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f1da0-174">État de santé et diagnostics</span><span class="sxs-lookup"><span data-stu-id="f1da0-174">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="f1da0-175">Journalisation HTTP</span><span class="sxs-lookup"><span data-stu-id="f1da0-175">HTTP Logging</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1da0-176">État de santé et diagnostics</span><span class="sxs-lookup"><span data-stu-id="f1da0-176">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="f1da0-177">Outils de journalisation</span><span class="sxs-lookup"><span data-stu-id="f1da0-177">Logging Tools</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f1da0-178">État de santé et diagnostics</span><span class="sxs-lookup"><span data-stu-id="f1da0-178">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="f1da0-179">Observateur de demandes</span><span class="sxs-lookup"><span data-stu-id="f1da0-179">Request Monitor</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1da0-180">État de santé et diagnostics</span><span class="sxs-lookup"><span data-stu-id="f1da0-180">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="f1da0-181">Analyzer</span><span class="sxs-lookup"><span data-stu-id="f1da0-181">Tracing</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f1da0-182">Sécurité</span><span class="sxs-lookup"><span data-stu-id="f1da0-182">Security</span></span></p></td>
<td><p><span data-ttu-id="f1da0-183">Filtrage des demandes</span><span class="sxs-lookup"><span data-stu-id="f1da0-183">Request Filtering</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1da0-184">Sécurité</span><span class="sxs-lookup"><span data-stu-id="f1da0-184">Security</span></span></p></td>
<td><p><span data-ttu-id="f1da0-185">Authentification de base</span><span class="sxs-lookup"><span data-stu-id="f1da0-185">Basic Authentication</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f1da0-186">Sécurité</span><span class="sxs-lookup"><span data-stu-id="f1da0-186">Security</span></span></p></td>
<td><p><span data-ttu-id="f1da0-187">Authentification par mappage de certificat client</span><span class="sxs-lookup"><span data-stu-id="f1da0-187">Client Certificate Mapping Authentication</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1da0-188">Sécurité</span><span class="sxs-lookup"><span data-stu-id="f1da0-188">Security</span></span></p></td>
<td><p><span data-ttu-id="f1da0-189">Authentification Windows</span><span class="sxs-lookup"><span data-stu-id="f1da0-189">Windows Authentication</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f1da0-190">Développement d’applications</span><span class="sxs-lookup"><span data-stu-id="f1da0-190">Application Development</span></span></p></td>
<td><p><span data-ttu-id="f1da0-191">Extensibilité .net 3,5</span><span class="sxs-lookup"><span data-stu-id="f1da0-191">.Net Extensibility 3.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1da0-192">Développement d’applications</span><span class="sxs-lookup"><span data-stu-id="f1da0-192">Application Development</span></span></p></td>
<td><p><span data-ttu-id="f1da0-193">Extensibilité .net 4,5</span><span class="sxs-lookup"><span data-stu-id="f1da0-193">.Net Extensibility 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f1da0-194">Développement d’applications</span><span class="sxs-lookup"><span data-stu-id="f1da0-194">Application Development</span></span></p></td>
<td><p><span data-ttu-id="f1da0-195">ASP.Net 3,5</span><span class="sxs-lookup"><span data-stu-id="f1da0-195">ASP.Net 3.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1da0-196">Développement d’applications</span><span class="sxs-lookup"><span data-stu-id="f1da0-196">Application Development</span></span></p></td>
<td><p><span data-ttu-id="f1da0-197">ASP.Net 4,5</span><span class="sxs-lookup"><span data-stu-id="f1da0-197">ASP.Net 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f1da0-198">Développement d’applications</span><span class="sxs-lookup"><span data-stu-id="f1da0-198">Application Development</span></span></p></td>
<td><p><span data-ttu-id="f1da0-199">Extensions ISAPI</span><span class="sxs-lookup"><span data-stu-id="f1da0-199">ISAPI Extensions</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1da0-200">Développement d’applications</span><span class="sxs-lookup"><span data-stu-id="f1da0-200">Application Development</span></span></p></td>
<td><p><span data-ttu-id="f1da0-201">Filtres ISAPI</span><span class="sxs-lookup"><span data-stu-id="f1da0-201">ISAPI Filters</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f1da0-202">Développement d’applications</span><span class="sxs-lookup"><span data-stu-id="f1da0-202">Application Development</span></span></p></td>
<td><p><span data-ttu-id="f1da0-203">Textes insérés par le serveur (SSI)</span><span class="sxs-lookup"><span data-stu-id="f1da0-203">Server Side Includes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1da0-204">Outils de gestion</span><span class="sxs-lookup"><span data-stu-id="f1da0-204">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="f1da0-205">Console de gestion IIS</span><span class="sxs-lookup"><span data-stu-id="f1da0-205">IIS Management Console</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f1da0-206">Outils de gestion</span><span class="sxs-lookup"><span data-stu-id="f1da0-206">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="f1da0-207">Compatibilité avec la métabase IIS 6</span><span class="sxs-lookup"><span data-stu-id="f1da0-207">IIS 6 Metabase compatibility</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1da0-208">Outils de gestion</span><span class="sxs-lookup"><span data-stu-id="f1da0-208">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="f1da0-209">Scripts et outils de gestion IIS</span><span class="sxs-lookup"><span data-stu-id="f1da0-209">IIS Management Scripts and Tools</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f1da0-210">Fonctionnalités .net 3,5 Framework</span><span class="sxs-lookup"><span data-stu-id="f1da0-210">.Net 3.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="f1da0-211">.Net 3,5 Framework</span><span class="sxs-lookup"><span data-stu-id="f1da0-211">.Net 3.5 Framework</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1da0-212">Fonctionnalités .net 4,5 Framework</span><span class="sxs-lookup"><span data-stu-id="f1da0-212">.Net 4.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="f1da0-213">.NET Framework 4,5</span><span class="sxs-lookup"><span data-stu-id="f1da0-213">.Net Framework 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f1da0-214">Fonctionnalités .net 4,5 Framework</span><span class="sxs-lookup"><span data-stu-id="f1da0-214">.Net 4.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="f1da0-215">ASP.Net 4,5</span><span class="sxs-lookup"><span data-stu-id="f1da0-215">ASP.Net 4.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1da0-216">Fonctionnalités .net 4,5 Framework</span><span class="sxs-lookup"><span data-stu-id="f1da0-216">.Net 4.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="f1da0-217">Activation HTTP</span><span class="sxs-lookup"><span data-stu-id="f1da0-217">HTTP Activation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f1da0-218">Fonctionnalités .net 4,5 Framework</span><span class="sxs-lookup"><span data-stu-id="f1da0-218">.Net 4.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="f1da0-219">Partage de port TCP</span><span class="sxs-lookup"><span data-stu-id="f1da0-219">TCP Port Sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1da0-220">Service de transfert intelligent en arrière-plan</span><span class="sxs-lookup"><span data-stu-id="f1da0-220">Background Intelligent Transfer Service</span></span></p></td>
<td><p><span data-ttu-id="f1da0-221">Extensions de serveur IIS</span><span class="sxs-lookup"><span data-stu-id="f1da0-221">IIS Server Extensions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f1da0-222">Services de prise en charge de l'écriture manuscrite</span><span class="sxs-lookup"><span data-stu-id="f1da0-222">Ink and Handwriting Services</span></span></p></td>
<td><p><span data-ttu-id="f1da0-223">Services de prise en charge de l'écriture manuscrite</span><span class="sxs-lookup"><span data-stu-id="f1da0-223">Ink and Handwriting Services</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1da0-224">Media Foundation</span><span class="sxs-lookup"><span data-stu-id="f1da0-224">Media Foundation</span></span></p></td>
<td><p><span data-ttu-id="f1da0-225">Media Foundation</span><span class="sxs-lookup"><span data-stu-id="f1da0-225">Media Foundation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f1da0-226">Interfaces utilisateur et infrastructure</span><span class="sxs-lookup"><span data-stu-id="f1da0-226">User Interfaces and Infrastructure</span></span></p></td>
<td><p><span data-ttu-id="f1da0-227">Outils et infrastructure de gestion graphique</span><span class="sxs-lookup"><span data-stu-id="f1da0-227">Graphical Management Tools and Infrastructure</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1da0-228">Interfaces utilisateur et infrastructure</span><span class="sxs-lookup"><span data-stu-id="f1da0-228">User Interfaces and Infrastructure</span></span></p></td>
<td><p><span data-ttu-id="f1da0-229">Expérience utilisateur</span><span class="sxs-lookup"><span data-stu-id="f1da0-229">Desktop Experience</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f1da0-230">Interfaces utilisateur et infrastructure</span><span class="sxs-lookup"><span data-stu-id="f1da0-230">User Interfaces and Infrastructure</span></span></p></td>
<td><p><span data-ttu-id="f1da0-231">Environnement graphique de serveur</span><span class="sxs-lookup"><span data-stu-id="f1da0-231">Server Graphical Shell</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1da0-232">Windows Identity Foundation 3,5</span><span class="sxs-lookup"><span data-stu-id="f1da0-232">Windows Identity Foundation 3.5</span></span></p></td>
<td><p><span data-ttu-id="f1da0-233">Windows Identity Foundation 3,5</span><span class="sxs-lookup"><span data-stu-id="f1da0-233">Windows Identity Foundation 3.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f1da0-234">Service d’activation des processus Windows</span><span class="sxs-lookup"><span data-stu-id="f1da0-234">Windows Process Activation Service</span></span></p></td>
<td><p><span data-ttu-id="f1da0-235">Modèle de processus</span><span class="sxs-lookup"><span data-stu-id="f1da0-235">Process Model</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1da0-236">Service d’activation des processus Windows</span><span class="sxs-lookup"><span data-stu-id="f1da0-236">Windows Process Activation Service</span></span></p></td>
<td><p><span data-ttu-id="f1da0-237">API de configuration</span><span class="sxs-lookup"><span data-stu-id="f1da0-237">Configuration APIs</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="f1da0-238">Dans Windows Server 2012 et Windows Server 2012 R2, vous pouvez utiliser Windows PowerShell 3,0 pour installer la configuration requise pour IIS.</span><span class="sxs-lookup"><span data-stu-id="f1da0-238">In Windows Server 2012 and Windows Server 2012 R2, you can use Windows PowerShell 3.0 to install the IIS Requirements.</span></span> <span data-ttu-id="f1da0-239">À l’aide du module ServerManager dans Windows PowerShell 3,0, tapez :</span><span class="sxs-lookup"><span data-stu-id="f1da0-239">Using the ServerManager module in Windows PowerShell 3.0, type:</span></span>

   ```PowerShell
    Import-Module ServerManager
   ```

   ```PowerShell
    Add-WindowsFeature Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-Framework-45-Core, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Console, Web-Mgmt-Compat, Windows-Identity-Foundation, Server-Media-Foundation, BITS -Source D:\sources\sxs
   ```

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="f1da0-240">New with Windows Server 2012 est le paramètre – source qui définit l’emplacement où se trouve le média source de Windows Server 2012.</span><span class="sxs-lookup"><span data-stu-id="f1da0-240">New with Windows Server 2012 is the –Source parameter that defines where the Windows Server 2012 source media can be found.</span></span> <span data-ttu-id="f1da0-241">Le média peut être défini comme lecteur de DVD (par exemple, D:\Sources\Sxs) ou sur un partage réseau dans lequel les fichiers multimédias ont été copiés (par exemple, \\ fileserver\windows2012\sources\Sxs).</span><span class="sxs-lookup"><span data-stu-id="f1da0-241">The media can be defined as a DVD drive (for example, D:\Sources\Sxs), or to a network share that the media files have been copied (for example, \\fileserver\windows2012\sources\Sxs).</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f1da0-242">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f1da0-242">See Also</span></span>


[<span data-ttu-id="f1da0-243">Configuration requise pour les services Internet (IIS) pour les pools frontaux et les serveurs Standard Edition dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f1da0-243">IIS requirements for Front End pools and Standard Edition servers in Lync Server 2013</span></span>](lync-server-2013-iis-requirements-for-front-end-pools-and-standard-edition-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

