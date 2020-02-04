---
title: 'Lync Server 2013 : installation de rapports d’analyse Lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing Lync Server 2013 Monitoring Reports
ms:assetid: 6f417569-b100-442c-ad48-fdd794626cf7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204989(v=OCS.15)
ms:contentKeyID: 48184445
ms.date: 02/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b6b5f9832ddc10d3cea46d09aee6b047595db0f7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726144"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-lync-server-2013-monitoring-reports"></a><span data-ttu-id="7c129-102">Installation des rapports d’analyse Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7c129-102">Installing Lync Server 2013 Monitoring Reports</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7c129-103">_**Dernière modification de la rubrique :** 2015-02-27_</span><span class="sxs-lookup"><span data-stu-id="7c129-103">_**Topic Last Modified:** 2015-02-27_</span></span>

<span data-ttu-id="7c129-104">Les rapports de surveillance de Microsoft Lync Server 2013 vous fournissent des informations sur la qualité et la quantité des sessions de communication qui interviennent au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="7c129-104">Microsoft Lync Server 2013 Monitoring Reports provide you with a wealth of information about the quality and quantity of the communication sessions that take place in your organization.</span></span> <span data-ttu-id="7c129-105">Toutefois, les rapports d’analyse ne sont pas automatiquement installés lors de l’installation de Lync Server 2013 ; au lieu de cela, vous devez installer des rapports de surveillance séparément, puis uniquement après l’installation de Lync Server sur votre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="7c129-105">However, Monitoring Reports are not automatically installed when you install Lync Server 2013; instead, you must install Monitoring Reports separately, and only after Lync Server has been installed on the computer.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7c129-p102">Il est recommandé d’installer les rapports de surveillance sur le même ordinateur que celui sur lequel la base de données de surveillance est installée. Cela simplifie le processus d’attribution des autorisations d’accès aux rapports : l’installation des rapports de surveillance sur l’ordinateur qui héberge le magasin d’analyse signifie qu’il n’est pas nécessaire de configurer les autorisations qui permettent à une base de données sur un premier ordinateur d’interagir avec le service Reporting Services exécuté sur un autre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="7c129-p102">It is recommended that you install Monitoring Reports on the same computer where the monitoring database is installed. This simplifies the process of assigning permissions for accessing the reports: installing Monitoring Reports on the computer that hosts the monitoring store means that you will not have to configure permissions that allow a database on one computer to interact with Reporting Services running on a second computer.</span></span>



</div>

