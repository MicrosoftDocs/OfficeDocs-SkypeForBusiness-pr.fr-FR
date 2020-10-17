---
title: 'Lync Server 2013 : test de la configuration de base de données'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing database configuration
ms:assetid: 60f7fcd2-5efe-4791-b159-b0f9bf39a41b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727307(v=OCS.15)
ms:contentKeyID: 63969606
ms.date: 07/07/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f1d57659c93aa42392f5408721157df1d14b56b0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504101"
---
# <a name="testing-database-configuration-in-lync-server-2013"></a><span data-ttu-id="04758-102">Test de la configuration de la base de données dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="04758-102">Testing database configuration in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="04758-103">_**Dernière modification de la rubrique :** 2016-07-07_</span><span class="sxs-lookup"><span data-stu-id="04758-103">_**Topic Last Modified:** 2016-07-07_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="04758-104">Planification de la vérification</span><span class="sxs-lookup"><span data-stu-id="04758-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="04758-105">Journalière</span><span class="sxs-lookup"><span data-stu-id="04758-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="04758-106">Outil de test</span><span class="sxs-lookup"><span data-stu-id="04758-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="04758-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="04758-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="04758-108">Autorisations requises</span><span class="sxs-lookup"><span data-stu-id="04758-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="04758-109">Lorsqu’ils sont exécutés localement à l’aide de Lync Server Management Shell, les utilisateurs doivent être membres du groupe de sécurité RTCUniversalServerAdmins et disposer de privilèges d’administrateur sur le serveur SQL Server.</span><span class="sxs-lookup"><span data-stu-id="04758-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group, and need to have Administrator privileges on the SQL server.</span></span></p>
<p><span data-ttu-id="04758-110">Lorsqu’ils sont exécutés à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter la cmdlet <strong>test-applet csdatabase</strong> .</span><span class="sxs-lookup"><span data-stu-id="04758-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsDatabase</strong> cmdlet.</span></span> <span data-ttu-id="04758-111">Pour afficher la liste de tous les rôles RBAC pouvant utiliser cette cmdlet, exécutez la commande suivante à partir de l’invite Windows PowerShell :</span><span class="sxs-lookup"><span data-stu-id="04758-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDatabase&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="04758-112">Description</span><span class="sxs-lookup"><span data-stu-id="04758-112">Description</span></span>

<span data-ttu-id="04758-113">L’applet de commande **test-applet csdatabase** vérifie la connectivité avec une ou plusieurs bases de données Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="04758-113">The **Test-CsDatabase** cmdlet verifies connectivity to one or more Lync Server 2013 databases.</span></span> <span data-ttu-id="04758-114">Lorsqu’elle est exécutée, l’applet de commande **test-applet csdatabase** lit la topologie Lync Server, tente de se connecter aux bases de données appropriées, puis signale la réussite ou l’échec de chaque tentative.</span><span class="sxs-lookup"><span data-stu-id="04758-114">When run, the **Test-CsDatabase** cmdlet reads the Lync Server topology, attempts to connect to relevant databases, and then reports back the success or failure of each try.</span></span> <span data-ttu-id="04758-115">Si une connexion peut être établie, l’applet de commande fournit également des informations telles que le nom de la base de données, les informations de version SQL Server et l’emplacement des éventuelles bases de données miroir installées.</span><span class="sxs-lookup"><span data-stu-id="04758-115">If a connection can be made, the cmdlet will also report back such information as the database name, SQL Server version information, and the location of any installed mirror databases.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="04758-116">Exécution du test</span><span class="sxs-lookup"><span data-stu-id="04758-116">Running the test</span></span>

<span data-ttu-id="04758-117">La commande de l’exemple 1 vérifie la configuration de la base de données Central Management.</span><span class="sxs-lookup"><span data-stu-id="04758-117">The command shown in Example 1 verifies the configuration of the Central Management database.</span></span>

    Test-CsDatabase -CentralManagementDatabase

<span data-ttu-id="04758-118">L’exemple 2 vérifie toutes les bases de données Lync Server installées sur l’ordinateur atl-sql-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="04758-118">Example 2 verifies all the Lync Server databases installed on the computer atl-sql-001.litwareinc.com.</span></span>

    Test-CsDatabase -ConfiguredDatabases -SqlServerFqdn "atl-sql-001.litwareinc.com"

