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
ms.openlocfilehash: 6d284fa2082c886a583baf116893f792535a096b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136191"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="iis-configuration-in-lync-server-2013"></a><span data-ttu-id="07e63-102">Configuration des services Internet (IIS) dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="07e63-102">IIS configuration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="07e63-103">_**Dernière modification de la rubrique :** 2014-02-17_</span><span class="sxs-lookup"><span data-stu-id="07e63-103">_**Topic Last Modified:** 2014-02-17_</span></span>

<span data-ttu-id="07e63-104">Pour compléter cette procédure, vous devez être connecté au serveur au minimum en tant qu’administrateur local et en tant qu’utilisateur de domaine.</span><span class="sxs-lookup"><span data-stu-id="07e63-104">To successfully complete this procedure, you should be logged on to the server minimally as a local administrator and a domain user.</span></span>

<span data-ttu-id="07e63-105">Avant de configurer et d’installer le serveur frontal pour Lync Server 2013, Standard Edition ou le premier serveur frontal dans un pool, vous installez et configurez le rôle serveur et les services Web pour Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="07e63-105">Before you configure and install the Front End Server for Lync Server 2013, Standard Edition or the first Front End Server in a pool, you install and configure the server role and Web Services for Internet Information Services (IIS).</span></span>

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="07e63-106">Si votre organisation nécessite que vous localisiez les services Internet (IIS) et tous les services Web sur un lecteur autre que le lecteur système, vous pouvez modifier le chemin d’accès de l’emplacement d’installation des fichiers Lync Server 2013 dans la boîte de dialogue Configuration lors de l’installation initiale de Lync Server 2013 Outils d’administration.</span><span class="sxs-lookup"><span data-stu-id="07e63-106">If your organization requires that you locate IIS and all Web Services on a drive other than the system drive, you can change the installation location path for the Lync Server 2013 files in the Setup dialog box when you initially install the Lync Server 2013 Administrative tools.</span></span> <span data-ttu-id="07e63-107">Vous devez installer ces derniers avant d’installer IIS.</span><span class="sxs-lookup"><span data-stu-id="07e63-107">You install the Administrative tools before installing IIS.</span></span> <span data-ttu-id="07e63-108">Si vous installez les fichiers d’installation dans ce chemin d’accès, y compris OCSCore. msi, les autres fichiers Lync Server 2013 seront également déployés sur ce lecteur.</span><span class="sxs-lookup"><span data-stu-id="07e63-108">If you install the Setup files to this path, including OCSCore.msi, the rest of the Lync Server 2013 files will be deployed to this drive as well.</span></span> <span data-ttu-id="07e63-109">Pour dtails, voir <A href="lync-server-2013-install-lync-server-administrative-tools.md">install Lync Server 2013 administrative Tools</A>.</span><span class="sxs-lookup"><span data-stu-id="07e63-109">For dtails, see <A href="lync-server-2013-install-lync-server-administrative-tools.md">Install Lync Server 2013 administrative tools</A>.</span></span> <span data-ttu-id="07e63-110">Pour plus d’informations sur la façon de déplacer le INETPUB déployé par le gestionnaire Windows Server lors de <A href="https://go.microsoft.com/fwlink/p/?linkid=216888">https://go.microsoft.com/fwlink/p/?linkId=216888</A>l’installation d’IIS, reportez-vous à la rubrique.</span><span class="sxs-lookup"><span data-stu-id="07e63-110">For details about how to relocate the INETPUB deployed by Windows Server Manager when installing IIS, see <A href="https://go.microsoft.com/fwlink/p/?linkid=216888">https://go.microsoft.com/fwlink/p/?linkId=216888</A>.</span></span>



</div>

<span data-ttu-id="07e63-111">Le tableau suivant indique les services de rôle IIS 7,5 requis.</span><span class="sxs-lookup"><span data-stu-id="07e63-111">The following table indicates the required IIS 7.5 role services.</span></span>