<span data-ttu-id="7c129-108">Les rapports de surveillance de Lync Server incluent plus de 30 rapports conçus pour fournir des informations détaillées sur les conférences, des sessions de messagerie instantanée d’égal à égal, des inscriptions d’utilisateur, l’application de groupe de réponse, etc.</span><span class="sxs-lookup"><span data-stu-id="7c129-108">Lync Server Monitoring Reports include over 30 reports designed to provide detailed information about conferences, peer-to-peer IM sessions, user registrations, the Response Group application, and much more.</span></span> <span data-ttu-id="7c129-109">Pour la version 2013, les rapports de surveillance de Lync Server incluent un certain nombre d’améliorations :</span><span class="sxs-lookup"><span data-stu-id="7c129-109">For the 2013 version, Lync Server Monitoring Reports include a number of enhancements:</span></span>

  - <span data-ttu-id="7c129-110">**Nouveaux rapports de qualité de la voix**.</span><span class="sxs-lookup"><span data-stu-id="7c129-110">**New voice quality reports**.</span></span> <span data-ttu-id="7c129-111">Ces nouveaux rapports incluent le [rapport Comparaison de qualité multimédia dans Lync Server 2013](lync-server-2013-media-quality-comparison-report.md), qui compare la qualité entre les différents types d’appels (par exemple, entre les appels câblés et les appels sans fil). ainsi que le [rapport de temps de participation à la Conférence dans Lync Server 2013](lync-server-2013-conference-join-time-report.md), qui fournit des informations relatives à la durée nécessaire pour que les utilisateurs puissent participer à une conférence.</span><span class="sxs-lookup"><span data-stu-id="7c129-111">These new reports include the [Media Quality Comparison Report in Lync Server 2013](lync-server-2013-media-quality-comparison-report.md), which compares quality between different types of calls (for example, between wired calls and wireless calls); and the [Conference Join Time Report in Lync Server 2013](lync-server-2013-conference-join-time-report.md), which provides information regarding the amount of time requires for users to join a conference.</span></span>

  - <span data-ttu-id="7c129-112">**Rapports améliorés pour l’analyse et la résolution des problèmes des sessions de partage vidéo et d’application.**</span><span class="sxs-lookup"><span data-stu-id="7c129-112">**Improved reports for analyzing and troubleshooting both video and application sharing sessions.**</span></span> <span data-ttu-id="7c129-113">Le [rapport synthèse sur la qualité multimédia dans Lync server 2013](lync-server-2013-media-quality-summary-report.md) fournit un moyen d’analyser les appels vidéo et de partage d’application, tandis que le [rapport sur les performances du serveur dans Lync Server 2013](lync-server-2013-server-performance-report.md) décrit les performances des serveurs qui génèrent ces appels.</span><span class="sxs-lookup"><span data-stu-id="7c129-113">The [Media Quality Summary Report in Lync Server 2013](lync-server-2013-media-quality-summary-report.md) provides a way to analyze video and application sharing calls, while the [Server Performance Report in Lync Server 2013](lync-server-2013-server-performance-report.md) details the performance of servers generating these calls.</span></span> <span data-ttu-id="7c129-114">Les métriques de partage d’application et de vidéo sont également signalées par le [rapport détaillé de session d’égal à égal dans Lync server 2013](lync-server-2013-peer-to-peer-session-detail-report.md) et le [rapport de détails de la Conférence dans Lync Server 2013](lync-server-2013-conference-detail-report.md).</span><span class="sxs-lookup"><span data-stu-id="7c129-114">Video and application sharing metrics are also now reported by the [Peer-to-Peer Session Detail Report in Lync Server 2013](lync-server-2013-peer-to-peer-session-detail-report.md) and the [Conference Detail Report in Lync Server 2013](lync-server-2013-conference-detail-report.md).</span></span>

  - <span data-ttu-id="7c129-p106">**Performances améliorées des rapports**. Ces améliorations incluent un temps de réponse et d’extraction des données plus court, ainsi qu’une navigation plus rapide et plus facile dans les rapports.</span><span class="sxs-lookup"><span data-stu-id="7c129-p106">**Improved report performance**. This includes faster response and data retrieval time, as well as faster and easier navigation through the reports.</span></span>

<span data-ttu-id="7c129-117">D’autres informations sur chaque rapport sont disponibles dans la documentation des rapports de surveillance.</span><span class="sxs-lookup"><span data-stu-id="7c129-117">More information on the individual reports can be found in the Monitoring Reports documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7c129-118">Il y a un autre rapport-sous-état de détails d’appels QoE, inclus dans Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7c129-118">There is another new report – QoE Call Detail Subreport – included in Lync Server 2013.</span></span> <span data-ttu-id="7c129-119">Toutefois, ce rapport est principalement destiné à un usage interne et non à un accès direct.</span><span class="sxs-lookup"><span data-stu-id="7c129-119">However, this report is primarily for internal use, and is not intended to be directly accessed.</span></span>



</div>

<span data-ttu-id="7c129-120">Il existe deux façons d’installer des rapports de surveillance de Lync Server : vous pouvez utiliser l’Assistant Déploiement de Lync Server ou utiliser un script Windows PowerShell inclus dans les fichiers d’installation de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7c129-120">There are two ways to install Lync Server Monitoring Reports: you can use the Lync Server Deployment Wizard or you can use a Windows PowerShell script included with the Lync Server 2013 installation files.</span></span> <span data-ttu-id="7c129-121">Quelle que doit la méthode utilisée pour installer les rapports, vous devez d’abord vous assurer que vous :</span><span class="sxs-lookup"><span data-stu-id="7c129-121">Regardless of the method you use to install the reports you must first make sure that you:</span></span>

  - <span data-ttu-id="7c129-122">avez le droit d’ajouter un rôle de base de données à un compte d’utilisateur dans la base de données de surveillance ;</span><span class="sxs-lookup"><span data-stu-id="7c129-122">Have the right to add a database role to a user account in the monitoring database.</span></span>

  - <span data-ttu-id="7c129-p109">détenez le rôle Gestionnaire de contenu dans SQL Server Reporting Services. Ce rôle vous donne le droit de déployer des rapports sur SQL Server Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="7c129-p109">Hold the Content Manager role in SQL Server Reporting Services. This role gives you the right to deploy reports to SQL Server Reporting Services.</span></span>