<span data-ttu-id="04758-p103">Dans l’exemple 3, la vérification est exécutée uniquement pour la base de données Archiving installée sur l’ordinateur atl-sql-001.litwareinc.com. Notez que l’inclusion du paramètre SqlInstanceName permet de spécifier l’instance SQL Server (Archinst) où se trouve la base de données Archiving.</span><span class="sxs-lookup"><span data-stu-id="04758-p103">In Example 3, verification is performed only for the Archiving database installed on the computer atl-sql-001.litwareinc.com. Note that the SqlInstanceName parameter is included to specify the SQL Server instance (Archinst) where the Archiving database is located.</span></span>

    Test-CsDatabase -DatabaseType "Archiving" -SqlServerFqdn "atl-sql-001.litwareinc.com" -SqlInstanceName "archinst"

<span data-ttu-id="04758-121">La commande illustrée à l’exemple 4 vérifie les bases de données installées l’ordinateur local.</span><span class="sxs-lookup"><span data-stu-id="04758-121">The command shown in Example 4 verifies the databases installed on the local computer.</span></span>

    Test-CsDatabase -LocalService

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="04758-122">Détermination de la réussite ou de l’échec</span><span class="sxs-lookup"><span data-stu-id="04758-122">Determining success or failure</span></span>

<span data-ttu-id="04758-123">Si la connectivité de la base de données est correctement configurée, vous recevrez un résultat similaire à celui-ci, avec la propriété réussite marquée **true**:</span><span class="sxs-lookup"><span data-stu-id="04758-123">If database connectivity is configured correctly, you'll receive output similar to this, with the Succeed property marked as **True**:</span></span>

<span data-ttu-id="04758-124">SqlServerFqdn : atl-sql-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="04758-124">SqlServerFqdn : atl-sql-001.litwareinc.com</span></span>

<span data-ttu-id="04758-125">SqlInstanceName : RTC</span><span class="sxs-lookup"><span data-stu-id="04758-125">SqlInstanceName : rtc</span></span>

<span data-ttu-id="04758-126">MirrorSqlServerFqdn :</span><span class="sxs-lookup"><span data-stu-id="04758-126">MirrorSqlServerFqdn :</span></span>

<span data-ttu-id="04758-127">MirrorSqlInstanceName :</span><span class="sxs-lookup"><span data-stu-id="04758-127">MirrorSqlInstanceName :</span></span>

<span data-ttu-id="04758-128">DatabaseName : XDS</span><span class="sxs-lookup"><span data-stu-id="04758-128">DatabaseName : xds</span></span>

<span data-ttu-id="04758-129">Source</span><span class="sxs-lookup"><span data-stu-id="04758-129">DataSource :</span></span>

<span data-ttu-id="04758-130">SQLServerVersion :</span><span class="sxs-lookup"><span data-stu-id="04758-130">SQLServerVersion :</span></span>

<span data-ttu-id="04758-131">ExpectedVersion : 10.13.2</span><span class="sxs-lookup"><span data-stu-id="04758-131">ExpectedVersion : 10.13.2</span></span>

<span data-ttu-id="04758-132">InstalledVersion :</span><span class="sxs-lookup"><span data-stu-id="04758-132">InstalledVersion :</span></span>

<span data-ttu-id="04758-133">Réussite : true</span><span class="sxs-lookup"><span data-stu-id="04758-133">Succeed : True</span></span>

<span data-ttu-id="04758-134">SqlServerFqdn : atl-sql-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="04758-134">SqlServerFqdn : atl-sql-001.litwareinc.com</span></span>

<span data-ttu-id="04758-135">SqlInstanceName : RTC</span><span class="sxs-lookup"><span data-stu-id="04758-135">SqlInstanceName : rtc</span></span>

<span data-ttu-id="04758-136">MirrorSqlServerFqdn :</span><span class="sxs-lookup"><span data-stu-id="04758-136">MirrorSqlServerFqdn :</span></span>

<span data-ttu-id="04758-137">MirrorSqlInstanceName :</span><span class="sxs-lookup"><span data-stu-id="04758-137">MirrorSqlInstanceName :</span></span>

