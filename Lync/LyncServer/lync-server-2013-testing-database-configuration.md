---
title: 'Lync Server 2013: test de la configuration d’une base de données'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing database configuration
ms:assetid: 60f7fcd2-5efe-4791-b159-b0f9bf39a41b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727307(v=OCS.15)
ms:contentKeyID: 63969606
ms.date: 07/07/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 805b62e234f7a5469d3af3677ba81478fb3abc8f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846546"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-database-configuration-in-lync-server-2013"></a><span data-ttu-id="4e1d7-102">Test de la configuration d’une base de données dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4e1d7-102">Testing database configuration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4e1d7-103">_**Dernière modification de la rubrique:** 2016-07-07_</span><span class="sxs-lookup"><span data-stu-id="4e1d7-103">_**Topic Last Modified:** 2016-07-07_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4e1d7-104">Échéancier de vérification</span><span class="sxs-lookup"><span data-stu-id="4e1d7-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="4e1d7-105">Jour</span><span class="sxs-lookup"><span data-stu-id="4e1d7-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e1d7-106">Outil de test</span><span class="sxs-lookup"><span data-stu-id="4e1d7-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="4e1d7-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4e1d7-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e1d7-108">Autorisations requises</span><span class="sxs-lookup"><span data-stu-id="4e1d7-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="4e1d7-109">Lorsque l’application est exécutée en local à l’aide de Lync Server Management Shell, les utilisateurs doivent être membres du groupe de sécurité RTCUniversalServerAdmins et doivent disposer de privilèges d’administrateur sur le serveur SQL Server.</span><span class="sxs-lookup"><span data-stu-id="4e1d7-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group, and need to have Administrator privileges on the SQL server.</span></span></p>
<p><span data-ttu-id="4e1d7-110">Lors de l’exécution à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter l’applet de commande <strong>test-CsDatabase</strong> .</span><span class="sxs-lookup"><span data-stu-id="4e1d7-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsDatabase</strong> cmdlet.</span></span> <span data-ttu-id="4e1d7-111">Pour afficher la liste de tous les rôles RBAC qui peuvent utiliser cette applet de commande, exécutez la commande suivante à partir de l’invite Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="4e1d7-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDatabase&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="4e1d7-112">Description</span><span class="sxs-lookup"><span data-stu-id="4e1d7-112">Description</span></span>

<span data-ttu-id="4e1d7-113">L’applet de **contrôle test-CsDatabase** vérifie la connectivité à une ou plusieurs bases de données Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4e1d7-113">The **Test-CsDatabase** cmdlet verifies connectivity to one or more Lync Server 2013 databases.</span></span> <span data-ttu-id="4e1d7-114">Lors de l’exécution, l’applet de connexion **test-CsDatabase** lit la topologie du serveur Lync, tente de se connecter aux bases de données pertinentes, puis signale la réussite ou l’échec de chaque tentative.</span><span class="sxs-lookup"><span data-stu-id="4e1d7-114">When run, the **Test-CsDatabase** cmdlet reads the Lync Server topology, attempts to connect to relevant databases, and then reports back the success or failure of each try.</span></span> <span data-ttu-id="4e1d7-115">S’il est possible de créer une connexion, l’applet de contrôle renvoie également des informations telles que le nom de la base de données, les informations de version de SQL Server et l’emplacement de toutes les bases de données de miroirs installées.</span><span class="sxs-lookup"><span data-stu-id="4e1d7-115">If a connection can be made, the cmdlet will also report back such information as the database name, SQL Server version information, and the location of any installed mirror databases.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="4e1d7-116">Exécution du test</span><span class="sxs-lookup"><span data-stu-id="4e1d7-116">Running the test</span></span>

<span data-ttu-id="4e1d7-117">La commande décrite dans l’exemple 1 vérifie la configuration de la base de données de gestion centrale.</span><span class="sxs-lookup"><span data-stu-id="4e1d7-117">The command shown in Example 1 verifies the configuration of the Central Management database.</span></span>

    Test-CsDatabase -CentralManagementDatabase

<span data-ttu-id="4e1d7-118">L’exemple 2 vérifie toutes les bases de données serveur Lync installées sur l’ordinateur atl-sql-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="4e1d7-118">Example 2 verifies all the Lync Server databases installed on the computer atl-sql-001.litwareinc.com.</span></span>

    Test-CsDatabase -ConfiguredDatabases -SqlServerFqdn "atl-sql-001.litwareinc.com"