<span data-ttu-id="7c129-125">Pour installer les rapports de surveillance à l’aide de l’Assistant Déploiement, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="7c129-125">To install the Monitoring Reports by using the Deployment Wizard, complete the following steps:</span></span>

1.  <span data-ttu-id="7c129-126">Cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Assistant Déploiement de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="7c129-126">Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Deployment Wizard**.</span></span>

2.  <span data-ttu-id="7c129-127">Dans l’Assistant Déploiement, cliquez sur **Déployer les rapports de surveillance** afin de démarrer l’Assistant Déploiement des rapports de surveillance.</span><span class="sxs-lookup"><span data-stu-id="7c129-127">In the Deployment Wizard, click **Deploy Monitoring Reports** in order to start the Deploy Monitoring Reports wizard.</span></span>

3.  <span data-ttu-id="7c129-p110">Dans l’Assistant Déploiement des rapports de surveillance, dans la page **Spécifier une base de données de surveillance**, vérifiez que le nom de domaine complet de l’ordinateur qui héberge votre magasin d’analyse apparaît dans la liste déroulante **Base de données de surveillance**. (Si vous avez plusieurs magasins d’analyse, vous devez sélectionner le serveur approprié dans la liste déroulante.) Vérifiez que l’instance SQL Server correcte apparaît dans la zone **Instance SQL Server Reporting Services (SSRS)** (par exemple, **atl-sql-001.litwareinc.com/archinst**), puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="7c129-p110">In the Deploy Monitoring Reports wizard, on the **Specify Monitoring Database** page, make sure that the fully qualified domain name of the computer hosting your monitoring store appears in the **Monitoring database** dropdown list. (If you have multiple monitoring stores you will need to select the appropriate server from the dropdown list.) Verify that the correct SQL Server instance appears in the **SQL Server Reporting Services (SSRS) instance** box (for example, **atl-sql-001.litwareinc.com/archinst**) and then click **Next**.</span></span>

4.  <span data-ttu-id="7c129-130">Dans la page **spécifier les informations d’identification** , dans la zone **nom d’utilisateur** , tapez le nom de domaine et le nom d’utilisateur du compte à utiliser lors de l’accès aux rapports de surveillance (par exemple, **litwareinc\\kenmyer**).</span><span class="sxs-lookup"><span data-stu-id="7c129-130">On the **Specify Credentials** page, in the **User name** box, type the domain name and user name of the account to be used when accessing the Monitoring Reports (for example, **litwareinc\\kenmyer**).</span></span> <span data-ttu-id="7c129-131">Si vous n’utilisez pas ce format (nom\\d’utilisateur de domaine), une erreur se produit.</span><span class="sxs-lookup"><span data-stu-id="7c129-131">If you do not use this format (domain\\user name) an error will occur.</span></span>
    
    <span data-ttu-id="7c129-p112">Tapez le mot de passe du compte d’utilisateur dans la zone **Mot de passe**, puis cliquez sur **Suivant**. Notez qu’aucun droit spécial n’est requis pour ce compte. Le nom de connexion et les autorisations de base de données requis sont octroyés automatiquement au compte une fois l’installation terminée.</span><span class="sxs-lookup"><span data-stu-id="7c129-p112">Type the user account password in the **Password** box, and then click **Next**. Note that no special rights are required for this account. The account will automatically be granted the required logon and database permissions when setup completes.</span></span>