<span data-ttu-id="04758-138">DatabaseName : lis</span><span class="sxs-lookup"><span data-stu-id="04758-138">DatabaseName : lis</span></span>

<span data-ttu-id="04758-139">Source</span><span class="sxs-lookup"><span data-stu-id="04758-139">DataSource :</span></span>

<span data-ttu-id="04758-140">SQLServerVersion :</span><span class="sxs-lookup"><span data-stu-id="04758-140">SQLServerVersion :</span></span>

<span data-ttu-id="04758-141">ExpectedVersion : 3.1.1</span><span class="sxs-lookup"><span data-stu-id="04758-141">ExpectedVersion : 3.1.1</span></span>

<span data-ttu-id="04758-142">InstalledVersion :</span><span class="sxs-lookup"><span data-stu-id="04758-142">InstalledVersion :</span></span>

<span data-ttu-id="04758-143">Réussite : true</span><span class="sxs-lookup"><span data-stu-id="04758-143">Succeed : True</span></span>

<span data-ttu-id="04758-144">Si la base de données est correctement configurée mais toujours disponible, le champ réussite affiche **false**et des avertissements et informations supplémentaires sont fournis :</span><span class="sxs-lookup"><span data-stu-id="04758-144">If the database is configured correctly but still available, the Succeed field will be shown as **False**, and additional warnings and information will be provided:</span></span>

<span data-ttu-id="04758-145">SqlServerFqdn : atl-sql-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="04758-145">SqlServerFqdn : atl-sql-001.litwareinc.com</span></span>

<span data-ttu-id="04758-146">SqlInstanceName : RTC</span><span class="sxs-lookup"><span data-stu-id="04758-146">SqlInstanceName : rtc</span></span>

<span data-ttu-id="04758-147">MirrorSqlServerFqdn :</span><span class="sxs-lookup"><span data-stu-id="04758-147">MirrorSqlServerFqdn :</span></span>

<span data-ttu-id="04758-148">MirrorSqlInstanceName :</span><span class="sxs-lookup"><span data-stu-id="04758-148">MirrorSqlInstanceName :</span></span>

<span data-ttu-id="04758-149">DatabaseName : XDS</span><span class="sxs-lookup"><span data-stu-id="04758-149">DatabaseName : xds</span></span>

<span data-ttu-id="04758-150">Source</span><span class="sxs-lookup"><span data-stu-id="04758-150">DataSource :</span></span>

<span data-ttu-id="04758-151">SQLServerVersion :</span><span class="sxs-lookup"><span data-stu-id="04758-151">SQLServerVersion :</span></span>

<span data-ttu-id="04758-152">ExpectedVersion : 10.13.2</span><span class="sxs-lookup"><span data-stu-id="04758-152">ExpectedVersion : 10.13.2</span></span>

<span data-ttu-id="04758-153">InstalledVersion :</span><span class="sxs-lookup"><span data-stu-id="04758-153">InstalledVersion :</span></span>

<span data-ttu-id="04758-154">Réussite : false</span><span class="sxs-lookup"><span data-stu-id="04758-154">Succeed : False</span></span>

<span data-ttu-id="04758-155">SqlServerFqdn : atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="04758-155">SqlServerFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="04758-156">SqlInstanceName : RTC</span><span class="sxs-lookup"><span data-stu-id="04758-156">SqlInstanceName : rtc</span></span>

<span data-ttu-id="04758-157">MirrorSqlServerFqdn :</span><span class="sxs-lookup"><span data-stu-id="04758-157">MirrorSqlServerFqdn :</span></span>

<span data-ttu-id="04758-158">MirrorSqlInstanceName :</span><span class="sxs-lookup"><span data-stu-id="04758-158">MirrorSqlInstanceName :</span></span>

<span data-ttu-id="04758-159">DatabaseName : lis</span><span class="sxs-lookup"><span data-stu-id="04758-159">DatabaseName : lis</span></span>

<span data-ttu-id="04758-160">Source</span><span class="sxs-lookup"><span data-stu-id="04758-160">DataSource :</span></span>