<span data-ttu-id="4e1d7-119">Dans l’exemple 3, la vérification est effectuée uniquement pour la base de données d’archivage installée sur l’ordinateur atl-sql-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="4e1d7-119">In Example 3, verification is performed only for the Archiving database installed on the computer atl-sql-001.litwareinc.com.</span></span> <span data-ttu-id="4e1d7-120">Notez que le paramètre SqlInstanceName est inclus pour spécifier l’instance SQL Server (Archinst) de l’emplacement de la base de données d’archivage.</span><span class="sxs-lookup"><span data-stu-id="4e1d7-120">Note that the SqlInstanceName parameter is included to specify the SQL Server instance (Archinst) where the Archiving database is located.</span></span>

    Test-CsDatabase -DatabaseType "Archiving" -SqlServerFqdn "atl-sql-001.litwareinc.com" -SqlInstanceName "archinst"

<span data-ttu-id="4e1d7-121">La commande affichée dans l’exemple 4 vérifie les bases de données installées sur l’ordinateur local.</span><span class="sxs-lookup"><span data-stu-id="4e1d7-121">The command shown in Example 4 verifies the databases installed on the local computer.</span></span>

    Test-CsDatabase -LocalService

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="4e1d7-122">Détermination du succès ou de l’échec</span><span class="sxs-lookup"><span data-stu-id="4e1d7-122">Determining success or failure</span></span>

<span data-ttu-id="4e1d7-123">Si la connectivité de la base de données est correctement configurée, vous recevrez une sortie similaire à celle-ci, avec la propriété réussite marquée comme **vraie**:</span><span class="sxs-lookup"><span data-stu-id="4e1d7-123">If database connectivity is configured correctly, you'll receive output similar to this, with the Succeed property marked as **True**:</span></span>

<span data-ttu-id="4e1d7-124">SqlServerFqdn: atl-sql-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="4e1d7-124">SqlServerFqdn : atl-sql-001.litwareinc.com</span></span>

<span data-ttu-id="4e1d7-125">SqlInstanceName: RTC</span><span class="sxs-lookup"><span data-stu-id="4e1d7-125">SqlInstanceName : rtc</span></span>

<span data-ttu-id="4e1d7-126">MirrorSqlServerFqdn :</span><span class="sxs-lookup"><span data-stu-id="4e1d7-126">MirrorSqlServerFqdn :</span></span>

<span data-ttu-id="4e1d7-127">MirrorSqlInstanceName :</span><span class="sxs-lookup"><span data-stu-id="4e1d7-127">MirrorSqlInstanceName :</span></span>

<span data-ttu-id="4e1d7-128">DatabaseName: XDS</span><span class="sxs-lookup"><span data-stu-id="4e1d7-128">DatabaseName : xds</span></span>

<span data-ttu-id="4e1d7-129">DataSource:</span><span class="sxs-lookup"><span data-stu-id="4e1d7-129">DataSource :</span></span>

<span data-ttu-id="4e1d7-130">SQLServerVersion :</span><span class="sxs-lookup"><span data-stu-id="4e1d7-130">SQLServerVersion :</span></span>

<span data-ttu-id="4e1d7-131">ExpectedVersion : 10.13.2</span><span class="sxs-lookup"><span data-stu-id="4e1d7-131">ExpectedVersion : 10.13.2</span></span>

<span data-ttu-id="4e1d7-132">InstalledVersion :</span><span class="sxs-lookup"><span data-stu-id="4e1d7-132">InstalledVersion :</span></span>

<span data-ttu-id="4e1d7-133">Réussite: vrai</span><span class="sxs-lookup"><span data-stu-id="4e1d7-133">Succeed : True</span></span>

<span data-ttu-id="4e1d7-134">SqlServerFqdn: atl-sql-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="4e1d7-134">SqlServerFqdn : atl-sql-001.litwareinc.com</span></span>

<span data-ttu-id="4e1d7-135">SqlInstanceName: RTC</span><span class="sxs-lookup"><span data-stu-id="4e1d7-135">SqlInstanceName : rtc</span></span>

<span data-ttu-id="4e1d7-136">MirrorSqlServerFqdn :</span><span class="sxs-lookup"><span data-stu-id="4e1d7-136">MirrorSqlServerFqdn :</span></span>

<span data-ttu-id="4e1d7-137">MirrorSqlInstanceName :</span><span class="sxs-lookup"><span data-stu-id="4e1d7-137">MirrorSqlInstanceName :</span></span>