5.  <span data-ttu-id="7c129-p113">Dans la page **Spécifier un groupe en lecture seule**, entrez le nom d’un groupe de sécurité qui disposera d’un accès en lecture seule à SQL Server Reporting Services dans la zone de groupe Utilisateur. Par exemple, pour octroyer aux administrateurs un accès en lecture seule aux rapports, entrez **RTCUniversalReadOnlyAdmins**. Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="7c129-p113">On the **Specify Read-Only Group** page enter the name of a security group that will be granted read-only access to the SQL Server Reporting Services in the User group box. For example, to give read-only administrators access to the reports enter **RTCUniversalReadOnlyAdmins**. Click **Next**.</span></span>

6.  <span data-ttu-id="7c129-138">Dans la page **Exécution de commandes**, cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="7c129-138">On the **Executing Commands** page, click **Finish**.</span></span>

<span data-ttu-id="7c129-139">Les rapports d’analyse peuvent également être installés à partir de Lync Server Management Shell en exécutant le script DeployReports. ps1 ; Ce script Windows PowerShell est disponible sur le média d’installation de Lync Server dans \\le\\dossier ReportingSetup du programme d’installation.</span><span class="sxs-lookup"><span data-stu-id="7c129-139">Monitoring Reports can also be installed from the Lync Server Management Shell by running the script DeployReports.ps1; this Windows PowerShell script can be found on the Lync Server installation media in the \\Setup\\ReportingSetup folder.</span></span> <span data-ttu-id="7c129-140">Pour installer des rapports d’analyse à l’aide de DeployReports. ps1, tapez une commande semblable à la suivante à l’invite Management Shell :</span><span class="sxs-lookup"><span data-stu-id="7c129-140">To install Monitoring Reports using DeployReports.ps1, type a command similar to the following at the Management Shell prompt:</span></span>

    C:\Program Files\Microsoft Lync Server 2013\Deployment\Setup\DeployReports.ps1 -storedUserName "litwareinc\kenmyer" -storedPassword "p@ssw0rd" -readOnlyGroupName "RTCUniversalReadOnlyAdmins" -reportServerSqlInstance "atl-sql-001.litwareinc.com" -monitoringDatabaseId "MonitoringDatabase:atl-sql-001.litwareinc.com"