### <a name="iis-75-role-services"></a><span data-ttu-id="07e63-112">Services de rôle IIS 7,5</span><span class="sxs-lookup"><span data-stu-id="07e63-112">IIS 7.5 Role Services</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="07e63-113">Titre de rôle</span><span class="sxs-lookup"><span data-stu-id="07e63-113">Role Heading</span></span></th>
<th><span data-ttu-id="07e63-114">Service de rôle</span><span class="sxs-lookup"><span data-stu-id="07e63-114">Role Service</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="07e63-115">Fonctionnalités HTTP communes installées</span><span class="sxs-lookup"><span data-stu-id="07e63-115">Common HTTP features installed</span></span></p></td>
<td><p><span data-ttu-id="07e63-116">Contenu statique</span><span class="sxs-lookup"><span data-stu-id="07e63-116">Static content</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="07e63-117">Fonctionnalités HTTP communes installées</span><span class="sxs-lookup"><span data-stu-id="07e63-117">Common HTTP features installed</span></span></p></td>
<td><p><span data-ttu-id="07e63-118">Document par défaut</span><span class="sxs-lookup"><span data-stu-id="07e63-118">Default document</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="07e63-119">Fonctionnalités HTTP communes installées</span><span class="sxs-lookup"><span data-stu-id="07e63-119">Common HTTP features installed</span></span></p></td>
<td><p><span data-ttu-id="07e63-120">Erreurs HTTP</span><span class="sxs-lookup"><span data-stu-id="07e63-120">HTTP errors</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="07e63-121">Développement d’applications</span><span class="sxs-lookup"><span data-stu-id="07e63-121">Application development</span></span></p></td>
<td><p><span data-ttu-id="07e63-122">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="07e63-122">ASP.NET</span></span></p>
<p><span data-ttu-id="07e63-123">ASP.NET Server 2012 nécessite également ASP. NET 4.5</span><span class="sxs-lookup"><span data-stu-id="07e63-123">Windows Server 2012 also requires ASP.NET4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="07e63-124">Développement d’applications</span><span class="sxs-lookup"><span data-stu-id="07e63-124">Application development</span></span></p></td>
<td><p><span data-ttu-id="07e63-125">Extensibilité .NET</span><span class="sxs-lookup"><span data-stu-id="07e63-125">.NET extensibility</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="07e63-126">Développement d’applications</span><span class="sxs-lookup"><span data-stu-id="07e63-126">Application development</span></span></p></td>
<td><p><span data-ttu-id="07e63-127">Extensions ISAPI (Internet Server API)</span><span class="sxs-lookup"><span data-stu-id="07e63-127">Internet Server API (ISAPI) extensions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="07e63-128">Développement d’applications</span><span class="sxs-lookup"><span data-stu-id="07e63-128">Application development</span></span></p></td>
<td><p><span data-ttu-id="07e63-129">Filtres ISAPI</span><span class="sxs-lookup"><span data-stu-id="07e63-129">ISAPI filters</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="07e63-130">État de santé et diagnostics</span><span class="sxs-lookup"><span data-stu-id="07e63-130">Health and diagnostics</span></span></p></td>
<td><p><span data-ttu-id="07e63-131">Journalisation HTTP</span><span class="sxs-lookup"><span data-stu-id="07e63-131">HTTP logging</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="07e63-132">État de santé et diagnostics</span><span class="sxs-lookup"><span data-stu-id="07e63-132">Health and diagnostics</span></span></p></td>
<td><p><span data-ttu-id="07e63-133">Outils de journalisation</span><span class="sxs-lookup"><span data-stu-id="07e63-133">Logging tools</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="07e63-134">État de santé et diagnostics</span><span class="sxs-lookup"><span data-stu-id="07e63-134">Health and diagnostics</span></span></p></td>
<td><p><span data-ttu-id="07e63-135">Analyzer</span><span class="sxs-lookup"><span data-stu-id="07e63-135">Tracing</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="07e63-136">Sécurité</span><span class="sxs-lookup"><span data-stu-id="07e63-136">Security</span></span></p></td>
<td><p><span data-ttu-id="07e63-137">Authentification anonyme (installée et activée par défaut)</span><span class="sxs-lookup"><span data-stu-id="07e63-137">Anonymous authentication (installed and enabled by default)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="07e63-138">Sécurité</span><span class="sxs-lookup"><span data-stu-id="07e63-138">Security</span></span></p></td>
<td><p><span data-ttu-id="07e63-139">Authentification Windows</span><span class="sxs-lookup"><span data-stu-id="07e63-139">Windows authentication</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="07e63-140">Sécurité</span><span class="sxs-lookup"><span data-stu-id="07e63-140">Security</span></span></p></td>
<td><p><span data-ttu-id="07e63-141">Authentification par mappage de certificat client</span><span class="sxs-lookup"><span data-stu-id="07e63-141">Client Certificate Mapping authentication</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="07e63-142">Sécurité</span><span class="sxs-lookup"><span data-stu-id="07e63-142">Security</span></span></p></td>
<td><p><span data-ttu-id="07e63-143">Filtrage des demandes</span><span class="sxs-lookup"><span data-stu-id="07e63-143">Request filtering</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="07e63-144">Performances</span><span class="sxs-lookup"><span data-stu-id="07e63-144">Performance</span></span></p></td>
<td><p><span data-ttu-id="07e63-145">Compression du contenu statique</span><span class="sxs-lookup"><span data-stu-id="07e63-145">Static content compression</span></span></p>
<p><span data-ttu-id="07e63-146">Compression de contenu dynamique</span><span class="sxs-lookup"><span data-stu-id="07e63-146">Dynamic content compression</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="07e63-147">Outils de gestion</span><span class="sxs-lookup"><span data-stu-id="07e63-147">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="07e63-148">Console de gestion IIS</span><span class="sxs-lookup"><span data-stu-id="07e63-148">IIS Management Console</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="07e63-149">Outils de gestion</span><span class="sxs-lookup"><span data-stu-id="07e63-149">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="07e63-150">Scripts et outils de gestion IIS</span><span class="sxs-lookup"><span data-stu-id="07e63-150">IIS Management Scripts and Tools</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="07e63-151">Sur le système d’exploitation Windows Server 2008 R2 SP1 x64, vous pouvez utiliser Windows PowerShell 2,0.</span><span class="sxs-lookup"><span data-stu-id="07e63-151">On the Windows Server 2008 R2 SP1 x64 operating system, you can use Windows PowerShell 2.0.</span></span> <span data-ttu-id="07e63-152">Vous devez d’abord importer le module ServerManager, puis installer le rôle et les services de rôle IIS 7.5.</span><span class="sxs-lookup"><span data-stu-id="07e63-152">You must first import the ServerManager module, and then install the IIS 7.5 role and role services.</span></span>

   ```PowerShell
    Import-Module ServerManager
   ```

   ```PowerShell
    Add-WindowsFeature Web-Server, Web-Static-Content, Web-Default-Doc, Web-Scripting-Tools, Web-Windows-Auth, Web-Asp-Net, Web-Log-Libraries, Web-Http-Tracing, Web-Stat-Compression, Web-Dyn-Compression, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Errors, Web-Http-Logging, Web-Net-Ext, Web-Client-Auth, Web-Filtering, Web-Mgmt-Console
   ```

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="07e63-153">L’authentification anonyme est installée par défaut avec le rôle de serveur IIS.</span><span class="sxs-lookup"><span data-stu-id="07e63-153">Anonymous authentication is installed by default with the IIS server role.</span></span> <span data-ttu-id="07e63-154">Vous pouvez gérer l’authentification anonyme après l’installation d’IIS.</span><span class="sxs-lookup"><span data-stu-id="07e63-154">You can manage anonymous authentication after the installation of IIS.</span></span> <span data-ttu-id="07e63-155">Pour plus d’informations, consultez la rubrique « activer l’authentification anonyme ( <A href="https://go.microsoft.com/fwlink/p/?linkid=203935">https://go.microsoft.com/fwlink/p/?linkId=203935</A>IIS 7) » à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="07e63-155">For details, see “Enable Anonymous Authentication (IIS 7)” at <A href="https://go.microsoft.com/fwlink/p/?linkid=203935">https://go.microsoft.com/fwlink/p/?linkId=203935</A>.</span></span>



</div>

<span data-ttu-id="07e63-156">Le tableau suivant indique les services de rôle IIS 8,0 et IIS 8,5 requis pour Windows Server 2012 et Windows Server 2012 R2.</span><span class="sxs-lookup"><span data-stu-id="07e63-156">The following table indicates the required IIS 8.0 and IIS 8.5 role services for Windows Server 2012 and Windows Server 2012 R2.</span></span>

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="07e63-157">Pour Windows Server 2012 et Windows Server 2012 R2, la cmdlet Add-WindowsFeature a été remplacée par la cmdlet install-WindowsFeature.</span><span class="sxs-lookup"><span data-stu-id="07e63-157">For Windows Server 2012 and Windows Server 2012 R2, the Add-WindowsFeature cmdlet has been replaced by the Install-WindowsFeature cmdlet.</span></span> <span data-ttu-id="07e63-158">Pour plus d’informations, consultez la rubrique <A href="https://go.microsoft.com/fwlink/p/?linkid=392274">install-WindowsFeature</A>.</span><span class="sxs-lookup"><span data-stu-id="07e63-158">For details, see <A href="https://go.microsoft.com/fwlink/p/?linkid=392274">Install-WindowsFeature</A>.</span></span>



</div>

### <a name="iis-80-and-iis-85-role-services"></a><span data-ttu-id="07e63-159">Services de rôle IIS 8,0 et IIS 8,5</span><span class="sxs-lookup"><span data-stu-id="07e63-159">IIS 8.0 and IIS 8.5 Role Services</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="07e63-160">Titre de rôle</span><span class="sxs-lookup"><span data-stu-id="07e63-160">Role Heading</span></span></th>
<th><span data-ttu-id="07e63-161">Service de rôle</span><span class="sxs-lookup"><span data-stu-id="07e63-161">Role Service</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="07e63-162">Serveur Web (IIS)</span><span class="sxs-lookup"><span data-stu-id="07e63-162">Web Server (IIS)</span></span></p></td>
<td><p><span data-ttu-id="07e63-163">Serveur web</span><span class="sxs-lookup"><span data-stu-id="07e63-163">Web Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="07e63-164">Fonctionnalités HTTP courantes</span><span class="sxs-lookup"><span data-stu-id="07e63-164">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="07e63-165">Document par défaut</span><span class="sxs-lookup"><span data-stu-id="07e63-165">Default Document</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="07e63-166">Fonctionnalités HTTP courantes</span><span class="sxs-lookup"><span data-stu-id="07e63-166">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="07e63-167">Exploration des répertoires</span><span class="sxs-lookup"><span data-stu-id="07e63-167">Directory Browsing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="07e63-168">Fonctionnalités HTTP courantes</span><span class="sxs-lookup"><span data-stu-id="07e63-168">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="07e63-169">Erreurs HTTP</span><span class="sxs-lookup"><span data-stu-id="07e63-169">HTTP Errors</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="07e63-170">Fonctionnalités HTTP courantes</span><span class="sxs-lookup"><span data-stu-id="07e63-170">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="07e63-171">Contenu statique</span><span class="sxs-lookup"><span data-stu-id="07e63-171">Static content</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="07e63-172">Fonctionnalités HTTP communes</span><span class="sxs-lookup"><span data-stu-id="07e63-172">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="07e63-173">Redirection HTTP</span><span class="sxs-lookup"><span data-stu-id="07e63-173">HTTP Redirection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="07e63-174">État de santé et diagnostics</span><span class="sxs-lookup"><span data-stu-id="07e63-174">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="07e63-175">Journalisation HTTP</span><span class="sxs-lookup"><span data-stu-id="07e63-175">HTTP Logging</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="07e63-176">État de santé et diagnostics</span><span class="sxs-lookup"><span data-stu-id="07e63-176">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="07e63-177">Outils de journalisation</span><span class="sxs-lookup"><span data-stu-id="07e63-177">Logging Tools</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="07e63-178">État de santé et diagnostics</span><span class="sxs-lookup"><span data-stu-id="07e63-178">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="07e63-179">Observateur de demandes</span><span class="sxs-lookup"><span data-stu-id="07e63-179">Request Monitor</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="07e63-180">État de santé et diagnostics</span><span class="sxs-lookup"><span data-stu-id="07e63-180">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="07e63-181">Analyzer</span><span class="sxs-lookup"><span data-stu-id="07e63-181">Tracing</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="07e63-182">Sécurité</span><span class="sxs-lookup"><span data-stu-id="07e63-182">Security</span></span></p></td>
<td><p><span data-ttu-id="07e63-183">Filtrage des demandes</span><span class="sxs-lookup"><span data-stu-id="07e63-183">Request Filtering</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="07e63-184">Sécurité</span><span class="sxs-lookup"><span data-stu-id="07e63-184">Security</span></span></p></td>
<td><p><span data-ttu-id="07e63-185">Authentification de base</span><span class="sxs-lookup"><span data-stu-id="07e63-185">Basic Authentication</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="07e63-186">Sécurité</span><span class="sxs-lookup"><span data-stu-id="07e63-186">Security</span></span></p></td>
<td><p><span data-ttu-id="07e63-187">Authentification par mappage de certificat client</span><span class="sxs-lookup"><span data-stu-id="07e63-187">Client Certificate Mapping Authentication</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="07e63-188">Sécurité</span><span class="sxs-lookup"><span data-stu-id="07e63-188">Security</span></span></p></td>
<td><p><span data-ttu-id="07e63-189">Authentification Windows</span><span class="sxs-lookup"><span data-stu-id="07e63-189">Windows Authentication</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="07e63-190">Développement d’applications</span><span class="sxs-lookup"><span data-stu-id="07e63-190">Application Development</span></span></p></td>
<td><p><span data-ttu-id="07e63-191">Extensibilité .net 3,5</span><span class="sxs-lookup"><span data-stu-id="07e63-191">.Net Extensibility 3.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="07e63-192">Développement d’applications</span><span class="sxs-lookup"><span data-stu-id="07e63-192">Application Development</span></span></p></td>
<td><p><span data-ttu-id="07e63-193">Extensibilité .net 4,5</span><span class="sxs-lookup"><span data-stu-id="07e63-193">.Net Extensibility 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="07e63-194">Développement d’applications</span><span class="sxs-lookup"><span data-stu-id="07e63-194">Application Development</span></span></p></td>
<td><p><span data-ttu-id="07e63-195">ASP.Net 3,5</span><span class="sxs-lookup"><span data-stu-id="07e63-195">ASP.Net 3.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="07e63-196">Développement d’applications</span><span class="sxs-lookup"><span data-stu-id="07e63-196">Application Development</span></span></p></td>
<td><p><span data-ttu-id="07e63-197">ASP.Net 4,5</span><span class="sxs-lookup"><span data-stu-id="07e63-197">ASP.Net 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="07e63-198">Développement d’applications</span><span class="sxs-lookup"><span data-stu-id="07e63-198">Application Development</span></span></p></td>
<td><p><span data-ttu-id="07e63-199">Extensions ISAPI</span><span class="sxs-lookup"><span data-stu-id="07e63-199">ISAPI Extensions</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="07e63-200">Développement d’applications</span><span class="sxs-lookup"><span data-stu-id="07e63-200">Application Development</span></span></p></td>
<td><p><span data-ttu-id="07e63-201">Filtres ISAPI</span><span class="sxs-lookup"><span data-stu-id="07e63-201">ISAPI Filters</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="07e63-202">Développement d’applications</span><span class="sxs-lookup"><span data-stu-id="07e63-202">Application Development</span></span></p></td>
<td><p><span data-ttu-id="07e63-203">Textes insérés par le serveur (SSI)</span><span class="sxs-lookup"><span data-stu-id="07e63-203">Server Side Includes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="07e63-204">Outils de gestion</span><span class="sxs-lookup"><span data-stu-id="07e63-204">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="07e63-205">Console de gestion IIS</span><span class="sxs-lookup"><span data-stu-id="07e63-205">IIS Management Console</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="07e63-206">Outils de gestion</span><span class="sxs-lookup"><span data-stu-id="07e63-206">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="07e63-207">Compatibilité avec la métabase IIS 6</span><span class="sxs-lookup"><span data-stu-id="07e63-207">IIS 6 Metabase compatibility</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="07e63-208">Outils de gestion</span><span class="sxs-lookup"><span data-stu-id="07e63-208">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="07e63-209">Scripts et outils de gestion IIS</span><span class="sxs-lookup"><span data-stu-id="07e63-209">IIS Management Scripts and Tools</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="07e63-210">Fonctionnalités .net 3,5 Framework</span><span class="sxs-lookup"><span data-stu-id="07e63-210">.Net 3.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="07e63-211">.Net 3,5 Framework</span><span class="sxs-lookup"><span data-stu-id="07e63-211">.Net 3.5 Framework</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="07e63-212">Fonctionnalités .net 4,5 Framework</span><span class="sxs-lookup"><span data-stu-id="07e63-212">.Net 4.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="07e63-213">.NET Framework 4,5</span><span class="sxs-lookup"><span data-stu-id="07e63-213">.Net Framework 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="07e63-214">Fonctionnalités .net 4,5 Framework</span><span class="sxs-lookup"><span data-stu-id="07e63-214">.Net 4.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="07e63-215">ASP.Net 4,5</span><span class="sxs-lookup"><span data-stu-id="07e63-215">ASP.Net 4.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="07e63-216">Fonctionnalités .net 4,5 Framework</span><span class="sxs-lookup"><span data-stu-id="07e63-216">.Net 4.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="07e63-217">Activation HTTP</span><span class="sxs-lookup"><span data-stu-id="07e63-217">HTTP Activation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="07e63-218">Fonctionnalités .net 4,5 Framework</span><span class="sxs-lookup"><span data-stu-id="07e63-218">.Net 4.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="07e63-219">Partage de port TCP</span><span class="sxs-lookup"><span data-stu-id="07e63-219">TCP Port Sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="07e63-220">Service de transfert intelligent en arrière-plan</span><span class="sxs-lookup"><span data-stu-id="07e63-220">Background Intelligent Transfer Service</span></span></p></td>
<td><p><span data-ttu-id="07e63-221">Extensions de serveur IIS</span><span class="sxs-lookup"><span data-stu-id="07e63-221">IIS Server Extensions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="07e63-222">Services de prise en charge de l'écriture manuscrite</span><span class="sxs-lookup"><span data-stu-id="07e63-222">Ink and Handwriting Services</span></span></p></td>
<td><p><span data-ttu-id="07e63-223">Services de prise en charge de l'écriture manuscrite</span><span class="sxs-lookup"><span data-stu-id="07e63-223">Ink and Handwriting Services</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="07e63-224">Media Foundation</span><span class="sxs-lookup"><span data-stu-id="07e63-224">Media Foundation</span></span></p></td>
<td><p><span data-ttu-id="07e63-225">Media Foundation</span><span class="sxs-lookup"><span data-stu-id="07e63-225">Media Foundation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="07e63-226">Interfaces utilisateur et infrastructure</span><span class="sxs-lookup"><span data-stu-id="07e63-226">User Interfaces and Infrastructure</span></span></p></td>
<td><p><span data-ttu-id="07e63-227">Outils et infrastructure de gestion graphique</span><span class="sxs-lookup"><span data-stu-id="07e63-227">Graphical Management Tools and Infrastructure</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="07e63-228">Interfaces utilisateur et infrastructure</span><span class="sxs-lookup"><span data-stu-id="07e63-228">User Interfaces and Infrastructure</span></span></p></td>
<td><p><span data-ttu-id="07e63-229">Expérience utilisateur</span><span class="sxs-lookup"><span data-stu-id="07e63-229">Desktop Experience</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="07e63-230">Interfaces utilisateur et infrastructure</span><span class="sxs-lookup"><span data-stu-id="07e63-230">User Interfaces and Infrastructure</span></span></p></td>
<td><p><span data-ttu-id="07e63-231">Environnement graphique de serveur</span><span class="sxs-lookup"><span data-stu-id="07e63-231">Server Graphical Shell</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="07e63-232">Windows Identity Foundation 3,5</span><span class="sxs-lookup"><span data-stu-id="07e63-232">Windows Identity Foundation 3.5</span></span></p></td>
<td><p><span data-ttu-id="07e63-233">Windows Identity Foundation 3,5</span><span class="sxs-lookup"><span data-stu-id="07e63-233">Windows Identity Foundation 3.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="07e63-234">Service d’activation des processus Windows</span><span class="sxs-lookup"><span data-stu-id="07e63-234">Windows Process Activation Service</span></span></p></td>
<td><p><span data-ttu-id="07e63-235">Modèle de processus</span><span class="sxs-lookup"><span data-stu-id="07e63-235">Process Model</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="07e63-236">Service d’activation des processus Windows</span><span class="sxs-lookup"><span data-stu-id="07e63-236">Windows Process Activation Service</span></span></p></td>
<td><p><span data-ttu-id="07e63-237">API de configuration</span><span class="sxs-lookup"><span data-stu-id="07e63-237">Configuration APIs</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="07e63-238">Dans Windows Server 2012 et Windows Server 2012 R2, vous pouvez utiliser Windows PowerShell 3,0 pour installer la configuration requise pour IIS.</span><span class="sxs-lookup"><span data-stu-id="07e63-238">In Windows Server 2012 and Windows Server 2012 R2, you can use Windows PowerShell 3.0 to install the IIS Requirements.</span></span> <span data-ttu-id="07e63-239">À l’aide du module ServerManager dans Windows PowerShell 3,0, tapez :</span><span class="sxs-lookup"><span data-stu-id="07e63-239">Using the ServerManager module in Windows PowerShell 3.0, type:</span></span>

   ```PowerShell
    Import-Module ServerManager
   ```

   ```PowerShell
    Add-WindowsFeature Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-Framework-45-Core, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Console, Web-Mgmt-Compat, Windows-Identity-Foundation, Server-Media-Foundation, BITS -Source D:\sources\sxs
   ```

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="07e63-240">New with Windows Server 2012 est le paramètre – source qui définit l’emplacement où se trouve le média source de Windows Server 2012.</span><span class="sxs-lookup"><span data-stu-id="07e63-240">New with Windows Server 2012 is the –Source parameter that defines where the Windows Server 2012 source media can be found.</span></span> <span data-ttu-id="07e63-241">Le média peut être défini comme lecteur de DVD (par exemple, D:\Sources\Sxs) ou sur un partage réseau dans lequel les fichiers multimédias ont été copiés (par \\exemple, fileserver\windows2012\sources\Sxs).</span><span class="sxs-lookup"><span data-stu-id="07e63-241">The media can be defined as a DVD drive (for example, D:\Sources\Sxs), or to a network share that the media files have been copied (for example, \\fileserver\windows2012\sources\Sxs).</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="07e63-242">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="07e63-242">See Also</span></span>


[<span data-ttu-id="07e63-243">Configuration requise pour les services Internet (IIS) pour les pools frontaux et les serveurs Standard Edition dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="07e63-243">IIS requirements for Front End pools and Standard Edition servers in Lync Server 2013</span></span>](lync-server-2013-iis-requirements-for-front-end-pools-and-standard-edition-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