<span data-ttu-id="4e1d7-138">DatabaseName: lis</span><span class="sxs-lookup"><span data-stu-id="4e1d7-138">DatabaseName : lis</span></span>

<span data-ttu-id="4e1d7-139">DataSource:</span><span class="sxs-lookup"><span data-stu-id="4e1d7-139">DataSource :</span></span>

<span data-ttu-id="4e1d7-140">SQLServerVersion :</span><span class="sxs-lookup"><span data-stu-id="4e1d7-140">SQLServerVersion :</span></span>

<span data-ttu-id="4e1d7-141">ExpectedVersion: 3.1.1</span><span class="sxs-lookup"><span data-stu-id="4e1d7-141">ExpectedVersion : 3.1.1</span></span>

<span data-ttu-id="4e1d7-142">InstalledVersion :</span><span class="sxs-lookup"><span data-stu-id="4e1d7-142">InstalledVersion :</span></span>

<span data-ttu-id="4e1d7-143">Réussite: vrai</span><span class="sxs-lookup"><span data-stu-id="4e1d7-143">Succeed : True</span></span>

<span data-ttu-id="4e1d7-144">Si la base de données est configurée correctement mais toujours disponible, le champ réussite s’affichera comme **faux**, et des alertes et informations supplémentaires seront fournies:</span><span class="sxs-lookup"><span data-stu-id="4e1d7-144">If the database is configured correctly but still available, the Succeed field will be shown as **False**, and additional warnings and information will be provided:</span></span>

<span data-ttu-id="4e1d7-145">SqlServerFqdn: atl-sql-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="4e1d7-145">SqlServerFqdn : atl-sql-001.litwareinc.com</span></span>

<span data-ttu-id="4e1d7-146">SqlInstanceName: RTC</span><span class="sxs-lookup"><span data-stu-id="4e1d7-146">SqlInstanceName : rtc</span></span>

<span data-ttu-id="4e1d7-147">MirrorSqlServerFqdn :</span><span class="sxs-lookup"><span data-stu-id="4e1d7-147">MirrorSqlServerFqdn :</span></span>

<span data-ttu-id="4e1d7-148">MirrorSqlInstanceName :</span><span class="sxs-lookup"><span data-stu-id="4e1d7-148">MirrorSqlInstanceName :</span></span>

<span data-ttu-id="4e1d7-149">DatabaseName: XDS</span><span class="sxs-lookup"><span data-stu-id="4e1d7-149">DatabaseName : xds</span></span>

<span data-ttu-id="4e1d7-150">DataSource:</span><span class="sxs-lookup"><span data-stu-id="4e1d7-150">DataSource :</span></span>

<span data-ttu-id="4e1d7-151">SQLServerVersion :</span><span class="sxs-lookup"><span data-stu-id="4e1d7-151">SQLServerVersion :</span></span>

<span data-ttu-id="4e1d7-152">ExpectedVersion : 10.13.2</span><span class="sxs-lookup"><span data-stu-id="4e1d7-152">ExpectedVersion : 10.13.2</span></span>

<span data-ttu-id="4e1d7-153">InstalledVersion :</span><span class="sxs-lookup"><span data-stu-id="4e1d7-153">InstalledVersion :</span></span>

<span data-ttu-id="4e1d7-154">Réussite: faux</span><span class="sxs-lookup"><span data-stu-id="4e1d7-154">Succeed : False</span></span>

<span data-ttu-id="4e1d7-155">SqlServerFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="4e1d7-155">SqlServerFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="4e1d7-156">SqlInstanceName: RTC</span><span class="sxs-lookup"><span data-stu-id="4e1d7-156">SqlInstanceName : rtc</span></span>

<span data-ttu-id="4e1d7-157">MirrorSqlServerFqdn :</span><span class="sxs-lookup"><span data-stu-id="4e1d7-157">MirrorSqlServerFqdn :</span></span>

<span data-ttu-id="4e1d7-158">MirrorSqlInstanceName :</span><span class="sxs-lookup"><span data-stu-id="4e1d7-158">MirrorSqlInstanceName :</span></span>

<span data-ttu-id="4e1d7-159">DatabaseName: lis</span><span class="sxs-lookup"><span data-stu-id="4e1d7-159">DatabaseName : lis</span></span>

<span data-ttu-id="4e1d7-160">DataSource:</span><span class="sxs-lookup"><span data-stu-id="4e1d7-160">DataSource :</span></span>