<span data-ttu-id="7c129-141">Les paramètres utilisés dans la commande précédente sont décrits dans le tableau suivant :</span><span class="sxs-lookup"><span data-stu-id="7c129-141">The parameters used in the preceding command are described in the following table:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7c129-142">Nom du paramètre</span><span class="sxs-lookup"><span data-stu-id="7c129-142">Parameter Name</span></span></th>
<th><span data-ttu-id="7c129-143">Obligatoire</span><span class="sxs-lookup"><span data-stu-id="7c129-143">Required</span></span></th>
<th><span data-ttu-id="7c129-144">Description</span><span class="sxs-lookup"><span data-stu-id="7c129-144">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7c129-145">storedUserName</span><span class="sxs-lookup"><span data-stu-id="7c129-145">storedUserName</span></span></p></td>
<td><p><span data-ttu-id="7c129-146">Oui</span><span class="sxs-lookup"><span data-stu-id="7c129-146">Yes</span></span></p></td>
<td><p><span data-ttu-id="7c129-147">Compte d’utilisateur (au format domaine\nomUtilisateur) utilisé pour accéder au magasin d’analyse ; par exemple :</span><span class="sxs-lookup"><span data-stu-id="7c129-147">User account (in the format domain\username) used to access the monitoring store; for example:</span></span></p>
<pre><code>-storedUserName &quot;litwareinc\kenmyer&quot;</code></pre>
<p><span data-ttu-id="7c129-148">Ce compte doit posséder les autorisations SQL Server et SQL Server Reporting Services précédemment spécifiées, sans quoi le script échoue.</span><span class="sxs-lookup"><span data-stu-id="7c129-148">This account must have the previously-specified SQL Server and SQL Server Reporting Services permissions or the script will fail.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c129-149">storedPassword</span><span class="sxs-lookup"><span data-stu-id="7c129-149">storedPassword</span></span></p></td>
<td><p><span data-ttu-id="7c129-150">Oui</span><span class="sxs-lookup"><span data-stu-id="7c129-150">Yes</span></span></p></td>
<td><p><span data-ttu-id="7c129-151">Mot de passe du compte d’utilisateur utilisé pour accéder au magasin d’analyse.</span><span class="sxs-lookup"><span data-stu-id="7c129-151">Password for the user account used to access the monitoring store.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7c129-152">readOnlyGroupName</span><span class="sxs-lookup"><span data-stu-id="7c129-152">readOnlyGroupName</span></span></p></td>
<td><p><span data-ttu-id="7c129-153">Non</span><span class="sxs-lookup"><span data-stu-id="7c129-153">No</span></span></p></td>
<td><p><span data-ttu-id="7c129-p115">Domaine ou groupe de sécurité local dont les membres disposent d’un accès en lecture seule aux rapports de surveillance. Notez que le script échoue si le groupe spécifié n’existe pas. Si vous décidez ultérieurement de révoquer ces autorisations ou si vous décidez d’octroyer à d’autres utilisateurs ou groupes des autorisations d’accès, vous pouvez le faire à l’aide du Gestionnaire de rapports SQL Service Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="7c129-p115">Domain or local security group whose members will be granted read-only access to the Monitoring Reports. Note that the script will fail if the specified group does not exist. If you later decide to revoke these permissions, or if you decide to grant other users or other groups access permissions, you can do so using the SQL Service Reporting Services Report Manager.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c129-157">reportSqlServerInstance</span><span class="sxs-lookup"><span data-stu-id="7c129-157">reportSqlServerInstance</span></span></p></td>
<td><p><span data-ttu-id="7c129-158">Non</span><span class="sxs-lookup"><span data-stu-id="7c129-158">No</span></span></p></td>
<td><p><span data-ttu-id="7c129-p116">Instance SQL Server qui héberge le service de rapport. L’instance de création de rapports doit être spécifiée à l’aide du nom de domaine complet du serveur de rapports ; par exemple :</span><span class="sxs-lookup"><span data-stu-id="7c129-p116">SQL Server instance that hosts the Reporting Service. The Reporting instance must be specified using the fully qualified domain name of the Report Server; for example:</span></span></p>
<pre><code>-reportServerSqlInstance atl-sql-001.litwareinc.com</code></pre>
<p><span data-ttu-id="7c129-161">Si ce paramètre n’est pas inclus, le script part du principe que les services de rapport sont hébergés par la même instance SQL Server que celle qui héberge la base de données de surveillance.</span><span class="sxs-lookup"><span data-stu-id="7c129-161">If this parameter is not included the script will assume that the reporting services are hosted by the same SQL Server instance that hosts the monitoring database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7c129-162">monitoringDatabaseId</span><span class="sxs-lookup"><span data-stu-id="7c129-162">monitoringDatabaseId</span></span></p></td>
<td><p><span data-ttu-id="7c129-163">Non</span><span class="sxs-lookup"><span data-stu-id="7c129-163">No</span></span></p></td>
<td><p><span data-ttu-id="7c129-p117">Identité de service de la base de données de surveillance. Vous pouvez retourner les identités pour vos bases de données de surveillance en exécutant cette commande :</span><span class="sxs-lookup"><span data-stu-id="7c129-p117">Service Identity for the monitoring database. You can return the Identities for your monitoring databases by running this command:</span></span></p>
<pre><code>Get-CsService -MonitoringDatabase</code></pre></td>
</tr>
</tbody>
</table>