<span data-ttu-id="04758-161">SQLServerVersion :</span><span class="sxs-lookup"><span data-stu-id="04758-161">SQLServerVersion :</span></span>

<span data-ttu-id="04758-162">ExpectedVersion : 3.1.1</span><span class="sxs-lookup"><span data-stu-id="04758-162">ExpectedVersion : 3.1.1</span></span>

<span data-ttu-id="04758-163">InstalledVersion :</span><span class="sxs-lookup"><span data-stu-id="04758-163">InstalledVersion :</span></span>

<span data-ttu-id="04758-164">Réussite : false</span><span class="sxs-lookup"><span data-stu-id="04758-164">Succeed : False</span></span>

<span data-ttu-id="04758-165">AVERTISSEMENT : Test-CsDatabase rencontré des erreurs.</span><span class="sxs-lookup"><span data-stu-id="04758-165">WARNING: Test-CsDatabase encountered errors.</span></span> <span data-ttu-id="04758-166">Consulter le fichier journal pour un</span><span class="sxs-lookup"><span data-stu-id="04758-166">Consult the log file for a</span></span>

<span data-ttu-id="04758-167">analyse détaillée et vérification de la prise en compte de toutes les erreurs (2) et avertissements (0)</span><span class="sxs-lookup"><span data-stu-id="04758-167">detailed analysis, and to make sure that all errors (2) and warnings (0) are addressed</span></span>

<span data-ttu-id="04758-168">avant de continuer.</span><span class="sxs-lookup"><span data-stu-id="04758-168">before continuing.</span></span>

<span data-ttu-id="04758-169">AVERTISSEMENT : les résultats détaillés sont disponibles à l’adresse</span><span class="sxs-lookup"><span data-stu-id="04758-169">WARNING: Detailed results can be found at</span></span>

<span data-ttu-id="04758-170">"C : \\ Users \\ testing \\ AppData \\ local \\ temp \\ 2 \\ test-applet csdatabase-b18d488a-8044-4679-bbf2-</span><span class="sxs-lookup"><span data-stu-id="04758-170">"C:\\Users\\Testing\\AppData\\Local\\Temp\\2\\Test-CsDatabase-b18d488a-8044-4679-bbf2-</span></span>

<span data-ttu-id="04758-171">04d593cce8e6.html».</span><span class="sxs-lookup"><span data-stu-id="04758-171">04d593cce8e6.html".</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="04758-172">Raisons pour lesquelles le test a pu échouer</span><span class="sxs-lookup"><span data-stu-id="04758-172">Reasons why the test might have failed</span></span>

<span data-ttu-id="04758-173">Voici quelques-unes des causes courantes de l’échec **de test-applet csdatabase** :</span><span class="sxs-lookup"><span data-stu-id="04758-173">Here are some common reasons why **Test-CsDatabase** might fail:</span></span>

  - <span data-ttu-id="04758-174">Une valeur de paramètre incorrecte a été fournie.</span><span class="sxs-lookup"><span data-stu-id="04758-174">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="04758-175">Si ce paramètre est utilisé, les paramètres facultatifs doivent être configurés correctement ou le test échoue.</span><span class="sxs-lookup"><span data-stu-id="04758-175">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="04758-176">Réexécutez la commande sans les paramètres facultatifs et vérifiez si elle réussit.</span><span class="sxs-lookup"><span data-stu-id="04758-176">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="04758-177">Cette commande échoue si la base de données n’est pas configurée correctement ou n’est pas encore déployée.</span><span class="sxs-lookup"><span data-stu-id="04758-177">This command will fail if the database is misconfigured or not yet deployed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="04758-178">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="04758-178">See Also</span></span>


[<span data-ttu-id="04758-179">Get-CsDatabaseMirrorState</span><span class="sxs-lookup"><span data-stu-id="04758-179">Get-CsDatabaseMirrorState</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsDatabaseMirrorState)  
[<span data-ttu-id="04758-180">Get-CsService</span><span class="sxs-lookup"><span data-stu-id="04758-180">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
[<span data-ttu-id="04758-181">Get-CsUserDatabaseState</span><span class="sxs-lookup"><span data-stu-id="04758-181">Get-CsUserDatabaseState</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsUserDatabaseState)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