<span data-ttu-id="4e1d7-161">SQLServerVersion :</span><span class="sxs-lookup"><span data-stu-id="4e1d7-161">SQLServerVersion :</span></span>

<span data-ttu-id="4e1d7-162">ExpectedVersion: 3.1.1</span><span class="sxs-lookup"><span data-stu-id="4e1d7-162">ExpectedVersion : 3.1.1</span></span>

<span data-ttu-id="4e1d7-163">InstalledVersion :</span><span class="sxs-lookup"><span data-stu-id="4e1d7-163">InstalledVersion :</span></span>

<span data-ttu-id="4e1d7-164">Réussite: faux</span><span class="sxs-lookup"><span data-stu-id="4e1d7-164">Succeed : False</span></span>

<span data-ttu-id="4e1d7-165">AVERTISSEMENT: test-CsDatabase a rencontré des erreurs.</span><span class="sxs-lookup"><span data-stu-id="4e1d7-165">WARNING: Test-CsDatabase encountered errors.</span></span> <span data-ttu-id="4e1d7-166">Consulter le fichier journal d’un</span><span class="sxs-lookup"><span data-stu-id="4e1d7-166">Consult the log file for a</span></span>

<span data-ttu-id="4e1d7-167">analyse détaillée et vérification de la prise en considération de toutes les erreurs (2) et avertissements (0)</span><span class="sxs-lookup"><span data-stu-id="4e1d7-167">detailed analysis, and to make sure that all errors (2) and warnings (0) are addressed</span></span>

<span data-ttu-id="4e1d7-168">avant de continuer.</span><span class="sxs-lookup"><span data-stu-id="4e1d7-168">before continuing.</span></span>

<span data-ttu-id="4e1d7-169">AVERTISSEMENT: des résultats détaillés sont disponibles à l’adresse suivante:</span><span class="sxs-lookup"><span data-stu-id="4e1d7-169">WARNING: Detailed results can be found at</span></span>

<span data-ttu-id="4e1d7-170">"C:\\les\\utilisateurs\\testent\\AppData\\\\local\\Temp 2 test-CsDatabase-b18d488a-8044-4679-bbf2-</span><span class="sxs-lookup"><span data-stu-id="4e1d7-170">"C:\\Users\\Testing\\AppData\\Local\\Temp\\2\\Test-CsDatabase-b18d488a-8044-4679-bbf2-</span></span>

<span data-ttu-id="4e1d7-171">04d593cce8e6. html».</span><span class="sxs-lookup"><span data-stu-id="4e1d7-171">04d593cce8e6.html".</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="4e1d7-172">Raisons pour lesquelles le test peut avoir échoué</span><span class="sxs-lookup"><span data-stu-id="4e1d7-172">Reasons why the test might have failed</span></span>

<span data-ttu-id="4e1d7-173">Voici quelques raisons courantes pour lesquelles **les tests-CsDatabase** peuvent échouer:</span><span class="sxs-lookup"><span data-stu-id="4e1d7-173">Here are some common reasons why **Test-CsDatabase** might fail:</span></span>

  - <span data-ttu-id="4e1d7-174">Une valeur de paramètre incorrecte a été fournie.</span><span class="sxs-lookup"><span data-stu-id="4e1d7-174">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="4e1d7-175">S’il est utilisé, les paramètres facultatifs doivent être correctement configurés ou le test échoue.</span><span class="sxs-lookup"><span data-stu-id="4e1d7-175">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="4e1d7-176">Réexécutez la commande sans les paramètres facultatifs et déterminez si l’opération aboutit.</span><span class="sxs-lookup"><span data-stu-id="4e1d7-176">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="4e1d7-177">Cette commande échoue si la base de données est mal configurée ou n’est pas encore déployée.</span><span class="sxs-lookup"><span data-stu-id="4e1d7-177">This command will fail if the database is misconfigured or not yet deployed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4e1d7-178">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4e1d7-178">See Also</span></span>


[<span data-ttu-id="4e1d7-179">Get-CsDatabaseMirrorState</span><span class="sxs-lookup"><span data-stu-id="4e1d7-179">Get-CsDatabaseMirrorState</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsDatabaseMirrorState)  
[<span data-ttu-id="4e1d7-180">Get-CsService</span><span class="sxs-lookup"><span data-stu-id="4e1d7-180">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
[<span data-ttu-id="4e1d7-181">Get-CsUserDatabaseState</span><span class="sxs-lookup"><span data-stu-id="4e1d7-181">Get-CsUserDatabaseState</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsUserDatabaseState)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