<span data-ttu-id="7c129-166">Une fois les rapports d’analyse installés, vous devez utiliser l’applet de contrôle Set-CsReportingConfiguration pour configurer l’URL utilisée pour accéder à ces rapports.</span><span class="sxs-lookup"><span data-stu-id="7c129-166">After the Monitoring Reports have been installed you must then use the Set-CsReportingConfiguration cmdlet to configure the URL used to access these reports.</span></span> <span data-ttu-id="7c129-167">Cette tâche peut être exécutée à partir de Lync Server Management Shell en exécutant la commande Windows PowerShell suivante.</span><span class="sxs-lookup"><span data-stu-id="7c129-167">This task can be carried out from the Lync Server Management Shell by running the following Windows PowerShell command.</span></span> <span data-ttu-id="7c129-168">Notez qu’il est recommandé, mais pas obligatoire, d’utiliser le protocole HTTPS pour configurer l’URL des rapports :</span><span class="sxs-lookup"><span data-stu-id="7c129-168">Note that it is recommended, but not required, that you use the HTTPS protocol when configuring the reporting URL:</span></span>

    Set-CsReportingConfiguration -Identity "MonitoringDatabase:atl-sql-001.litwareinc.com" -ReportingURL "https://atl-sql-001.litwareinc.com:443/Reports_ARCHINST"

<span data-ttu-id="7c129-p119">Dans la commande précédente, la propriété ReportingUrl doit avoir la valeur de l’URL du Gestionnaire de rapports utilisé par SQL Server 2008 R2 Reporting Services. Vous pouvez la déterminer en suivant les étapes ci-après sur l’ordinateur sur lequel SQL Server Reporting Services a été installé :</span><span class="sxs-lookup"><span data-stu-id="7c129-p119">In the preceding command, the ReportingUrl property should be set to the Report Manager URL used by SQL Server 2008 R2 Reporting Services. You can determine the Report Manager URL by completing the following steps on the computer where SQL Server Reporting Services has been installed:</span></span>

1.  <span data-ttu-id="7c129-171">Cliquez sur Démarrer, sur Tous les programmes, sur Microsoft SQL Server 2008 R2, sur Outils de configuration, puis sur Gestionnaire de configuration de Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="7c129-171">Click Start, click All Programs, click Microsoft SQL Server 2008 R2, click Configuration Tools, and then click Reporting Services Configuration Manager.</span></span>

2.  <span data-ttu-id="7c129-p120">Dans la boîte de dialogue Connexion relative à la configuration de Reporting Services, vérifiez que le nom de l’ordinateur Reporting Services apparaît dans la zone Nom du serveur. Sélectionnez l’instance SQL Server dans la liste déroulante Instance du serveur de rapports, puis cliquez sur Connecter.</span><span class="sxs-lookup"><span data-stu-id="7c129-p120">In the Reporting Services Configuration Connection dialog box, make sure that the name of the Reporting Services computer appears in the Server Name box. Select the SQL Server instance from the Report Server Instance dropdown list and then click Connect.</span></span>

3.  <span data-ttu-id="7c129-p121">Dans le Gestionnaire de configuration de Reporting Services, cliquez sur URL du Gestionnaire de rapports. Une ou plusieurs URL doivent apparaître dans le volet URL du Gestionnaire de rapports. Chacune de ces URL peut être utilisée en tant qu’URL de rapports, même si, là encore, il est recommandé d’utiliser le protocole HTTPS pour le paramètre ReportingUrl.</span><span class="sxs-lookup"><span data-stu-id="7c129-p121">In Reporting Services Configuration Manager, click Report Manager URL. One or more URLs should appear in the Report Manager URL pane. Any of these URLs can be used as the Reporting URL although, again, it is recommended that the ReportingUrl use the HTTPS protocol.</span></span>

<span data-ttu-id="7c129-177">Si vous avez configuré une base de données miroir pour votre base de données de surveillance, vous devez également associer les rapports de surveillance à la base de données miroir.</span><span class="sxs-lookup"><span data-stu-id="7c129-177">If you have set up a mirror database for your monitoring database then you must also associate the Monitoring Reports with the mirror database.</span></span> <span data-ttu-id="7c129-178">Pour plus d’informations, reportez-vous à l’article [Association de rapports d’analyse à une base de données miroir dans Lync Server 2013](lync-server-2013-associating-monitoring-reports-with-a-mirror-database.md) .</span><span class="sxs-lookup"><span data-stu-id="7c129-178">See the article [Associating Monitoring Reports with a mirror database in Lync Server 2013](lync-server-2013-associating-monitoring-reports-with-a-mirror-database.md) for details.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

